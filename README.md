# PsychSimplified

**Mental health made simple.** An evidence-based psychology & psychiatry education site
plus a personal clinical-psychology portfolio — built as a single, fast, offline-capable
static website with no build step.

Live idea: `https://psychsimplified.pages.dev` (your real URL appears after you deploy).

---

## What's inside

| File | What it is |
|---|---|
| `index.html` | The **entire website** (HTML + CSS + JavaScript in one file). This is where all content lives. |
| `manifest.webmanifest` | Makes the site installable as an app (PWA). |
| `sw.js` | Service worker — lets the site work offline and load fast on repeat visits. |
| `robots.txt` | Tells search engines they may index the site. |
| `sitemap.xml` | Lists your pages so Google finds them faster. |
| `_headers` | Security + caching rules (used automatically by Cloudflare Pages). |
| `404.html` | Friendly "page not found" screen. |
| `favicon.svg` / `favicon.ico` | Browser tab icon. |
| `icon-192.png` / `icon-512.png` | App icons (home-screen, PWA). |
| `apple-touch-icon.png` | iPhone/iPad home-screen icon. |
| `og-image.png` | Preview image shown when the link is shared on social media. |
| `MAINTENANCE.md` | How to add disorders, blog posts, PDFs, update your CV, etc. |

**Key idea:** it's a *static site*. There's no server, no database, no build tools.
That means it's free to host, nearly impossible to break, and loads instantly.

---

## Run it on your own computer (local preview)

You don't strictly need anything installed — you can double-click `index.html`.
But to test the app/offline features properly, run a tiny local server:

```bash
# Option A — Python (already on Mac/Linux; on Windows install from python.org)
python3 -m http.server 8080

# Option B — Node.js
npx serve .
```

Then open `http://localhost:8080` in your browser.

---

## Features already built in

- 28-disorder searchable library (6 fully written: Depression, OCD, Schizophrenia, GAD, PTSD, Bipolar; the rest use a structured template ready to fill).
- Interactive quizzes, flashcards, a symptom-sorting game, and a diagnostic decision tree.
- Study notes (printable one-pagers) and downloadable clinical worksheet templates.
- Blog, research/publications page, and an About/portfolio page.
- Site-wide keyword search.
- Full accessibility panel: dark mode, high contrast, **dyslexia-friendly font**, and text-size scaling — all remembered between visits.
- Installable as an app + works offline (PWA).
- SEO + social-share ready (meta tags, Open Graph, sitemap, robots).

---

## Deploy (short version)

1. Put this folder on **GitHub** (a free code home).
2. Connect the GitHub repo to **Cloudflare Pages** (free hosting).
3. Cloudflare gives you a free `https://…pages.dev` address with HTTPS already on.
4. Every time you push a change to GitHub, the site updates itself automatically.

The full click-by-click walkthrough is in the chat guide. Custom domain, analytics,
and everything else is covered there too.

---

## Editing philosophy

Everything is in `index.html`, organised into clearly commented blocks:

- `TOKENS` / CSS — colours, spacing, fonts.
- `DISORDERS`, `CONTENT`, `BLOG`, `RESOURCES`, `HUB` — your **content data** (plain JavaScript arrays/objects). This is what you edit most.
- Render + router functions — the machinery. You rarely touch these.

See `MAINTENANCE.md` for copy-paste recipes.

---

## Disclaimer

This site is for **education only** and is not a substitute for professional diagnosis
or care. A crisis line (India: Tele-MANAS **14416**) is shown in the footer. Keep this.
