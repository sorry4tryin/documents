---
class:
  - question
description: minimal-keystroke way to write array rules in obsidian without breaking rendering
tags:
  - system/question
status: resolved
topic: "[[math typesetting in obsidian]]"
created: 2026-10-07
---
## question
what is the shortest safe way to type array rules in obsidian?

## investigation
- (a) keep typing `\hline` — 6 keys, renders everywhere, zero risk
- (b) old `\\hl` snippet — broken output; see [[array rules in mathjax]]
- (c) trigger `\hl` → replace with `\hline` — renders everywhere but reverses the chosen direction
- (d) collapse `\hline` → `\hl` while typing, and define `\hl` once per session

## answer
**(d)**: a LaTeX Suite snippet (math-only, auto, priority 10) collapses `\hline` to `\hl` as it is typed, and `\gdef\hl{\hline}` in [[math macros]] makes it render. undo (Cmd+Z) immediately after the collapse restores the literal `\hline` — the escape hatch. implemented in [[latex snippet config]]; prove it with [[verify hline collapse end to end]].
