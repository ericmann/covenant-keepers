# Book 3: The Thread of Forgiveness — Illustration Specifications

## Style Direction

- **Interior:** Simple black-and-white line drawings. Clean composition with a single clear focal point per illustration. Minimal background detail — suggest setting with a few confident strokes rather than filling every inch. Think classic chapter-book illustrations: evocative, not exhaustive.
- **Cover:** Full color, but restrained. Limited palette (warm golds, dusty browns, bronze tones against cool stone). One strong composition, not a collage of elements. The cover should feel like a moment, not a summary.
- **Line weight:** Medium, with variation for depth and emphasis. Heavier lines for foreground subjects, lighter for environmental suggestion.
- **Characters:** Semi-realistic. Not cartoonish, not photorealistic. Must be recognizable and consistent across all 12 books. Establish model sheets with the illustrator before beginning.
- **The Fade:** When present, represented as a grinding heaviness — colors draining, edges going grey, a weight pressing down. In B&W line art, suggest this with heavier shadows pooling at the margins, denser cross-hatching making scenes feel oppressive.
- **The Pathfinder:** Consistent design in every appearance. Three symbols complete by end of book (stone, branch, thread). Incomplete symbols are faint, rough sketches; completed symbols are sharp, polished, with colored enamel and a faint glow.

---

## Cover Art (Full Color)

**Scene:** The three kids standing in the shadows of an Egyptian palace hall with tall stone columns. In the middle distance, a richly dressed Egyptian official weeps as he reveals himself to terrified men in rougher Canaanite clothing. A single colorful thread glows faintly on the stone floor between them. Warm torchlight against cool stone walls.

**Mood:** Emotional intensity and the rawness of forgiveness. The torchlight creates warmth in a cold stone space. The moment is private and shattering.

**Composition:** The kids partially hidden behind a column in the lower foreground, looking in. Joseph and his brothers in the middle ground. The glowing thread small but visible on the floor between them. The tall columns frame the scene vertically.

**Series elements:** The Pathfinder visible at Eli's belt or in his hand. Series title treatment and book number. Consistent spine design.

**What to avoid:** Don't show the full banquet. Don't try to render all ten brothers individually. Don't show the pit, the coat, and the palace all at once. One moment, one feeling.

---

## Interior Illustrations (8 x B&W Line Art)

### Illustration 1 — "The Camp in Canaan"
**Placement:** Chapter 1, when the kids arrive on the hillside and see the tents below
**Scene:** Three kids in rough linen tunics standing on a hillside, looking down at a camp of goatskin tents nestled in the shade of a wide oak tree. Wind moves through dry grass around them. The camp is suggested with a few shapes — tent peaks, a thin line of cook smoke.
**Focus:** The kids' posture — arriving, orienting, leaning forward to understand. The landscape is wide and open.
**Size:** Half-page

### Illustration 2 — "The Coat"
**Placement:** Chapter 2, when Jacob places the coat on Joseph's shoulders
**Scene:** A boy stands with his arms slightly raised as an older man settles a richly patterned coat onto his shoulders. The coat's patterns are rendered in intricate linework — stripes and swirls suggesting vivid color even in B&W. The boy's face shows startled joy. The old man's hands are gentle on the fabric.
**Focus:** The coat itself and the gesture of giving. The patterns in the fabric should be the most detailed element in the illustration.
**Size:** Half-page

### Illustration 3 — "The Pit"
**Placement:** Chapter 3, after Joseph is thrown into the cistern
**Scene:** A dark, vertical composition looking down into a dry cistern. At the bottom, barely visible, the shape of a boy curled against the smooth stone wall. The opening above is a circle of bright sky. The walls are smooth and unclimbable.
**Focus:** The depth and the trapped figure. The contrast between the bright sky above and the darkness below.
**Size:** Half-page

### Illustration 4 — "The Bloody Coat"
**Placement:** Chapter 4, the brothers dipping the torn coat in goat's blood
**Scene:** A pair of hands pressing a torn piece of patterned fabric into a dark liquid in a clay bowl. The fabric's intricate pattern is still visible despite the tearing. The hands are rough and work-hardened. No faces visible — just the hands, the fabric, the bowl.
**Focus:** The hands and the fabric. An intimate, damning gesture. The beauty of the coat's pattern makes the destruction worse.
**Size:** Quarter-page

### Illustration 5 — "The Vizier"
**Placement:** Chapter 5, Joseph as Egypt's second-in-command
**Scene:** A tall man in Egyptian dress — shaved head, gold collar, signet ring — stands alone between polished stone columns. His posture is straight and commanding, but his jaw is slightly tight. One hand rests on a column. His face is composed but marked — the face of someone who has survived something.
**Focus:** Joseph's transformation and his armor of composure. The contrast between the powerful figure and the vulnerable boy from earlier.
**Size:** Half-page

### Illustration 6 — "The Brothers Bow"
**Placement:** Chapter 6, when the brothers bow before Joseph without recognizing him
**Scene:** Ten men prostrate on a stone floor, faces down. Viewed from above and behind a seated figure on a raised platform — we see the back of Joseph's shaved head and one clenched fist on the armrest. The brothers are small below him.
**Focus:** The clenched fist and the bowing figures. Power, recognition, and the weight of what comes next.
**Size:** Half-page

### Illustration 7 — "Joseph Weeps"
**Placement:** Chapter 7, Joseph alone in the storeroom, sliding down the wall
**Scene:** A man sits on the floor against a stone wall in a small room, his hands covering his face, shoulders shaking. His gold collar and fine Egyptian clothes are visible but crumpled. A single shaft of light falls from a doorway. He is completely alone.
**Focus:** The solitary figure and the grief. The most powerful man in the kingdom, broken open.
**Size:** Half-page

### Illustration 8 — "The Third Symbol"
**Placement:** Chapter 8, after the return
**Scene:** Close-up of the Pathfinder on the desk. Three symbols now glow — stone (amber), branch (green), and thread (multicolored shimmer rendered in B&W as intricate, woven linework). The other nine remain faint scratches. Jordan stands by the window, his back to the viewer, one hand on the glass.
**Focus:** The three completed symbols and Jordan's solitary figure at the window. The growing pattern on the Pathfinder and the boy processing what forgiveness means.
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

- **Cover prompt:** `comfyui/prompts/covers/book-03-thread-of-forgiveness.txt`
- **Interior prompts:** `comfyui/prompts/interiors/book-03/` (8 files, one per illustration)
- **Character LoRAs:** Trained per-character for consistency — see `comfyui/training/README.md`
- **Workflows:** Build interactively in ComfyUI GUI using settings documented in `comfyui/workflows/`

## Consistency Notes (Apply to All 12 Books)

- **The Fade:** In Book 3, the Fade manifests as grinding heaviness — a weight that makes cruelty feel normal and forgiveness feel impossible. In the interior B&W art, this is suggested by dense shadows and oppressive cross-hatching at the margins.
- **The Pathfinder:** Same design in every appearance. Book 3 begins with 2 glowing symbols (stone + branch) and ends with 3 (stone + branch + thread). Incomplete symbols are faint, rough engravings; completed symbols are sharp, polished, colored, and glowing.
- **Characters:** Consistent clothing, hair, build across all books. Establish model sheets before beginning illustration work.
