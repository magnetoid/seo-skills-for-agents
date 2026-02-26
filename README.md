<div align="center">

# 🚀 SEO Skills for AI Agents

**Expert-level SEO knowledge for AI coding assistants.**

Semantic HTML · Core Web Vitals · Structured Data · JavaScript SEO · Ecommerce · International

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Skills](https://img.shields.io/badge/Skills-12-brightgreen.svg)](#-available-skills)
[![Google Aligned](https://img.shields.io/badge/Google%20Search%20Central-Aligned-4285F4.svg)](https://developers.google.com/search/docs)

*Built by [IMBA Marketing](https://imbamarketing.com)*

---

**Stop fighting your AI when it writes bad, un-crawlable HTML.**<br>
These skills force your AI coding assistant to act as an **Expert Technical SEO** — every time.

</div>

## ⚡ Quick Install

### Option 1: Clone directly into your project

```bash
git clone https://github.com/magnetoid/seo-skills-for-agents.git .seo-skills
cp -r .seo-skills/skills ./skills
cp .seo-skills/.cursorrules ./.cursorrules
# Copy whichever IDE config you use (see table below)
```

### Option 2: Git submodule (keeps it updatable)

```bash
git submodule add https://github.com/magnetoid/seo-skills-for-agents.git seo-skills
```

### Option 3: One-liner download

```bash
# Download and extract into current directory
curl -sL https://github.com/magnetoid/seo-skills-for-agents/archive/main.tar.gz | tar xz --strip-components=1
```

### Option 4: Manual copy

Download this repository and copy the `skills/` directory + your IDE config file into the root of your web project. Your AI assistant will automatically detect and enforce the SEO skills.

---

## 🎯 Supported AI IDEs

| IDE | Config File | Auto-detected? |
|---|---|---|
| **Cursor** | `.cursorrules` | ✅ |
| **Windsurf** | `.windsurfrules` | ✅ |
| **Trae.ai** | `.traerules` | ✅ |
| **Claude Code** | `.clauderules` | ✅ |
| **GitHub Copilot** | `.github/copilot-instructions.md` | ✅ |

---

## 📦 Available Skills

| # | Skill | Key Topics |
|---|---|---|
| 1 | **Core HTML & Architecture** | Semantic HTML, crawlable `<a href>` links, heading hierarchy, `data-nosnippet` |
| 2 | **Crawling & Indexing** | Canonicals, robots directives, sitemaps, `rel=nofollow/sponsored/ugc`, snippet controls |
| 3 | **Schema & Rich Snippets** | JSON-LD structured data, `WebSite` schema, sitelinks search box, `VideoObject` |
| 4 | **AI Crawlers & Citations** | `llms.txt`, semantic citations, Markdown fallbacks for LLM crawlers |
| 5 | **Performance & Core Web Vitals** | LCP, CLS, INP optimization, font loading, `fetchpriority`, resource hints |
| 6 | **Meta Tags & Open Graph** | Title tags, meta descriptions, OG, Twitter Cards, favicon, site name, dates |
| 7 | **URL Structure & Internal Linking** | Clean URLs, breadcrumbs, pagination, redirects, internal link architecture |
| 8 | **International & Multilanguage** | Hreflang (HTML/HTTP/sitemap), geotargeting, locale-adaptive pages, ISO codes |
| 9 | **Accessibility** | ARIA roles, skip navigation, focus management, media accessibility |
| 10 | **JavaScript SEO** | SPA rendering pipeline, History API, soft 404s, Web Components, fingerprinting |
| 11 | **Image & Video SEO** | WebP/AVIF, responsive `<picture>`, `VideoObject` schema, media sitemaps |
| 12 | **Ecommerce SEO** | Product URLs, variants, pagination, faceted nav, Merchant Center, Product schema |

---

## 🧠 How It Works

Each skill contains a standardized `SKILL.md` with **6 actionable sections**:

```
┌─────────────────┐
│  When to use     │ ← Conditions that trigger the skill
├─────────────────┤
│  Inputs required │ ← What the AI needs to gather first
├─────────────────┤
│  Procedure       │ ← Step-by-step rules with code examples
├─────────────────┤
│  Verification    │ ← How to confirm correct implementation
├─────────────────┤
│  Failure modes   │ ← Common mistakes and how to fix them
├─────────────────┤
│  Escalation      │ ← When to ask a human for help
└─────────────────┘
```

Some skills also include a `references/` directory with copy-pasteable JSON-LD templates and deep-dive docs.

---

## 📂 Project Structure

```
seo-skills-for-agents/
├── .cursorrules                     # Cursor IDE
├── .windsurfrules                   # Windsurf IDE
├── .traerules                       # Trae.ai
├── .clauderules                     # Claude Code
├── .github/copilot-instructions.md  # GitHub Copilot
├── skills/
│   ├── seo-core-html/               # + references/
│   ├── seo-crawling-indexing/        # + references/
│   ├── seo-schema-snippets/          # + references/
│   ├── seo-llm-context/             # + references/
│   ├── seo-performance/
│   ├── seo-meta-tags/
│   ├── seo-url-structure/
│   ├── seo-international/
│   ├── seo-accessibility/
│   ├── seo-javascript/
│   ├── seo-media/
│   └── seo-ecommerce/               # + references/
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

---

## 📚 Sources

All skills are grounded in official documentation:

| Source | Topics Covered |
|---|---|
| [Google Search Central](https://developers.google.com/search/docs) | Crawling, indexing, structured data, JavaScript SEO, ecommerce |
| [Schema.org](https://schema.org/) | Structured data vocabularies |
| [web.dev](https://web.dev/) | Core Web Vitals, performance, rendering |
| [W3C WAI](https://www.w3.org/WAI/) | Accessibility standards |

---

## 🤝 Contributing

We welcome contributions! Whether you're an SEO expert, web developer, or AI enthusiast — you can help improve these skills or add new ones.

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on skill structure and submission workflow.

---

## 🏢 About

This project is maintained by **[IMBA Marketing](https://imbamarketing.com)** — a digital marketing agency specializing in SEO, performance, and AI-driven growth strategies.

## 📄 License

[MIT](LICENSE) — use freely in personal and commercial projects.
