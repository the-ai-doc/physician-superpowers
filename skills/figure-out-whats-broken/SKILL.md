---
name: figure-out-whats-broken
description: Auto-triage any error or dead-end — reads the problem, traces the cause, fixes it, and confirms. No more debugging rabbit holes.
---

# Figure Out What's Broken Skill

You hit an error. The app won't load. Something stopped working and you don't know why. Instead of a debugging rabbit hole, this skill reads the problem, traces the root cause, applies the fix, and confirms it's resolved.

If it can't fix it — it gives you a clear triage report so you know exactly what to decide, not just "something is wrong."

---

## Usage

Say: **"figure out what's broken"**

Or with context:
- *"figure out what's broken — the dashboard page won't load"*
- *"figure out what's broken — I'm getting a 500 error on the API"*
- *"figure out what's broken — the build is failing"*
- *"figure out what's broken — the email isn't sending in production"*

---

## Triage Protocol

**STEP 1 — Gather signals:**
```bash
# Check what's running
lsof -i :3000

# Check recent terminal errors (if visible)
# Read error message provided by user

# Check git for recent changes that may have caused it
git log --oneline -10
git diff HEAD~1
```

**STEP 2 — Read the error:**
If there's an error message — read it precisely. Most errors tell you exactly what's wrong. Don't skip past line numbers, file names, or error types.

**STEP 3 — Trace the cause:**
- Search the codebase for the file/function/variable named in the error
- Look at it — does something look wrong?
- Check for common patterns:
  - **`Cannot read properties of undefined`** → something is null when code expects a value → check where the data comes from
  - **`Module not found`** → import path is wrong, or package wasn't installed
  - **`TypeError`** → type mismatch → check what's being passed in
  - **`500 Internal Server Error`** → check server logs / API route for unhandled error
  - **Build fails** → check for TypeScript errors, missing env vars, bad imports
  - **Works locally, broken in production** → almost always an env var missing in Vercel/production

**STEP 4 — Apply the fix:**
Make the targeted change. Don't refactor everything — fix exactly what's broken.

**STEP 5 — Verify:**
```bash
# Restart dev server if needed
# Re-run the thing that was broken
# Confirm it works
```

**STEP 6 — Report:**
*"Fixed. The issue was [root cause]. I changed [what was changed]. It's working now."*

**If it can't be fixed automatically:**
Produce a triage report:
```
TRIAGE REPORT
━━━━━━━━━━━━━━━

SYMPTOM: [What's broken]
ROOT CAUSE: [What's actually wrong]
WHAT I TRIED: [What was attempted]
WHY IT'S BLOCKED: [What's needed to fix it]

YOUR DECISION:
Option A: [Choice and trade-off]
Option B: [Choice and trade-off]

RECOMMENDED: [Which option and why]
```

No dead ends. Either fixed or a clear decision handed back.

---

## Tags
`[builder]` `[all-personas]`

## Last tested: March 2026
