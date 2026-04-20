# Pert Lomp — Personal Landing Page

Static site. Deploys to Vercel with zero configuration.

## Files

```
/
├── index.html              # Main landing page (EN + ET, light + dark)
├── sitemap.xml             # Search engine sitemap
├── robots.txt              # Crawler directives
├── site.webmanifest        # PWA manifest
├── vercel.json             # Vercel config (headers, caching, HTTPS)
└── assets/
    ├── pert-portrait.jpg   # Hero portrait
    ├── pert-square.jpg     # Square crop
    ├── pert-lomp-og.png    # 1200×630 social share card
    ├── pertlomp-logo.png   # Pert Lomp monogram logo
    ├── evoluna-icon.svg    # Evoluna mark (+ variants)
    ├── evoluna-wordmark.svg
    └── pathline*.svg       # Decorative squiggle motifs
```

## SEO — included

- Full meta tags (title, description, keywords, language, geo, theme-color)
- Open Graph (profile type) + Twitter Card (summary_large_image)
- Canonical URL + hreflang (EN / ET / x-default)
- JSON-LD structured data:
  - `Person` (Pert Lomp, with affiliations, knowsAbout, sameAs)
  - `ProfessionalService` with `OfferCatalog` (all 6 services + prices)
  - `WebSite`
  - `FAQPage` (8 Q&A pairs)
  - `BreadcrumbList`
- `sitemap.xml` with image sitemap + hreflang alternates
- `robots.txt` allowing all major search engines & AI crawlers, blocking scrapers
- Security headers via `vercel.json` (HSTS, X-Content-Type-Options, Referrer-Policy, Permissions-Policy)
- Aggressive caching for `/assets/*` (1 year, immutable)
- Skip-link for a11y; semantic `<main>` / `<header>` / `<nav>` / `<footer>` / `<section>` structure
- Descriptive alt text on images
- `<html lang>` + `hreflang` links for bilingual content

## Deploy

### Option 1 — Vercel via GitHub
1. Push this folder to a GitHub repo
2. Import the repo in Vercel → auto-deploys on every push
3. Add custom domain `pertlomp.com` in Vercel → Settings → Domains

### Option 2 — Vercel CLI
```bash
npm i -g vercel
vercel --prod
```

### Option 3 — Drag & drop
Drag this folder into vercel.com/new

## Post-deploy checklist

1. Verify domain `pertlomp.com` in Vercel dashboard
2. [Google Search Console](https://search.google.com/search-console) → add property → verify → submit `https://pertlomp.com/sitemap.xml`
3. [Bing Webmaster Tools](https://www.bing.com/webmasters) → submit sitemap
4. Test structured data: [Rich Results Test](https://search.google.com/test/rich-results)
5. Test social cards: [Facebook Debugger](https://developers.facebook.com/tools/debug/) · [Twitter/X Validator](https://cards-dev.twitter.com/validator)
6. Lighthouse audit (should score 95+ on all four)

## Editing

All content is in `index.html`. The page has a built-in language switcher (EN/ET) and theme toggle (light/dark). The Estonian translations live in the `I18N.et` object near the bottom of the file.

## Credits

Built on the Evoluna visual identity. Typography: Fraunces (display), Poppins (UI), JetBrains Mono (meta).
