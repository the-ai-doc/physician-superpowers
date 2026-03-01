---
name: grand-rounds
description: Weekly report on your app — what got used, what broke, what users want, what to build next. Like morning report, but for your product.
---

# Grand Rounds Skill

Every attending knows morning report. You walk in, get a structured briefing on what happened while you were gone, and leave knowing what needs to be addressed.

This skill is morning report for your app. Once a week, it analyses your logs, errors, usage patterns, and user feedback — and gives you a structured briefing so you know what's actually happening in your product.

---

## Usage

Say: **"grand rounds"**

Or schedule it by saying: *"run grand rounds every Monday morning"*

---

## What It Covers

```
GRAND ROUNDS — [App Name]
Week of [date range]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

VITAL SIGNS
• Users this week: [#] ([+/-]% vs last week)
• Active sessions: [#]
• Uptime: [%]
• Errors logged: [#]

TOP ACTIVITY (what got used most)
1. [Feature/page] — [# times used]
2. [Feature/page] — [# times used]
3. [Feature/page] — [# times used]

PROBLEMS (what broke or frustrated users)
• [Error/issue] — [# occurrences] — [severity]
• [Error/issue] — [# occurrences] — [severity]

USER SIGNALS (what they're asking for)
• [Feedback/request] — [source]
• [Feedback/request] — [source]

DEAD ZONES (what nobody used)
• [Feature/page nobody touched]
→ Remove it? Fix it? Depends on why.

ASSESSMENT
[2–3 sentences on the overall health of the product this week]

PLAN
1. [Highest priority fix or build]
2. [Second priority]
3. [Third priority]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Instructions for the Agent

When triggered:

**STEP 1 — Gather data:**
Depending on what's connected, pull from:
- **Vercel Analytics** — page views, visitors, geographic data
- **PostHog** — events, funnels, user recordings
- **Sentry / error logs** — what broke and how often
- **Supabase logs** — database query patterns
- **GitHub Issues** — open bug reports
- **User emails/DMs** — qualitative feedback (ask user to paste if not logged)

**STEP 2 — If nothing is instrumented:**
Note which analytics tools aren't set up yet and offer to add them. Run `git log --oneline --since="1 week ago"` to at least show what was shipped this week.

**STEP 3 — Write the brief:**
Use the format above. Be specific — no vague summaries. If you don't have data for a section, say so clearly and explain what would give you that data.

**STEP 4 — Prioritize the plan:**
Based on the data, make a direct recommendation on what to do first. Don't hedge — pick one thing.

---

## Tags
`[builder]` `[physician-entrepreneur]`

## Last tested: March 2026
