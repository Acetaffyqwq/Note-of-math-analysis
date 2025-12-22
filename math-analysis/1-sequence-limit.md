---
layout: default
title: 数列极限
sort_order: 1
is_note: true
---

## 无穷小量

对于数列 $\{x_n\}$，$\forall \epsilon \exists N,\forall n>N,\mid x_n\mid<\epsilon$，则为无穷小量， $\lim_{n\to \infty} x_n = 0$ 。

---

> $a>1$ ， 证明 $\lim_{n\to \infty} \sqrt[n]{a}=1$ 。

设 $y_n=\sqrt[n]{a}-1$。

$$
1+ny_n\le (y_n+1)^n=a\\
y_n\le \frac{a-1}{n}
$$

证明无穷小量一般比证明极限等于一个值简单，所以一般考虑等式左右相减。

> 证明 $\lim_{n\to \infty} \sqrt[n]{n}=1$ 。

设 $y_n=\sqrt[n]{a}-1$。

$$
\binom{n}{2} y_n^2\le (y_n+1)^n=n\\
y_n^2\le \frac{2}{n-1}
$$

$\dfrac{1}{n}$ 结构是最常见的无穷小量，往这方面凑就行。

---

对于不是证明一个特定值的极限，要善于使用定义进行证明。

> 若 $\lim_{n\to \infty} x_n=a$，证明 $\lim_{n\to \infty} \dfrac{\sum_{i=1}^n x_i}{n}=a$

令 $y_n={x_n}-a$，$y_n$ 是无穷小量。

$\forall \epsilon,\exists N , \text{s.t} \forall n> N,\mid y_n\mid <\epsilon/2$。

$s=\sum_{i=1}^N y_i$。

取 $N_1=N+\frac{2s}{\epsilon}$，那么 $\forall n>N_1,\dfrac{\sum_{i=1}^n y_i}{n}<\epsilon$。

在带回到 $x_n$ 就行。

---

来分析一些，极限的性质。

- 极限唯一

如果有两个反证一下就行。

- 收敛数列必然有界

因为 $>N$ 的部分在一个界里面，前面只有有限项肯定又有界。

- 保序性

，$\exists N,\forall n> N, x_n\le y_n$，$\lim_{n\to \infty} x_n\le \lim_{n\to \infty} y_n$。

如果在远处全部有偏序，那么极限肯定也有偏序。

如果极限反而不满足了，反证即可。

逆定理的话，要注意不能取等号才是对的。

- 夹逼性

有 $n>N$ 时，$x_n\le y_n\le z_n$，并且 $\lim x_n=\lim z_n$，那么 $\lim y_n=\lim x_n$。

直接用上面保序性感觉就对了。

- 极限可以四则运算

注意遇到无穷大量不要随便用，除法肯定不能分母是无穷小。

并且只能有限项加法，无限项不能考虑。

## 无穷大量

对于数列 $\{x_n\}$，$\forall \epsilon \exists N,\forall n>N,x_n>\epsilon$，则为无穷小量， $\lim_{n\to \infty} x_n = \infty$ 。

由于 $\dfrac{1}{x_n}=y_n$ 可以实现无穷大量和无穷小量的相互转化，所以没什么计算 trick。

> stolz 定理：如果有序列 $\{a_n\},\{b_n\}$，满足 $\{b_n\}$ 单调递增且为无穷大量，那么有：
>
>$$ 
>\lim_{n\to \infty} \frac{a_n-a_{n-1}}{b_n-b_{n-1}}=\lim_{n\to \infty} \frac{a_n}{b_n}
>$$

看上去非常神秘，但是可以发现这就是数列上的洛必达法则，分母的限制可以理解为洛必达中带入的值是 $\text{R}$ 上连续的，因此要单调递增且无穷大量。

本质就是，把原序列用差分来做。

> $\lim_{n\to \infty} \dfrac{1^k+2^k\cdots n^k}{n^{k+1}}$

$$
\lim_{n\to \infty} \dfrac{1^k+2^k\cdots n^k}{n^{k+1}}=\lim_{n\to \infty} \dfrac{n^k}{n^{k+1}-(n-1)^{k+1}}\\
=\lim_{n\to \infty} \dfrac{n^k}{(k+1)n-\binom{k}{2}n^2...}=\frac{1}{k+1}
$$
