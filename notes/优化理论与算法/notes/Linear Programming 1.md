## 标准型
$$
\begin{align*}
	&minimize\quad c^Tx \\
	&subject\,to\quad Ax=b \\
    &\qquad \qquad \qquad x\ge{0}
\end{align*}
$$

## 多面体
$$
	\{x\in \mathbb{R}\,|\,Ax\ge b\}
$$
线性规划的标准型可以改写成多面体的形式

## 极值点

[[lp_3几何性质介绍.pdf#page=9]]

## 基本解
1. $Ax=b$
2. $\exists$ 线性独立的列向量组

只和约束有关
	求解时直接将线性相关的$x_i$令为0后求解$Ax=b$

## 基本可行解
1. 是基本解
2. $x\ge0$

极值点 $\Leftrightarrow$ 基本可行解

对于存在最优解的LP问题，寻找最优解实际上就是在找基本可行解中最好的
