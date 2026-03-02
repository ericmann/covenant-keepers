# LoRA Training — Character Consistency

## Overview

Each main character gets a custom LoRA trained on 15-20 curated images. This bakes character identity into the model so every generation is consistent without fighting the style LoRA.

## Prerequisites

- [AI-Toolkit](https://github.com/ostris/ai-toolkit) installed
- Flux.1-dev base model
- 15-20 curated character images per character (from the bootstrap phase)

## Bootstrap Process (Generating Training Data)

Since these are fictional illustrated characters, we bootstrap from text descriptions:

1. Open `workflows/character-bootstrap.json` in ComfyUI
2. Load Flux.1-dev + PuLID Flux II (weight ~0.3) + vintage style LoRA
3. Use the character prompt from `prompts/characters/<name>.txt`
4. Generate 30-40 candidate images per character at 768x1024
5. Curate the best 15-20 images that are internally consistent:
   - Same face shape and features across all images
   - Consistent skin tone, hair style, build
   - Key distinguishing features present (glasses, bracelet, scar, etc.)
   - Variety of angles and expressions (front, 3/4, profile)
6. Save curated images to `training/datasets/<character-name>/` (one folder per character)
7. Create caption files (same filename with `.txt` extension) containing the activation token

## Training

Per-character configs are provided — one for each character:

```bash
python run.py config/config-eli-castillo.yaml
python run.py config/config-elena-castillo.yaml
python run.py config/config-jordan-park.yaml
python run.py config/config-abuelo-castillo.yaml
```

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
