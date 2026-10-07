---
class:
  - concept
description: LaTeX Suite snippets rewrite keystrokes while editing; trigger, replacement, options and priority decide what fires
tags:
  - system/concept
status: verified
topic: "[[math typesetting in obsidian]]"
references:
  - "[[latex suite docs]]"
created: 2026-10-07
---
## statement
a snippet is `{trigger, replacement, options, priority}`. `options` scope *when* it fires: `m` math only, `t` text only, `A` auto-expand on typing (without `A` it needs Tab), `w` word boundary, `r` regex. `priority` decides who runs first when several match — **higher wins**, default 0. the default snippets ship two priority-3 **macro-guards** that match any `\word` typed in math, so a snippet whose trigger looks like a macro needs `priority > 3` to win the final keystroke.

## evidence
- DOCS.md: "Snippets with higher priority are run first"; options table (`t`, `m`, `M`, `n`, `A`, `r`, `v`, `w`, `U`) — [[latex suite docs]]
- default snippets: "disable snippets while typing macros" and "insert space after macros" both regex-match `\[A-Za-z]{2,}` at priority 3 — [[latex suite docs]]
- typing `\hli…` mid-word is left alone because `\hline` is a real macro, so the guards' prefix checks pass

## verification
- [x] read from the plugin's DOCS.md and default_snippets.js (2026-10-07)
- [x] restated from memory

## used in
- [[math typesetting in obsidian]]
- [[shortest safe way to type array rules]]
- [[latex snippet config]]
