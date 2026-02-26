# SEO: Core HTML & Architecture Standards

<rules>
1. **Strict Semantic HTML:** Use `<article>`, `<section>`, `<nav>`, and `<aside>`. Never use generic `<div>` wrappers for meaningful content. Search engines rely on these landmarks to understand page topography.
2. **Crawlable Navigation:** All links MUST be standard `<a>` tags with resolvable `href` attributes. Do not use Javascript-only routing (e.g., `onClick={navigate}`) for internal links, as crawlers cannot easily follow them.
3. **Heading Integrity:** Enforce a strict `H1 -> H2 -> H3` structure. Every page must have exactly one `<h1>`. Never skip heading levels for styling purposes.
4. **Media SEO:** Every `<Image>` or `<img>` must have `alt` text describing the image. Use `loading="lazy"` for below-the-fold images and `fetchpriority="high"` for the primary above-the-fold image to optimize Core Web Vitals.
</rules>