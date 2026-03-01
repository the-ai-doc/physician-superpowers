# Component Vocabulary Reference
*Drawn from 95 design systems, 2,676 examples via [component.gallery](https://component.gallery)*

This is the vocabulary reference loaded by the `ui-design-brain` skill. Use exact component names and follow the best practices for each.

---

## Layout & Structure

### Header
- Contains: logo, primary nav, user menu, search, CTA
- Stick on scroll for content-heavy apps; static for marketing pages
- Max one primary action (e.g., "Sign up"); secondary actions as links
- Collapse to hamburger only on mobile (<768px)

### Footer
- Contains: secondary nav, legal links, social icons, newsletter
- Keep it light — not a second homepage
- Legal text: 12px, gray-400

### Hero
- One H1, one sub-headline, one CTA (max two CTAs: primary + ghost)
- Image/visual right-aligned on desktop, stacked on mobile
- Background: image with overlay, gradient, or clean white — never busy patterns

### Navigation
- Max 5–7 items in top nav; use mega-menu or dropdown for more
- Active state: underline or color change — always visible
- Current page: `aria-current="page"` for accessibility
- Mobile: full-screen overlay or bottom sheet, never nested hamburgers

### Sidebar
- Left sidebar: navigation (fixed position)
- Right sidebar: contextual detail/filters (scrolls with content)
- Dark sidebar: works for data-dense apps; needs 4:1 contrast ratio
- Collapsible to icon-only with tooltip labels

### Stack
- Vertical stack: consistent gap (16px or 24px between sections)
- Horizontal stack: flex row with gap; wrap on mobile
- Use CSS Grid for complex 2D layouts; Flexbox for 1D

---

## Feedback & Status

### Alert
- Types: info (blue), success (green), warning (amber), error (red)
- Always include icon + semantic color — never rely on color alone
- Dismissible: X button in top-right
- Max 2 sentences; link to action if needed
- Placement: top of the relevant section, not buried in page

### Toast / Notification
- Auto-dismiss: 4–6 seconds for success; persistent for errors
- Include "Undo" for destructive actions
- Stack multiple toasts vertically; max 3 visible at once
- Bottom-right on desktop; top-center on mobile

### Badge
- 1–2 words max; never a full sentence
- Pill shape for status (rounded-full); square for counts
- Color semantics: green=active/success, yellow=pending/warning, red=error/critical, gray=inactive
- Limit to 3–4 badge colors per product

### Progress Bar
- Show percentage text alongside bar
- Animated smooth fill (300ms transition)
- Use for multi-step processes (onboarding, uploads)
- Indeterminate variant for unknown duration

### Progress Indicator / Stepper
- Show all steps upfront; user sees where they are in the journey
- Completed steps: checkmark; current: highlighted; future: gray
- Allow clicking completed steps to go back
- Mobile: compress to "Step 2 of 5" text

### Spinner
- Use only for inline, small-scope loading (<1 second expected)
- Never full-page — use skeleton instead
- 16px–24px size; centered; matches brand color
- Include `aria-label="Loading"` for accessibility

### Skeleton
- Match the exact shape and proportions of the real content
- Shimmer animation (left-to-right gradient sweep, 1.5s loop)
- Never show skeletons for longer than 3 seconds — show error state instead
- Use for: cards, tables, profile sections, feed items

### Empty State
- Three parts: illustration/icon + headline + CTA
- Positive framing: "No results yet — create your first one" not "Nothing found"
- CTA should directly address the emptiness: "Add a skill", "Create project"
- Use for: tables, lists, search results, dashboards

---

## Data Display

### Table
- Sticky first column for horizontal scroll; sticky header for vertical scroll
- Right-align all numbers; left-align text
- Sortable columns: show direction indicator on hover + when active
- Row hover: subtle background highlight
- Actions: show on row hover (edit/delete icons), or use kebab menu
- Pagination or infinite scroll — never both

### Card
- Structure: [media] → [title] → [meta/description] → [action]
- Shadow OR border — never both
- Consistent corner radius across all cards (4px, 8px, or 12px — pick one)
- Clickable card: full surface area is the click target
- Avoid more than 3 cards per row on desktop

### List
- Dividers OR spacing between items — not both
- Consistent left alignment; icons/avatars always same size
- Keyboard navigable: arrow keys move selection
- "Load more" button preferred over infinite scroll for SEO content

### Carousel
- Always show navigation arrows and dot indicators
- Never auto-advance (user must control)
- Show partial next card to signal scrollability
- Touch/swipe on mobile; arrow keys for accessibility
- Avoid for more than 7 items — use a grid instead

### Pagination
- Show: first, prev, [pages], next, last
- Current page: clearly highlighted (not just bold)
- On mobile: "< Previous | Next >" text only
- Show total: "Showing 1–10 of 142 results"
- Jump-to-page input for large datasets (>20 pages)

### Rating
- Always use half-star precision; never decimal
- Read-only vs interactive states must be visually distinct
- Include text label: "4.5 out of 5" for screen readers
- Show count alongside: "4.5 (2,341 reviews)"

### Tree View
- Indent level: 16–20px per level
- Expand/collapse toggle: chevron icon, not +/–
- Keyboard: left/right arrows to expand/collapse, up/down to navigate
- Max 3–4 levels deep before redesigning the hierarchy

---

## Forms & Input

### Button
- Label: verb-first ("Save changes", "Delete project", not "OK")
- Hierarchy: Primary (filled) > Secondary (outlined) > Ghost (text-only)
- One primary button per section; multiple secondary/ghost allowed
- Loading state: spinner inside button, disabled, same size
- Destructive actions: red; always confirm before executing
- Min touch target: 44×44px

### Button Group
- Related actions; separated by divider not gap
- Only works if all actions are equally important
- Max 3–4 buttons; use dropdown for more

### Text Input
- Label always above input — never inside as placeholder-only
- Placeholder: example value, not the label
- Error state: red border + error message below (not tooltip)
- Success state: green checkmark icon inside input
- Character count: bottom-right when there's a limit

### Textarea
- Same rules as text input
- Show resize handle; min-height 80px
- Character limit visible at all times with countdown
- Auto-grow variant: expands with content up to max-height

### Checkbox
- Group label above the group; individual labels to the right of checkbox
- Indeterminate state for "select all" with partial selection
- Never use for mutually exclusive options — use radio buttons
- Min 16×16px touch area; prefer 20×20px

### Radio Button
- Always in a group of 2+; single choice
- Group label above; options stacked vertically (max 5) or horizontally (max 3)
- If >5 options, use Select dropdown instead

### Select / Dropdown
- Single select: native `<select>` or custom with search for >7 options
- Multi-select: use Combobox or tag input
- Always show currently selected value in the trigger
- Placeholder: "Select an option" not "---"

### Combobox
- Combines text input + dropdown — for searchable selects
- Debounce search: 200–300ms
- Keyboard: type to filter, arrow keys to navigate, Enter to select
- Shows matched terms highlighted in dropdown options

### Date Input / Datepicker
- Date input: `YYYY-MM-DD` format internally; localized display
- Datepicker: calendar overlay; show month/year navigation
- Range picker: highlight range on hover before selection
- Mobile: use native `<input type="date">` — don't reinvent the wheel

### Search Input
- Magnifying glass icon on left; clear (×) on right when has value
- Keyboard shortcut: Cmd+K or Ctrl+K to focus
- Debounce: 200–300ms before firing search
- Show result count or "No results" in real-time

### Slider
- Show current value alongside slider (tooltip or label)
- Min/max labels on ends
- Range slider: two handles; filled track between them
- Touch target: 44px height even if track is thinner

### Color Picker
- Show hex input + color swatch
- Include preset swatches for brand colors
- Eyedropper tool on supported browsers
- Alpha channel slider if transparency needed

### File Upload
- Drag and drop zone + click to browse button
- Show file type and size restrictions
- Upload progress: bar with percentage
- Preview thumbnails for images
- Error state: list invalid files with reason

### Rich Text Editor
- Toolbar: bold, italic, underline, link, list, heading (H2/H3 only)
- Keyboard shortcuts: Cmd+B, Cmd+I, Cmd+K
- Paste from Word: strip invisible formatting
- Mobile: simplified toolbar (floating or bottom sheet)

---

## Overlay & Contextual

### Modal
- Use for: confirmations, short forms, focused actions
- Don't use for: complex flows, multiple steps, large content
- Always: title + content + action buttons (primary right, cancel left/ghost)
- Close: X button, Escape key, backdrop click (optional)
- Trap focus inside modal while open
- Sizes: sm (400px), md (600px), lg (800px)

### Drawer / Panel
- Right drawer: contextual detail, editor, settings
- Left drawer: navigation (mobile)
- Width: 320–480px on desktop; full-width on mobile
- Backdrop: semi-transparent overlay; click to close
- Never use for primary navigation on desktop

### Popover
- Triggered by click (not hover) for interactive content
- Contains: rich content (forms, menus, previews)
- Dismiss: click outside or Escape
- Placement: auto-flip to stay in viewport
- Max width: 320px

### Tooltip
- Hover + focus trigger; never click
- Text only — no interactive elements (use Popover for those)
- Delay: 700ms on show; instant on hide
- Placement: auto based on viewport position
- Max width: 200px; 1–2 lines max

### Dropdown Menu
- 7±2 items; group related actions with dividers
- Destructive actions: last in list, red text
- Icons: optional but must be consistent across all items or none
- Keyboard: arrow keys to navigate, Enter to select, Escape to close

---

## Navigation Patterns

### Tabs
- 2–7 tabs max; use accordion if more
- Active indicator: bottom border (horizontal) or left border (vertical)
- Tabs don't scroll on desktop (if overflow, use dropdown "more")
- Mobile: horizontal scroll or convert to accordion/select
- Content: immediately visible on tab switch (no loading if avoidable)

### Accordion
- Use for: FAQs, long content, settings sections
- One open at a time (exclusive) OR multiple (non-exclusive) — pick one per context
- Chevron icon: right-aligned, rotates 180° when open
- Animation: 200–300ms height transition

### Breadcrumbs
- Show location hierarchy: Home > Category > Current Page
- Current page: not a link (or aria-current="page")
- Truncate middle items on mobile with "..."
- Max 4 levels before rethinking the IA

### Segmented Control
- 2–5 options; all mutually exclusive
- Equal-width segments for 2–3 options
- Use instead of tabs when switching view mode (not navigation)
- Mobile: full-width

### Pagination
*(see Data Display → Pagination)*

### Skip Link
- First element in DOM: "Skip to main content"
- Visible only on keyboard focus
- Links to `<main>` landmark
- Required for accessibility compliance (WCAG 2.1 AA)

---

## Media & Content

### Avatar
- Circle for people; rounded square for organizations/brands
- Fallback: initials (first + last name initial) with generated background color
- Sizes: xs(16) sm(24) md(32) lg(40) xl(48) 2xl(64)
- Group avatars: overlap with border, +N for overflow

### Image
- Always define width/height to prevent layout shift (CLS)
- Use `loading="lazy"` for below-fold images
- Provide `alt` text — descriptive for informative, `alt=""` for decorative
- Aspect ratio containers: 16:9 (landscape), 1:1 (square), 4:3 (wide)

### Icon
- Use a single icon library consistently (Lucide, Heroicons, Phosphor)
- Never mix icon libraries in one product
- Min size: 16px; touch target: 44px
- Label alongside icon for primary actions; tooltip for icon-only buttons

### Video
- Autoplay only if muted + not fullscreen
- Always include pause control
- Captions: required for accessibility
- Poster frame: show frame from video, not a blank black screen

### Quote / Blockquote
- Left border accent; indented; italic style optional
- Attribution below: "— Name, Role" in smaller text
- Use for testimonials, callouts, pull quotes

---

## Accessibility Essentials (apply to all components)

| Rule | Implementation |
|---|---|
| Color contrast | 4.5:1 for text, 3:1 for UI elements |
| Focus visible | Never `outline: none` without custom focus style |
| Keyboard navigable | Tab order logical; all interactive elements reachable |
| Screen reader labels | `aria-label` for icon-only buttons; `aria-describedby` for error messages |
| Motion safe | Respect `prefers-reduced-motion` for all animations |
| Touch targets | Minimum 44×44px for all interactive elements |

---

## Vocabulary Quick Reference

These are the exact terms used in real design systems. Use them when describing or requesting components:

`accordion` `alert` `avatar` `avatar-group` `badge` `breadcrumbs` `button` `button-group` `card` `carousel` `checkbox` `chip` `color-picker` `combobox` `data-table` `datepicker` `date-input` `dialog` `drawer` `dropdown-menu` `empty-state` `fieldset` `file-upload` `footer` `form` `header` `heading` `hero` `icon` `image` `label` `link` `list` `modal` `navigation` `pagination` `popover` `progress-bar` `progress-indicator` `quote` `radio-button` `rating` `rich-text-editor` `search-input` `segmented-control` `select` `separator` `sidebar` `skeleton` `skeleton-shimmer` `skip-link` `slider` `spinner` `stack` `stepper` `table` `tabs` `text-input` `textarea` `toast` `toggle` `tooltip` `tree-view` `video` `visually-hidden`

Source: [component.gallery](https://component.gallery) — 60 components, 95 design systems, 2,676 examples
