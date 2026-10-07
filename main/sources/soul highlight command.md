---
class:
  - source
description: in real LaTeX, \hl is the soul package's text-highlight command — a name collision for LaTeX export
tags:
  - system/source
status: digested
author: CTAN / TeX StackExchange
year:
url: https://www.ctan.org/pkg/soul
reliability: 5
topic: "[[math typesetting in obsidian]]"
created: 2026-10-07
---
## claims it supports
- `\hl{...}` highlights text (yellow by default, needs the `color` package); it is not a table rule
- `soul` is a text-mode LaTeX package — irrelevant to MathJax, but decisive for `.tex` export

## what i verified from it
- confirmed via the CTAN package page and TeX StackExchange answers on 2026-10-07

## quotes / locations
- soul docs: "The \hl command does only highlight if the color package was loaded, otherwise it falls back to underlining."
- implication: exporting obsidian math to LaTeX needs `\renewcommand{\hl}{\hline}` in the preamble — a plain `\newcommand` errors because `soul` already defines `\hl`
