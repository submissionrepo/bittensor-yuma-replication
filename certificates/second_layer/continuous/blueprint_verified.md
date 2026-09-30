# Candidate proof packet: repaired manuscript

Verbatim environments and application text. The accompanying full manuscript is authoritative; no additional proof is supplied here.

## thm:hedging

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

Source paper.tex line 1024.

\begin{proof}[Proof of Theorem~\ref{thm:hedging}]
Let the validator have signal $0$ and weight $x$ on miner $1$. When $k<m$
others report $1$, the medians are $0$ on miner $1$ and $1$ on miner $0$, so
the validator's weight on miner $1$ is clipped away, miner $0$ receives $M$,
and the validator holds $(1-x)/(n-k-x)$ of miner $0$. When $k>m$, it holds
$x/(k+x)$ of miner $1$, which receives $M$. When $k=m$, its weight $x$ is the
median on miner $1$, the other $m$ supporters of miner $1$ are clipped to $x$,
miner $1$ receives $xM$, and the validator holds $1/(m+1)$ of each miner
with positive clipped weight. At $x=0$ or $1$, the zero column contributes
nothing; the payment is still $V/(m+1)$. This gives Table~\ref{tab:cases}. The validator's signal-$0$ gain of weight $x$ over
weight $0$ is
\[
F_\beta(x)=Vx\Bigl[\sum_{k>m}\frac{w_k}{k+x}-\sum_{k<m}\frac{w_k(n-k-1)}{(n-k)(n-k-x)}\Bigr]+\beta Mw_mx,
\]
and $w_m=b$. The maps $x\mapsto x/(k+x)$ and $x\mapsto(1-x)/(n-k-x)$ are
strictly concave on $[0,1]$, so $F_\beta$ is strictly concave, and $F_\beta(0)=0$.
Weight $0$ is optimal against every $|\beta|\le\omega$ if and only if
$F_\omega'(0)=-VS_n(p)+\omega Mb\le0$, that is, $\omega\le\KY$. The same holds
for signal $1$ by symmetry. With free evaluation, a validator who does not
evaluate and submits weight $x$ earns the average of the payoffs that weight
$x$ earns under the two signals, and each of these is at most the honest payoff
for that signal; so skipping the evaluation does not pay either. To compare
$\KY$ with $K$, note that $F_0(1)$ is the payment loss from reporting against
one's signal, which is
$-2\Gs$ under majority sharing (proof of Lemma~\ref{lem:ic}), and strict
concavity gives $F_0'(0)>F_0(1)-F_0(0)=-2\Gs$, so $VS_n(p)<2\Gs$ and $\KY<K$.
For $n=3$ we have $w_0=p^3+q^3=1-3pq$, $w_2=pq$ and $b=2pq$, so
\[
S_3(p)=\frac{2w_0}{9}-\frac{w_2}{2}=\frac{4-21pq}{18},
\qquad
\KY=\frac{VS_3(p)}{Mb}=\frac VM\cdot\frac{4-21pq}{36pq}.
\qedhere
\]
\end{proof}

## prop:soft

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

Source paper.tex line 1059.

\begin{proof}[Proof of Proposition~\ref{prop:soft}]
We fix a validator with signal $0$, write $t=pq$ and $u=1-3t$, and let the
other two validators be $\ell$-honest. Given the validator's signal, the other
two put weight $\ell$, one $\ell$ and one $1-\ell$, or $1-\ell$ on miner $1$
with probabilities $u$, $2t$ and $t$. Let $v(x)$ be the validator's expected
payment divided by $V$ and $i(x)$ miner $1$'s expected share when it puts weight
$x$ on miner $1$. Computing the medians and the clipping as in
Table~\ref{tab:round} gives, for $x\le\ell$,
\begin{align*}
v_L&=u\tfrac{1-\ell+x}{3-\ell+x}+t\tfrac{2-\ell+3x}{2+\ell+x},\\
i_L&=u\tfrac{x+2\ell}{3-\ell+x}+t\tfrac{2+2\ell+3x}{2+\ell+x};
\end{align*}
for $\ell\le x\le1-\ell$,
\begin{align*}
v_C&=u\tfrac{1-x+\ell}{3-x+\ell}+t\tfrac{\ell+x}{2+\ell+x}+\tfrac{t}{1+\ell},\\
i_C&=\tfrac{3u\ell}{3-x+\ell}+t\bigl(1-\tfrac{3\ell}{2+\ell+x}\bigr)+\tfrac{t(\ell+2x)}{1+\ell};
\end{align*}
and for $x\ge1-\ell$,
\begin{align*}
v_R&=\tfrac{u(1-x+\ell)+2t(2-\ell-x)}{3-x+\ell}+t\tfrac{2-\ell-x}{4-\ell-x},\\
i_R&=\tfrac{3u\ell+2t(2-\ell)}{3-x+\ell}+\tfrac{3t(1-\ell)}{4-\ell-x}.
\end{align*}
The pieces agree at the interfaces, and $v_C(\ell)=1/3$. With $V=M$ and
ownership $\beta$, the gain of weight $x$ over weight $\ell$ is
$V\{v(x)-v(\ell)+\beta[i(x)-i(\ell)]\}$. Since $i$ increases in $x$, the worst
ownership is $+\omega$ for moves to the right and $-\omega$ for moves to the
left.

\emph{Necessary bound.} On the middle interval, with $\beta=\omega$, the derivative of the gain is
\[
\frac{u(-2+3\omega\ell)}{(3-x+\ell)^2}+\frac{t(2+3\omega\ell)}{(2+\ell+x)^2}+\frac{2\omega t}{1+\ell}.
\]
At $x=\ell$ its coefficient of $\omega$ is positive. A necessary condition
for equilibrium is therefore $\omega\le C_C(\ell)$, where
\[
C_C(\ell)=\frac{2u/9-t/[2(1+\ell)^2]}{u\ell/3+3\ell t/[4(1+\ell)^2]+2t/(1+\ell)} .
\]
For $p=3/4$, this bound is $C_C(\ell)=\tau(\ell)\le8/51<1$.
\emph{Sufficiency.} We henceforth take $0\le\omega\le C_C(\ell)$.
The middle derivative then has a negative first coefficient and a positive
second coefficient, so it decreases in $x$ and remains nonpositive.
On the left interval, with $\beta=-\omega$, the derivative is
$A_L/(3-\ell+x)^2+B_L/(2+\ell+x)^2$ with $A_L=u[2-3\omega(1-\ell)]$ and
$B_L=t[4(1+\ell)-\omega(4+\ell)]\ge3t\ell$. If $A_L\ge0$ it is positive. If
$A_L<0$ we multiply by $(2+\ell+x)^2$; the negative term then carries the factor
$[(2+\ell+x)/(3-\ell+x)]^2$, which increases in $x$, so nonnegativity at
$x=\ell$ controls the interval and gives $\omega\le C_L(\ell)$ with
\[
C_L(\ell)=\frac{2u/9+t/(1+\ell)}{u(1-\ell)/3+t(4+\ell)/[4(1+\ell)^2]} .
\]
On the right interval, with $\beta=\omega$, the derivative is
$C_R/(3-x+\ell)^2+D_R/(4-\ell-x)^2$ with
$C_R=u(-2+3\omega\ell)+2t[-(1+2\ell)+\omega(2-\ell)]$ and
$D_R=t[-2+3\omega(1-\ell)]$. The coefficient $C_R$ increases in $\omega$ and
equals $-(1-4t)(2-3\ell)-3t\ell\le0$ at $\omega=1$. The derivative jumps down at
$x=1-\ell$, so it is nonpositive just right of the interface whenever the
middle condition holds; if $D_R\le0$ it stays nonpositive, and if $D_R>0$ the
factor $[(3-x+\ell)/(4-\ell-x)]^2$ multiplying the positive term after scaling
by $(3-x+\ell)^2$ decreases in $x$, which again keeps the sign. The right
interval therefore adds no condition. With free evaluation, skipping the
evaluation does not pay once the reporting conditions hold, by the averaging
argument in the proof of Theorem~\ref{thm:hedging}. At $p=3/4$ we have
$C_L>C_C$ on $[0,1/2)$ and $C_C=\tau$, and the allocation formula of
Lemma~\ref{lem:inherit} gives
\[
\QY(\ell)=\frac12+d\Bigl(\frac12-\ell\Bigr)\Bigl(1-t+\frac{3t}{1+\ell}\Bigr).\qedhere
\]
\end{proof}

