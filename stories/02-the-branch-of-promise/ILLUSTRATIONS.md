# Book 2: The Branch of Promise — Illustration Specifications

## Style Direction

- **Interior:** Simple black-and-white line drawings. Clean composition with a single clear focal point per illustration. Minimal background detail — suggest setting with a few confident strokes rather than filling every inch. Think classic chapter-book illustrations: evocative, not exhaustive.
- **Cover:** Full color, but restrained. Limited palette (warm golds, dusty browns, bronze tones against a cool blue sky). One strong composition, not a collage of elements. The cover should feel like a moment, not a summary.
- **Line weight:** Medium, with variation for depth and emphasis. Heavier lines for foreground subjects, lighter for environmental suggestion.
- **Characters:** Semi-realistic. Not cartoonish, not photorealistic. Must be recognizable and consistent across all 12 books. Establish model sheets with the illustrator before beginning.
- **The Fade:** When present, represented as an oppressive clarity — the sky too bright, the light too perfect. In B&W line art, this can be suggested by leaving the background aggressively empty, with sharp, hard lines that make the scene feel sterile rather than natural.
- **The Pathfinder:** Consistent design in every appearance. Two symbols now complete (stone and branch by end of book). Incomplete symbols are faint, rough sketches; completed symbols are sharp, polished, with colored enamel and a faint glow.

---

## Cover Art (Full Color)

**Scene:** The three kids on the rain-soaked deck of a massive ancient wooden ark, gripping the railing as storm waves crash around them. A white dove flies toward them through breaking clouds, carrying a small olive branch that glows faintly in its beak. First rays of golden light pierce the dark storm clouds above.

**Mood:** Awe and relief breaking through endurance. The storm is receding, not arriving. The golden light is winning.

**Composition:** The kids in the foreground, the dove approaching from above right, the Ark's hull suggesting massive scale beneath them. The sky dominates the upper half — dark clouds parting to reveal gold. The dove and branch are the focal point.

**Series elements:** The Pathfinder visible at Eli's belt or tucked under his arm. Series title treatment and book number. Consistent spine design.

**What to avoid:** Don't show the whole Ark. Don't show the flood waters receding to reveal mountains. Don't crowd the composition with animals. One moment, one feeling.

---

## Interior Illustrations (8 x B&W Line Art)

### Illustration 1 — "The Pathfinder Activates"
**Placement:** Chapter 1, when the Pathfinder glows and the branch symbol trembles
**Scene:** Close-up of the Pathfinder on the desk. The first symbol (the stone) glows sharp and bright. The second symbol, a rough sketch of a branch, trembles and blurs, its faint lines shivering in the bronze. Light spreads outward from the center like ripples. Eli leans close, studying it intently.
**Focus:** The Pathfinder and the trembling symbol. The anticipation before departure.
**Size:** Quarter-page, centered

### Illustration 2 — "The Builder"
**Placement:** Chapter 2, when the kids first see Noah working on the Ark
**Scene:** An old man with a grey beard drives a wooden peg into a massive timber joint with a mallet. His sleeves are rolled up, his hands scarred and steady. He is alone in the frame, focused entirely on the work. The scale of the timber suggests something enormous being built, but only the joint and the man are visible.
**Focus:** Noah's steady hands and the mallet striking the peg. A portrait of endurance and commitment.
**Size:** Half-page

### Illustration 3 — "The Mockery"
**Placement:** Chapter 3, the settlement mocking Noah
**Scene:** Elena stands rigid, fists clenched at her sides, watching something off-frame. Her jaw is tight and her whole body radiates fury. Behind her, barely suggested, the curved shape of the Ark's hull rises.
**Focus:** Elena's body language — the anger on behalf of someone being mocked. Her clenched fists are the focal point.
**Size:** Quarter-page

### Illustration 4 — "The Animals Arrive"
**Placement:** Chapter 4, pairs of animals approaching the Ark
**Scene:** A pair of deer stand at the edge of a tree line, facing forward with calm patience. Behind them in the shadows, other animal shapes are suggested — large and small, moving in the same direction. The deer are still and dignified, like passengers waiting.
**Focus:** The deer pair and the sense of purposeful movement behind them. Calm, not chaotic.
**Size:** Half-page

### Illustration 5 — "The Door Closes"
**Placement:** Chapter 4, when the Ark's door seals shut
**Scene:** The interior of the Ark, looking toward the massive door as it rises and seals against the hull. A thin line of fading daylight narrows to nothing along the door's edge. Noah stands with his hands at his sides, watching. His sons are visible behind him. No one is touching the door.
**Focus:** The closing door and the last sliver of light. The finality of the moment.
**Size:** Half-page

### Illustration 6 — "Noah's Question"
**Placement:** Chapter 5, Noah alone in the dark Ark, whispering to a support beam
**Scene:** An old man stands alone in a dark corridor, one hand pressed against a thick timber beam. A single swaying oil lamp casts deep shadows. His head is bowed, his shoulders hunched. His lips are moving.
**Focus:** Noah's solitary figure and the single lamp. Isolation, doubt, and the decision to keep believing.
**Size:** Half-page

### Illustration 7 — "The Dove Returns"
**Placement:** Chapter 7, the dove lands on the window ledge with the olive branch
**Scene:** A white dove perched on a wooden window ledge, an olive branch with fresh green leaves in her beak. The branch glows faintly. Beyond the window, the sky is golden with late afternoon light. The dove is small and delicate against the massive timber frame.
**Focus:** The dove, the branch, and the light. A small, living thing carrying proof of a promise kept.
**Size:** Quarter-page, centered

### Illustration 8 — "The Second Symbol"
**Placement:** Chapter 8, after the return
**Scene:** Close-up of the Pathfinder on the desk. Two symbols now glow — the stone (amber) and the branch (green, living green like a leaf held to sunlight). The other ten remain faint scratches. Eli's empty hands hover above the device. Jordan stands nearby, arms not crossed for once, looking at the Pathfinder with something other than skepticism.
**Focus:** The two completed symbols and the contrast with the ten unfinished ones. The growing pattern.
**Size:** Half-page

---

## AI Concept Art Notes

For each illustration, generate 2-3 concept images using image generation tools to provide the illustrator with:
- Composition and framing direction
- Character positioning and body language
- Mood and lighting reference

Annotate each AI reference image with notes on what to keep and what to change. The illustrator should interpret the concepts in their own consistent style, not reproduce the AI output.

### ComfyUI Pipeline

All AI-generated concept art is produced via ComfyUI with Flux.1-dev. See `comfyui/README.md` for full setup instructions.

- **Cover prompt:** `comfyui/prompts/covers/book-02-branch-of-promise.txt`
- **Interior prompts:** `comfyui/prompts/interiors/book-02/` (8 files, one per illustration)
- **Character LoRAs:** Trained per-character for consistency — see `comfyui/training/README.md`
- **Workflows:** Build interactively in ComfyUI GUI using settings documented in `comfyui/workflows/`

## Consistency Notes (Apply to All 12 Books)

- **The Fade:** In Book 2, the Fade manifests as oppressive clarity and normalcy — everything too bright, too perfect, too obviously fine. In the interior B&W art, this is suggested by sterile emptiness and hard-edged lines at the margins.
- **The Pathfinder:** Same design in every appearance. Book 2 begins with 1 glowing symbol (stone) and ends with 2 (stone + branch). Incomplete symbols are faint, rough engravings; completed symbols are sharp, polished, colored, and glowing.
- **Characters:** Consistent clothing, hair, build across all books. Establish model sheets before beginning illustration work.
