# ComfyUI Illustration Pipeline — Covenant Keepers

## Overview

This pipeline generates two types of AI illustrations for the 12-book Covenant Keepers series:

1. **Cover art** (12 total): Full-color vintage painted style (1970s adventure paperback aesthetic). Wrap-around format for front/spine/back.
2. **Interior line art** (8 per book, 96 total): Black-and-white pen-and-ink chapter illustrations.

Character consistency across all 12 books is maintained through custom LoRAs trained on curated character images.

## Hardware

- **DGX Spark** — 128 GB unified memory (no VRAM constraints)
- ComfyUI with Flux.1-dev already installed

## Required Models

### Base Model

- **Flux.1-dev** (fp16) — already installed

### Style LoRAs

Download these from CivitAI and place in `ComfyUI/models/loras/`:

**For covers (vintage painted style):**

| Model | CivitAI Link | Notes |
|-------|-------------|-------|
| Vintage Fantasy Illustration (Flux) | https://civitai.com/models/1320787 | Richly detailed, hand-painted textures, warm nostalgic palette |
| Vintage Illustration / Western Art Style (Flux) | https://civitai.com/models/1147172 | Classic adventure illustration look |

**For interiors (B&W line art):**

| Model | CivitAI Link | Notes |
|-------|-------------|-------|
| Lineart (Flux/SDXL) | https://civitai.com/models/539031 | Multi-model lineart LoRA |
| Vintage Engraving Book Illustration | https://civitai.com/models/486564 | Vintage book illustration charm |

### Character LoRAs (trained locally)

After completing the bootstrap and training process (see `training/README.md`), place the character LoRAs in `ComfyUI/models/loras/`:

- `eli-castillo.safetensors` — activation token: `eli_castillo`
- `elena-castillo.safetensors` — activation token: `elena_castillo`
- `jordan-park.safetensors` — activation token: `jordan_park`
- `abuelo-castillo.safetensors` — activation token: `abuelo_castillo`

## Required Custom Nodes

Install via ComfyUI Manager or clone into `ComfyUI/custom_nodes/`:

| Node Pack | Repository | Purpose |
|-----------|-----------|---------|
| ComfyUI_IPAdapter_plus | `cubiq/ComfyUI_IPAdapter_plus` | IP-Adapter for reference images |
| ComfyUI-PuLID-Flux-Enhanced | `sipie800/ComfyUI-PuLID-Flux-Enhanced` | PuLID for character bootstrapping |
| ComfyUI-IPAdapter-Flux | `Shakker-Labs/ComfyUI-IPAdapter-Flux` | Flux-specific IP-Adapter |
| ComfyUI-Book-Tools | `Big-Idea-Technology/ComfyUI-Book-Tools` | Book production utilities |

## Workflow Overview

### Phase 1a: Initial Character Generation (no PuLID)

Since these are fictional characters, the very first batch has no reference face — PuLID can't help yet. Start with pure text-to-image generation.

**Build this workflow in the ComfyUI GUI (node → connection → node):**

1. **Load Diffusion Model** (UNETLoader) → `flux1-dev.safetensors`, weight_dtype: `default`
2. **DualCLIPLoader** → clip_name1: `t5xxl_fp16.safetensors`, clip_name2: `clip_l.safetensors`, type: `flux`
   - This loads the two text encoders Flux requires. **Not** PuLID — that has its own loader.
3. **VAELoader** → `ae.safetensors`
4. **CLIPTextEncode** (positive) → connect CLIP output from DualCLIPLoader → paste **only** the character prompt from `prompts/characters/<name>.txt`. Do **not** add the cover style keywords here — those overpower the character description and produce adventure scenes instead of portraits. You can optionally prepend "portrait of" and append ", plain background" to steer composition.
5. **CLIPTextEncode** (negative) → connect same CLIP output → use a minimal negative: `blurry, low quality, deformed hands, extra fingers, deformed fingers`. Do **not** use `prompts/covers/style-negative.txt` here — save that for Phase 2/3.
6. *(Optional, not recommended for first pass)* **LoraLoader** → connect between Load Diffusion Model and KSampler model inputs → select vintage style LoRA, strength_model: `0.6`, strength_clip: `0.6`. Style LoRAs can overpower character features — try without one first, then add if needed.
7. **EmptyLatentImage** → width: `768`, height: `1024`, batch_size: `1`
8. **KSampler** → connect model (from Load Diffusion Model or LoraLoader), positive/negative conditioning, latent_image from EmptyLatentImage → steps: `30`, cfg: `3.5`, sampler_name: `euler`, scheduler: `normal`, seed: vary per generation
9. **VAEDecode** → connect samples output from KSampler + VAE from VAELoader
10. **SaveImage** → connect image output from VAEDecode

**Workflow:**
```
Load Diffusion Model ──→ (optional LoraLoader) ──→ KSampler ──→ VAEDecode ──→ SaveImage
DualCLIPLoader ──→ CLIPTextEncode (pos) ──→ KSampler (positive)
                ──→ CLIPTextEncode (neg) ──→ KSampler (negative)
VAELoader ──→ VAEDecode (vae)
EmptyLatentImage ──→ KSampler (latent_image)
```

Generate 30-40 images per character. Keep the seed set to "randomize" and queue multiple runs. After the first 10-15 portraits, start appending pose/angle variations to the character prompt to build a diverse training set — e.g., "3/4 view", "profile view", "looking down at book", "smiling warmly", "serious expression", "outdoors in natural light", "sitting at desk". Pick the 1-3 best faces — these become your reference for Phase 1b.

Save this workflow to `workflows/character-bootstrap-text-only.json` via ComfyUI's menu (Workflow → Export).

### Phase 1b: PuLID-Guided Refinement

Now that you have a good reference face, add PuLID nodes to enforce face consistency across more variations.

**Add these nodes to the Phase 1a workflow:**

1. **PulidFluxModelLoader** → `pulid_flux_v0.9.0.safetensors`
2. **PulidFluxEvaClipLoader** → loads the EVA02-CLIP model (downloads automatically on first run)
3. **PulidFluxInsightFaceLoader** → provider: `CPU` (or `CUDA`) — loads the AntelopeV2 face analysis model
4. **LoadImage** → select your best reference face from Phase 1a
5. **ApplyPulidFlux** → connect:
   - `model` ← from Load Diffusion Model (or LoraLoader output)
   - `pulid` ← from PulidFluxModelLoader
   - `eva_clip` ← from PulidFluxEvaClipLoader
   - `face_analysis` ← from PulidFluxInsightFaceLoader
   - `ref_image` ← from LoadImage
   - Settings: weight: `0.3`, start_at: `0.0`, end_at: `1.0`
   - Output `model` → connects to KSampler (replacing the direct model connection)

**Updated workflow:**
```
Load Diffusion Model ──→ (LoraLoader) ──→ ApplyPulidFlux ──→ KSampler ──→ VAEDecode ──→ SaveImage
PulidFluxModelLoader ──→ ApplyPulidFlux (pulid)
PulidFluxEvaClipLoader ──→ ApplyPulidFlux (eva_clip)
PulidFluxInsightFaceLoader ──→ ApplyPulidFlux (face_analysis)
LoadImage (reference face) ──→ ApplyPulidFlux (ref_image)
DualCLIPLoader ──→ CLIPTextEncode (pos/neg) ──→ KSampler
VAELoader ──→ VAEDecode
EmptyLatentImage ──→ KSampler
```

Generate 20-30 more images per character with face consistency. Curate a total of 15-20 images per character for the training dataset — these should have:
- Same face shape and features across all images
- Consistent skin tone, hair style, build
- Key distinguishing features present (glasses, bracelet, scar, etc.)
- Variety of angles and expressions (front, 3/4, profile)

Save curated images to `training/datasets/<character-name>/` and create caption `.txt` files (see `training/README.md`).

Save this workflow to `workflows/character-bootstrap-pulid.json`.

### Phase 1c: Train Character LoRAs

Train a LoRA for each character using AI-Toolkit — see `training/README.md` for full instructions.

### Phase 2: Cover Generation

Use `workflows/cover-generation.json`:

1. Load Flux.1-dev + character LoRAs + vintage style LoRA
2. Generate front cover at 2:3 portrait aspect ratio using prompts from `prompts/covers/`
3. Use `workflows/outpaint-wraparound.json` to extend leftward for spine + back cover
4. Final composite: ~2560x960 (front + spine + back)

### Phase 3: Interior Generation

Use `workflows/interior-generation.json`:

1. Load Flux.1-dev + character LoRAs + lineart style LoRA
2. Generate illustrations using prompts from `prompts/interiors/`
3. Post-process: threshold to pure B&W if needed

## Prompt Structure

Each prompt file contains the full positive prompt on one line. Shared style keywords are in separate files:

- `prompts/covers/style-positive.txt` — append to every cover prompt
- `prompts/covers/style-negative.txt` — use as negative prompt for every cover
- `prompts/interiors/style-positive.txt` — append to every interior prompt
- `prompts/interiors/book-01/style-negative.txt` — use as negative for interiors

Character LoRA activation tokens (e.g., `eli_castillo`) should be included directly in scene prompts where that character appears.

## Workflow JSON Files

The `workflows/` directory is for **saving workflows you build** in the ComfyUI GUI — there are no pre-built JSON files to load. Build each workflow interactively following the node-by-node instructions above, then export via Workflow → Export.

**Important:** Flux.1-dev uses a different architecture than SD1.5/SDXL checkpoints. You must use:
- **Load Diffusion Model** (UNETLoader) — not "Load Checkpoint" (CheckpointLoaderSimple)
- **DualCLIPLoader** — clip_name1: `t5xxl_fp16.safetensors`, clip_name2: `clip_l.safetensors`, type: `flux`
- **VAELoader** — `ae.safetensors`

These three nodes replace the single "Load Checkpoint" node used with SD1.5/SDXL models.

### Workflow Summary

| Workflow | Purpose | Key Nodes | Resolution |
|----------|---------|-----------|------------|
| `character-bootstrap-text-only.json` | Phase 1a: Initial character generation | UNETLoader + DualCLIPLoader + VAELoader + (opt. LoraLoader) + KSampler | 768x1024 |
| `character-bootstrap-pulid.json` | Phase 1b: PuLID-guided face-consistent generation | Above + PulidFluxModelLoader + PulidFluxEvaClipLoader + PulidFluxInsightFaceLoader + ApplyPulidFlux | 768x1024 |
| `cover-generation.json` | Phase 2: Full-color cover art | UNETLoader + DualCLIPLoader + VAELoader + LoraLoader x3 + KSampler (steps 40) | 832x1216 |
| `interior-generation.json` | Phase 3: B&W line art | UNETLoader + DualCLIPLoader + VAELoader + LoraLoader x2 + KSampler | 768x768 to 1024x1024 |
| `outpaint-wraparound.json` | Wrap-around cover extension | Load Image + FLUX.1 Fill (outpaint left) | 832x1216 → ~2560x1216 |

### Cover Generation Notes

- Load multiple character LoRAs simultaneously for scenes with multiple kids (chain LoraLoader nodes)
- Character LoRA weight: `0.8` (reduce to `0.6` each when loading 3+ LoRAs to prevent interference)
- Vintage style LoRA #1 weight: `0.6`, #2 weight: `0.4`
- KSampler: steps `40`, cfg `3.5`, sampler `euler`, scheduler `normal`

### Interior Generation Notes

- Character LoRA weight: `0.7`, lineart LoRA weight: `0.8`
- KSampler: steps `30`, cfg `3.5`, sampler `euler`, scheduler `normal`
- Resolutions: 768x768 (spot), 768x1024 (half-page), 1024x1024 (full-page)
- Post-processing: threshold to pure B&W if needed (image editor or threshold node in ComfyUI)

### Outpaint Notes

- Input: 832x1216 front cover → Output: ~2560x1216 (front + spine + back)
- The outpainted region naturally simplifies, ideal for back cover/spine where text will be overlaid
- May need 2-3 generations to get a clean fade

## Production Checklist (Single-Pass Workflow)

Follow this order to produce all illustrations in one focused session.

### Step 1: Install Dependencies (~30 min)
- [ ] Verify Flux.1-dev is loaded in ComfyUI
- [ ] Download 2 cover style LoRAs from CivitAI (links above)
- [ ] Download 2 interior lineart LoRAs from CivitAI (links above)
- [ ] Install 4 custom node packs via ComfyUI Manager (listed above)
- [ ] Place all LoRAs in `ComfyUI/models/loras/`

### Step 2: Bootstrap Characters (~2 hours)
- [ ] Build Phase 1a workflow in ComfyUI GUI (see node-by-node instructions above)
- [ ] For each character (Eli, Elena, Jordan, Abuelo):
  - [ ] Generate 30-40 images using `prompts/characters/<name>.txt` (Phase 1a, no PuLID)
  - [ ] Pick 1-3 best faces as reference
  - [ ] Add PuLID nodes for Phase 1b workflow, use best face as reference
  - [ ] Generate 20-30 more images with PuLID face consistency
- [ ] Curate 15-20 best images per character (consistent face, features, build)
- [ ] Save to `training/datasets/<character-name>/`
- [ ] Create `.txt` caption files for each image (activation token + description)

### Step 3: Train Character LoRAs (~4 hours)
- [ ] From the AI-Toolkit directory, run training for each character (see `training/README.md` for full paths):
  - [ ] `python run.py /full/path/to/covenant-keepers/comfyui/training/config-eli-castillo.yaml`
  - [ ] `python run.py /full/path/to/covenant-keepers/comfyui/training/config-elena-castillo.yaml`
  - [ ] `python run.py /full/path/to/covenant-keepers/comfyui/training/config-jordan-park.yaml`
  - [ ] `python run.py /full/path/to/covenant-keepers/comfyui/training/config-abuelo-castillo.yaml`
- [ ] Validate each LoRA (generate test images, check consistency)
- [ ] Copy trained `.safetensors` to `ComfyUI/models/loras/`

### Step 4: Generate Covers (~3 hours)
- [ ] Build cover-generation workflow in ComfyUI GUI (same base nodes as Phase 1a + LoraLoader chain)
- [ ] Generate covers for Books 1-12 using prompts from `prompts/covers/`
- [ ] Select best generation for each book (generate 4-8 candidates each)
- [ ] Build outpaint-wraparound workflow
- [ ] Extend each cover for wrap-around (spine + back)
- [ ] Save finals to `output/covers/`

### Step 5: Generate Interiors (~6 hours)
- [ ] Build interior-generation workflow in ComfyUI GUI (same base nodes + lineart LoRA)
- [ ] For each book (1-12), generate 8 interiors using prompts from `prompts/interiors/book-NN/`
- [ ] Select best generation for each illustration (generate 4-8 candidates each)
- [ ] Post-process: threshold to pure B&W if needed
- [ ] Save finals to `output/interiors/book-NN/`

### Step 6: Quality Review
- [ ] Verify character consistency across all 12 covers
- [ ] Verify character consistency across all 96 interiors
- [ ] Check that no illustration contains AI-generated text
- [ ] Verify each interior has a single clear focal point
- [ ] Flag any deformed hands/fingers for regeneration

**Estimated total time: ~15 hours** (can be spread across 2-3 sessions; LoRA training can run overnight)

## Directory Structure

```
comfyui/
├── README.md
├── prompts/
│   ├── characters/              # Character appearance prompts (4 files)
│   ├── covers/                  # Cover scene prompts + shared style (14 files)
│   │   ├── book-01-stone-of-courage.txt ... book-12-thorn-of-promise.txt
│   │   ├── style-positive.txt
│   │   └── style-negative.txt
│   └── interiors/               # Interior scene prompts + shared style
│       ├── style-positive.txt   # Shared positive style keywords
│       ├── book-01/             # 8 illustration prompts + style-negative.txt
│       ├── book-02/ ... book-12/
├── workflows/                   # ComfyUI workflow JSON (build in GUI, export here — no pre-built files)
└── training/                    # LoRA training config and instructions
    ├── README.md
    ├── config.yaml              # Reference/template config
    ├── config-eli-castillo.yaml
    ├── config-elena-castillo.yaml
    ├── config-jordan-park.yaml
    └── config-abuelo-castillo.yaml
```
