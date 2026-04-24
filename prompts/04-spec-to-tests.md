# Prompt 04 · Spec → Tests

## When to use

Feature's built. Now you need UAT, unit tests, or QA coverage. The part everyone hates and rushes through.

**Typical moment:** "We're about to ship — I need a test plan" / "Write unit tests for this module" / "QA is asking for a UAT matrix."

## The prompt

```
You just built [feature].

Generate [UAT / unit / integration tests].

Format as [markdown table / jest / postman]:
— [column 1]
— [column 2]

Cover:
— Happy path for [top 2-3 scenarios]
— Validation edge cases
— [domain edge case — timeout, offline, bad GPS...]
— Accessibility [UI only]
— One chaos test: [worst-case]

Output as: [filename]
```

## An example, filled in

> You just built the **promoter check-in flow** (Login → Today → Check-in → Summary → Checkout).
>
> Generate a **UAT matrix**.
>
> **Format as a markdown table:**
> — Test ID
> — Scenario
> — Steps
> — Expected Result
> — Pass/Fail
>
> **Cover:**
> — Happy path for (a) first-time user with 1 store assigned, (b) returning user with 5 stores
> — Validation edge cases (empty photo upload, no GPS permission, all SKUs marked OOS)
> — Domain edge case: user loses connectivity mid-check-in and comes back 10 min later
> — Accessibility: keyboard-only navigation, screen reader labels, color contrast
> — One chaos test: server goes down while user is submitting
>
> Output as: `docs/uat-promoter-checkin.md`

## Why it works

Generic "generate tests" prompts get you six happy-path tests and nothing else. This one works because it explicitly names:

- **The format** — you don't spend 20 minutes reformatting someone else's test output
- **Coverage buckets** — not a wish list, mandatory buckets. Happy + validation + domain + a11y + chaos.
- **The "chaos test"** — this is the move that separates a QA plan your team will use from one they'll ignore. Naming a worst-case scenario forces the AI to reason about failure modes rather than just successful paths.

The chaos test is often where you discover the real bugs before production does.

## Variants worth remembering

- **For UAT matrices** → use markdown tables, put them in `/docs`
- **For unit tests** → specify Jest / Vitest / whatever, request AAA format (Arrange-Act-Assert)
- **For integration tests** → specify the runner (Playwright, Cypress) and what to mock vs. hit for real
- **For API tests** → format as Postman collection JSON or `.rest` files
