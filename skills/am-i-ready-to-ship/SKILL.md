---
name: am-i-ready-to-ship
description: Pre-deploy confidence check — runs through every critical gate before you push to production so nothing breaks for real users
---

# Am I Ready to Ship Skill

The feeling before deploying: did I forget something? This skill runs a systematic pre-deploy checklist so you ship with confidence, not anxiety.

It checks everything a tired developer forgets — env vars, console errors, security headers, type errors, SEO basics — and tells you exactly what's blocking vs. what's just a warning.

---

## Usage

Say: **"am I ready to ship"**

Or:
- *"am I ready to ship this to production"*
- *"am I ready to ship — check everything"*

---

## The Checklist

### 🔴 BLOCKING (do not ship until fixed)
- [ ] Build passes with zero errors (`npm run build`)
- [ ] No TypeScript errors (`npm run type-check`)  
- [ ] No unresolved `console.error` in browser on main user flows
- [ ] All required environment variables set in production (Vercel / hosting platform)
- [ ] Auth flow works end-to-end (sign up, log in, log out)
- [ ] No broken API routes (test each one)
- [ ] Database connections work in production environment

### 🟡 WARNINGS (ship but fix soon)
- [ ] `robots.txt` exists
- [ ] `sitemap.xml` exists
- [ ] Meta title and description on every page
- [ ] No `console.log` statements left in production code
- [ ] HTTPS configured (usually automatic on Vercel/Netlify)
- [ ] Error handling exists for API failures (no raw 500s shown to users)
- [ ] Loading states exist for async operations

### 🟢 NICE TO HAVE (future improvement)
- [ ] Security headers configured (CSP, X-Frame-Options, etc.)
- [ ] Lighthouse performance score > 80
- [ ] Images optimized / using next/image
- [ ] Privacy policy page exists
- [ ] Analytics connected (PostHog, Vercel Analytics)

---

## Instructions for the Agent

When triggered:

**STEP 1 — Run build check:**
```bash
npm run build 2>&1 | tail -30
```

**STEP 2 — Run type check:**
```bash
npm run type-check 2>&1 || npx tsc --noEmit 2>&1
```

**STEP 3 — Check env vars:**
Read `.env.example` (or `.env.local`) and compare with what's set in the hosting platform.
If no access to hosting platform, list what should be verified manually.

**STEP 4 — Quick browser audit:**
Use `show-me` skill to load the app. Check for:
- Console errors
- Visual regressions on main pages
- Auth flow (if testable)

**STEP 5 — Check SEO basics:**
```bash
# Check if these files exist
ls public/robots.txt public/sitemap.xml 2>&1
```
Read `<head>` of key pages for title/meta description.

**STEP 6 — Produce the report:**

```
SHIP CHECK — [App Name]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

🔴 BLOCKING ISSUES: [# found]
  • [Issue] — [what to do]
  
🟡 WARNINGS: [# found]
  • [Issue] — [priority]

🟢 STATUS: [READY TO SHIP / NOT READY]

VERDICT: [1-sentence summary]
```

**STEP 7 — Offer to fix:**
For each blocking issue: *"Want me to fix [issue] now?"*

---

## Tags
`[builder]` `[all-personas]`

## Last tested: March 2026
