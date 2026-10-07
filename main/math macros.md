---
class:
  - system
description: MathJax macro definitions — loaded by opening this note or Home once per Obsidian session
tags:
  - system/math
created: 2026-10-07
---
# math macros

Obsidian has no MathJax preamble, so custom commands must be defined inside a **rendered** math block. `\gdef` makes them global for the rest of the session. Open this note (or [[Home]], which embeds it) once after every Obsidian restart — until then, every `\hl` below renders as an error.

$$
\gdef\hl{\hline}
$$

With the macro loaded, this renders as a ruled table:

$$
\begin{array}{|c|c|}
\hl
a & b \\
\hl
c & d \\
\hl
\end{array}
$$

## why this exists
- typing `\hline` in math auto-collapses to `\hl` (LaTeX Suite snippet, priority 10). this note makes `\hl` render.
- if `\gdef` ever errors, replace it with `\newcommand{\hl}{\hline}` — same effect.
- for real LaTeX export: `\hl` belongs to the `soul` package (highlight), so a `.tex` preamble needs `\renewcommand{\hl}{\hline}` — see [[soul highlight command]].
- investigation trail: [[does hl render in obsidian]], [[shortest safe way to type array rules]].
