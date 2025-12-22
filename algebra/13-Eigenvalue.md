---

layout: default
title: 特征值与特征向量
sort_order: 1
is_node: true

---

先明确特征值为的目的：我们想要找到一组基，使得 $\mathcal A$ 对应的矩阵形式最简单，那么最简单的形式很显然就是尽量呈对角化。

## 定义

对于线性变换 $\mathcal A$，如果有非零向量 $\xi \in V,\lambda \in F$，满足：

$$
\mathcal A \xi=\lambda \xi
$$

那么 $\xi$ 是 $\mathcal A$ 的特征向量，$\lambda$ 是特征值。

这个啥意思呢，本质上就是说 $\mathcal A$ 作用在 $x$ 上只会改变它的长度，而不改变它的方向，也就是别的方向的分量不会影响我，一个类似独立的感觉。

举个例子，比如说对于平行于 $W$ 的投影变换 $P_U$，有：

$$
P_U(x)=x(x\in U)\\
P_U(x)=0(x\in W)
$$

因此我们可以得到一系列特征值和特征向量。

由于 $\xi$ 非零，很容易发现一个特征向量肯定对应唯一特征值，因此可以考虑按照特征值进行一个分类。

$$
V_{\lambda}:=\{x\in V \vert \mathcal A x=\lambda x \}
$$

注意这里我们把 $0$ 也放进去，方便后面处理。

很容易验证加法，数乘依然保留，因此可以说明 $V_{\lambda}$ 是 $V$ 的子空间。

由于两个子空间交集是 $\{0\}$，因此是直和。

然后我们想要证明，多个特征子空间加起来也是直和，这怎么证呢。

归纳 + 反证，我们已经证明了 $m-1$ 个特征值对应的特征子空间是直和。

假设不成立，说明存在 $v_i\in V_{\lambda_i}$ 满足：

$$
v_1+v_2+...+v_m=0\\
\mathcal A(v_1+v_2+...+v_m)=0\\
\sum \lambda_i v_i=0\\
\lambda_m\sum v_i=0\\
$$

最后两个式子相减我们就得到前 $m-1$ 个子空间不是直和的结论，矛盾，因此多个特征子空间加起来是直和。

---

可以确定一组基，然后把 $\mathcal A$ 变成矩阵方便后面的研究。

确定一组基 $\alpha$，如果 $\xi$ 在其上的坐标是 $\gamma$，那么有：

$$
\mathcal A\xi =\mathcal A(\alpha \gamma)\\
=\alpha (A\gamma)=\alpha (\lambda \gamma)
$$

因此我们得到矩阵的特征值定义：

$$
A\gamma=\lambda \gamma
$$

那么 $\lambda$ 是特征值，$\gamma$ 是特征向量。

从上面可以按出 $\mathcal A,A$ 的特征值对应相同，特征向量由基确定。

## 求法

由于矩阵比较具体，我们针对于矩阵去求特征值与特征向量。

$$
A\alpha=\lambda \alpha\\
(\lambda I-A)\alpha=0
$$

此时变成齐次线性方程组的非 $0$ 解，那么我选的特征值 $\lambda$ 就是想让这个方程有解因此 $|\lambda I-A|=0$，这是一个关于 $\lambda$ 的一元多项式，叫特征多项式，因此要求的特征值就是这个多项式的根。

虽然它是多项式，但是我们还是当做一个定义在一元多项式环 $F[\lambda]$ 上的矩阵，矩阵加，数乘，乘法依然保留。

注意数乘是相当于乘上一个多项式而并不是一定是一个数。

求特征值和特征向量：

- 解 $|(\lambda I-A)|=0$

- 解 $(\lambda I-A)X=0$

## 性质

-  相似矩阵特征多项式相同。

由于特征多项式定义在行列式上面，所以不难证明：

$$
B=S^{-1}AS\\
|B-\lambda I|=|S^{-1}AS-\lambda I|\\
=|S||S^{-1}AS-\lambda I||S^{-1}|
=|A-\lambda I|
$$

所以可以把矩阵的特征多项式称为线性变换的特征多项式。

- $|\lambda I -A|=0$，$\lambda^n$ 前面的系数是 $1$，$\lambda^{n-1}$ 的系数是 $-\text{tr}(A)$，常数项是 $|-A|$。

- 同理 $\lambda^k$ 的系数就是相当于任意选 $k$ 行列划掉得到子式的和，称划去行列相同的子式是**主子式**。

## 对角化

既然相似矩阵形成若干等价类，我们想要在每个等价类中寻找一个最简单的矩阵作为线性变换对应的矩阵。

但是并不是所有都可行，所以如果线性变换 $\mathcal A$ 可以找到一组基变成对角矩阵，那么称可对角化。

写出定义式子：

$$
\mathcal A(\alpha_1,\alpha_2,...,\alpha_n)=(\lambda_1\alpha_1,\lambda_2\alpha_2,...,\lambda_3\alpha_3)\\
\mathcal A\alpha_i=\lambda_i\alpha_i
$$

会发现 $\alpha_i$ 就是特征向量。

我们也就得到可对角化一个简单的等价条件：可以选出 $V$ 中一组基使得基中全都是 $\mathcal A$ 的特征向量。

由于特征子空间是直和，所以等价于每个特征值子空间选一组基，使得基的和是 $n$ 即可。

因此等价条件变成：

$$
V=V_{\lambda_1}\oplus V_{\lambda_2}...\oplus V_{\lambda_m}
$$

如果可对角化，我们选出每个 $V_{\lambda_i}$ 的一组基：$\alpha_{i,1},\alpha_{i,2},...,\alpha_{i,s_i}$，把所有的基放在一起，变成一个基 $\alpha$ （把二维压成一维）。

那么直接考虑在这组基下面 $\mathcal A$ 对应的矩阵是对角线上面 $s_1$ 个 $\lambda_1$，$s_2$ 个 $\lambda_2$，以此类推。

那么对于这个矩阵我们求特征多项式，就可以得到 $\mathcal A$ 的特征多项式

$$
\prod (x-\lambda_i)^{s_i}
$$

这里 $s_i$ 就和特征子空间维数相同，反过来，如果有这样一个特征多项式并且满足 $s_i$ 和维数相同我们就可以推出特征子空间是直和，因此这又是一个等价条件。

这里就可以发现不能对角化的条件了，因为在有的数域 $F$ 上存在不可约多项式，因此 $\lambda_i$ 不在 $F$ 上就不能用对角化。

注意，这里只是说，对于可对角化的矩阵，满足 $s_i=\dim V_{\lambda_i}$，但是一般情况下并不一定。

- $s_i$ 表示 $\lambda_i$ 在特征多项式重根个数，叫做代数重数，$\dim V_{\lambda_i}$ 叫做几何重数。

那么有几何重数 $\le$ 代数重数。

为啥呢也好理解，因为几何重数是真正表示了一组特征子空间基的大小，所以我可以选出这组基，然后扩充到 $n$，就可以说明特征多项式中有这一项。

但是代数重数就比较单薄，由于不一定可对角化所以不直接转化成矩阵，因此只满足 $\le$，而不是等于。

把线性变换的对角化结论很容易迁移到矩阵的对角化上面，相当于和对角矩阵相似，特征向量构成一组基。

## 不变子空间

并不是所有的线性变换都能对应到对角矩阵，所以我们考虑能不能相似到一个简单的矩阵。

注意到特征向量 $\alpha\in V_{\lambda_i}$ 满足：

$$
\mathcal A\alpha =\lambda_i\alpha\in V_{\lambda_i}
$$

类似的，如果线性子空间 $W$ 满足 

$$
\forall \alpha\in W,\mathcal AW\in W
$$

那么 $W$ 就是不变子空间。很容易发现两个平凡子空间 $V,0$。

还有一些很简单的，$\ker \mathcal A$，以及 $V_{\lambda}$ 肯定都是不变子空间。

而由于 $\mathcal A$ 是线性变换，也就是 $\text{Im}\mathcal A \subseteq V$，因此 $\text{Im} \mathcal A$ 也是不变子空间。

现在得到几个重要的不变子空间：$0,V,\ker,\text{Im},V_{\lambda}$。

接下来来寻找别的子空间。

- 不变子空间的交、和还是不变子空间。

通过定义，显然。

- 若一个子空间的基都满足 $\mathcal A \alpha\in W$，那么是不变子空间。

基确定了整个线性变换，容易证。

还有一个之后会用到的东西，如果 $\mathcal {A,B}$ 是课交换的线性映射，那么有：

- $\ker\mathcal B,\text{Im} \mathcal B$ 还有 $\mathcal B$ 的所有特征子空间都是 $\mathcal A$  的不变子空间。

由于有交换，所以不难证。

$$
\forall x\in \ker \mathcal B,\mathcal Bx=0\\
\mathcal {BA}x=\mathcal{AB}x=\mathcal A0=0\\
\mathcal Ax\in \ker \mathcal B
$$

$$
\forall x\in \text{Im} \mathcal B\\
\exists y\in V,\mathcal By=x\\
\mathcal {BA}y=\mathcal{AB}y=\mathcal Ax\\
\mathcal Ax\in \text{Im} \mathcal B
$$

$$
\forall x,\mathcal Bx=\lambda x\\
\mathcal{BA}x=\mathcal {AB}x=\lambda\mathcal Ax\\
$$

会发现可以交换的变换，他们的几个基本的子空间可以给对方。

## 零化多项式

回到主题，我们想要找到一个线性映射对应的尽量简单的矩阵。

既然可能不是对角化矩阵，我们想办法变成“分块对角矩阵”，也就是对角线上有一些方阵，别的地方都是 $0$。

相当于是我们找一个基，可以划分成若干个区间，每个区间的基的线性变换结果可以被这个区间里的基表出，那么会发现每个区间的基是一个不变子空间。

那么我们的目标就很简单，我们要找出一组不变子空间，他们的直和是 $V$。

但是我们现在已知的不变子空间肯定时候不够的，特征子空间如果可以直和说明可以变成对角矩阵，但是你都不行，说明特征子空间还不够。

我们就要通过可交换来获得更多的不变子空间。

---

如何快速找到一大堆和 $\mathcal A$ 可交换的线性变换，它们的核就是不变子空间。

不难发现，对于任意多项式 $f$，$f(\mathcal A)$ 和 $A$ 肯定是可以交换的。

先要完善一下多项式理论，因为 $\mathcal A$ 和自身的幂次乘法、加法可交换，所以可以构成多项式环 $F[\mathcal A]$。

也就是 $\forall f,\ker f(\mathcal A)$ 就是 $\mathcal A$ 的不变子空间。

然后研究 $\ker f(\mathcal A)$ 的性质。

多项式可以拆分为不可拆多项式，我们研究这里有什么性质。

如果 $f(x)=f_1(x)f_2(x),(f_1(x),f_2(x))=1$。

根据多项式理论，存在 $u(x)f_1(x)+v(x)f_2(x)=1$。（类似裴蜀定理）。

- $\ker f(\mathcal A)=\ker f_1(\mathcal A)\bigoplus \ker f_2(\mathcal A)$。

$$
\forall x\in \ker f_1(\mathcal A)+f_2(\mathcal A)\\
x=\alpha + \beta ,f_1(\mathcal A)\alpha=f_2(\mathcal A)\beta=0\\
f(\mathcal A)x=f(\mathcal A)(\alpha +\beta)=0\\
\ker f(\mathcal A)\supseteq \ker f_1(\mathcal A)+\ker f_2(\mathcal A)
$$

反过来，类似于分解成两部分，一个对应 $\ker f_1$，另一个是 $\ker f_2$。

$$
f(\mathcal A)x=0\\
x=Ix=(u(\mathcal A)f_1(\mathcal A)+v(\mathcal A)f_2(\mathcal A))x\\
f_2(\mathcal A)u(\mathcal A)f_1(\mathcal A)x=u(\mathcal A)f(\mathcal A)x=0\\
u(\mathcal A)f_1(\mathcal A)x\in \ker f_2(\mathcal A)\\
v(\mathcal A)f_2(\mathcal A)x\in \ker f_1(\mathcal A)\\
x\in \ker f_1(\mathcal A)+\ker f_2(\mathcal A)
$$

中间那一步是因为 $f\in F[\mathcal A]$ 都可交换。

所以 $f(\mathcal A)\subseteq f_1(\mathcal A)+f_2(\mathcal A)$。

所以 $f(\mathcal A)=f_1(\mathcal A)+f_2(\mathcal A)$。

$$
\forall x\in \ker f_1(\mathcal A) \cup \ker f_2(\mathcal A)\\
x=(u(\mathcal A)f_1(\mathcal A)+v(\mathcal A)f_2(\mathcal A))x=0\\
\ker f_1(\mathcal A)\cup \ker f_2(\mathcal A)=\{0\}
$$

证明了两者是直和。

同理可以归纳证明，如果拆分成若干互素的东西不可拆多项式，那么就是每一个 $\ker$ 直和起来。

回顾我们的目标：我们需要把 $V$ 分解成若干个 $\ker f$，因此有：

$$
V=\ker f=\bigoplus \ker f_i
$$

因此只需要找到一个 $f(\mathcal A)$ 使得 $\ker f(\mathcal A)=V$。

回顾 $\ker$ 的定义，等价于 $f(\mathcal A)=0$。

因此定义 $f(\mathcal A)=0$ 的多项式是**零化多项式**。

---

那么我们任务变成，去寻找 $\mathcal A$ 的零化多项式。

- 对于 $\dim V=n,\mathcal A: V\longmapsto V$，必然存在次数不超过 $n^2$ 零化多项式。

由于 $\dim \text{Hom}(V,V)=n^2$，所以 $I,\mathcal A,...\mathcal A^{n^2}$ 必然线性相关，因此存在零化多项式。

但是我们还是需要找一个，具体的能表示出来的零化多项式。

- $f(\lambda)=|\lambda I-A|$ 是 $A$ 的特征多项式，$f(A)=0$。

求行列式，会想到可以相似矩阵做。

$$
(\lambda I-A)(\lambda I-A)^*=|\lambda I-A|I
$$

左右都是 $M_{n\times n}(F[\lambda])$，因此相当于是每个 $\lambda^i$ 的系数是一个矩阵，要满足左右的 $\lambda^i$ 的系数矩阵相同。

假设 $|\lambda I-A|=\sum_{i=0}^n a_i\lambda^i$，那么右边就是 $\sum_{i=0}^n \lambda^ia_iI$。

左边东西看起来比较复杂，$(\lambda I-A)^*$，不超过 $n-1$ 次，我们写成 $\sum_{i=0}^{n-1} \lambda^iB_i$。

$$
(\lambda I-A)(\lambda I-A)^*=\sum_{i=1}^{n}\lambda^{i}B_{i-1}-\sum_{i=0}^{n-1}\lambda^iAB_i\\
-AB_0=a_0I\\
B_0-AB_1=a_1I\\
B_1-AB_2=a_2I\\
\cdots\\
B_{n-1}=a_nI
$$

此时关键一步：第 $i$ 个式子左右同时乘以 $A^i$，得到：

$$
0=\sum_{i=0}^n a_i A^i
$$

得证，特征多项式是零化多项式。

---

- 定义，零化多项式中次数最小并且首项是 $1$ 的多项式是「最小多项式」。

探究其性质。

- 线性变换的最小多项式等于它对应的矩阵的最小多项式。

考虑由于我们是选择一组基，在一组基下是 $0$ ，说明对应的矩阵肯定是 $0$ 矩阵。

- 相似矩阵最小多项式相同。

- 如果 $f(x)$ 是零化多项式，那么 $g(x)=u(x)f(x)$ 也肯定是零化多形式。

- 如果 $f(x)$ 是零化多项式，那么 $f(x)$ 一定是最小多项式 $M(x)$ 乘上 $g(x)$ 形式。

后一个证明考虑多项式带余除法，除出来的余数肯定不是零化多项式所以矛盾。

而我们已知了一个零化多项式 $|\lambda I-A|$，设 $|x I-A|=p(x)=\sum a_ix^i,M(x)=\sum b_i x^i$。

考虑对于任意 $p(x)$ 的根 $\lambda$，有特征向量 $Ax=\lambda x$。

$$
M(A)x=\sum b_i A^ix=\sum b_i\lambda^i x=M(\lambda)x=0\\ 
$$

直接得到 $\lambda$ 是最小多项式的根，也就是特征多项式和最小多项式有相同的根（只是重数可能不同）。

然后分析，我们划分成的子空间的最小多项式性质。

假设 $V=\bigoplus _{i=1}^m V_i$，$V$ 的最小多项式是 $m(V)$。

首先，如果 $F(x)$ 是所有 $m(V_i)$ 的公倍式，那么在每个子空间内都是零化多项式，所以 $F(x)$ 就是 $V$ 的零化多项式。

反过来，我们也可以证明，如果 $F(x)$ 是 $V$ 的零化多项式，那么它一定是 $m(V_i)$ 的公倍式，因为如果不是，对于一个 $m(V_i)$，直接多项式取模就可以证明余数肯定爆了。

也就是零化多项式集合和公倍式集合相同。

因此「最小多项式」就是「最小公倍式」。