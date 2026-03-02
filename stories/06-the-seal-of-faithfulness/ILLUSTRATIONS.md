# Book 6: The Seal of Faithfulness — Illustration Specifications

## Style Direction

- **Interior:** Simple black-and-white line drawings. Clean composition with a single clear focal point per illustration. Minimal background detail — suggest setting with a few confident strokes rather than filling every inch. Think classic chapter-book illustrations: evocative, not exhaustive.
- **Cover:** Full color, but restrained. Limited palette (cool blues, warm torchlight amber, deep stone greys). One strong composition, not a collage of elements. The cover should feel like a moment, not a summary.
- **Line weight:** Medium, with variation for depth and emphasis. Heavier lines for foreground subjects, lighter for environmental suggestion.
- **Characters:** Semi-realistic. Not cartoonish, not photorealistic. Must be recognizable and consistent across all 12 books.
- **The Fade:** More assertive than previous books. Arrives before the kids do. Manifests as thoughts and pressure, not just fog. When shown visually, suggest it as darkness with weight — shadows that press in.
- **The Pathfinder:** Six symbols complete by end of book. Incomplete symbols are faint, rough sketches; completed symbols are sharp, polished, with colored enamel and a faint glow.

---

## Cover Art (Full Color)

**Scene:** The three kids peering through the bars of a stone pit at dawn light breaking in. Below, Daniel sits peacefully among several large lions who rest undisturbed around him. A round seal stone near the pit entrance glows faintly. Cool blue dawn light contrasts with warm torchlight from inside.

**Mood:** Awe and relief at dawn. The longest night is over. The calm of the lions is the miracle — enormous, powerful creatures at rest beside a praying man.

**Composition:** The kids framing the upper portion, looking down. Daniel and the lions fill the lower half. The glow of the seal stone provides a warm accent against the cool dawn palette.

**Series elements:** The Pathfinder partially visible on Eli. Series title treatment and book number. Consistent spine design.

**What to avoid:** Don't make the lions cartoonish or friendly. They should be massive and real — the miracle is that they're calm, not that they're tame. Don't overcrowd the den with too many lions.

---

## Interior Illustrations (8 × B&W Line Art)

### Illustration 1 — "The Glazed Corridor"
**Placement:** Chapter 2, upon arrival in Babylon
**Scene:** A wide corridor of glazed blue brick, with raised-relief lions and bulls marching along the walls. Oil lamps in bronze brackets cast light. The three kids stand in the corridor, small against the ornate architecture, looking ahead.
**Focus:** The grandeur and scale of the Babylonian palace. The decorative lions on the walls foreshadow the real lions to come.
**Size:** Half-page

### Illustration 2 — "Daniel in the Court"
**Placement:** Chapter 2, when Daniel walks through the palace
**Scene:** Daniel walking through a hall of officials. He is older, grey-streaked beard, wearing simpler robes than those around him. Officials in elaborate embroidered robes step aside as he passes. His posture is steady and unhurried.
**Focus:** Daniel's quiet authority. The contrast between his simple dress and the ornate court. He moves through the crowd like a river through stones.
**Size:** Half-page

### Illustration 3 — "The Decree Is Sealed"
**Placement:** Chapter 3, when Darius presses his seal
**Scene:** Close-up of King Darius pressing a small cylinder seal into warm wax on a clay tablet. His hand is steady but his face, partially visible above, shows no awareness of the trap. The seal makes a deep impression.
**Focus:** The seal pressing into the wax. This small, precise action sets the entire tragedy in motion. An intimate, tight composition.
**Size:** Quarter-page

### Illustration 4 — "The Open Window"
**Placement:** Chapter 4, when Daniel opens the shutters and kneels
**Scene:** Daniel kneeling at an open window, hands folded, face turned toward the light. The window frames a distant horizon — the direction of Jerusalem. Grooves are worn into the floor where his knees have rested ten thousand times. Late afternoon light pours in.
**Focus:** Daniel's stillness and the open window. The grooves in the floor tell a story of decades of faithfulness. Simple, luminous, sacred.
**Size:** Half-page

### Illustration 5 — "The Sealed Stone"
**Placement:** Chapter 6, when the den is sealed
**Scene:** A massive stone slab being rolled across the mouth of a dark pit. Darius presses his seal stone into wet clay smeared across the seam. His hands shake. Torchlight barely reaches into the darkness beyond the stone.
**Focus:** The sealing of the den. The king's trembling hand pressing the seal. The darkness beyond the stone is absolute.
**Size:** Half-page

### Illustration 6 — "The Long Night"
**Placement:** Chapter 6, the kids waiting in the dark
**Scene:** The three kids huddled against a stone wall in near-total darkness. Elena leans against Eli's shoulder, eyes closed. Jordan sits with knees pulled up. The faint glow of the Pathfinder under Eli's robe provides the only light — five small points in the dark.
**Focus:** The vulnerability of three children in the dark, waiting. The tiny glow of the Pathfinder is a thread of hope in the blackness.
**Size:** Quarter-page

### Illustration 7 — "The Stone Rolls Away"
**Placement:** Chapter 7, when Darius orders the den opened
**Scene:** Darius at the sealed entrance, hands tearing at the clay seal, his face desperate and hollowed by a sleepless night. Guards strain to push the stone slab back. Dawn light streams down the corridor behind the king.
**Focus:** Darius breaking his own seal. The urgency in his hands and face. The dawn light behind him pushing back the darkness.
**Size:** Half-page

### Illustration 8 — "The Sixth Symbol"
**Placement:** Chapter 8, when the seal symbol transforms
**Scene:** Close-up of the Pathfinder on Abuelo's desk. Six symbols glow — the newest, a cylindrical seal stone, sharp and polished with deep red-brown enamel. The other six remain faint scratches. Eli's open, empty palm hovers above, the warmth still fading.
**Focus:** The transformed sixth symbol and Eli's empty hand. Six lights in a circle of twelve — halfway there.
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

- **Cover prompt:** `comfyui/prompts/covers/book-06-seal-of-faithfulness.txt`
- **Interior prompts:** `comfyui/prompts/interiors/book-06/` (8 files, one per illustration)
- **Character LoRAs:** Trained per-character for consistency — see `comfyui/training/README.md`
- **Workflows:** Build interactively in ComfyUI GUI using settings documented in `comfyui/workflows/`

## Consistency Notes (Apply to All 12 Books)

- **The Fade:** In Book 6, the Fade arrives before the kids and manifests as intrusive thoughts — "just this once," "pray quietly," "nobody has to know." Visually, represent this as weighted shadows and dimmed lamplight rather than rolling fog.
- **The Pathfinder:** Same design in every appearance. Book 6 begins with 5 completed symbols and ends with 6. Incomplete symbols are faint, rough engravings; completed symbols are sharp, polished, colored, and glowing.
- **Characters:** Consistent clothing, hair, build across all books. Jordan's growing openness should show in body language — less crossed arms, more leaning in.
