# Discrete mathematics

This is the dedicated storage space for maths-related notes, exercise answers and more. I’m using GitHub rather than GitLab because the latter imposes a limit on the number of mathematical expressions that can be rendered in LaTeX (exactly 50).

**Important to note** is that I’ve installed [xhub](https://github.com/nschloe/xhub#latex) on my browsers, to be better able to render mathematical expressions. This decision is largely influenced by this [blog post](https://nschloe.github.io/2022/05/20/math-on-github.html) which recommends xhub (which is also the author’s creation, by the way). Inline maths statements should be introduced with the following syntax:

```
`$…$`
```

Display maths are best written in a **code block**. It’s possible to use `katex` to specify the LaTeX generator instead of just `math` – KaTeX is known to be quicker to render than MathJax, which is what GitHub uses by default.

To trigger GitHub’s **online IDE**, replace `github.com/*` with `github.dev/*` and the online editor will load.