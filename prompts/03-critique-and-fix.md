# Prompt 03 · Critique & Fix

## When to use

You have working code. Someone (a designer, PM, QA, or senior eng) reviewed it and gave you a list of issues. You need fixes — not a rewrite.

**Typical moment:** "The PM says the signup flow skips a step" / "Designer flagged three inconsistencies on the dashboard" / "QA found two edge cases."

## The prompt

```
Look at [file / component].

A [role — designer / PM / QA] reviewed this and flagged:

1. [issue 1]
2. [issue 2]
3. [issue 3]

Fix these with production-grade patterns.

For each fix, explain:
— What you changed
— Why that approach (2 lines)
— What you rejected and why

Output the changes, then the explanation.
```

## An example, filled in

> Look at `components/StoreAuditForm.tsx`.
>
> A **designer** reviewed this and flagged:
>
> 1. The submit button moves position after validation errors — causes rage-clicks
> 2. Photo upload placeholder doesn't show file size constraints (max 5MB)
> 3. The "stock OOS" toggles have no loading state between click and save
>
> Fix these with production-grade patterns.
>
> **For each fix, explain:**
> — What you changed
> — Why that approach (2 lines)
> — What you rejected and why
>
> Output the changes, then the explanation.

## Why it works

The magic line is **"explain what you rejected and why."**

Without it, the AI grabs the first pattern it sees and ships a fix. With it, the AI has to articulate tradeoffs — which means it actually thinks through the options before picking one. You'll often see it say things like:

> "I considered disabling the button during validation errors, but that would hide the error state. Instead I reserved fixed space for error messages so the button position is stable."

That's senior-engineer reasoning, and you only get it by asking for it explicitly. This pattern also makes AI-generated PRs much easier to review — you see the *why*, not just the *what*.

## Pairs well with

**Prompt 05 · Refactor with Rails** — when the critique is structural ("this whole file is too coupled") rather than behavioral ("this button is wrong").
