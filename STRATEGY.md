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

## 🎩 WHITE HAT — Facts & Data
*What do we know? What's trending right now?*

### Top AI Trends (Feb 2026) relevant to physician builders:

**Claude Code (Anthropic)**
- Agentic CLI that runs in terminal — can fix bugs in large codebases autonomously
- New "agent teams" feature: multiple Claude agents collaborate on a task
- "Adaptive thinking" + "effort controls" — can do deep work autonomously
- **Physician superpower opportunity:** A `run-claude-code` skill that wires Claude Code into Anti-Gravity for complex refactoring tasks Anti-Gravity should delegate

**Google Anti-Gravity + AI Studio Integration**
- Anti-Gravity now integrates with AI Studio for prototyping → agent development pipeline
- Can swap models (Gemini, Claude, GPT) per task
- **Physician superpower opportunity:** A `switch-brain` skill — automatically selects the best model for the task type (Gemini for code, Claude for writing, GPT-4o for vision)

**OpenAI Codex CLI**
- Cross-platform local coding agent
- Available to GitHub Copilot users
- **Physician superpower opportunity:** A `codex-review` skill that runs Codex CLI as a final code review before shipping

**Multi-Agent Systems (trending hard)**
- The concept of "agent teams" — multiple AI agents with different specialties working together
- **Physician superpower opportunity:** A `my-team` skill — doctor describes a problem, it spins up a team: researcher agent, coder agent, reviewer agent, each doing their part

**Blotato (Content Engine)**
- Takes one piece of content (video, article, podcast) and repurposes it to every platform
- Generates AI visuals and audio
- Schedules posts for optimal timing
- **Physician superpower:** `content-engine` skill — paste a lecture or article, Blotato distributes to LinkedIn + IG + Twitter + newsletter in minutes

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
