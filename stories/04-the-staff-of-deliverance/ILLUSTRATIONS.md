# Book 4: The Staff of Deliverance — Illustration Specifications

## Style Direction

- **Interior:** Simple black-and-white line drawings. Clean composition with a single clear focal point per illustration. Minimal background detail — suggest setting with a few confident strokes rather than filling every inch. Think classic chapter-book illustrations: evocative, not exhaustive.
- **Cover:** Full color, but restrained. Limited palette (warm golds, dusty browns, bronze tones against cool blue-black water). One strong composition, not a collage of elements. The cover should feel like a moment, not a summary.
- **Line weight:** Medium, with variation for depth and emphasis. Heavier lines for foreground subjects, lighter for environmental suggestion.
- **Characters:** Semi-realistic. Not cartoonish, not photorealistic. Must be recognizable and consistent across all 12 books. Establish model sheets with the illustrator before beginning.
- **The Fade:** When present, represented as suffocating inevitability — the weight of empire, the feeling that nothing can ever change. In B&W line art, this is suggested by making structures feel oppressively large and figures oppressively small.
- **The Pathfinder:** Consistent design in every appearance. Four symbols complete by end of book (stone, branch, thread, staff). Incomplete symbols are faint, rough sketches; completed symbols are sharp, polished, with colored enamel and a faint glow.

---

## Cover Art (Full Color)

**Scene:** The three kids standing among a crowd at the edge of a parted sea. Towering walls of dark water rise on both sides. A robed figure ahead raises a wooden staff toward the sky. A dry path stretches between the water walls, lit by moonlight and a pillar of fire in the distance.

**Mood:** Awe and impossible scale. The water walls should feel both terrifying and beautiful. The figure with the staff is small against the enormity of the parted sea.

**Composition:** The kids in the foreground among the crowd (backs or three-quarter view), the dry path stretching into the middle ground, Moses' figure small but unmistakable with the raised staff. The water walls dominate the frame vertically. The pillar of fire provides a warm focal point in the distance.

**Series elements:** The Pathfinder visible at Eli's belt or in his hand. Series title treatment and book number. Consistent spine design.

**What to avoid:** Don't show the chariots and the parting at the same time. Don't show the far shore. Don't try to render the entire multitude. One moment, one feeling.

---

## Interior Illustrations (8 x B&W Line Art)

### Illustration 1 — "The Phone Call"
**Placement:** Chapter 1, Eli on the phone with Abuelo
**Scene:** A boy holds an old rotary phone receiver to his ear, standing in a dim hallway. His expression is intense, listening hard. One hand grips the receiver; the other is clenched at his side. A girl stands a few feet behind him, arms crossed over her pajama shirt, watching.
**Focus:** Eli's face and the act of listening. The phone is old and heavy and real. The moment is quiet and domestic but charged with meaning.
**Size:** Quarter-page

### Illustration 2 — "The Burning Bush"
**Placement:** Chapter 2, Moses approaching the bush that burns but is not consumed
**Scene:** A man seen from behind, walking up a rocky slope toward a bush wrapped in flame. The fire is bright and intricate — curling around the branches without consuming them. The man's sandals are in one hand, his feet bare on the ground. His staff leans against a rock behind him.
**Focus:** The bush and the fire. The flames should have a quality of presence — not destruction but intensity. The man is approaching, not fleeing.
**Size:** Half-page

### Illustration 3 — "The Slaves"
**Placement:** Chapter 3, the Hebrew workers in Egypt
**Scene:** A single figure — a woman — carrying a water jar on her bent back. The jar is enormous, bending her almost double. Her face is turned down, her feet bare in dust. Behind her, the base of an enormous stone column rises, suggesting the scale of the empire that holds her.
**Focus:** The contrast in scale — the small human figure and the massive column. The weight she carries, physical and otherwise.
**Size:** Half-page

### Illustration 4 — "Pharaoh's Refusal"
**Placement:** Chapter 4, during the plagues
**Scene:** Close-up of a hand wearing heavy gold rings, palm raised flat in a gesture of refusal. The hand is powerful and adorned, the fingers spread wide. Beyond the hand, blurred and small, the suggestion of a robed figure holding a staff.
**Focus:** The hand and the rings. Power refusing to bend. A single gesture that says everything about Pharaoh's stubbornness.
**Size:** Quarter-page

### Illustration 5 — "The Blood on the Door"
**Placement:** Chapter 5, Passover night
**Scene:** A doorway in a mud-brick wall. Dark marks of blood are painted on the doorposts and the wooden beam above — top and sides. Through the partially open doorway, the warm glow of a lamp is visible inside. A man's hand rests on the doorframe from within, holding it open.
**Focus:** The marked doorway and the contrast between the dark street and the warm light inside. The blood marks are simple but unmistakable.
**Size:** Half-page

### Illustration 6 — "Going Out"
**Placement:** Chapter 6, the Exodus begins
**Scene:** Elena standing on a low wall, one hand shading her eyes, looking out over an implied crowd (only the tops of a few heads visible at the bottom of the frame). Her expression is fierce and moved — the rough edge of trying not to cry. Wind catches her hair.
**Focus:** Elena's face and her elevated vantage point. She is watching something enormous happen.
**Size:** Quarter-page

### Illustration 7 — "Moses Raises the Staff"
**Placement:** Chapter 7, the moment before the sea parts
**Scene:** A man stands at the waterline, seen from behind. His staff is raised high above his head in both hands. The sea stretches flat and dark before him. His robes blow in a strong wind. His shoulders are shaking. He is alone in the frame.
**Focus:** The raised staff and the figure's vulnerability. The sea is vast and indifferent. The staff is just a stick. This is the centerpiece illustration of the book.
**Size:** Full-page

### Illustration 8 — "The Fourth Symbol"
**Placement:** Chapter 8, after the return
**Scene:** Close-up of the Pathfinder on the desk. Four symbols now glow — stone (amber), branch (green), thread (multicolored shimmer), and staff (warm olive-wood brown). The other eight remain faint scratches. Eli looks at his own empty, ordinary hands held open above the device.
**Focus:** The four completed symbols and Eli's hands. The contrast between ordinary hands and extraordinary purpose.
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

- **Cover prompt:** `comfyui/prompts/covers/book-04-staff-of-deliverance.txt`
- **Interior prompts:** `comfyui/prompts/interiors/book-04/` (8 files, one per illustration)
- **Character LoRAs:** Trained per-character for consistency — see `comfyui/training/README.md`
- **Workflows:** Build interactively in ComfyUI GUI using settings documented in `comfyui/workflows/`

## Consistency Notes (Apply to All 12 Books)

- **The Fade:** In Book 4, the Fade is deeply embedded in Egypt's oppressive system. It manifests as suffocating inevitability — the crushing weight of an empire too big to challenge. In interior B&W art, this is suggested through extreme scale contrasts (tiny figures against massive architecture).
- **The Pathfinder:** Same design in every appearance. Book 4 begins with 3 glowing symbols (stone + branch + thread) and ends with 4 (stone + branch + thread + staff). Incomplete symbols are faint, rough engravings; completed symbols are sharp, polished, colored, and glowing.
- **Characters:** Consistent clothing, hair, build across all books. Establish model sheets before beginning illustration work.
