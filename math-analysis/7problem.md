---
layout: default
title: 定积分杂题
sort_order: 1
is_note: true
---

> 函数 $f(x)$ 在 $[a,b]$ 上二阶可导，$f(\dfrac{a+b}{2})=0$，令 $M=\sum_{x\in [a,b]}f''(x)$，证明： 
>$$
>\int_a^b f(x) dx\le \frac{M(b-a)^3}{24}
>$$

这种题前面做过类似的，肯定是要用到泰勒展开，我们在特殊点 $\dfrac{a+b}{2}$ 处展开，然后用左右同时极限，这个做法还挺有用的。

$$
f(x)=f'(\frac{a+b}{2})(x-\frac{a+b}{2})+\frac{1}{2}f''(\xi)(x-\frac{a+b}{2})^2\\
\int_a^b f(x)dx=\frac{1}{6}\int_a^b f''(\xi)((\frac{a+b}{2})^3-(-\frac{a+b}{2})^3)\\
\le \frac{M(b-a)^3}{24}
$$

> $f$ 在 $[0,1]$ 上可积，并且单调递减，证明对于 $a\in (0,1)$ ，有：
>
>$$
> a\int_0^1 f(x)dx\le \int_0^a f(x)dx
>$$

这个是积分中值定理的运用，如果是离散情况下平均感性理解是比较显然的，这个连续情况就必须要用中值定理严谨写。

$$
\int_0^a f(x)=af(\xi_1),\xi_1 \in [0,a]\\
\int_a^1 f(x)=(1-a)f(\xi_2),\xi_2\in [a,1]\\
f(\xi_1)\ge f(\xi_2)\\
af(\xi_1)+(1-a)f(\xi_2)\le f(\xi_1)\\
a\int_0^1 f(x)dx\le \int_0^a f(x)dx
$$

