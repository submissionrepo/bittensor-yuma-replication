# Paper A: static

Audit the current manuscript statements and proofs, without repairing them. The full definitions, equation labels, model qualifications and surrounding mathematical claims are in `current_20260930.refs/paper.tex` (resolve as the sibling reference directory of this problem file). The blueprint transcribes the selected environments verbatim; paper.tex is authoritative if extraction creates ambiguity. All applicable model definitions and hypotheses from the paper are part of the problem. Do not assume another unreviewed mathematical result is established; check its supplied proof where needed. Introductory context and empirical/software fidelity claims are outside this proof audit. Audit the mathematical claims and reductions associated with these results, including claims made immediately after the statements. Do not read any ledger, factgraph, past verdict, unrelated notes or files outside Rethlas. Do not rerun existing certified computations.

Selected manuscript labels: lem:ic, lem:rent, lem:influence, thm:frontier, prop:binary, lem:inherit.

The complete candidate proof is in `reasoning/results/bittensor_paper_a/static_20260930/blueprint.md`. All manuscript inputs are in `reasoning/data/bittensor_paper_a/current_20260930.refs/`. This is an independent LLM audit, not formal machine verification.

## Original statement: lem:ic

\begin{lemma}[Incentive constraint]\label{lem:ic}
A rule $(a,v)\in\Rset$ supports honest evaluation at cost $\eta$ and ownership
bound $\omega$ if and only if
\[
\eta+\tfrac12\,\omega M H(a)\le G(v).
\]
\end{lemma}

## Original statement: lem:rent

\begin{lemma}[Premium cap]\label{lem:rent}
Every rule $(a,v)\in\Rset$ has $G(v)\le\Gs$, where
\[
\Gs=\frac{Vd(\Qmaj-p)}{2npq},
\]
and majority sharing attains $G(v)=\Gs$.
\end{lemma}

## Original statement: lem:influence

\begin{lemma}[Quality per unit of influence]\label{lem:influence}
Every allocation $a$ of a rule in $\Rset$ satisfies $Q(a)\le\Qmaj$ and
\[
Q(a)-\frac12\le\frac{\Qmaj-1/2}{b}\,H(a).
\]
\end{lemma}

## Original statement: thm:frontier

\begin{theorem}[Frontier]\label{thm:frontier}
Let $0\le\eta\le\Gs$ and $\omega>0$. The largest quality of a rule in $\Rset$
that supports honest evaluation at cost $\eta$ and ownership bound $\omega$ is
\[
Q^*(\omega)=\frac12+\Bigl(\Qmaj-\frac12\Bigr)\min\Bigl\{1,\frac{2(\Gs-\eta)}{\omega Mb}\Bigr\}.
\]
The damped majority rule of strength
$\lambda^*=\min\{1,2(\Gs-\eta)/(\omega Mb)\}$ with majority sharing attains it.
\end{theorem}

## Original statement: prop:binary

\begin{proposition}[All-or-nothing weights]\label{prop:binary}
With bond memory switched off, $0$-honest reports make Yuma pay miners by the
majority rule and validators by majority sharing. Hence $0$-honesty is an
equilibrium against all reports in $\{0,1\}$ if and only if
$\eta+\frac12\omega Mb\le\Gs$; with free evaluation, if and only if
$\omega\le K$.
\end{proposition}

## Original statement: lem:inherit

\begin{lemma}[Yuma stays inside the frontier]\label{lem:inherit}
Let bond memory be switched off and let $\ell$-honesty be an equilibrium for
some $\ell\in[0,1/2)$ at cost $\eta$ and ownership bound $\omega$. The map from
the number of validators whose signal names miner $1$ to Yuma's allocation and
payments is a rule in $\Rset$ that supports honest evaluation. In particular,
the quality of $\ell$-honesty is at most $Q^*(\omega)$.
\end{lemma}
