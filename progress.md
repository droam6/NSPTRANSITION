# North Shore Projects — Progress Tracker

> Last updated: 2026-03-20 (Added 60 tiling photos to gallery + arrow navigation on all service pages)

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

## Phase 3: Blog Infrastructure — REMOVED

| Item | Status | Notes |
|------|--------|-------|
| Blog removed from site | Done | All nav links, mobile menu links, footer links, blog preview sections, related blog sections, sitemap entries, and inline content links removed. Blog files still exist in `/blog/` but are unlinked. |

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

## Phase 10: Editorial Visual Redesign (v2) — COMPLETE

| Item | Status | Notes |
|------|--------|-------|
| CSS design system rewrite (`css/styles.css`) | Done | 2,885 lines. Full editorial-style adaptation: DM Serif Display + DM Sans fonts, gold #C19A6B, cream #FAFAF8 backgrounds, editorial section labels, numbered services, trust bar, FAQ accordion, gallery/lightbox, dark contact section |
| All existing class names preserved | Done | `.navbar`, `.mobile-menu`, `.hero-slideshow`, `.section`, `.form-group`, `.blog-card`, `.footer`, etc. — HTML pages continue to render |
| New component styles added | Done | `.trust-bar`, `.bento-card`, `.service-item` (numbered), `.why-card`, `.process-card`, `.faq-item`, `.gallery-scroll`, `.lightbox`, `.google-rating`, `.form-wrapper` |
| Light/dark form variants | Done | Dark (default) and `.form-light` variants with appropriate colors, placeholders, select arrows |
| Service page hero/description | Done | `.service-hero` with overlay, `.service-description` two-column layout, `.service-sidebar` |
| Minified CSS (`css/styles.min.css`) | Done | Re-minified via csso-cli: 61.8KB → 44.1KB (29% reduction). Note: all HTML pages reference `styles.css` directly, not the minified version |
| Google Fonts `<link>` update | Partial | index.html + 4 service pages + contact + 6 blog + 3 landing pages updated to DM Serif Display + DM Sans — 51 suburb pages still load Montserrat + Open Sans |
| Homepage HTML rebuild | Done | Full v2 redesign rebuild: DM Serif Display + DM Sans fonts, editorial numbered services, trust bar with stats, section labels, FAQ accordion, service areas grid (17 suburbs), blog preview, dark contact section with Google rating, scroll indicator, skip-link, form-validation.js integration, all empty tel:/mailto: links fixed, removals → external partner |
| Service pages HTML rebuild | Done | tiling.html (843 lines), painting.html (806 lines), cleaning.html (748 lines), removals.html (686 lines). All rebuilt with: hreflang, Twitter Card, og:locale, skip link, DM Serif+DM Sans, FA 6.5.1 SRI, AOS jsdelivr try-catch, enhanced JSON-LD (HomeAndConstructionBusiness, email, hours, rating), v2 redesign nav with Blog link + removals→external, mobile menu with close button (addEventListener), section labels, trust bar stats, numbered process steps (dark bg), FAQ accordion (5 Qs each), CTA banner, dark contact section with gold-line + Google rating, form action="/api/contact" + form-validation.js, Popular Areas footer, fixed empty tel:/mailto: links. Tiling/painting have real image galleries; cleaning/removals have placeholders. Cleaning has 17 suburb links + 1 blog post. Removals has no suburb links (per D04) and no blog posts. |
| Contact page HTML rebuild | Done | contact.html rebuilt: replaced old `.nav`/`.nav-toggle` structure with `.navbar`/`.navbar-toggle`, removed inline `<style>` mobile menu block, DM Serif+DM Sans fonts, AOS added, service hero header, trust bar, editorial dark contact section with gold-line + Google rating, form with service/suburb selects + action="/api/contact", map placeholder preserved, FAQ section (5 general Qs), CTA banner, updated footer, suburb dropdown expanded to 17 suburbs, all inline handlers removed |
| Suburb pages HTML rebuild | Done | All 51 suburb pages (17 tiling + 17 painting + 17 cleaning) rebuilt with v2 redesign navbar, mobile menu, footer, DM Serif Display + DM Sans fonts, AOS, section labels, FAQ accordion, CTA banner, scroll-to-top, mobile call button |
| Blog pages HTML update | Done | Blog listing + 5 article pages rebuilt with v2 redesign navbar, mobile menu, footer, AOS, section labels, scroll-to-top, mobile call button. Service-specific footer emails (tiling→northshoretiling8, painting→northshorepainting88, cleaning→northshorecleaning8). Blog listing cards fixed to point to correct files. |
| Landing pages CSS update | Done | All 3 landing pages rebuilt with editorial-style inline CSS: DM Serif Display + DM Sans fonts, gold #C19A6B, border-radius: 0, font-weight: 400 headings |

---

## Phase 11: Bug Fix Pass — COMPLETE

| Item | Status | Notes |
|------|--------|-------|
| contact.html navbar parity | Done | Instagram link was missing `?igsh=MW9vbzJtaXRoY3h3OQ==` tracking parameter — added to match all other pages |
| Mobile horizontal overflow | Done | Added `overflow-x: hidden` to `body` in styles.css (was only on `html`). Both needed for mobile Safari/Chrome to prevent AOS fade-left/right overflow |
| Hero text overlap on small screens | Done | Added comprehensive mobile overrides at `@media (max-width: 767px)`: reduced min-height to 85vh/85svh, tightened font sizes, spacing, button padding. Prevents label+title+subtitle+2 CTAs from overflowing viewport |
| Dynamic copyright year | Done | Replaced hardcoded `&copy; 2026` with `&copy; <script>document.write(new Date().getFullYear())</script>` across 63 files (root + suburbs/ + blog/). Landing pages excluded (inline CSS, separate maintenance) |
| Hidden form field consistency | Done | Verified: all 51 suburb pages already use `name="landing"` consistently (no `name="suburb_page"` exists). Field patterns are intentionally different by page type: homepage/contact use `source` only + dropdown `<select>` for service; service pages use `source` + hidden `service`; suburb pages use `source` + hidden `service` + hidden `landing` |
| Landing pages removed from sitemap | Done | Removed 3 `/landing/*.html` `<url>` entries from sitemap.xml. Added `Disallow: /landing/` to robots.txt. Resolves D09 inconsistency |

---

## Phase 12: Internal Removals Page — COMPLETE

| Item | Status | Notes |
|------|--------|-------|
| `northshore-removals.html` created | Done | Full service page with: hero, trust bar (155+ reviews, 1,500+ moves), 6 services (house moves, office relocations, furniture delivery, packing, piano/heavy items, short/long distance), sidebar (free quote, protective wrapping, experienced movers, transit insurance, no hidden fees, weekend availability), pricing callout ($170/hr weekday, 2 men & truck), placeholder gallery (6 items), 4-step process, 5 FAQ questions, CTA banner, dark contact section with Google rating (4.9, 155+ reviews), form with service=removals hidden field, removals-specific footer email + Instagram |
| index.html hero slide 3 updated | Done | Replaced "Get a Quote" button with "View Our Removals Page" link to northshore-removals.html (external "Learn More" CTA preserved) |
| index.html services #03 updated | Done | Added secondary "View our removals page" link below existing external "Explore removals" link |
| sitemap.xml updated | Done | Added northshore-removals.html entry with priority 0.9, lastmod 2026-03-20 |
| Nav/footer links unchanged | Done | External northshoreremovals.com links preserved in nav dropdown, mobile menu, and footer per plan |

---

## Phase 13: Phone-Frame Video Section + Gallery Enhancements — COMPLETE

| Item | Status | Notes |
|------|--------|-------|
| Phone-frame CSS component | Done | CSS-drawn iPhone mockup: 9/19.5 aspect ratio, dark bezel, notch, rounded corners, gold shadow accent. 280px mobile / 320px desktop. Added to `styles.css` |
| `tiling.html` video section | Done | Inserted between gallery/lightbox and process section. `<video>` with autoplay, muted, loop, playsinline. Source: `videos/North Shore Tiling Ashfield.MOV`. Dark background section with gold heading + caption |
| `index.html` teaser link | Done | "Watch our latest project" text link added below "Explore tiling" in services section (#01). Links to `tiling.html#video`. Subtle styling (smaller font, reduced opacity) |
| Cross-browser note | Done | HTML comment noting .MOV should ideally be converted to .mp4 for Chrome/Firefox compatibility |
| 60 new tiling photos added | Done | DSC06968–DSC07069 series copied from NSP-Tiling-Photos to `images/tiling/`. All 60 added to tiling.html gallery with `loading="lazy"` |
| Gallery arrow navigation | Done | Left/right arrow buttons + progress bar added to all 4 service pages (tiling, painting, cleaning, removals). CSS: gold-bordered circular buttons, gold progress bar. JS: smooth scroll 350px per click, disabled state at edges, progress bar tracks scroll position |

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
| ABN is placeholder | Medium | `12 345 678 901` is a dummy ABN — needs real ABN before launch |
| Aggregate ratings in schema | Medium | 4.9 stars / 87 reviews hardcoded in JSON-LD — need real review data or remove |
| Blog dates may be future-dated | Low | Blog posts dated Jan-Feb 2026 — verify these match desired publish schedule |
