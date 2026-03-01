---
name: lets-build
description: Turn any idea — no matter how rough — into a working app immediately. No planning paralysis, no setup friction.
---

# Let's Build Skill

This is the skill for when inspiration hits. You have an idea. It's vivid. You can feel the product. This skill captures that energy before it fades and turns it into a running application — fast.

No lengthy planning. No "first let's set up the project structure." You describe it, it builds it.

---

## Usage

Say: **"let's build"** then describe your idea.

Examples:
- *"let's build — a tool where I paste a YouTube transcript and it extracts the top 10 actionable insights as a numbered list"*
- *"let's build — a personal CRM for tracking who I've messaged on LinkedIn and when"*
- *"let's build — a landing page for my new online course about AI for physicians"*
- *"let's build — a dashboard that shows my Stripe revenue, active subscribers, and churn rate"*

---

## Instructions for the Agent

When triggered:

**STEP 1 — Capture the idea (30 seconds):**
Ask ONE question only if it's truly blocking:
- What's the primary user action? (what does someone DO on this thing?)

Skip all other planning questions. Get moving.

**STEP 2 — Pick the fastest stack:**
Based on what's being built, choose:
- **Landing page / marketing** → HTML + vanilla CSS + JS (fastest to ship, no build step)
- **Internal tool / dashboard** → Next.js + Tailwind + shadcn/ui  
- **Form + data** → Next.js + Supabase
- **Content tool** → Next.js + AI SDK (Vercel)
- **API/automation** → Node.js script or Next.js API route

**STEP 3 — Build the first working version:**
- Scaffold the project if needed (`npx create-next-app` etc.)
- Build the core user flow first — the one thing that makes this useful
- Use placeholder data where real data would come from an API
- Make it look presentable (not beautiful, but not embarrassing)
- Get it running

**STEP 4 — Show it:**
Use `show-me` skill to take a screenshot of the running app. Display it.

**STEP 5 — Offer the next layer:**
*"Here's your first version running. What do you want next — real data wired up, better design, user auth, or deploy it now?"*

---

## Philosophy
The goal is a working thing in under 30 minutes. Not a finished product — a thing that exists, works, and can be shown to someone. Ship the idea before the energy fades.

---

## Tags
`[builder]` `[all-personas]`

## Last tested: March 2026
