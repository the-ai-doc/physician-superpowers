---
name: analyze-website
description: Perform a deep forensic audit of any website — tech stack, product reverse engineering, conversion analysis, elite penetration-grade security analysis, competitive intelligence, and a Gemini 3.1 master rebuild prompt
---

# Analyze Website Skill

Perform a **comprehensive forensic audit** of any target website across 11 structured phases — from DOM inspection to competitive positioning, elite red-team security scanning, and a complete Gemini rebuild prompt. Use the `browser_subagent` tool to render the site, inspect scripts, and capture network calls.

---

## Usage

When the user says **"analyze website [URL]"** or **"do a deep dive on [URL]"**, follow all 11 phases below in order. Do NOT summarize early — work through each phase and extract maximum technical detail before writing the final report.

---

## Phase Execution Instructions

### PHASE 1 — Site Access & Rendering

Open the URL in a full browser environment and determine:

- Whether the site is **server-rendered, client-rendered, or hybrid**
- Whether content is **hidden behind JavaScript execution**
- Whether any **bot protection or scraping prevention** exists (Cloudflare challenge, reCAPTCHA, 403 walls)
- Whether content **changes after page load** (lazy loading, hydration)

If the site requires JavaScript, render the full DOM and capture final visible content.

---

### PHASE 2 — Page Structure Forensics

Extract the **entire page structure** including:

- HTML DOM tree outline
- All sections **in the order users see them**
- Navigation structure and links
- All **calls-to-action** (button text, target URLs)
- Forms and input fields
- Pricing sections (tiers, prices, features)
- Trust signals (testimonials, logos, review counts, media mentions)

Reconstruct the **full visible text content** of the page.

---

### PHASE 3 — Tech Stack Identification

Identify all technologies used:

| Layer | What to Check |
|---|---|
| Frontend framework | React, Vue, Next.js, Nuxt, Svelte, vanilla JS |
| Hosting | Vercel, Netlify, Cloudflare Pages, AWS, GCP |
| CDN | Cloudflare, Fastly, AWS CloudFront |
| Analytics | GA4, Mixpanel, Amplitude, Heap, PostHog |
| Tracking pixels | Meta Pixel, TikTok Pixel, LinkedIn Insight |
| Third-party scripts | Intercom, Hotjar, Segment, HubSpot |
| AI APIs | OpenAI, Anthropic, Replicate, Cohere |
| Payments | Stripe, Paddle, Lemon Squeezy |
| AI builders | Webflow, Framer, Lovable, Bolt, v0 |

Explain **how you identified each** (e.g., script tags, response headers, URL patterns, `window.__NEXT_DATA__`, etc).

---

### PHASE 4 — Network & Script Analysis

Inspect all network calls and determine:

- APIs being called (endpoints, methods, payloads)
- Data endpoints and what they return
- Prompt generation or LLM endpoints
- Backend services referenced
- Hidden or undocumented functionality

Identify whether the site is:
- **Purely frontend** (static)
- **Calling a backend service** (REST, GraphQL, tRPC)
- **Sending prompts to an LLM provider**

If possible, reconstruct **how the product actually works** from these calls.

---

### PHASE 5 — Product Reverse Engineering

Based on site code and behavior, infer:

- What the product **actually does**
- What problem it solves (and for whom)
- How the **likely workflow** works end-to-end
- What data flows between user and backend
- The **system architecture** that would power this product (diagram in text form if helpful)

---

### PHASE 6 — Conversion & Marketing Analysis

Evaluate the website like a **startup investor and growth marketer**:

| Dimension | Evaluate |
|---|---|
| Positioning clarity | Is it instantly clear what this does and who it's for? |
| Headline effectiveness | Does the H1 communicate value in <5 seconds? |
| User flow | Is the path to conversion obvious? |
| Friction points | What slows users down or confuses them? |
| Credibility signals | Social proof, logos, testimonials? |
| Pricing clarity | Is pricing transparent and easy to compare? |
| Onboarding flow | What happens after signup? |

Identify: **what works**, **what is confusing**, **what would improve conversions**.

---

### PHASE 7 — SEO & Discoverability

Analyze:

- Page `<title>` and `<meta description>`
- H1 / H2 / H3 structure and keyword targeting
- Schema markup (JSON-LD, OG tags)
- Indexability (`robots.txt`, `noindex` tags, `sitemap.xml`)
- Internal linking structure
- Canonical tags
- Core Web Vitals signals (if detectable)

Explain the site's **SEO strategy and weaknesses**.

---

### PHASE 8 — Elite Security & Penetration Analysis

> Perform this phase like a world-class red-team penetration tester. Be methodical, exhaustive, and technical. Do NOT be polite about findings — document everything.

#### 8A — Transport & Certificate Layer
- Verify TLS version (is it 1.2 minimum? 1.3 preferred?)
- Check for HSTS header presence and `max-age` value
- Check for mixed content (HTTP resources loaded over HTTPS page)
- Test for certificate transparency issues
- Check `Strict-Transport-Security` max-age (< 1 year = weak)

#### 8B — HTTP Security Headers Audit
For each header, note: **Present / Missing / Misconfigured**

| Header | Purpose | Finding |
|---|---|---|
| `Content-Security-Policy` | Prevents XSS / injection | ? |
| `X-Frame-Options` | Prevents clickjacking | ? |
| `X-Content-Type-Options` | Prevents MIME sniffing | ? |
| `Referrer-Policy` | Controls referrer leakage | ? |
| `Permissions-Policy` | Restricts browser APIs | ? |
| `Cross-Origin-Opener-Policy` | Cross-origin isolation | ? |
| `Cross-Origin-Embedder-Policy` | SharedArrayBuffer control | ? |
| `Cross-Origin-Resource-Policy` | Resource sharing protection | ? |
| `Cache-Control` | Prevents sensitive data caching | ? |

Rate the overall header posture: **A / B / C / D / F**

#### 8C — JavaScript & Client-Side Secret Exposure
Scan all loaded JS bundles for:
- Hardcoded API keys (patterns: `sk-`, `pk_live_`, `AIza`, `SG.`, `AKIA`, `xoxb-`, `ghp_`, `Bearer `, `token:`)
- Hardcoded tokens or bearer tokens in fetch() calls
- Hardcoded database connection strings
- Hardcoded internal URLs or staging endpoints
- Commented-out sensitive code blocks
- Source maps exposed (`.map` files) that reveal original unminified source
- `console.log()` leaking internal state or user PII
- Global `window.*` variables containing session tokens or user data

#### 8D — Endpoint & API Attack Surface
For every API endpoint discovered:
- Test unauthenticated access (remove Auth headers, test anonymous)
- Test JWT tampering: decode the token (base64 middle segment), attempt `alg: none` bypass
- Test for verbose error messages leaking stack traces or DB schema
- Test for IDOR: modify user IDs, record IDs in URL/body → can you access other users' data?
- Check if GraphQL introspection is enabled in production (`__schema` query)
- Probe hidden/debug endpoints:
  - `/.env` `/.git/config` `/.git/HEAD`
  - `/api/debug` `/api/internal` `/api/admin`
  - `/admin` `/wp-admin` `/wp-login.php`
  - `/__debug__` `/graphql` `/api/graphql`
  - `/actuator` `/actuator/health` `/actuator/env` (Spring Boot)
  - `/metrics` `/health` `/status`
  - `/_next/static/` for source maps

#### 8E — Authentication & Session Security
If a login system exists:
- Does login rate-limit requests? (> 10 attempts/min = brute-force vulnerable)
- Are passwords sent over HTTPS only?
- Session cookie flags: `HttpOnly` ✓/✗ · `Secure` ✓/✗ · `SameSite=Strict` ✓/✗
- JWT inspection: decode payload (no verification needed) — what claims? Is `alg: none` accepted?
- Refresh token storage: `httpOnly cookie` (safe) vs. `localStorage` (XSS theft risk)
- Password reset: does "forgot password" confirm if email exists? (user enumeration)
- OAuth flows: is the `state` parameter present? (CSRF protection)
- Is MFA available / enforced for admin accounts?

#### 8F — Supply Chain & Dependency Risk
- Identify major library versions from the bundle
- Flag any known-vulnerable library versions (e.g., lodash < 4.17.21, older React, axios < 1.6.0)
- Check all externally hosted scripts for missing **Subresource Integrity (SRI)** hashes:
  - `<script src="https://cdn.example.com/lib.js">` — no `integrity=` = CDN compromise → full site compromise
- Flag abandoned or deprecated packages
- Check if `package.json` or `package-lock.json` is publicly accessible

#### 8G — Infrastructure & Server Exposure
- What does the `Server` response header reveal? (Nginx/Apache version numbers = CVE surface)
- What does `X-Powered-By` reveal? (PHP version, Express version)
- Subdomains referenced in the codebase: `api.`, `admin.`, `staging.`, `dev.`, `internal.`
- CORS policy: does `Access-Control-Allow-Origin: *` allow any origin to read API responses?
- Open S3 buckets or GCS buckets referenced in asset URLs
- Directory listing enabled? (`/assets/`, `/uploads/`, `/static/`)
- Cloudflare IP leak: does the origin IP appear in any cert transparency logs or DNS records?

#### 8H — Client-Side Injection Vulnerabilities
- Any user-controlled content rendered as HTML? (Stored / Reflected XSS)
- URL parameters reflected into the DOM without sanitization?
- `dangerouslySetInnerHTML` usage in React (scan bundle for this string)
- Any `eval()`, `setTimeout(string)`, or `new Function(string)` calls in the bundle?
- File upload fields: are file types validated client-side only? (bypass = `.php.jpg`, null bytes)
- Open redirect vectors: `?redirect=`, `?next=`, `?url=`, `?return_to=` parameters

#### 8I — Privacy & Regulatory Exposure
- What third-party domains receive user data? (pixels, analytics, CDNs, fonts)
- Is any PII (email, name, IP address) sent to third parties without consent?
- Cookie consent mechanism present? (GDPR/CCPA requirement)
- Cookies set before user consent granted?
- Privacy Policy: does it exist? Does it accurately describe what is collected?
- Is the site targeting EU users? If yes, is a DPA (Data Processing Agreement) required?
- COPPA considerations: does the site target children under 13?

#### 8J — Final Security Risk Score

Produce a scored risk summary:

```
╔══════════════════════════════════════════════════════════╗
║           SECURITY RISK ASSESSMENT SUMMARY               ║
╠══════════════════════════════════════════════════════════╣
║  OVERALL RISK SCORE:    [1–10]  (10 = catastrophic)      ║
║  HEADER POSTURE GRADE:  [A/B/C/D/F]                      ║
║  OVERALL POSTURE:       [🔴 RED / 🟡 AMBER / 🟢 GREEN]   ║
╠══════════════════════════════════════════════════════════╣
║  🔴 CRITICAL (fix immediately):                          ║
║    • [finding]                                           ║
╠══════════════════════════════════════════════════════════╣
║  🟠 HIGH (fix within 7 days):                            ║
║    • [finding]                                           ║
╠══════════════════════════════════════════════════════════╣
║  🟡 MEDIUM (fix within 30 days):                         ║
║    • [finding]                                           ║
╠══════════════════════════════════════════════════════════╣
║  🔵 LOW / INFORMATIONAL:                                 ║
║    • [finding]                                           ║
╚══════════════════════════════════════════════════════════╝
```

---

### PHASE 9 — Competitive Landscape

Determine which **product category** this belongs to (e.g., AI prompt generator, AI website builder, landing page tool, prompt engineering platform, etc.)

Then list **at least 5 direct competitors** and compare:

| Competitor | Positioning | Differentiator | Weakness vs. target |
|---|---|---|---|
| ... | ... | ... | ... |

---

### PHASE 10 — Final Intelligence Report

Produce a structured final report:

1. **What the product actually is** (plain language)
2. **How it likely works technically** (architecture summary)
3. **Tech stack summary** (table)
4. **Defensibility** — Is this hard to copy? Does it have moats?
5. **Biggest weaknesses** — Product, tech, marketing, SEO
6. **How the product could be improved** — 5 concrete suggestions
7. **How a competitor could beat it** — Go-to-market angle, technical edge, positioning

---

### PHASE 11 — Gemini 3.1 Master Rebuild Prompt

After completing all analysis phases, synthesize everything into a **master reconstruction prompt** for Gemini 3.1. This prompt must be so detailed, specific, and prescriptive that a developer can paste it directly into Gemini and receive a production-ready, functionally superior version of the site — no hand-holding required.

**Rules for writing this prompt:**
- Use **real specifics** from your audit — no generic placeholders
- Include exact hex color codes, font names, section names, copy text
- Reference every security fix from Phase 8 as a hard requirement
- Reference every SEO fix from Phase 7 as a hard requirement
- Reference every conversion gap from Phase 6 as a feature requirement
- The prompt should read like a senior engineer's technical spec crossed with a designer's brand brief

**Format the prompt exactly as follows** (output as a raw fenced code block so it can be copy-pasted):

````
GEMINI 3.1 MASTER REBUILD PROMPT
════════════════════════════════

ROLE:
You are a senior full-stack engineer and product designer. Build a complete,
production-ready web application that is a significantly improved version of
[SITE NAME] at [URL]. Do not build a prototype — build the real thing.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
WHAT THE ORIGINAL DOES:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[2–3 sentences from your Phase 5 reverse engineering — what the product is and does]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
WHY THE ORIGINAL FALLS SHORT:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[Bullet list of every critical weakness from your audit — be specific and brutal]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
MANDATORY TECH STACK:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
- Framework: Next.js 14+ with App Router (server components, SSR, SSG)
- Language: TypeScript (strict mode)
- Styling: Tailwind CSS + shadcn/ui
- Animations: Framer Motion (entrance, scroll-triggered, microinteractions)
- Database: [recommend based on product — Supabase / PlanetScale / Turso]
- Auth: [recommend — Clerk / Supabase Auth / NextAuth.js]
- Email: Resend (for transactional email)
- Hosting: Vercel with Edge Functions
- Analytics: PostHog (self-hosted compatible, free tier)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
DESIGN SYSTEM:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[Fill in from your visual analysis:]
- Primary background: [exact hex from site]
- Primary accent: [exact hex, upgraded]
- Secondary accent: [exact hex]
- Text primary: [exact hex]
- Text muted: [exact hex]
- Border/surface: [exact hex]
- Font heading: [Google Font name + weight]
- Font body: [Google Font name + weight]
- Font mono: [Google Font name] (for code/output areas)
- Design language: [dark glassmorphism / warm minimal / bold brutalist / etc.]
- Border radius: [sm / md / lg / none]
- Shadow style: [soft / hard / glow / none]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
ANIMATION SPEC:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
- Page entrance: fade-up with stagger (each section delayed 100ms)
- Scroll-triggered: use Framer Motion `whileInView` with `once: true`
- Button hover: scale(1.03), brightness(1.1), 150ms ease
- Input focus: border glow (box-shadow with accent color at 40% opacity)
- Draggable elements: scale(1.04), elevated shadow on drag
- Loading states: skeleton shimmer (CSS animation)
- Transitions: spring physics (stiffness: 400, damping: 28)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
FEATURES TO REPLICATE (with upgrades):
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[For every feature in Phase 2, write:]
Feature: [name]
Original: [what it did]
Upgraded: [what your version will do better — be specific]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
NEW FEATURES TO ADD (audit gaps):
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[Every missed opportunity from Phases 6–10:]
1. [Feature + why it matters + how to implement]
2. ...

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PAGE / COMPONENT SPEC:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[For each section from Phase 2:]

### [Component Name]
- Purpose: [what this section does]
- Layout: [grid / flex / full-width / centered]
- Content: [exact real copy, not placeholder text]
- CTA: [button text → action/route]
- Animation: [entrance behavior]
- Responsive: [mobile layout description]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SEO REQUIREMENTS (mandatory — fix everything):
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[From Phase 7, list every fix as a hard requirement:]
- generateMetadata() in layout.tsx with title, description, OG, Twitter Card
- robots.ts and sitemap.ts in /app
- Schema markup: [specify type — SoftwareApplication / WebSite / LocalBusiness]
- Target keywords to include in headings: [list from audit]
- All pages must be SSR or SSG — no pure CSR

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECURITY REQUIREMENTS (mandatory — fix everything):
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[From Phase 8, every finding becomes a requirement:]
- next.config.js: add full security headers (CSP, HSTS, X-Frame-Options, etc.)
- All API keys in .env.local — never in client bundle
- HttpOnly + Secure + SameSite=Strict on all cookies
- Rate limiting on all API routes (use Upstash Ratelimit)
- Input validation with Zod on all form submissions
- No dangerouslySetInnerHTML
- CORS configured explicitly — no wildcard origins
- Privacy Policy page at /privacy
- Cookie consent banner before setting any analytics cookies

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
CONVERSION REQUIREMENTS:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[From Phase 6, every gap becomes a requirement:]
[e.g.: "Email capture modal appears after user generates prompt, before copy is enabled"]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
FILE STRUCTURE:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
/app
  layout.tsx          (global layout, fonts, metadata base)
  page.tsx            (home page)
  /api
    /[routes]         (API routes)
  /[other pages]
/components
  /ui                 (shadcn components)
  /[feature folders]
/lib
  /utils.ts
  /[service files]
/styles
  globals.css
next.config.js        (security headers, image domains)
tailwind.config.ts
.env.local            (all secrets — never committed)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
ENVIRONMENT VARIABLES:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[List every .env variable the rebuilt app will need:]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
BUILD ORDER:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Build in this exact order:
1. next.config.js with all security headers
2. globals.css with design tokens (CSS variables)
3. tailwind.config.ts with custom colors/fonts
4. Layout component and font loading
5. [Components in page order, top to bottom]
6. API routes
7. Email flows
8. Metadata and SEO files
9. Privacy Policy page

Start now. Write complete, working code for each file. Do not use placeholder 
text — use real copy based on the original site's positioning and audience.
Do not ask clarifying questions — make the best decisions and build.
````

---

## Output Format

Structure the full output as a **markdown report** with clear phase headers (`## Phase 1 — ...`). Be extremely thorough. Do NOT summarize early or skip phases.

Save the report to `website-audit-[domain].md`.

The Gemini rebuild prompt goes at the very end of the report in its own `## Phase 11 — Gemini Rebuild Prompt` section, formatted as a fenced code block ready to copy-paste.

---

## Tips

- Use `browser_subagent` to render JS-heavy sites and capture the live DOM
- Use `read_url_content` for fast static pages
- Check `view-source:` equivalent and look for `<script>` tags, `window.__` globals, and `data-` attributes
- Headers like `x-powered-by`, `server`, and `cf-ray` reveal hosting and CDN
- Source map URLs (`.map` files) can reveal framework internals
- `robots.txt` and `sitemap.xml` are always worth fetching
- For security scanning, probe `/.env`, `/.git/config`, `/api/debug`, etc. via `read_url_content`
- To decode a JWT: base64-decode the middle segment (no verification needed to read claims)
- SRI hash absence: `<script src="https://...">` with no `integrity=` attribute = supply chain risk
- When probing endpoints, a `403` or `401` means the route exists — document it; a `404` means it doesn't
