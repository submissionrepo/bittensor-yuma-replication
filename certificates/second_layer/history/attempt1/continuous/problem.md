# Paper A: continuous

Audit the current manuscript statements and proofs, without repairing them. The full definitions, equation labels, model qualifications and surrounding mathematical claims are in `current_20260930.refs/paper.tex` (resolve as the sibling reference directory of this problem file). The blueprint transcribes the selected environments verbatim; paper.tex is authoritative if extraction creates ambiguity. All applicable model definitions and hypotheses from the paper are part of the problem. Do not assume another unreviewed mathematical result is established; check its supplied proof where needed. Introductory context and empirical/software fidelity claims are outside this proof audit. Audit the mathematical claims and reductions associated with these results, including claims made immediately after the statements. Do not read any ledger, factgraph, past verdict, unrelated notes or files outside Rethlas. Do not rerun existing certified computations.

Selected manuscript labels: thm:hedging, prop:soft.

The complete candidate proof is in `reasoning/results/bittensor_paper_a/continuous_20260930/blueprint.md`. All manuscript inputs are in `reasoning/data/bittensor_paper_a/current_20260930.refs/`. This is an independent LLM audit, not formal machine verification.

## Original statement: thm:hedging

\begin{theorem}[Hedging]\label{thm:hedging}
Let bond memory be switched off and evaluation be free. For
$k\in\{0,\dots,2m\}$ let
$w_k=\binom{2m}{k}\bigl(p^{2m-k+1}q^k+q^{2m-k+1}p^k\bigr)$, the probability
that $k$ of the other $2m$ validators report $1$ given that one's own signal
is $0$, and let
\[
S_n(p)=\sum_{k<m}w_k\frac{n-k-1}{(n-k)^2}-\sum_{k>m}\frac{w_k}{k}.
\]
Then $0$-honesty is an equilibrium against all weights in $[0,1]$ if and only
if $\omega\le\KY$, where $\KY=VS_n(p)/(Mb)$. Moreover $\KY<K$, and for $n=3$,
\[
\KY=\frac VM\cdot\frac{4-21pq}{36pq}.
\]
\end{theorem}

## Original statement: prop:soft

\begin{proposition}[Softer weights]\label{prop:soft}
Let $n=3$, $V=M$, $p=3/4$, bond memory switched off and evaluation free. For
$\ell\in[0,1/2)$, $\ell$-honesty is an equilibrium against all weights in
$[0,1]$ if and only if $\omega\le\tau(\ell)$, where
\[
\tau(\ell)=\frac{2(28\ell^2+56\ell+1)}{3(28\ell^3+56\ell^2+127\ell+72)} .
\]
The tolerance $\tau$ increases from $\tau(0)=1/108$ to $\tau(1/2)=8/51$, and the
quality of $\ell$-honesty,
$\QY(\ell)=\frac12+\frac12\bigl(\frac12-\ell\bigr)\bigl(\frac{13}{16}+\frac{9}{16(1+\ell)}\bigr)$,
decreases from $27/32$ to $1/2$.
\end{proposition}
