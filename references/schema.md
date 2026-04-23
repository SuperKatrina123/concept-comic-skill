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

## Conditional Output

- Omit `socialCopy` when `platformTarget` is `comic_only`.
- If the user explicitly specifies a mode, do not override it.
- If `mode` is `auto`, output `modeDecision.reason` before expanding the comic.
- Unless the user explicitly requests another format, image prompts should assume a horizontal `4:3` canvas.
