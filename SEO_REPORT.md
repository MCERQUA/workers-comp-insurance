# SEO Report — workers-comp-insurance
Date: 2026-05-21

## 1. Site Identity
- **Framework**: Static HTML (single-page application)
- **Apparent domain/target audience**: Contractors Choice Agency — workers compensation insurance quote form for small-to-medium contractors in Arizona. Niche: insurance quote generation for construction/trade businesses.
- **Deployment status**: Git repository present with deploy keys (SSH-based deployment likely). No package.json, vercel.json, or netlify.toml detected.

## 2. Inventory
- **Total pages**: 1 HTML file (index.html)
- **URL structure**: Single-page flat structure (no subdirectories, no nested routes)
- **sitemap.xml present**: ❌ No
- **robots.txt present**: ❌ No

## 3. On-Page SEO (Single Page)

| Metric | Value |
|--------|-------|
| **Title tag** | "Workers Comp Insurance — Contractors Choice Agency" (57 chars) ✅ |
| **Title tag length** | Optimal (50–60 chars recommended) |
| **Meta description** | ❌ Missing |
| **Meta description length** | 0/160 chars ❌ Critical gap |
| **H1** | "WORKERS COMP INSURANCE" (22 chars, properly unique) ✅ |
| **H2–H6** | Only section labels (`.section-label`) with text like "Business Information", "Owner Information" etc. (not semantic headings) ⚠️ |
| **Canonical tag** | ❌ Missing |
| **OG tags** | ❌ All missing (og:title, og:description, og:image, og:url) |
| **Viewport** | ✅ Present and correct |
| **Language** | ✅ `lang="en"` declared |

**Issues found**:
- No meta description tag at all
- No canonical tag (essential for single-page sites to clarify indexing intent)
- No Open Graph tags (affects social sharing and previews)
- Section labels styled as `.section-label` but not semantic `<h2>` elements

## 4. Structured Data
- **JSON-LD present**: ❌ No structured data found
- **Schema.org types**: None
- **Missing opportunities**:
  - `LocalBusiness` (company address, phone, email all present in footer)
  - `Organization` (name, contact info)
  - `ContactPoint` (for service inquiry form)
  - `WebPage` (for page-level metadata)

## 5. Content Quality
- **Total word count (visible text)**: ~1,321 words ✅ Adequate for a conversion form
- **Word count breakdown**:
  - Hero section: ~8 words
  - Form labels & helpers: ~200 words
  - Footer: ~25 words
  - Form placeholders: ~100 words
- **Internal linking density**: 0 internal links (only tel: and mailto: links in header/footer)
- **Image count**: 0 images
- **Alt-text coverage**: N/A (no images)
- **Content depth**: Form-focused; minimal explanatory/educational content. No benefits section, testimonials, or FAQs.

## 6. Technical
- **robots.txt**: ❌ Missing (no crawl directives; site will be indexed by default)
- **Sitemap**: ❌ Not present (unnecessary for single page, but good practice)
- **404 handling**: ⚠️ Unknown (depends on server configuration)
- **Redirects/Headers**: None detected (static HTML has no config)
- **Mobile responsiveness**: ✅ Viewport meta present; media query for mobile at 480px breakpoint
- **CSS**: Inline styles only (1321 lines of style in `<style>` block) — no external stylesheet
- **JavaScript**: Inline (form handling, owner management logic embedded)
- **Load performance signals**: All resources inline (no render-blocking external assets) ✅

## 7. Top Issues (Ranked by Priority)

| # | Issue | File:Line | Impact |
|---|-------|-----------|--------|
| 1 | **Missing meta description** | index.html: after line 4 | Critical. Reduces CTR in SERPs; search engines will scrape content instead. |
| 2 | **No structured data (JSON-LD)** | index.html: entire document | High. Missing rich snippets opportunity; LocalBusiness schema not declared. |
| 3 | **No canonical tag** | index.html: `<head>` | Medium. Without canonical, pagination or variations could fragment SEO value. |
| 4 | **No robots.txt** | (not found) | Medium. Best practice; allows explicit crawl rules (e.g., noindex test pages). |
| 5 | **No Open Graph tags** | index.html: `<head>` | Medium. Social sharing will show no preview image/description. |
| 6 | **Missing sitemap.xml** | (not found) | Low. Single-page site, but useful for announcing to search engines. |
| 7 | **Semantic heading hierarchy** | index.html: lines 259, 279, 301, 321, 336, 351 | Low-Medium. Section labels use `.section-label` divs instead of `<h2>` tags. |
| 8 | **No educational content** | index.html: entire document | Medium. Form-only design misses keyword opportunities (e.g., "workers comp insurance for contractors", "how to get WC quote"). |
| 9 | **Form accessibility labels** | index.html: lines 262–361 | Low. Labels are present and properly associated; good accessibility. ✅ |
| 10 | **No favicon/brand assets** | (not found) | Low. Browser tab will show generic page indicator. |

## 8. Top Recommendations (Concrete Next Actions)

1. **Add meta description** (line 5, after viewport):
   ```html
   <meta name="description" content="Get workers compensation insurance quotes in 15 minutes for your contracting business. Insure roofing, HVAC, plumbing, and more. Free quote from Contractors Choice Agency.">
   ```
   *Rationale*: Drives CTR; summarizes value prop in 155 chars.

2. **Add JSON-LD LocalBusiness schema** (before `</head>`):
   ```json
   {
     "@context": "https://schema.org",
     "@type": "LocalBusiness",
     "name": "Contractors Choice Agency",
     "address": "12220 E Riggs Rd, Chandler, AZ 85249",
     "telephone": "844-967-5247",
     "email": "josh@contractorschoiceagency.com",
     "areaServed": "US",
     "description": "Workers compensation insurance for contractors",
     "url": "https://[your-domain]"
   }
   ```
   *Rationale*: Enables local knowledge panel; adds credibility signals.

3. **Add canonical tag** (line 6, after title):
   ```html
   <canonical href="https://[your-domain]/index.html">
   ```
   *Rationale*: Clarifies primary version if domain has www/non-www variants.

4. **Add Open Graph tags** (lines 5–8):
   ```html
   <meta property="og:title" content="Workers Comp Insurance — Get a Quote in 15 Minutes">
   <meta property="og:description" content="Free workers compensation quotes for roofing, HVAC, plumbing contractors.">
   <meta property="og:type" content="website">
   <meta property="og:url" content="https://[your-domain]">
   ```
   *Rationale*: Improves social sharing appearance.

5. **Create robots.txt** (at domain root):
   ```
   User-agent: *
   Allow: /
   Sitemap: https://[your-domain]/sitemap.xml
   ```
   *Rationale*: Explicitly allows crawling; announces sitemap.

6. **Replace `.section-label` divs with semantic `<h2>` tags**:
   - Lines 260, 279, 301, 321, 336, 351: Change from `<div class="section-label">` to `<h2 class="section-label">`
   - *Rationale*: Improves heading hierarchy; helps screen readers and SEO bots understand page structure.

7. **Create a sitemap.xml** (single entry, optional but recommended):
   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
     <url>
       <loc>https://[your-domain]/</loc>
       <lastmod>2026-05-21</lastmod>
       <priority>1.0</priority>
     </url>
   </urlset>
   ```

8. **Add educational content** (optional but high-value):
   - Add a brief FAQ section or blog link addressing:
     - "What does workers compensation insurance cover?"
     - "Why contractors need WC insurance"
     - "How we calculate your rate"
   - *Rationale*: Targets long-tail keywords; improves engagement; establishes authority.

---

## Summary

**SEO Health**: ⚠️ **Needs Work** — The site ranks on basic HTML structure and a clear title, but critical on-page metadata is missing (meta description, structured data, canonical). Social sharing will not preview correctly. Site will be indexed, but lacks signals for rich snippets and local prominence.

**Headline Finding**: Meta description missing; no structured data; no semantic heading hierarchy — fixes recommended before scaling traffic.

---

## 9. Structured Data Update — 2026-05-21

**Files changed**:
- `index.html` — added `<script type="application/ld+json">` block before `</head>` (single `@graph` payload, three nodes).

**Schema types added**:
- `InsuranceAgency` (`@id: #agency`) — name, description, telephone (+1-844-967-5247), email, full `PostalAddress` (12220 E Riggs Rd, Chandler, AZ 85249, US), `knowsAbout: ["workers compensation insurance"]`, `areaServed: State/Arizona`.
- `WebSite` (`@id: #website`) — name, description, `publisher` linked to `#agency`.
- `Service` — `serviceType: "Workers Compensation Insurance"`, name, description, `provider` linked to `#agency`, `areaServed: State/Arizona`.

**Not added**:
- `FAQPage` — page has no FAQ content; would require fabricating Q&A copy.
- Reviews / `aggregateRating` — no review data present on the page.

**Validation**: JSON parsed clean via `json.loads`; three `@graph` nodes resolved with expected `@type` values.

**Remaining gaps from §7 still open**: meta description, canonical, OG tags, robots.txt, sitemap.xml, semantic H2 promotion.
