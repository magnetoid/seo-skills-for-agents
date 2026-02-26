# Universal SEO Agent Skills

Expert-level SEO knowledge for AI coding assistants — semantic HTML, Core Web Vitals, structured data, JavaScript SEO, and modern search optimization.

Instead of fighting your AI when it writes bad, un-crawlable HTML, these skills force it to act as an **Expert Technical SEO**.

## Available Skills

| Skill | Directory | Description |
|---|---|---|
| **Core HTML & Architecture** | `skills/seo-core-html/` | Semantic HTML, crawlable links, heading hierarchy, `data-nosnippet` |
| **Crawling & Indexing** | `skills/seo-crawling-indexing/` | Canonical tags, robots directives, sitemaps, link qualification, snippet controls |
| **Schema & Snippets** | `skills/seo-schema-snippets/` | JSON-LD structured data, Featured Snippets, WebSite schema, sitelinks |
| **AI Crawlers & Citations** | `skills/seo-llm-context/` | `llms.txt`, semantic citations, markdown fallbacks |
| **Performance & Core Web Vitals** | `skills/seo-performance/` | LCP, CLS, INP optimization, font loading, resource hints |
| **Meta Tags & Open Graph** | `skills/seo-meta-tags/` | Title tags, meta descriptions, OG, Twitter Cards, favicon, site name |
| **URL Structure & Internal Linking** | `skills/seo-url-structure/` | Clean URLs, breadcrumbs, pagination, redirects |
| **International SEO** | `skills/seo-international/` | Hreflang tags, locale URLs, multilingual sitemaps |
| **Accessibility** | `skills/seo-accessibility/` | ARIA roles, skip navigation, focus management |
| **JavaScript SEO** | `skills/seo-javascript/` | SPA rendering, History API, soft 404s, Web Components, fingerprinting |
| **Image & Video SEO** | `skills/seo-media/` | Image optimization, responsive images, VideoObject schema, media sitemaps |

## Quick Start

Simply copy the entire contents of this repository into the root of your web project. Your AI coding assistant will automatically detect its specific instruction file and enforce the SEO skills.

### Supported AI IDEs

| IDE | Config File |
|---|---|
| Cursor | `.cursorrules` |
| Windsurf | `.windsurfrules` |
| Trae.ai | `.traerules` |
| Claude Code | `.clauderules` |
| GitHub Copilot | `.github/copilot-instructions.md` |

## How It Works

Each skill contains a standardized `SKILL.md` with:

- **When to use** — Conditions that trigger the skill
- **Inputs required** — What the AI needs to gather first
- **Procedure** — Step-by-step instructions with code examples
- **Verification** — How to confirm correct implementation
- **Failure modes** — Common mistakes and how to fix them
- **Escalation** — When to ask a human for help

Some skills also include a `references/` directory with deep-dive documentation on specific topics.

## Project Structure

```
├── .cursorrules                    # Cursor IDE instructions
├── .windsurfrules                  # Windsurf IDE instructions
├── .traerules                      # Trae.ai instructions
├── .clauderules                    # Claude Code instructions
├── .github/
│   └── copilot-instructions.md     # GitHub Copilot instructions
├── skills/
│   ├── seo-core-html/
│   │   ├── SKILL.md
│   │   └── references/
│   ├── seo-crawling-indexing/
│   │   ├── SKILL.md
│   │   └── references/
│   ├── seo-schema-snippets/
│   │   ├── SKILL.md
│   │   └── references/
│   ├── seo-llm-context/
│   │   ├── SKILL.md
│   │   └── references/
│   ├── seo-performance/
│   │   └── SKILL.md
│   ├── seo-meta-tags/
│   │   └── SKILL.md
│   ├── seo-url-structure/
│   │   └── SKILL.md
│   ├── seo-international/
│   │   └── SKILL.md
│   ├── seo-accessibility/
│   │   └── SKILL.md
│   ├── seo-javascript/
│   │   └── SKILL.md
│   └── seo-media/
│       └── SKILL.md
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

## Sources

Skills are built from official documentation, including:
- [Google Search Central](https://developers.google.com/search/docs) — Crawling, indexing, structured data, JavaScript SEO
- [Schema.org](https://schema.org/) — Structured data vocabularies
- [web.dev](https://web.dev/) — Core Web Vitals and performance
- [W3C WAI](https://www.w3.org/WAI/) — Accessibility standards

## Contributing

We welcome contributions! Whether you're an SEO expert, web developer, or AI enthusiast, you can help improve these skills.

See [CONTRIBUTING.md](CONTRIBUTING.md) for details on how to get started.

## License

[MIT](LICENSE)
