# Prompt 02 · The Scaffold

## When to use

You're starting a new feature or project from zero. Empty folder. Blank file. The "build me X" moment.

**Typical moment:** "I need to build a check-in screen for field promoters" / "I need a new settings page" / "Give me a new internal tool for the ops team."

## The prompt

```
Build a [WHAT] for [WHO] that [DOES WHAT].

Tech stack: [languages / frameworks / libraries]

Context:
— [constraint 1]
— [constraint 2]

Build these screens:
1. [screen] — what it shows, actions
2. [screen] — what it shows, actions

Design principles:
— Apply the AGENTS.md design doc
— [project-specific override]

Deliverables: working code, seed data, README.

# Start. Ask only if genuinely ambiguous.
```

## An example, filled in

> Build a **promoter check-in app** for **field associates at Multiplier** that **logs their daily store visits with GPS + photo**.
>
> **Tech stack:** Next.js 15, TypeScript, Tailwind, Zustand for state.
>
> **Context:**
> — Mobile-first, 375px base
> — Offline-tolerant (spotty 4G in tier-2 cities)
> — Hindi + English content mixed
>
> **Build these screens:**
> 1. Login — phone OTP, language toggle
> 2. Today — assigned store card, check-in CTA
> 3. Check-in — GPS capture, photo upload placeholder, 5 SKU toggles
> 4. Summary — time spent, what was logged, checkout CTA
>
> **Design principles:**
> — Apply the AGENTS.md design doc
> — 48px minimum tap targets (field users on small phones)
>
> **Deliverables:** working code, seed data, README.

## Why it works

Most devs prompt with a one-liner ("build me a check-in app") and wonder why the output misses the mark. This scaffold forces separation of four critical pieces:

- **What** (the artifact)
- **Who** (the user)
- **How** (tech + constraints)
- **Done looks like** (deliverables)

Skipping any one of these is what produces bad first drafts. The prompt also ends with *"Ask only if genuinely ambiguous"* — which prevents the AI from burning a full turn on clarifying questions that you've already answered.
