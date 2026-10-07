---
class:
  - topic
description: how math renders in obsidian (MathJax), how LaTeX Suite snippets change typing, and the \hline shortcut
aliases:
  - latex in obsidian
tags:
  - system/topic
  - math/latex
stage: connections
created: 2026-10-07
---
## foundations
- obsidian renders math with **MathJax**, not LaTeX — a browser engine that knows a fixed subset of TeX commands. it is not a full typesetter.
- LaTeX Suite edits **keystrokes**; rendering is a separate pipeline. changing what you type ≠ changing what renders.
- arrays: `$$\begin{array}{|c|c|} ... \end{array}$$` with `\hline` for rules — already used in [[game theory notes]].

## concepts
- [[mathjax vs latex]] — what renders, what errors, why definitions need `\gdef`
- [[latex suite snippets]] — trigger, replacement, options, priority; the macro-guards
- [[array rules in mathjax]] — `\hline` vs `\\` vs the personal `\hl`

## questions
- [[does hl render in obsidian]] — resolved: no, unless defined
- [[shortest safe way to type array rules]] — resolved: collapse `\hline` to `\hl`

## investigation
- MathJax's supported-commands list: `\hline` supported, `\hl` absent — [[mathjax supported commands]]
- LaTeX Suite docs + default snippets: options, priority, the priority-3 macro-guards — [[latex suite docs]]
- LaTeX itself: `\hl` is the `soul` package's highlight command — [[soul highlight command]]
- searched the vault: no `\gdef` / `\newcommand` anywhere; LaTeX Suite 1.12.8 has no preamble feature

## verification
- [x] `\hline` in the MathJax supported list (base package)
- [x] `\hl` absent from the same list
- [x] old `\\hl` snippet produced `\\hline`, which renders "hline" as cell text (TeX reads `\\` then plain letters) — commented out, see [[latex snippet config]]
- [ ] end to end: type `\hline` in an array, watch it collapse to `\hl`, see the rule render — [[verify hline collapse end to end]] (needs hands on a keyboard)

## problems
- [[verify hline collapse end to end]] — the practice step. todo.

## my explanation
obsidian never runs LaTeX. when it sees `$...$` it asks MathJax "can you draw this?", and MathJax only knows the commands on its list. `\hline` is on the list; `\hl` is not — so `\hl` is a made-up word unless MathJax is taught it, once per session, with `\gdef`. LaTeX Suite lives one layer up: it rewrites keystrokes before MathJax ever sees them. so the plan is: let typing `\hline` collapse to the shorter `\hl`, and teach MathJax that `\hl` means `\hline`. two layers, two fixes — and the practice problem proves they actually meet.

## connections
- [[game theory notes]] — live arrays using `\hline` today; the snippet changes future typing there, never existing text
- [[alias extension]] — shortcuts for machines vs shortcuts for hands: aliases let models run quicker, snippets let me type quicker
- [[academic independence]] — mastery means being able to reproduce it, hence problems before claims
- [[study method.canvas]] — this topic ran blurt → hypercorrection → practice as explanation → verification → problems
- apparently unrelated: the neovim/texlive setup in [[dig. notes system.canvas]] splits the same way — input mapping (keybinds, snippets) never changes what the engine renders

## final claim
*(provisional — holds only after [[verify hline collapse end to end]] is solved)*

typing `\hline` in math collapses to `\hl` (LaTeX Suite snippet, math-only, auto, priority 10); `\hl` renders as a rule because [[math macros]] defines `\gdef\hl{\hline}`, which must be rendered once per session — [[Home]] embeds it so opening the index is enough. the shortcut saves keystrokes and renders identically to `\hline` in obsidian. outside obsidian, `\hl` means highlight (`soul`), so LaTeX export needs `\renewcommand{\hl}{\hline}` in the preamble.
