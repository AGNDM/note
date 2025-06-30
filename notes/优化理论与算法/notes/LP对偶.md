$$
\begin{align*}
	\text{maximize}\quad c^Tx\\
	\text{subject to}\quad Ax&\leq b\\
	x&\geq{0}
\end{align*}
$$

$$
\begin{align}
\text{minimize}\quad b^Ty \\
\text{subject to}\quad A^Ty&\geq c \\
y&\geq{0} \\
\end{align}
$$

![[Pasted image 20250622202429.png]]

![[Pasted image 20250622203255.png]]

弱对偶、强对偶


## 互补松弛

![[Pasted image 20250622203545.png]]

$$
	最优\leftrightarrow x_{i}(c_{i}-A_{i}^Ty)=0
$$

这个的一种理解是，如果一个$x_{i}$在原问题里是最优解的非基变量，那么它肯定不是0，所以他必然独立地满足了一条原问题的约束，那么对应的就有一个$y_{i}$自由了，可以独立地让对偶问题中的一条约束得到满足（取等）

LP中的对偶的思路是将每一个约束和对偶问题中的一个变量建立联系。在最优解处，得益于强对偶，我们发现约束被满足和对偶问题中的变量被置零至少有一条要被满足。

## 灵敏度
### 局部
![[Pasted image 20250622205328.png]]
其中，$y^*$称为$b$的影子价格

### 全局
不会