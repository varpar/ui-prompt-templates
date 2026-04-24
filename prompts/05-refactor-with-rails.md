# Prompt 05 · Refactor with Rails

## When to use

You're fixing legacy code. You know what's wrong. You don't want a rewrite you can't review.

**Typical moment:** "This component grew to 800 lines" / "This util is used in 12 places, needs splitting" / "I want to add TypeScript types to a JS file without breaking anything."

## The prompt

```
Refactor [file / function].

Goals:
— [goal 1]
— [goal 2]

Non-negotiables (do NOT change):
— External function signatures
— Observable behavior
— [file / import — do not touch]

Process:
1. List what you plan to change
2. Wait for my "go ahead"
3. Then make the changes
4. Show me a diff summary

# Do not rewrite from scratch.
```

## An example, filled in

> Refactor `hooks/useStoreVisits.ts`.
>
> **Goals:**
> — Split the 400-line hook into smaller focused hooks
> — Add TypeScript types (currently untyped)
> — Remove the three `any` casts on lines 87, 143, 201
>
> **Non-negotiables (do NOT change):**
> — External function signatures (`useStoreVisits()` still returns the same shape)
> — Observable behavior — tests in `useStoreVisits.test.ts` must still pass without modification
> — Do not touch the Supabase query functions in `lib/queries.ts`
>
> **Process:**
> 1. List what you plan to change
> 2. Wait for my "go ahead"
> 3. Then make the changes
> 4. Show me a diff summary
>
> Do not rewrite from scratch.

## Why it works

The default failure mode of "refactor this" prompts is: the AI cheerfully rewrites the entire file in a different style, breaks three things you didn't notice, and hands you a PR you can't trust. This prompt fixes that with two moves:

**1. Non-negotiables (explicit)**
You list what *must not* change. The AI treats these as hard constraints, not suggestions. This is especially critical for anything exposed as a public API (exported functions, hook return shapes, component props).

**2. Plan-first protocol**
Step 1 is "list what you plan to change" and step 2 is "wait for my go-ahead." You're inserting a human review gate *before* the expensive step of actually writing code. If the plan is wrong, you catch it in 30 seconds instead of re-reviewing a 600-line diff.

This is the move that makes senior devs trust AI tools for real work. Without it, refactoring is a slot machine. With it, it's a reviewed process.

## Pairs well with

**Prompt 03 · Critique & Fix** — for *behavioral* issues ("this button is wrong").

Use **Refactor with Rails** for *structural* issues ("this whole file is too coupled"). The two are complementary.
