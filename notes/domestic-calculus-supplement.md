# 国内高数补充：重要极限、等价无穷小、洛必达与泰勒

[返回目录](../README.md)

与目前的极限、一元微分进度衔接的一份补充。章节选择参考[同济大学：函数与极限](https://gaoshutongbu.tongji.edu.cn/kcyx/dyz_hsyjx.htm)及[微分中值定理与导数的应用](https://gaoshutongbu.tongji.edu.cn/kcyx/dsz_wfzzdlydsdyy.htm)。超出上传 Week 1–4 的内容明确标为补充，参考链接直接定位到相应资料。

## 1. 无穷小、同阶、高阶与等价：比的是一个变化过程

> **来源定位：** [广州大学公开课件《无穷小的比较》· 第 2 页](https://maths.gzhu.edu.cn/gaoshu2/ppt1/1-9.pdf#page=2)。**上传课件对应页：无，本节是国内高数补充。**

无穷小是**在指定过程下趋于 0 的量**，不是某个固定的“特别小的数”。$x$ 在 $x\to0$ 时是无穷小，在 $x\to1$ 时不是。

对同一过程中的两个无穷小 $\alpha,\beta$，假设相关比值在去心邻域有定义：

| 比值的极限 | 关系 |
| --- | --- |
| $\alpha/\beta\to0$ | $\alpha$ 比 $\beta$ 高阶，记 $\alpha=o(\beta)$ |
| $\alpha/\beta\to c\ne0$，$c$ 有限 | 同阶 |
| $\alpha/\beta\to1$ | 等价，记 $\alpha\sim\beta$ |

例如 $x^2=o(x)$、$2x$ 与 $x$ 同阶但不等价、$\sin x\sim x$，这里都是 $x\to0$。$\sim$ 表示比值趋于 1，不是两个表达式恒等。

## 2. 两个重要极限，以及 $1^\infty$ 型的处理

> **来源定位：** 正弦极限见 [MAT1001 Week 1 · 第 48 页](../references/week1/page-048.jpg)；指数型极限见 [广州大学《极限存在准则》· 第 16 页](https://maths.gzhu.edu.cn/gaoshu2/ppt1/1-8.pdf#page=16)。**指数型公式超出上传课件，是补充。**

$$
\lim_{u\to0}\frac{\sin u}{u}=1,
\qquad
\lim_{n\to\infty}\left(1+\frac1n\right)^n=e.
$$

常用的另一种写法是：

$$
\lim_{u\to0}(1+u)^{1/u}=e,
$$

使用时要求附近 $1+u>0$，并排除 $u=0$。不能把“底数趋于 1”直接理解成“整个幂趋于 1”。

更一般地，若 $u(x)\to0$，且 $u(x)v(x)\to A$（有限），在正底数条件下：

$$
(1+u(x))^{v(x)}\to e^A.
$$

这个推广可通过取对数验证：$v\ln(1+u)=(uv)\,[\ln(1+u)/u]\to A$。要看底数的偏移量与指数的乘积，不是机械套 $e$。

## 3. 常用等价无穷小：先看整个内层是否趋于 0

> **来源定位：** [广州大学《无穷小的比较》· 第 8 页（公式表）](https://maths.gzhu.edu.cn/gaoshu2/ppt1/1-9.pdf#page=8)。**等价关系的统一记法是补充；三角公式的基础见 [Week 1 第 48 页](../references/week1/page-048.jpg)、[第 51 页](../references/week1/page-051.jpg)。**

下列均在 $u\to0$ 时使用，三角量用弧度：

| 量 | 等价无穷小 |
| --- | --- |
| $\sin u$、$\tan u$ | $u$ |
| $1-\cos u$ | $u^2/2$ |
| $\ln(1+u)$ | $u$ |
| $e^u-1$ | $u$ |
| $a^u-1$ | $u\ln a$，$a>0$ 且 $a\ne1$ |
| $(1+u)^r-1$ | $ru$，$r\ne0$，附近 $1+u>0$ |

例如 $\sin(3x)\sim3x$、$\ln(1+x^2)\sim x^2$。判断小量时要看整个角度或整个增量，不只看变量名字。

## 4. 等价替换为什么在相减时容易出错？

> **来源定位：** [广州大学《无穷小的比较》· 第 11–12 页（比值替换）](https://maths.gzhu.edu.cn/gaoshu2/ppt1/1-9.pdf#page=11)；[第 16 页（相减误用）](https://maths.gzhu.edu.cn/gaoshu2/ppt1/1-9.pdf#page=16)。**上传课件未直接讲等价替换定理。**

若 $\alpha\sim\widetilde\alpha$、$\beta\sim\widetilde\beta$，且相关分母在附近非零，则可用简化后的比值计算原比值的极限。例如：

$$
\lim_{x\to0}\frac{\sin(3x)}{\ln(1+2x)}
=\lim_{x\to0}\frac{3x}{2x}=\frac32.
$$

但是相加、相减不能仅凭每一项分别等价就逐项替换。主项可能抵消，让原本省略的高阶项成为答案的关键。

例如 $\sin x\sim x$，但把 $\sin x-x$ 直接替成 $x-x=0$ 会丢掉其三次项。第 7 节的展开给出 $\sin x-x=-x^3/6+o(x^3)$。

稳妥顺序：**先化简整个差值，再考虑替换；若主项抵消，保留到更高阶。**

## 5. 指数、对数的求导，作为补充公式

> **来源定位：** [OpenStax §3.9：指数与对数求导](https://openstax.org/books/calculus-volume-1/pages/3-9-derivatives-of-exponential-and-logarithmic-functions)。**上传 Week 1–4 没有直接对应页码；复合求导的基础见 [Week 3 第 25 页](../references/week3/page-025.jpg)。**

| 函数 | 导数 | 条件 |
| --- | --- | --- |
| $e^x$ | $e^x$ | $x\in\mathbb R$ |
| $a^x$ | $a^x\ln a$ | $a>0$；一般取 $a\ne1$ |
| $\ln x$ | $1/x$ | $x>0$ |
| $\log_a x$ | $1/(x\ln a)$ | $x>0$，$a>0$ 且 $a\ne1$ |

内层是可导函数 $u(x)$ 时，仍要用链式法则：$(e^u)'=e^u u'$，$(\ln u)'=u'/u$（$u>0$）。

固定指数的 $x^r$ 与固定底数的 $a^x$ 用不同公式；底数和指数都变时，例如 $x^x$（$x>0$），可写成 $e^{x\ln x}$ 再求导。

## 6. 洛必达法则：只在条件满足时联系两个极限

> **来源定位：** [同济大学第三章：洛必达法则](https://gaoshutongbu.tongji.edu.cn/kcyx/dsz_wfzzdlydsdyy.htm)；[OpenStax §4.8：条件与误用](https://openstax.org/books/calculus-volume-1/pages/4-8-lhopitals-rule)。**上传课件无对应页，本节是提前补充。**

对一个商的极限，先确认是 $0/0$ 或 $\infty/\infty$ 型。在相关去心邻域中，要求 $f,g$ 可导、原比值有定义且 $g'(x)\ne0$；若导数比的极限存在（有限或为正负无穷），则可推出：

$$
\lim\frac{f(x)}{g(x)}=\lim\frac{f'(x)}{g'(x)}.
$$

可用于相应的单侧极限或无穷远极限。每次再次使用，都需重新检查条件。它是**极限之间的结论**，不是 $f/g=f'/g'$ 的函数恒等式，也不是对整个商使用商法则求导。

没有得到 $0/0$ 或 $\infty/\infty$，就不能直接这样操作。$0\cdot\infty$、$\infty-\infty$ 通常先变成商；幂型未定式通常先取对数并检查正底数。

导数比的极限不存在，只表示这条法则不能得出结论，不能反推原极限不存在。例如 $x\to+\infty$ 时 $(x+\sin x)/x\to1$，但导数比 $1+\cos x$ 振荡。

## 7. 低阶泰勒：线性近似后再保留更多项

> **来源定位：** [同济大学第三章：泰勒公式](https://gaoshutongbu.tongji.edu.cn/kcyx/dsz_wfzzdlydsdyy.htm)；[OpenStax §6.3：泰勒多项式与余项](https://openstax.org/books/calculus-volume-2/pages/6-3-taylor-and-maclaurin-series)。**上传课件只讲一阶线性化，见 [Week 4 第 13 页](../references/week4/page-013.webp)；高阶部分是补充。**

线性近似保留常数项和一次项。若函数在附近有足够的连续高阶导数，还可以保留二次及更高次项：

$$
f(a+h)=f(a)+f'(a)h+\frac{f''(a)}{2!}h^2+\cdots
+\frac{f^{(n)}(a)}{n!}h^n+R_n(h).
$$

这里 $n!=1\cdot2\cdots n$。在 0 处展开叫麦克劳林展开；$h$ 是相对于中心的增量。

当 $x\to0$，常用的低阶形式为：

$$
e^x=1+x+\frac{x^2}{2}+o(x^2),\qquad
\ln(1+x)=x-\frac{x^2}{2}+o(x^2),
$$

$$
\sin x=x-\frac{x^3}{6}+o(x^3),\qquad
\cos x=1-\frac{x^2}{2}+o(x^2).
$$

余项不能无条件丢掉。$o(x^k)$ 表示余项除以 $x^k$ 后趋于 0；相减题要展开到主项抵消后仍留下的那一阶。

若 $f$ 在包含中心和目标点的区间上有连续的 $n+1$ 阶导数，则拉格朗日余项为 $R_n=f^{(n+1)}(\xi)h^{n+1}/(n+1)!$，其中 $\xi$ 在中心与目标之间。若该阶导数绝对值不超过 $M$，则 $|R_n|\le M|h|^{n+1}/(n+1)!$。这给出了比“目标很近”更具体的误差控制。

## 8. 数列的单调有界准则：先保证极限存在，再求可能的值

> **来源定位：** [广州大学《极限存在准则》· 第 10 页](https://maths.gzhu.edu.cn/gaoshu2/ppt1/1-8.pdf#page=10)；[同济大学：极限存在的常见误解](https://gaoshutongbu.tongji.edu.cn/info/1057/1112.htm)。**上传课件没有直接对应页码。**

单调递增且有上界的数列必有有限极限；单调递减且有下界也一样。

只有有界不够，$(-1)^n$ 有界但振荡；只有单调也不够，$n$ 单调递增却没有有限极限。

遇到递推数列，直接设 $a_n\to L$ 再解关于 $L$ 的方程，通常只是在找可能的极限值。还需先证明收敛，并检查哪一个解与初值、界和单调性一致。

## 学习顺序

先掌握第 1–4 节，与当前极限内容一起复习；学会指数和对数求导后再看第 6 节；第 7 节用来理解线性近似的延伸。第 8 节作为数列极限的补充工具。

[重要三角极限](week1-functions-important-limits.md) · [线性近似与微分](week4-linear-approximation.md) · [课件页面索引](../references/README.md)
