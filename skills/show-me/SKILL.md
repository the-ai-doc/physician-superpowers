---
name: show-me
description: Instantly screenshot your running dev server and display it in the conversation — then fix what you point at
---

# Show Me Skill

Opens your dev server in a browser, takes a screenshot, and displays it right in the conversation. Then you point at what's wrong and it fixes it — with another screenshot to confirm.

No more switching windows. No more "does it look right?" guessing.

---

## Usage

Say: **"show me"**

Or more specifically:
- *"show me the dashboard page"*
- *"show me what the mobile view looks like"*
- *"show me and fix the button alignment"*

---

## How It Works

1. Detects your running dev server (checks common ports: 3000, 3001, 5173, 8080)
2. Opens it in a browser via `browser_subagent`
3. Takes a full-page screenshot
4. Displays it in the conversation
5. If you point at something: traces it to the exact component/CSS and fixes it
6. Takes a second screenshot showing the before/after

---

## Instructions for the Agent

When triggered:

**STEP 1 — Find the dev server:**
Run `lsof -i :3000 -i :3001 -i :5173 -i :8080 | grep LISTEN` to find what's running. Use the first active port found.

**STEP 2 — Launch browser and screenshot:**
Use `browser_subagent` to:
- Navigate to `http://localhost:[PORT]`
- Wait 2 seconds for full render
- Take a full-page screenshot
- Return the screenshot

**STEP 3 — Display and ask:**
Show the screenshot. If the user didn't specify what to fix, ask:
*"Here's what your app looks like right now. What do you want to change?"*

**STEP 4 — Trace and fix:**
When the user points at something:
- Identify the component responsible (search the codebase for the text, class, or element)
- Locate the exact file and line
- Apply the fix
- Take a new screenshot to confirm

**STEP 5 — Confirm:**
Show before/after screenshots. Ask: *"Better? Or keep adjusting?"*

---

## Tips
- Works with Next.js, Vite, React, Vue — anything running on localhost
- If nothing is running, say so and offer to start the dev server
- For mobile view: use `browser_subagent` with a 375px viewport width
- Last tested: March 2026
