# Candidate proof packet: repaired manuscript

Verbatim environments and application text. The accompanying full manuscript is authoritative; no additional proof is supplied here.

## lem:ic

\begin{lemma}[Incentive constraint]\label{lem:ic}
A rule $(a,v)\in\Rset$ supports honest evaluation at cost $\eta$ and ownership
bound $\omega$ if and only if
\[
\eta+\tfrac12\,\omega M H(a)\le G(v).
\]
\end{lemma}

Source paper.tex line 910.

\begin{proof}[Proof of Lemma~\ref{lem:ic}]
We check the two kinds of deviation in turn, starting with a validator who
evaluated and holds signal $s$. The symmetry
$v_{0,k}=v_{1,n-k}$ makes the expected payment of reporting $s$ exceed that of
reporting $1-s$ by $2G(v)$ for either signal. The increments
$a_{k+1}-a_k$ are symmetric under $k\mapsto n-1-k$, so switching the report
changes the expected share of miner $1$ by $H(a)$ conditional on either signal.
Against the worst sign of ownership, honest reporting after evaluation is
optimal if and only if
\begin{equation}\label{eq:after}
2G(v)-\omega MH(a)\ge0 .
\end{equation}
A validator who skips the evaluation earns the same expected payment from
either fixed report. Under honest evaluation miner $1$'s expected share is
$1/2$, and a fixed report for miner $1$ raises it by $H(a)/2$. Skipping also
saves $\eta$, so evaluation beats every blind report if and only if
$G(v)-\frac12\omega MH(a)-\eta\ge0$. A randomized blind report is a mixture of
the two fixed reports, randomized reports after evaluation are mixtures of pure
reports for each signal, and randomizing the evaluation decision cannot beat
the better pure decision. Because $\eta\ge0$, the last condition already
implies~\eqref{eq:after}:
\[
2G(v)-\omega MH(a)\ge2\eta\ge0 .\qedhere
\]
\end{proof}

## lem:rent

\begin{lemma}[Premium cap]\label{lem:rent}
Every rule $(a,v)\in\Rset$ has $G(v)\le\Gs$, where
\[
\Gs=\frac{Vd(\Qmaj-p)}{2npq},
\]
and majority sharing attains $G(v)=\Gs$.
\end{lemma}

Source paper.tex line 936.

\begin{proof}[Proof of Lemma~\ref{lem:rent}]
By the budget~\eqref{eq:budget} and the equal treatment of validators, the
premium is $V/n$ minus the blind payment $\sum_jh_jv_{1,1+j}$, so we minimize
the latter. Write $t_k=v_{1,k}$. The symmetries give
$kt_k+(n-k)t_{n-k}=V$. For $1\le k\le m$ we eliminate $t_{n-k}$ from each pair;
using $h_j=h_{n-1-j}$, the coefficient of $t_k$ in the blind payment is
\[
h_{k-1}-\frac{k}{n-k}\,h_k=\frac12\binom{n-1}{k-1}(p-q)\bigl(q^{k-1}p^{n-k-1}-p^{k-1}q^{n-k-1}\bigr)>0,
\]
since $p>q$ and $n-k-1>k-1$. We therefore set $t_k=0$ and $t_{n-k}=V/(n-k)$ for
$1\le k\le m$; unanimity fixes $t_n=V/n$. This is majority sharing. Its blind
payment follows from $\frac1k\binom{n-1}{k-1}=\frac1n\binom nk$:
\[
\sum_jh_j\,v_{1,1+j}=\frac{V}{2n}\Bigl(\frac{\Qmaj}{p}+\frac{1-\Qmaj}{q}\Bigr),
\]
and therefore
\[
\frac Vn-\frac{V}{2n}\Bigl(\frac{\Qmaj}{p}+\frac{1-\Qmaj}{q}\Bigr)=\frac{Vd(\Qmaj-p)}{2npq}.
\qedhere
\]
\end{proof}

## lem:influence

\begin{lemma}[Quality per unit of influence]\label{lem:influence}
Every allocation $a$ of a rule in $\Rset$ satisfies $Q(a)\le\Qmaj$ and
\[
Q(a)-\frac12\le\frac{\Qmaj-1/2}{b}\,H(a).
\]
\end{lemma}

Source paper.tex line 958.

\begin{proof}[Proof of Lemma~\ref{lem:influence}]
The first bound holds profile by profile: given $k$ reports for miner $1$, the
posterior that miner $1$ is better exceeds $1/2$ exactly when $k>n/2$, so the
majority rule pays the likelier miner in every profile. For the second bound
we decompose the allocation into threshold rules. Let
$\Delta_j=a_{j+1}-a_j\ge0$; symmetry gives $\Delta_j=\Delta_{2m-j}$ and
$\sum_j\Delta_j\le1$. For $j<m$ let
$f_j(k)=\frac12(\one\{k>j\}+\one\{k>2m-j\})$, and let $f_m(k)=\one\{k>m\}$.
Then
\[
a=\Bigl(1-\sum_j\Delta_j\Bigr)\frac12+\sum_{j<m}2\Delta_j\,f_j+\Delta_m f_m ,
\]
and $Q$ and $H$ are affine in $a$, so we may compare the thresholds one at a
time. For an accuracy $t\in[1/2,p]$ let $Q_j(t)=\E f_j(\Bin(n,t))$ and let
$H_j(t)$ be the influence of $f_j$ at accuracy $t$:
\begin{gather*}
H_j(t)=\tfrac12\tbinom{2m}{j}\bigl[t^j(1-t)^{2m-j}+t^{2m-j}(1-t)^j\bigr]\quad(j<m),\\
H_m(t)=\tbinom{2m}{m}\bigl[t(1-t)\bigr]^m .
\end{gather*}
Differentiating the binomial sums gives
\[
Q_j'(t)=nH_j(t),\qquad Q_j(1/2)=1/2,
\]
and the ratio of the two influences is
\[
\frac{H_j(t)}{H_m(t)}=\frac{\tbinom{2m}{j}}{\tbinom{2m}{m}}\,\cosh\Bigl((m-j)\log\tfrac{t}{1-t}\Bigr),
\]
which increases for $t\ge1/2$. Hence
\[
\frac{H_j(t)}{H_j(p)}\le\frac{H_m(t)}{H_m(p)}\qquad\text{for }t\in[1/2,p],
\]
and since $H_m(p)=b$ and $Q_m(p)=\Qmaj$, integrating gives
\begin{align*}
\frac{Q_j(p)-1/2}{H_j(p)}&=n\int_{1/2}^{p}\frac{H_j(t)}{H_j(p)}\,dt\\
&\le n\int_{1/2}^{p}\frac{H_m(t)}{H_m(p)}\,dt=\frac{\Qmaj-1/2}{b}.
\end{align*}
With mixture weights $c_j=2\Delta_j$ for $j<m$ and $c_m=\Delta_m$, we conclude
\begin{align*}
Q(a)-\frac12&=\sum_{j\le m}c_j\Bigl(Q_j(p)-\frac12\Bigr)
\le\frac{\Qmaj-1/2}{b}\sum_{j\le m}c_jH_j(p)\\
&=\frac{\Qmaj-1/2}{b}\,H(a).\qedhere
\end{align*}
\end{proof}

## thm:frontier

\begin{theorem}[Frontier]\label{thm:frontier}
Let $0\le\eta\le\Gs$. For $\omega>0$, the largest quality of a rule in $\Rset$
that supports honest evaluation at cost $\eta$ and ownership bound $\omega$ is
\[
Q^*(\omega)=\frac12+\Bigl(\Qmaj-\frac12\Bigr)\min\Bigl\{1,\frac{2(\Gs-\eta)}{\omega Mb}\Bigr\}.
\]
The damped majority rule of strength
$\lambda^*=\min\{1,2(\Gs-\eta)/(\omega Mb)\}$ with majority sharing attains it.
At $\omega=0$, the optimum is $Q^*(0)=\Qmaj$, attained with $\lambda^*=1$.
\end{theorem}

Source paper.tex line 494.

\begin{proof}
At $\omega=0$, majority sharing supports full majority allocation because
$\eta\le\Gs$; Lemma~\ref{lem:influence} gives its optimality. We now take
$\omega>0$ and combine the three lemmas. A rule that supports honest evaluation has
$H(a)\le2(G(v)-\eta)/(\omega M)\le2(\Gs-\eta)/(\omega M)$ by
Lemmas~\ref{lem:ic} and~\ref{lem:rent}, and Lemma~\ref{lem:influence} then gives
\[
Q(a)-\frac12\le\Bigl(\Qmaj-\frac12\Bigr)\min\Bigl\{1,\frac{H(a)}b\Bigr\}
\le\Bigl(\Qmaj-\frac12\Bigr)\lambda^*.
\]
For attainment we take the damped majority rule of strength $\lambda$ with
majority sharing. It has $H=\lambda b$ and $G=\Gs$, so by Lemma~\ref{lem:ic} it
supports honest evaluation exactly when $\lambda\le\lambda^*$, and at
$\lambda=\lambda^*$ its quality is
\[
\frac12+\lambda^*\Bigl(\Qmaj-\frac12\Bigr)=Q^*(\omega).\qedhere
\]
\end{proof}

## prop:binary

\begin{proposition}[All-or-nothing weights]\label{prop:binary}
With bond memory switched off, $0$-honest reports make Yuma pay miners by the
majority rule and validators by majority sharing. Hence $0$-honesty is an
equilibrium against all reports in $\{0,1\}$ if and only if
$\eta+\frac12\omega Mb\le\Gs$; with free evaluation, if and only if
$\omega\le K$.
\end{proposition}

Source paper.tex line 587.

\begin{proof}
We take a profile in which $k>m$ validators put all weight on miner $1$. The
median weight is $1$ on miner $1$ and $0$ on miner $0$. Clipping removes every
weight the minority placed on miner $1$ and every weight the majority placed on
miner $0$, so miner $1$ receives $M$ and each majority validator holds a
current share $1/k$ of miner $1$, while the minority holds nothing of it.
The zero column for miner $0$ contributes no payment. The payments are $V/k$ to each majority validator and $0$ to the others, and
unanimity pays $V/n$ each. Lemma~\ref{lem:ic} with $H=b$ and $G=\Gs$ turns the
equilibrium condition into
\[
\eta+\tfrac12\,\omega Mb\le\Gs .\qedhere
\]
\end{proof}

## lem:inherit

\begin{lemma}[Yuma stays inside the frontier]\label{lem:inherit}
Let bond memory be switched off and let $\ell$-honesty be an equilibrium for
some $\ell\in[0,1/2)$ at cost $\eta$ and ownership bound $\omega$. The map from
the number of validators whose signal names miner $1$ to Yuma's allocation and
payments is a rule in $\Rset$ that supports honest evaluation. In particular,
the quality of $\ell$-honesty is at most $Q^*(\omega)$.
\end{lemma}

Source paper.tex line 1005.

\begin{proof}[Proof of Lemma~\ref{lem:inherit}]
We first check that the induced allocation is monotone. Under $\ell$-honesty,
when $k>m$ validators name miner $1$ the median weight on
miner $1$ is $1-\ell$ and on miner $0$ is $\ell$. Clipping leaves miner $1$ with
total weight $k(1-\ell)+(n-k)\ell$ and miner $0$ with $n\ell$, so
\[
a_k=\frac{k(1-\ell)+(n-k)\ell}{k+2\ell(n-k)},\qquad
\frac{\partial a_k}{\partial k}=\frac{(1-2\ell)\,n\ell}{\bigl(k+2\ell(n-k)\bigr)^2}\ge0 ,
\]
and $a_{n-k}=1-a_k$ by symmetry, so $a_m\le\frac12\le a_{m+1}$. Payments sum to
$V$ in every profile, are nonnegative, and treat validators and miners alike.
The induced rule is therefore in $\Rset$. Each deviation of the induced rule
(evaluating and reporting against one's signal, or reporting a fixed miner
without evaluating) corresponds to submitting the weights of an
$\ell$-honest validator with the other signal, which is available in Yuma.
Hence the induced rule supports honest evaluation, and
Theorem~\ref{thm:frontier} gives $\QY(\ell)\le Q^*(\omega)$.
\end{proof}

