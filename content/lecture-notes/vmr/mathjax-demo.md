+++
title = "MathJax demo"
norss = true
showDate = false
toc = false
+++
Throwaway page to check that the math rendering works. Delete it whenever.

---
## Inline
---
A document is a vector $d \in \mathbb{R}^{|V|}$ over the vocabulary $V$, and the
similarity of two documents is the cosine of the angle between them, $\cos\theta$,
which lands in $[0, 1]$ for non-negative weights.

Because `$` is an inline math delimiter, a literal dollar sign has to be written
`\\$` (double backslash — markdown eats one, MathJax needs the other), otherwise
everything between two dollars becomes an equation: this book costs \\$12, that
one \\$8.

---
## Display
---
Term frequency times inverse document frequency:

$$
\mathrm{tfidf}(t, d, D) = \underbrace{\frac{f_{t,d}}{\sum_{t' \in d} f_{t',d}}}_{\text{tf}}
\cdot \underbrace{\log \frac{|D|}{|\{d' \in D : t \in d'\}|}}_{\text{idf}}
$$

Cosine similarity, written with the other delimiter pair (`\[ ... \]`):

\[
\mathrm{sim}(d_1, d_2) = \frac{d_1 \cdot d_2}{\lVert d_1 \rVert \, \lVert d_2 \rVert}
= \frac{\sum_{i=1}^{n} d_{1i} d_{2i}}{\sqrt{\sum_{i=1}^{n} d_{1i}^2} \sqrt{\sum_{i=1}^{n} d_{2i}^2}}
\]

---
## Multi-line and numbered
---
PageRank, derived over a few steps:

$$
\begin{align}
    PR(p_i) &= \frac{1 - d}{N} + d \sum_{p_j \in M(p_i)} \frac{PR(p_j)}{L(p_j)} \\
    \mathbf{r} &= \frac{1 - d}{N} \mathbf{1} + d \, \mathbf{M} \mathbf{r} \\
    \mathbf{r} &= \left( \mathbf{I} - d \mathbf{M} \right)^{-1} \frac{1 - d}{N} \mathbf{1}
\end{align}
$$

Equation \eqref{eq:jaccard} is tagged and can be referenced:

$$
\begin{equation}
    J(A, B) = \frac{|A \cap B|}{|A \cup B|} \label{eq:jaccard}
\end{equation}
$$

---
## Matrices and cases
---
$$
\mathbf{M} =
\begin{pmatrix}
    0 & \tfrac{1}{2} & \tfrac{1}{3} \\
    1 & 0 & \tfrac{1}{3} \\
    0 & \tfrac{1}{2} & \tfrac{1}{3}
\end{pmatrix}
\qquad
w_{t,d} =
\begin{cases}
    1 + \log f_{t,d} & \text{if } f_{t,d} > 0 \\
    0 & \text{otherwise}
\end{cases}
$$

---
## Code blocks are left alone
---
Math delimiters inside code must render as plain text, not equations:

```python
# $x^2$ and \(y\) stay literal here
price = f"${amount:.2f}"
tfidf = tf * math.log(len(docs) / df)
```

And inline `$\alpha$` in backticks stays literal too.
