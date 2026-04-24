# Prompt 06 · The Bug Hunt

## When to use

Something's broken. You don't know why. You've already tried two things. You're frustrated.

**Typical moment:** "It works on my machine" / "This was working yesterday" / "The error message makes no sense."

## The prompt

```
[PASTE ERROR / DESCRIBE BEHAVIOR]

Expected: [what should happen]
Actual: [what is happening]

Relevant files:
— [file 1]
— [file 2]

What I've tried:
— [attempt 1] → [result]
— [attempt 2] → [result]

Your process:
1. List 3 root causes, ranked by likelihood
2. How to verify each in 1 line
3. Pick the most likely
4. Propose the fix
5. Warn me of side effects

# Do not blindly patch. Diagnose first.
```

## An example, filled in

> **`TypeError: Cannot read properties of undefined (reading 'latitude')` in `components/CheckInButton.tsx:47`**
>
> **Expected:** User taps check-in, GPS permission prompt appears, coordinates capture.
>
> **Actual:** On some Android devices (Samsung M-series, Xiaomi Redmi), the button throws this error immediately. iOS and Pixel devices work fine.
>
> **Relevant files:**
> — `components/CheckInButton.tsx`
> — `hooks/useGeolocation.ts`
> — `lib/gps-utils.ts`
>
> **What I've tried:**
> — Added `navigator.geolocation` null check → still throws on same devices
> — Wrapped in try/catch → error is caught but user never sees GPS prompt
>
> **Your process:**
> 1. List 3 root causes, ranked by likelihood
> 2. How to verify each in 1 line
> 3. Pick the most likely
> 4. Propose the fix
> 5. Warn me of side effects
>
> Do not blindly patch. Diagnose first.

## Why it works

AI tools love to guess-and-patch. You describe a bug, it immediately proposes a fix — often before you've given it enough context to reason properly. This prompt forces a diagnostic pause.

**1. Ranked hypotheses**
Instead of *one* answer, the AI gives you three — ordered by likelihood. Even if the top one is wrong, the #2 and #3 are often where the real bug lives. You're maximizing the chance of hitting the problem in the first response.

**2. Verification in one line**
"How would I verify this in 1 line?" is a check on the AI's thinking. If it can't give you a one-line test, the hypothesis is too vague and you should push back.

**3. "Warn me of side effects"**
The best bug fixes often break something else. This clause forces the AI to think about downstream impact before you merge the fix. You'd be surprised how often it responds with "this fix will also affect the onboarding flow because both share `useGeolocation`."

**4. "What I've tried" is not optional**
If you don't tell the AI what you've already ruled out, it will confidently suggest the first thing you tried. Always list your failed attempts.

## Common mistake

People paste the error but forget the "expected vs. actual" section. The AI can see the error, but it doesn't know what *should* happen. You end up with a fix that makes the error go away but doesn't actually solve your problem.

Always say both: what's happening, and what you wanted to happen.
