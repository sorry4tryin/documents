---
class:
  - source
description: LaTeX Suite README, DOCS.md and default snippets — snippet anatomy, options, priority, macro-guards
tags:
  - system/source
status: digested
author: artisticat1
year: 2026
url: https://github.com/artisticat1/obsidian-latex-suite/blob/main/DOCS.md
reliability: 5
topic: "[[math typesetting in obsidian]]"
created: 2026-10-07
---
## claims it supports
- snippet fields: trigger, replacement, options, priority, description; "snippets with higher priority are run first", default 0
- options: `t` text, `m` math, `M` block math, `n` inline math, `A` auto, `r` regex, `w` word boundary, `v` visual, `U` skip undo
- the default snippets include two priority-3 guards matching `\[A-Za-z]{2,}` — "disable snippets while typing macros" and "insert space after macros"
- without `U`, undo removes the snippet expansion first and reinserts the trigger key — that is the escape hatch

## what i verified from it
- read DOCS.md, README and src/default_snippets.js on 2026-10-07; the installed version here is 1.12.8 and has **no preamble feature** (grep of main.js: zero matches)

## quotes / locations
- DOCS.md → options table; default_snippets.js → the two macro-guard snippets
