# Paper A: capacity

Audit the current manuscript statements and proofs, without repairing them. The full definitions, equation labels, model qualifications and surrounding mathematical claims are in `repaired_20260930.refs/paper.tex` (resolve as the sibling reference directory of this problem file). The blueprint transcribes the selected environments verbatim; paper.tex is authoritative if extraction creates ambiguity. All applicable model definitions and hypotheses from the paper are part of the problem. Do not assume another unreviewed mathematical result is established; check its supplied proof where needed. Introductory context and empirical/software fidelity claims are outside this proof audit. Audit the mathematical claims and reductions associated with these results, including claims made immediately after the statements. Do not read any ledger, factgraph, past verdict, unrelated notes or files outside Rethlas. Do not rerun existing certified computations.

Selected manuscript labels: thm:capacity.

The complete candidate proof is in `reasoning/results/bittensor_paper_a/capacity_20260930/attempt2/blueprint.md`. All manuscript inputs are in `reasoning/data/bittensor_paper_a/repaired_20260930.refs/`. This is an independent LLM audit, not formal machine verification.

## Repair submission

This is the second submission of the same proof group, after the author's authorized repairs. The original manuscript, packets and first verdict are preserved separately. Audit the actual revised manuscript, including all boundaries; do not silently add arguments.

## Revised statement: thm:capacity

\begin{theorem}[Premium capacity]\label{thm:capacity}
For $j=m+2,\dots,n$ let
$R_j=\frac{Vd}{2}\bigl(p^{j-1}q^{n-j}-q^{j-1}p^{n-j}\bigr)$, and for
$k=0,\dots,n$ let
\[
C_k=\sum_{j=m+2}^{n}\Bigl[\binom nj-\binom{n-k}{j}\Bigr]R_j .
\]
A vector $(g_1,\dots,g_n)\ge0$ satisfies $G_i(v)\ge g_i$ for all $i$ under
some payment rule if and only if $\sum_{i\in T}g_i\le C_{|T|}$ for every set
$T$ of validators. The total capacity is $C_n=n\Gs$.
\end{theorem}

