---
layout: post
title:  "Finding the Minkowski's bound"
usemathjax: true
---
$$
\renewcommand{\Re}{\operatorname{Re}}
\renewcommand{\Im}{\operatorname{Im}}
\newcommand{\abs}[1]{|#1|}
$$The finiteness of the class group is one of the cornerstone results in
algebraic number theory. However, many proofs I've read before are unmotivating and
drenched in symbols, and it's very easy to miss the forest for the trees. The
key ideas of the proof are really intuitive and beautiful, and in this post, I
want to show how anyone can come up with it just by trying out natural steps.

# Notation and definitions
In the following, $$K$$ is a number field of degree $$n$$ over $$\mathbb{Q}$$
and $$\mathcal{O}_K$$ is the ring of integers of $$K$$.

A fractional ideal of $$\mathcal{O}_K$$ is a finitely generated
$$\mathcal{O}_K$$-submodule of $$K$$. In particular, the usual ideals of
$$\mathcal{O}_K$$ are fractional ideals since $$\mathcal{O}_K$$ is noetherian. We will call these
*integral* ideals to differentiate from fractional ideals that do not lie inside $$\mathcal{O}_K$$.
The inverse of a fractional ideal $$\mathfrak{A}$$ is defined to be the set
$$\mathfrak{A}^{-1} = \{ a \in \mathcal{O}_K \mid a\mathfrak{A} \subseteq \mathcal{O}_K\}$$ which is also a fractional ideal. The fractional ideals form a group under ideal multiplication; we will use
$$J_K$$ to denote this group, and $$I_K$$ to denote
the subgroup of fractional ideals that are principal. The class group $$C_K$$ is defined as
the quotient group $$J_K/I_K$$.

Given an (integral) ideal $$\mathcal{A}$$ of $$\mathfrak{O}_K$$, we use $$\mathcal{N}(\mathfrak{A})$$
to denote the absolute norm, i.e., the size of the ring $$\mathcal{O}_K/\mathfrak{A}$$. This is multiplicative; $$\mathcal{N}(\mathfrak{A}\mathfrak{B}) = \mathcal{N}(\mathfrak{AB})$$. Moreover, if $$\mathfrak{A} = (a)$$ is principal, then $$\mathcal{N}(\mathfrak{A}) = \abs{N_{K/\mathbb{Q}}(a)}$$.

Finally, we use $$\Delta_K$$ to denote the discriminant of the number field $$K$$.

# Introduction
The main result that we're going to prove is
<div class=theorem><b>Theorem 1 (Minkowski's Bound).</b>
Let \(\mathfrak{A}\) be an integral ideal of \(\mathcal{O}_K\).
Then there exists an element \(a \in \mathfrak{A}\) such that
\[ |N_{K/\mathbb{Q}}(a)| \leq \frac{n!}{n} \left(\frac{4}{\pi}\right)^s|\Delta_K|^{1/2} \mathcal{N}(\mathfrak{A}) = M \cdot \mathcal{N}(\mathfrak{A}),\]
where \(M\) is a constant that does not depend on \(\mathfrak{A}\).
</div>

First, let's see how this implies that the class group is finite. If we try to move
the norm on the right side to the left side, the inequality becomes

$$ |N_{K/\mathbb{Q}}(a)|\cdot\mathcal{N}(\mathfrak{A})^{-1} \leq M $$

Since $$a\mathfrak{A}^{-1}$$ is an integral ideal (check this!), the multiplicative property of
the norm gives $$ \mathcal{N}(a\mathfrak{A}^{-1}) \leq M $$. Since in $$C_K$$ we are modding out by
principal ideals, this means that for any integral ideal $$\mathfrak{A}$$, the ideal class of $$\mathfrak{A}^{-1}$$ contains an integral ideal whose norm is less than $$M$$. Unsurprisingly, this actually covers all ideal classes. That is,

<div class=proposition><b>Proposition 1.</b>
Any ideal class in \(C_K\) contains an integral ideal whose norm is less than \(M\).
</div>
*Proof.* We just have to show that any ideal class in $$C_K$$ contains
$$\mathfrak{A}^{-1}$$ where $$\mathfrak{A}$$ is an integral ideal. Take any ideal class, and let $$\mathfrak{B}$$ be a fractional ideal in it. Then $$\mathfrak{B}^{-1}$$ is also a fractional ideal, and
there exists $$b \in \mathcal{O}_K$$ such that $$b\mathfrak{B}^{-1}$$ is an integral ideal (in fact we can take $$b$$ to be any element of $$\mathfrak{B}$$.) Then $$(b\mathfrak{B}^{-1})^{-1} = b^{-1}\mathfrak{B} \in [\mathfrak{B}]$$, so we are done.

Now the proposition below immediately shows what we're looking for.
<div class=proposition><b>Proposition 2.</b>
There are only finitely many integral ideals of bounded norm.
</div>
*Proof.* The proof is actually quite easy. Remember that any prime ideal $$\mathfrak{p}$$ of $$\mathcal{O}_K$$ contains a unique prime number $$p \in \mathbb{Z}$$, and that the norm $$\mathcal{N}(\mathfrak{p})$$ is a power of $$p$$. In particular, it is greater than or equal to $$p$$.

Now suppose that we're trying to construct an integral ideal $$\mathfrak{A}$$ whose norm is bounded above by $$M$$. If we write the factorization of $$\mathfrak{A}$$ as

$$\mathfrak{A} = \mathfrak{p}_1^{e_1}\mathfrak{p}_2^{e_2}\cdot\ldots\cdot\mathfrak{p}_g^{e_g}, $$

then $$\mathcal{N}(\mathfrak{A})$$ is a product of powers of the norms of prime ideals on the right hand side. Since the former is bounded by $$M$$, this means that each $$\mathcal{N}(\mathfrak{p}_i)$$ is also bounded by $$M$$. In particular, any prime in $$\mathbb{Z}$$ that $$\mathfrak{p}_i$$ contains must be smaller than $$M$$. Since any prime of $$\mathbb{Z}$$ is contained in only finitely many prime ideals of $$\mathcal{O}_K$$, (they are precisely the prime ideals appearing in the factorization of $$p\mathcal{O}_K$$) this shows that there are only finitely many prime ideals that can appear in the factorization of $$\mathfrak{A}$$. Finally, the powers $$e_i$$ must be finite as well since $$p^{e_i} \leq \mathcal{N}(\mathfrak{p}_i)^{e_i} \leq M$$. This finishes the proof.

Since the ideal classes are disjoint (they are the cosets of a group), proposition 1 and 2 combined together shows that there are only finitely many ideal classes. i.e., the class group $$C_K$$ is finite.

# A brief review on lattices
A *lattice* $$\mathcal{L}$$ in a vector space $$V$$ is an abelian subgroup of the form $$\mathbb{Z}v_1 + \mathbb{Z}v_2 + \cdots + \mathbb{Z}v_n$$ where $$\{v_i\}$$ is a basis of $$V$$. Now let $$\mathcal{L}$$ be a lattice in $$\mathbb{R}^n$$. The *fundamental parallelepiped* is defined as the set

$$ T = \{c_1v_1 + c_2v_2 + \cdots + c_nv_n, 0 \leq c_i \leq 1\}. $$

The *mesh* of $$\mathcal{L}$$ is the volume of $$T$$. This can be computed as the absolute value of the determinant of the matrix where the columns are $$v_i$$ written in terms of the standard basis.

# Attack plan
Now let's try to prove the Minkowski's bound at the start of the article. Remember that $$\mathcal{O}_K$$, and more generally any integral ideal $$\mathfrak{A}$$ of $$\mathcal{O}_K$$, is a free $$\mathbb{Z}$$-module of rank $$n$$. Therefore, $$\mathfrak{A}$$ forms a lattice in the number field $$K$$. What Minkowski's bound shows is that for any such lattice, there is a lattice point with quite a small norm relative to the norm of the ideal (which can be seen as an analog of the mesh of the lattice.) Right now we have no idea how to prove this, but if we are working in $$\mathbb{R}^n$$ instead, there is a theorem that can precisely deal with this kind of statement.

<div class=theorem><b>Theorem 2 (Minkowski's Theorem).</b>
    Let \(S \subseteq \mathbb{R}^n\) be a convex, centrally symmetric (if \(x \in S\) then \(-x \in S\)), compact set containing the origin. Let \(\mathcal{L}\) be a lattice, and let \(d\) be its mesh. If the volume of \(S\) is greater than or equal to \(2^nd\), then \(S\) contains a lattice point of \(\mathcal{L}\).
</div>

Therefore, what we will try to do is embed $$K$$ in $$\mathbb{R}^n$$ such that the image of $$\mathfrak{A}$$ becomes a lattice in $$\mathbb{R}^n$$ instead, and construct a set $$S \subseteq \mathbb{R}^n$$ which satisfies the conditions above. Then $$S$$ must contain an element of the lattice, and we will be able to bound the norm of this element by constructing $$S$$ in a special way.

# Setup
As stated before, we first want to embed $$K$$ in $$\mathbb{R}^n$$ in a way that respects the additive structure so that we can use the Minkowski's theorem on it. A natural idea is to first pick a basis of $$K$$ over $$\mathbb{Q}$$, and then map that basis to the standard basis of $$\mathbb{R}^n$$. However, it turns out that there is a better way to do it without choosing any particular basis.

Since the extension $$K/\mathbb{Q}$$ is separable, there are exactly $$n$$ homomorphisms from $$K$$ to $$\mathbb{C}$$ fixing $$\mathbb{Q}$$. Let them be labelled as $$\sigma_1, \sigma_2, \ldots, \sigma_n$$. Then we can define the map $$\phi: K \to \mathbb{C}^n$$ as

$$ \phi(x) = (\sigma_1(x), \sigma_2(x), \ldots, \sigma_n(x)). $$

By splitting each complex coordinate into the corresponding real and imaginary parts, we can turn this into an embedding of $$K$$ in $$\mathbb{R}^{2n}$$. The problem with this is that the image of $$\mathfrak{A}$$ will not be a lattice anymore since it cannot span $$\mathbb{R}^{2n}$$; the dimension is way too high. Instead of this, we can embed $$K$$ in $$\mathbb{R}^n$$ by throwing away some of the redundant information in the above map.

Recall that if $$\sigma$$ is an embedding from $$K \to \mathbb{C}$$, then its composition with complex conjugation, defined by $$\overline{\sigma}(x) = \overline{\sigma(x)}$$ is also another embedding from $$K \to \mathbb{C}$$. When the image of $$K$$ under $$\sigma$$ is real, $$\overline{\sigma}$$ is the same embedding as $$\sigma$$, but when the image is complex, it is a different embedding. Therefore, each complex embedding can be paired with its conjugate embedding. Let $$r$$ be the number of real embeddings, and $$s$$ be the number of pairs of complex embeddings. Then WLOG, relabel $$\sigma_i$$ such that $$\sigma_1, \ldots, \sigma_r$$ are real embeddings, and $$\sigma_{r+1}, \overline{\sigma_{r+1}}, \ldots, \overline{\sigma_{r+s}}$$ are complex embeddings. We really only need the information of one complex embedding from each pair, since we can recover the other pair just by composing it with complex conjugation. This motivates us to define the embedding $$v: K \to \mathbb{R}^n$$ as

$$ v(x) = (\sigma_1(x), \sigma_2(x), \ldots, \sigma_r(x), \Re(\sigma_{r + 1}(x)), \Im(\sigma_{r + 1}(x)), \ldots, \Im(\sigma_{r + s}(x))). $$

In other words, we have kept the real embeddings as they are, and replaced conjugate pairs of complex coordinates by the real and imaginary parts of one of them.

# Computing the mesh of the lattice
Now let's check that $$v(\mathfrak{A})$$ is actually a lattice in $$\mathbb{R}^n$$.

<div class=proposition><b>Proposition 3.</b>
Let \(v: K \to \mathbb{R}^n\) be defined as before. Then \(v(\mathfrak{A})\) is a lattice with mesh
\(2^{-s}\mathcal{N}(\mathfrak{A})|\Delta_K|^{1/2}\).
</div>

*Proof.* Let's first handle the case when $$\mathfrak{A}$$ is the whole ring $$\mathcal{O}_K$$. Pick a $$\mathbb{Z}$$-basis $$a_1, a_2, \ldots, a_n$$ of $$\mathcal{O}_K$$. Then $$v(a_1), v(a_2), \ldots, v(a_n)$$ is a $$\mathbb{Z}$$-basis of $$v(\mathcal{O}_K)$$, since $$v$$ is an injective homomorphism of abelian groups. Let's compute the mesh first. It is the absolute value of the determinant of the matrix having $$v(a_i)$$ as column vectors, i.e., we need to compute the following:

$$
\det
\begin{bmatrix}
    \sigma_1(a_1) & \cdots & \sigma_1(a_n) \\
    \vdots & \ddots & \vdots \\
    \sigma_r(a_1) & \cdots & \sigma_r(a_n) \\
    \Re(\sigma_{r + 1}(a_1)) & \cdots & \Re(\sigma_{r + 1}(a_n)) \\
    \vdots & \ddots & \vdots \\
    \Im(\sigma_{r + s}(a_1)) & \cdots & \Im(\sigma_{r + s}(a_n))
\end{bmatrix}.
$$

Now a bit of row manipulation shows that the above quantity is equal to

$$
(-2i)^s
\begin{bmatrix}
    \sigma_1(a_1) & \cdots & \sigma_1(a_n) \\
    \vdots & \ddots & \vdots \\
    \sigma_r(a_1) & \cdots & \sigma_r(a_n) \\
    \Re(\sigma_{r + 1}(a_1)) + i\Im(\sigma_{r + 1}(a_1)) & \cdots & \Re(\sigma_{r + 1}(a_n)) + i\Im(\sigma_{r + 1}(a_1)) \\
    \vdots & \ddots & \vdots \\
    \Re(\sigma_{r + s}(a_1)) - \Im(\sigma_{r + s}(a_1)) & \cdots & \Re(\sigma_{r + s}(a_n)) - \Im(\sigma_{r + s}(a_n))
\end{bmatrix}
$$

which is just

$$
(-2i)^{-s}\det
\begin{bmatrix}
    \sigma_1(a_1) & \cdots & \sigma_1(a_n) \\
    \vdots & \ddots & \vdots \\
    \sigma_n(a_1) & \cdots & \sigma_n(a_n) \\
\end{bmatrix}.
$$

Therefore, squaring gives

$$ \text{mesh}^2 = |(-4)^{-s} \Delta_K| \Longrightarrow \text{mesh} = 2^{-s} |\Delta_K|^{1/2}, $$

and we're done with the proof in the case when $$\mathfrak{A} = \mathcal{O}_K$$.

Now, proving the proposition for all integral ideals take a little bit more work, so I'll only sketch it. Note that $$\mathcal{N}(\mathfrak{A})$$ is the number of points in $$\mathcal{O}_K/\mathfrak{A}$$. Therefore, $$\mathfrak{A}$$ contains only $$1/\mathcal{N}(\mathfrak{A})$$ points of $$\mathcal{O}_K$$. Hence its mesh should be $$\mathcal{N}(\mathfrak{A})$$ times the mesh of $$\mathcal{O}_K$$, which is equal to $$2^{-s} \abs{\Delta_K}^{1/2} \mathcal{N}(\mathfrak{A})$$. The rigorous proof can be done by first picking a basis $$a_1, a_2, \ldots, a_n$$ and proceeding as before to show that

$$ \text{mesh} = 2^{-s} |\Delta(a_1, a_2, \ldots, a_n)|^{1/2} $$

and then using the equality

$$ |\Delta(a_1, a_2, \ldots, a_n)|^{1/2} = \mathcal{N}(\mathfrak{A}) |\Delta_K|^{1/2} $$

which is saying the same thing as the geometric fact stated above.

Actually, we're not done yet since we need to show that $$v(a_i)$$ is a basis of $$\mathbb{R}^n$$. This
is now obvious since the mesh is non-zero. (It is well-known that $$\Delta_K$$ is non-zero.)

# Picking a suitable set
In order to use Minkowski's theorem on the lattice $$v(\mathfrak{A}) \subseteq \mathbb{R}^n$$, we need to pick a suitable convex, centrally symmetric and compact set $$S$$ that is big enough. It might seem strange at first, but I propose to pick the following set
for a suitable value of $$t$$.

$$
\begin{multline}
S = \{ (x_1, x_2, \ldots, x_r, y_{r + 1}, z_{r + 1}, \ldots, z_{r + s}) \mid \\
\abs{x_1} + \abs{x_2} + \cdots + \abs{x_r} + 2\sqrt{y_{r + 1}^2 + z_{r + 1}^2} + \cdots + 2\sqrt{y_{r + s}^2 + z_{r + s}^2} \leq t\}.
\end{multline}
$$

This is a centrally symmetric, convex, compact set. The reason why we pick this set is that it makes the norm of any element in it very easy to bound. Suppose that $$v(a)$$ is in $$S$$ for some $$a \in \mathfrak{A}$$. Then we have

$$ \abs{N_{K/\mathbb{Q}}(a)}^{1/n} = \left(\prod_{i = 1}^n \abs{\sigma_i(a)}\right)^{1/n} \leq \frac{\sum_{i = 1}^n \abs{\sigma_i(a)}}{n} $$

by the AM-GM inequality. The sum on the right hand side is precisely

$$
\begin{multline}
\frac{1}{n}(\abs{\sigma_1(a)} + \cdots + \abs{\sigma_r(a)} + 2\sqrt{\Re(\sigma_{r + 1}(a))^2 + \Im(\sigma_{r + 1}(a)^2)}\\
 + \cdots + 2\sqrt{\Re(\sigma_{r + s}(a))^2 + \Im(\sigma_{r + s}(a)^2)}) \leq \frac{t}{n}. 
\end{multline}$$

Therefore, we have the inequality
$$ \abs{N_{K/\mathbb{Q}}(a)} \leq \frac{t^n}{n^n} $$
for any $$a \in \mathfrak{A}$$ whose image under $$v$$ lies in $$S$$.

In order to apply Minkowski's theorem, we must pick a value of $$t$$ such that the volume of the set
is equal to $$2^n$$ times the mesh. By some calculus, we can show that

<div class=proposition><b>Proposition 4.</b>
The volume of \(S\) (in terms of \(t\)) is \(\dfrac{2^{r - s}\pi^st^n}{n!}\).
</div>

Therefore, it suffices to pick the value of $$t$$ such that

$$\frac{2^{r - s}\pi^st^n}{n!} = 2^{n} \cdot 2^{-s}\mathcal{N}(\mathfrak{A})\abs{\Delta_K}^{1/2}
\Longrightarrow t^n = n!\left(\frac{4}{\pi}\right)^s\mathcal{N}(\mathfrak{A})|\Delta_K|^{1/2},$$

where we used the fact that $$r + 2s = n$$. Combining all the pieces together, we see that for such a value of $$t$$, by Minkowski's theorem, there exists a lattice point $$v(a)$$ inside $$S$$, which implies that

$$ \abs{N_{K/\mathbb{Q}}(a)} \leq \frac{n!}{n^n} \left(\frac{4}{\pi}\right)^s\mathcal{N}(\mathfrak{A})\abs{\Delta_K}^{1/2}, $$

and we're done!

# References
Evan Chen. *An Infinitely Large Napkin*  
Gerald J. Janusz. *Algebraic Number Fields*