# Welcome to Dea!

Hi, and welcome, compiler enthusiasts and systems folks!

We're building a new, small, and carefully designed systems programming language called **Dea**.

It's being grown as a sequence of increasingly powerful languages that build on each other,
starting with **Dea/L0** (or just **L0** when we're being terse).

Dea/L0 is a small C-family language with no undefined behavior in the language itself,
deterministic resource management (`with` / `cleanup` plus ARC for `string`), sum types with
pattern matching, explicit nullability, and pointers without UB. From the start, the plan was to
write its compiler in Dea itself.

**That plan is now reality.** The L0 Stage 2 compiler is self-hosted: it compiles itself, and the
result is verified through a strict triple-bootstrap fixed-point check (`make triple-test`).

Here's where L0 stands today:

- **Stage 1** (Python bootstrap compiler): complete, still the reference for language behavior and
  diagnostics, and used to kick off the bootstrap chain.
- **Stage 2** (self-hosted Dea compiler): full public CLI parity with Stage 1, installable via
  `make PREFIX=... install`, with embedded build provenance reported by `--version`.
- **Platforms**: Linux x86_64, macOS (arm64 + x86_64), and Windows (MinGW-w64 via MSYS2 UCRT64 or
  MINGW64), all tested in CI.
- **CI/CD**: GitHub Actions on every PR across Linux, macOS, and Windows; tag-triggered
  multi-platform releases with SHA-256 checksums; manual-dispatch snapshot pre-releases, on the
  `l0-v*` / `l0-snapshot-*` release lines.
- **Docs**: generated HTML API reference on GitHub Pages, PDF release assets, and optional Chirpy
  blog integration.

Python was the right choice for Stage 1: simplicity and fast prototyping. That paid off - Stage 1
is a proven bootstrap path, and the real compiler is Dea all the way down.

**Dea/L1 is now well underway.** It lives in the same repository as a sibling subtree under
`l1/`. The Stage 1 L1 compiler (`compiler/stage1_l0/`, written in Dea/L0 and built by
`l0c-stage2`) already builds and tests on Linux, macOS, and Windows under its own
`l1-ci.yml` workflow. This is the first concrete proof that L0 is strong enough to host the
language above it.

L1 has already grown beyond L0 in language and library surface:

- the fixed-width integer family `tiny` / `short` / `ushort` / `int` / `uint` / `long` / `ulong`,
  with hex/bin/oct prefixed and contextual-bigint integer literals;
- `float` and `double` with real literals and a precise, backend-validated FP contract;
- bitwise operators `&`, `|`, `^`, `~`, `<<`, `>>`;
- top-level `const`, string equality / ordering / `+` concatenation, same-type `T?` and pointer
  identity equality, the `is(x, Variant)` enum-tag intrinsic, function pointer types (plain and
  `unsafe`), fixed-size arrays `T[N]` with checked indexing, raw-pointer indexing inside `unsafe func`, and single-statement `while` / `for` / `match` bodies;
- module-level export manifests, alias and selective imports, and deterministic textual `.l1m`
  module-interface emission and round-trip;
- stdlib growth: `std.real`, wider-integer helpers in `std.integer`, wide-integer text conversions
  in `std.text`, and the new `std.types` value-type query surface.

The next milestone is the self-hosted Stage 2 L1 compiler under `compiler/stage2_l1/`, after which
the cycle repeats for successive levels. Until Stage 2 L1 and its install/dist contract land, L1
is deliberately bootstrap-only - no release line yet (future tags will use `l1-v*` /
`l1-snapshot-*`).

Best,
-- gwz

P.S.: If you want to join the project, please reach out (see
[CONTRIBUTING.md](https://github.com/googlielmo/dea-lang/blob/main/CONTRIBUTING.md) in the main
repo)!

## The Dea repository

The Dea monorepo houses both the L0 release line and the in-progress L1 subtree:
<https://github.com/googlielmo/dea-lang>

## License

Dea is licensed under either the
[MIT license](https://github.com/googlielmo/dea-lang/blob/main/LICENSE-MIT) or the
[Apache License 2.0](https://github.com/googlielmo/dea-lang/blob/main/LICENSE-APACHE), at your
option.

## AI-Assisted Contributions Policy

The use of AI or other automated tools to assist in writing code, documentation, or other project
materials is **encouraged** in order to experiment, iterate rapidly, and explore solutions more
efficiently. Contributors remain fully responsible for the correctness, rights to contribute and
license, licensing compatibility, and security of their contributions, regardless of the tools
used.

**All contributions must comply with the project's licensing, contribution guidelines, and
quality standards.**

## The Dea language team

- `gwz` a.k.a. [googlielmo](https://github.com/googlielmo) - creator and lead developer - blog:
  [googlielmo.github.io](https://googlielmo.github.io)
- `[your name here]` - you can be part of this too! Join us!
