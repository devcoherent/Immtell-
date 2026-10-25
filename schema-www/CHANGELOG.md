# www canonical migration: schema change log

## Batch 1: static pages (applied 2026-10-25, not published)
- Location: Page Settings → Schema markup (jsonLdSchema) on 36 static pages
- Change: domain only, `https://immtell.com` → `https://www.immtell.com`. Paths, fragments and trailing slashes are unchanged.
- URLs updated: 918 (426 page/URL pairs; full list in batch1-static-pages-audit.csv)
- Verified: all 36 pages read back from the Webflow API match the prepared JSON exactly
  - 0 non-www URLs left
  - schema.org vocabulary and Google property checks give the same results as before
  - every @id reference resolves
- Untouched: sameAs (LinkedIn, Google Maps), CDN logo URLs, emails, other external URLs
- Skipped:
  - 16 pages with no schema setting (utility pages and CMS templates; CMS schema is handled in Batch 2)
  - 4 registered scripts that are not attached to any page
- Flagged, not changed:
  - "Business Services" breadcrumb (position 2) points to the home page on 5 /business/uk-immigration/* pages

## Batch 2: CMS schema fields (applied 2026-10-25, not published)
- Location: CMS field `schema-markup` (Resources, News, Topics, Case Studies, Team) and `structured-data` (Sectors)
- Items updated: 178 (Resources 111 incl. 1 draft, News 34, Topics 13, Sectors 13, Case Studies 5, Team 2)
- URLs updated: 1,943, domain only (`https://immtell.com` → `https://www.immtell.com`). Page-by-page list in batch2-cms-audit.csv
- Verified by independent read-back of all items:
  - 178/178 field values match the prepared versions exactly
  - all blocks are valid JSON
  - RichText embed wrapper is intact, with no `&quot;` escaping
  - 0 non-www URLs left in any schema field
  - each item's schema contains its own `https://www.immtell.com/<collection-path>/<slug>` URL
  - no other field changed, and no draft or archived status changed
- Skipped:
  - 12 archived News and 12 archived Case Studies (no schema, not live)
  - Testimonials, Events, News Topics, Resource Types and Case Study Sectors (no schema field)
- Flagged, not changed:
  - `/resources-pages/what-happens-during-a-home-office-compliance-audit` uses `#organisation` and `https://www.immtell.com/` instead of `#organization` and no slash
  - 16 Resources items use `/about/gavin-webster#person`; the rest of the site uses `/#gavin-webster`
  - `#website` is referenced but not defined on 2 Resources items (compliance-audit, uk-tourist-visitor-visa)

## Remaining non-www references outside schema
- Canonical tags: the 23 Oct crawl showed `<link rel="canonical" href="https://immtell.com/...">` on every page (54/54 crawled). These come from Webflow site settings, not page code. Set www as the default domain in Publishing and set Global canonical tag URL to `https://www.immtell.com` in SEO settings. The og:url fallback script in head copies the canonical, so it follows automatically.
- Resources `body` field (live), 2 hard-coded links:
  - `uk-visa-sponsorship-in-the-uk-care-sector` → https://immtell.com/resources-pages/home-office-sponsor-licence-holders-reporting-duties
  - `uk-business-residency-uk-self-sponsorship-and-expansion-worker-visas` → https://immtell.com/resources-pages/indefinite-leave-to-remain-ilr--permanent-residency-in-the-uk
- None found in: page SEO/OG fields, site or page custom code, other CMS fields, static page links in the crawl
- The 4 registered but unused scripts were not checked or changed: schemaapplysponsorlicence, immtell_schema_part_1, immtell_schema_part_2_faq, topicresourcecount

## Pages to test after publish (Rich Results Test + Schema Markup Validator)
Static:
- https://www.immtell.com/
- https://www.immtell.com/about
- https://www.immtell.com/contact-us
- https://www.immtell.com/business/uk-immigration/apply-for-a-sponsor-licence
- https://www.immtell.com/business/uk-immigration/uk-immigration-business-plans
- https://www.immtell.com/fees/sponsor-licence-application-fees
- https://www.immtell.com/individuals/settle-in-the-uk/indefinite-leave-to-remain
- https://www.immtell.com/resources/glossary
- https://www.immtell.com/resources/tool/civil-penalty-calculator
- https://www.immtell.com/testimonials

CMS (one or more per template):
- https://www.immtell.com/resources-pages/what-happens-during-a-home-office-compliance-audit
- https://www.immtell.com/resources-pages/home-office-contact-us
- https://www.immtell.com/resource-article/ihs-increase-delayed
- https://www.immtell.com/topics/buyer-commercial
- https://www.immtell.com/business/case-study/uk-immigration-support-for-an-international-consultancy
- https://www.immtell.com/business/sectors/healthcare
- https://www.immtell.com/about/gavin-webster

What to check on each:
- No errors
- `@id`s use www
- On News, check for any empty `ld+json` block (seen in the 23 Oct crawl)

## Follow-up fixes (applied 2026-10-25, not published)
1. `/resources-pages/what-happens-during-a-home-office-compliance-audit`:
   - `#organisation` → `#organization` (2 places)
   - Organization `url` `https://www.immtell.com/` → `https://www.immtell.com`
2. Gavin Webster `@id` unified to `https://www.immtell.com/about/gavin-webster#person` (was `/#gavin-webster`):
   - 81 references on 36 static pages
   - 112 references in 54 CMS items (News 34, Sectors 13, Case Studies 5, Team 2)
   - the 16 Resources items already used this @id
3. Added the standard WebSite node (`#website`) to 2 Resources items that referenced it without defining it:
   - compliance-audit
   - uk-tourist-visitor-visa (no `publisher` here, because that page has no Organization node)
4. Ewen McKenzie:
   - `@id` unified to `https://www.immtell.com/about/ewen-mckenzie#person` (was `/#ewen-mckenzie`; 13 references)
   - schema `jobTitle` and descriptions changed from "Head of Sponsor Compliance" to "Head of Compliance", to match the profile page hero, intro, FAQ and SEO description
   - affected: /about, /fees/compliance-audit-fees, /business/uk-immigration/protect-your-sponsor-licence, and Team items ewen-mckenzie and gavin-webster
- Verified by read-back:
  - fixes 1–3: 36/36 static and 56/56 CMS match exactly
  - fix 4: 3 pages and 2 Team items checked
  - no duplicate or unresolved @ids
  - 0 `#gavin-webster`, `#organisation` or `#ewen-mckenzie` left
- Skipped on request:
  - "Immtell Ltd" name / text identifier on the compliance-audit Organization node
  - missing `image` on NewsArticle/Article
- Page content (not schema) still says "Head of Sponsor Compliance" in the Team `role` field, the SEO title and the video caption/alt text
