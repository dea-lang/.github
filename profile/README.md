## Welcome to Dea/L0

Hi, and welcome, compiler enthusiasts and systems folks!

We're growing a new, small, and carefully designed systems programming language called **Dea**.

The way it's being grown is through a sequence of increasingly powerful languages that build on each
other. We're starting with **Dea/L0**, or just **L0** when we're being terse.

Dea/L0 is a small language with C-family syntax, no undefined behavior in the language itself,
deterministic resource management, ARC-managed strings, and sum types with pattern matching. But
from the beginning the plan was to write its compiler in Dea itself.

**That plan is now reality.** The Stage 2 compiler is self-hosted: it compiles itself, and the
result is verified through a strict triple-bootstrap fixed-point test (S1->S2, S2->S2, S2->S2; the
retained generated C must match byte-for-byte, and on stable host toolchains the normalized native
binaries must match as well).

Here's where things stand today:

- **Stage 1** (Python bootstrap compiler): complete and still used to kick off the bootstrap chain.
- **Stage 2** (self-hosted Dea compiler): full CLI parity with Stage 1, installable from the main
  repo via `make PREFIX=... install`, with embedded build provenance in `--version`.
- **Platforms**: Linux x86_64, macOS (arm64 + x86_64), and Windows (MinGW-w64 via MSYS2), all
  tested in CI.
- **CI/CD**: GitHub Actions on every PR across Linux, macOS, and Windows; tag-triggered
  multi-platform releases with SHA-256 checksums; manual-dispatch snapshot pre-releases.
- **API docs**: generated HTML on GitHub Pages, PDF release assets, and optional Chirpy blog
  integration.

So many alternatives exist for a bootstrap language, but we cut the bikeshedding short and settled
on Python, for simplicity and ease of prototyping. That choice paid off: Stage 1 is now a proven
bootstrap path, and the real compiler is Dea all the way down.

The next step is **Dea/L1**. Dea/L0 is the compiler base that will be used to build it.

Best,

-- gwz

P.S.: If you want to join the project, please reach out (see
[CONTRIBUTING.md](https://github.com/googlielmo/dea-lang-l0/blob/main/CONTRIBUTING.md) in the main
repo)!

## The Dea/L0 repository

The main repository for the Dea language: https://github.com/googlielmo/dea-lang-l0

## License

Dea is licensed under either the
[MIT license](https://github.com/googlielmo/dea-lang-l0/blob/main/LICENSE-MIT) or the
[Apache License 2.0](https://github.com/googlielmo/dea-lang-l0/blob/main/LICENSE-APACHE), at your
option.

## AI-Assisted Contributions Policy

The use of AI or other automated tools to assist in writing code, documentation, or other project
materials is **encouraged** in order to experiment, iterate rapidly, and explore solutions more
efficiently. Contributors remain fully responsible for the correctness, rights to contribute and
license, licensing compatibility, and security of their contributions, regardless of the tools used.

**All contributions must comply with the project's licensing, contribution guidelines, and quality
standards.**

## The Dea language team

- `gwz` a.k.a. [googlielmo](https://github.com/googlielmo) - creator and lead developer - blog:
  [googlielmo.github.io](https://googlielmo.github.io)
- `[your name here]` - you can be part of this too! Join us!
