---
title: SEO International & i18n
description: Rules for implementing hreflang tags, locale-aware URLs, and multilingual sitemaps.
version: 1.0.0
---

# SEO: International & i18n

## When to use
Use this skill when:
- Building a multilingual or multi-region website.
- Adding language/locale variants of existing pages.
- Configuring `hreflang` tags for search engine localization.
- Generating multilingual XML sitemaps.

## Inputs required
- Target languages and regions (e.g., `en-US`, `es-ES`, `fr-FR`).
- URL strategy: subdirectories (`/en/`), subdomains (`en.example.com`), or separate domains.
- Whether content is fully translated or partially localized.

## Procedure

### 1. Hreflang Tags
- Add `<link rel="alternate" hreflang="...">` tags in `<head>` for every language variant.
- Include a self-referencing hreflang tag for the current page.
- Always include an `x-default` fallback.

```html
<!-- On the English page: /en/about -->
<head>
  <link rel="alternate" hreflang="en" href="https://example.com/en/about" />
  <link rel="alternate" hreflang="es" href="https://example.com/es/about" />
  <link rel="alternate" hreflang="fr" href="https://example.com/fr/about" />
  <link rel="alternate" hreflang="x-default" href="https://example.com/en/about" />
</head>
```

### 2. URL Structure
- Use subdirectories for most sites (simplest to manage and best for SEO consolidation).
- Ensure the `<html lang="...">` attribute matches the page's language.

```html
<!-- English page -->
<html lang="en">

<!-- Spanish page -->
<html lang="es">
```

| Strategy | Example | Best For |
|---|---|---|
| Subdirectories | `example.com/en/`, `example.com/es/` | Most sites, single domain authority |
| Subdomains | `en.example.com`, `es.example.com` | Large teams with separate infrastructure |
| Separate domains | `example.com`, `example.es` | Strong local brand presence needed |

### 3. Multilingual Sitemaps
- Include `xhtml:link` elements for each language variant in the sitemap.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9"
        xmlns:xhtml="http://www.w3.org/1999/xhtml">
  <url>
    <loc>https://example.com/en/about</loc>
    <xhtml:link rel="alternate" hreflang="en" href="https://example.com/en/about" />
    <xhtml:link rel="alternate" hreflang="es" href="https://example.com/es/about" />
    <xhtml:link rel="alternate" hreflang="fr" href="https://example.com/fr/about" />
  </url>
  <url>
    <loc>https://example.com/es/about</loc>
    <xhtml:link rel="alternate" hreflang="en" href="https://example.com/en/about" />
    <xhtml:link rel="alternate" hreflang="es" href="https://example.com/es/about" />
    <xhtml:link rel="alternate" hreflang="fr" href="https://example.com/fr/about" />
  </url>
</urlset>
```

### 4. Content Considerations
- Never auto-redirect based on IP/geo without user consent.
- Provide a visible language switcher.
- Translate meta titles and descriptions — don't just translate body content.

## Verification
- **Hreflang validation:** Use [Aleyda Solis' Hreflang Generator](https://www.aleydasolis.com/english/international-seo-tools/hreflang-tags-generator/) to validate tags.
- **Search Console:** Check the International Targeting report in Google Search Console.
- **Sitemap check:** Verify multilingual sitemaps include `xhtml:link` elements.
- **HTML lang check:** Confirm `<html lang="...">` matches the page's content language.

## Failure modes / debugging
| Problem | Cause | Fix |
|---|---|---|
| Wrong language version ranking | Missing or incorrect hreflang tags | Add bidirectional hreflang tags for all language pairs |
| "Duplicate content" across languages | Missing hreflang `x-default` | Add `x-default` hreflang pointing to the primary/fallback version |
| Users forced to wrong locale | Auto-redirect based on IP | Use a banner/prompt instead of forced redirect |
| Missing translations in SERPs | Meta title/description not translated | Translate all `<title>` and `<meta description>` tags |

## Escalation
- If the site requires regional pricing, currency, or legal content differences, consult a localization specialist.
- If hreflang conflicts arise from CMS plugins, escalate to the CMS admin.
