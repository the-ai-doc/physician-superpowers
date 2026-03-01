# 🩺 Physician Superpowers
### Custom skills for [Google Anti-Gravity](https://antigravity.google) — built by a physician, for physicians who build.

> **What is Google Anti-Gravity?** It's an AI-powered coding agent built by Google DeepMind. You talk to it, it writes code, fixes bugs, builds apps, runs commands — all from inside your editor. Skills are packages of instructions that teach Anti-Gravity how to do specific things on command. This repo is a library of skills built specifically for physician entrepreneurs.

---

## How This Works

1. You have **Google Anti-Gravity** installed in your editor
2. You clone this repo and copy the `skills/` folder to `~/.gemini/skills/`
3. From that point on, you just *say* what you want — in plain English — and Anti-Gravity knows how to do it

**Example:** You say *"let's build — I want a tool where patients can book time with me online"*. Anti-Gravity reads the `lets-build` skill, scaffolds a Next.js app, builds the booking UI, and shows you a screenshot — all in one shot.

> **Also works with Claude Code** — every `SKILL.md` in this repo is cross-compatible with Claude Code (`~/.claude/skills/`) and GitHub Copilot (`~/.copilot/skills/`).

---

## Who This Is For

| Role | What you'll find here |
|---|---|
| 🛠️ **Physician builder** | Skills to ship faster — idea to deployed app without planning paralysis |
| 📱 **Physician content creator** | AI content engines to grow your brand without burning more time |
| 🏢 **Physician executive** (CMO, CIO, CEO) | Decision support, briefs, and reporting at speed |
| 🏥 **Practice owner** | Tools to run the business side smarter |

---

## Quick Install

```bash
# 1. Clone this repo
git clone https://github.com/the-ai-doc/physician-superpowers.git

# 2. Copy all skills globally (works in every project after this)
cp -r physician-superpowers/skills/* ~/.gemini/skills/

# 3. Open Anti-Gravity and just start talking
# "let's build", "save my place", "humanize this" — it all works now
```

---

## Full Skills Library

### 🛠️ Builder Skills (for shipping faster)
| Say this | Skill | What happens |
|---|---|---|
| *"let's build — [idea]"* | `lets-build` | Idea → working app, no planning paralysis |
| *"make this real — [voice note]"* | `make-this-real` | Rambling thought → structured spec → code |
| *"show me"* | `show-me` | Screenshots your running app live in the conversation |
| *"build this UI"* + screenshot | `visual-builder` | Any screenshot → working React component |
| *"map this project"* | `map-this-project` | Full map of your codebase — stack, routes, data flow, status |
| *"figure out what's broken"* | `figure-out-whats-broken` | Auto-triage errors; always produces a fix or a clear decision |
| *"am I ready to ship"* | `am-i-ready-to-ship` | Pre-deploy checklist — blocking issues, warnings, verdict |
| *"turbo mode"* | `turbo-mode` | Skips approval prompts for safe ops — stay in flow state |
| *"vibe to ship"* | `vibe-to-ship` | Coding session → commit message + PR description + changelog |
| *"save my place"* | `save-my-place` | Saves your exact context for ADHD-friendly switching |
| *"where was I"* | `save-my-place` | Resumes exactly where you left off |

### 📱 Content Creator Skills
| Say this | Skill | What happens |
|---|---|---|
| *"content engine"* + source | `content-engine` | One input → LinkedIn + Twitter thread + IG carousel + newsletter via Blotato |
| *"humanize this"* + text | `humanizer` | Strips AI writing patterns so your content reads like you, not a chatbot |

### 🏢 Executive Skills
| Say this | Skill | What happens |
|---|---|---|
| *"executive brief on [topic]"* | `executive-brief` | Sourced, decision-ready summary in under 5 minutes |
| *"grand rounds"* | `grand-rounds` | Weekly: what got used, what broke, what users want, what to build next |

### 🔬 Research & Analysis Skills
| Say this | Skill | What happens |
|---|---|---|
| *"analyze website [url]"* | `analyze-website` | 11-phase forensic audit — tech stack, security penetration, SEO + Gemini rebuild prompt |

---

## The Philosophy

Physician burnout is real. A significant part of it comes from feeling like you have no control — over your schedule, your practice, your voice.

These skills are about **reclaiming leverage**. If you can think it, you can build it. Google Anti-Gravity makes that possible. This repo makes it fast.

---

## Contributing

Physician builders are encouraged to contribute. Open a PR with:
- A new skill folder with a `SKILL.md`
- A real scenario that triggered you to build it
- Your specialty (so others can find tools built by people who understand their context)

---

## Built by

**The AI Doc** — [@the-ai-doc](https://github.com/the-ai-doc)

A physician building at the intersection of medicine and AI. Focused on reducing physician burnout through automation, not more meetings.

---

*This repo evolves. Last updated: March 2026.*
