---
name: visual-builder
description: Point at any screenshot or image of a UI and get back a production-ready React component — no manual translation required
---

# Visual Builder Skill

You see a UI somewhere — a screenshot, a photo of a design, a competitor's interface — and you want it built. This skill takes that image and produces a working React/Next.js component, styled with Tailwind, ready to drop into your project.

No more describing what you want. Just show it.

---

## Usage

Say: **"build this UI"** then attach or paste a screenshot.

Or:
- *"build this UI — make it dark mode"*
- *"build this UI but with my color scheme"*
- *"build this UI as a mobile component"*
- Drag an image into the conversation and say *"build this"*

---

## What It Produces

- A complete `.tsx` React component
- Tailwind CSS classes (no inline styles)
- TypeScript props interface
- Responsive by default (mobile + desktop)
- Placeholder data for any dynamic content
- A note on what data/props you'd need to wire up for it to be real

---

## Instructions for the Agent

When triggered with an image:

**STEP 1 — Analyze the screenshot:**
- Identify every UI element: navbar, cards, buttons, inputs, text blocks, images, icons
- Note the layout structure (flex/grid, columns, spacing)
- Identify the color palette (note hex codes if visible)
- Identify the typography hierarchy
- Note any animations or hover states implied by the design

**STEP 2 — Ask clarifying questions (fast — max 2):**
- "Is this for web or mobile?"
- "Use your existing color scheme or match the screenshot exactly?"

Skip these if the answers are obvious from context.

**STEP 3 — Build the component:**

```tsx
// [ComponentName].tsx
import { FC } from 'react'

interface [ComponentName]Props {
  // typed props
}

const [ComponentName]: FC<[ComponentName]Props> = ({ ... }) => {
  return (
    // Tailwind-styled JSX matching the screenshot
  )
}

export default [ComponentName]
```

**STEP 4 — Note what's missing:**
- What data would need to come from an API
- What interactions aren't yet wired (onClick, etc.)
- Any icons that would need a library (lucide-react, heroicons)

**STEP 5 — Offer next steps:**
*"Here's the component. Want me to wire up the interactions, add it to a page, or make a mobile variant?"*

---

## Tags
`[builder]`

## Last tested: March 2026
