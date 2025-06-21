这一章主要是研究似然比

我们之前在假设检验中研究过似然函数，并且我们认为能使似然函数达到最大值的参数$\hat{\theta}$的估计量是非常好的，把它适当纠偏后我们就得到了很合理的一个估计量。

但是，之前我们在计算出这个极大似然估计之后只能依靠直觉判断他的拒绝域，在这一章里我们希望借助似然比来系统性地分析拒绝域的选取。

首先定义似然比

$$
\Lambda=\frac{L(\theta_{0};X)}{L(\hat{\theta};X)}
$$

### 似然比检验
我们可以发现，$\Lambda$越靠近1，越好，所以我们的拒绝域就是形如$\{\Lambda\leq c\}$

进一步我们发现$\Lambda$还有一些非常好的性质

$$
\begin{align}
-2\log \Lambda  & \to \chi^2(1) \\
H_{0}下,\quad\hat{\theta} & \to \theta \\
\sqrt{ n }(\hat{\theta}-\theta_{0}) & \to N\left(0, \frac{1}{I(\theta_{0})} \right)
\end{align}
$$

### Wald型检验
由上面最后一条性质我们变形

$$
\sqrt{nI(\theta_{0})}(\hat{\theta}_{n}-\theta_{0})\to N(0,1)
$$

所以我们就可以使用统计量

$$
	\chi^2_{W}=nI(\hat{\theta}_{n})(\hat{\theta}_{n}-\theta_{0})^2
$$

它服从卡方分布，我们一般就看可以用卡方分布的上$\alpha$部分作为拒绝域

### 得分型检验
由于一些数学上的原因，我们发现另一个统计量也有很好的性质

$$
	\chi^2_{R}=\left\{\frac{l'(\theta_{0})}{\sqrt{ nI(\theta_0) }}\right\}^2\sim nI(\theta_{0})(\hat{\theta}_{n}-\theta_{0})^2\to \chi^2(1)
$$

所以我们可以通过类似的方法也选一个拒绝域

