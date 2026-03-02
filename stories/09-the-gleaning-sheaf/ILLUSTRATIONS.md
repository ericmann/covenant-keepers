# Book 9: The Gleaning Sheaf — Illustration Specifications

## Style Direction

- **Interior:** Simple black-and-white line drawings. Clean composition with a single clear focal point per illustration. Minimal background detail — suggest setting with a few confident strokes rather than filling every inch. Think classic chapter-book illustrations: evocative, not exhaustive.
- **Cover:** Full color, but restrained. Limited palette (warm golds, harvest ambers, dusty earth tones against a pale sky). One strong composition, not a collage of elements. The cover should feel like a moment, not a summary.
- **Line weight:** Medium, with variation for depth and emphasis. Heavier lines for foreground subjects, lighter for environmental suggestion.
- **Characters:** Semi-realistic. Not cartoonish, not photorealistic. Must be recognizable and consistent across all 12 books.
- **The Fade:** In Book 9, the Fade manifests as dullness and flatness rather than fog — colors draining, everything looking washed out and unimportant. Represented in B&W as areas of emptiness and thinned linework at the margins.
- **The Pathfinder:** Consistent design in every appearance. Eight symbols glowing at the start of this book; nine by the end.

---

## Cover Art (Full Color)

**Scene:** Three children standing at the edge of a golden harvest field at sunrise, watching a young woman bent over gathering fallen grain stalks behind the harvesters. A sheaf of grain in her arms glows faintly. Rolling hills of Bethlehem farmland stretch behind.

**Mood:** Quiet dignity and warmth. The golden light should feel earned — not flashy, but steady. The woman's posture conveys determination, not defeat.

**Composition:** The kids at the left edge in three-quarter view, looking toward Ruth in the middle ground. The field stretches to the right and beyond. The glowing sheaf is the subtle focal point. Open sky above, giving the scene room to breathe.

**Series elements:** The Pathfinder visible at Eli's belt. Series title treatment and book number. Consistent spine design.

**What to avoid:** Don't crowd the field with harvesters. Don't show the town. This is about one woman, one field, one handful of grain.

---

## Interior Illustrations (8 x B&W Line Art)

### Illustration 1 — "The Pathfinder Hums"
**Placement:** Chapter 1, as the Pathfinder's hum shifts and the ninth engraving stirs
**Scene:** Close-up of the Pathfinder on the desk. Eight symbols glow with sharp detail and enamel inlay. A ninth — a faint scratch suggesting a sheaf of grain — stirs at the edge. Eli's hand reaches toward the bronze disc.
**Focus:** The contrast between the eight completed symbols and the rough ninth. The warmth of the device.
**Size:** Quarter-page, centered

### Illustration 2 — "The Road to Bethlehem"
**Placement:** Chapter 2, when Naomi and Ruth appear on the road
**Scene:** Two figures on a dusty road — one bent and grey-haired leaning on a walking stick, the other younger and straight-backed carrying a heavy bundle. They walk in silence toward a small, dust-colored town on a low ridge ahead.
**Focus:** The contrast between the two women — Naomi's grief-bent posture and Ruth's steady determination. The empty road stretching behind them.
**Size:** Half-page

### Illustration 3 — "The Gleaning"
**Placement:** Chapter 3, Ruth working the field
**Scene:** A young woman bent at the waist, one hand gathering a few stalks of barley from the ground, a small bundle under her other arm. She is alone at the edge of a harvested field. A wide gap of empty space separates her from any other figures.
**Focus:** Ruth's solitary, repetitive labor. The smallness of her bundle. The isolation.
**Size:** Half-page

### Illustration 4 — "Boaz Sees Ruth"
**Placement:** Chapter 4, when Boaz approaches Ruth
**Scene:** A broad-shouldered man with a grey-streaked beard stands a few paces from a young woman who has straightened from her gleaning, clutching her small bundle against her chest. She looks startled. He speaks with one hand extended in a gesture of welcome.
**Focus:** The moment of recognition — Boaz choosing to see Ruth when everyone else has ignored her. Ruth's tension giving way to surprise.
**Size:** Half-page

### Illustration 5 — "Elena Helps with the Grain"
**Placement:** Chapter 6, Elena slips inside to help Ruth sort grain
**Scene:** Two figures working in a dim interior — a girl kneeling on the floor, hands dusty with chaff, sorting grain alongside a young woman. A sleeping figure lies on a mat in the background. The scene is lit by a single oil lamp.
**Focus:** Elena's hands in the grain, working beside Ruth. The intimacy and quiet of the shared labor.
**Size:** Quarter-page

### Illustration 6 — "The Last Day of Harvest"
**Placement:** Chapter 7, Ruth binding her final sheaf
**Scene:** A woman standing in a harvested field, binding a thick bundle of barley stalks with a strip of cloth. The field behind her is empty stubble. Late afternoon light. She lifts the sheaf to her shoulder. A faint glow emanates from within the bundle.
**Focus:** The sheaf — thick, complete, glowing. Ruth's posture is one of quiet accomplishment.
**Size:** Half-page

### Illustration 7 — "The Fallen Stalk"
**Placement:** Chapter 7, when Eli kneels to pick up the glowing stalk
**Scene:** A boy kneeling in a harvested field, one hand reaching toward a single stalk of barley lying in the dirt, glowing with warm light. The field is bare around him — just stubble and dust. At the edges of the illustration, faint wisps suggest the Fade pressing inward.
**Focus:** Eli's hand and the glowing stalk. The contrast between the ordinary dirt and the extraordinary light.
**Size:** Half-page

### Illustration 8 — "The Ninth Symbol"
**Placement:** Chapter 8, the symbol transforms
**Scene:** Close-up of the Pathfinder on the desk. Nine symbols now glow — the newest a precise, beautiful engraving of a sheaf of barley filled with rich gold enamel. Three symbols remain faint and rough. A soft light pulses from the ninth symbol. Eli's empty hands hover above the device.
**Focus:** The ninth symbol and the contrast with the three remaining rough engravings. The growing completeness of the Pathfinder.
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

- **Cover prompt:** `comfyui/prompts/covers/book-09-gleaning-sheaf.txt`
- **Interior prompts:** `comfyui/prompts/interiors/book-09/` (8 files, one per illustration)
- **Character LoRAs:** Trained per-character for consistency — see `comfyui/training/README.md`
- **Workflows:** Build interactively in ComfyUI GUI using settings documented in `comfyui/workflows/`

## Consistency Notes (Apply to All 12 Books)

- **The Fade:** In Book 9, the Fade is subtle — a dullness, a flatness, a suggestion that nothing here is worth remembering. In B&W, represent as thinned linework and empty space at the margins. Not fog. Not darkness. Just absence.
- **The Pathfinder:** Same design in every appearance. Eight symbols glowing at start of Book 9; nine by end. Incomplete symbols are faint, rough engravings; completed symbols are sharp, polished, colored, and glowing.
- **Characters:** Consistent clothing, hair, build across all books.
