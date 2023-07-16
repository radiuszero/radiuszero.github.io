---
layout: post
title:  "On Minkowski's theorem"
usemathjax: true
---
Recall that a set $$S$$ is *convex* if for any two points $$A$$ and $$B$$ in
$$S$$, the line segment joining $$A$$ and $$B$$ is also in $$S$$. $$S$$ is
*centrally symmetric* if it is symmetric about the origin. Finally, $$S$$ is
*bounded* if it is contained in a disk of finite radius. Below is an example of
a bounded, centrally symmetric convex set --- an ellipse.

{:refdef: style="text-align: center;"}
![Example of a bounded, centrally symmetric, convex set](/assets/figures/centrally-symmetric-set.svg)
{: refdef}

Minkowski's theorem states that such a set *which is also sufficiently big*
always contains a lattice point inside it which is different from the origin.

<div class=theorem><b>Theorem (Minkowski).</b> Suppose that \(A\) is a bounded, centrally symmetric,
convex set in \(\mathbb{R}^n\) having volume strictly greater than \(2^n\). Then
there is a lattice point in \(A\) different from the origin. </div>

The lower bound of $$2^n$$ in the theorem is strict since we can take the open
cube of side length $$2$$ centered at the origin which does not contain any
other lattice point except for the origin itself.

The proof of this theorem turns out to be really short and slick, and you should
really give some time thinking about it if you have not seen it before. I'll
demonstrate it for $$\mathbb{R} ^2$$ so that we can draw diagrams on this
2-dimensional webpage, but remember that it can be generalized easily for
arbitary $$n$$.

The key idea is to use the pigeonhole principle to utilize the lower bound for
the volume. Consider the tiling of $$\mathbb{R}^2$$ by squares of side length
$$2$$ centered at points with even coordinates. Such a tiling chops up the set
$$S$$ into multiple different pieces.
<!-- Insert figure here -->

Consider translating all those pieces into the $$2 \times 2$$ square centered at
the origin. Since the total volume of all these pieces is strictly greater than
$$2^2$$ which is equal to the area of the square, it follows that some pieces
must overlap, i.e. there exists a point $$z$$ inside the square which is
contained in at least two pieces, say $$\mathcal{A}$$ and $$\mathcal{B}$$.

Now move the pieces back to their original positions, and let $$x$$ and $$y$$ be
the respective images of $$z$$ under moving $$\mathcal{A}$$ and $$\mathcal{B}$$.
An important observation is that $$x$$ and $$y$$ (and $$z$$) have the same
position relative to their squares in the tiling. Therefore, the vector $$x -
y$$ is equal to the vector which translates the center of the square of $$y$$ to
that of $$x$$, and in particular, it must have even coordinates.

You might see where this is heading now. Let $$p$$ be the point $$\frac{1}{2}(x - y)$$. 
Of course, this point has integer coordinates, so it is a lattice point.
We now claim that $$p$$ is in $$A$$ and that $$p$$ is different from the origin.
The second part is easy; since $$ x \ne y$$, we must have $$p \ne 0$$. Now let's
show that $$p$$ is inside $$A$$.

This is where we finally use the other conditions given in the theorem
statement. Since $$y$$ is in $$A$$ and $$A$$ is centrally symmetric, it follows
that $$-y$$ is also in $$A$$. As $$p$$ is the midpoint of the segment joining
$$x$$ and $$-y$$ and $$A$$ is convex, $$p$$ must also be in $$A$$. This finishes
the proof.