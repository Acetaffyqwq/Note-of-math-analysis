---

layout: default
title: 线性映射
sort_order: 1
is_node: true

---

## 线性映射

对于线性空间 $V,V'$，对于其映射：$f:V\longmapsto V'$，如果满足映射后保留加法乘法，那么就称为**线性映射**。

容易发现和同构映射的区别是，同构映射必须要求是双射，而线性映射可以不是双射。

$A$ 到自己的线性映射是线性变换。

$$
f(\sum k_i \alpha _i)=\sum k_if(\alpha_i)
$$

也就是说，我们如果找出 $V$ 的一组基 $\alpha$ ，如果我们确定这组基的映射，那么就可以确定整个线性映射。

也就是 $\forall \alpha_i,f(\alpha_i)=g(\alpha_i) \to f=g$。

多项式环性质比较好，因此形如

$$
D(f(x))=f'(x)\\
A(f(x))=g(x)f(x)
$$

这种都是线性变换。

## 投影映射

对于 $V$ 的子空间 $U,W$，如果有 $V=U\bigoplus W$（直和），那么定义投影映射为，对于 $a\in V,a=a_1+a_2(a_1\in U,a_2\in W)$，则 $f_U(a)=a_1$ 。$f_U$ 称为平行于 $W$ 在 $U$ 上面的投影向量，注意到 $W$ 不同，投影结果是不同的。

由于是直和，拆解方法是唯一的，因此加法和乘法保留性是很好证明的。

容易得到投影映射乘法的一些性质：

$$
f_Uf_U=f_U\\
f_Wf_U=f_Uf_W=0
$$

## 刻画全体线性映射结构

定义 $\text{Hom}(V,V')$ 表示 $V$ 到 $V'$ 的全体线性映射，现在探究他们之间的性质。

有 $f,g\in \text{Hom}(V,V')$，定义 $(f+g)a:=fa+ga$，容易发现这样定义 $f+g$ 同样满足是线性映射。

同理 $(kf)(a):=k\times f(a)$。

这样就会发现 $\text{Hom}(V,V')$ 内部，加法数乘封闭了，因此 $\text{Hom}(V,V')$ 是一个线性空间。

有了加法数乘，可以去和映射乘法结合，如果 $f,g$ 都是线性映射，那么 $gf$ 也是线性映射，这个不难验证。

定义一个线性空间 $V$，如果满足其上定义了向量乘法，并且满足

- 分配律： $u,v,w\in V,(uv)w=uw+vw$ 。

- 与数乘的结合率（并不一定需要向量乘法结合律）：$u,v\in V,k\in F,kuv=ukv=uvk$。

那么 $V$ 是**代数系统**。

会发现 $\text{Hom}(V,V)$ 构成代数系统，我们在上面定义其多项式：

$$
\underline A: V\longmapsto V\\
\underline A^k = \underline A \underline A^{k-1}\\
f(\underline A)=\sum a_i \underline A^i
$$

然后可以用多项式相关理论说明这是个多项式环，但是暂时先搁置。

## 杂题 1

> $A$ 是线性变换，如果 $A^{m-1}a\ne 0,A^ma=0$ ，证明 $a,Aa,A^2a,...,A^{m-1}a$ 线性无关。

反证，如果线性相关，那么有

$$
\sum k_iA^{i}a=0\\
A^{m-1}\sum k_iA^{i}a=k_0A^{m-1}a=0\to k_0=0
$$

同理可以递推证明 $k_1,k_2,...$ 依次下去都是 $0$ ，矛盾，所以线性无关。

> 已知线性变换 $A,B$ 满足 $AB-BA=I$，求 $A^kB-BA^k$。

最考验代数功底的一集。

$$
ans_k=A^kB-BA^k=A^kB-A^{k-1}BA+A^{k-1}BA-BA^k\\
=A^{k-1}(AB-BA)+(A^{k-1}B-BA^{k-1})A\\
=A^{k-1}+ans_{k-1}A
$$

施加归纳，就可以证明答案是 $kA^{k-1}$

> 有幂等变换 $A,B$，证明
>
> - $A+B$ 是幂等变换与 $AB=BA=0$ 充要。

必要性显然。

充分：

$$
(A+B)^2=A+B\to AB+BA=0\\
A(AB+BA)=AB+ABA=0\\
(AB+BA)A=ABA+BA=0\\
ABA=0\\
AB=BA=0
$$

## 核

对于线性映射 $f:V\longmapsto V'$，刚刚研究了线性映射之间的关系以及运算，现在研究内部结构。

定义核 (Kernel) 为 $V'$ 的 $0$ 对应的原像，也就是：

$$
\ker(f)=\{x|x\in V,fx=0'\}\\
\text{rank}(f) = \dim \ker f
$$

- 核是 $V$ 的子空间。

首先有零元，然后加法乘法封闭。

- 核只有 $0$ 与 $f$ 是单射是充要条件。（重要）

线性空间性质优秀，很好证明。

稍微说一下商空间是个啥，有线性空间 $V$ 和它的子空间 $N$，$V/N$ 表示，把 $\{v+x\vert x\in N\}$ 的元素合并成一个得到的线性空间，这个线性空间里面的元素都是陪集 $\{v+x\vert x\in N\}$。

那我们考虑对于一个 $v$，把 $\{x\vert x\in V,fx=v\}$ 的元素放在一起，比如 $v=0$ 对应的就是 $\ker f$，那么 $V$ 中所有陪集 $v+\ker f$ 可以对应 $fv$，这样我们就完成了一个 $V/\ker f\longmapsto \text{Im} f$

先考虑在集合空间上面理解这个东西，如果我们的 $f$ 就是一个投影，那么平面 $U$，穿过原点直线 $W$，那么 $\ker P_U$ 就是直线上的点，那么会发现商空间 $v+W$ 就是把这个直线平移，这样我们就直观看到了直线到它经过平面上的点的一个对应。

容易证明，在集合空间上面这是一个线性映射，因为相当于平面上的向量加法。

那么我们再证明一般情况下的映射是什么，我们现在有 $g: V/\ker f\longmapsto \text{Im} f$，具体映射规则是 $g(v+\ker f)=fv$。

- 先证明，这是一个映射，如果有 $g(v_1+\ker f)\ne  g(v_2+\ker f),v_1+\ker f=v_2+\ker f$，那么 $v_1-v_2\in \ker f$，则 $fv_1=fv_2$，前面的矛盾，因此一个陪集只能对应一个，所以是映射。

- 然后说明是线性映射，$g(v_1+\ker f)+g(v_1+\ker f)=f(v_1+v_2)=g(v_1+v_2+\ker f)$，数乘同理。

- 是单射，如果 $f(v_1)=f(v_2)$ 说明 $v_1-v_2\in \ker f$，所以一定是单射。

- 是满射，$\text{Im} f$ 的定义，每个 $x\in V'$ 都能找到 $fv=x$，那么 $g(v+\ker f)=x$。

因此得到了，$g$ 是**同构映射**。$V/\ker f\cong \text{Im} f$

本质上是刻画了，$V$ 上元素关于 $fv$ 进行分类后得到了一个关于陪集的线性空间。

根据商空间以及同构的性质，有：

$$
\dim V=\dim \ker f+ \dim \text{Im} f
$$

有注意到单射和 $\dim \ker f=0$ 是充要的。

> $f:V\longmapsto V',\dim V=\dim V'=n$，且 $f$ 是线性映射，则 $f$ 是单射和 $f$ 是满射是充要的。

单射说明 $\dim \ker f=0\to \dim \text{Im} f=n=\dim V'$，因此 $\text{Im} f$ 与 $V'$ 同构，所以满射。

满射反过来就可以证明。

这个性质就很厉害了，映射只要满足是线性的就可以推出单射和双射是等价的。

注意到虽然有两个 $\dim$ 相加是 $V$，但是不能说明是直和，因为直和需要说明两者交为空，但是 $\ker f$ 和 $\text{Im} f$ 是有交集的。

> $f$ 是 $V$ 上线性幂等变换，证明 $V=\ker f+\text{Im} f$。

如果有 $v\ne 0,v\in \ker f,v\in \text{Im} f$，那么 $v=fx,fv=0,f^2x=0\ne v$。

所以两者是直和，因此加起来就是 $V$。由于是直和，$V$ 可分解为两个子空间，然后容易证明这个映射一定是一个投影。

- 推论：如果 $V=U\bigoplus W$，$P_U$ 表示平行于 $W$ 到 $U$ 上投影，那么 $\ker P_U=W,\text{Im} P_U=U$。

- $V$ 的任何一个子空间可以看成平行于补空间的投影的像。

- $V$ 的任何一个子空间可以看成到补空间上投影的核。

因此，投影是幂等变换，幂等变换也一定可以表示为投影。

直观的理解：如果把映射看成是类似排列上的结构，那么幂等变换就是深度是一，环是自环的基环树森林。而投影同样满足类似的结构。

回顾之前的知识，对于线性方程组 $Ax=0$，把 $A$ 看成线性映射，解空间就是 $\ker A$，而 $\dim \text{Im}$ 就是矩阵的秩（线性表出的维数等于秩的维数），那么很容易说明秩，解空间和 $n$ 的关系了，$\text{rank} f=\dim \text{Im} f$。

最后引入「余核」的概念，一个线性映射的余核是：

$$
\text{Coker} f=V'/\text{Im} f
$$

这个是用来考虑陪集的结构，暂时还不知道有啥用。

## 杂题 2

> 有 $A:V\longmapsto W,B:W\longmapsto U$，证明：
> 
> $$
> \dim(\ker BA)\le \dim (\ker A)+\dim(\ker B)
>$$

$$
\dim(\ker BA)=\dim V-\dim \text{Im} BA\\
= \dim V-\dim \text{Im} (B|AV)\\
= \dim \ker A+\dim (AV) - \dim \text{Im} (B|AV) \\
= \dim \ker A+\dim \ker(B|AV)\\
\le \dim (\ker A)+\dim(\ker B)
$$

可以不断 $\ker,\text{Im}$ 变换的性质很优秀。

> 有 $A:V\longmapsto W,B:W\longmapsto U,\dim W=m$，证明：
> 
> $$
> \text{rank}(BA)\ge \text{rank}(A)+\text{rank}(B)-m
>$$

$$
\text{rank}(BA)+m=\dim \text{Im} (B\vert AV)+m\\
=\text{rank}(A)+m-\dim \ker (B|AV)\\
\ge \text{rank}(A)+\dim W-\dim \ker B\\
=\text{rank}(A)+\text{rank}(B)
$$

会发现 $W\supseteq AV$ 是很常用的放缩。

>  有 $A:V\longmapsto W,B:W\longmapsto U,C:U\longmapsto M$，证明：
> 
> $$
> \text{rank}(CBA)\ge \text{rank}(BA)+\text{rank}(CB)-\text{rank}(B)
>$$

$$
\text{rank}(CBA)+\text{rank}(B)=\dim \text{Im} (C|BAV)+\text{rank}(B)\\
= \text{rank} (BA)+\text{rank}(B) - \dim \ker(C|BAV)\\
\ge \text{rank} (BA)+\text{rank}(B) - \dim \ker(C|BW)\\
= \text{rank}(BA)+\text{rank}(CB)
$$

会发现和上面一题的证明思路是非常类似的，并且如果是更多项乘起来也可以用这个东西去拆。

> $A$ 是 $V$ 上线性变换，$\dim V=n$，证明存在 $m$，满足
>
>$$
>A^{m+1}V=A^mV
>$$

$\dim A^{i+1}V\le \dim A^{i}V$，找到相等的，说明核是 $0$，因此可以说明单射然后双射。

## 矩阵表示线性映射

$f:V\longmapsto V',\dim V=n,\dim V'=m$，那么 $\text{Hom} (V,V')$ 可以用 $m\times n$ 的矩阵来表示。

向量表示线性空间中一个元素的坐标，因此先要确定 $V$ 内的一组基 $\alpha_1,\alpha_2...,\alpha_n$，$V'$ 内的一组基 $\beta_1,\beta_2,...,\beta_m$。

由于线性映射是由基的映射决定的，因此我们只需要知道 $(f\alpha_1,f\alpha_2,...,f\alpha_n)$，确定他们在 $V'$ 下的坐标。

于是有：

$$
(f\alpha_1,f\alpha_2,...,f\alpha_n)=(\beta_1,\beta_2,...,\beta_m)A
$$

$A$ 是一个 $m\times n$ 的矩阵，相当于把左边每一项确定其坐标。

可以记为：

$$
f\alpha=\beta A
$$

所以我们就确定了在 $(\alpha,\beta)$ 这组基下，线性映射 $f$ 对应矩阵 $A$。

由于 $\beta$ 是一组基，所以给定了基之后，一个线性映射对应的矩阵肯定是唯一的。

对于线性变换，一般认为 $\alpha=\beta$，此时矩阵也变成方阵。

从线性映射的角度来定义矩阵，仔细验证一下发现矩阵加法，数乘，乘法等运算是完全等价定义的。

确定基后把线性映射到对应矩阵的映射建出来，验证一下发现是线性映射，并且是双射，因此同构，也就是说每个矩阵都必然能找到一个对应的线性映射。

从这个方面想，也容易验证 $\dim M_{m\times n}(F)=m\times n$。

也就是得到简单结论 $\dim \text{Hom}(V,V')=\dim V\times \dim V'$。

---

统一符号，矩阵 $A$ 对应线性变换 $\mathcal A$。

由于矩阵和线性映射的对应会发现乘法是完全等价的，所以有：

- 矩阵 $A$ 可逆，线性映射 $f$ 可逆，并且对应。

- 矩阵 $A$ 幂等，线性映射也是幂等。

把乘法等价具体写出来：

$$
\mathcal A\alpha= \alpha A\\
$$

然后我们讨论，如果经过两个变换，如何转化为矩阵：

$$
\mathcal{AB} \alpha=\mathcal A (\alpha B)
$$

注意这里**不能**直接变成 $(\alpha B)A$，为什么呢？因为 $\mathcal A \alpha =\alpha A$ 这一步基于 $\mathcal A$ 作用于 $\alpha$ 这组基，但是 $\alpha B$ 不再是原来的基，所以对应的矩阵当然不一样。

此时要用超级关键的性质：由于线性变换是支持加法保留的，也就是我右边进行线性变换，加法会“穿过”线性变换，具体写出来就是：

$$
\mathcal A \alpha B=\mathcal A(\sum \alpha_i b_{i,1},\sum \alpha_i b_{i,2},...)\\
=(\sum \mathcal A \alpha_i b_{i,1},\sum \mathcal A \alpha_i b_{i,2}...)\\
=(\mathcal A \alpha)B\\
=\alpha (AB)
$$

可以简单记为 $\alpha$ （标量）可以直接闯过线性方程组变换而保持顺序不变，而不能记为先进行 $B$ 变换再进行 $A$ 变换。

然后可以有一些简单的例子，比如我知道 $\alpha$ 下一个点的坐标 $X$，然后我对其进行 $\mathcal A$ 变换，怎么求变换后的坐标呢。

$$
\mathcal A(\alpha X)=\alpha (AX)
$$

可以发现这个时候 $A$ 必须在 $X$ 前面，不然乘不了，和上面推理符合。

---

然后研究，取不同的基，有什么性质。

假设 $V$ 上两组基 $\alpha,\eta$，那么肯定有矩阵 $S$ 满足 $\alpha S=\eta$，这个 $S$ 叫做过渡矩阵。

对于线性变换 $\mathcal A$，设：

$$
\mathcal A \alpha =\alpha A\\
\mathcal A \eta=\eta B
$$

- 矩阵 $S$ 是可逆矩阵。

把定义拿出来，线性方程组只有 $0$ 解来证，不太难。

$$
\mathcal A \eta=\mathcal A (\alpha S)\\
=\alpha AS=\alpha SB\\
A=SBS^{-1}\\
B=S^{-1}AS
$$

也就是一个线性变换在不同的基下对应的矩阵相似。

然后也可以证明，如果两个矩阵相似，必然存在一个线性变换，使得这个线性变换可以取两个基使得对应矩阵分别是这两个矩阵。

构造方法就是一个基是单位，另一个取 $S$ 的行向量就行。

## 相似矩阵性质

我们定义 $A,B\in M_{n\times n}(F)$，如果 $\exists M$，$M$ 是可逆矩阵，并且有 $A=M^{-1}B M$，那么说 $A,B$ **相似**。

容易验证相似是一个等价关系，可以把 $M_{n}(F)$ 划分成若干等价类。

现在从矩阵视角研究相似矩阵有什么性质。

- $|MM^{-1}|=1\to |A|=|B|$。

- $\text{rank}A=\text{rank}(M^{-1}BM)=\text{rank}(B)$

> 定义，矩阵的迹 $\text{tr}(A)$ 表示方阵 $A$ 的对角线元素之和。

迹有一些很基本的性质的：

- $\text{tr}(A+B)=\text{tr}(A)+\text{tr}(B)$

- $\text{tr}(kA)=k\text{tr}(A)$

- $\text{tr}(AB)=\text{tr}(BA)$

有了交换律，那么很简单，如果 $A,B$ 相似，那么有：

- $\text{tr}(A)=\text{tr}(B)$

因此我们得到，一个相似等价类中不变量有：行列式，秩，迹。

因此可以定义线性变换的的行列式等于对应矩阵的行列式，因为都是相同的，同理线性变换的迹就是对应矩阵的迹。

至于秩，已经有自己的定义是 $\dim \text{Im} \mathcal A$，而可以证明和对应矩阵的秩相同。

## 杂题 3

> $\mathcal A$ 是 $n$ 维线性空间 $V$ 上面的一个线性变换，证明：
>
> - 存在一次数不超过 $n^2$ 的多项式 $f$ 满足 $f(\mathcal A)=0$。
>
> - $\mathcal A$ 可逆当且仅当存在常数项不是 $0$ 多项式 $f$ 满足 $f(\mathcal A)=0$。

因为 $A^k\in \text{Hom}(V,V),\dim \text{Hom} (V,V) =n^2$，所以 $A^0,A^1,...,A^{n^2}$ 必然线性相关，因此存在。

充分：由上一个可知存在一个多项式 $f(\mathcal A)=0$，如果常数项是 $0$ 左右同时乘 $A^{-1}$ 即可。

必要：

$$
\sum_{i=0}^m a_iA^i=0,a_0\ne 0\\
\sum_{i=1}^m a_iA^i=-a_0I\\
A(\sum_{i=0}^{m-1}a_{i+1}A^i)=-a_0I\\
A^{-1}=-\frac{1}{a_0}(\sum_{i=0}^{m-1}a_{i+1}A^i)
$$
