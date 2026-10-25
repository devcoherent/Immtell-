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
