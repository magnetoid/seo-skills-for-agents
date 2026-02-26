# Advanced SEO: AI Crawlers & Citations

<rules>
1. **LLM Root Files:** Maintain a `public/llms.txt` file. Update it when adding major features or pages to provide a clean, markdown-formatted summary for modern AI search bots (like ChatGPT Search and Perplexity).
2. **Citation Architecture:** When stating facts or statistics, use HTML `<cite>` and `<blockquote>`. Search engines use this to verify E-E-A-T (Experience, Expertise, Authoritativeness, Trustworthiness).
3. **Markdown Fallbacks:** For text-heavy dynamic routes, expose a `?format=md` endpoint that returns raw Markdown, stripping away UI/CSS for easier crawler ingestion.
</rules>