# Case $n = 2k + 1$

We are now ready to prove the case $n = 2k + 1$.

---

## Lemma

Let $z_1, \dots, z_n$ be distinct points on the unit circle with  

$$
|P'(z_j)| = \prod_{k \neq j} |z_j - z_k| = C \quad \text{independent of } j.
$$

If $n$ is odd, then $z_1, \dots, z_n$ are the vertices of a regular $n$-gon (up to rotation), and $C = n$.

---

### Proof

Let $z_1,\dots,z_n$ be distinct complex numbers with $|z_j|=1$, and let  

$$
P(z) = \prod_{k=1}^n (z-z_k)
$$

be the monic polynomial with these zeros. Then  

$$
P'(z_j) = \prod_{k\ne j}(z_j-z_k)\qquad |P'(z_j)| = \prod_{k\ne j}|z_j-z_k|.
$$

By hypothesis, $|P'(z_j)|=C>0$ is independent of $j$.

Let $S := \prod_{m=1}^n z_m$ (so $|S|=1$). Using $\overline{z}=1/z$ on the unit circle,

$$
\overline{P'(z_j)}
= \prod_{k\ne j}(\overline{z_j}-\overline{z_k})
= \prod_{k\ne j}\left(\frac{1}{z_j}-\frac{1}{z_k}\right)
= \frac{\prod_{k\ne j}(z_k-z_j)}{z_j^{n-1}\prod_{k\ne j}z_k}
= \frac{(-1)^{n-1}}{z_j^{n-2}S}P'(z_j).
$$

Set $\beta := (-1)^{n-1}/S$, so $|\beta|=1$. Then

$$
\overline{P'(z_j)} = \beta z_j^{-(n-2)}P'(z_j)\qquad (j=1,\dots,n).
$$

Write $P'(z_j)=C\eta_j$ with $|\eta_j|=1$. From the above,

$$
\overline{\eta_j}
= \beta z_j^{-(n-2)}\eta_j,
$$

hence  

$$
\eta_j^2=\beta^{-1}z_j^{n-2}.
$$

Choose $\sigma$ with $|\sigma|=1$ and $\sigma^2=\beta^{-1}$. Then for some $\varepsilon_j\in\{\pm1\}$,

$$
\eta_j=\sigma\varepsilon_jz_j^{\frac{n-2}{2}}, \qquad
\frac{1}{P'(z_j)}=\frac{\overline{\sigma}}{C}\varepsilon_jz_j^{-\frac{n-2}{2}}.
$$

For a monic $P$ with simple zeros $z_j$, by the theorem of residue, we obtain the Lagrange-Hermite formula:

$$
\sum_{j=1}^n \frac{z_j^m}{P'(z_j)}=
\begin{cases}
0,& m=0,1,\dots,n-2, \\
1,& m=n-1.
\end{cases}
$$

Using this for $m=0,1,\dots,n-2$ gives

$$
\sum_{j=1}^n \varepsilon_jz_j^{m-\frac{n-2}{2}}=0.
$$

Fix any $w_j$ with $w_j^2=z_j$, and define $u_j:=\varepsilon_j w_j$. Then  

$$
\sum_{j=1}^n u_j^{k}=0\qquad (k=1,3,\dots,n-2).
$$

Let

$$
Q(t):=\prod_{j=1}^n (t-u_j)=t^n+a_1 t^{n-1}+a_2 t^{n-2}+\cdots+a_n,
$$

and $p_k:=\sum_{j=1}^n u_j^{k}$. Newton's identities imply

$$
p_m+a_1 p_{m-1}+a_2 p_{m-2}+\cdots+a_{m-1}p_1+m a_m=0.
$$

We only need use this identity when $m$ is odd. Observe that $p_k = 0$ when $k$ is odd, we have by induction that:

$$
a_{2r+1}=0 \quad\text{for all odd indices up to $n-2$}.
$$

Since $n$ is odd, due to the fact that $Q(t)$ is a self-inversive polynomial, $a_{2r} = 0$ for $1 \leq r \leq \frac{n-1}{2}$.

Since $|u_j|=1$,

$$
Q(t)=t^n+a_n, \qquad |a_n|=1.
$$

Therefore the $u_j$ are the $n$ th roots of $-a_n$, equally spaced.

Recall $z_j=u_j^{2}$. When $n$ is odd, the map $u\mapsto u^2$ permutes the $n$th roots of unity; hence the $z_j$ form a regular $n$-gon. For such a polygon,  

$$
P(z)=z^n-\omega^n,\quad P'(z)=n z^{n-1},\quad |P'(z_j)|=n.
$$

Thus $C=n$. ∎

---

## Theorem 1 (case $n = 2k + 1$)

Let $z_1, z_2,\ldots,  z_{2k + 1} \in \mathbb{C}$ with $|z_i| = 1$, and define  

$$
s_k := \sum_{i=1}^{2k+1} z_i^k, \qquad k \in \mathbb{Z}.
$$

Assume there exist integers $a < b$ such that

$$
s_{a+1} = \cdots = s_{a+2k} = s_{b+1} = \cdots =s_{b+2k} = 0.
$$

Set $q := b-a$. Upon reordering,

$$
\{z_1, z_2, \ldots , z_{2k+1}\} = \{1, \zeta, \ldots, \zeta^{2k}\}, \qquad
\zeta = e^{2\pi i/{(2k + 1)}}.
$$

---

### Proof

By Proposition 1, the $z_i$ are pairwise distinct and $z_i^q = 1$; in particular $|z_i| = 1$. Let $c_i := z_i^a$.  

The zero block at $a$ gives

$$
\sum_{i=1}^{2k + 1} c_i = 0,\quad \ldots,\quad \sum_{i=1}^{2k + 1} c_i z_i^{2k-1} = 0.
$$

This is $2k$ equations with $2k+1$ unknowns. The rank is $2k$, so the kernel has dimension 1. Therefore

$$
z_1^{a+1} = \mu\prod_{2 \leq i < j \leq n}(z_i - z_j), \quad \ldots
$$

Taking moduli and using $|z_i|=1$ yields

$$
\prod_{i \neq 1}|z_1 - z_i| = \cdots = \prod_{i \neq n} |z_n - z_i|.
$$

Thus, from Lemma 1, the $2k+1$ points form a regular polygon. ∎
