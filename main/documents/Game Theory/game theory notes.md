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
modified: 2026-09-30 00:00
---
- most player underestimate the value of fairness within certain scenarios; defines how individuals assume that other players are inherently selfish and greedy. 
	- fairness is actually what individuals are founded upon (more likely to come across)
- *game-frame*: a table of player strategies we have no information about regarding the preferences of the players

 1.e.1.a
Suppose we have two players: let Antonia be player 1 and Bob player 2: $I = \{ 1,2\}$. Each player has select values $S_{1}=\{ 2,4,6 \}$ (Antonia) and $S_{2}=\{ 1,3,5 \}$ (Bob). Each strategy pair $(s_{1},s_{2}) \in S_{1} \times S_{2}$ produces an outcome $f(s_{1},s_{2})=s_{1}+s_{2}\rightarrow O$.
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
Therefore, the following scenario represents $\braket{I = \{1,2\},\ (S_{1},S_{2}) = (\{2,4,6\},\ \{1,3,5\}),\ O = \{M, I, J\},\ f: S \to O}$.

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

1.e.1.c
- *dominance*: compares strategies within one player's own $\braket{S_{i}}$ while fixing what the other player does; a comparison across $\braket{S_{1} \times S_{2}}$ is instead called better
	- fix $s_{-i} \in \braket{S_{-i}}$ (for player 1, this is Bob's choice of $s_{2}$); then every row of Player 1's column reduces to a single payoff
- *strictly dominates*: $a$ strictly dominates $b$ iff $\forall s_{-i} \; U_{1}(a, s_{-i}) > U_{1}(b, s_{-i})$. Player 1's $a$ is a **best response** against every $s_{2}$, so $b$ can never be part of a Nash equilibrium
	- equivalently in preference terms: $\forall s_{-i} \; a \;>_{Antonia}\; b \; wrt \; s_{-i}$
- *weakly dominates*: $a$ weakly dominates $b$ iff $\forall s_{-i} \; U_{1}(a, s_{-i}) \geq U_{1}(b, s_{-i})$ and $\exists s_{-i}^{*} \; U_{1}(a, s_{-i}^{*}) > U_{1}(b, s_{-i}^{*})$. The second clause is what forbids a from tying $b$ everywhere, otherwise "weak dominance" would be satisfied by $a = b$
	- preference form: $a \;>_{Antonia}\; b \; wrt \; s_{-i}^{*}$ and $a \;>=\; b \; wrt \; s_{-i}$ otherwise
- strict $\Rightarrow$ weak, because $\braket{>}$ satisfies both clauses at once
	- clause 1 ($a$ never worse): $x > y \Rightarrow x \geq y$, so $>$-everywhere gives $\geq$-everywhere for free
	- clause 2 ($a$ strictly better somewhere): strict dominance gives $a$ strictly better *everywhere*, so in particular at one $s_{-i}^{*}$
	- equivalently: weak $= \braket{\geq} \forall \; + \; > \; \exists$, while strict $= \braket{> \; \forall}$. strict is weak with all of the ties removed
	- the converse fails: weak permits ties, strict does not. so the only gap between the two definitions is in the weakly-dominated-but-not-strictly-dominated strategies
- same holds against mixed strategies: if $a$ strictly dominates $b$ then the degenerate mixture $\lambda_{a} = 1$ weakly dominates $b$, since $\sum_{k} \lambda_{k} U_{1}(k, s_{-i}) \geq U_{1}(b, s_{-i}) \; \forall s_{-i}$ and strict at every $s_{-i}$

1.e.1.d
Read dominance off the reduced-form table by comparing rows for Player 1 and columns for Player 2. Antonia, per column of hers:
- Mexican $\to \braket{3, 3, 2}$
- Italian $\to \braket{3, 2, 1}$
- Japanese $\to \braket{2, 1, 1}$
Bob, per row of his:
- Mexican $\to \braket{2, 2, 3}$
- Italian $\to \braket{2, 3, 1}$
- Japanese $\to \braket{3, 1, 1}$
Antonia:
- Mexican strictly dominates Japanese, since $\braket{3 > 2, \; 3 > 1, \; 2 > 1}$
- Mexican weakly but not strictly dominates Italian, since $\braket{3 = 3, \; 3 > 2, \; 2 > 1}$ — ties at Bob's Mexican
- Italian weakly but not strictly dominates Japanese, since $\braket{3 > 2, \; 2 > 1, \; 1 = 1}$ — ties at Bob's Japanese
Bob: no pair is comparable in either direction
- Mexican vs Italian $\braket{\geq, \; <, \; >}$ / Italian vs Mexican $\braket{\leq, \; >, \; <}$
- Mexican vs Japanese $\braket{<, \; >, \; >}$ / Japanese vs Mexican $\braket{>, \; <, \; <}$
- Italian vs Japanese $\braket{<, \; >, \; =}$ / Japanese vs Italian $\braket{>, \; <, \; =}$
Italian weakly dominates Mexican for Player 1 but strictly dominates Mexican for Player 2, since $\braket{2 = 2, \; 3 > 2}$ vs $\braket{2 = 2, \; 2 < 3}$. dominance is per-player, not a property of the column

1.e.1.e
*iterated elimination of strictly dominated strategies* (IESDS): delete every strictly dominated strategy, recompute, repeat, until nothing more can go. IESDS is **order independent** and never deletes a Nash equilibrium
- step 1: delete Antonia's Japanese (strictly dominated by Mexican), leaving
$$
\begin{array}{cc} \\
  & \text{Player 2 (Bob)} \\
\text{Player 1 (Antonia)} &
\begin{array}{|c|c|c|}
\hline
  & \text{Mexican} & \text{Italian} & \text{Japanese} \\
\hline
\text{Mexican}  & 3 \quad 2 & 3 \quad 2 & 2 \quad 3\\
\hline
\text{Italian}  & 3 \quad 2 & 2 \quad 3 & 1 \quad 1\\
\hline
\end{array}
\end{array}
$$
- step 2: stuck. Antonia's Mexican weakly dominates Italian and Bob's Italian weakly dominates Mexican, but nothing is *strictly* dominated anymore, so pure-strategy IESDS terminates here with $\braket{Mexican, Italian}$ and $\braket{Mexican, Japanese}$ both still on the board
- unique Nash equilibrium is $\braket{Mexican, Japanese} \to o_{3} = \braket{2, 3}$: Bob strictly prefers Japanese to both $\braket{3 > 2, \; 3 > 1}$ when Antonia plays Mexican, and Mexican is Antonia's best response to Japanese $\braket{2 > 1 = 1}$
- $\braket{Mexican, Mexican}$ is not an equilibrium, since Bob gains $2 \to 3$ by switching to Japanese

1.e.1.f
strictly dominated strategies can be deleted freely, weakly dominated ones cannot
- Antonia's Italian is weakly dominated by Mexican, yet $\braket{Italian, Mexican} \to o_{4} = \braket{3, 2}$ **is** a Nash equilibrium: both are best responses to each other. deleting Italian destroys it
- the rule: IESDS preserves every Nash equilibrium. iterated elimination of weakly dominated strategies may discard genuine ones, so use it only in the mixed form $\braket{\sum_{k} \lambda_{k} U_{i}(k, s_{-i}) \geq U_{i}(b, s_{-i}) \; \forall \; , \; > \; \exists}$, and then track the order of elimination
- tie caveat: weak dominance requires $\braket{a = b}$ somewhere, i.e. a tie *as a payoff*, which under an ordinal utility representation means indifference. so the criterion needs a utility or a tie-breaking refinement, not just the ordinal ranking $\braket{M >_{Antonia} I >_{Antonia} J}$