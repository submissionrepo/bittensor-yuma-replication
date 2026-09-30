# Candidate proof packet

Verbatim theorem and proof environments from the manuscript. The complete source is supplied for all definitions and equations. No missing argument has been added.

# lemma thm:default

## statement

Source paper.tex line 722.

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

## proof

Source paper.tex line 738.

\begin{proof}[Proof sketch]
Appendix~\ref{app:yuma} lists the certificates; here we outline the argument.
For part~(ii) we fix the other two validators at $\ell=49/100$. A deviator's
state reduces to the difference $D$ between its bonds in the two miners, and
$|D|\le1/2$ under every deviation. In units of $V$, the old bonds contribute
$(1-\alpha)D(I-\frac12)$ to the round's payoff, where $I$ is miner $1$'s share. We let $\psi(D,x)$ be the deviator's
one-round payoff from weight $x$, including the value of the bonds it buys, and
choose the potential $\Phi(D)=\frac1{20}\bigl(|D|-\frac1{20}\bigr)_+$. For all
$D\in[-1/2,1/2]$ and $x\in[0,1]$,
\[
\psi(D,x)-\psi(D,\ell)+\delta\,\E\Phi(D')-\Phi(D)\le-\varepsilon|x-\ell|,\qquad \varepsilon=\frac1{1000},
\]
where $D'$ is the next bond difference. The inequality splits into $324$
univariate rational inequalities, each certified by nonnegative Bernstein
coefficients. Summing it over rounds telescopes the potential and bounds every
multi-round deviation by the payoff of $\ell$-honesty. Ownership up to $1/2000$
uses part of the margin $\varepsilon$, and skipping the evaluation loses at
least $\varepsilon(1-2\ell)/2$ per round, which covers the cost. For part~(i),
a finite run of rounds in which the deviator's signal is $1$ and the others'
are $0$ pushes $D$ toward its honest maximum, where the payoff's right
derivative in $x$ at $x=\ell$ is positive for every $\ell\in(0,2/5]$; the case
$\ell=0$ fails in the first round. For part~(iii), when the others submit $1/2$
a deviator's current share of each miner never exceeds $1/n$, so no deviation
earns more than $V/n$ per round in validator pay. A reflection argument bounds
what a deviator gains through its ownership, and the ownership share this
equilibrium tolerates is
\[
\frac VM\cdot\frac{2\alpha(n-1)}{n}\cdot\frac{1-\delta(1-\alpha)/(2n-1)}{1-\delta(1-\alpha)}=\frac{8218}{8175}>1.\qedhere
\]
\end{proof}

Source paper.tex line 1155.

\begin{proof}[Proof of Theorem~\ref{thm:default}]
The Bernstein certificates, the $18$ derivative bounds and the profitable
deviations are in the replication package; here we assemble the argument.
Throughout, the other two validators are $\ell$-honest and we follow one
deviator. We write $r=1-\alpha$ and $z=\delta r$, let $B_1,B_0$ be the deviator's
bonds, and set $S=B_1+B_0$ and $D=B_1-B_0$. For weight $x$ and a count $k$ of
other reports for miner $1$, let $I(x,k)$ be miner $1$'s share and
$\Delta_j(x,k)$ the deviator's current share of miner $j$. The other validators
put weight at least $\ell>0$ on each miner, so every miner has positive clipped
weight and the bonds evolve as $B_j'=rB_j+\alpha\Delta_j$. With three
equal-stake validators a clipped weight never exceeds the sum of the other two,
so $\Delta_j\le1/2$ and $|D|\le1/2$ under every deviation.

\emph{Reduction.} In units of $V$ the deviator's current pay is
$r\{S/2+D(I-\frac12)\}+\alpha\{I\Delta_1+(1-I)\Delta_0\}$. We add the value
$\delta\kappa S'$ and subtract $\kappa S$ with $\kappa=r/(2(1-z))$, which removes
$S$ and leaves the one-round payoff
\begin{equation}\label{eq:reduced}
R(D,x,k)=rD\Bigl(I-\frac12\Bigr)+\alpha\Bigl\{I\Delta_1+(1-I)\Delta_0+\frac{z(\Delta_1+\Delta_0)}{2(1-z)}\Bigr\}.
\end{equation}

\emph{Potential.} Let $\psi(D,x)$ be the expectation of $R$ given signal $0$
and $\Phi(D)=\frac1{20}(|D|-\frac1{20})_+$. For $\ell=49/100$, all
$D\in[-\frac12,\frac12]$ and all $x\in[0,1]$,
\begin{equation}\label{eq:potential}
\psi(D,x)-\psi(D,\ell)+\delta\,\E\Phi(D')-\Phi(D)\le-\varepsilon|x-\ell|,\qquad \varepsilon=\frac1{1000}.
\end{equation}
For fixed $x$ the left side is convex in $D$ on each of the intervals with
endpoints $-\frac12,-\frac1{20},\frac1{20},\frac12$, so the four endpoints
suffice. On each of the report intervals $[0,\ell]$, $[\ell,1-\ell]$ and
$[1-\ell,1]$ the quantities $I$ and $\Delta_j$ are rational in $x$, and the
three positive parts in $\E\Phi(D')$ split into $27$ affine branches. The
resulting $4\cdot3\cdot27=324$ univariate rational inequalities have positive
denominators and nonnegative Bernstein coefficients on their intervals. The
inequality for signal $1$ follows by symmetry.

\emph{All deviations.} Averaging~\eqref{eq:potential} over the two signals, a
deviator who evaluates satisfies $\E[R-c+\delta\Phi(D')]-\Phi(D)\le C-c$, where
$c=\eta/V$ and $C=\alpha/(3(1-z))$ is the average payoff of $\ell$-honesty. A
deviator who does not evaluate cannot condition $x$ on the signal, and
$\frac12(|x-\ell|+|x-1+\ell|)\ge\frac12-\ell$, so its bound is
$C-\varepsilon(\frac12-\ell)\le C-c$ whenever $c\le\varepsilon(\frac12-\ell)=10^{-5}$.
Multiplying by $\delta^t$ and summing over rounds telescopes the potential.
Since $\Phi(0)=0$ and $\Phi$ is bounded, every deviation earns at most
$(V/3-\eta)/(1-\delta)$, which $\ell$-honesty attains. With ownership
$\beta_i$ the round's payoff gains $\beta_i(M/V)[i(x)-i(\ell)]$. On all nine
branches $0\le\partial I/\partial x\le1$, so this term is at most
$\omega(M/V)|x-\ell|$, and~\eqref{eq:potential} holds with margin
$\varepsilon-\omega M/V\ge1/2000$ when $\omega\le1/2000$ and $V=M$; the margin
covers costs up to $V\cdot\frac1{2000}(\frac12-\ell)=1/400000$. Along honest play
$|D|\le d_*=4/453<1/20$, so the potential vanishes on the equilibrium path. This
proves part~(ii); the quality is $\QY(49/100)$.

\emph{Part (i).} After $T$ rounds in which the deviator's signal is $1$ and the
others' are $0$, an event of probability $(3/32)^T$, the lean is
$D_T=(1-r^T)d_*$ with $d_*=2(1-2\ell)/(3(2-\ell))$. At $D=d_*$ and signal $0$,
the right derivative of $\psi(D,\cdot)$ at $x=\ell$ is a rational function of
$\ell$ whose numerator, after multiplication by $\ell$, has positive Bernstein
coefficients on $[0,\frac25]$, so it is positive for every
$\ell\in(0,\frac25]$. By continuity in $D$ it stays positive at $D_T$ for a finite
$T$, and after that history a slightly larger weight on miner $1$, followed by
$\ell$-honesty, is strictly profitable. For $\ell=0$ the deviation pays in the
first round: with signal $0$ and equal initial bonds, weight $1/100$ on
miner $1$ raises the discounted payoff by $53506799/2288569920$.

\emph{Part (iii).} If the others put weight $\frac12$ on each miner, a
deviator's current share of each miner is at most $1/n$ whatever its weight,
and the rate-$\alpha$ average keeps its bonds at most $1/n$. Its validator pay is
therefore at most $V/n$ per round, which not evaluating and submitting $\frac12$
attains. A reflection argument bounds the gain from ownership, and with $n=3$,
$\alpha=\frac1{10}$, $\delta=\frac{99}{100}$ and $V=M$ the tolerated ownership is
\[
\frac VM\cdot\frac{2\alpha(n-1)}{n}\cdot\frac{1-\delta(1-\alpha)/(2n-1)}{1-\delta(1-\alpha)}=\frac{8218}{8175}>1.\qedhere
\]
\end{proof}
