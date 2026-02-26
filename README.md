# Universal SEO Agent Rules

A standardized set of instructions (skills) that teach AI coding assistants how to write code that perfectly aligns with modern SEO best practices. 

Instead of fighting your AI when it writes bad, un-crawlable HTML, these rules force it to act as an Expert Technical SEO.

## Supported AI IDEs
* Cursor (`.cursorrules`)
* Windsurf (`.windsurfrules`)
* Trae.ai (`.traerules`)
* Claude Code (`.clauderules`)
* GitHub Copilot (`.github/copilot-instructions.md`)

## How to Use
Simply copy the entire contents of this repository into the root of your web project. Your vibe coding IDE of choice will automatically detect its specific instruction file, which points it to the core rules in the `seo-rules/` directory.

## What it Enforces
1. **Core HTML & Architecture:** Forces semantic tags and crawlable links.
2. **Crawling & Indexing:** Automates canonicals and robots directives.
3. **Schema & Snippets:** Teaches the AI to write JSON-LD and optimize for Featured Snippets.
4. **AI Crawlers & Citations:** Rules for LLM optimization (like `llms.txt` and semantic citations).
