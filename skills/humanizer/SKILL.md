---
name: humanizer
description: Strip AI writing patterns from any content so it reads like a real person wrote it — not a chatbot
---

# Humanizer Skill

AI-generated content has tells. Certain phrases, sentence rhythms, and structures that immediately signal "a robot wrote this." For a physician with a public voice, that's a credibility problem.

This skill rewrites any AI-generated text to sound like *you* — confident, direct, human.

---

## Usage

Say: **"humanize this"** then paste the text.

Or inline:
- *"humanize this LinkedIn post"*
- *"humanize this — make it sound more like how I actually talk"*
- *"humanize this email draft"*

---

## AI Writing Patterns to Remove

The skill hunts for and eliminates these:

**Filler phrases:**
- "In today's fast-paced world..."
- "It's important to note that..."
- "Crucially," / "Importantly,"
- "In conclusion," / "To summarize,"
- "It goes without saying..."
- "Needless to say..."

**Robot vocabulary:**
- "Delve into" → cut or replace with "look at"
- "Leverage" → "use"
- "Utilize" → "use"
- "Facilitate" → "help" or "make easier"
- "Endeavor" → "try"
- "Robust" → be specific about what's being described
- "Comprehensive" → what does it actually cover?

**Structural tells:**
- Excessive em-dashes mid-sentence
- Lists of three things that all start with the same word
- Sentences that begin with "As a [job title]..."
- Overly balanced "on one hand... on the other hand" structures
- Ending with a question to engage the reader

**Tone corrections:**
- Remove corporate hedging ("may potentially", "could possibly")
- Remove excessive enthusiasm ("Exciting news!", "I'm thrilled to share")
- Add opinions where the AI was neutral ("This worked well" → "This worked better than expected, mostly because...")
- Shorten long sentences. Physicians speak in short, clear sentences.

---

## Instructions for the Agent

When triggered:

1. Read the provided text carefully.
2. Identify and list which AI patterns are present.
3. Rewrite the text, preserving:
   - The core information and structure
   - The user's known vocabulary and style (if you've seen their writing before, match it)
   - Any specific examples or stories they included
4. Make it shorter if possible — AI tends to over-explain.
5. Output the humanized version, then briefly note what was changed.
6. Ask: *"Does this sound more like you? I can adjust the tone — more casual, more direct, more authoritative."*

---

## Tags
`[creator]` `[physician-entrepreneur]`

## Last tested: March 2026
