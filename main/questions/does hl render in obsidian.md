---
class:
  - question
description: does \hl render in obsidian math, and if not, what makes it render
tags:
  - system/question
status: resolved
topic: "[[math typesetting in obsidian]]"
created: 2026-10-07
---
## question
does `\hl` render in obsidian, or is it an undefined macro?

## investigation
- MathJax supported-commands list: no `\hl` anywhere — [[mathjax supported commands]]
- searched the whole vault: no `\gdef`, `\newcommand`, or preamble file exists; LaTeX Suite 1.12.8 has no preamble setting (grep of its main.js: zero matches)
- MathJax docs + community reports: definitions work when placed inside a **rendered** math block, ideally with `\gdef` so they persist for the session

## answer
**no — undefined macro, red error text.** it renders only after [[math macros]] (or [[Home]], which embeds it) has been rendered once in the session, because that note runs `\gdef\hl{\hline}`.
