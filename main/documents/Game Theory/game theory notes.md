---
class:
  - document
description: scripts when reading the book
aliases:
  - game-theory
tags:
  - documents/game-theory
  - documents
created: 2026-09-21 12:48
modified: 2026-09-23 18:22
---
- most player underestimate the value of fairness within certain scenarios; defines how individuals assume that other players are inherently selfish and greedy. 
	- fairness is actually what individuals are founded upon (more likely to come across)
- *game-frame*: a table of player strategies we have no information about regarding the preferences of the players

 1.e.1.a
Suppose we have two players: let Antonia be player 1 and Bob player 2: $I = \{ 1,2\}$. Define their strategies: $S_{1}=\{ 2,4,6 \}$ (Antonia) and $S_{2}=\{ 1,3,5 \}$ (Bob). The function is $f(s_{1}, s_{2})$, similar to $s_{1}+s_{2}$, with a result of $o_{n}$
$$
\begin{array}{|c|c|c|c|c|c|c|c|c|}
\hline
(2,1) & (2,3) & (2,5) & (4,1) & (4,3) & (4,5) & (6,1) & (6,3) & (6,5) \\
\hline
o_{1} & o_{2} & o_{3} & o_{4} & o_{5} & o_{6} & o_{7} & o_{8} & o_{9} \\
\hline
\end{array}
$$
Calculate: 
$$
\begin{array}{|c|c|c|c|c|c|c|c|c|}
\hline
3 & 5 & 7 & 5 & 7 & 9 & 7 & 9 & 11 \\
\hline
o_{1} & o_{2} & o_{3} & o_{4} & o_{5} & o_{6} & o_{7} & o_{8} & o_{9} \\
\hline
\end{array}
$$
Suppose $5 \geq x$ is Mexican ($M$), $7=x$ is Italian ($I$), and $9 \le x$ is Japanese ($J$):
$$
\begin{array}{|c|c|c|c|c|c|c|c|c|}
\hline
M & M & I & M & I & J & I & J & J \\
\hline
o_{1} & o_{2} & o_{3} & o_{4} & o_{5} & o_{6} & o_{7} & o_{8} & o_{9} \\
\hline
\end{array}
$$
1.e.1.b
$$
\begin{array}{c|cccccccc}
\text{outcome} \rightarrow & o_{1} & o_{2} & o_{3} & o_{4} & o_{5} & o_{6} & o_{7} & o_{8} & o_{9} \\
\hline
\text{utility function} \downarrow \\
U_{1}~(\text{Antonia})  & 3 & 3 & 2 & 3 & 2 & 1 & 2 & 1 & 1 \\
U_{2}~(\text{Bob})  & 2 & 2 & 3 & 2 & 3 & 1 & 3 & 1 & 1 & 
\end{array}
$$