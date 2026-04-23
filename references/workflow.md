# Workflow

## Mode Definitions

### Literal

Interpret the phrase directly and physically.

- Humor comes from strict literal visualization.
- Do not convert the idea into advice, philosophy, or emotion-first commentary.
- The scene should read in one glance.

### Satire

Use the term to expose an absurd reality behind a polished story.

- Humor comes from the gap between stated ideal and actual behavior.
- Keep it grounded in work, product, or social reality.
- Do not collapse into wordplay-only literalism.

### Reflective

Use the term to express an observation or feeling that still works as a comic.

- Stay concrete enough to draw.
- Do not drift into abstract essay mode.
- The image must still carry the piece.

## Auto Mode Heuristics

When `mode` is `auto`, prefer:

- `literal` when the term already implies a strong physical object, container, barrier, machine, direction, or spatial action
- `satire` when the term is mainly used as management language, product language, or polished institutional rhetoric
- `reflective` only when the strongest version depends on lived feeling rather than a literal device or structural critique

If both `literal` and `satire` could work, choose the one with the cleaner one-glance visual premise for the default path.

## Four-Panel Rules

- Panel 1 = `setup`: establish normal world, scene, and keyword.
- Panel 2 = `trigger`: someone takes the phrase seriously or starts the action.
- Panel 3 = `twist`: the phrase becomes literal, awkward, or revealing.
- Panel 4 = `payoff`: strongest hit, not explanation.

Hard constraints:

- One core function per panel.
- Panel 4 must be stronger than Panel 3.
- Panel 4 must introduce either escalation, reversal, or a deadpan conclusion that adds new information.
- Dialogue stays short.
- The image should do more work than the text.
- Keep the mood deadpan unless the user asks otherwise.
- Prefer minimal office, product, or everyday staging over complex sci-fi scenes.

Failure signals:

- The final panel only explains the joke.
- Panel 4 is interchangeable with Panel 3.
- The comic needs a paragraph to make sense.
- A `literal` idea turns into metaphor or reflection.
- A `satire` idea loses the concrete scene and becomes abstract commentary.

## Stage Pipeline

### Stage 1: Classify / Interpret

Output:

- best mode
- why that mode fits
- the normal-world meaning of the term
- one sentence comic premise

### Stage 2: Angle Generation

Generate 3 angle candidates in the chosen mode.

Each candidate must:

- differ clearly from the others
- be expandable into 4 panels
- have a plausible Panel 4 payoff
- vary by at least one axis such as object choice, scene choice, or escalation pattern
- avoid being three near-synonyms of the same shot

### Stage 3: Idea Breakdown

Choose one candidate and lock:

- `title`
- `coreJoke`
- `normalWorld`
- `twist`
- `finalPayoff`

Do not rewrite the premise in later stages.

Punch test for `finalPayoff`:

- If you remove Panel 4 and the joke still lands the same way, the payoff is too weak.
- If Panel 4 only labels what Panel 3 already showed, rewrite it.
- Prefer a calm line that locks the absurd logic into place.

### Stage 4: Storyboard

Write 4 panels in Chinese with:

- `purpose`
- `scene`
- `action`
- `dialogue`

Keep scenes visually clear and not overly crowded.

### Stage 5: Image Prompt

Write English prompt text suitable for image models.

Always preserve:

- horizontal 4:3 canvas by default unless the user asks otherwise
- clean 2x2 panel grid by default unless the user asks otherwise
- visible panel borders or gutters so each panel reads separately
- simple webcomic style
- clear composition
- readable acting
- minimal background clutter
- non-cinematic finish
- avoid long vertical strips, irregular collage layouts, or overlapping panels by default

### Stage 6: Guardrails / Recovery / Social Copy

Add:

- one anti-drift prompt
- one recovery prompt
- optional social copy if requested
