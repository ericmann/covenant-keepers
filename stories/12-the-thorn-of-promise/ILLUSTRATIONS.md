# Book 12: The Thorn of Promise — Illustration Specifications

## Style Direction

- **Interior:** Simple black-and-white line drawings. Clean composition with a single clear focal point per illustration. Minimal background detail — suggest setting with a few confident strokes rather than filling every inch. Think classic chapter-book illustrations: evocative, not exhaustive.
- **Cover:** Full color, but restrained. Limited palette (sun-baked stone and pale blue sky, with a warm golden glow from the thorn in the thicket). One strong composition, not a collage of elements. The cover should feel like a moment, not a summary.
- **Line weight:** Medium, with variation for depth and emphasis. Heavier lines for foreground subjects, lighter for environmental suggestion.
- **Characters:** Semi-realistic. Not cartoonish, not photorealistic. Must be recognizable and consistent across all 12 books.
- **The Fade:** In Book 12, the Fade targets the kids directly for the first time — attacking their personal doubts and wounds. In B&W, represented as a closing-in effect at the edges of each panel, pressing the frame tighter around the characters.
- **The Pathfinder:** Consistent design in every appearance. Eleven symbols glowing at the start of this book; twelve by the end. The completed Pathfinder unfolds into a map of light.

---

## Cover Art (Full Color)

**Scene:** Three children on a barren mountaintop watching an elderly man and a teenage boy beside a stone altar. A ram caught in a thorny thicket nearby, a thorn glowing with warm golden light. The father's hand is stayed, knife lowered, his face showing relief and awe. The boy looks up at his father with trust. Dramatic sunrise light breaking over Mount Moriah with a vast landscape below.

**Mood:** Relief, awe, and sacred weight. The worst is over. The provision has been revealed. The light is breaking through.

**Composition:** The kids in the lower left foreground, watching. Abraham and Isaac at the altar in the middle ground. The glowing thorn thicket to the right. The vista stretching beyond and below. The sunrise catches everything in warm gold.

**Series elements:** The Pathfinder visible at Eli's belt. Series title treatment and book number. Consistent spine design.

**What to avoid:** Don't show the knife raised. Show the moment after — the knife lowered, the relief, the ram revealed. This is about provision, not threat.

---

## Interior Illustrations (8 x B&W Line Art)

### Illustration 1 — "The Last Slot"
**Placement:** Chapter 1, Eli studying the Pathfinder with eleven symbols glowing
**Scene:** A boy sitting on a rug, the Pathfinder on his knees. Eleven symbols glow in sharp detail. One rough scratch — a thorn — is barely visible. The boy traces the thorn symbol with his fingertip. Lamplight catches the bronze surface.
**Focus:** The near-complete Pathfinder. The single rough thorn engraving. The boy's concentration.
**Size:** Quarter-page, centered

### Illustration 2 — "The Climb"
**Placement:** Chapter 2, Abraham and Isaac walking up the mountain path
**Scene:** Two figures on a narrow, winding path through scrubland — a tall man with grey-streaked hair carrying a fire pot and a knife, a teenage boy behind him carrying a bundle of wood on his back. Thorny bushes line the path. The summit is visible above.
**Focus:** The two figures climbing together. The father's rigid posture. The son following with trust. No lamb between them.
**Size:** Half-page

### Illustration 3 — "Where Is the Lamb?"
**Placement:** Chapter 3, Isaac's question
**Scene:** A boy standing beside a half-built stone altar, his bundle of wood set down at his feet. He looks at his father with an open, questioning face. The father's back is turned, his hands on the altar stones, his shoulders carrying an invisible weight.
**Focus:** Isaac's face — trusting, questioning. Abraham's turned back. The unfinished altar between them.
**Size:** Half-page

### Illustration 4 — "The Binding"
**Placement:** Chapter 4, Abraham binds Isaac on the altar
**Scene:** A man's hands carefully wrapping cord around a boy's wrists. The boy lies on a finished stone altar with wood arranged beneath him. The boy's eyes are open, looking at the sky. The man's face is wet with tears. Only the altar, the hands, and the two figures are visible.
**Focus:** The tenderness of the binding. The father's tears. The son's open eyes looking upward. Intimacy, not violence.
**Size:** Half-page

### Illustration 5 — "The Ram in the Thicket"
**Placement:** Chapter 5, the ram is discovered caught in the thorns
**Scene:** A ram tangled in a dense thicket of thorny branches — hooves caught, horns snagged, wool snarled. One thorn in the center of the tangle glows with a warm ember-light. The bush is wild and sharp. The ram is still, waiting.
**Focus:** The ram caught and held. The glowing thorn. The provision that was already there.
**Size:** Half-page

### Illustration 6 — "Elena Reaches for the Thorn"
**Placement:** Chapter 6, Elena pushes her arm into the thorn bush
**Scene:** A girl on her knees, reaching one arm into a dense tangle of thorny branches. Thin scratches line her forearm. Her fingers close around a small, glowing object deep in the bush. Her expression is determined, unflinching.
**Focus:** Elena's arm in the thorns. The scratches. The glow between her fingers. Action without hesitation.
**Size:** Quarter-page

### Illustration 7 — "The Map Unfolds"
**Placement:** Chapter 7, the completed Pathfinder unfolds into a map of light
**Scene:** The Pathfinder on a desk, its twelve symbols lifted from the surface and floating in the air in a circle. Lines of light connect them — a web, a constellation, a map. The lines all converge on an empty center point. The room around the map is suggested by a few strokes — the corner of a bookshelf, the edge of a window.
**Focus:** The floating symbols and the lines of light between them. The empty center where all lines converge. Wonder, not explanation.
**Size:** Full-page

### Illustration 8 — "Three Kids, One Map"
**Placement:** Chapter 9, the final scene — the kids looking at the completed map
**Scene:** Three children in a study, looking up at a map of light spread across the ceiling. One boy stands by the desk. A girl sits on the desk edge, legs swinging, head tilted back. Another boy leans against the doorframe, glasses reflecting twelve points of light. The map of light fills the air above them.
**Focus:** The three kids and the map above. Their expressions — wonder, satisfaction, openness. The sense that something is complete and something is just beginning.
**Size:** Full-page

---

## AI Concept Art Notes

For each illustration, generate 2-3 concept images using image generation tools to provide the illustrator with:
- Composition and framing direction
- Character positioning and body language
- Mood and lighting reference

Annotate each AI reference image with notes on what to keep and what to change. The illustrator should interpret the concepts in their own consistent style, not reproduce the AI output.

### ComfyUI Pipeline

All AI-generated concept art is produced via ComfyUI with Flux.1-dev. See `comfyui/README.md` for full setup instructions.

- **Cover prompt:** `comfyui/prompts/covers/book-12-thorn-of-promise.txt`
- **Interior prompts:** `comfyui/prompts/interiors/book-12/` (8 files, one per illustration)
- **Character LoRAs:** Trained per-character for consistency — see `comfyui/training/README.md`
- **Workflows:** Build interactively in ComfyUI GUI using settings documented in `comfyui/workflows/`

## Consistency Notes (Apply to All 12 Books)

- **The Fade:** In Book 12, the Fade attacks the kids personally — targeting their doubts and wounds. In B&W, represent as a tightening frame around the characters, pressing inward. The Fade is most dangerous when it tells the truth about fear.
- **The Pathfinder:** Same design in every appearance. Eleven symbols glowing at start of Book 12; twelve by end. The completed Pathfinder unfolds into a map of light with an empty center.
- **Characters:** Consistent clothing, hair, build across all books.
