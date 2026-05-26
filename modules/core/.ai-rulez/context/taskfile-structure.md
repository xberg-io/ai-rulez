---
priority: medium
---

# Taskfile Structure

All repos use [Taskfile.yaml](https://taskfile.dev) with the `task` CLI. Always prefer `task` commands over raw tool invocations.

- **Discovery:** `task --list` shows all available tasks
- **Common tasks:** `task setup`, `task build`, `task test`, `task lint`, `task format`
- **Language-scoped:** `task rust:test`, `task python:lint`, `task node:build`, etc.
- **Build profiles:** `BUILD_PROFILE=release task build` or `task build:release`
- **Alef regeneration:** `task alef:generate` runs `alef all --clean --format=false`; it regenerates Alef-managed files without compiling bindings or running post-generation formatters.
- **Alef build:** `task alef:build` or `task build:bindings` compiles language bindings explicitly.
- **Alef verification:** `task alef:verify` checks generated output freshness when needed; do not hide verification inside fast regeneration.
