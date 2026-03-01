---
name: executive-brief
description: Get a fast, sourced, decision-ready summary on any topic — built for physician executives who need full context in 5 minutes
---

# Executive Brief Skill

You have a board meeting in an hour. Someone just sent you a 40-page report. A new regulation just dropped. You need to understand something fast — and well enough to make a decision or lead a conversation about it.

This skill produces a structured brief on any topic: healthcare policy, AI tool, clinical research, business strategy, market landscape — whatever you need to walk in informed.

---

## Usage

Say: **"executive brief on [topic]"**

Examples:
- *"executive brief on CMS reimbursement changes for telehealth 2026"*
- *"executive brief on Cursor vs Anti-Gravity for a physician dev team"*
- *"executive brief on starting a 501c3 for physician wellness programs"*
- *"executive brief on the competitive landscape for AI scribes in 2026"*

---

## What It Produces

```
EXECUTIVE BRIEF: [Topic]
Generated: [Date/Time]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

THE 30-SECOND VERSION
[2–3 sentences. What this is, why it matters, what decision it affects.]

KEY FACTS
• [Fact 1 — specific, sourced]
• [Fact 2 — specific, sourced]
• [Fact 3 — specific, sourced]
• [Fact 4 — specific, sourced]
• [Fact 5 — specific, sourced]

WHAT'S CHANGING
[What's new, different, or in motion about this topic right now]

THE MAIN DEBATE
[If there are competing views, what are the positions and who holds them]

WHAT IT MEANS FOR YOU
[Practical implications for a physician executive — what decisions this affects,
what opportunities or risks it creates]

WHAT TO WATCH
[The 2–3 things to monitor as this evolves]

SOURCES
• [Source 1]
• [Source 2]
• [Source 3]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
CONFIDENCE: [High / Medium / Low] — [brief note on data quality]
```

---

## Instructions for the Agent

When triggered:

1. Use `search_web` to research the topic — prioritize authoritative, recent sources
2. Look for: news articles, official documents, academic sources, expert commentary
3. Synthesize — don't just summarize. Pull out what actually matters for a busy executive.
4. Flag if the topic is rapidly changing and the brief may be out of date quickly
5. If the topic is unclear, ask one clarifying question: *"Any specific angle — regulatory, competitive, financial, technical?"*

---

## Tags
`[executive]` `[practice-owner]`

## Last tested: March 2026
