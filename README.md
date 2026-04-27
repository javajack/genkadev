# Genka.dev — Founder Feedback, Gaps &amp; the Revised Pitch

> **Live page:** [javajack.github.io/genkadev](https://javajack.github.io/genkadev/)

A single-page, mobile-first, neo-brutalist memo that combines:

1. **Part I — Founder Feedback** — second-person, builder-to-builder review of `genka.dev` after a real test pass against the live API.
2. **Part II — The Gaps** — data, correctness, business-model and fairness gaps, named honestly.
3. **Part III — The Revised Pitch** — the wedge, integrated moats, the multi-account Family Vault, pricing redesign, GTM, defensibility math, the **Fairness &amp; Compliance Charter**, and the why-now meta-thesis.
4. **Part IV — Execution** — risks ranked + 90-day plan.
5. **Part V — The Bet** — one paragraph.

## Stack

- Single self-contained `index.html` (~125 KB).
- No build step, no JS framework. Inline CSS, vanilla JS for theme toggle and scroll reveal.
- Google Fonts via CSS `@import` (graceful degrade to system fonts offline).
- Light theme default; dark toggle persists via `localStorage`.

## Files

| File | Purpose |
|---|---|
| `index.html` | The memo. |
| `og.svg` | 1200×630 social-share image. |
| `robots.txt` | Crawler policy (allows GPTBot, ClaudeBot, PerplexityBot, etc.). |
| `sitemap.xml` | Single-page sitemap. |
| `.github/workflows/publish.yml` | GitHub Pages deployment workflow. |
| `.gitignore` | Excludes `genka_key.txt` and other secrets. |

## Local preview

```bash
xdg-open index.html        # Linux
open index.html            # macOS
start index.html           # Windows
```

Or any static server:

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Deployment

Pushes to `main` are auto-deployed to GitHub Pages via `.github/workflows/publish.yml`. **One-time setup:** in repo settings → Pages → Source → "GitHub Actions".

## Author

**Rakesh Waghela** — Engineering Leader · Product Builder · Systems Architect.
17+ years shipping production systems across fintech, edtech, SaaS.

- Portfolio: [javajack.github.io](https://javajack.github.io/)
- LinkedIn: [linkedin.com/in/rakeshwaghela](https://www.linkedin.com/in/rakeshwaghela/)
- GitHub: [github.com/javajack](https://github.com/javajack)
- X: [@webiyo](https://x.com/webiyo)

## Disclosures

Independent analysis. No commercial relationship with Genka, its investors, or any competitor named. ARR projections labelled `[thesis estimate]`, not promises. Trial API key used during validation has been redacted in all curl examples and is excluded from this repository via `.gitignore`. Where I'm wrong, I'd rather know.

## Note on the OG image

`og.svg` is an SVG (vector) social-share card. Modern Facebook / LinkedIn / Discord render it correctly; some Twitter clients prefer raster. To convert:

```bash
# Using rsvg-convert (librsvg)
rsvg-convert -w 1200 -h 630 og.svg -o og.png

# Or via Inkscape
inkscape og.svg --export-type=png --export-filename=og.png -w 1200
```

Then add a second `og:image` meta tag pointing to `og.png` if you want maximum cross-platform compatibility.
