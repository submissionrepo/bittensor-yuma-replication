# Candidate proof packet

Verbatim theorem and proof environments from the manuscript. The complete source is supplied for all definitions and equations. No missing argument has been added.

# lemma thm:memory

## statement

Source paper.tex line 833.

\begin{theorem}[Frontier with persistence]\label{thm:memory}
Let $\Lambda=(p/q)^n$ and let $\Pi\in[1/2,1)$ solve
$\Pi=\frac{1-\rho}2+\rho\frac{\Lambda\Pi}{1+(\Lambda-1)\Pi}$.
If $\Pi\ge p$, no rule of this kind supports honest evaluation. If $\Pi<p$, let
$G_\rho=2(p-\Pi)\Gs/d$; honest evaluation can be supported if and only if
$\eta\le G_\rho$, and then the largest quality is
\[
Q^*_\rho(\omega)=\frac12+\Bigl(\Qmaj-\frac12\Bigr)\min\Bigl\{1,\frac{G_\rho-\eta}{\omega Mb\,(p-d\Pi)}\Bigr\},
\]
attained by repeating the damped majority rule with majority sharing. The
condition $\Pi\ge p$ holds if and only if
$\rho\ge\rho_c=d\,\frac{p^{n+1}+q^{n+1}}{p^{n+1}-q^{n+1}}$, and $\rho_c$
decreases to $d$ as $n$ grows.
\end{theorem}

## proof

Source paper.tex line 1294.

\begin{proof}[Proof of Theorem~\ref{thm:memory}]
We first bound what a validator can know. Before a new evaluation, its belief
$\pi$ that miner $1$ is better combines, from each past round, at most $n$
conditionally independent signals:
the other validators' reports and at most one signal of its own. The likelihood
ratio from one round lies in $[\Lambda^{-1},\Lambda]$, so with the Markov
transition the belief stays in $[1-\Pi,\Pi]$ under every deviation, and runs of
unanimous honest reports approach both ends. Because the rule ignores history,
a deviation changes future payoffs only through this belief, and the
equilibrium conditions are the static ones at each belief. Let $W_1(\pi)$ be the
expected payment of reporting miner $1$ blindly at belief $\pi$. It is affine
in $\pi$, and it equals $V/n$ at $\pi=p$, because the belief after one's own
signal $1$ is $p$ and honest pay given that signal is $V/n$ by symmetry. Hence
\[
\frac Vn-W_1(\pi)=\frac{2(p-\pi)}{d}\,G(v).
\]
Reporting miner $1$ blindly raises its expected share by
$(\pi q+(1-\pi)p)H(a)=(p-d\pi)H(a)$ over honest evaluation, so the constraint at
belief $\pi$ is $2(p-\pi)G(v)/d\ge\eta+\omega M(p-d\pi)H(a)$. The ratio
$[2(p-\pi)G(v)/d-\eta]/(p-d\pi)$ has derivative
$-(4pqG(v)/d+d\eta)/(p-d\pi)^2<0$, so the binding belief is $\pi=\Pi$. If
$\Pi\ge p$ the left side is nonpositive there, which rules out $\eta>0$.
Otherwise the constraint at $\Pi$ and Lemma~\ref{lem:rent} give
$\omega M(p-d\Pi)H(a)\le2(p-\Pi)G(v)/d-\eta\le G_\rho-\eta$, and
Lemma~\ref{lem:influence} turns this bound on $H(a)$ into the bound
$Q^*_\rho(\omega)$ on quality, which the damped majority rule with majority
sharing attains. Setting $\Pi=p$ in the fixed-point equation gives
\[
\rho_c=d\,\frac{p^{n+1}+q^{n+1}}{p^{n+1}-q^{n+1}}.\qedhere
\]
\end{proof}
