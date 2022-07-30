---
title: 'Cauchy Principal Value'
date: '2022-03-03'
tags: ['Mathematics', 'Calculus']
summary: 'A short introduction to principal value integrals'
---

## Definition

### For a singularity at $\infty$

Suppose that $f: \mathbb{R}\to\mathbb{R}$ is a continuous function on $(-\infty, \infty)$. If

$$
\lim\limits_{R\to\infty}\int_{-R}^{R}f(x)dx
$$

exists, then we can define the _Cauchy principal value of the integral of $f$ over $(-\infty, \infty)$_ to be this value, and we write

$$
PV\int_{-\infty}^{\infty}f(x)dx=\lim\limits_{R\to\infty}\int_{-R}^{R}f(x)dx
$$

for the value of this limit.

### For a singularity at a finite number $b$

Suppose that $f:\mathbb{R}\to\mathbb{R}$ is a continuous function on $(a, c)$. Let $a<b<c$, with $b$ being a difficult point on $f(x)$ where the behavior of the function is such that

$$
\int_a^b f(x)dx=\pm\infty \text{ and } \int_b^c f(x)dx=\mp\infty,
$$

then

$$
PV\int_a^c f(x)dx=\lim\limits_{\varepsilon\to 0^+}\biggl[\int_a^{b-\varepsilon}f(x)dx+\int_{b+\varepsilon}^c f(x)dx\biggl].
$$

## Note

$$
\exists\int_{-\infty}^{\infty}f(x)dx\implies \int_{-\infty}^{\infty}f(x)dx=PV\int_{-\infty}^{\infty}f(x)dx
$$

but

$$
\exists \ PV\int_{-\infty}^{\infty}f(x)dx \text{ does not imply } \exists \int_{-\infty}^{\infty}f(x)dx.
$$

For example,

$$
PV\int_{-\infty}^{\infty}\frac{2xdx}{x^2+1}=0 \text{ whereas } \int_{-\infty}^{\infty}\frac{2xdx}{x^2+1} = -\infty + \infty.
$$

In the same way, for $(a, c)\in\mathbb{R} \text{ and } a<c$,

$$
\exists \int_{a}^{c}f(x)dx \implies \int_{a}^{c}f(x)dx=PV\int_{a}^{c}f(x)dx
$$

but

$$
\exists \ PV\int_{a}^{c}f(x)dx \text{ does not imply } \exists \int_{a}^{c}f(x)dx.
$$

For example,

$$
PV\int_{-1}^1 \frac{dx}{x}=0 \text{ whereas }\int_{-1}^1 \frac{dx}{x}=-\infty+\infty.
$$

## Example

$$
\int_{0}^{4}\frac{x}{x^2-1}dx
$$

### Standard evaluation

$$
\int_{0}^{4}\frac{x}{x^2-1}dx=\int_{0}^{1}\frac{x}{x^2-1}dx+\int_{1}^{4}\frac{x}{x^2-1}dx
$$

$$
=\lim\limits_{\varepsilon\to 0^+}\biggl(\int_{0}^{1-\varepsilon}\frac{x}{x^2-1}dx+\int_{1+\varepsilon}^{4}\frac{x}{x^2-1}dx\biggl)
$$

$$
=\lim\limits_{\varepsilon\to 0^+}\biggl(\biggl[\frac{\textrm{ln}\left| x^2-1\right|}{2}\biggl]_{0}^{1-\varepsilon}+\biggl[\frac{\textrm{ln}\left| x^2-1\right|}{2}\biggl]_{1+\varepsilon}^{4}\biggl)
$$

$$
=-\infty+\infty
$$

### Principal value evaluation

Since $\lim\limits_{x\to1^-}f(x)=-\infty$ and $\lim\limits_{x\to1^+}f(x)=\infty$, we can assume that there exists a $b>1$ such that $\int_{0}^{1}f(x)dx+\int_{1}^{b}f(x)dx=0.$ Once found, we can find $PV\int_{0}^{4}f(x)dx$ by evaluating $\int_{b}^{4}f(x)dx.$

$$
\int_{0}^{1}\frac{x}{x^2-1}dx+\int_{1}^{b}\frac{x}{x^2-1}dx=0
$$

$$
\lim\limits_{\varepsilon\to 0^+}\biggl(\int_{0}^{1-\varepsilon}\frac{x}{x^2-1}dx=-\int_{1+\varepsilon}^{b}\frac{x}{x^2-1}dx\biggl)
$$

$$
\lim\limits_{\varepsilon\to 0^+}\biggl( \biggl[\frac{\textrm{ln}\left| x^2-1\right|}{2}\biggl]_{0}^{1-\varepsilon}=-\biggl[\frac{\textrm{ln}\left| x^2-1\right|}{2}\biggl]_{1+\varepsilon}^{b} \biggl)
$$

$$
\lim\limits_{\varepsilon\to 0^+}\biggl(\frac{\textrm{ln}\left|(1-\varepsilon)^2-1\right|}{2}=-\frac{\textrm{ln}\left|b^2-1\right|}{2}+\frac{\textrm{ln}\left|(1+\varepsilon)^2-1\right|}{2}\biggl)
$$

$$
0=-\frac{\textrm{ln}\left|b^2-1\right|}{2}
$$

$$
b=\sqrt{2}
$$

$$
\therefore PV\int_{0}^{4}\frac{x}{x^2-1}dx
$$

$$
=\int_{\sqrt{2}}^{4}\frac{x}{x^2-1}dx
$$

$$
=\frac{\textrm{ln}15}{2}
$$

## Showing the Divergence of Integrals

If the principal value of an integral can be computed, why can't we assert that as the standard value?

Consider again the aforementioned divergent integral:

$$
\int_{-\infty}^{\infty}\frac{2x}{x^2+1}dx
$$

A standard evaluation of the integral gives us the indeterminate $-\infty+\infty$. Recalling the definition for a singularity at $\infty$, we can rewrite the integral as the following:

$$
\lim\limits_{R\to\infty}\int_{-R}^{R}\frac{2x}{x^2+1}dx.
$$

This integral evaluates to 0, and, given the graph's symmetry, this appears to be the answer. But, we can also rewrite the integral as the following:

$$
\lim\limits_{R\to\infty}\int_{-2R}^{R}\frac{2x}{x^2+1}dx,
$$

which evaluates to $-\text{ln}4$. We can set up formulas with a variable $c\in\mathbb{R^+}$ to represent all possible values of this integral's principal value:

$$
\lim\limits_{R\to\infty}\int_{-cR}^{R}\frac{2x}{x^2+1}dx=-\text{ln}(c^2)
$$

and

$$
\lim\limits_{R\to\infty}\int_{-R}^{cR}\frac{2x}{x^2+1}dx=\text{ln}(c^2).
$$

These formulas' combined domain is $(-\infty, 0)\cup(0, \infty)$, showing why the integral is considered divergent; no one value can be assigned to it through the principal value evaluation.

(The PDF for this article can be found [here](https://index.baguetteboy.com/math/cauchy-principal-value/cauchy-principal-value.pdf))
