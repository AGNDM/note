## 如何寻找初始基本可行解
### 两阶段法
对于原问题
$$
\begin{align*}
	minimize_{x}\quad c^Tx&\\
	subject\;to\quad Ax&=b\\
	x &\ge 0
\end{align*}
$$
使用辅助问题
$$
\begin{align*}
	minimize_{x,y}\quad e^Ty&\\
	subject\;to\quad Ax+y&=b \\
	x,y&\ge 0 \\
	\\
	where\quad e = 
\begin{pmatrix}
1 \\
1 \\
\vdots \\
1
\end{pmatrix}	
\end{align*}
$$
不妨假设$b \ge 0$，这个问题有基本可行解
$$
X^*=
\begin{cases}
	 x=0\\
	 y=b \ge 0
\end{cases}
$$
从$X^*$开始，我们进行单纯形法求解
1. 如果最终的最优值不为0，则原问题不可行
2. 否则，$X^*$就是原问题的一个初始可行解

使用这一方法需要注意构造时要使$b \ge 0$并化成**规范型**

### 大M法
核心思想是用一个很大的惩罚M来达到两阶段法的第一阶段，然后自然而然转向第二阶段
构造辅助问题
$$
\begin{align*}
	minimize_{x}\quad c^Tx+M& \sum_{i=1}^m y_{i}\\
	subject\;to\quad Ax+y&=b\\
	x,y &\ge 0
\end{align*}
$$
这个问题有初始可行解
$$
X_{init}=
\begin{cases}
x=0 \\
y=b
\end{cases}
$$

### 布兰德法则
始终选择下标最小的那个入基/出基，就不会出现循环
证明见$Bertsimas \S 3.4$

### 复杂度
没看懂，似乎不是很复杂
