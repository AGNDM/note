## ANOVA 单因素方差分析
### 定义
推断两个或两个以上总体均值是否有差异的检验方法，我们主要讨论但因素（factor，对实验指标产生影响的原因）的情况

考虑假设检验：
$$
	H_{0}:\mu_{1}=\mu_{2}=\dots=\mu_{n}\quad vs\quad H_{1}: \mu\text{不全相等}
$$

我们有很多个总体$X_{1},X_{2},\dots,X_{r}$，对于某一个总体$X_i$中有样本$X_{i1},X_{i2},\dots,X_{in_{i}}$

$$
{\begin{align}
所有总体的样本数量之和n & =\sum_{i=1}^rn_{i} \\
第i个总体的样本均值\bar{X}_{i} & =\frac{1}{n_{i}}X_{ij} \\
所有总体的样本的均值\bar{X} & =\frac{1}{n}\sum_{i=1}^r\sum_{j=1}^{n_{i}}X_{ij} \\
\text{total sum of squares }S_{T} & =\sum_{i=1}^r\sum_{j=1}^{n_{i}}(X_{ij}-\bar{X})^2 \\
\text{sum of squares between groups }S_{A} & =\sum _{i=1}^rn_{i}(\bar{X}_{i}-\bar{X})^2  \\
\text{sum of squares within group }S_{E} & =\sum_{i=1}^r\sum_{j=1}^{n_{i}}(X_{ij}-\bar{X}_{i})^2
\end{align}}
$$

需要注意的点：
1. 前三个是我们对数据的预处理，我们采取三种方法看待后面的三个统计量，第一种是把所有总体的样本抽出来看作同一个大整体的统计量$X_{big}$，而$S_T$就是这个$X_{big}$的方差。第二种是把每一个总体转化成一个（方差，样本量）的新样本，放到一个新的总体里，然后用样本量为权求方差的加权方差。最后一个是各个总体的方差之和。
2. $S_{T}=S_{A}+S_{E}$
3. $\frac{S_{E}}{\sigma^2}\sim \chi^2(n-r)$由学生定理
4. $H_{0}$下，$\frac{S_{A}}{\sigma^2}\sim \chi^2(r-1)$
5. 由3和4，我们有$\frac{{\frac{S_{A}}{r-1}}}{\frac{S_{E}}{n-r}}\sim F(r-1,n-r)$这是我们拒绝域的来源

### ANOVA表
Source | Sum of squares | Degree of freedom | Mean squares | F | p-value | F crit
-- | -- |--|--|--|--|--|
Between group|$S_A$|$r-1$|$MS_A=\frac{S_{A}}{r-1}$|$\frac{MS_{A}}{MS_{E}}$|$P\{F(r-1,n-r)\geq f_{0}\}$|$F_{\alpha}(r-1,n-1)$
Within group|$S_E$|$n-r$|$MS_{E}=\frac{S_{E}}{n-r}$|
Total|$S_{T}$|$n-1$