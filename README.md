# Multiplier Session · AI Prompt Library

A working set of prompts for AI-driven UI development — shared during the *"The UI is the Moat"* session at Multiplier, 2026.

---

## The core idea

Code is commoditized. Every team has AI. The only thing that still separates a good product from a generic one is the UI — and the **design document** that controls it.

This repo has two kinds of files:

1. **`agents-md-starter.md`** — the minimal design doc you drop at the root of any project. Every AI coding tool (Claude Code, Cursor, OpenCode, Windsurf, Copilot) will auto-load it and make every prompt produce consistent output.
2. **`prompts/*.md`** — six reusable prompt templates for the situations you'll hit every week: building something new, fixing bugs, writing tests, refactoring legacy code, handling critique, and extracting a design doc from image references.

---

## How to use this repo

### Step 1 — Drop the design doc into your project root

Copy `agents-md-starter.md` to the root of your project. Rename it based on the AI tool you use:

| Tool | Filename |
| --- | --- |
| OpenCode | `AGENTS.md` |
| Claude Code | `CLAUDE.md` |
| Cursor | `.cursorrules` |
| Windsurf | `.windsurfrules` |
| GitHub Copilot | `.github/copilot-instructions.md` |
| Zed AI | `.rules` |

Edit the colors, fonts, and rules to match your brand. This file is **living** — every time you catch the AI defaulting to generic slop, add a new "don't" rule.

### Step 2 — Use the prompts when you hit each situation

The prompts in `/prompts` are templates with `[PLACEHOLDERS]`. Copy, paste, fill in the brackets, and send to your AI tool. The templates force the right structure; you just supply the specifics.

---

## The prompts, at a glance

| # | Prompt | When to use |
| --- | --- | --- |
| 01 | [Extract AGENTS.md from images](prompts/01-extract-agents-md.md) | You have inspiration screenshots and want to turn them into a design doc |
| 02 | [The Scaffold](prompts/02-scaffold.md) | Starting a new feature or project from zero |
| 03 | [Critique & Fix](prompts/03-critique-and-fix.md) | Someone reviewed your code and flagged issues |
| 04 | [Spec → Tests](prompts/04-spec-to-tests.md) | Feature is built, now you need UAT / unit tests |
| 05 | [Refactor with Rails](prompts/05-refactor-with-rails.md) | Cleaning up legacy code without a full rewrite |
| 06 | [The Bug Hunt](prompts/06-bug-hunt.md) | Something's broken, you don't know why |

---

## Why this works

Good AI output isn't a prompting problem. It's a **context** problem. These templates work because they give the AI:

1. A **design doc** (`AGENTS.md`) that persists across every conversation — so the AI inherits your taste automatically.
2. **Situation-specific scaffolds** (the prompts) that force the right kind of reasoning for the task — diagnosing before patching, explaining tradeoffs, respecting non-negotiables.

Without both, you're rolling dice. With both, you're delegating taste instead of prompting from scratch every time.

---

## The homework

1. **Save three screenshots a week.** Build a Notion or Raindrop board. When you start a new project, you'll already have references.
2. **Your AGENTS.md is a living file.** Every time you catch the AI defaulting to slop, write a new "don't" rule.
3. **Judge competitors visually, not technically.** Your users see the UI, not your backend.
4. **Generic output means your doc is too thin.** Add examples. Add forbidden patterns. Thicken the doc.

---

## Credits

Prepared by [Varun Parmar](https://linkedin.com/in/varunparmar) · [varun@gradeless.ai](mailto:varun@gradeless.ai)

Shared under a permissive license — fork, remix, use in client projects, no attribution required.
