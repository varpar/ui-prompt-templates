# 00 / AI INSTRUCTIONS

Read this file first. Follow it on every prompt.
Do not introduce colors, fonts, or patterns not listed below.
When in doubt between two options, pick the one closer to these principles.

# 01 / PHILOSOPHY

Precision over decoration. Dark-first. One accent color. Nothing superfluous.
Every visible element should earn its place. If it doesn't communicate or serve a function, remove it.

# 02 / COLOR TOKENS

```css
:root {
  --bg:      #0a0a0a;  /* base background */
  --surface: #141414;  /* elevated surfaces: cards, modals */
  --ink:     #e8e8e8;  /* primary text */
  --ink-dim: #8a8a8a;  /* secondary text, metadata */
  --accent:  #5e6ad2;  /* single accent — use sparingly */
  --rule:    #1e1e1e;  /* borders, dividers */
  --warn:    #e8b25c;  /* warnings only */
  --red:     #e86a5c;  /* errors only */
}
```

Use named tokens in code, never raw hex. If you need a color that isn't here, propose it as a new token first.

# 03 / TYPOGRAPHY

- **Family:** Inter (body + UI). Fallback: system-ui.
- **Scale:** 13 · 15 · 18 · 24 · 36 · 56px. Do not introduce intermediate sizes.
- **Weight:** 400 body, 600 display, 700 only for emphasis
- **Line-height:** 1.5 for body, 1.15 for display
- **Letter-spacing:** -0.02em on large text (24px+), 0 otherwise

# 04 / LAYOUT

- **Grid:** 8px rhythm. All spacing must be a multiple of 8 (8, 16, 24, 32, 48, 64).
- **Max-width:** 1200px for main content. 680px for reading-heavy pages.
- **Alignment:** Left-default. Centered text only for hero moments and empty states.
- **Whitespace:** Generous. When in doubt, add more space, not less.

# 05 / COMPONENTS

**Buttons**
- Radius: 6px
- Height: 36px (default), 44px (touch targets on mobile)
- Variants: solid-accent (primary), ghost (secondary), text (tertiary)
- No gradient fills. No shadows.

**Cards**
- 1px border in `--rule`
- No shadow
- Flat surface in `--surface`
- Padding: 24px default

**Forms**
- Labels above inputs, 13px, `--ink-dim`
- Input height: 40px
- Border: 1px `--rule`, focus state: 1px `--accent`
- Error state: 1px `--red` + helper text below

# 06 / MOTION

- Duration: 150–200ms for micro-interactions, 300ms for transitions.
- Easing: `cubic-bezier(0.4, 0, 0.2, 1)` — standard material curve.
- Forbidden: bouncy springs, parallax scrolling, spinners longer than 1s.

# 07 / DO / DON'T

**DO**
- Thin borders, flat surfaces
- Monochrome base with single accent
- Generous whitespace
- Honest empty states ("No stores assigned yet" — not a clever illustration)
- Italic for emphasis, one word per headline max

**DON'T**
- Shadows, drop-shadows, or elevation beyond 1px borders
- Gradients — not on buttons, not on text, not on backgrounds
- Emoji in UI copy
- Rounded-full pills (stick to 6px radius)
- Purple + pink combinations (the AI-default look)
- More than one accent color
- Centered body text

# 08 / QUICKSTART

When starting a new feature, paste this into your first prompt:

> Build [feature] following the AGENTS.md design doc at project root. Use only the tokens and components defined. If you need a new pattern, propose it as an addition to AGENTS.md first. Output working code, seed data, and a brief README.
