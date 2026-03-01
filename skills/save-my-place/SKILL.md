---
name: save-my-place
description: Save your exact working context at any moment — what you're building, what's working, what's broken, what you were about to do next
---

# Save My Place Skill

Context switching is a productivity killer. This skill captures your complete mental context in one command so you can walk away, sleep, see patients, attend a meeting — and come back without losing a single thread.

Pair with **"where was I"** to resume.

---

## Usage

Say: **"save my place"**

Or:
- *"save my place before I go"*
- *"save my place, I have to step away"*

To resume later: **"where was I"**

---

## What It Saves

Creates `WHERE-I-WAS.md` in the root of your current project:

```markdown
# Where I Was — [timestamp]

## Project
[Project name and one-line description]

## What I Was Building
[Specific feature or task in progress]

## Current State
- ✅ Working: [what's confirmed working]
- ⚠️ In Progress: [what's partially done]
- ❌ Broken: [what's not working and why]

## The Open Problem
[The exact thing I was trying to figure out when I stopped]

## Decision I Was About to Make
[If applicable — what choice was coming up]

## Next Immediate Step
[The single most important next action]

## Files I Was Working In
[List of recently edited files]

## Notes
[Anything else that's important to remember]
```

---

## Instructions for the Agent

When "save my place" is triggered:

**STEP 1 — Gather context:**
```bash
git status                    # what files changed
git log --oneline -5          # recent commits
git diff --name-only          # what's modified
```
Also read any open TODO files or recent conversation context.

**STEP 2 — Read recently touched files:**
Look at the 3–5 files most recently modified to understand what was in progress.

**STEP 3 — Write WHERE-I-WAS.md:**
Fill in each section with specifics — no vague placeholders. If something is broken, say exactly what the error is.

**STEP 4 — Confirm:**
*"Saved. When you come back, just say 'where was I' and I'll pick up exactly here."*

---

## The "Where Was I" Resume

When triggered with **"where was I"**:

1. Read `WHERE-I-WAS.md`
2. Re-read the files listed in "Files I Was Working In"
3. Give a 3-sentence briefing: what the project is, where you left off, what the next step is
4. Ask: *"Ready to pick up from [Next Immediate Step]?"*
5. Go.

---

## Tags
`[builder]` `[all-personas]`

## Last tested: March 2026
