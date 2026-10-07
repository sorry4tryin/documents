---
class:
  - source
description: official MathJax list of supported TeX commands — used to check \hline, \hl, \gdef, \newcommand
tags:
  - system/source
status: digested
author: MathJax documentation
year:
url: https://docs.mathjax.org/en/latest/input/tex/macros/
reliability: 5
topic: "[[math typesetting in obsidian]]"
created: 2026-10-07
---
## claims it supports
- `\hline` is supported (base package)
- `\gdef` is supported via the *begingroup* extension (autoloaded); `\newcommand` via the *newcommand* package
- there is no `\hl` in the supported list

## what i verified from it
- confirmed `\hline` present and `\hl` absent on 2026-10-07
- macro definitions must sit inside math delimiters (macros page, same site)

## quotes / locations
- supported-commands table, sections H and G
