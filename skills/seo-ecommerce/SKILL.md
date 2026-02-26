---
title: Ecommerce SEO
description: Best practices for ecommerce URL structures, pagination, faceted navigation, and Product structured data.
version: 1.0.0
---

# SEO: Ecommerce Operations

## When to use
Use this skill when:
- Designing or modifying URL structures for products, categories, or filters.
- Implementing product variations (colors, sizes, etc.).
- Building pagination, "Load More" buttons, or infinite scroll for product grids.
- Creating faceted navigation or filtering systems.
- Implementing structured data for single products or grouped products (variants).

## Inputs required
- The product catalog structure and how variants are handled.
- The pagination UX (numbered pages, infinite scroll, load more).
- The filtering/sorting parameters used by the store.
- Pricing, reviews, and availability data for schema markup.

## Procedure

### 1. URL Structure for Products and Variants
Google needs clear, static-looking URLs to understand ecommerce catalogs.

- Use descriptive words in URLs, not just IDs.
- Use `?key=value` for parameters, not just `?value`.
- Avoid temporary parameters (session IDs, timestamps) in crawlable links.

```html
<!-- ✅ CORRECT: Descriptive path -->
<a href="/products/mens-running-shoes">Running Shoes</a>

<!-- ❌ WRONG: Non-descriptive, parameter-only, or multi-value -->
<a href="/products/1234">Running Shoes</a>
<a href="/products/shoes?green">Green Shoes</a>
<a href="/products?type=shoes&type=green">Green Shoes</a>
```

#### Handling Product Variants (e.g., Colors, Sizes)
Make every variant accessible via a unique URL so Google can index specific colors/sizes.

```html
<!-- ✅ Strategy A: Path segment -->
<a href="/products/classic-t-shirt/green">Green T-Shirt</a>

<!-- ✅ Strategy B: Query parameter -->
<a href="/products/classic-t-shirt?color=green">Green T-Shirt</a>
```

If using query parameters for variants, Google recommends setting the canonical URL to the base product URL (omitting the query parameter) to consolidate indexing signals.

### 2. Pagination Best Practices
Google must be able to crawl deeply into product categories.

- **Must use `<a href>`:** Googlebot does not click buttons or trigger JavaScript. You must provide real links to the next page.
- **Sequential Linking:** Link page 1 to page 2, page 2 to page 3, etc.
- **Unique URLs:** Use `?page=n` to give each page a unique URL.
- **Do NOT canonicalize to page 1:** Every paginated URL must have a self-referencing canonical tag.
- **Never use URL fragments (`#page2`):** Google ignores everything after the hash.

```html
<!-- ✅ CORRECT: True links for pagination -->
<nav class="pagination">
  <a href="/category/shoes?page=1">1</a>
  <a href="/category/shoes?page=2">2</a>
  <a href="/category/shoes?page=3" rel="next">Next</a>
</nav>

<!-- ❌ WRONG: Uncrawlable JavaScript pagination -->
<button onclick="loadPage(2)">Load More</button>
<div onscroll="infiniteScroll()">...</div>
<a href="#page2">Page 2</a>
```

> **Note on Infinite Scroll:** If using infinite scroll, you MUST implement the History API to update the URL to `?page=n` as the user scrolls, AND provide `<a href="?page=2">` fallback links in the DOM for crawlers.

### 3. Faceted Navigation and Crawl Budget
Ecommerce filters (price sorting, size, brand) can create infinite URL combinations, draining Google's crawl budget and causing duplicate content issues.

Avoid indexing URLs with filters or alternative sort orders.

```html
<!-- An unfiltered category page (Indexable) -->
<link rel="canonical" href="https://store.com/category/shoes" />
<meta name="robots" content="index, follow" />

<!-- A filtered/sorted category page (Do not index) -->
<!-- https://store.com/category/shoes?sort=price_low&size=10 -->
<meta name="robots" content="noindex, follow" />
```

Alternatively, use `robots.txt` to block parameter crawling:
```text
# robots.txt
User-agent: *
Disallow: /*?sort=
Disallow: /*&size=
```

### 4. Product Structured Data
To get product rich results (price, rating, availability in SERPs), you must include `Product` structured data.

See the dedicated [Product Schema Reference](references/product-schema.md) for full JSON-LD templates covering:
- Single Products with Offers and Reviews
- `ProductGroup` for parent products with multiple variants

## Verification
- **URL Inspection:** Verify variant URLs resolve and have the correct canonical tag.
- **Pagination Crawlability:** Disable JavaScript in the browser. Confirm you can still navigate to page 2, 3, etc., using standard `href` links.
- **Canonical Check:** Verify `?page=2` has a canonical tag pointing to `?page=2`, NOT page 1.
- **Facet Indexing Check:** Verify filter combinations (e.g., `?color=red&size=large`) contain a `noindex` tag or are blocked in robots.txt.
- **Rich Results Test:** Run product pages through [search.google.com/test/rich-results](https://search.google.com/test/rich-results) to validate schema.

## Failure modes / debugging
| Problem | Cause | Fix |
|---|---|---|
| Deep products not indexed | Pagination relies on JS `onclick` or infinite scroll without hrefs | Add `<a>` tags with `href="?page=n"` alongside JS logic |
| "Duplicate, Google chose different canonical than user" | Variants use query params but self-canonicalize | Aim canonicals for variant query params (e.g. `?color=red`) back to the base URL |
| Millions of excluded URLs in GSC | Search facets (filters/sorts) are being crawled | Add `noindex` to filtered views or block parameters in `robots.txt` |
| Missing price in search results | Invalid or missing `Product` > `Offer` schema | Fix JSON-LD according to schema guidelines |

## Escalation
- If faceted navigation generates millions of indexable pages and crawl budget is exhausted, escalate to a Technical SEO to design a comprehensive parameter handling strategy.
- For complex `ProductGroup` schema mapping with headless variants, consult the backend team to ensure inventory data aligns with structured data requirements.

### References
- [Google: SEO Best Practices for Ecommerce](https://developers.google.com/search/docs/specialty/ecommerce)
- [Google: Designing a URL structure for ecommerce](https://developers.google.com/search/docs/specialty/ecommerce/designing-a-url-structure-for-ecommerce-sites)
- [Google: Pagination & incremental loading](https://developers.google.com/search/docs/specialty/ecommerce/pagination-and-incremental-page-loading)
