---
priority: high
---

# Alef Workflow

- Treat Alef-managed binding files as generated output. Change Rust source, README templates, fixtures, or `alef.toml` instead of hand-editing generated packages.
- Use `task alef:generate` for fast regeneration. It must run `alef all --clean --format=false`.
- Do not compile bindings or run verification from `task alef:generate`.
- Use `task alef:build` or `task build:bindings` when binding compilation is needed.
- Use `task format` or `prek run --all-files` for formatting. Alef post-generation formatters are opt-in via `alef ... --format`.
- Commit generator inputs and regenerated output together.
