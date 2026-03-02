# Book 5: The Horn of Obedience — Illustration Specifications

## Style Direction

- **Interior:** Simple black-and-white line drawings. Clean composition with a single clear focal point per illustration. Minimal background detail — suggest setting with a few confident strokes rather than filling every inch. Think classic chapter-book illustrations: evocative, not exhaustive.
- **Cover:** Full color, but restrained. Limited palette (warm golds, dusty browns, bronze tones against a desert sky). One strong composition, not a collage of elements. The cover should feel like a moment, not a summary.
- **Line weight:** Medium, with variation for depth and emphasis. Heavier lines for foreground subjects, lighter for environmental suggestion.
- **Characters:** Semi-realistic. Not cartoonish, not photorealistic. Must be recognizable and consistent across all 12 books.
- **The Fade:** More present than Books 1–4. Grey fog creeping across the ground, threading between figures, draining edges. Recognizable to returning readers and noticeable to newcomers.
- **The Pathfinder:** Five symbols complete by end of book. Incomplete symbols are faint, rough sketches; completed symbols are sharp, polished, with colored enamel and a faint glow.

---

## Cover Art (Full Color)

**Scene:** The three kids among a crowd marching around massive ancient city walls. Priests carrying the Ark of the Covenant ahead of them, one priest blowing a ram's horn. The walls of Jericho tower above, cracking and beginning to crumble at the top as dust falls. Dramatic sunset light.

**Mood:** Tension reaching its breaking point. The long march is ending. The walls are about to fall. Golden-amber light and rising dust.

**Composition:** The kids in the lower foreground, the marching procession filling the middle ground, the walls towering above as the focal backdrop. The cracking walls draw the eye upward.

**Series elements:** The Pathfinder visible at Eli's belt or partially hidden under his tunic. Series title treatment and book number. Consistent spine design.

**What to avoid:** Don't show the walls fully collapsed — this is the moment just before. Don't crowd the composition with the entire army. Suggest the multitude with a few figures; let the walls dominate.

---

## Interior Illustrations (8 × B&W Line Art)

### Illustration 1 — "The Pathfinder Pulses"
**Placement:** Chapter 1, when the Pathfinder hums louder than before
**Scene:** Close-up of the Pathfinder on the desk. Four completed symbols glow — stone, branch, thread, staff — sharp and polished. The fifth symbol, a tiny horn, trembles visibly in the bronze. Light begins to emanate from the center. Eli's hand hovers above.
**Focus:** The Pathfinder itself, with the contrast between completed and unfinished symbols. The vibrating fifth symbol is the key detail.
**Size:** Quarter-page, centered

### Illustration 2 — "The Walls of Jericho"
**Placement:** Chapter 2, when the kids first see the walls
**Scene:** Wide view looking up at the walls of Jericho from the base. The walls rise five stories, massive and unbroken, with tiny guard figures on the ramparts. The three kids stand at the bottom, dwarfed by the scale.
**Focus:** The overwhelming scale of the walls against the small figures below. Let the empty vertical space convey the impossibility.
**Size:** Full-page or three-quarter page

### Illustration 3 — "Joshua's Command"
**Placement:** Chapter 2, when Joshua addresses the crowd
**Scene:** Joshua standing before the assembled crowd, one arm raised. He is broad-shouldered, weathered, carved from the desert. His face is iron-set. A few soldiers visible in the foreground, their expressions uncertain.
**Focus:** Joshua's authority and stillness. He is the calm center of a confused crowd. One figure, commanding.
**Size:** Half-page

### Illustration 4 — "The Silent March"
**Placement:** Chapter 3, during the first circuit
**Scene:** A long procession of figures marching along the base of the enormous wall. Seven priests carry curved ram's horns at the front. The line stretches into the distance. From the ramparts above, small figures look down. Everything is silent — the image should feel hushed.
**Focus:** The length and solemnity of the procession against the looming wall. The contrast between the marching column below and the watchers above.
**Size:** Half-page

### Illustration 5 — "Elena Breaks"
**Placement:** Chapter 5, when Elena steps out of the procession
**Scene:** Elena standing alone outside the marching column, fists clenched at her sides, face turned upward toward the wall. Her mouth is open mid-shout. Eli reaches for her arm. The procession flows around them like water around stones.
**Focus:** Elena's frustration and defiance. Her body language — planted feet, raised chin, clenched fists — tells the story.
**Size:** Half-page

### Illustration 6 — "The Seventh Circuit"
**Placement:** Chapter 6, during the final march
**Scene:** Elena walking with tears on her face, jaw clenched, one sandal bloody. She stares straight ahead. The world around her is faded — grey fog curls at the edges of the illustration. She is the only sharp thing in the frame.
**Focus:** Elena's determination through exhaustion and pain. The Fade closing in but unable to stop her.
**Size:** Half-page

### Illustration 7 — "The Walls Fall"
**Placement:** Chapter 7, the moment of collapse
**Scene:** Massive stone blocks tumbling outward from the wall in a cascade of dust and debris. The ground heaves. A column of dust rises high into the sky. At the very bottom of the illustration, tiny figures — soldiers and the three kids — brace against the earthquake.
**Focus:** The scale of the destruction. The wall peeling open. Dust and stone in motion. The figures are small — this is about the event, not the people.
**Size:** Full-page

### Illustration 8 — "The Fifth Symbol"
**Placement:** Chapter 8, when the horn symbol transforms
**Scene:** Close-up of the Pathfinder on Abuelo's desk. Five symbols now glow — the newest, a horn, sharp and polished with deep golden enamel. The other seven remain faint scratches. Elena's empty hand hovers above the device, fingers still curled as if holding something that has dissolved.
**Focus:** The transformed fifth symbol and Elena's empty hand. The warmth of completion contrasted with the rough, waiting symbols.
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

- **Cover prompt:** `comfyui/prompts/covers/book-05-horn-of-obedience.txt`
- **Interior prompts:** `comfyui/prompts/interiors/book-05/` (8 files, one per illustration)
- **Character LoRAs:** Trained per-character for consistency — see `comfyui/training/README.md`
- **Workflows:** Build interactively in ComfyUI GUI using settings documented in `comfyui/workflows/`

## Consistency Notes (Apply to All 12 Books)

- **The Fade:** More assertive in Books 5–8. Arrives earlier. Grey fog thicker and more deliberate. In Book 5, it seeps from the ground and threads between tents — subtle but pervasive.
- **The Pathfinder:** Same design in every appearance. Book 5 begins with 4 completed symbols and ends with 5. Incomplete symbols are faint, rough engravings; completed symbols are sharp, polished, colored, and glowing.
- **Characters:** Consistent clothing, hair, build across all books. Elena's gap-toothed grin, Jordan's glasses and rubber band, Eli's careful posture.
