# ErdosProblem-974
Solution to the ErdosProblem #974

We are now ready to prove the case $n = 2k + 1$.

> **Lemma**
>
> Let $z_1, \dots, z_n$ be distinct points on the unit circle with
> $$|P'(z_j)| = \prod_{k \neq j} |z_j - z_k| = C \quad \text{independent of } j.$$
> If $n$ is odd, then $z_1, \dots, z_n$ are the vertices of a regular $n$-gon (up to rotation), and $C=n$.

---

*Proof.*

Let $z_1,\dots,z_n$ be distinct complex numbers with $|z_j|=1$, and let
$$P(z)=\prod_{k=1}^n (z-z_k)$$
be the monic polynomial with these zeros. Then
$$P'(z_j)=\prod_{k\ne j}(z_j-z_k),\qquad |P'(z_j)|=\prod_{k\ne j}|z_j-z_k|.$$
By hypothesis, $|P'(z_j)|=C>0$ is independent of $j$.

***

*Step 1: A conjugation identity at the zeros.*

Let $S:=\prod_{m=1}^n z_m$ (so $|S|=1$). Using $\overline{z}=1/z$ on the unit circle,
$$
\overline{P'(z_j)}
=\prod_{k\ne j}(\overline{z_j}-\overline{z_k})
=\prod_{k\ne j}\!\left(\frac{1}{z_j}-\frac{1}{z_k}\right)
=\frac{\prod_{k\ne j}(z_k-z_j)}{z_j^{\,n-1}\,\prod_{k\ne j}z_k}
=\frac{(-1)^{n-1}}{z_j^{\,n-2}S}\,P'(z_j).
$$Set $\beta:=(-1)^{n-1}/S$, so $|\beta|=1$. Then$$
\overline{P'(z_j)}=\beta\,z_j^{-(n-2)}\,P'(z_j)\qquad (j=1,\dots,n). \tag{1}
$$

***

*Step 2: The phases of $P'(z_j)$.*

Write $P'(z_j)=C\,\eta_j$ with $|\eta_j|=1$. From (1),
$$
\overline{\eta_j}=\frac{\overline{P'(z_j)}}{|P'(z_j)|}
=\beta\,z_j^{-(n-2)}\,\eta_j,
$$hence $\eta_j^2=\beta^{-1}z_j^{\,n-2}$. Choose $\sigma$ with $|\sigma|=1$ and $\sigma^2=\beta^{-1}$. Then for some $\varepsilon_j\in\{\pm1\}$,$$
\eta_j=\sigma\,\varepsilon_j\,z_j^{\frac{n-2}{2}},
\qquad\text{so}\qquad
\frac{1}{P'(z_j)}=\frac{\overline{\eta_j}}{C}
=\frac{\overline{\sigma}}{C}\,\varepsilon_j\,z_j^{-\frac{n-2}{2}}. \tag{2}
$$
(Here $n$ is odd, so $(n-2)/2$ is a half-integer; any choice of the square root of $z_j$ is allowed, and the final identities below depend only on *odd* powers, hence are independent of the branch.)

***

*Step 3: Lagrange (barycentric) identities.*

For a monic $P$ with simple zeros $z_j$, the classical Lagrange identities give
$$
\sum_{j=1}^n \frac{z_j^m}{P'(z_j)}=
\begin{cases}
0,& m=0,1,\dots,n-2,\\
1,& m=n-1.
\end{cases} \tag{3}
$$
(For instance, interpolate the monomial $z^m$ at the nodes $z_j$ and compare the $z^{n-1}$-coefficients.)
Using (2) in (3) for $m=0,1,\dots,n-2$,
$$\sum_{j=1}^n \varepsilon_j\,z_j^{\,m-\frac{n-2}{2}}=0.$$
Fix any $w_j$ with $w_j^2=z_j$, and define $u_j:=\varepsilon_j w_j$ (so $|u_j|=1$ and $u_j^2=z_j$). Then, because $k:=2m-(n-2)$ is *odd* for $m=0,1,\dots,n-2$ (and $n$ odd),
$$\sum_{j=1}^n u_j^{\,k}=0\qquad\text{for all odd }k\in\{-(n-2),-(n-4),\dots,n-2\}. \tag{4}$$
In particular,
$$\sum_{j=1}^n u_j^{\,k}=0\qquad (k=1,3,\dots,n-2). \tag{5}$$

***

*Step 4: A polynomial with zeros $u_j$.*

Let
$$Q(t):=\prod_{j=1}^n (t-u_j)=t^n+a_1 t^{n-1}+a_2 t^{n-2}+\cdots+a_n,$$
and let $p_k:=\sum_{j=1}^n u_j^{\,k}$ be the power sums. Newton's identities (for a monic polynomial) assert that for $m\ge1$,
$$p_m+a_1 p_{m-1}+a_2 p_{m-2}+\cdots+a_{m-1}p_1+m a_m=0. \tag{6}$$
From (5) with $m=1$ we get $p_1=0$, hence $a_1=0$. Assume inductively that $a_1,a_3,\dots,a_{m-2}=0$ for some odd $m\le n-2$. In (6) with this $m$:
* $p_m=0$ (by (5));
* if $r$ is even, then $p_{m-r}$ is odd-indexed and hence $0$ by (5);
* if $r$ is odd, then $a_r=0$ by the inductive hypothesis.

Therefore (6) reduces to $m a_m=0$, so $a_m=0$. By induction,
$$a_{2r+1}=0\qquad\text{for all }r\ge0\text{ with }2r+1\le n-2. \tag{7}$$

***

*Step 5: Self-inversive symmetry kills the even coefficients.*

Since $|u_j|=1$ for all $j$,
$$\widetilde{Q}(t):=t^n\,\overline{Q\!\left(\frac{1}{\overline{t}}\right)}$$
has the same zeros as $Q$ (namely $u_1,\dots,u_n$), hence there is a constant $\kappa\ne0$ such that $\widetilde{Q}=\kappa Q$. Writing $Q(t)=\sum_{m=0}^{n} c_m t^m$ with $c_n=1$ and $c_0=a_n$, a direct computation shows
$$\widetilde{Q}(t)=\sum_{m=0}^{n}\overline{c_{n-m}}\,t^m.$$
Comparing coefficients in $\widetilde{Q}=\kappa Q$ yields
$$\overline{c_{n-m}}=\kappa\,c_m\qquad (m=0,1,\dots,n). \tag{8}$$
Since $c_m=a_{n-m}$ for $m<n$ and $c_n=1$, (8) is equivalently
$$a_m=\mu\,\overline{a_{n-m}}\qquad (m=0,1,\dots,n), \tag{9}$$
with $\mu:=a_n$ satisfying $|\mu|=1$ (because $|a_n|=\prod|u_j|=1$). As $n$ is odd, if $2\le m\le n-1$ is even then $n-m$ is odd, so by (7) we have $a_{n-m}=0$, and thus $a_m=0$ by (9). Combining with (7) we obtain
$$a_1=a_2=\cdots=a_{n-1}=0,$$
i.e.
$$Q(t)=t^n+a_n\quad\text{with }|a_n|=1.$$
Therefore the $u_j$ are the $n$th roots of $-a_n$, equally spaced on the unit circle.

***

*Step 6: Back to $z_j$ and the value of $C$.*

Recall $z_j=u_j^{\,2}$. When $n$ is odd, the map $u\mapsto u^2$ permutes the set of $n$th roots of unity; hence the $z_j$ are equally spaced as well—i.e., the vertices of a regular $n$-gon (up to rotation). For a regular $n$-gon one has $P(z)=z^n-\omega^n$ for some unimodular $\omega$, so $P'(z)=n z^{n-1}$ and therefore $|P'(z_j)|=n$. Thus $C=n$. □

---

### Theorem 1 (case $n = 2k + 1$)

Let $z_1, z_2,\ldots, z_{2k + 1} \in \mathbb{C}$ with $|z_i| = 1$, and define $s_k := \sum_{i=1}^{2k+1} z_i^k$ for $k \in \mathbb{Z}$. Assume there exist integers $a < b$ such that
$$s_{a+1} = \cdots = s_{a+2k} = s_{b+1} = \cdots =s_{b+2k} = 0.$$
Set $q := b-a$. Upon to reordering,
$$\{z_1, z_2, \ldots , z_{2k+1}\} = \{1, \zeta, \ldots, \zeta^{2k}\} \qquad (\zeta = e^{2\pi i/{(2k + 1)}}).$$

---

*Proof*.

By Proposition 1 we already know that $z_1, z_2, \ldots,z_{2k + 1}$ are pairwise distinct and $z_i^q = 1$ for $i=1, 2, \ldots, 2k + 1$; in particular $|z_i| = 1$. Let $c_i := z_i^a$. The zero block at $a$ gives
$$\sum_{i=1}^{2k + 1} c_i = 0, \ldots \sum_{i=1}^{2k + 1} c_i z_i^{2k-1} = 0.$$
This is a set of $2k$ equations with $2k + 1$ unknowns. Since the rank of the coefficient matrix is known to be of rank $2k$, the kernel has a dimension 1. Therefore
equivalently
$$z_1^{a+1} = \mu\prod_{2 \leq i < j \leq n}(z_i - z_j), \ldots, \quad z_3^{a+1} = \mu\prod_{1 \leq i < j \leq n-1}(z_i - z_j).$$
Taking moduli and using $|z_i|=1$ yields
$$|\mu| |\prod_{2 \leq i < j \leq n}(z_i - z_j)| = \cdots = |\mu| |\prod_{1 \leq i < j \leq n-1}(z_i - z_j)| = 1,$$
so
$$\prod_{i \neq 1}|z_1 - z_i| = \cdots = \prod_{i \neq n} |z_n - z_i|.$$
Thus, from lemma 1, the $2k + 1$ points $z_1, z_2, \ldots, z_n$ on the unit circle form an regular n-sided polygon, and the conclusion follows. □
