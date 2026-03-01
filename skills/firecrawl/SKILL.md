---
name: firecrawl
description: Give Anti-Gravity eyes on the entire internet — scrape any webpage, crawl full sites, extract structured data, run autonomous web research, and control real browser sessions. Powered by Firecrawl MCP.
---

# Firecrawl Skill

Firecrawl gives Anti-Gravity the ability to read the live internet — not just what it was trained on. It can scrape any page, crawl entire websites, extract structured data, run autonomous research agents, and control real browsers.

---

## When to Use This Skill

Activate whenever the user wants to:
- Read a specific webpage or pull content from a URL
- Extract structured data from a site (prices, features, names, contacts)
- Map all URLs on a website
- Crawl an entire site across all its pages
- Research a topic by searching across the live web
- Automate a browser to interact with a site (login, click, fill forms)
- Monitor competitor sites for changes
- Batch process many URLs at once
- Anything that requires real-time information from the internet

---

## Tool Selection Guide

Use this to pick the right Firecrawl tool for the job:

| Situation | Use |
|---|---|
| I know the URL and want the content | `firecrawl_scrape` |
| I want specific data fields only (prices, names, etc.) | `firecrawl_scrape` with JSON schema |
| I need to read 3+ pages I know the URLs for | `firecrawl_batch_scrape` |
| I don't know the URLs on a site — I want to discover them | `firecrawl_map` |
| I want to read every page on a site | `firecrawl_crawl` |
| I want to search the live web for something | `firecrawl_search` |
| I want to pull specific data from many pages at once | `firecrawl_extract` |
| I have a complex open-ended research task | `firecrawl_agent` |
| I need to interact with a site (login, click, fill forms) | `firecrawl_browser_*` |

---

## How to Use Each Tool (What You'd Actually Say)

### 📄 Scrape a Single Page
**When:** You know exactly which page has what you want.

> *"Scrape the pricing page at stripe.com/pricing and tell me every plan and what it costs"*

> *"Read this article and summarize it: [url]"*

> *"Get the brand colors, fonts, and design tokens from apple.com"*

The branding mode is especially powerful — it reverse-engineers a site's entire visual identity.

---

### 📚 Batch Scrape (Many URLs at Once)
**When:** You have a list of URLs and want them all read in parallel.

> *"Read all three of these competitor blog posts and compare them: [url1, url2, url3]"*

> *"Scrape all these pages from my notes: [list of URLs]"*

---

### 🗺️ Map a Website
**When:** You want to see all the pages that exist on a site before deciding what to scrape.

> *"Map the entire physician.ai website — I want to see what sections and pages they have"*

> *"List every URL on doximity.com"*

Returns: complete sitemap of every indexed URL. Use this before crawling to understand what's there first.

---

### 🕷️ Crawl an Entire Website
**When:** You want to read ALL pages on a site, not just one.

> *"Crawl the entire Athenahealth documentation site and extract all the API endpoints"*

> *"Read every page on my competitor's site and summarize their messaging"*

Best combined with: map first to see scale, then crawl selectively.

---

### 🔍 Search the Live Web
**When:** You want to search Google/the web from inside Anti-Gravity.

> *"Search the web for the best AI scribing tools for physicians in 2026"*

> *"Find recent news about FDA approval of AI diagnostic tools"*

---

### 🧠 Extract Structured Data
**When:** You want specific fields pulled out cleanly, not raw text.

> *"Extract the name, specialty, location, and contact info for every doctor listed on this directory: [url]"*

> *"From this competitor's pricing page, extract: plan name, price, features included, and limitations"*

Returns clean JSON you can copy into a spreadsheet, database, or use to build something.

---

### 🤖 Autonomous Research Agent
**When:** You have a complex research mission and don't know which sites to look at.

> *"Find the top 10 EHR companies targeting independent practices, their pricing, and their key differentiators"*

> *"Research what physicians are saying about AI burnout on forums, journal articles, and news sites"*

> *"Find every healthcare accelerator program in the US that accepts physician founders"*

The agent goes off, searches the web autonomously, follows links, reads multiple sources, and comes back with a structured report. You can do other things while it works — it may take a few minutes for complex queries.

---

### 🌐 Browser Automation (Advanced)
**When:** You need to interact with a site, not just read it — click buttons, fill forms, log in.

> *"Navigate to [site], click 'Book a demo', fill out the form with [details]"*

> *"Log into [site] and download the usage report"*

This creates a real browser session in the cloud — useful for sites that have paywalls or require interaction.

---

## Physician-Specific Use Cases

| Scenario | What you say |
|---|---|
| Research competitor telehealth platforms | `firecrawl_agent`: "Find every telehealth platform for physicians, their pricing models, and their differentiators" |
| Monitor a competitor site for changes | `firecrawl_scrape` + schedule weekly |
| Build a physician directory scraper | `firecrawl_extract` with schema: `{name, specialty, location, phone}` |
| Research a medical topic from current web sources | `firecrawl_search` + `firecrawl_extract` |
| Analyze your competitor's entire content strategy | `firecrawl_crawl` → summary of all their pages |
| Pull CME conference schedule from a site | `firecrawl_scrape` with JSON format |
| Get branded style from a site you admire | `firecrawl_scrape` with `branding` format |
| Find grant opportunities for physician entrepreneurs | `firecrawl_agent`: "Find open grant programs for physician-led health startups in 2026" |

---

## Power Combo: Firecrawl → NotebookLM

1. Use `firecrawl_agent` to gather web research
2. Add the source URLs to a NotebookLM notebook
3. Query across all sources for synthesis
4. Generate a briefing doc, mind map, or audio deep dive

This is the physician research stack: Firecrawl finds and reads → NotebookLM synthesizes → you get a decision-ready report.

---

## Setup

Already configured globally. API key lives in `~/.gemini/antigravity/mcp_config.json`.

To protect the key: store a copy in `~/.env` and consider regenerating at [firecrawl.dev](https://firecrawl.dev) since the original key was shared in chat.

---

## Tags
`[research]` `[builder]` `[executive]` `[all-personas]`

## Last tested: March 2026
