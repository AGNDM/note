## 完备性
完备性的提出主要是为了让Rao-Blackwell定理能够直接确保我们能找到MVUE。

## 正则指数分布类
一类可以写成以下形式的分布

$$
\begin{align}
f(x;\theta) & =\exp\{p(\theta)K(x)+H(x)+q(\theta)\}, x \in S \\
f(x;\theta) & =0, x\not\in S
\end{align}
$$

实际上大多数我们常见的分布类型都可以写成这种形式

同时我们也可以发现，在这里我们运用Neyman分解定理可以求得$\sum_{i=1}^nK(X_{i})$实际上就是SS，也就是CSS


最后我们总结得到我们可以利用Rao-Blackwell定理达到：CSS+无偏$\to$MVUE