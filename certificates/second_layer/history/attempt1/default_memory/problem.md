# Paper A: default memory

Audit the current manuscript statements and proofs, without repairing them. The full definitions, equation labels, model qualifications and surrounding mathematical claims are in `current_20260930.refs/paper.tex` (resolve as the sibling reference directory of this problem file). The blueprint transcribes the selected environments verbatim; paper.tex is authoritative if extraction creates ambiguity. All applicable model definitions and hypotheses from the paper are part of the problem. Do not assume another unreviewed mathematical result is established; check its supplied proof where needed. Introductory context and empirical/software fidelity claims are outside this proof audit. Audit the mathematical claims and reductions associated with these results, including claims made immediately after the statements. Do not read any ledger, factgraph, past verdict, unrelated notes or files outside Rethlas. Do not rerun existing certified computations.

Selected manuscript labels: thm:default.

The complete candidate proof is in `reasoning/results/bittensor_paper_a/default_memory_20260930/blueprint.md`. All manuscript inputs are in `reasoning/data/bittensor_paper_a/current_20260930.refs/`. This is an independent LLM audit, not formal machine verification.

## Established algebraic premises

Accept the following first-layer calculations only within their explicit domains. They do not establish the state reduction, endpoint sufficiency, reflection, acquisition optimality or infinite-horizon argument. Review those arguments in the manuscript. Saved outputs and generating scripts are in the reference directory.

P1 (established layers: exact, sympy): All 324 rational interval inequalities at the stated D endpoints/report intervals/positive-part branches have positive denominators and nonnegative Bernstein coefficients. Eighty-four exact epoch comparisons and the fresh-payment, fresh-share and state-potential identities pass.

P2 (established layers: exact, sympy): Eighteen allocation derivative bounds, one strict hard-report interval bound and the ell=2/5 ten-round finite-history deviation pass exact algebra. Full discounted gain is 1346965493913734921202558254069/4862851903431954529117440000000000000; positive ownership/cost constants are exact.

P3 (established layers: exact, sympy): The dynamic pooling potential residual exactly equals three nonpositive terms; the ownership cap simplifies to the displayed formula and equals 8218/8175 at n=3,alpha=1/10,delta=99/100,V=M; 256 rational three-period report paths verify the orientation comparison.

P4 (established layers: exact, sympy): Under classic zero-column post-EMA normalization, n=3,p=3/4,alpha=1/10,delta=99/100,rho=0,initial B=1/3 and fixed extreme future reports, a zero-owner validator with signal 0 gains 53506799/2288569920 by reporting 1/100 instead of 0.

## Original statement: thm:default

\begin{theorem}[Default parameters]\label{thm:default}
Let $n=3$, $p=3/4$, $V=M=1/2$, $\alpha=1/10$, discount factor $\delta=99/100$,
the state $\theta$ drawn independently in each round, and every initial bond
equal to $1/3$. In the repeated game:
\begin{enumerate}
\item For every $\ell\in[0,2/5]$, $\ell$-honesty is not a Nash equilibrium when
all ownership is zero.
\item $\tfrac{49}{100}$-honesty is a Nash equilibrium whenever
$|\beta_i|\le1/2000$ for all $i$ and $0\le\eta\le1/400000$. Its quality is
$241237/476800$.
\item Not evaluating and submitting weight $1/2$ on each miner in every round
is a Nash equilibrium for every $\eta\ge0$ and every ownership profile with
$|\beta_i|\le1$.
\end{enumerate}
\end{theorem}
