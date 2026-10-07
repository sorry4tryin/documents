---
class:
  - problem
description: hands-on proof that typing \hline collapses to \hl and still renders as a rule
tags:
  - system/problem
status: todo
topic: "[[math typesetting in obsidian]]"
created: 2026-10-07
---
## problem
prove, at the keyboard, that the `\hline` → `\hl` shortcut works end to end in obsidian. nothing in this topic is *applicable* until this is solved — protocol one.

## attempt
run after **reloading obsidian** (new snippets load at startup):

1. open [[Home]] once — this renders [[math macros]] and defines `\hl` for the session
2. new test note, enter display math: `$$`, then `\begin{array}{|c|c|}`, Enter
3. type `\hline` slowly, watching the final `e`
   - expect: the word collapses to `\hl ` as soon as it completes
4. type `a & b \\`, Enter, `\hline` again, `c & d \\`, Enter, `\hline` once more, `\end{array}`, `$$`
5. reading view (Cmd+E): expect a 2×2 ruled table — identical to what `\hline` produces
6. escape hatch: in edit mode, type `\hline` again, then Cmd+Z once — expect the literal `\hline` back

## solution
*(fill in after running)*

## check
- [ ] collapse fired while typing, no Tab needed (step 3)
- [ ] rule renders with the macro loaded (step 5)
- [ ] session rule: after restarting obsidian, `\hl` errors until [[Home]] is opened again
- [ ] undo restores the literal `\hline` (step 6)

if any step fails: record what happened under `attempt`, set `status` to `failed`, and fix via [[latex snippet config]] or [[math macros]].
