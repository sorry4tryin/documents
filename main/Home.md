---
class:
  - system
description: index and manual for the knowledge-learning system
aliases:
  - home
  - index
tags:
  - system
created: 2026-10-07
---
# home

![[math macros]]

## map
![[knowledge base.base]]

- example topic — [[math typesetting in obsidian]] (stage: connections)
- math macros — [[math macros]] (must render once per session)
- snippet work log — [[latex snippet config]]

## the system
one note per entity, one folder per entity. the `class` property is the source of truth.

| entity | folder | template | status values |
| --- | --- | --- | --- |
| topic | `topics/` | [[topicnote]] | `stage:` foundations → concepts → questions → investigation → verification → problems → explanation → connections → claimed |
| concept | `concepts/` | [[conceptnote]] | draft, verified |
| question | `questions/` | [[questionnote]] | open, investigating, resolved, dropped |
| problem | `problems/` | [[problemnote]] | todo, solving, solved, failed |
| source | `sources/` | [[sourcenote]] | unread, reading, digested |
| project | `projects/` | [[projectnote]] | idea, active, paused, done |

existing material is untouched: book notes stay in `documents/`, clips in `web-clips/`, captures in `quick notes/`. link them wherever they support a claim.

## workflow
topic → foundations → concepts → questions → investigation → verification → problems → my explanation → connections → final claim

this is the existing study method (see [[study method.canvas]]), structured:
- blurt → **my explanation** — write it from memory
- hypercorrection → **verification** — check against sources
- practice questions → **problems** — derive/solve myself
- evaluate → **final claim** — the defensible summary

## protocol one (si → ai)
anything an AI (or anyone) tells you enters the system **unverified**. it only becomes applicable knowledge after you have verified it in practice — solved the problem, checked the source, or derived it yourself. enforced by:
- concepts stay `draft` until checked against a source
- a topic cannot reach `claimed` while a problem is unsolved

## expansion rule
promote an idea to its own concept note only when it is reused by at least two notes or blocks understanding. everything else stays inline in the topic. controlled expansion without cutting real connections — including connections to apparently unrelated topics, which go under `connections` first.

## capture
create a note inside an entity folder and its template auto-applies (templater folder templates). unsorted thoughts still go to `quick notes/` — triage from there.

## snippet change log (2026-10-07)
- LaTeX Suite: typing `\hline` in math now collapses to `\hl` (priority 10). `\hl` renders via [[math macros]].
- the old `\\hl` snippet was commented out — its output `\\hline` renders the word "hline" as text, not a rule. restore it in `Settings → LaTeX Suite → Snippets` if wanted.
- **reload obsidian** to load the new snippets, then prove it with [[verify hline collapse end to end]].
