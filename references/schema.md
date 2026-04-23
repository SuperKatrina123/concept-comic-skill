# Schema

## Input

```yaml
rawIdea: string
mode: auto | literal | satire | reflective
domain: ai | office | product | everyday
tone: deadpan | playful | sharper
platformTarget: comic_only | xiaohongshu | twitter | both
```

## Defaults

```yaml
mode: auto
domain: ai
tone: deadpan
platformTarget: comic_only
imageAspectRatio: landscape_4_3
panelLayout: grid_2x2
titleTreatment: large_top_title
```

## Output

```yaml
modeDecision:
  selectedMode: literal | satire | reflective
  reason: string

angleCandidates:
  - title: string
    oneLinePremise: string
    whyItWorks: string
  - title: string
    oneLinePremise: string
    whyItWorks: string
  - title: string
    oneLinePremise: string
    whyItWorks: string

ideaBreakdown:
  title: string
  coreJoke: string
  normalWorld: string
  twist: string
  finalPayoff: string

storyboard:
  - panel: 1
    purpose: setup
    scene: string
    action: string
    dialogue: string
  - panel: 2
    purpose: trigger
    scene: string
    action: string
    dialogue: string
  - panel: 3
    purpose: twist
    scene: string
    action: string
    dialogue: string
  - panel: 4
    purpose: payoff
    scene: string
    action: string
    dialogue: string

imagePrompt:
  stylePrompt: string
  fullPrompt: string

guardrailPrompt: string
recoveryPrompt: string

socialCopy:
  xiaohongshuTitle: string
  xiaohongshuBody: string
  twitterPost: string
```

## Language Split

- `modeDecision`, `angleCandidates`, `ideaBreakdown`, `storyboard`, and social copy are in Chinese.
- `imagePrompt`, `guardrailPrompt`, and `recoveryPrompt` are in English.

## Image Prompt Format

- `stylePrompt` is a short English style summary.
- `fullPrompt` is the production prompt and should use a fixed template rather than a free-form paragraph.
- `fullPrompt` should contain these sections in order:
  - `Title: {{title}}`
  - `Please create a 4-panel humorous comic in a simple indie webcomic style.`
  - `Core joke:`
  - `4-panel structure:`
  - `Style requirements:`
  - `Important:`

## Conditional Output

- Omit `socialCopy` when `platformTarget` is `comic_only`.
- If the user explicitly specifies a mode, do not override it.
- If `mode` is `auto`, output `modeDecision.reason` before expanding the comic.
- Unless the user explicitly requests another format, image prompts should assume a horizontal `4:3` canvas.
- Unless the user explicitly requests another layout, image prompts should assume a clean `2x2` four-panel grid with visible gutters and borders.
- Unless the user explicitly requests another treatment, image prompts should assume a large readable title above the comic.
