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
modified: 2026-09-23 19:46
---
- most player underestimate the value of fairness within certain scenarios; defines how individuals assume that other players are inherently selfish and greedy. 
	- fairness is actually what individuals are founded upon (more likely to come across)
- *game-frame*: a table of player strategies we have no information about regarding the preferences of the players

 1.e.1.a
Suppose we have two players: let Antonia be player 1 and Bob player 2: $I = \{ 1,2\}$. Each player has select values $S_{1}=\{ 2,4,6 \}$ (Antonia) and $S_{2}=\{ 1,3,5 \}$ (Bob). Each strategy pair $(s_{1},s_{2}) \in S_{1} \times S_{2}$ produces an outcome $f(s_{1},s_{2})=s_{1}+s_{2}\rightarrow O$
$$
\begin{array}{|c|c|c|c|c|c|c|c|c|}
\hline
(2,1) & (2,3) & (2,5) & (4,1) & (4,3) & (4,5) & (6,1) & (6,3) & (6,5) \\
\hline
o_{1} & o_{2} & o_{3} & o_{4} & o_{5} & o_{6} & o_{7} & o_{8} & o_{9} \\
\hline
\end{array}
$$
Calculate payoff per outcome: 
$$
\begin{array}{cc}
 & \text{Player 2 (Bob)} \\
\text{Player 1 (Antonia)} & 
\begin{array}{|c|c|c|}

\hline
3 & 5 & 7\\
\hline
5 & 7 & 9\\
\hline
7 & 9 & 11\\
\hline
\end{array}
\end{array}
$$
Let $5 \geq x$ is Mexican ($M$), $7=x$ is Italian ($I$), and $9 \le x$ is Japanese ($J$):
$$
\begin{array}{cc} \\
 & \text{Player 2 (Bob)} \\
 \text{Player 1 (Antonia)} & 
\begin{array}{|c|c|c|}
\hline
M & M & I\\
\hline
M & I & J\\
\hline
I & J & J \\
\hline
\end{array}
\end{array}
$$
Therefore, the following scenario represents $\braket{I = \{1,2\},\ (S_{1},S_{2}) = (\{2,4,6\},\ \{1,3,5\}),\ O = \{M, I, J\},\ f: S \to O}$

1.e.1.b
For Antonia: $M >_{Antonia}I>_{Antonia}J$; for Bob: $I>_{Bob}M>_{Bob}J$. Use values $1,2$ and $3$ with utility function:
$$
\begin{array}{r|cccccccc}
outcome \rightarrow & o_{1} & o_{2} & o_{3} & o_{4} & o_{5} & o_{6} & o_{7} & o_{8} & o_{9} \\
utility \; function \downarrow \\
\hline
U_{1}~(\text{Antonia})  & 3 & 3 & 2 & 3 & 2 & 1 & 2 & 1 & 1 \\
U_{2}~(\text{Bob})  & 2 & 2 & 3 & 2 & 3 & 1 & 3 & 1 & 1 & 
\end{array}
$$
Represent the corresponding reduced-form game as table:
$$
\begin{array}{cc}
 & \text{Player 2 (Bob)} &  \\ \\
\text{Player 1 (Antonia)} & 
\begin{array}{|c|c|c|c|}
\hline
\quad & \text{Mexican} & \text{Italian} & \text{Japanese} \\
\hline
\text{Mexican}  & 3 \quad 2  & 3 \quad 2 &  2 \quad 3\\
\hline
\text{Italian}  & 3 \quad 2 & 2 \quad 3 & 1 \quad 1\\
\hline 
\text{Japanese} & 2 \quad 3  & 1 \quad 1 & 1 \quad 1\\
\hline
\end{array}
\end{array}
$$