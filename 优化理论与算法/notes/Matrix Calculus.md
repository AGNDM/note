## Gradient 
$$
(\nabla_{A}f(A)))_{ij} = 
\frac{{\partial f(A)}}{\partial A_{ij}}
$$

## Hessian
$$
\nabla^2_{x}f(x)\in\mathbb{R}^{n\times n}=
\begin{bmatrix} 
\nabla_{x}(\nabla_{x}f(x))_1\dots\nabla_{x}(\nabla_{x}f(x))_{n}
\end{bmatrix}
$$

## Quadratic
$$
\begin{align*}
\nabla_{x}b^Tx&=b\\
\nabla_{x}x^TAx&=2Ax(\text{if A symmetric})\\
\nabla_{x}^2x^TAx&=2A(\text{if A symmetric})
\end{align*}
$$

## Determinant
$$
\nabla_A |A| = (\text{adj}(A))^T = |A|A^{-T}
$$

It is worth mentioning that here our input is a $m\times n$ matrix so the result is also a $m\times n$ matrix instead of a $(m+n)\times 1$ one.