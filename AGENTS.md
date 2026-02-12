# AI Agent Workflow — Covenant Keepers

## Philosophy

The author (Eric) owns the narrative vision, character voices, and theological accuracy. AI agents assist with drafting, brainstorming, and polishing — never with final creative decisions. Every word in the published manuscript has been read, considered, and approved by a human.

## Recommended Model Tiers

### Tier 1: Local Model (Brainstorming & Rough Drafts)
- **Model:** Qwen3 14B (Q4/Q5 quantized) via Ollama
- **Hardware:** RTX 5060 Ti (16GB VRAM)
- **Use for:** Dialogue exploration, "what if" scenarios, rough scene drafts, character voice testing, generating multiple approaches to a scene
- **Cost:** Free (local inference)
- **Why:** This is where you burn the most tokens. Exploring 5 different ways a scene could play out, testing whether a character's dialogue sounds right, brainstorming plot complications — all of this is high-volume, low-stakes work where "good enough" output saves money.

### Tier 2: Cloud API (Structured Drafting & Polish)
- **Model:** Claude Sonnet 4.5 via API
- **Use for:** Scene polishing, voice consistency passes, continuity checks across chapters, refining dialogue, ensuring age-appropriate vocabulary
- **Cost:** ~$3-5 per book
- **Why:** Better than local models at maintaining consistent character voice, catching continuity errors, and producing prose that needs minimal human editing. The cost-quality tradeoff is excellent for this stage.

### Tier 3: Premium (Architecture & Critical Scenes)
- **Model:** Claude Opus via API or claude.ai
- **Use for:** Series bible refinement, theological accuracy review, critical emotional scenes (Jordan's arc moments, the Book 12 climax), ensuring the series arc holds together
- **Cost:** ~$5-15 per session (use sparingly)
- **Why:** Reserved for work where quality truly matters and can't be achieved at lower tiers. Maybe 2-3 sessions per book.

### Alternative: Sudowrite ($22/mo Professional)
- **Model:** Muse 1.5 (fiction-specialized)
- **Use for:** Could replace Tier 1 and Tier 2 for prose generation. Purpose-built for fiction with strong dialogue, scene blocking, and cliché avoidance.
- **Tradeoff:** Monthly subscription vs. pay-per-use. At 2-3 books per month throughput, cost-effective. Also provides Story Bible feature for series consistency.

## Workflow Per Book

### Step 1: Outline Expansion (Tier 1 or Tier 3)
**Input:** The book's `OUTLINE.md` (high-level beats from series bible)
**Task:** Expand into a detailed chapter-by-chapter outline with scene beats, dialogue notes, and pacing markers.
**Prompt pattern:**
```
You are helping outline a chapter book for 8-10 year old readers.
The series is called Covenant Keepers. [Paste series bible context]
This book is: [title, Biblical event, theme, relic]
The characters are: [paste relevant character profiles]

Expand the following high-level outline into a chapter-by-chapter
breakdown. Each chapter should be 800-1200 words in the final draft.
For each chapter, provide:
- Chapter title
- Setting/location
- Key events (3-5 beats)
- Character moments (whose arc advances and how)
- The Fade's presence/influence (if any)
- Chapter-ending hook

[Paste OUTLINE.md content]
```

### Step 2: Scene Drafting (Tier 1)
**Input:** One chapter's outline beats
**Task:** Generate 2-3 rough draft attempts at each chapter
**Prompt pattern:**
```
Write Chapter [N] of a children's adventure book for 8-10 year olds.
Target: 800-1000 words. Short paragraphs. Simple but not dumbed-down
vocabulary. Fast pacing. Show don't tell.

Character voices:
- Eli: Thoughtful, cautious, uses bigger vocabulary than his age suggests
- Sofia: Direct, physical, speaks in short bursts, uses action verbs
- Jordan: Dry, questioning, uses qualifiers ("I mean..." "But what if...")

Chapter outline:
[Paste chapter beats]

Previous chapter ended with:
[Paste last paragraph of previous chapter for continuity]
```

### Step 3: Assembly & Polish (Tier 2)
**Input:** Best draft segments from Step 2, assembled into a full chapter
**Task:** Polish prose, smooth transitions, verify character voice consistency, check reading level
**Prompt pattern:**
```
You are editing a chapter book for 8-10 year old readers (Lexile 600-800).
Review the following chapter draft and:
1. Smooth any transitions between scenes
2. Ensure each character's voice is distinct and consistent
3. Flag any vocabulary that's too advanced for the target age
4. Tighten any sections that drag — this age group needs momentum
5. Verify the chapter ends on a hook that makes the reader turn the page

Character voice reference:
[Paste character profiles]

Draft:
[Paste assembled chapter]
```

### Step 4: Continuity Review (Tier 2 or Tier 3)
**Input:** Complete manuscript draft
**Task:** Check for continuity errors across the full book and against series canon
**Prompt pattern:**
```
Review this manuscript for internal consistency and series continuity.
Check for:
- Character knowledge: Do characters reference things they shouldn't know yet?
- Pathfinder rules: Are the established rules followed? (See series bible)
- Timeline: Does the sequence of events make sense?
- The Fade: Is its behavior consistent with series progression?
- Biblical accuracy: Do the historical events match scripture?
- Character arc: Does this book advance the right character's journey?

Series bible context:
[Paste relevant sections]

Manuscript:
[Paste full manuscript]
```

### Step 5: Final Human Review
**Input:** AI-polished manuscript
**Task:** Eric reads every word. Adjusts voice, fixes anything that feels "AI-ish," ensures theological accuracy, and makes final creative decisions. This step is non-negotiable and cannot be delegated to any AI tier.

## Prompt Library

Store reusable prompts in a `prompts/` directory if the collection grows. For now, the patterns above cover the core workflow.

## Context Management

Each AI session should include:
1. The series bible (or relevant excerpts)
2. The relevant character profiles
3. The current book's outline
4. The previous 1-2 chapters (for continuity)
5. Any series-level notes about where we are in the arc

For local models with limited context windows, prioritize: character profiles > current chapter outline > previous chapter ending > series rules. The full series bible may need to be summarized for Tier 1 models.

## Quality Signals

A chapter draft is ready for human review when:
- [ ] Each character sounds distinct (cover the names and you can tell who's speaking)
- [ ] The chapter is 800-1200 words
- [ ] It ends on a hook
- [ ] No AI-isms ("I understand your concern," "It's important to note," "delve")
- [ ] Vocabulary is age-appropriate without being condescending
- [ ] The Fade's presence matches the series progression for this book's position
- [ ] Biblical events are depicted accurately
