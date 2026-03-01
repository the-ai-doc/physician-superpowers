---
name: vibe-to-ship
description: Auto-generate a commit message, PR description, and changelog from your recent work — turns a messy vibe coding session into clean, documented, shipped code
---

# Vibe to Ship Skill

You coded in flow state. Things got built. But now you have uncommitted changes, no PR description, and nothing documented.

This skill looks at what you actually did and writes all the boring shipping documentation automatically — commit message, PR description, and changelog entry — so you can merge and move on.

---

## Usage

Say: **"vibe to ship"**

Or:
- *"vibe to ship — I just fixed the authentication flow"*
- *"vibe to ship and push"*

---

## What It Produces

1. **Commit message** — conventional commits format (`feat:`, `fix:`, `refactor:`, etc.)
2. **PR description** — what changed, why, what to test
3. **Changelog entry** — user-facing description of what's new (for `CHANGELOG.md`)
4. **Optional: branch name** — if you forgot to create one

---

## Instructions for the Agent

When triggered:

**STEP 1 — Read what changed:**
```bash
git diff --staged   # staged changes
git diff            # unstaged changes  
git status          # overall picture
git log --oneline -5  # recent commit history for context
```

**STEP 2 — Understand the changes:**
- Read the actual file diffs
- Identify: what files changed, what was added/removed/fixed
- Determine the type: feature / bug fix / refactor / style / docs / chore

**STEP 3 — Generate documentation:**

**Commit message** (one line, max 72 chars):
```
feat(auth): add email confirmation step before dashboard access
```

**PR description** (markdown):
```markdown
## What changed
[Clear description of what was built or fixed]

## Why
[Context — what problem this solves]

## How to test
1. [Step to reproduce or verify]
2. [Expected behavior]

## Screenshots
[If UI changed — note that screenshots should be added]
```

**Changelog entry:**
```markdown
### [version/date]
- Added: [user-facing description]
- Fixed: [bug description]
```

**STEP 4 — Ask to execute:**
*"Here's the documentation for your session. Want me to commit with this message and open a PR?"*

If yes: `git add .` → `git commit -m "[message]"` → `git push`

---

## Tags
`[builder]`

## Last tested: March 2026
