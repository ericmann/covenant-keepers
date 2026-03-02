# LoRA Training — Character Consistency

## Overview

Each main character gets a custom LoRA trained on 15-20 curated images. This bakes character identity into the model so every generation is consistent without fighting the style LoRA.

**Tool boundaries:** ComfyUI handles image generation (Phases 1-3). AI-Toolkit handles LoRA training (this document). They are separate tools with separate installs — AI-Toolkit does not run inside ComfyUI.

## Prerequisites

- [AI-Toolkit](https://github.com/ostris/ai-toolkit) installed (cloned and set up separately from ComfyUI)
- Flux.1-dev base model
- 15-20 curated character images per character (from the bootstrap phase — see `../README.md` Phases 1a/1b)

## Bootstrap Process (Generating Training Data)

Since these are fictional illustrated characters, we bootstrap from text descriptions using a two-pass approach. All image generation is done in **ComfyUI** — see `../README.md` for detailed node-by-node workflow instructions.

### Pass 1: Text-Only Generation (Phase 1a)

Generate initial candidates without PuLID (no reference face exists yet):

1. Build the Phase 1a workflow in ComfyUI (UNETLoader + DualCLIPLoader + VAELoader + CLIPTextEncode + KSampler + VAEDecode + SaveImage — see `../README.md` for exact node wiring)
2. Use the character prompt from `../prompts/characters/<name>.txt`
3. Generate 30-40 candidate images per character at 768x1024
4. Pick the 1-3 best faces — these become your reference for Pass 2

### Pass 2: PuLID-Guided Refinement (Phase 1b)

Use the best face from Pass 1 as a reference to enforce consistency:

1. Add PuLID nodes to the workflow (PulidFluxModelLoader + PulidFluxEvaClipLoader + PulidFluxInsightFaceLoader + ApplyPulidFlux — see `../README.md` Phase 1b)
2. Load your best reference face via LoadImage node
3. ApplyPulidFlux weight: `0.3`, start_at: `0.0`, end_at: `1.0`
4. Generate 20-30 more images per character

### Curate the Dataset

From both passes, curate 15-20 images per character that are internally consistent:
- Same face shape and features across all images
- Consistent skin tone, hair style, build
- Key distinguishing features present (glasses, bracelet, scar, etc.)
- Variety of angles and expressions (front, 3/4, profile)

Save curated images to `datasets/<character-name>/` (one folder per character).
Create caption files (same filename with `.txt` extension) containing the activation token.

## Training

Per-character configs are provided — one for each character. Run these from the **AI-Toolkit** directory, passing the full path to the config file in this repository:

```bash
cd /path/to/ai-toolkit

python run.py /path/to/covenant-keepers/comfyui/training/config-eli-castillo.yaml
python run.py /path/to/covenant-keepers/comfyui/training/config-elena-castillo.yaml
python run.py /path/to/covenant-keepers/comfyui/training/config-jordan-park.yaml
python run.py /path/to/covenant-keepers/comfyui/training/config-abuelo-castillo.yaml
```

Replace `/path/to/ai-toolkit` and `/path/to/covenant-keepers` with your actual paths. AI-Toolkit's `run.py` expects to be run from its own directory.

Or use Flux Gym for a GUI-based workflow. Each config has character-appropriate sample prompts for validation during training.

## Training Configuration

See `config.yaml` for the full template. Key settings:

| Parameter | Value | Notes |
|-----------|-------|-------|
| Base model | Flux.1-dev | fp16 |
| Network type | LoRA | Standard LoRA, not LoCon |
| Rank | 32 | Good balance of quality and file size |
| Alpha | 16 | Alpha = rank/2 is standard |
| Learning rate | 1e-4 | Standard for character LoRAs |
| Epochs | 12 | Monitor for overfitting after epoch 8 |
| Image repeats | 15 | Compensates for small dataset |
| Batch size | 1 | Can increase on DGX Spark but 1 is proven |
| Resolution | 768, 1024 | Multi-resolution training |
| Optimizer | AdamW8bit | Memory-efficient |

## Output

Trained LoRAs are saved to:

- `eli-castillo.safetensors` — activation token: `eli_castillo`
- `elena-castillo.safetensors` — activation token: `elena_castillo`
- `jordan-park.safetensors` — activation token: `jordan_park`
- `abuelo-castillo.safetensors` — activation token: `abuelo_castillo`

Copy these to `ComfyUI/models/loras/` for use in the cover and interior workflows.

## Validation

After training, validate each LoRA:

1. Load the LoRA in ComfyUI at weight 0.8-1.0
2. Generate the character in multiple poses and settings
3. Verify facial features, build, and distinguishing details remain consistent
4. Test with both the cover style LoRA and the interior lineart LoRA
5. If features drift, add more training images or adjust epochs

## Caption Format

Each image in the training dataset needs a matching `.txt` caption file:

```
eli_castillo, 12-year-old Latino boy, warm brown skin, thick dark brown wavy hair, brown eyes, lean build, worn khaki field jacket, [describe pose/action in this specific image]
```

The activation token must appear first. Include character-specific details plus a description of what's happening in that particular image.
