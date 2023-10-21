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
        x = 0 \ \text{or} \ x &= 1 \\
        \text{Therefore } \{0, 1\}
        $$
    \end{aligned}
- `$E = \{x \in \mathbb{R} : \ x^2 + 1 = 0\}$`