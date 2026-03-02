# Book 8: The Coin of Second Chances — Illustration Specifications

## Style Direction

- **Interior:** Simple black-and-white line drawings. Clean composition with a single clear focal point per illustration. Minimal background detail — suggest setting with a few confident strokes rather than filling every inch. Think classic chapter-book illustrations: evocative, not exhaustive.
- **Cover:** Full color, but restrained. Limited palette (Mediterranean blues, harbor golds, storm-dark greys, warm bronze). One strong composition, not a collage of elements. The cover should feel like a moment, not a summary.
- **Line weight:** Medium, with variation for depth and emphasis. Heavier lines for foreground subjects, lighter for environmental suggestion.
- **Characters:** Semi-realistic. Not cartoonish, not photorealistic. Must be recognizable and consistent across all 12 books.
- **The Fade:** At its most assertive for the mid-series. Manifests as moral arguments — "they don't deserve mercy." Visually, show as heavy shadows and cold mist that the characters physically lean against.
- **The Pathfinder:** Eight symbols complete by end of book. Abuelo is present in the study for this book — his first time witnessing the departure and return.

---

## Cover Art (Full Color)

**Scene:** The three kids at a bustling ancient Mediterranean harbor, watching a reluctant bearded man board a wooden sailing ship. Dark storm clouds gather on the horizon. A single coin glows faintly on the dock planks where it was dropped as fare payment. The harbor is busy with merchants and sailors.

**Mood:** Unease and foreboding. The storm is coming. The man boarding the ship is running, not traveling. The glowing coin on the dock is small but magnetic — the eye finds it.

**Composition:** The kids in the lower foreground, exchanging worried glances. Jonah on the gangplank in the middle ground, moving away from the viewer. The ship and gathering storm fill the upper half. The coin glows on the dock between the kids and the ship.

**Series elements:** The Pathfinder partially visible on Eli. Series title treatment and book number. Consistent spine design.

**What to avoid:** Don't show the fish/whale — that comes later. Don't make Jonah look villainous; he looks desperate and angry. Don't overcrowd the harbor.

---

## Interior Illustrations (8 × B&W Line Art)

### Illustration 1 — "Abuelo in the Study"
**Placement:** Chapter 1, when Abuelo enters the study
**Scene:** Abuelo lowering himself into the chair by the desk, his cane hooked over the armrest. He is thinner than before, but his eyes are sharp behind half-moon glasses. The Pathfinder sits on the desk before him, seven symbols glowing. He looks at it with an expression of pride and concern.
**Focus:** Abuelo's face and hands — the weariness of his body and the sharpness of his mind. The Pathfinder's glow reflected in his glasses.
**Size:** Half-page

### Illustration 2 — "Jonah Runs"
**Placement:** Chapter 2, when Jonah pushes through the crowd
**Scene:** A broad-shouldered, dark-bearded man pushing through a harbor crowd. He clutches a leather satchel to his chest. His eyes are wild, scanning behind him. He moves against the flow of traffic — everyone else is working, he is fleeing. A heavy cloak despite the heat.
**Focus:** Jonah's body language — hunched, desperate, eyes darting. A man running from something invisible.
**Size:** Half-page

### Illustration 3 — "The Storm"
**Placement:** Chapter 3, when the storm strikes
**Scene:** The ship's deck in chaos. The mast tilts at a sharp angle. A single torn sail whips in the wind. One sailor clings to a rope, face turned upward at a black sky. Waves crest above the railing. The world is all diagonal lines and spray.
**Focus:** The violence and chaos of the storm. One sailor against the elements. Diagonal composition to convey the ship's tilt and the danger.
**Size:** Half-page

### Illustration 4 — "Into the Deep"
**Placement:** Chapter 3, when Jonah is thrown overboard
**Scene:** A figure falling into dark water, seen from above. Jonah's cloak spreads around him. His face is turned upward — not panicked, resigned. Below him, in the deep water, a vast dark shadow is rising. The shadow is suggested, not detailed — just an immense, darker shape beneath the waves.
**Focus:** Jonah falling and the shadow rising. The contrast between the small man and the enormous presence below. The sea should feel deep and absolute.
**Size:** Half-page

### Illustration 5 — "Prayer in the Dark"
**Placement:** Chapter 4, Jonah praying inside the fish
**Scene:** Jonah sitting with his back against a curved surface, knees drawn to his chest, face turned upward. Total darkness surrounds him. His mouth is open — praying. The curved walls suggest an organic interior without being graphic. The three kids are nearby, barely visible silhouettes in the dark.
**Focus:** Jonah's upturned face in the dark. A man at absolute bottom, speaking upward. The darkness is the setting; his face is the focal point.
**Size:** Half-page

### Illustration 6 — "Nineveh's Gates"
**Placement:** Chapter 5, when the kids first see Nineveh
**Scene:** The massive gates of Nineveh — colossal carved stone, flanked by enormous winged bulls with human faces. Tiny figures stream through the gates. The walls stretch in both directions, curving out of sight. The scale is oppressive.
**Focus:** The sheer size of the city gates and the winged bull statues. This is the most powerful city in the ancient world. People are ants in comparison.
**Size:** Half-page

### Illustration 7 — "The City Turns"
**Placement:** Chapter 6, when Nineveh repents
**Scene:** A single figure — a merchant or soldier — kneeling in a wide street, head bowed, hands open on his knees. He wears rough sackcloth instead of his fine clothing, which lies discarded beside him. Behind him, more kneeling figures recede into the distance, filling the street.
**Focus:** One person's act of repentance, multiplied. The single kneeling figure in the foreground tells the story; the figures behind show it spreading.
**Size:** Half-page

### Illustration 8 — "The Coin at the Harbor"
**Placement:** Chapter 8, when Eli finds the relic
**Scene:** Close-up of Eli's hand reaching down between two quay stones to pick up a small bronze coin wedged in a crack. The coin glows with faint amber light. The empty harbor stretches behind, golden in late afternoon sun. His fingers are about to close around it.
**Focus:** Eli's hand and the glowing coin. The simplicity of the gesture — picking up a small, forgotten coin — carries the weight of the entire story. The harbor is empty, peaceful, waiting.
**Size:** Quarter-page

---

## AI Concept Art Notes

For each illustration, generate 2–3 concept images using image generation tools to provide the illustrator with:
- Composition and framing direction
- Character positioning and body language
- Mood and lighting reference

Annotate each AI reference image with notes on what to keep and what to change. The illustrator should interpret the concepts in their own consistent style, not reproduce the AI output.

### ComfyUI Pipeline

All AI-generated concept art is produced via ComfyUI with Flux.1-dev. See `comfyui/README.md` for full setup instructions.

- **Cover prompt:** `comfyui/prompts/covers/book-08-coin-of-second-chances.txt`
- **Interior prompts:** `comfyui/prompts/interiors/book-08/` (8 files, one per illustration)
- **Character LoRAs:** Trained per-character for consistency — see `comfyui/training/README.md`
- **Workflows:** Build interactively in ComfyUI GUI using settings documented in `comfyui/workflows/`

## Consistency Notes (Apply to All 12 Books)

- **The Fade:** In Book 8, the Fade's argument is moral: "They don't deserve mercy." It weaponizes truth — the Assyrians were terrible. Visually, the Fade is thickest on the hillside scene with Jonah and thinnest at the harbor when the relic is found.
- **The Pathfinder:** Same design in every appearance. Book 8 begins with 7 completed symbols and ends with 8. Abuelo witnesses the departure and return for the first time. Incomplete symbols are faint, rough engravings; completed symbols are sharp, polished, colored, and glowing.
- **Characters:** Consistent clothing, hair, build across all books. Jordan's arc is pivotal in this book — his body language should be more open than in any previous book. Abuelo is physically present but fragile.
