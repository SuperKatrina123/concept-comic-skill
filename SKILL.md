---
name: concept-comic-skill
description: Use when the user asks for a four-panel comic, webcomic, literal comic, satire comic, AI term comic, workplace concept comic, deadpan comic, or wants to turn a word, phrase, or concept into a comic with storyboards and image prompts.
---

# Concept Comic Skill

Turn a term or premise into a clean four-panel comic package for simple webcomic-style posts.

## When to Use

Use this skill when the user wants to:

- develop a term, concept, or meme into a four-panel comic
- explore literal, satire, or reflective joke directions
- get a Chinese storyboard plus English image prompts
- keep a visual joke from drifting into abstract commentary
- generate optional Xiaohongshu or X copy around the comic

Do not use this skill for:

- long-form comics or multi-page narratives
- polished UI products
- direct image generation or model execution
- metaphor-heavy essays with no clear visual premise

## Default Behavior

- If `mode` is unspecified, infer the best mode first.
- Keep `Idea Breakdown`, `Storyboard`, and social copy in Chinese.
- Keep `Image Prompt`, `Guardrail Prompt`, and `Recovery Prompt` in English.
- Default tone is `deadpan`.
- Default output path is: 3 angle candidates in one mode, then 1 full comic package.

## Workflow

Follow this order. Do not merge steps into one free-form response.

1. Classify the idea and choose `literal`, `satire`, or `reflective`.
2. Generate 3 angle candidates within the selected mode.
3. Expand the strongest angle into `ideaBreakdown`.
4. Write a 4-panel Chinese storyboard.
5. Generate an English image prompt package.
6. Generate guardrails, recovery prompt, and optional social copy.

Preserve the chosen premise across all later stages. Do not silently switch modes midway.

## Hard Rules

- Panel flow is fixed: `setup -> trigger -> twist -> payoff`.
- Each panel gets one narrative job.
- Panel 4 must hit harder than Panel 3.
- Panel 4 must add a new hit, escalation, or deadpan conclusion instead of merely restating Panel 3.
- Keep dialogue short.
- Prefer visual clarity over explanation.
- Favor simple webcomic staging over cinematic spectacle.
- In `literal` mode, do not turn the joke into a lesson, metaphor, or reflective caption.

## References

Read only what you need:

- For input and output contract: `references/schema.md`
- For mode definitions, panel rules, and pipeline: `references/workflow.md`
- For system prompt and stage prompts: `references/prompt-templates.md`
- For anti-drift and recovery controls: `references/guardrails.md`
- For proven baselines and examples: `references/examples.md`

## Output Contract

Return a structured package with:

- `modeDecision`
- `angleCandidates`
- `ideaBreakdown`
- `storyboard`
- `imagePrompt`
- `guardrailPrompt`
- `recoveryPrompt`
- `socialCopy` when requested
