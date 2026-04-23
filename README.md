<div align="center">

# Concept Comic Skill

### 把黑话，画成笑话  
### Turn jargon into deadpan four-panel comics.

Transform AI terms, office jargon, and product concepts into a complete **four-panel comic package** — including **angle options**, **Chinese storyboard**, and **English image prompt**.

![License: MIT](https://img.shields.io/badge/license-MIT-black)
![Format: 4 panel comic](https://img.shields.io/badge/format-4_panel_comic-black)
![Tone: deadpan](https://img.shields.io/badge/tone-deadpan-lightgrey)
![Output: storyboard + prompt](https://img.shields.io/badge/output-storyboard_%2B_prompt-6ee7b7)

**concept → angle → storyboard → prompt**

</div>

<p align="center">
  <img src="./assets/human-in-the-loop.png" alt="Concept Comic Skill preview" width="900" />
</p>

<p align="center">
  Input one concept → get a structured comic package.
</p>

---

## Install

```bash
npx skills add SuperKatrina123/concept-comic-skill
```

---

## What it does

`concept-comic-skill` turns a **word, phrase, term, or abstract concept** into a comic-ready output package.

It is designed for people who want to turn things like:

- AI terms
- office jargon
- product language
- workflow concepts
- short meme premises

into clean, deadpan, social-media-friendly four-panel comics.

By default, the output is optimized for:

- Chinese `Idea Breakdown` and `Storyboard`
- English image prompts
- horizontal `4:3` framing
- clean `2x2` four-panel layout
- large readable title above the comic
- literal / satire / reflective mode control
- deadpan webcomic-style humor

---

## What you get

Given one raw idea, the skill returns a structured package with:

- mode decision
- 3 angle candidates
- idea breakdown
- 4-panel Chinese storyboard
- English image prompt in a fixed production template
- anti-drift guardrail prompt
- recovery prompt for rerolling bad generations
- optional social copy

This makes the output useful both for **human ideation** and for **downstream image-generation workflows**.

---

## Good for concepts like

- Human in the Loop
- Guardrails
- Context Window
- Tool Calling
- Chain of Thought
- Open Office
- Highest Priority
- Model Distillation

---

## Quick example

**Input**

```yaml
rawIdea: Human in the Loop
mode: auto
domain: ai
tone: deadpan
platformTarget: comic_only
```

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
