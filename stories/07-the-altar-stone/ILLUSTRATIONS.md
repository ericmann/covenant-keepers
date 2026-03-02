# Book 7: The Altar Stone — Illustration Specifications

## Style Direction

- **Interior:** Simple black-and-white line drawings. Clean composition with a single clear focal point per illustration. Minimal background detail — suggest setting with a few confident strokes rather than filling every inch. Think classic chapter-book illustrations: evocative, not exhaustive.
- **Cover:** Full color, but restrained. Limited palette (brilliant white-gold fire against a dark sky, rocky browns, the green of mountain oaks). One strong composition, not a collage of elements. The cover should feel like a moment, not a summary.
- **Line weight:** Medium, with variation for depth and emphasis. Heavier lines for foreground subjects, lighter for environmental suggestion.
- **Characters:** Semi-realistic. Not cartoonish, not photorealistic. Must be recognizable and consistent across all 12 books.
- **The Fade:** Aggressive in Book 7. Arrives early and thick. After the fire, it shifts from fog to intrusive rationalizations. Visually, show it as a pervasive grey wash that retreats dramatically from the fire.
- **The Pathfinder:** Seven symbols complete by end of book. Incomplete symbols are faint, rough sketches; completed symbols are sharp, polished, with colored enamel and a faint glow.

---

## Cover Art (Full Color)

**Scene:** The three kids on a mountaintop watching fire fall from the sky onto a stone altar drenched with water. The flames consume the altar completely, impossibly bright against a darkening sky. A lone prophet stands with arms raised before the fire. Rocky, barren mountaintop of Carmel.

**Mood:** Overwhelming awe. The fire is the most vivid, real thing in the frame — everything else pales beside it. This is the moment when God answers.

**Composition:** Elijah in the middle ground, arms raised, silhouetted against the fire. The kids in the lower foreground, shielding their eyes but unable to look away. The fire is the centerpiece — a column of white-gold descending from above.

**Series elements:** The Pathfinder partially visible on Eli. Series title treatment and book number. Consistent spine design.

**What to avoid:** Don't show the prophets of Baal or the crowd — keep the focus on the altar, the fire, and the prophet. Don't make the fire look like a natural blaze; this is divine fire, unnaturally bright and consuming.

---

## Interior Illustrations (8 × B&W Line Art)

### Illustration 1 — "Eli's Notebook"
**Placement:** Chapter 1, when Eli reviews his notes
**Scene:** Close-up of Eli's hand holding an open notebook. His tight, slanted handwriting is visible — rules listed, a question underlined twice. The Pathfinder glows faintly in the background on the desk, six symbols sharp and bright.
**Focus:** The notebook and Eli's hand. This is about the thinker trying to plan for something that can't be planned. The handwriting and the underlined question tell the story.
**Size:** Quarter-page

### Illustration 2 — "The Summit of Carmel"
**Placement:** Chapter 2, arriving at the mountain
**Scene:** Wide landscape view from a ridge looking down — a valley on one side, the sea on the other. Crowds stream up a road along the mountain spine. At the summit, a broad flat clearing of exposed rock. Wind-bent oaks ring the edges.
**Focus:** The geography and scale. This is a natural amphitheater — a stage set for a confrontation. The crowd is suggested, not detailed.
**Size:** Half-page

### Illustration 3 — "Elijah Alone"
**Placement:** Chapter 3, when Elijah faces the crowd
**Scene:** Elijah standing alone at one end of the summit clearing. He is lean, sunburnt, wearing rough animal hide. His hair is wild and matted. His eyes burn with certainty. His hands are shaking. At the far end, a wall of robed prophets is suggested by a few figures.
**Focus:** Elijah's isolation and fierce resolve. The trembling hands and the burning eyes — terrified and absolutely certain at the same time.
**Size:** Half-page

### Illustration 4 — "The Frenzy"
**Placement:** Chapter 4, the prophets of Baal screaming
**Scene:** A single prophet of Baal, arms raised, mouth open in a desperate shout, robes torn, sweat and exhaustion on his face. He screams at an empty sky. The sky above is blank — featureless, indifferent, nothing.
**Focus:** The desperation of a man calling into emptiness. One figure against a void. The contrast between the man's intensity and the sky's indifference is the entire illustration.
**Size:** Half-page

### Illustration 5 — "Twelve Stones and Water"
**Placement:** Chapter 5, when Elijah builds the altar
**Scene:** Elijah kneeling, placing a stone onto a rough altar. Water pours from a large jar held by a servant, soaking the wood and stones. A trench around the base is filling with water. The altar is rough, unpolished — twelve stones stacked with care.
**Focus:** Elijah's hands on the stone and the water pouring over the impossible sacrifice. The absurdity of drenching an altar you want to burn.
**Size:** Half-page

### Illustration 6 — "The Fire Falls"
**Placement:** Chapter 6, the moment fire descends
**Scene:** A column of fire descending from above onto the altar. The fire is dense, absolute — cross-hatching rendered as white space to suggest blinding light. The altar is being consumed. Steam rises from the trench. At the very edges of the frame, wisps of grey fog are shredding apart.
**Focus:** The fire itself. This is the centerpiece illustration of the book. The fire should dominate the page — pure, total, consuming. The Fade tearing apart at the margins.
**Size:** Full-page

### Illustration 7 — "The Altar Stone Glows"
**Placement:** Chapter 7, when Eli finds the relic
**Scene:** Eli kneeling at the edge of a scorch mark on the ground. His hand reaches toward a single small stone, the size of a fist, sitting in the ashes. The stone glows with faint amber light. The ground around it is blackened. Everything else is gone.
**Focus:** Eli's reaching hand and the glowing stone in the ash. The contrast between the destroyed altar and this one surviving, glowing remnant.
**Size:** Quarter-page

### Illustration 8 — "The Seventh Note"
**Placement:** Chapter 8, when the altar stone symbol transforms
**Scene:** Close-up of the Pathfinder on Abuelo's desk. Seven symbols glow — the newest, an altar stone, sharp and polished with warm amber enamel. The other five remain faint scratches. Eli stands behind the desk, hands at his sides, shaking slightly.
**Focus:** The seven glowing symbols — more than half complete. The melody is almost forming. The five empty spaces feel more urgent now.
**Size:** Half-page

---

## AI Concept Art Notes

For each illustration, generate 2–3 concept images using image generation tools to provide the illustrator with:
- Composition and framing direction
- Character positioning and body language
- Mood and lighting reference

Annotate each AI reference image with notes on what to keep and what to change. The illustrator should interpret the concepts in their own consistent style, not reproduce the AI output.

### ComfyUI Pipeline

All AI-generated concept art is produced via ComfyUI with Flux.1-dev. See `comfyui/README.md` for full setup instructions.

- **Cover prompt:** `comfyui/prompts/covers/book-07-altar-stone.txt`
- **Interior prompts:** `comfyui/prompts/interiors/book-07/` (8 files, one per illustration)
- **Character LoRAs:** Trained per-character for consistency — see `comfyui/training/README.md`
- **Workflows:** Build interactively in ComfyUI GUI using settings documented in `comfyui/workflows/`

## Consistency Notes (Apply to All 12 Books)

- **The Fade:** In Book 7, the Fade shifts tactics — after the fire, it can no longer erase the event, so it tries to reinterpret it. "It was just lightning." Visually, this is harder to show. Before the fire, use thick grey fog. After the fire, the fog is gone but suggest unease through uncertain expressions and hesitant postures.
- **The Pathfinder:** Same design in every appearance. Book 7 begins with 6 completed symbols and ends with 7. Incomplete symbols are faint, rough engravings; completed symbols are sharp, polished, colored, and glowing.
- **Characters:** Consistent clothing, hair, build across all books. Eli's self-doubt should show in his posture — hunched shoulders, hands in pockets or folded. Jordan's walls continue to lower.
