---
class:
  - concept
description: obsidian renders math with MathJax 3, a fixed subset of TeX — no packages, no preamble; unknown commands error instead of rendering
tags:
  - system/concept
status: verified
topic: "[[math typesetting in obsidian]]"
references:
  - "[[mathjax supported commands]]"
created: 2026-10-07
---
## statement
obsidian uses **MathJax 3** for `$...$` and `$$...$$`. it supports one fixed list of TeX commands; packages don't exist; `\newcommand`/`\gdef` only take effect inside a rendered math block; an unknown macro renders as an error message instead of a guess.

## evidence
- MathJax's supported-commands table lists `\hline` (base) but no `\hl`; `\gdef` comes from the *begingroup* extension, `\newcommand` from the *newcommand* package — [[mathjax supported commands]]
- MathJax docs: macro definitions "must be enclosed in math delimiters" — there is no document preamble inside obsidian

## verification
- [x] checked against the MathJax supported-commands list (2026-10-07)
- [x] can restate from memory: subset engine, definitions only inside rendered math, errors on unknown macros

## used in
- [[math typesetting in obsidian]]
- [[does hl render in obsidian]]
