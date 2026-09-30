# Paper A: persistence

Audit the current manuscript statements and proofs, without repairing them. The full definitions, equation labels, model qualifications and surrounding mathematical claims are in `repaired_20260930.refs/paper.tex` (resolve as the sibling reference directory of this problem file). The blueprint transcribes the selected environments verbatim; paper.tex is authoritative if extraction creates ambiguity. All applicable model definitions and hypotheses from the paper are part of the problem. Do not assume another unreviewed mathematical result is established; check its supplied proof where needed. Introductory context and empirical/software fidelity claims are outside this proof audit. Audit the mathematical claims and reductions associated with these results, including claims made immediately after the statements. Do not read any ledger, factgraph, past verdict, unrelated notes or files outside Rethlas. Do not rerun existing certified computations.

Selected manuscript labels: thm:memory.

The complete candidate proof is in `reasoning/results/bittensor_paper_a/persistence_20260930/attempt2/blueprint.md`. All manuscript inputs are in `reasoning/data/bittensor_paper_a/repaired_20260930.refs/`. This is an independent LLM audit, not formal machine verification.

## Repair submission

This is the second submission of the same proof group, after the author's authorized repairs. The original manuscript, packets and first verdict are preserved separately. Audit the actual revised manuscript, including all boundaries; do not silently add arguments.

Additional established premise (exact, sympy): `repair_checks.json` records 14 exact clipping/reflection identities, the affine honest-continuation Bellman identity, a finite binary-channel Bayes identity, and the soft-threshold necessary-bound factorization and Bernstein upper bound. Accept only this displayed algebra. The strategy simulation, general conditional-expectation argument, filtration assumptions and infinite-horizon conclusion still require proof review.

## Revised statement: thm:memory

\begin{theorem}[Frontier with persistence]\label{thm:memory}
Let $\Lambda=(p/q)^n$ and let $\Pi\in[1/2,1)$ solve
$\Pi=\frac{1-\rho}2+\rho\frac{\Lambda\Pi}{1+(\Lambda-1)\Pi}$.
If $\Pi\ge p$, no rule of this kind supports honest evaluation. If $\Pi<p$, let
$G_\rho=2(p-\Pi)\Gs/d$; honest evaluation can be supported if and only if
$\eta\le G_\rho$. On this feasible domain the largest quality is
$Q^*_\rho(0)=\Qmaj$ at zero ownership; for $\omega>0$ it is
\[
Q^*_\rho(\omega)=\frac12+\Bigl(\Qmaj-\frac12\Bigr)\min\Bigl\{1,\frac{G_\rho-\eta}{\omega Mb\,(p-d\Pi)}\Bigr\},
\]
attained by repeating the damped majority rule with majority sharing. The
condition $\Pi\ge p$ holds if and only if
$\rho\ge\rho_c=d\,\frac{p^{n+1}+q^{n+1}}{p^{n+1}-q^{n+1}}$, and $\rho_c$
decreases to $d$ as $n$ grows.
\end{theorem}

