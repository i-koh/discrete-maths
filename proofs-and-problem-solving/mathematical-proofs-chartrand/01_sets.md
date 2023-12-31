# Sets

_Notes and exercise answers_

| **Symbol** | **Set it represents** |
| --- | --- |
| `$\mathbb{N}$` | Natural numbers (positive integers) |
| `$\mathbb{Z}$` | Integers (negative, zero and positive whole numbers) |
| `$\mathbb{Q}$` | Rational numbers (`$\frac{m}{n}$`, where `$m, n \in \mathbb{Z}$`) |
| `$\mathbb{I}$` | Irrational numbers (`$m, n \notin \mathbb{Z}$`) |
| `$\mathbb{R}$` | Real numbers (`$\mathbb{R} \subset \mathbb{C}$`) |
| `$\mathbb{C}$` | Complex numbers |

## A note on rendering sets with `$\LaTeX$` using GitHub Markdown

- For **inline** expressions, use this form:
    ```
    `$\{<elements_of_set>\}$`
    ```
- For **displays**, use this form and note that the [curly braces have to be escaped _twice_](https://stackoverflow.com/questions/41312777/mathjax-curly-brackets-dont-show-up-using-jekyll):
    ```
    $$
    \begin{aligned}
    \\{<elements_of_set>\\}
    \end{aligned}
    $$
    ```
  Failing to escape twice causes the curly braces to be unrecognised, and they will not be rendered.

## 1.1 Describing a set

### 1.1 Exercises

**QUESTION 1.1.**

The following are sets:

- `$\{1, \{2\}, 3\}$`
- `$\{1, 2, a, b\}$`

**QUESTION 1.2.**

Let `$S = \{-2, -1, 0, 1, 2, 3\}$`. The task is to describe the following sets in terms of `$S$`. Use the form `$\{x \in S: \ p(x)\}$`, where `$p(x)$` refers to some appropriate condition that the sets’ elements satisfy.

- `$A = \{1, 2, 3\}$`: `$\{x \in S: \ x \in \mathbb{Z}^+\}$`
- `$B = \{0, 1, 2, 3\}$`: `$\{x \in S: \ x \geq 0\}$`
- `$C = \{-2, -1\}$`: `$\{x \in S: \ x < 0\}$`
- `$D = \{-2, 2, 3\}$`: `$\{x \in S: \ x \notin \{-1, 0, 1\}\}$`

**QUESTION 1.4.**

List the elements of the following sets within braces.

> `$A = \{n \in \mathbb{Z} : \ -4 < n \leq 4\}$`  

`$\{-3, -2, -1, 0, 1, 2, 3, 4\}$`

> `$B = \{n \in \mathbb{Z} : \ n^2 < 5\}$`  

`$\{1, 2\}$`

> `$C = \{n \in \mathbb{N} : \ n^3 < 100\}$`  
    
```
ghci> filter (\y -> y < 100) $ map (\x -> x^3) [1..]
[1,8,27,64]
```

> `$D = \{x \in \mathbb{R} : \ x^2 - x = 0\}$`

$$
\begin{aligned}
x^2 - x &= 0 \\
x(x - 1) &= 0 \\
\end{aligned}
$$

Since `$x = 0$` or `$x = 1$`, we have `$\{0, 1\}$`.

> `$E = \{x \in \mathbb{R} : \ x^2 + 1 = 0\}$`

Since `$x = i$` or `$x = -i$`, we have `$\{\varnothing\}$` as the element of `$E$`.

**QUESTION 1.5.**

Rewrite each set in the form `$\{x \in \mathbb{Z}: \ p(x)\}$`. (Refer to the text for the original form of the sets.)

- `$A = \{x \in \mathbb{Z}: \ x < 0\}$`
- `$B = \{x \in \mathbb{Z}: \ -3 \leq x \leq 3\}$`
- `$C = \{x \in \mathbb{Z}: \ -2 \leq x \leq 2 \ \text{excluding zero}\}$`

**QUESTION 1.7.**

The _defining condition_ of a set `$E = \{..., -4, -2, 0, 2, 4, ...\}$` can be written as

$$
\begin{aligned}
E &= \\{y = 2x: \ x \in \mathbb{Z}\\}
&= \\{2x: x \in \mathbb{Z}\\}.
\end{aligned}
$$

Describe the following sets similarly.

- `$A = \{..., -4, -1, 2, 5, 8, ...\} = \{3x - 1: x \in \mathbb{Z}\}$`
- `$B = \{..., -10, -5, 0, 5, 10, ...\} = \{5x: x \in \mathbb{Z}\}$`
- `$C = \{1, 8, 27, 64, 125, ...\} = \{x^3: x \in \mathbb{Z}\}$`

**QUESTION 1.8.**

Let

$$
\begin{aligned}
A &= \\{n \in \mathbb{Z}: \ 2 \leq |n| \leq 4\\}, \\
B &= \\{x \in \mathbb{Q}: \ 2 < x \leq 4\\}, \\
C &= \\{x \in \mathbb{R}: \ x^2 - (2 + \sqrt{2})x + 2 \sqrt{2} = 0\\}, \\
\text{and} \ D &= \\{x \in \mathbb{Q}: \ x^2 - (2 + \sqrt{2})x + 2 \sqrt{2} = 0\\}.
\end{aligned}
$$

> Describe the set `$A$` by listing its elements.

`$A = \{-4, -3, -2, 2, 3, 4\}$`

> Give an example of three elements that belong to `$B$` but do not belong to `$A$`.

`$\left\{\frac{8}{3}, \frac{10}{3}, \frac{11}{3}\right\}$`

> Describe the set `$C$` by listing its elements.

$$
\begin{aligned}
x^2 - (2 + \sqrt{2})x + 2 \sqrt{2} &= 0 \\
x(x - 2 - \sqrt{2}) &= -2\sqrt{2}
\end{aligned}
$$

We have that `$x = -2\sqrt{2}$` or `$x - 2 - \sqrt{2} = -2\sqrt{2}$`. Working on the second root, we have

$$
\begin{aligned}
x = 2 - \sqrt{2}.
\end{aligned}
$$

As such, `$C = \{-2\sqrt{2}, 2 - \sqrt{2}\}$`.

> Describe the set `$D$` in another manner.

Since `$\sqrt{2}$` is an _irrational_ number, `$D = \{\varnothing\}$`.

> Determine the cardinality of each of the sets `$A$`, `$C$` and `$D$`.

$$
\begin{aligned}
|A| &= 6 \\
|C| &= 2 \\
|D| &= 0
\end{aligned}
$$

## 1.2 Subsets

- A set `$A$` is a **subset** of a set `$B$`, `$A \subseteq B$`, if every element in `$A$` is also an element in `$B$`.
- By the above definition, every set is a subset of itself.
- A set `$C$` is **not a subset** of a set `$D$`, `$C \not\subseteq D$`, if `$C$` has at least one element that is absent in `$D$`.
- Since the empty set `$\varnothing$` contains no elements, it cannot have an element that is absent in another set; going by the above definition, we can _never_ have a situation in which `$\varnothing \not\subseteq E$`, where `$E$` is an arbitrary non-empty set. Therefore, we conclude with the opposite assertion: `$\varnothing$` is a subset of every set.
- The **universal set** is denoted as `$U$` and it is the set we define in which our subsets of interest live. For example, when using Venn diagrams to draw sets, `$U$` is the rectangle that surround the circles (representing the subsets).
- If we have two sets `$A$` and `$B$` such that `$A \subseteq B$` and `$B \subseteq A$`, then `$A = B$`. Thus, an element `$x \in A$` is also said to have membership in `$B$`.
- A set `$A$` is a **proper subset** of a set `$B$` if `$A \subseteq B$` and `$A \neq B$`. In such a case we write `$A \subset B$`.
- The **power set** of a given set `$A$` is denoted as `$\mathcal{P}(A)$` and constitutes all combinations of subsets of `$A$` (which also includes both `$A$` itself and `$\varnothing$`, based on the above definitions). Hence, if `$A = \{1, 2\}$`, then `$\mathcal{P}(A) = \{\varnothing, \{1\}, \{2\}, \{1, 2\}\}$`. It is called a power set because, if `$A$` is a finite set, then `$\mathcal{P}(A) = 2^{|A|}$`. Notice that there is no specification stating that `$A$` must be non-empty: `$\mathcal{P}(\varnothing) = 2^{|\varnothing|} = 2^0 = 1$`.

### 1.2 Worked examples

**EXAMPLE 1.6.**

> We have two sets `$A$` and `$B$` that are each a subset of `$\{1, 2, 3, 4, 5\}$` and share the same dimension, such that `$|A| = |B| = 3$`.
>
> We also have the following constraints:
>
> - `$1$` belongs to `$A$` but not `$B$`.
> - `$2$` belongs to `$A$` but not `$B$`.
> - `$3$` belongs to exactly one of `$A$` and `$B$`.
> - `$4$` belongs to exactly one of `$A$` and `$B$`.
> - `$5$` belongs to at least one of `$A$` and `$B$`.
>
> What are the possibilities for the set `$A$`?

We know that `$1$` and `$2$`’s set memberships are mutually exclusive, so we’ll pick `$1$` for `$A$` (meaning that `$2$` goes to `$B$`). `$A$` and `$B$` each has one element. Next we assume that `$5$` is a member of both sets; `$A$` and `$B$` now have two elements each.

We finish off both sets by determining what goes into which so that both will have a dimension of 3. Since `$3$` and `$4$` belong to one set but not the other, we can take our pick of either number for `$A$`. Accordingly, `$A \subseteq \{1, 2, 3, 4, 5\}$` can be described as either `$\{1, 3, 5\}$` or `$\{1, 4, 5\}$`.

**EXAMPLE 1.8.**

For each set `$A$` below, determine the power set `$\mathcal{P}(A)$`, `$|A|$` and `$|\mathcal{P}(A)|$`.

> `$A = \{\varnothing\}$`

$$
\begin{aligned}
\mathcal{P}(A) &= \\{\varnothing\\} \\
|A| &= 0 \\
|\mathcal{P}(A)| &= 1
\end{aligned}
$$

> `$A = \{a, b\}$`

$$
\begin{aligned}
\mathcal{P}(A) &= \\{ \varnothing, \\{a\\}, \\{b\\}, \\{a, b\\} \\} \\
|A| &= 2 \\
|\mathcal{P}(A)| &= 4
\end{aligned}
$$

> `$A = \{1, 2, 3\}$`

$$
\begin{aligned}
\mathcal{P}(A) &= \\{ \varnothing, \\{1\\}, \\{2\\}, \\{3\\}, \\{1, 2\\}, \\{2, 3\\}, \\{1, 3\\}, \\{1, 2, 3\\} \\} \\
|A| &= 3 \\
|\mathcal{P}(A)| &= 8
\end{aligned}
$$

**Be aware that,** in `$\mathcal{P}(A)$`, `$\varnothing$` appears as itself and not `$\{\varnothing\}$` (which is interpreted as a subset containing an empty set). It’s important to remember that `$\varnothing \neq \{\varnothing\}$`.

### 1.2 Exercises

**QUESTION 1.14.**

Find `$\mathcal{P}(A)$` and `$|\mathcal{P}(A)|$` for the following sets.

> `$A = \{1, 2\}$`

`$\mathcal{P}(A) = \{ \varnothing, \{1\}, \{2\}, \{1, 2\} \}$`  
`$|\mathcal{P}(A)| = 4$`

> `$A = \{\varnothing, 1, \{a\}\}$`

`$\mathcal{P}(A) = \{ \varnothing, \{\varnothing\}, \{1\}, \{\{a\}\}, \{\varnothing, 1\}, \{\varnothing, \{a\}\}, \{1, \{a\}\}, \{\varnothing, 1, \{a\}\} \}$`  
`$|\mathcal{P}(A)| = 8$`

**QUESTION 1.16.**

> Find `$\mathcal{P}(\mathcal{P}(\{1\}))$` and its cardinality.

$$
\begin{aligned}
\mathcal{P}(\mathcal{P}(\\{1\\})) &= \mathcal{P(\\{ \varnothing, \\{1\\} \\})} \\
&= \\{ \varnothing, \\{\varnothing\\}, \\{1\\}, \\{\varnothing, \\{1\\}\\} \\} \\
\\
|\mathcal{P}(\mathcal{P}(\\{1\\}))| &= 4
\end{aligned}
$$

**QUESTION 1.20.**

Determine whether the following statements are true or false.

> If `$\{1\} \in \mathcal{P}(A)$`, then `$1 \in A$` but `$\{1\} \notin A$`.

False. `$1$` will indeed be a member of `$A$` but `$\{1\}$` could also be a member in the same set. If appearing alone in `$\mathcal{P}(A)$`, the latter would appear as `$\{ \{1\} \}$`.

> If `$A$`, `$B$` and `$C$` are sets such that `$A \subset \mathcal{P}(B) \subset C$` and `$|A| = 2$`, then `$|C|$` can be `$5$` but not `$4$`.

False. The set `$C$` could also be `$4$` because of the requirement that a proper subset not be identical to its parent set. If we increment the set membership count by one, then we have `$|A| = 2, |\mathcal{P}(B)| = 3$` and `$|C| = 4$`.

> If a set `$B$` has one more element than a set `$A$`, then `$\mathcal{P}(B)$` has at least two more elements than `$\mathcal{P}(A)$`.

True. We consider an example where `$|B| = 5$` and `$|A| = 4$`. Then `$\mathcal{P}(B) = 2^{4 + 1} = 2^4\cdot2^1 = 32$` and `$\mathcal{P}(A) = 2^4 = 16$`. If the two sets differ by one element, then `$B$`’s power set will contain twice the number of elements than `$A$`’s power set.

> If four sets `$A$`, `$B$`, `$C$` and `$D$` are subsets of `$\{1, 2, 3\}$` such that `$|A| = |B| = |C| = |D| = 2$`, then at least two of these sets are equal.

True. Since `${3\choose2} = 3$`, and we have four sets containing two elements each, at least two of them necessarily have to be identical.

## 1.3 Set operations

- **Union:** `$A \cup B = \{x: \ x \in A \ \text{or} \ x \in B\}$`
- **Intersection:** `$A \cap B = \{x: \ x \in A \ \text{and} \ x \in B\}$`
- For two sets `$A$` and `$B$`, their intersection is a subset of their union: `$A \cap B \subseteq A \cup B$`
- If `$A \cap B = \varnothing$`, then the sets `$A$` and `$B$` are said to be **disjoint**; a real-world example of this is the sets `$\mathbb{Q}$` and `$\mathbb{I}$`
- The **difference** `$A - B$` of two sets `$A$` and `$B$` is defined as `$A - B = \{x: \ x \in A \ \text{and} \ x \not\in B\}$`; this is essentially what a **left anti-join** is
- Consider a universal set `$U$` in which all sets of interest are subsets of it, including the set `$A$`
  - Then, the **complement** of `$A$` is denoted as `$\overline{A} = U - A = \{x: \ x \in U \ \text{and} \ x \not\in A\}$`; notice the complement is defined in terms of a difference
  - The complement of `$A$` could also be written as `$A^{\prime}$`
  - We use the `overline` command in `$\LaTeX$` rather than `bar` to denote the complement (the latter results in a narrow bar)
- Going back to the difference of two sets, the set `$A - B$` can be expressed in terms of complements: `$A - B = A \cap \overline{B}$`

## 1.3 Exercises

**QUESTION 1.22.**

Let `$U = \{1, 3, ..., 15\}$` be the universal set, `$A = \{1, 5, 9, 13\}$` and `$B = \{3, 9, 15\}$`. Determine the following sets.

> `$A \cup B$`

`$\{1, 3, 5, 9, 13, 15\}$`

> `$A \cap B$`

`$\{9\}$`

> `$A - B$`

`$\{1, 5, 13\}$`

> `$B - A$`

`$\{3, 15\}$`

> `$\overline{A}$`

`$\{3, 7, 11, 15\}$`

> `$A \cap \overline{B}$`

This is the same as `$A - B$`.

**QUESTION 1.30.**

Let `$A = \{x \in \mathbb{R}: \ |x - 1| \leq 2\}$`, `$B = \{x \in \mathbb{R}: \ |x| \geq 1\}$` and `$C = \{x \in \mathbb{R}: \ |x + 2| \leq 3\}$`.

> Express `$A$`, `$B$` and `$C$` using interval notation.

`$A = [-1, 3]$`  
`$B = (-\infty, -1] \cup [1, \infty)$`  
`$C = [-5, 1]$`

> Determine each of the following sets using interval notation:  
> `$A \cup B$`, `$A \cap B$`, `$B \cap C$`, `$B - C$`.

`$A \cup B = (-\infty, \infty)$`  
`$A \cap B = [-1] \cup [1, 3]$`  
`$B \cap C = [-5, -1] \cup [1]$`  
`$B - C = (-\infty, -6] \cup [2, \infty)$`