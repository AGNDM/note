## 参数的函数
寻找$g(\theta)$的MVUE
1. 直接找SS的某个个函数值，然后把他的期望纠偏到$g(\theta)$
2. 先找到$g(\theta)$的一个无偏估计量，然后用Rao-Blackwell找到MVUE

对于第一种想法，我们最朴素的构造就是用$g(\theta)$的MLE，也就是把$\hat{\theta}$代进去。更复杂地，我们可以用一些巧妙的构造比如$E[X_{1}+X_{2}]=g(\theta)$

## 指数分布类
$$
f(x;\theta)  =\exp\left\{ \sum_{j=1}^mp_{j}(\theta)K_{j}(x)+H(x)+q(\theta) \right\}, x \in S
$$

我们同样可以通过Neyman分解定理找出SS

## 最小充分性和从属统计量
通俗理解下最小的意思是其他的SS都可以由这个SS加以表达出来

从属统计量就是我们在这个过程中剔除的那些，或者说没什么关系的那些统计量
