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
- For **displays**, use this form and note that the curly braces have to be escaped _twice_:
    ```
    $$
    \begin{aligned}
    \\{<elements_of_set>\\}
    \end{aligned}
    $$
    ```
  Failing to escape twice causes the curly braces to be unrecognised, and they will not be rendered.

## 1.1: Describing a set

### Exercises

**Question 1.1**

The following are sets:

- `$\{1, \{2\}, 3\}$`
- `$\{1, 2, a, b\}$`

**Question 1.2**

Let `$S = \{-2, -1, 0, 1, 2, 3\}$`. The task is to describe the following sets in terms of `$S$`. Use the form `$\{x \in S: \ p(x)\}$`, where `p(x)` refers to some appropriate condition that the sets’ elements satisfy.

- `$A = \{1, 2, 3\}$`: `$\{x \in S: \ x \in \mathbb{Z}^+\}$`
- `$B = \{0, 1, 2, 3\}$`: `$\{x \in S: \ x \geq 0\}$`
- `$C = \{-2, -1\}$`: `$\{x \in S: \ x < 0\}$`
- `$D = \{-2, 2, 3\}$`: `$\{x \in S: \ x \notin \{-1, 0, 1\}\}$`

**Question 1.4**

List the elements of the following sets within braces.

- `$A = \{n \in \mathbb{Z} : \ -4 < n \leq 4\}$`  
    `$\{-3, -2, -1, 0, 1, 2, 3, 4\}$`
- `$B = \{n \in \mathbb{Z} : \ n^2 < 5\}$`  
    `$$\{1, 2\}`
- `$C = \{n \in \mathbb{N} : \ n^3 < 100\}$`  
    ```
    ghci> filter (\y -> y < 100) $ map (\x -> x^3) [1..]
    [1,8,27,64]
    ```
- `$D = \{x \in \mathbb{R} : \ x^2 - x = 0\}$`

    $$
    \begin{aligned}
    x^2 - x &= 0 \\
    x(x - 1) &= 0 \\
    \end{aligned}
    $$

    Since `$x = 0$` or `$x = 1$`, we have `$\{0, 1\}$`.
- `$E = \{x \in \mathbb{R} : \ x^2 + 1 = 0\}$`

    Since `$x = i$` or `$x = -i$`, we have `$\{\varnothing\}$` as the element of `$E$`.

**Question 1.5**

Rewrite each set in the form `$\{x \in \mathbb{Z}: \ p(x)\}$`. (Refer to the text for the original form of the sets.)

- `$A = \{x \in \mathbb{Z}: \ x < 0\}$`
- `$B = \{x \in \mathbb{Z}: \ -3 \leq x \leq 3\}$`
- `$C = \{x \in \mathbb{Z}: \ -2 \leq x \leq 2 \ \text{excluding zero}\}$`

**Question 1.7**

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

**Question 1.8**

Let

$$
\begin{aligned}
A &= \\{n \in \mathbb{Z}: \ 2 \leq |n| \leq 4\\}, \\
B &= \\{x \in \mathbb{Q}: \ 2 < x \leq 4\\}, \\
C &= \\{x \in \mathbb{R}: \ x^2 - (2 + \sqrt{2})x + 2 \sqrt{2} = 0\\}, \\
\text{and} \ D &= \\{x \in \mathbb{Q}: \ x^2 - (2 + \sqrt{2})x + 2 \sqrt{2} = 0\\}.
\end{aligned}
$$

- Describe the set `$A$` by listing its elements.

    `$A = \{-4, -3, -2, 2, 3, 4\}$`
- Give an example of three elements that belong to `$B$` but do not belong to `$A$`.

    `$\left\{\frac{8}{3}, \frac{10}{3}, \frac{11}{3}\right\}$`
- Describe the set `$C$` by listing its elements.

    <!-- $$
    \begin{aligned}
    x^2 - (2 + \sqrt{2})x + 2 \sqrt{2} &= 0 \\
    x(x - 2 - \sqrt{2}) &= - \sqrt{2}
    \end{aligned}
    $$ -->
- Describe the set `$D$` in another manner.
- Determine the cardinality of each of the sets `$A$`, `$C$` and `$D$`.

$$
\begin{aligned}
x^2 - (2 + \sqrt{2})x + 2 \sqrt{2} &= 0 \\
x &= - \sqrt{2}
\end{aligned}
$$