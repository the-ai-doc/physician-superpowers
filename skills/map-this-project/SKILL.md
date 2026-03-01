---
name: map-this-project
description: Generate a complete visual map of your current project — tech stack, data flow, what's done, what's next
---

# Map This Project Skill

At any point in a project, say "map this project" and get back a clear, intuitive picture of everything — the tech stack, how data flows, what's been built, what's broken, and where you are.

Built for context switching. Built for ADHD. Built for the physician who hasn't touched the project in a week.

---

## Usage

Say: **"map this project"**

---

## How It Works

The agent reads your project structure and produces:

1. **What it is** — Plain language description of what you're building
2. **Tech stack table** — Every layer, identified from package.json, imports, and config files
3. **Page/route map** — Every page or screen, what it does, who sees it
4. **Data flow diagram** — How data moves (text-based ASCII or Mermaid)
5. **Progress snapshot** — What's working, what's in progress, what's not started
6. **Last open context** — What file was last edited, what the current focus appears to be
7. **Next suggested step** — Based on TODOs, open issues, and incomplete code

---

## Instructions for the Agent

When triggered:

**STEP 1 — Read project structure:**
- Run `find . -type f -name "*.tsx" -o -name "*.ts" -o -name "*.js" -o -name "*.py" | grep -v node_modules | grep -v .git | head -60`
- Read `package.json` (or `requirements.txt`, `Cargo.toml`, etc.)
- Read `README.md` if present
- Check for `.env.example` to understand services used

**STEP 2 — Identify stack:**
From package.json dependencies and file structure, identify:
- Framework (Next.js, Vite+React, Django, etc.)
- Styling (Tailwind, CSS modules, styled-components)
- Database (Supabase, Prisma, Mongoose, etc.)
- Auth (Clerk, NextAuth, Supabase Auth)
- Key third-party services

**STEP 3 — Map routes/pages:**
- For Next.js: read `/app` or `/pages` directory structure
- For React: look for Router definitions
- For APIs: look for `/api` routes

**STEP 4 — Assess progress:**
- Look for TODO comments in code
- Look for placeholder content ("Coming soon", "Not implemented")
- Look for empty/stub functions
- Check git log for recent activity (`git log --oneline -10`)

**STEP 5 — Output the map:**
Format:
```
PROJECT: [name]
WHAT IT IS: [2-sentence plain English description]

TECH STACK:
  [layer]: [technology]
  ...

PAGES & ROUTES:
  /[route] → [what it does] ([status: ✅ done / ⚠️ partial / ❌ not started])
  ...

DATA FLOW:
  [ASCII or Mermaid diagram]

WHERE WE ARE:
  Last edited: [file]
  In progress: [feature/area]
  
NEXT SUGGESTED STEP:
  [specific actionable next thing to do]
```

---

## Tags
`[builder]` `[all-personas]`

## Last tested: March 2026
