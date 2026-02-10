# North Shore Projects — Website Documentation

## Business
- **Name:** North Shore Projects
- **Domain:** https://northshoreprojects.com.au
- **Services:** Tiling, Painting, Cleaning (Removals via external partner)
- **Area:** North Shore Sydney, NSW, Australia
- **Phone:** 0433 333 332
- **Emails (service-specific):**
  - Tiling: northshoretiling8@gmail.com
  - Painting: northshorepainting88@gmail.com
  - Cleaning: northshorecleaning8@gmail.com
  - General pages default to: northshoretiling8@gmail.com
- **ABN:** 12 345 678 901
- **Hours:** Mon–Sat 7am–6pm

## Project Structure

```
/
├── index.html                  # Homepage
├── tiling.html                 # Tiling service page
├── painting.html               # Painting service page
├── cleaning.html               # Cleaning service page
├── contact.html                # Contact / enquiry page
├── sitemap.xml                 # XML sitemap (all pages)
├── robots.txt                  # Crawler directives
├── CLAUDE.md                   # This file
│
├── css/
│   ├── styles.css              # Full design system CSS
│   └── styles.min.css          # Minified CSS (used in all HTML)
│
├── images/                     # Image assets (placeholder references)
│   └── (images to be added)
│
├── suburbs/                    # 51 suburb landing pages (17 suburbs × 3 services)
│   ├── tiling-{suburb}.html    # 17 tiling suburb pages
│   ├── painting-{suburb}.html  # 17 painting suburb pages
│   └── cleaning-{suburb}.html  # 17 cleaning suburb pages
│
├── blog/
│   ├── index.html                          # Blog listing page
│   ├── how-to-choose-bathroom-tiles.html   # Tiling guide
│   ├── interior-painting-tips.html         # Painting tips
│   ├── end-of-lease-cleaning-checklist.html # Cleaning checklist
│   ├── kitchen-splashback-trends.html      # Splashback trends 2026
│   └── how-often-repaint-house.html        # Repainting guide
│
├── landing/                    # Meta Ads landing pages (conversion-optimized)
│   ├── tiling.html
│   ├── painting.html
│   └── cleaning.html
│
└── src/                        # Next.js source (original scaffold, not used for static site)
    └── app/
```

## Suburbs Covered (17)
Chatswood, Killara, Gordon, Pymble, Turramurra, Lindfield, Roseville, St Ives, Wahroonga, Lane Cove, Willoughby, Artarmon, Crows Nest, North Sydney, Neutral Bay, Mosman, Cremorne

## Suburb Page Naming Convention
`suburbs/{service}-{suburb-slug}.html`
- Slugs use lowercase with hyphens: `st-ives`, `north-sydney`, `crows-nest`, `lane-cove`

## Design System
- **Primary colour:** #1a1a2e (dark navy)
- **Gold accent:** #D4A853
- **Heading font:** Montserrat (Google Fonts)
- **Body font:** Open Sans (Google Fonts)
- **Icons:** Font Awesome 6.5.1 (CDN)
- **Approach:** Mobile-first responsive CSS

## SEO Implementation
- Unique `<title>` and `<meta description>` on every page
- JSON-LD structured data on every page (LocalBusiness + Service/Article schemas)
- Open Graph and Twitter Card tags on every page
- Canonical URLs on every page
- hreflang="en-AU" on every page
- Sitemap XML with all 65+ pages
- robots.txt with sitemap reference
- Proper heading hierarchy (single H1 per page)
- Descriptive alt text on all images
- aria-labels on interactive elements

## Tracking Placeholders
All pages include:
- `<!-- GOOGLE TAG MANAGER -->` in `<head>`
- `<!-- GTM NOSCRIPT -->` after opening `<body>`
- `window.dataLayer.push()` on form submission
- `// CONVERSION TRACKING - fire GTM event here` comment

Landing pages additionally include:
- `<!-- META PIXEL CODE HERE -->` in `<head>`
- Hidden field `source=meta-ad` on forms

## Form Structure
All enquiry forms POST to `/api/contact` with fields:
- name, email, phone, service, suburb, message
- Hidden `source` field (organic / meta-ad)
- dataLayer push on submission: `{event: 'form_submission', service, source}`

## Internal Linking Strategy
- Homepage → all 3 service pages, blog, key suburb pages
- Service pages → 17 suburb pages for that service, relevant blog posts
- Suburb pages → main service page, homepage, 2-3 nearby suburb pages, blog
- Blog posts → relevant service page, 1-2 suburb pages
- Footer → services, 6 popular suburb pages, blog

## To-Do (Not Yet Implemented)
- [ ] Add actual images to /images/ folder
- [ ] Configure Google Tag Manager container
- [ ] Install Meta Pixel
- [ ] Set up form backend (/api/contact endpoint)
- [ ] Configure Google My Business
- [ ] Submit sitemap to Google Search Console
- [ ] Set up Google Ads conversion tracking
- [ ] Add actual Google Map embed on contact page
- [ ] Create privacy.html and terms.html pages
- [ ] Add favicon and apple-touch-icon
- [ ] Remove landing pages from sitemap.xml
- [ ] Add `Disallow: /landing/` to robots.txt
- [ ] Replace placeholder ABN with real ABN
- [ ] Replace placeholder aggregate ratings with real review data
- [ ] Standardise hidden field names (`landing` vs `suburb_page`) across suburb pages
- [ ] Minify form-validation.js for production

---

## File Tracking Protocol

This project maintains two tracking files that must be kept current across all sessions:

### `progress.md`
- **Purpose:** Tracks what has been built, what remains, and known issues
- **When to update:** After completing any feature, fixing a bug, or discovering a new issue
- **Structure:** Phased checklist (Done/Remaining/Known Issues tables)

### `decisions.md`
- **Purpose:** Logs every significant architectural or design decision with rationale
- **When to update:** When making a non-trivial choice (new technology, structural change, naming convention, etc.)
- **Structure:** Numbered entries (D01, D02...) with Decision, Rationale, and Trade-offs
- **Next ID:** D18

### Rules for All Sessions
1. **Read both files at the start** of any session that involves code changes
2. **Update `progress.md`** whenever you complete a task, discover a bug, or add something to the remaining work list
3. **Add to `decisions.md`** whenever you make a choice that a future developer would want to understand (use the next available D-number)
4. **Never delete decision entries** — if a decision is reversed, add a new entry explaining the reversal and reference the original
5. **Keep `progress.md` timestamps current** — update the "Last updated" date at the top
