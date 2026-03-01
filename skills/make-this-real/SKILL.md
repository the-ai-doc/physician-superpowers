---
name: make-this-real
description: Paste a voice note, rambling thought, or stream of consciousness — get back a structured feature spec and working code
---

# Make This Real Skill

You had an idea in the car, dictated it into your phone, and now it's a wall of unstructured text. Or you brain-dumped something messy into the chat. This skill extracts the real idea buried in the noise and turns it into something you can actually build.

---

## Usage

Say: **"make this real"** then paste the raw text.

Examples:
- *"make this real — [paste voice note transcript]"*
- *"make this real — okay so I want like a thing where physicians can like share their schedules and then patients can book time and maybe there's like a waitlist and notifications or whatever"*
- *"make this real — [paste 3 paragraphs of scattered thoughts]*

---

## What It Produces

1. **Extracted core idea** — one clear sentence describing what this actually is
2. **User story** — "As a [user], I want to [action] so that [outcome]"
3. **MVP feature list** — the 3–5 things that make this useful (not the full vision, just the core)
4. **What it's NOT** — things mentioned that aren't core and can come later
5. **First screen** — what the user sees when they open this thing
6. **Stack recommendation** — what to build it on and why
7. **First working version** — built immediately after spec is confirmed

---

## Instructions for the Agent

When triggered:

**STEP 1 — Read the raw input:**
Don't judge the quality. Voice notes and brain dumps are full of signal — find it.

**STEP 2 — Extract the core:**
Ask yourself:
- What is the user actually trying to accomplish?
- Who uses this thing?
- What's the one action that makes this valuable?
- What can wait for v2?

**STEP 3 — Write the spec (concise, formatted):**
```
IDEA: [One clear sentence]

WHO: [Who uses this and in what context]

CORE ACTION: [The one thing this lets someone do]

MVP FEATURES:
1. [Must have]
2. [Must have]
3. [Must have]

SAVE FOR LATER:
- [Thing mentioned but not core]
- [Thing mentioned but not core]

FIRST SCREEN: [Describe what the user sees when they open it]

STACK: [Framework] + [Database if needed] + [Key lib]

REASON: [Why this stack for this specific thing]
```

**STEP 4 — Confirm:**
*"Here's what I extracted. Is this right? Or should I adjust before I start building?"*

**STEP 5 — Build it:**
As soon as confirmed (or immediately if it's clear), start building. Use `lets-build` skill logic. Get something running.

---

## Tags
`[builder]` `[all-personas]`

## Last tested: March 2026
