# Welcome to Dea!

Hi, and welcome, compiler enthusiasts and systems folks!

Yours truly has been crafting a new, small but decidedly non-toy, carefully designed systems programming language called
**Dea**.

The design is deliberately conservative: operations are either well-defined, rejected at compile time, or fail with a
specified runtime error.

Dea includes deterministic resource management, ARC strings, sum types and pattern matching, explicit nullability, and
checked pointer semantics, with a portable C99 backend.

From the start, the plan was to write Dea's compiler in Dea itself as soon as possible, growing the language and its
compiler together.

Dea therefore evolves as a sequence of increasingly powerful language levels, connected through a staged bootstrap
chain:
each level eventually implements its own compiler and becomes the foundation for the next one, starting with **Dea/L0**.

## Where Dea stands today

**Dea/L0** is the current stable language level.

- released as **L0 2.0.0**
- self-hosted through its Stage 2 compiler, written in L0 itself
- verified through a triple-bootstrap fixed-point test
- supported on Linux, macOS, and Windows

**Dea/L1** is now the bleeding edge.

Its bootstrap compiler is written in L0, while L1 itself is already significantly more capable than L0. This provides
the first concrete proof that L0 is strong enough to host the language above it.

Dea/L1 extends the language and compiler model well beyond L0 while preparing for the next milestone: a self-hosted L1
compiler written in L1 itself, after which the cycle can repeat for successive levels.

## Start here

The practical starting point for using the language today is **Dea/L0**. If you are interested in compiler development
and the evolving language design, **Dea/L1** is where most active development happens.

**Source, compiler, specifications, tests, design documents, and current development:**

[https://github.com/googlielmo/dea-lang](https://github.com/googlielmo/dea-lang)

**Try Dea right in the browser:**

[https://playground.dealang.org/](https://playground.dealang.org/)

## Feedback and contributions

Dea is experimental, and external technical criticism is particularly valuable.

If you are interested in programming languages, compilers, systems programming, bootstrapping, C backends, language
semantics, or simply finding flaws in language design, please take a look.

Bug reports and code contributions are welcome, but so are questions and critical feedback about semantics, compiler
architecture, unnecessary complexity, missing cases, or questionable design decisions.

See the [contribution guide](https://github.com/googlielmo/dea-lang/blob/main/CONTRIBUTING.md) to get started.

## License

Dea is licensed under either the
[MIT license](https://github.com/googlielmo/dea-lang/blob/main/LICENSE-MIT) or the
[Apache License 2.0](https://github.com/googlielmo/dea-lang/blob/main/LICENSE-APACHE), at your option.

## The Dea language team

- [googlielmo](https://github.com/googlielmo) a.k.a. `gwz` | creator and lead developer | blog:
  [googlielmo.github.io](https://googlielmo.github.io)
- [gidad](https://github.com/gidad) | project advisor
- `[your name here]` | perhaps you could be part of this too!

Best,

-- gwz
