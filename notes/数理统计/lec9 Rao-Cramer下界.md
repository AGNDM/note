## Fisher 信息量
首先对总体$X$有对数极大似然估计函数

$$
	\log f(X;\theta)
$$

然后我们定义Fisher信息量

$$
	I(\theta)=E\left[ \left\{ \frac{{\partial \log f(X;\theta)}}{\partial \theta} \right\}^2 \right]
$$

接着如果满足了一些可导性方面的要求，我们还有

$$
{\begin{align}
I(\theta) & =Var\left[ \frac{{\partial\log f(X;\theta)}}{\partial \theta} \right] \\
I(\theta) & =-E\left[ \frac{{\partial^2\log f(X;\theta)}}{\partial \theta^2} \right]
\end{align}}
$$

可以看出，Fisher信息量和我们的对数极大似然函数十分相关

并且我们同时定义score function

$$
	 \frac{{\partial \log f(X;\theta)}}{\partial \theta} 
$$

## Rao-Cramer下界
我们在估计参数$\theta$的时候会想要我们的估计量$Y=u(X_{1},X_{2},\dots,X_{n})$的方差尽可能小，而Rao-Cramer下界就告诉我们了最小可能是多少（不一定真正能达到）。同时，我们令$E[Y]=k(\theta)$

有了Fisher信息量，我们定义Rao-Cramer下界

$$
	Var(Y)\geq \frac{[k'(\theta)]^2}{nI(\theta)}
$$

当$k(\theta)=\theta$，即我们的估计量$Y$是无偏的时候，我们的下界就是

$$
	Var(Y)\geq \frac{1}{nI(\theta)}
$$

### 有效性
一个无偏估计量的有效性通常会定义为

$$
\frac{\text{最小可能方差（一般就是RCB）}}{\text{无偏估计量的方差}}
$$

因此效率越靠近1越好

### RCB
如果估计量$Y$是无偏的，并且其方差达到了RC下界，则称它为RCB
