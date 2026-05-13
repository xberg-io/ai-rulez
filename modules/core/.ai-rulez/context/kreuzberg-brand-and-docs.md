---
priority: high
---

# Kreuzberg Brand and Docs

**Company**: Kreuzberg, Inc.
**Landing**: kreuzberg.dev
**Open-source docs domain pattern**: `docs.<repo>.kreuzberg.dev` (core extraction lib uses bare `docs.kreuzberg.dev`)
**Commercial docs domain**: docs.kreuzberg.cloud

Authoritative product list (use this exact ordering and wording in every README ecosystem block):

- [Kreuzberg](https://docs.kreuzberg.dev) — document intelligence: text, tables, metadata from 91+ formats with optional OCR.
- [Kreuzberg Cloud](https://docs.kreuzberg.cloud) — managed extraction API with SDKs, dashboards, and observability.
- [kreuzcrawl](https://docs.kreuzcrawl.kreuzberg.dev) — web crawling and scraping with HTML→Markdown and headless-Chrome fallback.
- [html-to-markdown](https://docs.html-to-markdown.kreuzberg.dev) — fast, lossless HTML→Markdown engine.
- [liter-llm](https://docs.liter-llm.kreuzberg.dev) — universal LLM API client with native bindings for 14 languages and 143 providers.
- [tree-sitter-language-pack](https://docs.tree-sitter-language-pack.kreuzberg.dev) — tree-sitter grammars and code-intelligence primitives.

Docs sites use the Zensical SSG (Material theme) with shared canonical assets:
- `docs/css/extra.css` (identical across repos; per-repo accent overrides at end of file allowed)
- `docs/overrides/main.html` (identical across repos; only GA ID, og-image URL, edit-link prefix substituted per-repo)
- `zensical.toml` theme/plugins/markdown_extensions blocks (identical across repos)
- Nav: `Home → Get Started → Guides → Concepts → Reference → More`
- `docs/index.md`: hero → "Why X" 6-card grid → Language Support table → Quick Example tabs → "Part of Kreuzberg, Inc." ecosystem grid → "Explore the Docs" cards → Getting Help
- `docs/llms.txt`: canonical sitemap shape with an Ecosystem section listing all sibling docs subdomains

Every repo's root Taskfile exposes the same docs commands via `.task/tools/docs.yml`:
- `task docs:build` — build the site (zensical build --clean)
- `task docs:build:strict` — strict build (CI-equivalent)
- `task docs:serve` — local dev server with live reload
- `task docs:lint:links` — lychee link check
- `task docs:lint:prose` — textlint prose lint
- `task docs:snippets:validate` (kreuzberg only) — verify all `docs/snippets/` compile via snippet-runner

Prose style: terse, second-person imperative. No marketing adjectives. No emoji headers. Lead with structural facts ("Eight extraction functions are available…") rather than "This section will walk you through…". Use admonitions only for genuine `tip`/`warning`/`info` callouts.
