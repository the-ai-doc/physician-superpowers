---
name: turbo-mode
description: Skip repetitive approval prompts for known-safe operations and move at full speed — no hand-holding
---

# Turbo Mode Skill

When you're in a flow state and Anti-Gravity keeps asking "are you sure?" for things you've already approved a dozen times — this stops that.

Turbo mode signals to the agent that you trust it to execute known-safe operations without confirmation. You stay focused. The work keeps moving.

---

## Usage

Say: **"turbo mode"**

Or inline:
- *"turbo mode — refactor all these components to use the new design system"*
- *"turbo mode on, clean up all the TypeScript errors"*
- *"turn off turbo mode"* to restore normal confirmations

---

## What Counts as "Known-Safe" in Turbo Mode

✅ Auto-approved (no prompt):
- File edits and rewrites
- Creating new files
- Running build/lint/type-check commands
- Installing npm packages
- Git add and commit
- Refactoring within existing files

⚠️ Still requires confirmation even in turbo mode:
- Deleting files
- Git push to main
- Any destructive database operation
- Sending emails or API calls to external services
- Anything touching production environment variables

---

## Instructions for the Agent

When turbo mode is activated:

1. Acknowledge it: *"Turbo mode on. I'll skip confirmations for safe operations and move fast. Say 'turn off turbo mode' to restore normal flow."*

2. Set an internal flag: proceed with safe operations without asking each time.

3. For any operation in the ⚠️ list above — still pause and confirm, even in turbo mode. Briefly note why: *"Pausing turbo mode — this deletes a file."*

4. When the task is complete, report back what was done in a single summary instead of step-by-step.

5. Turbo mode ends automatically when the current task is complete, or when the user says "turn off turbo mode."

---

## Tags
`[builder]` `[all-personas]`

## Last tested: March 2026
