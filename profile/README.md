## Welcome to Dea/L0

Hi, and welcome, compiler enthusiasts and systems folks!

We're growing a new, small and carefully designed systems programming language called **Dea**.

The way it's being grown is through a sequence of increasingly powerful languages that build on each other.

We're starting with **Dea/L0**, or just **L0** for short.

L0 is a small language, but from the beginning we're planning to write its compiler in L0 itself.
In other words, it’s designed to become self-hosted.

Of course, we need to start a first implementation in *some* language.
So many alternatives exist, but we cut the bikeshedding short and settled on using Python, for simplicity and ease
of prototyping.

The first step is almost complete: stage 1 of the compiler can now translate L0 source code into C99.

Stage 2 is under development: it's being written in L0 itself and includes a growing standard library.

Best,

-- gwz

P.S.: If you want to join the project, please reach out (see CONTRIBUTING.md in the main repo)!

## The L0 repository

The main repository for the L0 language: https://github.com/googlielmo/dea-lang-l0

## License

L0 is licensed under either the MIT license or the Apache License 2.0, at your option.

## AI-Assisted Contributions Policy

The use of AI or other automated tools to assist in writing code, documentation, or other project materials is
**encouraged** in order to experiment, iterate rapidly, and explore solutions more efficiently.
Contributors remain fully responsible for the correctness, rights to contribute and license, licensing compatibility,
and security of their contributions, regardless of the tools used.

**All contributions must comply with the project’s licensing, contribution guidelines, and quality standards.**

## The Dea language team

* `gwz` a.k.a. [googlielmo](https://github.com/googlielmo) - creator and lead developer -
  blog: [googlielmo.github.io](https://googlielmo.github.io)
* `[your name here]` - you can be part of this too! Join us!
