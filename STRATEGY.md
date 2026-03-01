# Physician Superpowers — Six Hats Strategy Session
## What to build next, and why

This document applies Edward de Bono's Six Thinking Hats to the physician-superpowers skill library, identifying gaps, risks, and opportunities. It also incorporates research from top AI YouTube/Twitter creators as of February 2026 and the physician archetype framework.

---

## THE THREE PHYSICIAN ARCHETYPES

Before the hats — here are the three physician builder personas driving skill design:

### 🏥 The Practice Owner
*Solo or small group practice. Wears clinical hat AND business hat.*
- Needs: Patient communication at scale, online reputation, scheduling automation, billing/revenue analytics
- Time available: 30–60 min/week for building
- Pain: No marketing team, no ops team — just them

### 📱 The Physician Content Creator
*Built a following on social media. Teaches medicine, promotes wellness, has a brand.*
- Needs: High-volume content without high-volume time, repurposing long-form to short-form, brand consistency
- Time available: 2–3 hrs/week for content
- Pain: Content is a second job on top of the actual job
- **Tools relevant:** Blotato (AI content engine — take one piece of content + blast it to every platform), Opus Clip, Descript

### 🏢 The Physician Executive
*CMO, CIO, Medical Director, startup founder/CEO in healthcare.*
- Needs: Executive summaries, stakeholder communication, literature review, board decks, strategic analysis
- Time available: Sporadic; decision-making at speed
- Pain: Information overload; everything needs a decision

---

## 🎩 WHITE HAT — Real Research: What Creators Are Actually Doing
*Sourced from live browser research on YouTube channels and Twitter/X accounts, March 2026*

---

### YouTube — What Top Channels Published This Week

**Matt Wolfe (@mreflow)**
- *"20+ NotebookLM Tricks to 3X Productivity"* — Specific technique: **Source Synthesis** feature auto-generates strategy docs from raw notes → **Physician superpower: auto-generate clinical protocols from research dumps**
- *"The AI Tools You'll ACTUALLY Use Every Day"* — Featured **Blotato** for marketing automation and **Testsprite** for rapid app testing → confirms Blotato as legitimate physician creator tool
- *"AI News: AI's Biggest Stand Just Happened"* — Covered Google Nano Banana 2 for real-time local data processing without API costs → **relevant for HIPAA: run models locally, no data leaves the machine**

**Fireship**
- *"The wild rise of OpenClaw..."* — Covered shift from traditional IDEs to fully agentic terminals like **OpenClaw** and **Claude Code** — confirms Claude Code + Anti-Gravity hybrid is the trending workflow
- *"10 open source tools that feel illegal"* — Included **Anti-Gravity Pre-hooks** for automating repetitive git workflows → **new skill category: pre-hooks for automating context before any agent task runs**

**Theo (@t3dotgg)**
- *"Delete your CLAUDE.md (and your AGENT.md too)"* — Key insight: static config files are being replaced by dynamic **Skill Injection** via CLI — confirms SKILL.md is the right long-term approach
- *"Gemini 3.1 Pro is the smartest model ever made"* — Shows 2M+ token context handling for analyzing entire codebases → **can now ingest an entire medical practice's data in one context window**
- *"My new app is really stupid (I wrote none of the code)"* — 100% AI-generated codebase using Claude Code with zero manual coding

**David Ondrej (@DavidOndrej)**
- *"Gemini 3.1 Pro in Antigravity can do anything"* — Demonstrates **Universal Task Runner** skill: verbal idea → mapped directly to agent workflow → **this is essentially the `let's build` skill we planned**
- *"AgentZero just released the OpenClaw killer"* — Hierarchical multi-agent teams with specialized roles → **physician team of agents: clinical researcher + coder + HIPAA reviewer + content creator**

**Greg Isenberg (@GregIsenberg)**
- *"How I Use Obsidian + Claude Code to Run My Life"* — Uses personal knowledge base as a context skill for automating email, scheduling, content → **physician version: clinical knowledge base feeds every agent task automatically**
- *"Claude Code Built My $450K Marketing Campaign"* — Uses **Blotato + Claude Code** for multi-channel campaigns for busy executives → **exact physician entrepreneur use case confirmed at scale**

---

### Twitter/X — Specific Techniques With Engagement Data

| # | Creator | What They Shared | Engagement | Physician Superpower Derived |
|---|---|---|---|---|
| 1 | **@levelsio** (Pieter Levels) | Shell alias to bypass Claude Code permissions: `c() { IS_SANDBOX=1 claude --dangerously-skip-permissions "$@"; }` | **3,800+ likes** | **`turbo-mode`** skill — skips approval prompts for known-safe operations (saves minutes/session) |
| 2 | **@mattshumer_** | **Agent Relay SDK** — headless Slack layer so AI agents communicate via channels, threads, DMs to coordinate long-term goals | 536 likes | **`agent-team`** skill — physician agents coordinate: researcher finds evidence, coder builds feature, reviewer checks HIPAA |
| 3 | **@danshipper** | **Claw-to-Claw Collaboration** — multiple agents live-edit a document simultaneously, like multiplayer agentic writing | 170+ likes | **`agentic-coauthor`** skill — multiple agents refine a grant proposal or whitepaper simultaneously |
| 4 | **@KimYx0207** | **"De-AI Smell" skill** — strips typical AI writing hallmarks ("crucially important", "in addition", "delve") from generated content | Viral technique | **`humanizer`** — post-processing skill so physician content doesn't read like a robot wrote it |
| 5 | **@buildyrs** | **Chronicle Vibe Skill** — auto-documents a coding session, bridges "vibe coding" and shipped code | Growing | **`vibe-to-ship`** — auto-generates PR description and changelog from your coding session |
| 6 | **Trending (OpenClaw)** | **OpenClaw** — open-source agent runner, rises as alternative to proprietary environments | Rapid rise | **`local-runner`** — run agents on open-source models (Llama 4) locally; no data sent to external APIs = HIPAA-safer |
| 7 | **@shivasek5** | **Design-to-Code Pipeline** — Figma "Make" + Claude Code turns screenshots into functional React components instantly | 40+ views | **`visual-builder`** — physician points at a screenshot of any UI, Anti-Gravity builds it |
| 8 | **Trending** | **SKILL.md Standardization** — packaging every automation as a standalone SKILL.md file, now portable across Claude Code, Anti-Gravity, and GitHub Copilot | Industry standard | **Confirms our entire approach** — SKILL.md is cross-platform and future-proof |
| 9 | **@wei_daisy** | **"Enoughness" framework** — knowing when MVP is done; prevents over-engineering | Viral insight | **`mvp-guardian`** — prevents agent from gold-plating when you need to ship |
| 10 | **@steadeepanda** | **Agent Ruler (Sandbox)** — local deterministic monitor that ensures agents stay confined to safe local environment | Beta | **`local-safe`** — privacy-first skill for handling sensitive medical data locally, zero external API leaks |

---

### SKILL.md Is Now Cross-Platform
Confirmed by research: a `SKILL.md` file works identically across:
- **Google Anti-Gravity** (`~/.gemini/skills/`)
- **Claude Code** (`~/.claude/skills/`)
- **GitHub Copilot** (`~/.copilot/skills/`)

This means every skill built in this repo works for ANY physician regardless of which AI agent they use.

---

## 🎩 RED HAT — Emotions & Instincts
*What feels right? What would excite the community?*

- **The "save my place" skill** feels deeply personal and ADHD-aligned. It will resonate immediately with any physician who has lost their train of thought switching between a patient and their laptop.
- **The content engine** feels like a liberation. The physician content creator grind is real — filming, editing, captioning, scheduling is a second job. Automating it feels genuinely life-changing.
- **The executive brief skill** feels powerful for the physician leader who gets 200 emails a day and needs to make a decision in 10 minutes with full context.
- **Risk feeling:** The repo could feel like "yet another dev resource" if it doesn't lead with the physician story front and center. The README must earn the trust.

---

## 🎩 BLACK HAT — Critical Risks
*What could go wrong?*

- **HIPAA risk**: Any skill that touches patient data must have explicit warnings. The `patient-comms` skill especially — can't store, log, or pass PHI to external LLMs without proper BAA (Business Associate Agreement).
- **Skills becoming stale**: AI moves fast. A skill written for Claude today may break in 6 months if the API changes. Need a `last-tested` date in every SKILL.md.
- **Generalization risk**: "Physician" is not one persona. A dermatologist's needs ≠ an ICU intensivist's needs ≠ a radiologist's needs. Skills need to be persona-tagged.
- **Adoption friction**: Doctors aren't developers. Install instructions must be truly one-command.
- **Scope creep**: This repo could become 500 skills that do nothing well. Better to have 10 skills that are incredible.

---

## 🎩 YELLOW HAT — Optimism & Opportunities
*What's the best case?*

- This repo becomes the go-to resource mentioned in every "doctors who code" Twitter thread.
- Physician builders from other specialties (surgery, psychiatry, EM) contribute their own skills — a self-growing library.
- The `the-ai-doc` GitHub org becomes a recognized brand in the physician entrepreneur community.
- Skills from this repo get adopted by the broader vibe coding community as high-quality examples.
- A Skool community, YouTube channel, or newsletter forms around this — passive influence and income for the physician creator.
- One or two skills get shared by AI influencers (Theo, Fireship, Matt Wolfe, etc.) and go viral.

---

## 🎩 GREEN HAT — Creative Ideas
*What new ideas does this spark?*

### Skills not yet built that would be high-impact:

1. **`dictate-a-feature`** — Physician dictates a feature into their phone (like they dictate clinical notes). Skill transcribes, structures it as a spec, and builds it. Meets doctors where they already are.

2. **`literature-to-product`** — Paste a PubMed abstract or clinical guideline. Skill extracts the key finding, then generates either: (a) a patient handout, (b) a pitch deck insight, or (c) a feature idea for a health tech product.

3. **`compliance-check`** — Before shipping any patient-facing feature, run this skill. It checks against common HIPAA/regulatory patterns and flags risks.

4. **`peer-review-my-code`** — Mirrors the peer review process physicians know well. Another "perspective" reviews your code like a colleague would — catches logic errors, edge cases, and documentation gaps.

5. **`on-call-coder`** — Like being on call, this skill monitors your running app overnight (logs, errors, uptime) and sends you a morning brief on what happened.

6. **`grand-rounds`** — A weekly automated analysis: what features got used, what broke, what users asked about. Presented like morning report.

7. **`switch-brain`** — Automatically routes a task to the best model: Gemini for code, Claude for long-form writing, GPT-4o for image analysis. The physician doesn't have to think about which AI to use.

---

## 🎩 BLUE HAT — Process & Next Steps
*What's the plan?*

### Immediate priorities (build now):
1. `show-me` — solves the #1 stated friction point
2. `map-this-project` — high value for orientation at any time
3. `content-engine` (Blotato) — high value for physician content creator persona
4. `save-my-place` / `where-was-i` — ADHD superpower

### Next wave (build over next 30 days):
5. `dictate-a-feature`
6. `compliance-check`
7. `executive-brief`
8. `literature-to-product`

### Community building:
- Publish repo with strong README
- Post on X/Twitter with screen recording of `show-me` in action
- Share in Skool communities
- Open GitHub Discussions for community Q&A

### Repo governance:
- Every skill must have: name, description, trigger phrase, example scenario, `last-tested` date
- Tag each skill with persona: `[builder]` `[creator]` `[executive]` `[practice-owner]`
- Deprecate skills that break — don't let the repo rot

---

## TOP AI CONTENT CREATORS TO WATCH
*(Sources for skill inspiration)*

**YouTube:**
- Matt Wolfe (@mreflow) — AI tool reviews, workflow automation
- Fireship — fast-paced coding + AI
- Theo (t3.gg) — opinionated dev takes, Next.js ecosystem
- Andrej Karpathy — deep technical AI
- David Ondrej — AI agents and automation
- Greg Isenberg — startup + AI intersection
- Riley Brown — vibe coding tutorials

**Twitter/X:**
- @levelsio (Pieter Levels) — solo builder philosophy
- @mckaywrigley — LLM integration patterns
- @swyx — AI engineering trends
- @venturetwins — consumer AI apps
- @danshipper — writing + AI workflows
- @MattWolfe — AI tool releases

---

*This is a living document. Updated as the skill library grows.*
