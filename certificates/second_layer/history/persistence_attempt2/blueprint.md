# Candidate proof packet: repaired manuscript

Verbatim environments and application text. The accompanying full manuscript is authoritative; no additional proof is supplied here.

## thm:memory

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

Source paper.tex line 1289.

\begin{proof}[Proof of Theorem~\ref{thm:memory}]
We first bound the pre-acquisition belief $\pi$. Each round reveals at most
$n$ fresh signals, giving likelihood ratio in $[\Lambda^{-1},\Lambda]$.
The Markov transition confines $\pi$ to $[1-\Pi,\Pi]$; unanimous honest
histories approach both endpoints. A blind report $1$ has affine validation
pay $W_1(\pi)$, with $W_1(1/2)=V/n-G(v)$ and $W_1(p)=V/n$ by symmetry.
Its miner-allocation gain is $(p-d\pi)H(a)$, giving
$2(p-\pi)G(v)/d\ge\eta+\omega M(p-d\pi)H(a)$.
The label-flipped constraint covers report $0$. Blind-report losses equal
probability-weighted conditional misreport losses, so neither acquired
misreports nor mixtures gain.

For fixed $\beta_i$, honest flow payoff is
$V/n-\eta+\beta_iM[1-Q+(2Q-1)\pi]$, $Q=Q(a)$.
Iterating affine Markov prediction and discounting therefore gives an
affine bounded honest continuation value $U(\pi)$.
For every current policy, $\E[\pi'\mid\text{history}]=(1-\rho)/2+\rho\pi$,
so affine $U$ makes expected continuation independent of acquisition and
reporting. The current constraints give
$\E[u_i+\delta U(\pi')\mid\text{history}]\le U(\pi)$.
Bounded $U$ lets this telescope for arbitrary randomized history-dependent
deviations. A strict endpoint violation yields a profitable one-round
deviation at a finite unanimous history, followed by honest play.

Feasibility implies $G(v)\ge\eta>0$. The ratio
$[2(p-\pi)G(v)/d-\eta]/(p-d\pi)$ has derivative
$-(4pqG(v)/d+d\eta)/(p-d\pi)^2<0$, so $\Pi$ binds.
If $\Pi\ge p$, positive cost is infeasible. Otherwise
Lemmas~\ref{lem:rent} and~\ref{lem:influence} give the frontier, attained by
damped majority and majority sharing; at $\omega=0$, full majority is feasible
exactly when $\eta\le G_\rho$. Setting $\Pi=p$ in its fixed-point equation gives
$\rho_c=d(p^{n+1}+q^{n+1})/(p^{n+1}-q^{n+1})$.\qedhere
\end{proof}

