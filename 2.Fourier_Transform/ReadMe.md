# 泰勒公式和泰勒级数

## 泰勒公式

> ref: 《高等数学》上册 P140
### 推导过程

提出如下问题：设函数$f(x)$在含有$s_0$的开区间内具有直到$(n+1)$阶导数，试找出一个关于$(x-x_0)$的$n$次多项式
$$p_n(x) = a_0 + a_1 (x - x_0) + a_2(x - x_0)^2 + ... + a_n(x - x_0)^n$$
来近似表达$f(x)$，要求$p_n(x)$与$f(x)$之差是比$(x - x_0)$高阶的无穷小，并给出误差$|f(x) - p_n(x)|$的具体表达式

假设$p_n(x)$在$x_0$处的函数值及它的直到$n$阶导数在$x_0$处的值依次与$f(x_0)$，$f^{\prime}(x_0)$，...，$f^{(n)}(x_0)$相等，即满足
$$
\begin{cases}
p_n(x_0) = f(x_0), \\
p_n^{\prime}(x_0) = f^{\prime}(x_0), \\
p_n^{\prime \prime}(x_0) = f^{\prime \prime}(x_0), \\
... \\
p_n^{(n)}(x_0) = f^{(n)}(x_0), \\
\end{cases}
$$

按照这些等式来确定多项式$p_n(x)$的系数$a_0, a_1, a_2, ..., a_n$。为此，对 $p_n(x)$求各阶导数，然后分别带入以上等式得：
$$
\begin{cases}
a_0 = f(x_0) \\
1 * a_1 = f^{\prime}(x_0) \\
2! * a_2 = f^{\prime \prime}(x_0) \\
... \\
n! * a_n = f^{(n)}(x_0) \\
\end{cases}
$$

即得：
$$
\begin{cases}
a_0 = f(x_0) \\
a_1 = f^{\prime}(x_0) \\
a_2 = \frac{1}{2!} f^{\prime \prime}(x_0) \\
... \\
a_n = \frac{1}{n!} f^{(n)}(x_0) \\
\end{cases}
$$

将所求到的$a_0, a_1, a_2, ..., a_n$带入到 $p_n(x)$，得：
$$
p_n(x) = f(x_0) + f^{\prime}(x_0)(x - x_0) + \frac{f^{\prime \prime}(x_0)}{2!} (x - x_0)^2 + ... + \frac{f^{(n)}(x_0)}{n!} (x - x_0)^n
$$



**泰勒中值定理**：

如果函数$f(x)$在含有$x_0$的某个开区间$(a, b)$内具有直到$(n + 1)$阶的导数，则对任一$x \in (a, b)$，有
$$
p_n(x) = f(x_0) + f^{\prime}(x - x_0) + \frac{f^{\prime \prime}(x_0)}{2!} (x - x_0)^2 + ... + \frac{f^{(n)}(x_0)}{n!} (x - x_0)^n + R_n(x)
$$

其中
$$
R_n(x) = \frac{f^{(n+1)}(\xi)}{(n + 1)!} (x - x_0)^{(n + 1)}
$$
这里$\xi$是$x_0$与$x$之间的某个值，泰勒中值定理是拉格朗日中值定理的推广，证明暂且忽略，需要可以查看《高等数学》上册P141




## 泰勒级数

> ref: 《高等数学》下册 P278

泰勒级数（Taylor Series）的推导过程主要基于函数的无限次可微性（即光滑性）以及多项式逼近的思想。泰勒级数提供了一种将函数表示为无限项和（即级数）的方法，每一项都是函数在某点的导数乘以该点到该点的距离（或该点的幂）的乘积。

### 推导过程

经常会遇到问题：给定函数$f(x)$，要考虑他能否在某个区间内展开成幂级数，也就是说，是否能找到这样一个幂级数，他在某区间内收敛，且其恰好就是给定的函数$f(x)$，如果能找到这样的幂级数，我们就说，函数$f(x)$在该区间内能展开成幂级数，而这个幂级数在该区间内就表达了函数$f(x)$。

假设函数$f(x)$在点$x_0$的某邻域$U(x_0)$内能展开成幂级数，即有：
$$
f(x) = a_0 + a_1(x - x_0) + a_2(x - x_0)^2 + ... + a_n(x - x_0)^n + ..., x \in U(x_0)
$$
那么根据和函数的性质，可知$f(x)$在$U(x_0)$内应具有任意阶导数，且
$$
f^{(n)}(x) = n!a_n + (n+1)!a_{n+1}(x - x_0) + \frac{(n + 2)!}{2!}(x - x_0)^2 + ...,
$$
当$x=x_0$时，可得：
$$
f^{(n)}(x_0) = n! a_n
$$

于是
$$
	a_n = \frac{1}{n!} f^{n}(x_0) \quad (n = 0, 1, 2, ...)
$$

这就表明，如果函数$f(x)$有幂级数展开式，那么该幂级数的系数$a_n$由上式决定，该幂级数必定为：
$$
f(x_0) + f^{\prime}(x_0)(x - x_0) + ... + \frac{f^{(n)}(x_0)}{n!} (x - x_0)^n + ... = \sum_{n = 0}^{\infty} \frac{f^{(n)}(x_0)}{n!} (x - x_0)^n
$$

因此$f(x)$在$x_0$邻域内的展开式必定为：
$$
f(x) = \sum_{n = 0}^{\infty} \frac{f^n(x_0)}{n!}(x - x_0)^n, \quad x \in U(x_0)
$$

上式即为函数$f(x)$在点$x_0$处的泰勒级数

### 注意事项

- 泰勒级数的收敛性取决于函数f(x)的性质以及x与x0​之间的距离。
- 并非所有函数都有泰勒级数，或者其泰勒级数在整个定义域内都收敛。
- 泰勒级数在理论分析和数值计算中都有广泛应用，特别是在求解微分方程、近似计算等方面。


### 区别和联系

- **区别**：泰勒公式是一个有限项的和加上一个余项，用于近似计算；泰勒级数是一个无限项的和，用于表示函数或进行幂级数展开。
- **联系**：当泰勒公式的余项趋于0时，泰勒公式就变成了泰勒级数。在某些情况下，泰勒级数可以精确地表示函数，但在其他情况下可能只在某个区间内收敛。

因此，虽然泰勒公式和泰勒级数在形式上有相似之处，但它们是两个不同的概念，用于不同的数学分析和计算中。



## 欧拉公式

由于欧拉公式也是用了泰勒级数相关的内容，因此一并放到此章节

### 前备知识点

> ref: 《高等数学》下册P280

函数$f(x) = e^x$展开成$x$的幂级数为：$e^x = 1 + x + \frac{x^2}{2!} + ... + \frac{x^n}{n!} + ...,$

函数$f(x) = \sin{x}$展开成$x$的幂级数为：$x - \frac{x^3}{3!} + \frac{x^5}{5!} - (-1)^k\frac{x^{2k + 1}}{(2k + 1)!} + ... \quad (-\infty < x < + \infty)$，
更一般的可以写为：$\sin{x} = \sum_{k=0}^{\infty} \frac{(-1)^k}{(2k + 1)!}x^{2k + 1} \quad (-\infty < x < +\infty)$

对$\sin{x}$两边求导可得：$\cos{x} = \sum_{k=0}^{\infty} \frac{(-1)^k}{(2k)!}x^{2k} \quad (-\infty < x < +\infty)$

### 推导过程

> ref: 《高等数学》下册P291

设有复数项级数为
$$
(u_1 + iv_1) + (u_2 + iv_2) + ... + (u_n + iv_n) + ...,\quad \quad (1)
$$
其中$u_n, v_n, (n = 1, 2, 3, ...)$为实数或实函数，如果实部所成的级数
$$u_1 + u_2 + ... + u_n + ... \quad \quad (2)$$
收敛于和$u$，并且虚部所成的级数
$$v_1 + v_2 + ... + v_n + ... \quad \quad (3) $$
收敛于和$v$，那就说上式的级数收敛且其和为$u + iv$

如果式(1)各项的模所构成的级数$\sqrt{u_1^2 + v_1^2} + \sqrt{u_2^2 + v_2^2} + ... +  + \sqrt{u_n^2 + v_n^2} + ...$，收敛，则称式(1)绝对收敛

由于$|u_n| \leq \sqrt{u_n^2 + v_n^2}, \, |v_n| \leq \sqrt{u_n^2 + v_n^2} \, (n = 1, 2, 3, ...)$，那么级数(2)(3)绝对收敛，从而级数(1)绝对收敛

考察复数项级数：
$$
1 + z + \frac{1}{2!}z^2 + ... + \frac{1}{n!}z^n + ... \quad (z = x + iy) \quad \quad (4)
$$
可以证明级数(4)在整个复平面上是绝对收敛的。在$x$轴上$(z = x)$他表示指数函数$e^x$，在整个复平面上用它来定义复变量指数函数，记作$e^z$。于是$e^z$定义为
$$
e^z = 1 + z + \frac{1}{2!}z^2 + ... + \frac{1}{n!}z^n + ... \quad (|z| < \infty) \quad \quad (5)
$$
当$x = 0$时，$z$为纯虚数$iy$，式(5)成为：
$$
\begin{align}
e^{iy} &= 1 + iy + \frac{1}{2!}(iy)^2 + \frac{1}{3!}(iy)^3 + ... + \frac{1}{n!}(iy)^n + ... \\
&= 1 + iy - \frac{1}{2!}y^2 - i\frac{1}{3!}y^3 + \frac{1}{4!}y^4 + i\frac{1}{5!}y^5 - ...\\
&= (1 - \frac{1}{2!}y^2 + \frac{1}{4!}y^4 - ...) + (iy - i\frac{1}{3!}y^3 + i\frac{1}{5!}y^5 - ...)\\
\end{align}
$$

把$y$换成$x$，上式变为
$$
e^{ix} = \cos{x} + i \sin{x}
$$
这就是欧拉公式

### 推导过程_法2

欧拉公式的推导通常涉及泰勒级数（或称为幂级数）的展开。
1. **首先，考虑 $e^x$ 的泰勒级数展开**：
	$$e^x = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \frac{x^4}{4!} + \cdots$$
2. **接着，考虑 $\cos x$ 和 $\sin x$ 的泰勒级数展开**：
	$$
	\cos x = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \frac{x^6}{6!} + \cdots \\
	$$
	$$
	\sin x = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!} + \cdots \\
	$$
3. **将 $x$ 替换为 $ix$ 并代入 $e^x$ 的泰勒级数中**：
	 $$e^{ix} = 1 + ix + \frac{(ix)^2}{2!} + \frac{(ix)^3}{3!} + \frac{(ix)^4}{4!} + \cdots$$

4. **展开并合并同类项**：
	$$e^{ix} = 1 + ix - \frac{x^2}{2!} - \frac{ix^3}{3!} + \frac{x^4}{4!} + \frac{ix^5}{5!} - \frac{x^6}{6!} - \frac{ix^7}{7!} + \cdots$$

	注意到，这里的项可以分组为实部和虚部：
	 - 实部：$1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \frac{x^6}{6!} + \cdots$，这正是 $\cos x$ 的泰勒级数。
	 - 虚部：$ix - \frac{ix^3}{3!} + \frac{ix^5}{5!} - \frac{ix^7}{7!} + \cdots$，这可以重写为 $i\left(x - \frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!} + \cdots\right)$，这正是 $i\sin x$ 的泰勒级数。


5. **因此，我们可以得出**：
	$$e^{ix} = \cos x + i\sin x$$
* **结论**

通过上述推导，我们证明了欧拉公式 $e^{ix} = \cos x + i\sin x$ 成立。这个公式在复变函数、电子学、量子力学等领域有着广泛的应用。



# 傅里叶变换

## 傅里叶级数

### 傅里叶级数的一般形式

#### 三角级数

以一般的形式表示正弦函数：
$$
y = A\sin{(wt + \phi)}
$$
其中：$A$: 振幅，$w$: 角频率，$\phi$: 初相

为了研究非正弦周期函数，使用幂展开的方式将周期函数展开成由简单的周期函数（例如三角函数）组成的级数，具体地说，将周期为$T( = \frac{2\pi}{w})$的周期函数用一系列用T为周期的正弦函数$A_n\sin{(nwt + \phi_n)}$组成的级数来表示，记为：
$$
f(t) = A_0 + \sum_{n = 1}^{\infty}A_n\sin{(nwt + \phi_n)}
$$

在电工学上，这种展开称为谐波分析，$A_0$被称为$f(t)$的直流分量；$A_1\sin(wt + \phi_1)$被称为一次谐波（又称为基波）；而$A_2\sin(wt + \phi_2)...$依次称为二次谐波，三次谐波等

为了方便起见，将公式展开：
$$
A_n\sin{(nwt + \phi_n) = A_n\sin{\phi_n\cos{nwt}} + A_n\cos{\phi_n\sin{nwt}}}
$$
令$\frac{a_0}{2} = A_0$，$a_n = A_n\sin{\phi_n}$，$b_n = A_n\cos{\phi_n}$，$w = \frac{\pi}{l}$（即 $T = 2l$），则上式可以改写为：
$$
\frac{a_0}{2} + \sum_{n = 1}^{\infty}(a_n\cos{\frac{n \pi t}{l}} + b_n\sin{\frac{n \pi t}{l}})
$$
形如上式的级数被称为**三角级数**

令$\frac{\pi t}{l} = x$，上式可以改为：
$$
\frac{a_0}{2} + \sum_{n = 1}^{\infty}(a_n\cos{nx} + b_n\sin{nx})
$$
这便是把以$2l$为周期的三角函数转换成了以$2\pi$为周期的三角函数

#### 三角级数的正交性

所谓三角函数系：
$$
1, \cos{x}, \sin{x}, \cos{2x}, \sin{2x}, ..., \cos{nx}, \sin{nx}
$$
在区间$[-\pi, \pi]$上正交，就是指三角函数系中任何不同的两个函数的乘积在趋近啊$[-\pi, \pi]$上的积分等于零，即：
$$
\begin{align}
&\int_{-\pi}^{\pi} \cos{nx}\, dx = 0 \quad (n = 1, 2, 3, ...), \\
&\int_{-\pi}^{\pi} \sin{nx}\, dx = 0 \quad (n = 1, 2, 3, ...), \\
&\int_{-\pi}^{\pi} \sin{kx} \cos{nx}\, dx = 0 \quad (k,n = 1, 2, 3, ..., k \neq n), \\
&\int_{-\pi}^{\pi} \cos{kx} \cos{nx}\, dx = 0 \quad (k,n = 1, 2, 3, ..., k \neq n), \\
&\int_{-\pi}^{\pi} \sin{kx} \sin{nx}\, dx = 0 \quad (k,n = 1, 2, 3, ..., k \neq n), \\
\end{align}
$$
证明：
利用三角函数中的和差化积公式：$\cos{kx}\cos{nx} = \frac{1}{2}[\cos{(k + n)}x + \cos{(k - n)}x]$，
当$k \neq n$时，有：
$$
\begin{align}
\int_{-\pi}^{\pi} \cos{kx}\cos{nx}\,dx &= \frac{1}{2} \int_{-\pi}^{\pi}[\cos{(k + n)}x + \cos{(k - n)}x]\,dx \\
&= \frac{1}{2} [\frac{\sin{(k + n)x}}{k + n} + \frac{\sin{(k - n)}x}{k - n}]_{-\pi}^{\pi} \\
&= 0 \quad (k,n = 1, 2, 3, ..., k \neq n)\\
\end{align}
$$

两个相同函数的乘积在区间$[-\pi, \pi]$上的积分不等于零，即：

$$
\begin{align}
&\int_{-\pi}^{\pi} 1^2 dx = 2\pi \\
&\int_{-\pi}^{\pi} \sin^2{nx} \, dx = \pi \\
&\int_{-\pi}^{\pi} \cos^2{nx} \, dx = \pi \\
\end{align}
$$
其中$n = 1, 2, 3 ...$


#### 推导过程

设$f(x)$是周期为$2\pi$的周期函数，且能展开成三角函数：
$$
f(x) = \frac{a_0}{2} + \sum_{k = 1}^{\infty}(a_k\cos{kx} + b_k\sin{kx})\quad \quad(1)
$$
假设上式中右端的级数可以逐项积分，先求$a_0$，对上式从$-\pi$到$\pi$进行积分，因此有：
$$
\int_{-\pi}^{\pi}f(x)\,dx = \int_{-\pi}^{\pi} \frac{a_0}{2}\,dx + \sum_{k=1}^{\infty}[a_k\int_{-\pi}^{\pi}\cos{kx}\,dx + b_k\int_{-\pi}^{\pi}\sin{kx}\,dx]
$$

根据三角函数系的正交性，等式右边除了第一项外，其余各项均为零，所以：
$$
\int_{-\pi}^{\pi}f(x)\,dx = \frac{a_0}{2} * 2\pi
$$
于是得
$$
a_0 = \frac{1}{\pi}\int_{-\pi}^{\pi} f(x)dx
$$

其次求$a_n$，用$\cos{nx}$乘式(1)两端，再从$-\pi$到$\pi$积分，得到：
$$
\int_{-\pi}^{\pi} f(x) \cos{nx}\,dx = \frac{a_0}{2} \int_{-\pi}^{\pi} {\cos{nx}}\,dx + \sum_{k=1}^{\infty}[a_k\int_{-\pi}^{\pi} \cos{kx} \cos{nx}\,dx + b_k\int_{-\pi}^{\pi}\sin{kx} \cos{nx}\,dx]
$$
根据三角函数系的正交性，等式右端出了$k=n$的一项外，其余各项均为零，所以
$$
\int_{-\pi}^{\pi}f(x)cos{nx}\,dx = a_n\int_{-\pi}^{\pi} \cos^2{nx}\,dx = a_n\pi
$$
于是得：
$$
a_n = \frac{1}{\pi}\int_{-\pi}^{\pi}f(x) \cos{nx}\,dx \quad (n = 1, 2, 3,...)
$$
类似的，用$\sin{x}$乘式(1)两端，再从${-\pi}$到$\pi$积分，可得：
$$
b_n = \frac{1}{\pi}\int_{-\pi}^{\pi}f(x) \sin{nx}\,dx \quad (n = 1, 2, 3,...)
$$

由于当$n=0$时，$a_n$的表达式正好给出$a_0$，因此，已得结果可以合并写成：
$$
\begin{cases}
a_n = \frac{1}{\pi}\int_{-\pi}^{\pi}f(x) \cos{nx}\,dx \quad (n = 1, 2, 3,...) \\
b_n = \frac{1}{\pi}\int_{-\pi}^{\pi}f(x) \sin{nx}\,dx \quad (n = 1, 2, 3,...) \\
\end{cases}
$$
如果上式中的$a_n$和$b_n$都存在，这时它们定出的系数$a_0, a_1, b_1,...$叫做函数$f(x)$的傅里叶系数，将这些系数带入式(1)右端，所得的三角级数
$$
f(x) = \frac{a_0}{2} + \sum_{k = 1}^{\infty}(a_k\cos{kx} + b_k\sin{kx})
$$
叫做傅里叶级数

一个定义在$(-\infty, +\infty)$上周期为$2\pi$的函数$f(x)$，如果他在一个周期上可积，则一定可以做出$f(x)$的傅里叶级数。然而，函数$f(x)$的傅里叶级数是否一定收敛？如果它收敛，他是否一定收敛于函数$f(x)$？一般来说，这两个问题的答案都不是肯定的。那么，$f(x)$在怎样的条件下，他的傅里叶级数不仅收敛，而且收敛于$f(x)$？也就是说，$f(x)$满足什么条件可以展开成傅里叶级数？如下给出收敛定理

定理（收敛定理，狄利克雷（Dirichlet）充分条件） 设$f(x)$是周期为$2\pi$的周期函数，如果它满足：
1. 在一个周期内连续或只有有限个第一类时间点
2. 在一个周期内至多只有有限个极值点
则$f(x)$的傅里叶级数收敛，并且
* 当$x$是$f(x)$的连续点时，级数收敛于$f(x)$
* 当$x$是$f(x)$的间断点时，级数收敛于$\frac{1}{2}[f(x^-) + f(x^+)]$


**以上是以$2\pi$为周期的推导，如果以$T$为周期：**

$$ f(t) = \frac{a_0}{2} + \sum_{n=1}^{\infty} \left( a_n \cos\left(\frac{2\pi n t}{T}\right) + b_n \sin\left(\frac{2\pi n t}{T}\right) \right) $$

其中，系数$a_n$和$b_n$分别为：

$$ a_n = \frac{2}{T} \int_{t_0}^{t_0+T} f(t) \cos\left(\frac{2\pi n t}{T}\right) \, dt $$

$$ b_n = \frac{2}{T} \int_{t_0}^{t_0+T} f(t) \sin\left(\frac{2\pi n t}{T}\right) \, dt $$

这里$t_0$是任意实数。


**如果以$2l$为周期：**

$$ f(t) = \frac{a_0}{2} + \sum_{n=1}^{\infty} \left( a_n \cos\left(\frac{n\pi t}{l}\right) + b_n \sin\left(\frac{n\pi t}{l}\right) \right) $$

其中：

$$ a_n = \frac{1}{l} \int_{-l}^{l} f(t) \cos\left(\frac{n\pi t}{l}\right) \, dt \quad (n = 0, 1, 2, 3, \ldots) $$

$$ b_n = \frac{1}{l} \int_{-l}^{l} f(t) \sin\left(\frac{n\pi t}{l}\right) \, dt \quad (n = 1, 2, 3, \ldots) $$

证明：

做变量代换$z=\frac{\pi x}{l}$，于是区间$-l \leq x \leq l$就变换成$-\pi \leq z \leq \pi$。设函数$f(x)=f(\frac{lz}{\pi}) = F(z))$，从而$F(z)$是周期为$2\pi$的周期函数，并且它满足收敛定理的条件，将$F(z)$展开成傅里叶级数
$$
F(z) = \frac{a_0}{2} + \sum_{n=1}^{\infty} \left( a_n \cos\left(nz\right) + b_n \sin\left(nz\right) \right) 
$$
其中
$$
\begin{align}
a_n = \frac{1}{\pi}\int_{-\pi}^{\pi} F(z)\cos{(nz)}\,dz \\
b_n = \frac{1}{\pi}\int_{-\pi}^{\pi} F(z)\sin{(nz)}\,dz \\
\end{align}
$$
在上式中，零$z=\frac{\pi x}{l}$，并注意到$F(z) = f(x)$，于是有
$$
f(x) = \frac{a_0}{2} + \sum_{n=1}^{\infty} \left( a_n \cos\left(\frac{n\pi x}{l}\right) + b_n \sin\left(\frac{n\pi x}{l}\right) \right) 
$$
其中：
$$ a_n = \frac{1}{l} \int_{-l}^{l} f(x) \cos\left(\frac{n\pi x}{l}\right) \, dt \quad (n = 0, 1, 2, 3, \ldots) $$

$$ b_n = \frac{1}{l} \int_{-l}^{l} f(x) \sin\left(\frac{n\pi x}{l}\right) \, dt \quad (n = 1, 2, 3, \ldots) $$

### 傅里叶级数的复数形式

在周期为$2l$的傅里叶级数的基础上，利用欧拉公式 $\cos{t} = \frac{e^{it} + e^{-it}}{2}, \sin{t} = \frac{e^{it} - e^{-it}}{2i}$，可以把周期为$2l$的傅里叶级数化为：
$$
\begin{align}
f(x) &= \frac{a_0}{2} + \sum_{n=1}^{\infty} \left( a_n \cos\left(\frac{n\pi x}{l}\right) + b_n \sin\left(\frac{n\pi x}{l}\right) \right)  \\
&= \frac{a_0}{2} + \sum_{n = 1}^{\infty}[\frac{a_n - ib_n}{2} e^{i\frac{n \pi x}{l}} + \frac{a_n + ib_n}{2} e^{-i\frac{n \pi x}{l}}] \quad \quad (1)
\end{align}
$$
记
$$
\frac{a_0}{2} = c_0, \frac{a_n - ib_n}{2} = c_n, \frac{a_n + ib_n}{2} = c_{-n} \quad (n = 1, 2, 3,...) \quad \quad (2)
$$
则式(1)就可以表示为：

$$
\begin{align}
&c_0 + \sum_{n = 1}^{\infty}(c_ne^{i\frac{n \pi x}{l}} + c_{-n}e^{-i\frac{n \pi x}{l}}) \\
&=(c_ne^{i\frac{n \pi x}{l}})_{n=0} + \sum_{n = 1}^{\infty}(c_ne^{i\frac{n \pi x}{l}} + c_{-n}e^{-i\frac{n \pi x}{l}})
\end{align}
$$
即得傅里叶级数的复数形式为：
$$
\sum_{n = - \infty}^{\infty} c_n e^{i\frac{n \pi x}{l}}
$$
为了得出系数$c_n$的表达式，把$2l$周期的傅里叶级数带入到式(2)中，得：
$$
\begin{align}
c_0 &= \frac{a_0}{2} = \frac{1}{2l} \int_{-l}^{l}f(x)\,dx \\

c_n &= \frac{a_n - ib_n}{2} \\
&= \frac{1}{2}[\frac{1}{l}\int_{-l}^{l} f(x) \cos{\frac{n \pi x}{l}} \, dx - \frac{i}{l}\int_{-l}^{l}f(x) \sin{\frac{n \pi x}{l}} \, dx] \\
&= \frac{1}{2l}\int_{-l}^{l}f(x)(\cos {\frac{n \pi x}{l}} - i \sin{\frac{n \pi x}{l}}) \, dx \\
&= \frac{1}{2l}\int_{-l}^{l}f(x) e^{-i\frac{n \pi x}{l}}\,dx \quad \quad (n = 1, 2, 3,...) \\

c_{-n} &= \frac{a_n + ib_n}{2} \\
&= \frac{1}{2l}\int_{-l}^{l}f(x)e^{i\frac{n \pi x}{l}}\,dx \quad \quad (n = 1, 2, 3,...) \\
\end{align}
$$

将已得的结果合并写为：
$$
c_n = \frac{1}{2l}\int_{-l}^{l}f(x) e^{-i\frac{n \pi x}{l}}\,dx \quad \quad (n = 0, \pm1, \pm2,...)
$$





以$t$为变量，有复数形式的傅里叶级数如下：
$$ f(t) = \sum_{n = -\infty}^{\infty} C_n e ^{i \frac{n \pi t}{l}} $$

其中，
$$ Cn = \frac{1}{2l} \int_{-l}^{l} f(t) e^{-i \frac{n \pi t}{l}} \, d(t) \quad (n = \pm1, \pm2, \pm3, \ldots)$$


## 傅里叶(Fourier)变换

> ref：《积分变换》-- 东南大学数学系 张元林 编 P5

有复数形式的傅里叶级数如下：
$$ f(t)_{2l} = \sum_{n = -\infty}^{\infty} C_n e ^{i \frac{n \pi t}{l}} $$

其中，
$$ Cn = \frac{1}{2l} \int_{-l}^{l} f(t)_{2l} \, e^{-i \frac{n \pi t}{l}} \, dt \quad (n = \pm1, \pm2, \pm3, \ldots)$$

即：
$$ f(t)_{2l} = \frac{1}{2l} \sum_{n = -\infty}^{\infty} \int_{-l}^{l} f(\tau)_{2l} \, e^{-i \frac{n \pi \tau}{l}} \, d\tau \, e ^{i \frac{n \pi t}{l}} $$
由于$C_n$是一个常数，因此这里为了区分，将$C_n$得积分变量改为$\tau$

令$w= \frac{2\pi}{2l} = \frac{\pi}{l}$得：
$$ f(t)_{2l} = \frac{1}{2l} \sum_{n = -\infty}^{\infty} \int_{-l}^{l} f(\tau)_{2l} \, e^{-i n w \tau} \, d\tau \, e ^{i n w t} $$

令$w_n = nw \quad (n = 0, \pm1, \pm2,...)$得：
$$ f(t)_{2l} = \frac{1}{2l} \sum_{n = -\infty}^{\infty} \int_{-l}^{l} f(\tau)_{2l} \, e^{-i w_n \tau} \, d\tau \, e ^{i w_n t} $$

由于$Cn = \frac{1}{2l} \int_{-l}^{l} f(\tau)_{2l} \, e^{-i w_n \tau} \, d\tau \quad (n = \pm1, \pm2, \pm3, \ldots)$，对于固定的周期$2l$是一个常数，因此这里可以直接把它当成一个常数看待，当周期$2l \rightarrow \infty$，$w_0 = \frac{2\pi}{2l} = \frac{\pi}{l} \rightarrow 0 (\triangle w)$时，将$l = \frac{\pi}{w_0}$代入
$$
\begin{align}
f(t)_{2l} &= \frac{1}{2l} \sum_{n = -\infty}^{\infty} \int_{-l}^{l} f(\tau)_{2l} \, e^{-i w_n \tau} \, d\tau \, e ^{i w_n t} \\
&= \frac{2 \pi}{2l} * \frac{1}{2 \pi} \sum_{n = -\infty}^{\infty} \int_{-l}^{l} f(\tau)_{2l} \, e^{-i w_n \tau} \, d\tau \, e ^{i w_n t} \\
&= \frac{\pi}{l} * \frac{1}{2 \pi} \sum_{n = -\infty}^{\infty} \int_{-l}^{l} f(\tau)_{2l} \, e^{-i w_n \tau} \, d\tau \, e ^{i w_n t} \\
&= \triangle w * \frac{1}{2 \pi} \sum_{n = -\infty}^{\infty} \int_{-l}^{l} f(\tau)_{2l} \, e^{-i w_n \tau} \, d\tau \, e ^{i w_n t} \\
&= \frac{1}{2 \pi} \int_{-\infty}^{\infty} \int_{-l}^{l} f(\tau)_{2l} \, e^{-i w_n \tau} \, d\tau \, e ^{i w_n t} \, dw \\
&= \frac{1}{2 \pi} \int_{-\infty}^{\infty} \int_{-l}^{l} f(\tau)_{2l} \, e^{-i w_n \tau} \, d\tau \, e ^{i w_n t} \, dw \\
\end{align}
$$

又因为$\lim_{l \to \infty}$，因此有：
$$
\begin{align}
f(t) &= \frac{1}{2 \pi} \int_{-\infty}^{\infty} \int_{-l}^{l} f(\tau)_{2l} \, e^{-i w_n \tau} \, d\tau \, e ^{i w_n t} \, dw \\
&= \frac{1}{2 \pi} \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} f(\tau) \, e^{-i w_n \tau} \, d\tau \, e ^{i w_n t} \, dw \\
\end{align}
$$
上式称为傅里叶积分公式，其中间的积分为$F(w)$，即傅里叶变换：
$$
F(w) = \int_{-\infty}^{\infty} f(\tau) \, e^{-i w_n \tau} \, d\tau
$$
外边的积分为傅里叶反变换，即：
$$
f(t) = \frac{1}{2 \pi} \int_{-\infty}^{\infty} F(w) \, e ^{i w_n t} \, dw
$$

总结如下：
$$
\begin{cases}
f(t) = \frac{1}{2\pi} \int_{-\infty}^{+\infty} \int_{-\infty}^{+\infty} f(\tau) e^{-iw\tau} d\tau \, e^{iwt} dw, \quad 周期：\infty，中间的积分也即 F(w)\\
F(w) = \int_{-\infty}^{+\infty} f(t) e^{-iwt} dt, \quad 傅里叶变换(FT) \\
f(t) = \frac{1}{2\pi} \int_{-\infty}^{+\infty} F(w) e^{iwt} dw, \quad 傅里叶反变换(IFT)
\end{cases}
$$

对应傅里叶积分公式，给出傅里叶（Fourier）积分定理：
1. $f(t)$在任一有限区间上满足Dirichlet条件
2. $f(t)$在无限区间$(-\infty, \infty)$上绝对可积（即积分$\int_{-\infty}^{\infty}|f(t)|dt$收敛
则有：
$$
f(t) = \frac{1}{2 \pi} \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} f(\tau) \, e^{-i w_n \tau} \, d\tau \, e ^{i w_n t} \, dw \\
$$
成立，而左端的$f(t)$在他的间断点$t$处，应以$\frac{f(t + 0) +f(t - 0)}{2}$来代替。这个定理的条件是充分的，他的证明需要用到较多的理论基础，这里从略



## 拉普拉斯(Laplace)变换

### 拉普拉斯正变换

> ref：《积分变换》-- 东南大学数学系 张元林 编 P90

傅里叶变换的绝对可积的条件是比较强的，许多函数即使是很简单的函数（例如单位阶跃函数、正弦、余弦函数以及线性函数等）都不满足这个条件，其次可以进行Fourier变换的函数必须在整个数轴上有定义，但在物理、无线电技术等实际应用中，许多以$t$作为自变量的函数往往在$t < 0$时是无意义的或者是不需要考虑的，像这样的函数都不能区Fourier变换。这就使得Fourier变换的应用范围受到相当大的限制。

对于任意一个函数$\phi(t)$，能否经过适当的改造使其进行Fourier变换时克服上述两个缺点呢？这就使我们想到前面讲过的单位阶跃函数$u(t)$和指数衰减函数$e^{-\beta t}(\beta > 0)$所具有的特点，用前者乘上$\phi(t)$可以使积分区间由$(-\infty, \infty)$换成$[0, \infty)$，用后者称$\phi(t)$就有可能使其变成绝对可积，因此，为了克服Fourier变换上述哦两个缺点，自然会想到用$u(t)e^{-\beta t}(\beta > 0)$来乘$\phi(t)$，即：
$$\phi(t)u(t)e^{-\beta t}(\beta > 0)$$
结果发现，只要$\beta$选得适当，一般来说，这个函数的Fourier变换总是存在的。对函数$\phi(t)$进行先乘$u(t)e^{-\beta t}(\beta > 0)$，再取Fourier变换的运算，这样就产生了 Laplace 变换。

对函数$\phi(t)u(t)e^{-\beta t}(\beta > 0)$取Fourier变换，可得：
$$
\begin{align}
G_{\beta}(w) &= \int_{-\infty}^{\infty} \phi(t)u(t)e^{-\beta t}e^{-iwt}dt \\
&= \int_{0}^{\infty} f(t) e^{-(\beta + iw)t} \, dt \\
&= \int_{0}^{\infty} f(t) e^{-st} \, dt \\
\end{align}
$$
其中
$$s = \beta + iw, \quad f(t) = \phi(t)u(t)$$
若再设$F(s) = G_{\beta}(\frac{s - \beta}{i})$，则得：
$$
\begin{align}
F(s) &= G_{\beta}(\frac{s - \beta}{i}) \\
&= \int_{0}^{\infty} f(t) e^{-(\beta + i \frac{s - \beta}{i}) t} \, dt \\
&= \int_{0}^{\infty} f(t) e^{-s t} \, dt \\
\end{align}
$$
这一步只是为了把自变量$w$换成$s$，上式被称为Laplace变换。

**定义**：

设函数$f(t)$当$t \geq 0$时有定义，而且积分
$\int_{0}^{+\infty} f(t) e^{-st} dt (s是一个复参量)$
在复平面$s$得某一区域内收敛，由此积分所确定的函数记为：
$$
F(s) = \int_{0}^{+\infty} f(t) e^{-st} dt
$$
则称上式为函数$f(t)$得Laplace变换式


**Laplace变换的存在定理**：

1. 在$t \geq 0$的任一有限区间上连续或分段连续
2. 当$t \rightarrow {+\infty}$时，$f(t)$的增长速度不超过某一指数函数，亦即存在常数$M > 0$及$c \geq 0$，使得$|f(t)| \leq Me^{ct}, \quad 0 \leq t < +\infty$成立（满足此条件的函数，称他的增大是不超过指数级的，$c$为他的增长指数）
则$f(t)$的Laplace变换
$$
F(s) = \int_{0}^{+\infty} f(t) e^{-st} dt
$$
在半平面$Re(s) > c$上一定存在，有短的积分在$Re(s) \geq c > c$上绝对收敛而且一致收敛，并且在$Re(s) > c$的半平面内，$F(s)$为解析函数


### 拉普拉斯逆变换

由Laplace变换的概念可知，函数$f(t)$的Laplace变换，实际上就是$F(t)u(t)e^{-\beta t}$的Fourier变换。于是，当$f(t)u(t)e^{-\beta t}$满足Fourier积分定理的条件时，按Fourier积分公式，在$f(t)$连续点处有：
$$
\begin{align}
f(t)u(t)e^{-\beta t} &= \frac{1}{2\pi} \int_{-\infty}^{+\infty} \left[\int_{-\infty}^{+\infty} f(\tau) u(\tau) e^{-\beta \tau} e^{-iw\tau} d\tau \right] \, e^{iwt} dw \\
&= \frac{1}{2\pi} \int_{-\infty}^{+\infty} \, e^{iwt} dw \left[\int_{0}^{+\infty} f(\tau) u(\tau) e^{-(\beta + iw)\tau} d\tau \right] \\
&= \frac{1}{2\pi} \int_{-\infty}^{+\infty} \, F(\beta + iw) e^{iwt} dw, \quad (t > 0) \\
\end{align}
$$
等式两边同乘$e^{\beta t}$并考虑到他与积分变量$w$无关，则
$$
f(t) = \frac{1}{2\pi} \int_{-\infty}^{+\infty} \, F(\beta + iw) e^{(\beta + iw)t} dw, \quad (t > 0) \\
$$
令$\beta + iw = s(即 w = \frac{s - \beta}{i}$，则有
$$
\begin{align}
f(t) &= \frac{1}{2\pi} \int_{\beta - i\infty}^{\beta + i\infty} \, F(s) e^{st} \frac{d[s - \beta]}{i} \\
&= \frac{1}{2\pi i} \int_{\beta - i\infty}^{\beta + i\infty} \, F(s) e^{st} ds \quad (t > 0)
\end{align}
$$
上式右边则称为 Laplace 反演积分，或 反变换


## 关系

$$
\begin{align}
Fourier Series \quad \overset{周期 \to \infty}{\longrightarrow} \quad \quad Fourier Transform \\
Fourier Transform \quad \overset{两边乘上 u(t) e^{-\beta t}}{\longrightarrow} \quad \quad Laplace Transform \\
\end{align}
$$

# 离散变换

## Z变换

欧拉公式：$e^{i\theta} = \cos(\theta) + i\sin(\theta)$

T为采样周期
$$e(t) \overset{采样}{\longrightarrow} e^*(t) = \sum_{n=0}^{\infty} e(nT) \delta(t-nT) $$

拉氏变换：
$$
E^*(s) = \int_{-\infty}^{\infty} e^*(t)e^{-st} dt \\
= \int_{-\infty}^{\infty}[\sum_{n=0}^{\infty} e(nT) \delta(t-nT)]e^{-st}dt \\
= \sum_{n=0}^{\infty} e(nT) [\int_{-\infty}^{\infty} \delta(t-nT)e^{-st}dt]
$$

由脉冲信号筛选性质：$\int_{-\infty}^{\infty} \delta(t-nT)f(t)dt=f(nT)$

故：$E^*(s) = \sum_{n=0}^{\infty} e(nT) e^{-nsT}$

令 $\delta = e^{sT}$ 得 $E(z) = E^*(s)|_{s=\frac{1}{T}ln(z)} = \sum_{n=0}^{\infty}e(nT)z^{-n}$
## 离散傅里叶级数

## 离散傅里叶变换
