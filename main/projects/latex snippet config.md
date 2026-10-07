---
class:
  - project
description: applied work log — the \hline to \hl shortcut in LaTeX Suite and the macro that makes it render
tags:
  - system/project
status: active
topic: "[[math typesetting in obsidian]]"
created: 2026-10-07
---
## goal
make typing `\hline` cost the fewest keystrokes without breaking rendering — the shortcut requested in the session.

## log
- 2026-10-07 — backup: `.obsidian/plugins/obsidian-latex-suite/data.json.bak-20261007`
- 2026-10-07 — added snippet `{trigger: "\\hline", replacement: "\\hl ", options: "mA", priority: 10}`; priority 10 beats the macro-guards (priority 3) on the final keystroke
- 2026-10-07 — commented out the old `\\hl` → `\\hline` snippet (broken output; restore = uncomment one line in Settings → LaTeX Suite → Snippets)
- 2026-10-07 — templater folder templates wired for topics/concepts/questions/problems/sources/projects; timestamps plugin now stamps non-empty new files, `templates/` excluded
- pending — reload obsidian to load the snippets, then run [[verify hline collapse end to end]]
- pending — run `~/obsidian-dotfiles/sync.sh ~/Documents/vmain/main` and commit, so the config reaches other devices

## done-when
[[verify hline collapse end to end]] is solved and its checklist is ticked.
