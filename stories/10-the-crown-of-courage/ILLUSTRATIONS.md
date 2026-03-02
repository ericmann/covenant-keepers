# Book 10: The Crown of Courage — Illustration Specifications

## Style Direction

- **Interior:** Simple black-and-white line drawings. Clean composition with a single clear focal point per illustration. Minimal background detail — suggest setting with a few confident strokes rather than filling every inch. Think classic chapter-book illustrations: evocative, not exhaustive.
- **Cover:** Full color, but restrained. Limited palette (deep sapphire blues, palace golds, rich purples against warm amber torchlight). One strong composition, not a collage of elements. The cover should feel like a moment, not a summary.
- **Line weight:** Medium, with variation for depth and emphasis. Heavier lines for foreground subjects, lighter for environmental suggestion.
- **Characters:** Semi-realistic. Not cartoonish, not photorealistic. Must be recognizable and consistent across all 12 books.
- **The Fade:** In Book 10, the Fade amplifies real fear rather than creating supernatural dread. Colors drain from palace tiles. Torches dim. Shadows lengthen. In B&W, represented as deepening shadows and loss of detail at the margins.
- **The Pathfinder:** Consistent design in every appearance. Nine symbols glowing at the start of this book; ten by the end.

---

## Cover Art (Full Color)

**Scene:** Three children hidden behind a palace curtain, watching a young queen in royal robes walking alone down a long ornate hall toward a distant throne where a king sits. The hall is vast, the queen small but resolute. A jewel from her crown catches the light and glows faintly. Persian palace architecture with tall carved columns.

**Mood:** Tension and courage. The enormous empty space between queen and throne is the story. The light is warm amber torchlight, but the shadows are deep.

**Composition:** The kids in the left foreground, partially obscured by a curtain. Esther in the middle ground, a small figure walking toward the distant throne. The hallway's columns create strong perspective lines. The glowing jewel is a subtle focal point.

**Series elements:** The Pathfinder visible at Eli's belt. Series title treatment and book number. Consistent spine design.

**What to avoid:** Don't show the crowd of courtiers. Don't show Haman. This is about one woman, one hallway, one walk.

---

## Interior Illustrations (8 x B&W Line Art)

### Illustration 1 — "The Pathfinder Pulls"
**Placement:** Chapter 1, when the Pathfinder vibrates and slides across the desk
**Scene:** The Pathfinder sitting on a leather cloth on a desk, vibrating visibly — suggested by motion lines. Nine symbols glow on its surface. The bronze disc has slid to one edge of the cloth. A boy's hand pushes it back toward center.
**Focus:** The restless movement of the device. The urgency in its pull.
**Size:** Quarter-page, centered

### Illustration 2 — "The Palace of Susa"
**Placement:** Chapter 2, upon arrival in the Persian palace
**Scene:** A vast hallway lined with towering carved columns, the floor paved with patterned tiles. Three children in rough tunics stand dwarfed by the architecture, looking up in awe. The perspective lines draw the eye deep into the corridor.
**Focus:** The scale of the palace — the children tiny against the monumental architecture. The oppressive grandeur.
**Size:** Full-page or three-quarter page

### Illustration 3 — "Mordecai Refuses to Bow"
**Placement:** Chapter 2, when Mordecai remains standing as Haman passes
**Scene:** A sea of people bowed low, foreheads to the ground. A single older man remains upright among them, weathered and plainly dressed, his face steady and quiet. He stands like a post in a flattened field.
**Focus:** The contrast — one figure standing among hundreds bowing. The quiet defiance.
**Size:** Half-page

### Illustration 4 — "Mordecai in Sackcloth"
**Placement:** Chapter 3, Mordecai mourning at the palace gate
**Scene:** An older man sitting in torn clothes and ashes at the base of a massive gate. His face is streaked with tears and dirt. He rocks forward, hands on his knees. The gate towers above him.
**Focus:** Mordecai's grief against the cold indifference of the palace architecture. Raw mourning versus stone.
**Size:** Half-page

### Illustration 5 — "Esther Prepares"
**Placement:** Chapter 5, Esther being dressed in her royal robes
**Scene:** A young woman standing before a polished bronze mirror while a handmaid drapes a robe across her shoulders. A crown with a single jewel sits on a table nearby. The woman's hands are trembling — suggested by light motion lines at her fingers.
**Focus:** The trembling hands. The crown waiting. The weight of the moment on a single person.
**Size:** Half-page

### Illustration 6 — "The Longest Walk"
**Placement:** Chapter 6, Esther walking the corridor toward the throne room
**Scene:** A lone woman in royal robes walking down a long, straight corridor lined with columns. She is small in the frame. The corridor stretches ahead of her toward a distant archway of light. Her chin is slightly lifted. Her back is straight.
**Focus:** The empty corridor and the solitary figure. The distance between her and the archway. Every step a choice.
**Size:** Full-page

### Illustration 7 — "The Scepter"
**Placement:** Chapter 6, the king extends the gold scepter
**Scene:** Close-up of a gold scepter extended from the right edge of the frame. A woman's hand reaches toward it, fingers trembling. The tip of the scepter catches the light. Only the hand and the scepter are in sharp focus.
**Focus:** The two hands — the king's scepter and Esther's reaching fingers. The trembling. The moment between life and death.
**Size:** Quarter-page

### Illustration 8 — "The Tenth Symbol"
**Placement:** Chapter 8, the symbol transforms
**Scene:** Close-up of the Pathfinder on the desk. Ten symbols glow — the newest a precise engraving of a crown filled with deep sapphire enamel. Two symbols remain faint and rough — a flame and a thorn. Faint colored light from the ten completed symbols casts across the desk surface.
**Focus:** The tenth symbol and the two remaining rough engravings. The map nearing completion.
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

- **Cover prompt:** `comfyui/prompts/covers/book-10-crown-of-courage.txt`
- **Interior prompts:** `comfyui/prompts/interiors/book-10/` (8 files, one per illustration)
- **Character LoRAs:** Trained per-character for consistency — see `comfyui/training/README.md`
- **Workflows:** Build interactively in ComfyUI GUI using settings documented in `comfyui/workflows/`

## Consistency Notes (Apply to All 12 Books)

- **The Fade:** In Book 10, the Fade doesn't need supernatural tricks — it amplifies real fear. The danger is genuine. In B&W, represent as deepening shadows, dimming torchlight, and loss of detail at the margins of each panel.
- **The Pathfinder:** Same design in every appearance. Nine symbols glowing at start of Book 10; ten by end. Incomplete symbols are faint, rough engravings; completed symbols are sharp, polished, colored, and glowing.
- **Characters:** Consistent clothing, hair, build across all books.
