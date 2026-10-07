---
class:
  - concept
description: in arrays, \\ ends a row and \hline draws a full-width rule; \\hline is not a rule — it is a row break followed by the literal text "hline"
tags:
  - system/concept
status: verified
topic: "[[math typesetting in obsidian]]"
references:
  - "[[mathjax supported commands]]"
created: 2026-10-07
---
## statement
inside `\begin{array}`: `\\` separates rows; `\hline` draws a rule across the full width and sits **between** rows. TeX reads `\\hline` as `\\` (row break) followed by the ordinary letters `hline` — it renders the word "hline" as cell text. that is why the old `\\hl` snippet (typed `\\hl` → produced `\\hline`) was broken: its output is a row break plus visible "hline", not a rule.

## evidence
- MathJax lists `\hline` and `\\` as separate supported commands — [[mathjax supported commands]]
- tokenization: a control word ends at the first non-letter; `\\` is a control symbol, so letters after it are plain text

## verification
- [x] traced TeX tokenization against the MathJax command list (2026-10-07)
- [x] restated from memory

## used in
- [[math typesetting in obsidian]]
- [[shortest safe way to type array rules]]
