---
name: ui-design-brain
description: Gives Anti-Gravity real UI component knowledge — best practices, vocabulary, layout patterns, and design-system conventions from 95 real design systems. Loads automatically for any UI building task.
---

# UI Design Brain Skill

When you're building any UI — a dashboard, landing page, form, or component — this skill loads a vocabulary and best-practices reference drawn from 2,676 examples across 95 real-world design systems (via [component.gallery](https://component.gallery)).

The result: you stop getting generic-looking AI output and start getting interfaces that look like they came from a real product team.

---

## When This Skill Activates

Apply automatically whenever the user asks to:
- Build, design, or generate any web UI
- Create a landing page, dashboard, settings page, or marketing site
- Build a React, Next.js, Tailwind, or HTML/CSS component
- Fix or improve the aesthetics of an existing UI
- Use `visual-builder` skill (this skill loads alongside it)
- Ask "make this look better" or "polish this UI"

---

## Design Philosophy

Every generated interface must feel **modern, minimal, and production-ready** — not like a template, not like a bootcamp project.

### Non-negotiables:
1. **Typography hierarchy** — H1 > H2 > body > caption. Never let everything be the same size.
2. **Spacing system** — use a consistent scale (4px base). No arbitrary margins.
3. **Color discipline** — one primary, one accent, neutrals for everything else. Semantic colors for status (success/warning/error).
4. **State coverage** — every interactive element needs: default, hover, focus, active, disabled states.
5. **Empty states** — every list, table, or feed needs a designed empty state (not a blank void).
6. **Loading states** — skeleton screens for layout-heavy content; spinners only for small inline ops.
7. **Mobile-first** — design for 375px, then expand. Never the reverse.

---

## Workflow

**STEP 1 — Name the components:**
Before writing any code, identify exactly which components are needed. Use the vocabulary in `components.md` (in this skill folder). This prevents you from inventing component names or patterns that don't exist in real design systems.

**STEP 2 — Apply best practices per component:**
For each identified component, apply the rules in `components.md`. Don't invent behavior — follow established patterns.

**STEP 3 — Choose a design direction:**
Based on context, select one:
- **Clinical / Minimal** — white space dominant, light grays, subtle borders, Inter font
- **Dashboard / Data** — dense, information-rich, dark sidebar, card-based layout
- **Marketing / Landing** — bold typography, gradient accents, high contrast CTAs
- **App / Consumer** — rounded corners, warm tones, playful micro-animations

**STEP 4 — Generate code:**
- React + Tailwind CSS as default
- Use `shadcn/ui` component primitives where appropriate
- TypeScript with explicit prop interfaces
- Responsive from the first line

---

## Anti-Patterns — Never Generate These

These patterns immediately signal generic, low-quality UI:

| Anti-Pattern | Why It's Bad | What to Do Instead |
|---|---|---|
| Rainbow status badges | No semantic meaning | 3 colors max: green/yellow/red |
| Modal inside modal | Confusing UX | Use a page or a drawer for complex flows |
| Disabled submit with no explanation | User has no idea what's missing | Inline validation showing what's required |
| Spinner for full-page loads | Shows nothing about layout | Skeleton screen matching actual layout |
| "Click here" link text | Not descriptive | Link text = the destination ("View report") |
| Hamburger menu on desktop | Hidden navigation wastes space | Visible sidebar or top nav |
| Auto-advancing carousel | User loses control | Dots indicator + manual arrows only |
| Placeholder-only form fields | Label disappears when typing | Always use visible labels above inputs |
| Equal-weight buttons everywhere | No visual hierarchy | Primary / Secondary / Ghost hierarchy |
| Text under 12px | Illegible, especially on mobile | Body min 14px, prefer 16px |
| Hardcoded colors | Impossible to theme | Use CSS variables or Tailwind semantic tokens |
| Border + shadow on cards | Visual overload | Shadow OR border, not both |

---

## Reference

Full component vocabulary with best practices, aliases, and layout patterns: see `components.md` in this skill folder.

Source: [component.gallery](https://component.gallery) — 60 components, 95 design systems, 2,676 real-world examples.

---

## Tags
`[builder]` `[creator]` `[all-personas]`

## Last tested: March 2026
