---

layout: default
title: 二次型（题）
sort_order: 1
is_node: true

---

> 证明：一个 $n$ 元二次型可以表示成两个一次多项式乘积 $\Longleftrightarrow$ 这个二次型秩是一或者秩是二并且符号差是 $0$ 。

$\Longrightarrow$：

如果有二次型等于 $\sum_{i=1}^n a_ix_i \times \sum _{i=1}^n b_ix_i$。

- 如果 $(a_1,a_2,...,a_n)\ne k(b_1,b_2,...,b_n)$。

那么令 $y_1=\sum a_ix_i,y_2=\sum b_ix_i$，然后把 $y$ 填充成一组基，那么 $Y=CX$。

$f(X)=y_1y_2$，而 $y_1y_2$ 配方一下就得到了秩是 $2$ ，符号差是 $0$ 的矩阵。

- 如果 $(a_1,a_2,...,a_n)=k(b_1,b_2,...,b_n)$。

那么 $y_1=\sum a_ix_i$，然后填充成一组基。

$f(X)=ky_1^2$ ，秩是 $1$ 。

$\Longleftarrow$：

基本就是上面东西反过来，把 $y$ 拆成 $x$ 就好了。

从中可以看出把二次型转化为等价的标准型性质很好。

> 有二次型 $f(A)=X^TAX$，有两个 $R^n$ 上列向量 $\alpha_1,\alpha_2$，满足 $f(\alpha_1)<0<f(\alpha_2)$ ，证明存在非 $0$ 向量 $\alpha_3$ ，满足 $f(\alpha_3)=0$

$A=P^TDP$，其中 $D$ 是规范型，那么我们把列向量变成 $P\alpha_1,P\alpha_2$ 就得到了 $D$ 上满足 $>0,<0$ 的两个列向量。

也就是说，$D$ 的正惯性系数和负惯性系数都不是 $0$ 。

那么当然存在 $\beta_3$ 满足 $\beta_3^TD\beta_3=0$ ，令 $\alpha_3=P^{-1}\beta_3$ 即可。

## 正定二次型

定义如果对于任意 $\alpha\in R^n$，有 $\alpha^TA\alpha>0$ ，那么称 $X^TAX$ 是正定二次型。

其充要条件显然是规范型惯性正指数等于 $n$。