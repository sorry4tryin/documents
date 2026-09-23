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
modified: 2026-09-23 17:39
---
- most player underestimate the value of fairness within certain scenarios; defines how individuals assume that other players are inherently selfish and greedy. 
	- fairness is actually what individuals are founded upon (more likely to come across)
- *game-frame*: a table of player strategies we have no information about regarding the preferences of the players

 1.e.1.a
$$
\begin{gathered}
I = \{1,2,\dots, n\} \\
\text{Let Antonia be player 1 and Bob player 2} \\
\text{Suppose Antonia is constrained to the vaules} \;2,4,6 \text{and Bob to}\;1,3,5. \\
\text{Represent the those values by}\;S_{n}\;\text{:} \\
S_{1} = \{ 2,4,6 \}\quad \text{and}\quad S_{2} = \{ 1,3,5 \}
\end{gathered}
$$
$$
\begin{aligned}
& I = (1, 2, \dots, n) \\
& \text{Let Antonia be player 1 and Bob player 2.} \\
& \text{Suppose Antonia is constrained to the values } 2, 4, 6 \text{ and Bob to } 1, 3, 5. \\
& \text{Represent those values by } S_n \text{:} \\
& S_1 = \{ 2, 4, 6 \} \quad \text{and} \quad S_2 = \{ 1, 3, 5 \}
\end{aligned}
$$
$$
\begin{array}{l}
I = (1, 2, \dots, n) \\
\text{Let Antonia be player 1 and Bob player 2.} \\
\text{Suppose Antonia is constrained to the values } 2, 4, 6 \text{ and Bob to } 1, 3, 5. \\
\text{Represent those values by } S_n \text{:} \\
S_1 = \{ 2, 4, 6 \} \quad \text{and} \quad S_2 = \{ 1, 3, 5 \}
\end{array}
$$

		
$I= {1,2}$ 
		$\text{Let Antonia be player 1 and Bob player 2}$
		$S_{1}=\{ 2,4,6 \}$ 
		$\text{Antonia will serve as the rows}$
		$S_{2}=\{ 1,3,5 \}$
		$\text{Bob will serve as the columns}$
		$S=\begin{bmatrix}&(1,2)&(1,4)&(1,6)&(3,2)&(3,4)&(3,6)&(5,2)&(5,4)&(5,6)\\&o_{1}&o_{2}&o_{3}&o_{4}&o_{5}&o_{6}&o_{7}&o_{8}&o_{9}&\end{bmatrix}$
		$\text{Let}~S~\text{contain each}~f(s_{1},s_{2})~\text{corresponding with}~o_{n}. ~ \text{Calculate the sum of each function:}$
		$S=\begin{bmatrix}&&1&&3&&5&\\2&&3&&5&&7\\4&&5&&7&&9\\6&&7&&9&&11\end{bmatrix}$
		$\text{Suppose 5~≥~x be Mexican,}~\text{7 = x be Italian,}~\text{and}~\text{9~<~x~ be Japanese}$
		$\text{Let}~M~\text{represent Mexican,}~I~\text{represent Italian,}~J~\text{represent Japanese}$
		$S=\begin{bmatrix}&&1&&3&&5&\\2&&M&&M&&I\\4&&M&&I&&J\\6&&I&&J&&J\end{bmatrix}$
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