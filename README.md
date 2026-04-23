# concept-comic-skill

![License: MIT](https://img.shields.io/badge/license-MIT-green)
![Package Type](https://img.shields.io/badge/package-skill_asset-blue)
![Runtime](https://img.shields.io/badge/runtime-general_skill_runtime-black)
![Layout](https://img.shields.io/badge/layout-2x2_grid-orange)
![Canvas](https://img.shields.io/badge/canvas-4%3A3_horizontal-purple)
![Prompt](https://img.shields.io/badge/prompt-fixed_template-teal)

Turn a word, phrase, term, or concept into a **four-panel comic creation package**.

Chinese storyboard. English image prompt. Deadpan webcomic logic.

`concept-comic-skill` is a skill asset package for general skill runtimes. It is designed for people who want to turn AI terms, office language, product jargon, or short meme premises into clean, deadpan, social-media-friendly comics.

It is optimized for:

- Chinese `Idea Breakdown` and `Storyboard`
- English image prompts
- default horizontal `4:3` image framing
- default clean `2x2` four-panel layout
- default large title above the comic
- literal / satire / reflective mode control
- deadpan webcomic-style humor
- AI, workplace, product, and workflow concepts

## Quick Start

Install:

```bash
npx skills add SuperKatrina123/concept-comic-skill
```

Load the skill from your runtime, then invoke it by name or by matching intent:

```text
Use $concept-comic-skill to turn "guardrails" into a four-panel comic.
```

```text
用 $concept-comic-skill 把 “Human in the Loop” 做成四格小漫画。
```

If your runtime supports keyword-based routing, `concept-comic-skill` is intended to match requests such as:

- four-panel comic
- 四格漫画
- 四格小漫画
- webcomic
- literal comic
- satire comic
- reflective comic
- deadpan comic
- AI term comic
- 职场梗漫画
- 把这个词画成漫画
- 把这个术语变成四格
- 把这个概念做成小漫画

## What You Get

Given a raw idea such as a term, phrase, or short premise, the skill returns a structured package with:

- mode decision
- 3 angle candidates
- idea breakdown
- 4-panel Chinese storyboard
- English image prompt in a fixed production template
- anti-drift guardrail prompt
- recovery prompt for rerolling bad generations
- optional social copy

The output is designed to be useful both for human ideation and for passing into downstream image-generation workflows.

By default, image prompts assume a **horizontal 4:3 canvas**, a **clean 2x2 four-panel grid**, and a **large readable title above the comic** unless your runtime or prompt overrides them.

The final image prompt is not a loose paragraph. It is formatted as a stable production template with:

- `Title`
- `Core joke`
- `4-panel structure`
- `Style requirements`
- `Important`

## Example Inputs

These are the kinds of inputs the skill is built for:

```yaml
rawIdea: guardrails
mode: auto
domain: ai
tone: deadpan
platformTarget: comic_only
```

```yaml
rawIdea: Chain of Thought
mode: auto
domain: ai
tone: deadpan
platformTarget: comic_only
```

```yaml
rawIdea: Open Office
mode: satire
domain: office
tone: deadpan
platformTarget: comic_only
```

## Preview

### Model Distillation

![Model Distillation Preview](./assets/model-distillation.png)

### Highest Priority

![Highest Priority Preview](./assets/highest-priority.png)

### Human in the Loop

![Human in the Loop Preview](./assets/human-in-the-loop.png)

## How It Thinks

The skill follows a fixed pipeline instead of dumping one loose answer:

1. classify the idea and pick the best mode
2. generate 3 candidate angles in that mode
3. lock the strongest comic premise
4. turn it into a 4-panel storyboard
5. generate an English image prompt
6. add guardrails and recovery prompts

It is especially strict about two things:

- not letting literal ideas drift into abstract reflection
- making sure Panel 4 is stronger than Panel 3

It also defaults to:

- no speaker-name prefixes in dialogue
- a meaningful Panel 2 that actually advances the joke
- a cleaner one-line payoff in Panel 4 when possible

## Package Contents

This package includes:

- `SKILL.md`
- `agents/openai.yaml`
- `references/schema.md`
- `references/workflow.md`
- `references/prompt-templates.md`
- `references/guardrails.md`
- `references/examples.md`

The references include built-in cases such as:

- `Highest Priority`
- `Open Office`
- `Human in the Loop`
- `Model Distillation`
- `guardrails`

## Runtime Notes

This is an **asset package**, not a CLI.

It does **not** auto-install itself into a host runtime. It is intended for runtimes that:

- load skill assets from installed npm packages
- load skills from explicit package paths
- support skill discovery by metadata and keyword matching

Exported asset paths:

- `concept-comic-skill/SKILL.md`
- `concept-comic-skill/agents/openai.yaml`
- `concept-comic-skill/references/schema.md`
- `concept-comic-skill/references/workflow.md`
- `concept-comic-skill/references/prompt-templates.md`
- `concept-comic-skill/references/guardrails.md`
- `concept-comic-skill/references/examples.md`

## License

MIT
