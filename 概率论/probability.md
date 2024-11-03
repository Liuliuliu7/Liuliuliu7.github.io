[TOC]

# 概率论
Course: [Probabilistic Systems Analysis and Applied Probability | Electrical Engineering and Computer Science | MIT OpenCourseWare](https://ocw.mit.edu/courses/6-041-probabilistic-systems-analysis-and-applied-probability-fall-2010/)
Book: [Introduction to Probability](./Introduction%20to%20Probability,%202nd%20Edition%20(Dimitri%20P.%20Bertsekas,%20John%20N.%20Tsitsiklis)%20(Z-Library).pdf)
[概率论基础中文](./概率论基础%20第三版%20(李贤平)%20(Z-Library).pdf)

## 第一章

### 事件与概率

#### 频率

#### 古典概率
**性质**
- 非负性 $P(A) >= 0$
- 规范性 $P(S) = 1$
- 加法 $P(A U B) = P(A) + P(B) - P(A \cap B)$

**样本点**
- 样本空间 $\Omega$: 一次试验的所有可能结果的集合
- 样本点 $\omega$: 样本空间中的元素
- 事件 $A \subseteq \Omega $: 样本空间的子集 $\rightarrow $ 事件之间的关系转换为集合之间的关系

**德摩根定律**

$$
\begin{array}{lll}
A \cap B = \overline{^{} { (\bar{A} \cup \bar{B})}} \\
A \cup B = \overline{^{} { (\bar{A} \cap \bar{B})}} \\
A - B = A \cap \bar{B} 
\end{array}
$$

**组合数**
$$
C_n^r ={n  \choose r}= \frac{n!}{r!(n-r)!}
$$
这里的组合数意义是二项式系数
$$
(a+b)^n=\sum_\limits{r=0}^{n} {n \choose r} a^{r}b^{n-r}
$$
可以定义多项式系数
$$
P_n^{(r_1,r_2,...,r_k)} = \frac{n!}{r_1!r_2!...r_k!}, \text{for } r_1+r_2+...+r_k=n
$$
这里的多项式系数代表了多项式的展开式中的系数
$$
(a_1+a_2+...+a_k)^n = \sum_\limits{r_1+r_2+...+r_k=n} P_n^{(r_1,r_2,...,r_k)} a_1^{r_1}a_2^{r_2}...a_k^{r_k}
$$
**重复组合数**
$$
H_n^r = {n+r-1 \choose r} = \frac{(n+r-1)!}{r!(n-1)!}
$$
***Proof***:
设 $n$ 个不同的元素为 $1,2,3,\ldots,n$
设取出的 $r$ 个元素为 $a_1,a_2,a_3,\ldots,a_r$
构造一个组合 $b_1,b_2,b_3,\ldots,b_r$
其中
$$
\begin{array}{lll} 
b_1 = a_1 \\
b_2 = a_2 + 1 \\
b_3 = a_3 + 2 \\
\ldots \\
b_r = a_r + r - 1
\end{array} 
$$
显然 $b_i$ 是不重复的，且 $b_i \in \{1,2,3,\ldots,n+r-1\}$，所以有 $H_n^r$ 种组合

讨论组合数时，下列的展开式是有用的
$$
(1+x)^n=\sum_\limits{r=0}^{n} {n \choose r} x^{r}
$$
令 $x=1$，得到
$$
2^n = \sum_\limits{r=0}^{n} {n \choose r}
$$
$$
\begin{array}{lll}
(1+x)^a(1+x) ^b = (1+x)^{a+b} \\
\sum_\limits{n1=0}^{a} {a \choose n1} x^{n1} \sum_\limits{n2=0}^{b} {b \choose n2} x^{n2} = \sum_\limits{n=0}^{a+b} {a+b \choose n} x^{n} , \text{for } n1+n2=n
\end{array}
$$
可以由系数相等得到
$$
{a \choose 0} {b \choose n}  + {a \choose 1} {b \choose n-1} + ... + {a \choose n} {b \choose 0} = {a+b \choose n}
$$
when $n = a,b$
$$
{n \choose 0}^2 + {n \choose 1}^2 + ... + {n \choose n}^2 = {2n \choose n}
$$
可以定义
$$
\begin{array}{ccc}
A_x^r = x(x-1)\cdots (x-r+1),\text{ for } x \in  \Re  \text{ and } r \in N\\
{x \choose r} = \frac{A_x^r}{r!}
\end{array}
$$
可以验证
$$
{-a \choose k} = (-1)^k {a+k-1 \choose k}
$$

**二项分布和超几何分布**

$$
\begin{array}{ccc}
b_k = {n \choose k} p^k (1-p)^{n-k}\\
h_k = \frac{{M \choose k} {N-M \choose n-k}}{{N \choose n}}
\end{array}
$$
**古典概率的基本性质**
1. 非负性 $P(A) \geq 0$
2. 规范性 $P(S) = 1$
3. 加法 $P(A \cup B) = P(A) + P(B) - P(A \cap B)$

#### 几何概率
几何概率定义
$$
P(A_g) = \frac{m}{n}, m为g的测度，n为\Omega的测度
$$
**几何概率基本性质**
1. 非负性 $P(A) \geq 0$
2. 规范性 $P(S) = 1$
3. 加法 $P(\sum_\limits{n=1}^{\infty }A_n) = \sum_\limits{n=1}^{\infty }P(A_n)$

#### 概率论公理化
记全体事件为 $\Gamma $，由 $\Omega $ 的部分子集（可测度的）构成，为了便于讨论，对 $\Gamma$ 加入如下限制：
1. $\Omega \in \Gamma$
2. 若 $A \in \Gamma$，则 $\bar{A} \in \Gamma$
3. 若 $A_1,A_2,... \in \Gamma$，则 $\cup_{n=1}^{\infty}A_n \in \Gamma$

满足上述条件的集合 $\Gamma$ 称为 $\Omega$ 的 $\sigma$ 代数
**定理**：给定 $\Omega$ 的非空子集 $\mathcal{F}$，必存在唯一一个 $\sigma$ 代数 $\Gamma$，使得 $\mathcal{F} \subseteq \Gamma$, 且 $\Gamma$ 是 $\mathcal{F}$ 的最小 $\sigma$ 代数
**证明**：

**博雷尔点集**

$$
\begin{array}{ccc}
\mathcal{B}_1 = \{a,b \in \mathcal{R}^1 | [a, b)\} \\
\mathcal{B}_n = \{x_i, y_i \in \mathcal{R}^n, r \in \mathcal{R}^1  |\sqrt{(x_i - y_i)^2} < r\}
\end{array}
$$

**概率的定义**
$P:$ $\Gamma \rightarrow \mathcal{R}^1$，满足
1. 非负性 $P(A) \geq 0$
2. 规范性 $P(\Omega) = 1$
3. 加法 $P(\bigcup_{n=1}^{\infty}A_n) = \sum_\limits{n=1}^{\infty}P(A_n)$
#### 习题
45: 证明 $\left|P(AB) - P(A)P(B)\right| \le \frac{1}{4}$
***Proof:***
只证明一个方向：
$P(AB) - P(A)P(B) \le \frac{1}{4}$
Obiously $P(A) \ge P(AB) \text{ and } P(B) \ge P(AB)$, so we have $P(A)P(B) \ge P(AB)^2$ so $P(AB) - P(A)P(B) \le P(AB) - P(AB)^2$, so define $x = P(AB)$, then $f(x) = x(1-x)$, obiously $f(x) \le \frac{1}{4}$

## 第二章
在此都假设事件是独立同分布的
### 几何分布
$$
\begin{array}{ccc}
W_k = \bar{A_1} \bar{A_2} \cdots \bar{A_k} \cdots {A_n}\\
g(k;p)=P(W_k) = (1-p)^{k-1} p
\end{array}
$$
由于 $g(k;p)$ 是几何级数的一般项，所以有
$$
\sum_\limits{k=1}^{\infty } g(k;p) = \sum_{k=1}^{\infty } (1-p)^{k-1} p = p \sum_{k=0}^{\infty } (1-p)^k = p \frac{1}{1-(1-p)} = 1
$$
显然，几何分布具有无记忆性
$$
P(\eta ' =k) = P(\eta  = m + k | \eta  > m) = q^{k-1}p
$$
### 帕斯卡分布
第 $\eta$ 次成功发生在第 $r$ 次试验的概率 $P(C_k)$
$$
P(C_k) = {k-1 \choose r-1} p^r (1-p)^{k-r}
$$
### 二项分布
$$
b(k;n,p) = {n \choose k} p^k (1-p)^{n-k}
$$
单调性：
$$
\frac{b(k;n,p)}{b(k-1;n,p)}=\frac{n-k+1}{k} \frac{p}{1-p} \ge 1 \text{ for } k \le \frac{n(1-p)}{p}
$$
when $k=\lfloor (n+1)p \rfloor$ 时值最大
可以证明 $b(m;n,p)\approx (2\pi npq)^{-\frac{1}{2}}$
### 泊松分布
若 $np_n \rightarrow \lambda$, 则当 $n \rightarrow \infty$ 时，$b(k;n,p_n) \rightarrow \frac{\lambda^k}{k!}e^{-\lambda}$
这里 $k$ 应该不太大
下面研究泊松过程
**引理**
若函数 $f(x)$ 满足 $f(x+y) = f(x) f(y), \text{ for } \forall x, y \in R$, 则 $f(x) = a^x$
考虑一个事件 A，其满足如下性质
1. 平稳性：$[t_0,t)$ 时间内，$k$ 与 $t_0$ 无关，至于 $t$ 有关
2. 独立增量性：$[t_0,t_1)$ 与 $[t_1,t_2)$ 是独立的
3. 普通性：充分小时间内，最多发生一次
记 $P_k(t)$ 为时间 $t$ 内发生 $k$ 次的概率

则 $[0, t+\Delta t)$ 中到来 $k$ 次的概率为
$$
P_k(t+\Delta t) = P_k(t)P_0(\Delta t) + P_{k-1}(t)P_1(\Delta t) + \cdots + P_0(t)P_k(\Delta t)
$$
当 $k=0$ 时，有 $P_0(t+\Delta t) = P_0(t)P_0(\Delta t)$
则 $P_0(t)=a^t = e^{-\lambda t}$
由于普通性 $P_l(\Delta t) \rightarrow 0 , \text{ for } \forall l \ge 2$
则 $$
P_k(t+\Delta t) = P_k(t)P_0(\Delta t) + P_{k-1}(t)P_1(\Delta t)
$$
可以近似得到：
$$
P_k(t) = \frac{(\lambda t)^k}{k!} e^{-\lambda t}
$$
### 习题
46. 证明下面等式
$$
\sum_{k=0}^{N}{N+k \choose k}(\frac{1}{2})^k = 2^N
$$
***Proof:***

## 第三章
随机变量$\eta $：将样本空间映射到实数集的函数，即$\Omega \stackrel{\eta }{\longrightarrow  } \mathcal{R}^1$
分布函数：$F_{\eta }(x) = P(\eta(\omega ) \le x)$
其中$F(x-0) = F(x)$

### 正态分布
一元分布
$$ f(x|\mu, \sigma) = \frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^2} $$
二元分布
$$
f(x_1, x_2) = \frac{1}{2\pi\sigma_1\sigma_2\sqrt{1-\rho^2}} \exp\left(-\frac{1}{2(1-\rho^2)}\left[\frac{(x_1-\mu_1)^2}{\sigma_1^2} - 2\rho\frac{(x_1-\mu_1)(x_2-\mu_2)}{\sigma_1\sigma_2} + \frac{(x_2-\mu_2)^2}{\sigma_2^2}\right]\right)
$$
可以将二元分布函数进行分解
1. $N(\mu _1, \sigma _1^2)$ + $N(\mu _2+\rho \frac{\sigma _2}{\sigma _1}(x-\mu _1), \sigma _2^2(1-\rho ^2)$
2. $N(\mu _2, \sigma _2^2)$ + $N(\mu _1+\rho \frac{\sigma _1}{\sigma _2}(y-\mu _2), \sigma _1^2(1-\rho ^2)$

$n$元分布
$$
f(\mathbf{x}) = \frac{1}{(2\pi)^{n/2}|\boldsymbol{\Sigma}|^{1/2}} \exp\left(-\frac{1}{2}(\mathbf{x}-\boldsymbol{\mu})^T\boldsymbol{\Sigma}^{-1}(\mathbf{x}-\boldsymbol{\mu})\right)
$$
### 指数分布
$$
F(x) = 1 - e^{-\lambda x}, x \ge 0
$$
无记忆性
$$
P(\eta > s+t | \eta > s) = P(\eta > t)
$$
### 条件分布
$$
P(\eta < y | \xi =x) = \frac{P(\eta \le y, \xi = x)}{P(\xi = x)} = \frac{f_{\eta , \xi }(y,x)}{f_{\xi }(x)}
$$
### 独立性 
设$\eta _1, \eta _2, \cdots, \eta _n$为随机变量，若对于任意的$x_1, x_2, \cdots, x_n$有
$$
P(\eta _1 < x_1, \eta _2 < x_2, \cdots, \eta *n < x_n) = P(\eta *1 < x_1)P(\eta *2 < x_2) \cdots P(\eta *n < x_n)
$$
对于连续型随机变量，可以用密度函数来表示
$$
p(x_1, x_2, \cdots, x_n) = p(x_1)p(x_2) \cdots p(x_n)
$$

### 随机变量的函数
1. 转换法
当$y=g(x)$单调时
$$
G(y) = P(\eta \le y) = P(g(x) \le y) = P(x \le g^{-1}(y)) = F(g^{-1}(y))
$$
当$y=g(x)$分段单调时
$$
G(y) = \sum*{i} P(x \in A_i) = \sum*{i} P(g(x) \in B_i) = \sum*{i} P(y \in B_i) = \sum*{i} F(g^{-1}(y))
$$
2. 变换法
当$\eta =g(\xi)$单调时
$$
p(\eta) = p(g^{-1}(y))\left|\frac{d}{dy}g^{-1}(y)\right|
$$
### 随机向量的函数
利用转换法或变换法可以讨论
1. $\eta = \xi _1 + \xi _2$
2. $\eta = \xi _1 \xi _2$
3. $\eta = \xi _1 / \xi _2$

**顺序统计量**
若$\eta _1, \eta_2, \cdots, \eta_n$ 是来自同一分布的$n$个独立同分布的随机变量，$F(x)$是其分布函数，$f(x)$是其密度函数，$F_n(x)$是其顺序统计量的分布函数，$f_n(x)$是其密度函数。若按照某一次实验的结果的大小顺序排列，第$i$个实验的结果记为$\eta _{(i)}$，则有
$$
\eta^* _1 \le \eta _2^* \le \cdots \le \eta _n ^*
$$
极大值$\eta ^*_n$的分布函数为
$$
P(\eta _n^* \le x) = P(\eta _1 \le x, \eta _2 \le x, \cdots, \eta _n \le x) = F(x)^n
$$
极小值$\eta _1^*$的分布函数为
$$
P(\eta _1^* \le x) = 1 - P(\eta _1 > x, \eta _2 > x, \cdots, \eta _n > x) = 1 - (1-F(x))^n
$$