# SEO: Crawling & Indexing

<rules>
1. **Canonicalization:** Every public-facing page MUST render a `<link rel="canonical" href="https://yourdomain.com/current-path" />` in the document `<head>` to prevent duplicate content penalties.
2. **Robots Directives:** If a page is dynamic user-state (e.g., `/dashboard`, `/cart`, `/settings`), automatically inject `<meta name="robots" content="noindex, nofollow" />`.
3. **Sitemap Automation:** Ensure new dynamic routes (like blog posts or product pages) are automatically appended to `sitemap.xml` with appropriate `<lastmod>` tags.
</rules>