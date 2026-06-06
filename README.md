# AI-Rulez

Shared AI governance modules for kreuzberg.dev polyglot projects. Include modules by `path`; consumer repos
generate local AGENTS.md from these sources.

## Available Modules

### `modules/core` — All repos need this

- **Agents** (7): code-reviewer, polyglot-architect, rust-core-engineer, ffi-engineer, docs-writer,
  security-auditor, performance-engineer
- **Rules** (12): Rust conventions, bindings, FFI interop, Alef workflow, commit procedure, git hygiene, test guidance
- **Contexts** (5): prek, polyrepo-structure, pre-commit-tooling, taskfile-structure, kreuzberg-brand-and-docs
- **Skills** (2): common-task-commands, quick-start

### `modules/languages` — Repos with language bindings

- **Agents** (16): python, typescript, ruby, go, java, csharp, php, elixir, wasm, dart, swift,
  kotlin-android, zig, r, c-ffi, jni specialists

### `modules/cicd` — Most repos need this

- **Agents** (2): release-engineer, devops-engineer
- **Rules** (3): CI/CD pipelines, GitHub workflows, task automation

### `modules/e2e-generator` — Repos with `tools/e2e-generator/`

- **Agents** (1): e2e-generator-engineer
- **Rules** (3): conventions, fixture schema, generated code policy
- **Skills** (2): create-e2e-fixture, add-language-generator

### `modules/infrastructure` — Deployed services only

- **Rules** (3): Docker, GCloud, monitoring

## Usage

```yaml
includes:
  - name: kreuzberg-core
    source: https://github.com/kreuzberg-dev/ai-rulez.git
    path: modules/core
    merge_strategy: local-override
  - name: kreuzberg-languages
    source: https://github.com/kreuzberg-dev/ai-rulez.git
    path: modules/languages
    merge_strategy: local-override
  - name: kreuzberg-cicd
    source: https://github.com/kreuzberg-dev/ai-rulez.git
    path: modules/cicd
    merge_strategy: local-override
```

Run `ai-rulez generate` from each consumer repo after updating include pins or local rule sources.

## Consumer Configurations

| Repo | Modules |
|------|---------|
| kreuzberg | core, languages, cicd, infrastructure, e2e-generator |
| html-to-markdown | core, languages, cicd, infrastructure, e2e-generator |
| liter-llm | core, languages, cicd, e2e-generator |
| kreuzcrawl | core, languages, cicd, e2e-generator |
| tree-sitter-language-pack | core, languages, cicd, e2e-generator |
| kreuzberg-cloud | cicd, infrastructure |
| infra | cicd, infrastructure |
| actions | cicd |

## License

See the LICENSE file for licensing information.
