---
priority: critical
---

- Bindings are minimal glue: call Rust core, convert types, convert errors — no business logic
- Canonical surface: Rust core API first, C FFI ABI second, language bindings third;
  integrations/adapters sit outside bindings
- Crate naming: {lib}-py (PyO3), {lib}-node (NAPI-RS), {lib}-rb (Magnus), {lib}-php (ext-php-rs),
  {lib}-wasm (wasm-bindgen), {lib}-ffi (C FFI), {lib}-jni (JNI)
- Distribution paths: packages/python/ (PyPI), typescript/ (npm), ruby/ (RubyGems), php/ (Composer),
  go/ (Go module), java/ (Maven), csharp/ (NuGet), dart/ (pub.dev), swift/ (SwiftPM),
  kotlin-android/ (Maven/Gradle), r/ (CRAN/GitHub), zig/ (Zig package)
- Each binding has its own language-native test suite — 80%+ coverage
- Generated e2e code lives under e2e/{language}/ and is not hand-edited
- Error conversion must preserve context (message + numeric code) at every FFI boundary
- Async: pyo3_asyncio (Python), native #[napi] async (TS), Fiber (Ruby), block on Tokio via FFI only at
  sync host boundaries
