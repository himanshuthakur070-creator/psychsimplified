# Maintenance Guide

Everything lives in **`index.html`**. Open it in any text editor (VS Code is ideal).
Use `Ctrl/Cmd + F` to jump to the labelled blocks named below.
After any edit: save → `git add .` → `git commit -m "…"` → `git push`. The live site updates in ~1 minute.

---

## 1. Add a new disorder

**Step A — register it.** Find the `const DISORDERS = [` block. Add one entry:

```js
{ id:'panic', name:'Panic Disorder', icon:'💓', cat:'Anxiety', tag:'tag-teal', sub:'Sudden surges of intense fear' },
```

- `id` — short, lowercase, no spaces (used in the URL).
- `cat` — must match one of the hub categories.
- `tag` — `tag-teal`, `tag-lav`, `tag-amber`, or `tag-rose` (just a colour).

That alone makes it appear in the library with an auto-generated template page.

**Step B (optional) — write full content.** Find the `const CONTENT = {` block.
Copy an existing full entry (e.g. `depression: { … }`) and adapt it under your new `id`.
Each disorder can include `mythData`, `quiz`, and `flash` (flashcards). Follow the shape of the Depression entry exactly.

---

## 2. Publish a new blog post

Find `const BLOG = [`. Add:

```js
{ t:'Title of the post', cat:'Awareness', date:'2026-07-10', read:'5 min',
  ex:'One-sentence summary that also feeds the search.',
  body:'<p>Your post. Use HTML tags: &lt;p&gt;, &lt;h3&gt;, &lt;ul&gt;&lt;li&gt;…&lt;/li&gt;&lt;/ul&gt;.</p>' },
```

Newest posts go at the **top** of the array. `cat` becomes a filter tag automatically.

---

## 3. Add a downloadable PDF / worksheet

Find `const RESOURCES = [`. Add:

```js
{ t:'Worksheet name', d:'Short description of what it is and who it helps.' },
```

The site turns this into a printable template. **To offer a real PDF file instead:**
1. Drop your `my-worksheet.pdf` into this project folder.
2. In the resource card, link to it: add `link:'/my-worksheet.pdf'` and it becomes a direct download.

---

## 4. Update your profile / CV

- **About page text:** find `function renderAbout(`. Edit the education timeline, highlights, and interests directly.
- **Research/publications:** find `function renderResearch(`. Update publications, conferences, and the dissertation summary.
- **Downloadable CV:** find `function downloadResume(`. Edit the details there; the site generates a printable CV on click.

---

## 5. Monitor website performance

- **Cloudflare dashboard → your project → Web Analytics:** visitors, top pages, countries. Free, privacy-friendly, no cookie banner needed.
- **Google PageSpeed Insights** (pagespeed.web.dev): paste your URL for a speed + best-practices score. Aim for 90+.
- **Google Search Console** (search.google.com/search-console): shows which search terms bring people in, and any indexing problems. Submit your `sitemap.xml` here once.

---

## 6. Improve accessibility over time

- The built-in panel already covers dark mode, contrast, dyslexia font, and text scaling.
- When adding images later, always give them descriptive `alt` text.
- Keep colour contrast strong (don't put pale text on pale backgrounds).
- Test with keyboard only (Tab / Enter) now and then.
- Run the free **WAVE** checker (wave.webaim.org) on your live URL.

---

## 7. Optimise SEO over time

- Keep each disorder's opening paragraph clear and keyword-rich (natural language, not stuffing).
- When you add pages, add matching `<url>` lines to `sitemap.xml`.
- Update the `og-image.png` if you rebrand.
- Earn links: share posts on LinkedIn, cite the site in talks.
- Re-submit the sitemap in Search Console after big content additions.

---

## Safety rules (never remove)

- The **"education only, not a substitute for care"** disclaimer in the footer.
- The **crisis line** (Tele-MANAS 14416) in the footer.
- Never present template/placeholder disorder content as final clinical guidance — mark drafts clearly until you've written and checked them.

---

## Emergency: undo a bad change

Because everything is in Git, you can always roll back:

```bash
git log --oneline          # find the last good commit (copy its code, e.g. a1b2c3d)
git revert a1b2c3d          # safely undoes that change as a new commit
git push
```

Or restore a single file to how it was in the last commit:

```bash
git checkout -- index.html
```
