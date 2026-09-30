# Candidate proof packet

Verbatim theorem and proof environments from the manuscript. The complete source is supplied for all definitions and equations. No missing argument has been added.

# lemma thm:capacity

## statement

Source paper.tex line 793.

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

## proof

Source paper.tex line 1234.

\begin{proof}[Proof of Theorem~\ref{thm:capacity}]
We pair each report profile $r$ with its label flip $\mathbf1-r$ and write $W$
for the set of validators in the majority of $r$, with $|W|=j$. In $G_i(v)$ the
payment $v_i(r)$ carries the coefficient $\Pr(r)-\frac12\Pr(r_{-i})$, which for
$i\in W$ equals
\[
c_j=\frac d4\bigl(p^{j-1}q^{n-j}-q^{j-1}p^{n-j}\bigr),
\]
zero for $j=m+1$ and positive for $j\ge m+2$, and which is negative for
$i\notin W$. Moving a minority member's payment to the majority therefore
weakly raises every premium, so each set $W$ with $|W|=j\ge m+2$ contributes a
resource $2Vc_j=R_j$ that only its members can receive. A set $T$ of $k$
validators can draw only on the sets $W$ that meet it, and there are
$\binom nj-\binom{n-k}{j}$ of them of each size $j$; this proves necessity. For
sufficiency we fix weights $z\ge0$. The largest $z$-weighted premium is
$\sum_WR_{|W|}\max_{i\in W}z_i$, and sorting
$z_{(1)}\ge\dots\ge z_{(n)}\ge z_{(n+1)}=0$ gives
\[
\sum_WR_{|W|}\max_{i\in W}z_i=\sum_{k=1}^{n}\bigl(z_{(k)}-z_{(k+1)}\bigr)C_k .
\]
If $g$ satisfies every subset condition, $z\cdot g$ is at most this value for
every $z\ge0$. The deliverable premium vectors form a compact, downward-closed
polytope, so a vector outside it is separated by a hyperplane with a
nonnegative normal, which the display rules out. Hence there is a flow
$f_{W,i}\ge0$ from each $W$ to its members with $\sum_{W\ni i}f_{W,i}\ge g_i$.
Setting $v_i=f_{W,i}/(2c_{|W|})$ on the two profiles with majority $W$, we obtain
\[
G_i(v)=\sum_{W\ni i}f_{W,i}\ge g_i .\qedhere
\]
\end{proof}

# Associated application: one validator with at least half the stake

Verbatim associated paragraph from paper.tex; this is part of the audit scope.

\paragraph{One validator with at least half the stake.} Let $n=3$, let
validator $1$ hold stake $\varphi_1\ge\frac12$ and the other two equal stakes,
with common $\eta$ and $\omega$, and write $t=pq$. Averaging over the two small
validators keeps quality and every constraint, so an allocation is described
by $0\le a_0\le a_1\le a_2\le\frac12$, miner $1$'s share when validator $1$
reports $0$ and none, one or both small validators report $1$; the other
profiles follow by symmetry, and at $\varphi_1=\frac12$ ties force
$a_2=\frac12$. Integrating over profiles,
\begin{gather*}
Q=p+d\,[\,ta_2-2ta_1-(1-t)a_0\,],\\
H_1=1-(1-2t)(a_0+a_2)-4ta_1,\\
H_S=(1-4t)a_1-(1-2t)a_0+2ta_2,
\end{gather*}
where $H_1$ and $H_S$ are the influences of the large and of a small validator.
With three validators only unanimous profiles create premium, so every
nonempty capacity equals $C_k=Vd^2/2$ and the subset conditions of
Theorem~\ref{thm:capacity} reduce to
$3\eta+\frac12\omega M(H_1+2H_S)\le Vd^2/2$. The allocations form a polytope
with vertices $(\frac12,\frac12,\frac12)$, $(0,0,0)$, $(0,0,\frac12)$ and
$(0,\frac12,\frac12)$, whose pairs (quality gain over one half divided by $d$,
total influence $H_1+2H_S$) are $(0,0)$, $(\frac12,1)$,
$(\frac{1+t}2,\frac12+3t)$ and $(\frac{1-t}2,\frac32-3t)$. The third vertex has
the highest quality gain and the highest ratio of gain to influence; its cross
products with the second and fourth differ by nonnegative multiples of $1-4t$.
Mixing it with the even split is therefore optimal, and the constraint gives
\[
Q^*=\frac12+\frac{d(1+t)}2\min\Bigl\{1,\frac{Vd^2-6\eta}{\omega M(\frac12+3t)}\Bigr\}.
\]

