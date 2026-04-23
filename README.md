# concept-comic-skill

`concept-comic-skill` is an npm-distributed skill asset package for turning a word, phrase, term, or concept into a four-panel comic creation package.

The skill is optimized for:

- Chinese `Idea Breakdown` and `Storyboard`
- English image prompts
- literal / satire / reflective mode control
- deadpan webcomic-style joke development
- AI terms, office concepts, product language, and workflow jargon

## Install

```bash
npm install concept-comic-skill
```

## What This Package Contains

- `SKILL.md`
- `agents/openai.yaml`
- `references/schema.md`
- `references/workflow.md`
- `references/prompt-templates.md`
- `references/guardrails.md`
- `references/examples.md`

This package does not auto-install the skill into a host runtime. It is intended for hosts that load skill assets from installed npm packages or from explicit package paths.

## Triggering Intents

Hosts can use the skill name directly:

- `$concept-comic-skill`

Hosts that support keyword-based routing should consider these trigger phrases:

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

## Example Usage

```text
Use $concept-comic-skill to turn "guardrails" into a four-panel comic.
```

```text
Use $concept-comic-skill to turn "Chain of Thought" into a deadpan webcomic.
```

```text
用 $concept-comic-skill 把 “Human in the Loop” 做成四格小漫画。
```

## Asset Paths

If a host wants to load files directly from the package, these paths are exported:

- `concept-comic-skill/SKILL.md`
- `concept-comic-skill/agents/openai.yaml`
- `concept-comic-skill/references/schema.md`
- `concept-comic-skill/references/workflow.md`
- `concept-comic-skill/references/prompt-templates.md`
- `concept-comic-skill/references/guardrails.md`
- `concept-comic-skill/references/examples.md`

## Package Purpose

This is an asset package, not a CLI. It ships the skill definition and supporting prompt assets so another runtime can discover, load, and invoke the skill.

## License

MIT
