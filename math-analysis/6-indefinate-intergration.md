---
layout: default
title: 不定积分
sort_order: 1
is_note: true
---

不定积分可以直接看成就是导数的逆运算。

$$
df(x)=g(x)dx\\
\int g(x)dx=f(x)\\
d\int f(x) dx=f(x)dx
$$

也就是 $d,\int$ 可以看成互逆的变换。

- 不定积分可以线性相加。

这个挺显然的。

## 换元

想要对于积分换底。

我们找到一个和 $x$ 有关的变量 $u$，那么 $\dfrac{du}{dx}=u'$。

$$
\int f(x) dx=\int \frac{f(x)}{u'}du
$$

注意最后求出的结果如果是和 $u$ 有关要转化回 $x$。

- $u=g(x)$。

$$
\int f(x) dx=\int \frac{f(x)}{g'(x)}du
$$

这个一般是除掉一个式子用的。

- $x=g(u)$。

$$
\int f(x) dx=\int f(x)g'(u) du
$$

这个一般就不用开了乘上去的 $g'(u)$，要尽量满足 $f(x)$ 可以被 $u$ 凑出。

- 三角换元。

遇到比如 $\sqrt{1-x^2}$ 这样的，有平方有根号，令 $x=\cos^2\theta$ 就可以把复杂的东西直接变成一个 $\sin x$。

## 分部

导数求导里，有：

$$
(uv)'=u'v+v'u
$$

左右同时积分，得到：

$$
uv=\int uv'dx+\int vu'dx\\
=\int udv+\int vdu
$$

所以得到：

$$
\int udv=uv-\int vdu
$$

## 基本积分表

$$
\int \frac{1}{x}dx=\ln |x|+C\\
\int \ln xdx=x(x\ln x-1)+C\\
\int a^xdx=\frac{a^x}{\ln a}+C\\
\int \tan xdx=-\ln |\cos x|+C\\
\int \cot xdx=\ln |\sin x|+C\\
\int \sec xdx=\ln |\sec x+\tan x|+C\\
\int \csc xdx=\ln |\csc x-\cot x|+C\\
\int \frac{dx}{\sqrt{a^2-x^2}}=\arcsin \frac{x}{a}+C\\
\int \frac{dx}{\sqrt{x^2+a^2}}=\ln |x+\sqrt{x^2+a^2}|+\\
\int \frac{dx}{x^2-a^2}=\frac{1}{2a}\ln |\frac{x-a}{x+a}|+C\\
\int \frac{dx}{x^2+a^2}=\frac{1}{a}\arctan \frac{x}{a}+C\\
$$