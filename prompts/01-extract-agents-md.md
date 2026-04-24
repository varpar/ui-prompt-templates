# Prompt 01 · Extract AGENTS.md from images

## When to use

You have 3–5 screenshots of products whose design language you want to borrow from, and you want to turn them into a working design document that your AI coding tool will use on every future prompt.

**Typical moment:** "I love how Linear / Stripe / Arc looks. How do I get the AI to build things that feel like that?"

## The prompt

```
I'm attaching [3-5 screenshots] of products whose design language I want to build on.

Look at them together. Extract the common design grammar. Write it as a Markdown design doc with these sections:

# 00 / AI INSTRUCTIONS
# 01 / PHILOSOPHY
# 02 / COLOR TOKENS (as CSS variables)
# 03 / TYPOGRAPHY (fonts, sizes, usage)
# 04 / LAYOUT (spacing, grid, alignment)
# 05 / COMPONENTS (cards, forms, etc.)
# 06 / MOTION
# 07 / DO / DON'T (explicit rules)
# 08 / QUICKSTART (kickoff prompt)

Rules:
— Name colors with roles, not just hex (--bg, --ink, --accent — not "blue")
— Explain the why behind choices
— Be opinionated in "don'ts"
— Do NOT invent what isn't visible

Output: the full Markdown, ready to paste into AGENTS.md at project root.
```

## How to use it

1. Go to **Mobbin**, **Godly**, **Land-book**, or **Refero**.
2. Grab 3–5 screenshots of products whose *vibe* matches what you're building.
3. Open a Claude or ChatGPT conversation, attach all images in one message, paste the prompt above.
4. Review the output. The first draft is ~80% there.
5. Fix what's wrong. Add the "don'ts" it missed. Name the tokens.
6. Save the final version as `AGENTS.md` (or the equivalent filename for your tool) in your project root.

## Why it works

- **Role-based tokens** force the AI to think semantically (`--accent`), not cosmetically (`blue`). This makes the doc portable when you rebrand.
- **The "do not invent" rule** prevents hallucination. The AI will stay grounded in what's actually in the screenshots.
- **Explicit don'ts** are more powerful than explicit dos for AI output. Models default to safe slop; naming the slop out loud stops it.
- **Nine fixed sections** force comprehensive coverage. If the AI skips one, you know immediately.
