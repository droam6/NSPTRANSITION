# North Shore Projects — Progress Tracker

> Last updated: 2026-02-11

---

## Phase 1: Technical SEO Foundation — COMPLETE

| Item | Status | Notes |
|------|--------|-------|
| CSS design system (`css/styles.css`) | Done | 1,394 lines. Custom properties, mobile-first, all component styles |
| Minified CSS (`css/styles.min.css`) | Done | Production bundle referenced by all HTML pages |
| Google Fonts (Montserrat + Open Sans) | Done | Preconnected, loaded via Google Fonts CDN |
| Font Awesome 6.5.1 icons | Done | CDN with SRI hash |
| Mobile-first responsive breakpoints | Done | 768px / 1024px / 1200px |
| Mobile hamburger nav | Done | Inline JS toggle on all navigable pages |
| Skip-to-content link | Done | Accessibility baseline |
| Semantic HTML5 structure | Done | `<header>`, `<main>`, `<section>`, `<footer>`, `<nav>` |
| Meta tags (title, description) | Done | Unique per page |
| Open Graph + Twitter Card tags | Done | All pages |
| Canonical URLs | Done | All pages |
| hreflang `en-AU` | Done | All pages |
| JSON-LD structured data | Done | LocalBusiness + Service/Article schemas per page type |
| Heading hierarchy (single H1) | Done | Verified across all pages |

## Phase 2: Suburb Landing Pages (51) — COMPLETE

| Item | Status | Notes |
|------|--------|-------|
| 17 tiling suburb pages | Done | Unique content per suburb, local landmarks referenced |
| 17 painting suburb pages | Done | Same structure, painting-specific content |
| 17 cleaning suburb pages | Done | Same structure, cleaning-specific content |
| Internal cross-links (nearby suburbs) | Done | 2-3 nearby suburb links per page |
| Service-specific JSON-LD | Done | @graph with Service + HomeAndConstructionBusiness |
| Hidden tracking fields | Done | `source=organic`, `landing={service}-{suburb}`, `suburb_page={suburb}` |
| Forms with `action="/api/contact"` | Done | All 51 pages |
| Breadcrumb navigation | Done | Home > Service > Suburb |

### Suburbs covered
Chatswood, Killara, Gordon, Pymble, Turramurra, Lindfield, Roseville, St Ives, Wahroonga, Lane Cove, Willoughby, Artarmon, Crows Nest, North Sydney, Neutral Bay, Mosman, Cremorne

## Phase 3: Blog Infrastructure — COMPLETE

| Item | Status | Notes |
|------|--------|-------|
| Blog listing page (`blog/index.html`) | Done | Card grid, 5 posts listed |
| How to Choose Bathroom Tiles | Done | ~800-1200 words, links to tiling service + suburbs |
| Interior Painting Tips | Done | ~800-1200 words, links to painting service + suburbs |
| End of Lease Cleaning Checklist | Done | ~800-1200 words, links to cleaning service + suburbs |
| Kitchen Splashback Trends 2026 | Done | ~800-1200 words, links to tiling service + suburbs |
| How Often to Repaint Your House | Done | ~800-1200 words, links to painting service + suburbs |
| Article schema (JSON-LD) | Done | Article type on blog posts |
| Cross-links to services + suburbs | Done | Each post links to relevant service page + 1-2 suburb pages |

## Phase 4: Meta Ads Landing Pages (3) — COMPLETE

| Item | Status | Notes |
|------|--------|-------|
| Tiling landing (`landing/tiling.html`) | Done | Inline CSS, no nav, conversion-optimised |
| Painting landing (`landing/painting.html`) | Done | Same pattern |
| Cleaning landing (`landing/cleaning.html`) | Done | Same pattern |
| `noindex, nofollow` meta | Done | Prevents indexing of ad-only pages |
| Hidden `source=meta-ad` field | Done | Attribution tracking |
| Trust badges + testimonials | Done | Social proof for conversion |
| Meta Pixel placeholder | Done | `<!-- META PIXEL CODE HERE -->` in head |
| Inline validation CSS | Done | Form validation styles embedded |

## Phase 5: Internal Linking — COMPLETE

| Item | Status | Notes |
|------|--------|-------|
| Homepage links to all services | Done | Service card grid |
| Homepage links to blog + key suburbs | Done | Blog preview section, service areas |
| Service pages link to 17 suburb pages | Done | Service areas grid with links |
| Suburb pages link to parent service | Done | Breadcrumb + body links |
| Suburb pages link to nearby suburbs | Done | Pill-style buttons, 2-3 nearby |
| Blog posts link to services + suburbs | Done | Contextual in-article links |
| Footer links | Done | Services, popular suburbs, blog |

## Phase 6: Tracking Placeholders — COMPLETE

| Item | Status | Notes |
|------|--------|-------|
| GTM `<head>` placeholder | Done | All pages: `<!-- GOOGLE TAG MANAGER -->` |
| GTM `<noscript>` placeholder | Done | All pages: after `<body>` |
| `dataLayer.push()` on form submit | Done | Fires via `form-validation.js` |
| Meta Pixel placeholder | Done | Landing pages only |
| Conversion tracking comment | Done | `// CONVERSION TRACKING - fire GTM event here` |

## Phase 7: Final Polish — COMPLETE

| Item | Status | Notes |
|------|--------|-------|
| `sitemap.xml` | Done | 65+ URLs with priority + changefreq |
| `robots.txt` | Done | Allow all, disallow `/api/`, sitemap ref |
| `CLAUDE.md` project docs | Done | Full documentation |
| Contact details (phone) | Done | 0433 333 332 / +61433333332 across all pages |
| Service-specific emails | Done | Tiling/Painting/Cleaning routed correctly |

## Phase 8: Form Validation — COMPLETE

| Item | Status | Notes |
|------|--------|-------|
| `js/form-validation.js` created | Done | 357 lines, IIFE pattern |
| Validation CSS in `styles.css` | Done | Error/success states, char counter, loading spinner |
| Name validation | Done | Letters/spaces/hyphens/apostrophes, min 2 chars, auto-capitalise |
| Email validation | Done | Regex format check, auto-lowercase |
| Phone validation | Done | Australian format (0/+61 prefix, 10 digits) |
| Message validation | Done | 10-1000 chars, live character counter |
| Select validation | Done | Required selects must have a value |
| Honeypot spam field | Done | Hidden `website_url` field, bot gets fake success |
| Timestamp check | Done | Rejects submissions under 3 seconds |
| Loading spinner on submit | Done | Button disabled + spinner animation |
| Script tag on all 59 pages with forms | Done | Root=`js/`, suburbs/landing=`../js/` |
| Inline form handlers removed | Done | No duplicate submit handlers |

---

## Phase 9: Mobile UX Overhaul — COMPLETE

| Item | Status | Notes |
|------|--------|-------|
| Mobile hero redesign (index.html) | Done | 65vh height, flex-end layout, left-aligned text, stacked CTAs (320px max-width), hidden arrows/indicators |
| Slideshow auto-rotate on mobile | Done | `setInterval` at 5s — arrows/indicators hidden so autoplay is the only navigation |
| Slide text bleed-through fix | Done | `transition: none` on `.hero-slide` in mobile media query prevents crossfade overlap |
| Hamburger menu close button | Done | `.mobile-menu-close` (absolute-positioned X) on all 5 main pages |
| Hamburger menu redesign | Done | Opaque #1A1A2E background, grouped navigation (Services label), tap-to-call, Instagram link, gold CTA button |
| Header CTA hidden when menu open | Done | `:has(.navbar-toggle.active)` hides Get a Quote in header |
| AOS CDN fix | Done | Switched from cdnjs (404) to jsdelivr; `AOS.init()` wrapped in try-catch on 4 pages |
| Hamburger double-toggle bug | Done | Removed duplicate inline `onclick` — only `addEventListener` handler remains |
| Horizontal overflow fix | Done | Added `html { overflow-x: hidden; }` to prevent AOS fade-left/right from causing scroll |
| contact.html mobile menu parity | Done | Added `mobile-menu` class + inline `<style>` block for contact page (uses different nav implementation) |

---

## Phase 10: Bosland-Inspired Visual Redesign (v2) — IN PROGRESS

| Item | Status | Notes |
|------|--------|-------|
| CSS design system rewrite (`css/styles.css`) | Done | 2,885 lines. Full Bosland-style adaptation: DM Serif Display + DM Sans fonts, gold #C19A6B, cream #FAFAF8 backgrounds, editorial section labels, numbered services, trust bar, FAQ accordion, gallery/lightbox, dark contact section |
| All existing class names preserved | Done | `.navbar`, `.mobile-menu`, `.hero-slideshow`, `.section`, `.form-group`, `.blog-card`, `.footer`, etc. — HTML pages continue to render |
| New component styles added | Done | `.trust-bar`, `.bento-card`, `.service-item` (numbered), `.why-card`, `.process-card`, `.faq-item`, `.gallery-scroll`, `.lightbox`, `.google-rating`, `.form-wrapper` |
| Light/dark form variants | Done | Dark (default) and `.form-light` variants with appropriate colors, placeholders, select arrows |
| Service page hero/description | Done | `.service-hero` with overlay, `.service-description` two-column layout, `.service-sidebar` |
| Minified CSS (`css/styles.min.css`) | Remaining | Must re-minify after CSS changes |
| Google Fonts `<link>` update | Remaining | HTML pages still load Montserrat + Open Sans — need DM Serif Display + DM Sans |
| Homepage HTML rebuild | Remaining | Will be done page-by-page |
| Service pages HTML rebuild | Remaining | tiling.html, painting.html, cleaning.html |
| Contact page HTML rebuild | Remaining | contact.html |
| Suburb pages HTML update | Remaining | 51 suburb pages need font links + any class changes |
| Blog pages HTML update | Remaining | Blog listing + 5 posts |
| Landing pages CSS update | Remaining | Inline CSS on landing pages uses old gold #D4A853 |

---

## REMAINING WORK

### High Priority (blocks launch)

| Item | Blocked By | Notes |
|------|-----------|-------|
| Form backend (`/api/contact`) | Hosting decision | Need serverless function or email service (Formspree, Netlify Forms, etc.) |
| Actual images in `/images/` | Photography/stock | All `<img>` tags reference placeholder paths. Hero backgrounds, service cards, blog thumbnails, OG images all needed |
| Privacy policy page (`privacy.html`) | Legal content | Linked from 45+ page footers and tiling.html consent checkbox. Currently 404 |
| Terms & conditions page (`terms.html`) | Legal content | Linked from 45+ page footers. Currently 404 |
| Favicon + apple-touch-icon | Asset creation | No `<link rel="icon">` on any page. Need .ico, .png, .svg |

### Medium Priority (blocks marketing)

| Item | Blocked By | Notes |
|------|-----------|-------|
| Google Tag Manager container | GTM account | Replace `GTM-XXXXXXX` placeholder with real container ID |
| Meta Pixel installation | Meta Business account | Replace `<!-- META PIXEL CODE HERE -->` in landing pages |
| Google Ads conversion tracking | Ads account | Uncomment and configure conversion snippet |
| Google My Business setup | GMB account | Needed for local SEO + map pack |
| Google Search Console | DNS verification | Submit sitemap.xml |
| Google Maps embed on contact page | Maps API key | Currently placeholder in contact.html |

### Low Priority (nice to have)

| Item | Notes |
|------|-------|
| CSS minification automation | Currently manual `npx csso-cli` — consider build script |
| JS minification | `form-validation.js` is unminified (357 lines) |
| Image optimisation pipeline | WebP conversion, srcset, lazy loading already in HTML |
| 404 page | No custom 404.html |
| Accessibility audit | Skip links done, aria-labels done, needs WAVE/axe testing |
| Performance audit | Lighthouse / PageSpeed Insights once live |

---

## KNOWN ISSUES

| Issue | Severity | Details |
|-------|----------|---------|
| Landing pages in sitemap.xml | Low | 3 landing pages have `noindex, nofollow` but are listed in sitemap.xml. Should be removed from sitemap or sitemap should exclude `/landing/` |
| Landing pages not blocked in robots.txt | Low | `/landing/` directory should have `Disallow` since pages are noindex |
| ABN is placeholder | Medium | `12 345 678 901` is a dummy ABN — needs real ABN before launch |
| Aggregate ratings in schema | Medium | 4.9 stars / 87 reviews hardcoded in JSON-LD — need real review data or remove |
| Hidden field inconsistency | Low | Suburb pages use either `name="landing"` or `name="suburb_page"` depending on batch — should standardise |
| Blog dates may be future-dated | Low | Blog posts dated Jan-Feb 2026 — verify these match desired publish schedule |
| Contact page footer year | Low | Verify `2025` vs `2026` copyright year consistency across all footers |
