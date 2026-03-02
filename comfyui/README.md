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

The JSON files in `workflows/` are best created interactively in the ComfyUI GUI and exported. The files document the node graph settings so you can build them:

- `cover-generation.json` — Flux.1-dev + character LoRAs + style LoRA, 2:3 portrait
- `interior-generation.json` — Flux.1-dev + character LoRAs + lineart LoRA, variable aspect
- `character-bootstrap.json` — Flux.1-dev + PuLID Flux II for initial character generation
- `outpaint-wraparound.json` — FLUX.1 Fill outpainting for wrap-around covers

## Directory Structure

```
comfyui/
├── README.md
├── prompts/
│   ├── characters/          # Character appearance prompts (4 files)
│   ├── covers/              # Cover scene prompts + shared style (14 files)
│   └── interiors/           # Interior scene prompts + shared style
│       └── book-01/         # 8 illustration prompts + negative style
├── workflows/               # ComfyUI workflow JSON (build in GUI, export here)
└── training/                # LoRA training config and instructions
    ├── README.md
    └── config.yaml
```
