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

### Phase 1: Character Bootstrap

Use `workflows/character-bootstrap.json` (build interactively in ComfyUI):

1. Load Flux.1-dev + PuLID Flux II (weight ~0.3) + vintage style LoRA
2. Generate 30-40 candidate images per character using prompts from `prompts/characters/`
3. Curate 15-20 images per character that are internally consistent (same face, build, features)
4. Train character LoRAs (see `training/README.md`)

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

The JSON files in `workflows/` are best created interactively in the ComfyUI GUI and exported. Build these four workflows:

### 1. `character-bootstrap.json` — Character Image Generation
**Nodes:** Load Checkpoint (Flux.1-dev) → Apply PuLID Flux II (weight 0.3) → Apply LoRA (vintage style, weight 0.6) → CLIP Text Encode (use prompts from `prompts/characters/`) → KSampler (steps: 30, cfg: 3.5, sampler: euler, scheduler: normal) → VAE Decode → Save Image
**Resolution:** 768x1024
**Purpose:** Generate 30-40 candidate images per character for LoRA training dataset curation.

### 2. `cover-generation.json` — Full-Color Cover Art
**Nodes:** Load Checkpoint (Flux.1-dev) → Apply LoRA x3 (character LoRA weight 0.8, vintage style LoRA #1 weight 0.6, vintage style LoRA #2 weight 0.4) → CLIP Text Encode (positive from `prompts/covers/book-NN-*.txt` + `style-positive.txt`, negative from `style-negative.txt`) → KSampler (steps: 40, cfg: 3.5, sampler: euler, scheduler: normal) → VAE Decode → Save Image
**Resolution:** 832x1216 (2:3 portrait)
**Notes:** Load multiple character LoRAs simultaneously for scenes with multiple kids. Adjust character LoRA weights down to 0.6 each when loading 3+ LoRAs to prevent interference.

### 3. `interior-generation.json` — B&W Line Art
**Nodes:** Load Checkpoint (Flux.1-dev) → Apply LoRA x2 (character LoRA weight 0.7, lineart LoRA weight 0.8) → CLIP Text Encode (positive from `prompts/interiors/book-NN/*.txt` + `style-positive.txt`, negative from `style-negative.txt`) → KSampler (steps: 30, cfg: 3.5, sampler: euler, scheduler: normal) → VAE Decode → Save Image
**Resolution:** 768x768 (spot), 768x1024 (half-page), 1024x1024 (full-page)
**Post-processing:** Threshold to pure B&W if needed (Image → Adjustments → Threshold in any image editor, or add a threshold node in ComfyUI).

### 4. `outpaint-wraparound.json` — Wrap-Around Cover Extension
**Nodes:** Load Image (front cover) → FLUX.1 Fill (outpaint left, 50% extension) → Save Image
**Resolution:** Input 832x1216 → Output ~2560x1216 (front + spine + back)
**Notes:** The outpainted region naturally simplifies, which is ideal for the back cover/spine where text will be overlaid. May need 2-3 generations to get a clean fade.

## Production Checklist (Single-Pass Workflow)

Follow this order to produce all illustrations in one focused session.

### Step 1: Install Dependencies (~30 min)
- [ ] Verify Flux.1-dev is loaded in ComfyUI
- [ ] Download 2 cover style LoRAs from CivitAI (links above)
- [ ] Download 2 interior lineart LoRAs from CivitAI (links above)
- [ ] Install 4 custom node packs via ComfyUI Manager (listed above)
- [ ] Place all LoRAs in `ComfyUI/models/loras/`

### Step 2: Bootstrap Characters (~2 hours)
- [ ] Build `character-bootstrap.json` workflow in ComfyUI GUI (node graph above)
- [ ] Generate 30-40 images for Eli using `prompts/characters/eli-castillo.txt`
- [ ] Generate 30-40 images for Elena using `prompts/characters/elena-castillo.txt`
- [ ] Generate 30-40 images for Jordan using `prompts/characters/jordan-park.txt`
- [ ] Generate 30-40 images for Abuelo using `prompts/characters/abuelo-castillo.txt`
- [ ] Curate 15-20 best images per character (consistent face, features, build)
- [ ] Save to `training/datasets/<character-name>/`
- [ ] Create `.txt` caption files for each image (activation token + description)

### Step 3: Train Character LoRAs (~4 hours)
- [ ] Run `python run.py config/config-eli-castillo.yaml`
- [ ] Run `python run.py config/config-elena-castillo.yaml`
- [ ] Run `python run.py config/config-jordan-park.yaml`
- [ ] Run `python run.py config/config-abuelo-castillo.yaml`
- [ ] Validate each LoRA (generate test images, check consistency)
- [ ] Copy trained `.safetensors` to `ComfyUI/models/loras/`

### Step 4: Generate Covers (~3 hours)
- [ ] Build `cover-generation.json` workflow in ComfyUI GUI
- [ ] Generate covers for Books 1-12 using prompts from `prompts/covers/`
- [ ] Select best generation for each book (generate 4-8 candidates each)
- [ ] Build `outpaint-wraparound.json` workflow
- [ ] Extend each cover for wrap-around (spine + back)
- [ ] Save finals to `output/covers/`

### Step 5: Generate Interiors (~6 hours)
- [ ] Build `interior-generation.json` workflow in ComfyUI GUI
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
├── workflows/                   # ComfyUI workflow JSON (build in GUI, export here)
└── training/                    # LoRA training config and instructions
    ├── README.md
    ├── config.yaml              # Reference/template config
    ├── config-eli-castillo.yaml
    ├── config-elena-castillo.yaml
    ├── config-jordan-park.yaml
    └── config-abuelo-castillo.yaml
```
