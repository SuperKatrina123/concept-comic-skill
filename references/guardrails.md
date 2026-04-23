# Guardrails

## Universal Guardrail

```text
Preserve the original comic premise.
Keep the comic visually simple and easy to read.
Each panel should serve exactly one clear narrative function.
Do not add unnecessary backstory or visual clutter.
The final panel must deliver the strongest payoff.
```

## Literal Guardrail

```text
The joke must stay strictly literal.
Do not reinterpret the phrase metaphorically.
Do not turn it into a life lesson, emotional reflection, or philosophical message.
Humor must come from direct literal visualization of the phrase.
Preserve the original wording and comic premise.
```

## Satire Guardrail

```text
Keep the satire grounded in real workplace or product reality.
Do not turn the joke into pure wordplay only.
Do not soften the absurdity into vague commentary.
The humor should come from exposing the gap between stated ideal and actual behavior.
```

## Reflective Guardrail

```text
Keep the comic observant and concrete.
Do not drift into abstract philosophy.
The reflection must still be visualizable as a four-panel comic.
Avoid turning the whole piece into a caption with illustrations.
```

## Recovery Prompt Template

```text
You drifted away from the original comic premise.

Return to this exact idea:
[core premise]

Requirements:
- Keep the mode as [literal / satire / reflective].
- Do not replace the premise with a broader message.
- Do not make it more philosophical, emotional, or metaphorical.
- Keep the same 4-panel structure:
  1. setup
  2. trigger
  3. twist
  4. strongest payoff
- Preserve the visual joke.
- Rewrite only to improve clarity, pacing, and punch.
```

## Literal Recovery Add-On

```text
This joke works only if the phrase is interpreted directly and physically.
```

## Common Drift Patterns

- `literal` drifts into self-help or reflection
- `satire` loses the system critique and becomes a literal pun
- `reflective` becomes caption-first and image-second
- panel 4 explains instead of landing the joke
