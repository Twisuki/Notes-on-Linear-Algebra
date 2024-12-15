# 线性代数学习笔记 第四章

# 4 线性方程组

## 4.1 解线性方程组的消元法

### 4.1.1 线性方程组解的存在性

设 $n$ 个未知元, $m$ 个方程的线性方程组为

$$
\begin{cases}
  a_{11} x_1 + a_{12} x_2 + \cdots + a_{1n} x_n = b_1 \\
  a_{21} x_1 + a_{21} x_2 + \cdots + a_{2n} x_n = b_2 \\
  \cdots \cdots \cdots \cdots \\
  a_{m1} x_1 + a_{m2} x_2 + \cdots + a_{mn} x_n = b_m
\end{cases}
$$

记

$$
A = \begin{pmatrix}
  a_{11} & a_{12} & \cdots & a_{1n} \\
  a_{21} & a_{22} & \cdots & a_{2n} \\
  \vdots & \vdots &   & \vdots \\
  a_{m1} & a_{m2} & \cdots & a_{mn}
\end{pmatrix} 
\ , \ 
X = \begin{pmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{pmatrix}
\ , \ 
b = \begin{pmatrix} b_1 \\ b_2 \\ \vdots \\ b_n \end{pmatrix}
$$

则方程组可写作

$$
AX = b
$$

又记

$$
\overline{A} = \begin{pmatrix}
  a_{11} & a_{12} & \cdots & a_{1n} & b_1 \\
  a_{21} & a_{22} & \cdots & a_{2n} & b_2 \\
  \vdots & \vdots &   & \vdots & \vdots \\
  a_{m1} & a_{m2} & \cdots & a_{mn} & b_m
\end{pmatrix}
$$

$A$ 和 $\overline{A}$ 分别称为方程组的系数矩阵和增广矩阵

将系数矩阵 $A$ 按列分块, 即

$$
A = (\alpha_1, \alpha_2, \cdots, \alpha_n)
$$

其中 $\alpha_j = (a_{1j}, a_{2j}, \cdots , a_{mj})^T \ (j = 1, 2, \cdots , n)$ 为系数矩阵 $A$ 的第 $j$ 列, 则方程组又可写作

$$
x_1 \alpha_1 + x_2 \alpha_2 + \cdots + x_n \alpha_n = b
$$

当向量 $b \ne \mathbf{0}$ 时, 称 $AX = b$ 为非齐次线性方程组;
而称 $AX = \mathbf{0}$ 为齐次线性方程组, 它也称线性方程组 $AX == b$ 的导出组

> 定义1 若线性方程组有解, 则称改方程组是相容的, 否则称为不相容的

线性方程组是否相容与它的系数矩阵 $A$ 和增广矩阵 $\overline{A}$ 的秩有关,

线性方程组 $AX = b$ 相容性等价于 $b$ 能否用 $A$ 的列向量 $\alpha_1, \alpha_2, \cdots , \alpha_n$ 线性表示

若 $b$ 能由向量组 $\alpha_1, \alpha_2, \cdots , \alpha_n$ 线性表示, 则向量组 $\alpha_1, \alpha_2, \cdots , \alpha_n, b$ 与向量组 $\alpha_1, \alpha_2, \cdots , \alpha_n$ 有相同的秩.
又向量组的秩等同于以其为列向量的矩阵的秩, 则 $\alpha_1, \alpha_2, \cdots , \alpha_n, b$ 与 $\alpha_1, \alpha_2, \cdots , \alpha_n$ 有相同分秩等价于 $A$ 与 $\overline{A}$ 秩相等

> 定理1 线性方程组有解或相容充要条件是它的系数矩阵 $A$ 和增广矩阵 $\overline{A}$ 秩相等, 即 $r(A) = r(\overline{A})$

线性方程组解存在且唯一的充要条件是 $b$ 能由系数矩阵 $A$ 的列向量组 $\alpha_1, \alpha_2, \cdots , \alpha_n$ 线性表示且表示方法唯一.
则 $\alpha_1, \alpha_2, \cdots , \alpha_n$ 线性无关, 即向量组 $\alpha_1, \alpha_2, \cdots , \alpha_n$ 的秩等于 $n$

> 定理2 线性方程组存在唯一解的充要条件是它的系数矩阵 $A$ 与其增广矩阵 $\overline{A}$ 的秩都等于 $n$ , 即 $r(A) = r(\overline{A}) = n$

### 4.1.2 消元法

> 定理3 设线性方程组 $AX = b$ 的增广矩阵 $\overline{A} = (A, b)$ 经初等行变换后得到矩阵为 $\overline{B} = (B, d)$ , 则矩阵 $\overline{B}$ 所对应的线性方程组 $BX = d$ 与愿方程组 $AX = b$ 同解, 即它们有相同的解集

例 解线性方程组

$$
\begin{cases}
  x_1 + x_2 + x_3 = 1 \\
  x_1 + 2x_1 - 5x_3 = 2 \\
  2x_1 + 3x_2 - 4x_3 = 3
\end{cases}
$$

解

对方程组增广矩阵进行初等行变换

$$
\overline{A} = \begin{pmatrix}
  1 & 1 & 1 & 1 \\
  1 & 2 & -5 & 2 \\
  2 & 3 & -4 & 3
\end{pmatrix}
\xrightarrow[r_3 + (-2) \times r_1]{r_2 + (-1) \times r_1}
\begin{pmatrix}
  1 & 1 & 1 & 1 \\
  0 & 1 & 6 & 1 \\
  0 & 1 & -6 & 1
\end{pmatrix}
\xrightarrow[r_3 + (-1) \times r_1]{r_1 + (-1) \times r_2}
\begin{pmatrix}
  1 & 0 & 7 & 0 \\
  0 & 1 & -6 & 1 \\
  0 & 0 & 0 & 0
\end{pmatrix}
$$

变换后对应阶梯线性方程组

$$
\begin{cases}
  x_1 \ \ \ \ \ \ \ + 7x_3 = 0 \\
  \ \ \ \ \ \ \ x_2 - 6x_3 = 1
\end{cases}
$$

它与原方程同解, 取 $x_3 = k$ , 则 $x_1 = -7k, x_2 = 1 + 6k$ , 则原方程解为

$$
\begin{cases}
  x_1 = -7k \\
  x_2 = 1 + 6k \\
  x_3 = k
\end{cases}
$$

求解

$$
\begin{cases}
  x_1 - x_2 + 5x_3 - x_4 = 0 \\
  x_1 + x_2 - 2x_3 + 3x_3 = 0 \\
  3x_1 - x_2 + 8x+3 + X_4 = 0 \\
  x_1 + 3x_2 - 9x_3 + 7x_4 = 0
\end{cases}
$$

解 (变换系数矩阵)

$$
A = \begin{pmatrix}
  1 & -1 & 5 & -1 \\
  1 & 1 & -2 & 3 \\
  3 & -1 & 8 & 1 \\
  1 & 3 & -9 & 7
\end{pmatrix}
\xrightarrow[\cdots]{\cdots}
\begin{pmatrix}
  1 & 0 & \frac{3}{2} & 1 \\
  0 & 1 & - \frac{7}{2} & 2 \\
  0 & 0 & 0 & 0 \\
  0 & 0 & 0 & 0
\end{pmatrix}
\\
  \begin{cases}
  x_1 + \frac{3}{2} x_3 + x_4 = 0 \\
  x_2 - \frac{7}{2} x_3 + 2x_4 = 0
\end{cases}
\\
x_3 = k_1, x_4 = k_2 \Rightarrow \begin{cases}
  x_1 = - \frac{3}{2} k_1 - k_2 \\
  x_2 = \frac{7}{2} k_1 - 2k_2 \\
  x_3 = k_1 \\
  x_4 = k_2
\end{cases}
$$

上述方法本质为对线性方程组逐步消元, 称为高斯消元法

求解

$$
\begin{cases}
  x_1 + x_2 + 2x_3 + 3x_4 = 1 \\
  x_2 + x_3 - 4x_4 = 1 \\
  x_1 + 2x_2 + 3x_3 - 4x_4 = 4 \\
  2x_1 + 3x_2 - x_3 - x_4 = -6
\end{cases}
$$

解

$$
\overline{A} = \begin{pmatrix}
  1 & 1 & 2 & 3 & 1 \\
  0 & 1 & 1 & -4 & 1 \\
  1 & 2 & 3 & -1 & 4 \\
  2 & 3 & -1 & -1 & -6
\end{pmatrix}
\xrightarrow[\cdots]{\cdots}
\begin{pmatrix}
  1 & 1 & 2 & 3 & 1\\
  0 & 1 & 1 & -4 & 1 \\
  0 & 0 & 2 & 1 & 3 \\
  0 & 0 & 0 & 0 & 1
\end{pmatrix}
$$

因为 $r(A) = 3, r(\overline{A}) = 4 \ne r(A)$ , 则原方程组无解

实际上上述矩阵最后一行对应方程为 $0x_1 + 0x_2 + 0x_3 + 0x_4 = 1$ , 故无解

## 4.2 齐次线性方程组解的结构

### 4.2.1 齐次线性方程组有非零解的条件

$n$ 元齐次方程组

$$
AX = \mathbf{0}
$$

其中 $A$ 为 $m \times n$ 矩阵, 由于零向量总可以由任意向量组表示, 故齐次线性方程组总是相容的, 显然 $X = \mathbf{0}$ 为一个解(称为零解或平凡解)

将其写成向量形式

$$
x_1 \alpha_1 + x_2 \alpha_2 + \cdots + x_n \alpha_n = \mathbf{0}
$$

则下面四个命题等价

- 方程有非零解
- 存在不全为零的数 $x_1, x_2, \cdots , x_n$ 是方程成立
- $\alpha_1, \alpha_2, \cdots , \alpha_n$ 线性相关
- $r(A) = r(\alpha_1, \alpha_2, \cdots , \alpha_n) < n$

> 定理1 设 $A$ 是 $m \times n$ 矩阵, 则为齐次线性方程组 $AX = \mathbf{0}$ 有非零解地方充要条件是 $r(A) < n$

**等价命题 $nn$ 元齐次线性方程组 $AX = \mathbf{0}$ 只有零解充要条件是** $r(A) = n$

> 推论1 设 $A$ 是 $m \times n$ 矩阵, 则

- 当 $m < n$ 时, 线性方程组 $AX = \mathbf{0}$ 必有非零解
- 当 $m = n$ 时, 线性方程组 $AX = \mathbf{0}$ 有非零解的充要条件是 $\left | A \right | = 0$

例

判断 $\lambda$ 为何值时, 下列齐次线性方程组有非零解, 只有零解

$$
\begin{cases}
  x_1 + \lambda x_2 + x_3 = 0 \\
  x_1 - x_2 + x_3 = 0 \\
  \lambda x_1 + x_2 + 2x_3 = 0
\end{cases}
$$

解1

设系数矩阵为 $A$

$$
A = \begin{pmatrix}
  1 & \lambda & 1 \\
  1 & -1 & 1 \\
  \lambda & 1 & 2
\end{pmatrix}
\xrightarrow[\cdots]{\cdots}
\begin{pmatrix}
  1 & -1 & 1 \\
  0 & \lambda + 1 & 0 \\
  0 & 0 & 2 - \lambda
\end{pmatrix}
$$

则当 $\lambda = 2$ 或 $\lambda = -1$ 时, $\left | A \right | = 0$ , 方程组有非零解

当 $\lambda \ne 2$ 且 $\lambda \ne -1$ 时, $\left | A \right | \ne 0$ , 方程组只有零解

### 4.2.2 齐次线性方程组解的结构

记 $S$ 为 $AX = \mathbf{0}$ 的解集, 则 $S$ 构成一个向量空间, 称之为齐次线性方程组的解空间, 该解空间的一组基, 称为该方程组的一个基础解系

齐次线性方程组的全部解都能由基础解系线性组合表示, 基础解系的线性组合也一定是解, 则只需求齐次线性方程组的一个基础解系 $\xi_1, \xi_2, \cdots , \xi_t$ , 便可知道所有解

$$
k_1 \xi_1 + k_2 \xi_2 + \cdots + k_t \xi_t \ , \ k_1, k_2, \cdots , k_t \in R
$$

> 定理2 设 $n$ 元齐次方程组 $AX = \mathbf{0}$ 的系数矩阵 $A$ 的秩 $r(A) = r < n$ , 则齐次线性方程组 $AX = \mathbf{0}$ 的解空间是 $n - r$ 维的 , 即 $AX = \mathbf{0}$ 的基础解系中含有 $n - r$ 个解向量

$$
\begin{aligned}
  & r(A) = r < n, 则矩阵A至少存在一个r阶子式不为零, 而所有的r + 1阶子式均为零, 不妨设左上角的r阶子式不为零, 则初等行变换A有 \\
  & \begin{pmatrix}
    c_{11} & c_{12} & \cdots & c_{1r} & c_{1, r + 1} & \cdots & c_{1n} \\
    0 & c_{22} & \cdots & c_{2r} & c_{2, r + 1} & \cdots & c_{2n} \\
    \vdots & \vdots &   & \vdots & \vdots &   & \vdots \\
    0 & 0 & \cdots & c_{rr} & c_{r, r + 1} & \cdots & c_{rn} \\
    0 & 0 & \cdots & 0 & 0 & \cdots & 0 \\
    \vdots & \vdots &   & \vdots & \vdots &   & \vdots \\
    0 & 0 & \cdots & 0 & 0 & \cdots & 0
  \end{pmatrix} \\
  & \ \\
  & 这里 c_{ii} \ne 0 \ (i \le i \le r), 则 AX = \mathbf{0} 同解方程组如下 \\
  & \begin{cases}
    c_{11} x_1 + c_{12} x_2 + \cdots + c_{1r} x_r + c_{1, r + 1} x_{r + 1} + \cdots + c_{1n} x_n = 0 \\
    c_{22} + \cdots + c_{2r} x_r + c_{2, r + 1} x_{r + 1} + \cdots + c_{2n} x_n = 0 \\
    \cdots \cdots \cdots \cdots \\
    c_{rr} x_r + c_{r, r + 1} x_{r + 1} + \cdots + c_{rn} x_n = 0
  \end{cases} \\
  & \ \\
  & 将 x_{r + 1}, x_{r + 2}, \cdots , x_n 移至方程组右边并逐步回代的方程组一般解 \\
  & \begin{cases}
    x_1 = d_{11} x_{r + 1} + d_{12} x_{r + 2} + \cdots + d_{1, n - r} x_n \\
    x_2 = d_{21} x_{r + 1} + d_{22} x_{r + 2} + \cdots + d_{2, n - r} x_n \\
    \cdots \cdots \cdots \cdots \\
    x_r = d_{r1} x_{r + 1} + d_{r2} x_{r + 2} + \cdots + d_{r, n - r} x_n
  \end{cases} \\
  & 其中 x_{r + 1}, x_{r + 2}, \cdots , x_n 为任意实数, 称之为自由未知量 \\
  & \ \\
  & 若取 x_{r + 1}, x_{r + 2}, \cdots , x_n 的 n - r 组值 : \\
  & \begin{pmatrix} x_{r + 1} \\ x_{r + 2} \\ x_{r + 3} \\ \vdots  \\ x_n \end{pmatrix} = 
  \begin{pmatrix} 1 \\ 0 \\ 0 \\ \vdots \\ 0 \end{pmatrix} \ , \
  \begin{pmatrix} 0 \\ 1 \\ 0 \\ \vdots \\ 0 \end{pmatrix} \ , \
  \cdots \ , \
  \begin{pmatrix} 0 \\ 0 \\ 0 \\ \vdots \\ 1 \end{pmatrix} \\
  & 则可得齐次线性方程组 AX = \mathbf{0} 的 n - r 个解向量 \\
  & \begin{matrix}
    \xi_1 = (d_{11}, \cdots , d_{r1}, 1, 0, \cdots , 0)^T \\
    \xi_2 = (d_{12}, \cdots , d_{r2}, 0, 1, \cdots , 0)^T \\
    \cdots \\
    \xi_{n - r} = (d_{1, n - r}, \cdots , d_{r, n - r}, 0, 0, \cdots , 1)^T
  \end{matrix} \\
  & 易得 \xi_1, \xi_2, \cdots , \xi_{n - r} 线性无关
\end{aligned}
$$

下面证明齐次线性方程组 $AX = \mathbf{0}$ 的每个解都可由 $\xi_1, \xi_2 , \cdots , \xi_{n - r}$ 线性表示

$$
\begin{aligned}
  & 上式中, 任取 x_{r + 1}, x_{r + 2}, \cdots , x_n 的一组值 k_1, k_2, \cdots , k_{n - r} , 的齐次线性方程组 AX = \mathbf{0} 的解为 \\
  & \begin{cases}
    x_1 = k_1 d_{11} + k_2 d_{12} + \cdots + k_{n - r} d_{1, n - r} \\
    x_2 = k_1 d_{21} + k_2 d_{22} + \cdots + k_{n - r} d_{2, n - r} \\
    \cdots \cdots \cdots \cdots \\
    x_r = k_1 d_{r1} + k_2 d_{r2} + \cdots + k_{n - r} d_{r, n - r} \\
    x_{r + 1} = k_1 \\
    x_{r + 2} = k_2 \\
    \cdots \cdots \cdots \cdots \\
    x_n = k_{n - r}
  \end{cases} \\
  & \ \\
  & 上式写成向量形式为 \\
  & X = (x_1, x_2, \cdots , x_n)^T = k_1 \xi_1 + k_2 \xi_2 + \cdots + k_{n - r} \xi_{n - r} \\
  & 所有 \xi_1, \xi_2, \cdots , \xi_{n - r} 是齐次线性方程组 AX = \mathbf{0} 的一组基, 从而它的解空间是 n - r 维的, 而上式为齐次线性方程组通解
\end{aligned}
$$

例

求下列齐次线性方程组的一个基础解系并写出通解

$$
\begin{cases}
  x_1 + 2x_2 + 2x_3 + x_4 = 0 \\
  2x_1 + x_2 - 2x_3 - 2x_4 = 0 \\
  x_1 - x_2 - 4x_3 - 3x_4 = 0
\end{cases}
$$

解

$$
A = \begin{pmatrix}
  1 & 2 & 2 & 1 \\
  2 & 1 & -2 & -2 \\
  1 & -1 & -4 & -3
\end{pmatrix}
\xrightarrow[\cdots]{\cdots}
\begin{pmatrix}
  1 & 0 & -2 & - \frac{5}{3} \\
  0 & 1 & 2 & \frac{4}{3} \\
  0 & 0 & 0 & 0
\end{pmatrix}
$$

则原方程组同解方程组为

$$
\begin{cases}
  x_1 - 2x_3 - \frac{5}{3} x_4 = 0 \\
  x_2 + 2x_3 + \frac{4}{3} x_4 = 0
\end{cases}
$$

上式中分别取 $x_3 = 1, x_4 = 0$ 和 $x_3 = 0, x_4 = 1$ , 得到基础解系 $\xi_1, \xi_2$

$$
\xi_1 = (2, -2, 1, 0)^T \ , \ \xi_2 = (\frac{5}{3}, - \frac{4}{3}, 0, 1)^T
$$

则原方程组通解为

$$
X = (x_1, x_2, x_3, x_4)^T = k_1 \xi_1 + k_2 \xi_2
$$

即

$$
\begin{cases}
  x_1 = 2k_1 + \frac{5}{3} k_2 \\
  x_2 = -2k_1 - \frac{4}{3} k_2 \\
  x_3 = k_1 \\
  x_4 = k_2
\end{cases} \\
\ \\
k_1, k_2 \in R
$$

求齐次方程组 $AX = \mathbf{0}$ 的通解, 其系数矩阵为

$$
A = \begin{pmatrix}
  1 & 1 & -2 & 1 & 3 \\
  2 & -1 & 2 & 2 & 6 \\
  3 & 2 & -4 & -5 & -7
\end{pmatrix}
$$

解

$$
A \xrightarrow[\cdots]{\cdots} \begin{pmatrix}
  1 & 1 & -2 & 1 & 3 \\
  0 & -3 & 6 & 0 & 0 \\
  0 & -1 & 2 & -8 & -16
\end{pmatrix} = B
$$

$r(B) = 3$ , 继续进行初等列变换, 将其第 $1, 2$ 和 $4$ 列构成的矩阵化为单位矩阵

$$
B \xrightarrow[\cdots]{\cdots} \begin{pmatrix}
  1 & 0 & 0 & 0 & 1 \\
  0 & 1 & -2 & 0 & 0 \\
  0 & 0 & 0 & 1 & 2
\end{pmatrix}
$$

则齐次线性原方程组同解线性方程组为

$$
\begin{cases}
  x_1 + x_5 = 0 \\
  x_2 - 2x_3 = 0 \\
  x_4 + 2x_5 = 0
\end{cases}
$$

取 $x_3, x_5$ 诶自由未知量, 分别取 $x_3 = 1, x_5 = 0$ 和 $x_3 = 0, x_5 = 1$ , 的基础解系 $\xi_1, \xi_2$ , 其中

$$
\xi_1 = (0, 2, 1, 0, 0)^T \ , \ \xi_2 = (-1, 0, 0, -2, 1)^T
$$

而原方程组通解为

$$
X = k_1 \xi_1 + k_2 \xi_2
$$

即

$$
\begin{cases}
  x_1 = -k_2 \\
  x_2 = 2k_1 \\
  x_3 = k_1 \\
  x_4 = -2k_2 \\
  x_5 = k_2
\end{cases}
$$

求解

$$
\begin{cases}
  x_1 + x_2 + x_3 + 4x_4 - 3x_5 = 0 \\
  x_1 - x_2 + 3x_3 - 2x_4 - x_5 = 0 \\
  2x_1 + x_2 + 3x_3 + 5x_4 - 5x_5 = 0 \\
  3x_1 + x_2 + 5x_3 + 6x_4 - 7x_5 = 0
\end{cases}
$$

解

方程个数 $m = 4$ , 自变量个数 $n = 5$ , $m < n$ , 则方程有无穷多组解

$$
A \xrightarrow[\cdots]{\cdots} \begin{pmatrix}
  1 & 0 & 2 & 1 & -2 \\
  0 & 1 & -1 & 3 & -1 \\
  0 & 0 & 0 & 0 & 0 \\
  0 & 0 & 0 & 0 & 0
\end{pmatrix} \\
\ \\
\begin{cases}
  x_1 = -2x_3 - x_4 + 2x_5 \\
  x_2 = x_3 - 3x_4 + x_5
\end{cases} \
, \ 其中 x_3, x_4, x_5 为自由自变量 \\
\ \\
分别令 \begin{pmatrix} x_3 \\ x_4 \\ x_5 \end{pmatrix} 取值
\begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix} \ , \
\begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix} \ , \
\begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix} \\
\ \\
\xi_1 = (-2, 1, 1, 0, 0)^T \ , \ \xi_2 = (-1, -3, 0, 1, 0)^T \ , \ \xi_3 = (2, 1, 0, 0, 1)^T \\
\ \\
X = k_1 \xi_1 + k_2 \xi_2 + k_3 \xi_3
$$

设 $A = (a_{ij})_{m \times n}$ , $B = (s_{jk})_{n \times l}$ , $AB = O$ , 证明 $r(A) + r(B) \le n$

证明

记 $B = (\beta_1, \beta_2, \cdots , \beta_l)$ , 则从 $AB = O$ 和 $AB = (A \beta_1, A \beta_2, \cdots , A \beta_l)$ 可知

$$
A \beta_k = \mathbf{0} \ , \ (k = 1, 2, \cdots , l)
$$

即 $B$ 的 $l$ 个列向量都是齐次方程 $AX = O$ 的解, 由于 $AX = O$ 的基础解系含 $n - r(A)$ 的向量 $\xi_1, \xi_2, \cdots , \xi_{n - r(A)}$ , 即方程解空间 $V$ 的维数为 $n - r(A)$ , 则 $\beta_1, \beta_2, \cdots , \beta_l \in V$ 时, 次组向量的秩不会大于解空间 $V$ 的维数, 即 $r(B) \le n - r(A)$ , 则 $r(A) + r(B) \le n$

## 4.3 非齐次线性方程组解的结构

非齐次线性方程组 $AX = b$ , 其中 $A$ 为 $m \times n$ 矩阵, $b \ne 0$ 为 $m$ 维列向量, 则 $AX = b$ 有解的充要条件是系数矩阵 $A$ 和增广矩阵 $\overline{A}$ 的秩相等, 且这两个矩阵的秩都等于未知数个数 $n$ 时 $AX = b$ 有唯一解

由上一节知, $AX = \mathbf{0}$ 的解关于线性运算封闭, 对于非齐次线性方程组, 这个性质不再保持. 设 $X_1, X_2$ 是非齐次线性方程组 $AX = b$ 的解, 因为:

$$
A(X_! + X_2) = AX_1 + AX_2 = b + b = 2b \ne B
$$

则 $X_1, X_2$ 不再是 $AX = b$ 的解

> 定理1 设 $\eta_1, \eta_2$ 是非齐次线性方程组  $AX = b$ 的两个解, $\xi$ 是其导出组 $AX = \mathbf{0}$ 的解, 则下面四个命题等价

- $\eta_1 - \eta_2$ 是导出组 $AX = \mathbf{0}$ 的解
- $\eta_1 + \xi$ 是线性方程组 $AX = b$ 的解

证

$$
A(\eta_1 - \eta_2) = A \eta_1 - A \eta_2 = b - b = \mathbf{0} \\
A(\eta_1 + \xi) = A \eta_1 + A \xi = b + \mathbf{0} = b
$$

> 定理2 若 $\eta_0$ 是非齐次线性方程组 $AX = b$ 的一个特解, 则非齐次线性方程组 $AX = b$ 的任一解 $\eta$ 都可表为

$$
\eta = \eta_0 + \xi
$$

的形式, 其中 $\xi$ 是导出组 $AX = \mathbf{0}$ 的解

证

$$
\eta = \eta_0 + (\eta - \eta_0)
$$

由定理1, $\xi = \eta - \eta_0$ 是导出组的一个解, 且 $\eta = \eta_0 + \xi$

据定理2, 求出 $AX = b$ 的全部解, 只需找到一个特解以及它的导出组的全部解, 导出组解可由基础解系表示

因此, 只需求 $AX = b$ 的特解和导出组 $AX = \mathbf{0}$ 的基础解系表示它的全部解.

若 $\eta_0$ 是非齐次线性方程组的一个特解, $\xi_1, \xi_2, \cdots , \xi_{n - r}$ 是其导出组的一个基础解系, 则非齐次线性方程组 $AX = b$ 的任一解 $\eta$ 都可表为

$$
\eta = \eta_0 + k_1 \eta_1 + k_2 \eta_2 + \cdots + k_{n - r} \eta_{n - r}
$$

其中 $k_1, k_2, \cdots , k_{n - r}$ 为任意实数, $r = r(A) < n$

例

下列方程是否有解, 若有解, 求解

$$
\begin{cases}
  & 2x + 3y + z = 1 \\
  & x + y + 2z = 2 \\
  & 4x + 7y + 7z = -1 \\
  & x + 3y + 8z = -4
\end{cases}
$$

解

先写出线性方程组的增广矩阵, 并初等变换

$$
\overline{A} = \begin{pmatrix}
  2 & 3 & 1 & 1 \\
  1 & 1 & -2 & 2 \\
  4 & 7 & 7 & -1 \\
  1 & 3 & 8 & -4
\end{pmatrix}
\xrightarrow[\cdots]{\cdots}
\begin{pmatrix}
  1 & 0 & -7 & 5 \\
  0 & 1 & 5 & 3 \\
  0 & 0 & 0 & 0 \\
  0 & 0 & 0 & 0
\end{pmatrix}
$$

$r(\overline{A}) = r(A) = 2 < 3$ , 故原方程有无穷组解

$$
\begin{cases}
  & x_1 - 7x_3 = 5 \\
  & x_2 + 5x_3 = -3
\end{cases}
$$

得到通解表达式

$$
\begin{cases}
  & x_1 = 5 + 7k \\
  & x_2 = -3 - 5k \\
  & x_3 = k
\end{cases}
$$

写成向量形式

$$
\begin{pmatrix} x_1 \\ x_2 \\ x_3 \end{pmatrix} =
\begin{pmatrix} 5 \\ -3 \\ 0 \end{pmatrix} + 
k \begin{pmatrix} 7 \\ -5 \\ 1 \end{pmatrix}
$$

其中 $\eta_0 = (5, -3, 0)^T$ 为原线性方程组的一个特解, 而 $\eta_0 = (7, -5, 1)^T$ 为导出组的一个基础解系

例

设线性方程组 $AX = b$ 的增广矩阵为

$$
\begin{pmatrix}
  1 & 3 & -1 & 2 & -1 & | & -4 \\
  -3 & 1 & 2 & -5 & -4 & | & -1 \\
  2 & -3 & -1 & -1 & 1 & | & 4 \\
  -4 & 16 & 1 & 3 & -9 & | & -21
\end{pmatrix}
$$

求此线性方程组通解

解

$$
\overline{A} \xrightarrow[\cdots]{\cdots}
\begin{pmatrix}
  1 & 0 & 0 & -27 & -22 & 2 \\
  0 & 1 & 0 & -4 & -4 & -1 \\
  0 & 0 & 1 & -41 & -33 & 3 \\
  0 & 0 & 0 & 0 & 0 & 0
\end{pmatrix}
$$

显然 $r(\overline{A}) = r(A) = 3 < 5$ , 故线性方程组有无穷多组解

$$
\begin{cases}
  & x_1 - 27x_4 - 22x_5 = 2 \\
  & x_2 - 4x_4 - 4x_5 = -1 \\
  & x_3 - 41x_4 - 33x_5 = 3
\end{cases}
$$

令 $x_4 = x_5 = 0$ , 的原线性方程组的一个特解 $\eta_0 = (2, -1, 3, 0, 0)^T$ , 令右端向量为零, 分别取 $(x_4, x_5) = (1, 0), (0, 1)$ , 可得导出组的一个基础解系

$$
\xi_1 = (27, 4, 41, 1, 0)^T \ , \ \xi_2 = (22, 4, 33, 0, 1)^T
$$

故原方程的通解为 $X = \eta_0 + k_1 \xi_1 + k_2 \xi_2$

例

设四元非齐次线性方程组系数矩阵秩为 $3$ , 已知 $\eta_1, \eta_2, \eta_3$ 是它的三个解向量, 且 $\eta_1 = (2, 3, 4, 5)^T , \eta_2 + \eta_3 = (1, 2, 3, 4)^T$ , 求该线性方程组的通解

解

设四元非齐次线性方程组为 $AX = b$ , 则 $A \eta_1 = b, A \eta_2 = b, A \eta_3 = b$ , 又

$$
A \cdot \frac{1}{2} (\eta_2 + \eta_3) = \frac{1}{2} A \eta_2 + \frac{1}{2} A \eta_3 = \frac{1}{2} b + \frac{1}{2} b = b
$$

故 $\frac{1}{2} (\eta_2 + \eta_3)$ 也是线性方程组 $AX = b$ 的解, 因此 $\eta_1 - \frac{1}{2} (\eta_2 + \eta_3)$ 是它导出组 $AX = \mathbf{0}$ 的解

因为 $r(A) = 3$ , 故 $AX = \mathbf{0}$ 的基础解系中只含有一个向量, 又

$$
\eta_1 - \frac{1}{2} (\eta_2 + \eta_3) = (\frac{3}{2}, 2, \frac{5}{2}, 3)^T \ne \mathbf{0}
$$

故 $\eta_1 - \frac{1}{2} (\eta_2 + \eta_3)$ 是 $AX = \mathbf{0}$ 的基础解系, 故 $AX = b$ 的通解为

$$
X = \eta_1 + k (\eta_1 = \frac{1}{2} (\eta_1 + \eta_2)) = (2, 3, 4, 5)^T + k(\frac{3}{2}, 2, \frac{5}{2}, 3)^T
$$

## 4.4 矩阵的特征值与特征向量

### 4.4.1 特征值与特征向量

> 定义1 设 $A$ 是 $n$ 阶方阵, 若存在一个数 $\lambda$ 和 $n$ 维非零向量 $\alpha$ , 使

$$
A \alpha = \lambda \alpha
$$

成立, 则称数 $\lambda$ 为方阵 $A$ 的特征值, 非零向量 $\alpha$ 称为 $A$ 对应于特征值 $\lambda$ 的特征向量

**若 $\alpha, \beta$ 是矩阵 $A$ 的属于特征值 $\lambda$ 的特征向量, 则 $k \alpha$ 和 $k_1 \alpha + k_2 \beta$ 也为 $A$ 的属于特征值 $\lambda$ 的特征向量**

设 $n$ 阶矩阵 $A$ 的特征值为 $\lambda$ , 非零向量 $\alpha$ 为 $A$ 的属于特征值 $\lambda$ 的特征向量, 则

$$
(\lambda E - A) \alpha = \mathbf{0}
$$

因此, 特征向量 $\alpha$ 是齐次线性方程组 

$$
(\lambda E - A) X = \mathbf{0}
$$

的非零解. 又方程组有非零解充要条件是其系数矩阵为降秩矩阵, 即系数矩阵的行列式

$$
\left | \lambda E - A \right | = 0
$$

因此, $\lambda$ 是方阵 $A$ 的特征值的充要条件是 $\left | \lambda E - A \right | = 0$

> 定义2 设 $A$ 是 $n$ 阶方阵, 称 $f(\lambda) = \left | \lambda E - A \right |$ 为 $A$ 的特征多项式, 方程 $\left | \lambda E - A \right | = 0$ 称为 $A$ 的特征方程

由此可知, 矩阵 $A$ 的特征值就是其特征方程的根. 复数范围内, $n$ 阶矩阵 $A$ 有 $n$ 个特征值

矩阵 $A$ 的属于特征值 $\lambda$ 的特征向量就是齐次线性方程组 $(\lambda E - A) = \mathbf{0}$ 的非零解

**注意: 由于 $\left | \lambda E - A \right | = (-1)^n \left | \lambda E - A \right |$ , 故又是也称 $\left | \lambda E - A \right |$ 为 $A$ 的特征方程**

相应的, 矩阵 $A$ 的属于特征值 $\lambda$ 的特征向量是齐次线性方程组 $(\lambda E - A) X = \mathbf{0}$ 的非零解

求解一个矩阵 $A$ 的特征值与特征方程的步骤为

1. 求出 $A$ 的特征方程 $\left | \lambda E - A \right | = 0$ 的全部根, 即得 $A$ 的全部特征值 $\lambda_1, \lambda_2, \cdots, \lambda_n$
2. 将每个特征值 $\lambda_i$ 代入齐次线性方程组 $(\lambda_i E - A) X = \mathbf{0}$ , 求出基础解系, 就是 $A$ 对应于特征值 $\lambda_i$ 的特征向量, 基础解系的线性组合(零向量除外)就是 $A$ 对应于 $\lambda_i$ 的全部特征向量

例 求矩阵

$$
A = \begin{pmatrix}
  -1 & 1 & 0 \\
  -4 & 3 & 0 \\
  1 & 0 & 2
\end{pmatrix}
$$

的特征值和相应的特征向量

解 $A$ 的特征方程为

$$
\left | \lambda E - A \right | = 
\begin{vmatrix}
  \lambda + 1 & -1 & 0 \\
  4 & \lambda - 3 & 0 \\
  -1 & 0 & \lambda - 2
\end{vmatrix}
= (\lambda - 2)(\lambda - 1)^2 = 0
$$

故 $A$ 的特征值分别为 $\lambda_1 = 2, \lambda_2 = \lambda_3 = 1$

当 $\lambda = 2$ 时

$$
\lambda E - A = 2E - A =
\begin{pmatrix}
  3 & -1 & 0 \\
  4 & -1 & 0 \\
  -1 & 0 & 0
\end{pmatrix}
\xrightarrow[\cdots]{\cdots}
\begin{pmatrix}
  1 & 0 & 0 \\
  0 & 1 & 0 \\
  0 & 0 & 0
\end{pmatrix}
$$

因此, 齐次线性方程组 $(2E - A)X = \mathbf{0}$ 的一个基础解系为 $\xi_1 = (0, 0, 1)^T$ , 从而矩阵 $A$ 的属于特征值 $\lambda = 2$ 的一个特征向量为 $\xi_1 = (0, 0, 1)^T$

当 $\lambda = 1$ 时

$$
E - A = 
\begin{pmatrix}
  2 & -1 & 0 \\
  4 & -2 & 0 \\
  -1 & 0 & -1
\end{pmatrix}
\xrightarrow[\cdots]{\cdots}
\begin{pmatrix}
  1 & 0 & 1 \\
  0 & 1 & 2 \\
  0 & 0 & 0
\end{pmatrix}
$$

因此, 齐次线性方程组 $(E - A)X = \mathbf{0}$ 的一个基础解系为 $\xi_2 = (-1, -2, 1)^T$ , 从而矩阵 $A$ 的属于特征值 $\lambda = 1$ 的一个特征向量为 $\xi_2 = (-1, -2, 1)^T$

综上, $k_1 \xi_1, k_2 \xi_2$ 分别为 $A$ 的属于特征值 $2$ 和 $1$ 的特征向量

例 求矩阵

$$
A = \begin{pmatrix}
  1 & 1 & 1 & 1 \\
  1 & 1 & 1 & 1 \\
  1 & 1 & 1 & 1 \\
  1 & 1 & 1 & 1
\end{pmatrix}
$$

的特征值和特征向量

解

$A$ 的特征多项式

$$
f(\lambda) = \left | \lambda E - A \right | = 
\begin{vmatrix}
  \lambda - 1 & -1 & -1 & -1 \\
  -1 & \lambda - 1 & -1 & -1 \\
  -1 & -1 & \lambda - 1 & -1 \\
  -1 & -1 & -1 & \lambda - 1
\end{vmatrix}
$$

把行列式二三四列加到一列, 得

$$
\begin{aligned}
  & f(\lambda) = \begin{vmatrix}
    \lambda - 4 & -1 & -1 & -1 \\
    \lambda - 4 & \lambda - 1 & -1 & -1 \\
    \lambda - 4 & -1 & \lambda - 1 & -1 \\
    \lambda - 4 & -1 & -1 & \lambda - 1
  \end{vmatrix} \\
  & = (\lambda - 4) \begin{vmatrix}
    1 & -1 & -1 & -1 \\
    1 & \lambda - 1 & -1 & -1 \\
    1 & -1 & \lambda - 1 & -1 \\
    1 & -1 & -1 & \lambda - 1
  \end{vmatrix} \\
  & =(\lambda - 4) \begin{vmatrix}
    1 & -1 & -1 & -1 \\
    0 & \lambda & 0 & 0 \\
    0 & 0 & \lambda & 0 \\
    0 & 0 & 0 & \lambda
  \end{vmatrix} \\
  & =\lambda^3 (\lambda - 4)
\end{aligned}
$$

故 $A$ 的特征值为 $\lambda_1 = \lambda_2 = \lambda_3 = 0, \lambda_4 = 4$

当 $\lambda = 0$ 时, $(\lambda E - A) X = -AX = \mathbf{0}$ 的基础解系为方程

$$
x_1 + x_2 + x_3 + x_4 = 0
$$

的基础解系, 即 $\xi_1 = (-1, -1, 0, 0)^T, \xi_2 = (-1, 0, 1, 0)^T, \xi_3 = (-1, 0, 0, 1)^T$

故 $A$ 的输入 $\lambda = 0$ 的特征向量为全体 $k_1 \xi_1 + k_2 \xi_2  + k_3 \xi_3$

当 $\lambda = 4$ 时

$$
4E - A = \begin{pmatrix}
  3 & -1 & -1 & -1 \\
  -1 & 3 & -1 & -1 \\
  -1 & -1 & 3 & -1 \\
  -1 & -1 & -1 & 3
\end{pmatrix}
\xrightarrow[]{} \begin{pmatrix}
  1 & 0 & 0 & -1 \\
  0 & 1 & 0 & -1 \\
  0 & 0 & 1 & -1 \\
  0 & 0 & 0 & 0 
\end{pmatrix}
$$

因此, 齐次线性方程组 $(4E - A)X = \mathbf{0}$ 的一个基础解系为 $\xi_4 = (1, 1, 1, 1)^T$ , 而 $k_4 \xi_4$ 是 $A$ 的属于 $\lambda = 4$ 的全部特征向量

### 4.4.2 特征值与特征向量的性质

> 性质1 $n$ 阶矩阵 $A$ 与它的转置矩阵 $A^T$ 有相同的特征值

证

$$
\left | \lambda E - A^T \right | = \left | (\lambda E - A)^T \right | = \left | \lambda E - A \right |
$$

则 $A^T$ 和 $A$ 有相同的特征多项式

> 性质2 设 $A = (a_{ij})$ 是 $n$ 阶矩阵, 则

$$
\begin{aligned}
  & f(\lambda) = \left | \lambda E - A \right | = \\
  & \begin{vmatrix}
    \lambda - a_{11} & -a_{12} & \cdots & -a_{1n} \\
    -a_{21} & \lambda - a_{22} & \cdots & -a_{2n} \\
    \vdots & \vdots &   & \vdots \\
    -a_{n1} & -a_{n2} & \cdots & \lambda - a_{nn}
  \end{vmatrix} \\
  & \lambda^n - (a_{11} + a_{22} + \cdots + a_{nn}) \lambda^{n - 1} + \cdots + (-1)^n \left | A \right |
\end{aligned}
$$

设 $\lambda_1, \lambda_2, \cdots, \lambda_n$ 是 $A$ 的 $n$ 个特征值, 则由 $n$ 次代数方程组的跟据系数关系知

- $\lambda_1 + \lambda_2 + \cdots + \lambda_n = a_{11} + a_{22} + \cdots + a_{nn}$
- $\left | A \right | = \lambda_1 \lambda_2 \cdots \lambda_n$

其中 $A$ 的主对角线元素之和 $a_{11} + a_{22} + \cdots + a_{nn}$ 称为矩阵 $A$ 的迹, 记作 $tr(A)$

**由性质2可知, 若 $A$ 可逆, 则 $A$ 的特征值都不等于零, 而 $A$ 是奇异矩阵时, $A$ 至少有一个零特征值**

> 性质3 设 $\lambda$ 是矩阵 $A$ 的特征值, $\alpha$ 是 $A$ 的属于特征值 $\lambda$ 的特征向量, 则

- $k \lambda$ 是 $kA$ 的特征值 $(k \in R)$
- $\lambda^m$ 是 $A^m$ 的特征值 $(m是正整数)$
- 当 $A$ 可逆时, $\lambda^{-1}$ 是 $A^{-1}$ 的特征值

**而且, $\alpha$ 仍是 $kA, A^m, A^{-1}$ 分别属于特征值 $k \lambda, \lambda^m, \lambda^{-1}$ 的特征向量**

证明 3

若 $A \alpha = \lambda \alpha$ , 由 $\lambda \ne 0$ 知

$$
\lambda = A^{-1} \lambda \alpha \ , \ A^{-1} \alpha = \frac{1}{\lambda} \alpha
$$

故 $\frac{1}{\lambda}$ 是 $A^{-1}$ 的特征值, 同时 $\alpha$ 是 $A^{-1}$ 的输入 $\frac{1}{\lambda}$ 的特征向量

例 设三阶矩阵 $A$ 的特征值为 $1, -1, 2$ , $A^*$ 为 $A$ 的伴随矩阵, 求 $\left | A^* + 3A - 2E \right |$

解

因为 $A$ 的特征值全不为零, 则 $A$ 可逆. 由 $A^* A = \left | A \right | E$ 以及 $\left | A \right | = \lambda_1 \lambda_2 \lambda_3 = -2$ 知, $A^* = -2 A^{-1}$ . 所以, 令

$$
B = A^* + 3A - 2E = -2A^{-1} + 3A - 2E
$$

则 $B$ 有特征值 $-1, -3, 3$ (一般地, 当 $A$ 有特征值 $\lambda$ 时, $aA + bE$ 有特征值 $a \lambda + b$), 从而

$$
\left | A^* + 3A - 2E \right | = \left | B \right | = (-1) \cdot (-3) \cdot 3 = 9
$$

> 性质4 $n$ 阶矩阵 $A$ 的互不相同的特征值 $\lambda_1, \lambda_2, \cdots , \lambda_n$ 对应的特征向量 $\alpha_1, \alpha_2, \cdots , \alpha_n$ 线性无关

证 数学归纳法

已知 $A \alpha_i = \lambda_i \alpha_i \ (i = 1, 2, \cdots , m)$

当 $m = 1$ 时, $\alpha_1 \ne \mathbf{0}$ , 结论成立

假设 $m - 1$ 时结论成立

设有常数 $k_1. k_2. \cdots , k_m$ , 使

$$
k_1 \alpha_1 + k_2 \alpha_2 + \cdots + k_{m - 1} \alpha_{m - 1} + k_m \alpha_m = \mathbf{0}
$$

用矩阵 $A$ 左乘上式 

$$
k_1 A \alpha_1 + k_2 A \alpha_2 + \cdots + k_{m - 1} A \alpha_{m - 1} + k_m A \alpha_m = \mathbf{0}
$$

代入 $A \alpha_i = \lambda_i \alpha_i \ (i = 1, 2, \cdots , m)$

$$
k_1 \lambda_1 \alpha_1 + k_2 \lambda_2 + \alpha_2 + \cdots + k_{m - 1} \lambda_{m - 1} \alpha_{m - 1} + k_m \lambda_m \alpha_m
$$

上式减去 $\lambda_m$ 倍一式, 消去 $\alpha_m$ , 得

$$
k_1 (\lambda_1 - \lambda_m) \alpha_1 + k_2 (\lambda_2 - \lambda_m) \alpha_2 + \cdots + k_{m - 1} (\lambda_{m - 1} - \lambda_m) \alpha_{m - 1} = \mathbf{0}
$$

假设 $m - 1$ 时成立, 即 $\alpha_1, \alpha_2, \cdots , \alpha_{m - 1}$ 线性无关, 则

$$
k_i (\lambda_i - \lambda_m) = 0 \ (i = 1, 2, \cdots , m - 1)
$$

因为 $\lambda_1, \lambda_2, \cdots , \lambda_m$ 互不相同, 则

$$
k_i = 0 \ (i = 1, 2, \cdots , m - 1)
$$

代入一式得 $k_m \alpha_m = \mathbf{0}$ , 而 $\alpha_m \ne \mathbf{0}$ , 则 $k_m = 0$ , 同理

$$
k_1 = k_2 = \cdots = k_m = 0
$$

即 $\alpha_1, \alpha_2, \cdots , \alpha_m$ 线性无关, 证毕

## 4.5  矩阵的相似对角化
### 4.5.1 相似矩阵的概念和性质

> 定义1 设 $A, B$ 都是 $n$ 阶矩阵, 若存在可逆矩阵 $P$ , 使

$$
P^{-1}AP = B
$$

则称 $B$ 是 $A$ 的相似矩阵, 并称矩阵 $A$ 与 $B$ 相似, 记作 $A \sim B$

矩阵的相似关系是一种等价关系, 满足

- 自反性 : $A \sim A$
- 对称性 : 若 $A \sim B$ , 则 $B \sim A$
- 传递性 : 若 $A \sim B, B \sim C$ , 则 $A \sim C$

证明第三个

若 $A \sim B, B \sim C$ , 则分别存在可逆矩阵 $P, Q$ , 使

$$
P^{-1}AP = B \ , \ Q^{-1}BQ = C
$$

故

$$
C = Q^{-1}(P^{-1}AP)Q = (Q^{-1}P^{-1})A(PQ) = (PQ)^{-1}A(PQ)
$$

则 $A \sim C$

例 设矩阵 $A = \begin{pmatrix} 3 & 1 \\ 5 & -1 \end{pmatrix} \ , \ B = \begin{pmatrix} 4 & 0 \\ 0 & -2 \end{pmatrix}$ , 试严重存在可逆矩阵 $P = \begin{pmatrix} 1 & 1 \\ 1 & -5 \end{pmatrix}$ , 使 $A \sim B$

易证 $P$ 可逆, 且 $P^{-1} = \begin{pmatrix} \frac{5}{6} & \frac{1}{6} \\ \frac{1}{6} & -\frac{1}{6} \end{pmatrix}$ , 由

$$
P^{-1}AP = \frac{1}{5} \begin{pmatrix} 5 & 1 \\ 1 & -1 \end{pmatrix} \begin{pmatrix} 3 & 1 \\ 5 & -1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & -5 \end{pmatrix} = \begin{pmatrix} 4 & 0 \\ 0 & -2 \end{pmatrix} = B
$$

得 $A \sim B$

> 性质1 若 $A \sim B$ , 则 $r(A) = r(B)$ , 即相似矩阵有相同的秩

若 $A \sim B$ , 则 $A \approx B (等价)$ , 故 $r(A) = r(B)$

> 性质2 相似矩阵行列式相等

$$
\left | P^{-1}AP \right | = \left | P^{-1} \right | \left | A \right | \left | P \right | 
= \left | P^{-1} \right | \left | P \right | \left | A \right | \\
= \left | P^{-1}P \right | \left | A \right | = \left | E \right | \left | A \right | = \left | A \right |
$$

> 性质3 相似矩阵具有相同和可逆性, 当他们可逆时, 他们的逆矩阵也相似

若 $A, B$  相似且都可逆, 则存在非奇异矩阵 $P$ , 使

$$
P^{-1}AP = B
$$

于是

$$
B^{-1} = P^{-1}A^{-1}P
$$

即 $A^{-1}, B^{-1}$ 相似

> 性质4 若 $A \sim B$ , 则 $A. B$ 存在相同的特征多项式, 从而欧相同的特征值

证

$$
\left | \lambda E - B \right | = \left | \lambda E - P^{-1}AP \right | = \left | P^{-1}(\lambda E - A)P \right | = \left | P^{-1} \right | \left | \lambda E - A \right | \left | P \right | = \left | \lambda E - A \right |
$$

即 $A, B$ 有相同的特征多项式, 均为 $f(\lambda) = (\lambda - 4)(\lambda + 2)$ , 故 $A, B$ 有相同的特征值 $\lambda_1 = 4, \lambda_2 = -2$

### 4.5.2 矩阵与对角矩阵形似的条件

规定对角矩阵

$$
\Lambda = \begin{pmatrix}
  \lambda_1 \\
   & \lambda_2 \\
   &   & \ddots \\
   &   &   & \lambda_n
\end{pmatrix}
$$

可简记为 $\Lambda = diag(\lambda_1, \lambda_2, \cdots , \lambda_n)$

> 定理1 $n$ 阶矩阵 $A$ 与对角矩阵 $\Lambda = diag(\lambda_1, \lambda_2, \cdots , \lambda_n)$ 相似的充要条件为矩阵 $A$ 有 $n$ 个线性无关的特征向量

证

必要性 若 $A$ 与 $\Lambda$ 相似, 则存在可逆矩阵 $P$ 使得

$$
P^{-1}AP = \Lambda
$$

设 $P = (p_1, p_2, \cdots , p_n)$ , 其中 $p_i \ (i = 1, 2, \cdots , n)$ 为 $P$ 的列向量, 则由 $AP = P\Lambda$ 得

$$
A(p_1, p_2, \cdots , p_n) = (p_1, p_2, \cdots , p_n)\begin{pmatrix}
  \lambda_1 \\
   & \lambda_2 \\
   &   & \ddots \\
   &   &   & \lambda_n
\end{pmatrix}
$$

即

$$
Ap_i = \lambda_i p_i \ (i = 1, 2, \cdots , n)
$$

因为 $P$ 可逆, 则 $\left | P \right | \ne 0$ , 从而 $p_i \ (i = 1, 2, \cdots , n)$ 都是非零向量. 因此 $p_1, p_2, \cdots , p_n$ 都是 $A$ 的特征向量, 且它们线性无关

充分性 设 $p_1, p_2, \cdots , p_n$ 为 $A$ 的 $n$ 个线性无关的特征向量, 它们所对应的特征值为 $\lambda_1, \lambda_2, \cdots , \lambda_n$ , 则有

$$
Ap_i = \lambda_i p_i / (i = 1, 2, \cdots , n)
$$

令 $P = (p_1, p-2, \cdots , p_n)$ , 易知 $P$ 可逆, 且

$$
AP = A(p_1, p_2, \cdots , p_n) = (Ap_1, Ap_2, \cdots , Ap_n) \\ \ \\
= (\lambda_1 p_1, \lambda_2 p_2 , \cdots , \lambda_n p_n) \\ \ \\
= (p_1, p_2, \cdots , p_n) \begin{pmatrix}
  \lambda_1 \\
   & \lambda_2 \\
   &   & \ddots \\
   &   &   & \lambda_n
\end{pmatrix}
$$

> 推论1 若 $n$ 阶矩阵 $A$ $b$ 个互异的特征值 $\lambda_1, \lambda_2, \cdots , \lambda_n$ , 则 $A$ 与对角矩阵 $\Lambda = diag(\lambda_1, \lambda_2, \cdots , \lambda_n)$ 相似

对于 $n$ 阶方阵 $A$ , 若存在可逆矩阵 $P$ , 使 $P_{-1}AP = \Lambda$ 为对角矩阵, 则称方阵 $A$ 可对角化

给定 $n$ 阶方阵 $A$ , 其特征方程式 $f(\lambda) = (\lambda - \lambda_1)^{n_1} \cdots (\lambda - \lambda_s)^{n_s}$ , 其中 $n_1 + n_2 + \cdots + n_s = n$ , 则有

> 定理2 $n$ 阶矩阵 $A$ 可对角化的充要条件是对应于 $A$ 的每个特征值的线性无关的特征向量的个数恰好等于该特征值的重数, 即设 $\lambda_i$ 为矩阵 $A$ 的 $n_i$ 重特征值, 则 $A$ 与 $\Lambda$ 相似, 当且仅当

$$
r(\lambda_i E - A) = n - n_i \ (i = 1, 2, \cdots , s)
$$

例如, 矩阵 $\begin{pmatrix} 1 & 1 & 1 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix}$ 的特征值为 $1, 0, 0$ , 对于 $\lambda_2 = 0, n_2 = 3, n = 3$ , 有

$$
r(\lambda_2 E - A) = 1 = n - n_2
$$
故 $a$ 能对角化

又如, 矩阵 $\begin{pmatrix} 1 & 1 & 0 \\ 0 & 0 & 1 \\ 0 & 0 & 0 \end{pmatrix}$ 的特征值也为 $1, 0, 0$ , 对 $\lambda_2 = 0, n_2 = 2, n = 3$ , 有

$$
r(\lambda_2 E - A) = 2 \ne n - n_2
$$

故 $B$ 不能对角化

### 4.5.3 矩阵对角化的步骤

定理1证明过程即为矩阵对角化的步骤, 当方阵 $A$ 可对角化时

- 求出 $A$ 的全部特征值 $\lambda_1, \lambda_2, \cdots , \lambda_s$
- 对于每个特征值 $\lambda_i$ , 设其重数为 $n_i$ , 则对应齐次方程组

$$
(\lambda_i E - A)X = \mathbf{0}
$$

的基础解系由 $n_i$ 个向量 $\xi_{11}, \xi_{12}, \cdots , \xi_{1n_i}$ 构成, 即 $\xi_{11}, \xi_{12}, \cdots , \xi_{1n_i}$ 为 $\lambda_i$ 对应的特征向量

- 上面求出的特征向量 $\xi_{11}, \xi_{12}, \cdots , \xi_{1n_1}; \xi_{21}, \xi_{22}, \cdots , \xi_{2n_2}; \cdots \cdots; \xi_{s1}, \xi_{s2}, \cdots , \xi_{sn_s}$ 恰好为矩阵 $A$ 的 $n$ 个线性无关的特征向量
- 令 $\Lambda = diag(\lambda_1, \cdots , \lambda_1; \lambda_2, \cdots , \lambda_2; \cdots \cdots ; \lambda_s, \cdots ,\lambda_s)$ , $P = \xi_{11}, \xi_{12}, \cdots , \xi_{1n_1}; \xi_{21}, \xi_{22}, \cdots , \xi_{2n_2}; \cdots \cdots; \xi_{s1}, \xi_{s2}, \cdots , \xi_{sn_s}$ , 则

$$
P^{-1}AP = \Lambda
$$

例 设 $A = \begin{pmatrix} 0 & 0 & 1 \\ 1 & 1 & a \\ 1 & 0 & 0 \end{pmatrix}$ , $a$ 为何值时, 矩阵 $A$ 能对角化

解

$$
\left | \lambda E - A \right | = \begin{pmatrix}
  \lambda & 0 & -1 \\
  -1 & \lambda - 1 & -a \\
  -1 & 0 & \lambda
\end{pmatrix} 
= (\lambda - 1)^2 (\lambda + 1)
$$

得 $\lambda_1 = -1, \lambda_2 = \lambda_3 = 1$ , 要使矩阵 $A$ 能对角化, 由定理2: 对应单根 $\lambda_1 = -1$ , 可求得线性无关的特征向量恰有 $1$ 个; 对应重根 $\lambda_2 = \lambda_3 = 1$ , 应有 $2$ 个线性无关的特征向量, 即方程

$$
\left | E - A \right | X = 0
$$

有两个线性无关的解, 即系数矩阵 $E - A$ 的秩

$$
r(E - A) = 1
$$

又

$$
E - A = \begin{pmatrix}
  1 & 0 & -1 \\
  -1 & 0 & -a \\
  -1 & 0 & 1
\end{pmatrix}
\xrightarrow[]{}
\begin{pmatrix}
  1 & 0 & -1 \\
  0 & 0 & a + 1 \\
  0 & 0 & 0
\end{pmatrix}
$$

要使 $r = 1$ , 则 $a + 1 = 0$ , 即 $a = -1$

因此, $a = -1$ 时, 矩阵 $A$ 能对角化

例 给定矩阵 

$$
A = \begin{pmatrix}
  1 & -2 & 2 \\
  -2 & -2 & 4 \\
  2 & 4 & -2
\end{pmatrix}
$$

判断 $A$ 能否化为对角矩阵; 求可逆矩阵 $P$ 和对角矩阵 $\Lambda$ , 使 $P^{-1}AP = \Lambda$ ; 求 $A^n \ (n \ge 2)$

解

$$
\left | \lambda E - A \right | = \begin{pmatrix}
  \lambda - 1 & 2 & -2 \\
  2 & \lambda + 2 & 4 \\
  -2 & -4 & \lambda + 2
\end{pmatrix} 
= (\lambda - 2)^2(\lambda + 7) = 0
$$

得特征值 $\lambda_1 = \lambda_2 = 2, \lambda_3 = -7$ , 对应 $\lambda_1, \lambda_2$ 为二重特征值, 可验证 $r(\lambda_1 E - A) = 1$ , 故得齐次线性方程组

$$
(\lambda_1 E - A)X = \mathbf{0}
$$

的基础解系有两个线性无关的解, 又 $\lambda_3 = -7$ 时, 可知 $r(\lambda_3 E - A) = 2$ , 则

$$
(\lambda_3 E - A)X = \mathbf{0}
$$

的基础解系只有一个向量, 故矩阵 $A$ 有三个线性无关的特征向量, 从而 $A$ 可以对角化

从上式中分别求出基础解系

$$
p_1 = \begin{pmatrix} -1 \\ 1 \\ 0 \end{pmatrix} , 
p_2 = \begin{pmatrix} 2 \\ 0 \\ 1 \end{pmatrix} \\
p_3 = \begin{pmatrix} 1 \\ 2 \\ -2 \end{pmatrix}
$$

令 $P = (p_1, p_2, p_3) = \begin{pmatrix}
  -2 & 2 & 1 \\
  1 & 0 & 2 \\
  0 & 1 & -2
\end{pmatrix} \ , \ \Lambda = \begin{pmatrix}
  2 \\
    & 2 \\
    &  & -7 
\end{pmatrix}$ , 则有

$$
P^{-1}AP = \Lambda
$$

此时 $P^{-1} = \frac{1}{9} \begin{pmatrix}
  -2 & 5 & 4 \\
  2 & 4 & 5 \\
  1 & 2 & -2
\end{pmatrix}$

由 $P^{-1}AP = \Lambda$ 得 $A = P\Lambda P^{-1}$ , 从而

$$
A^2 = A \cdot A = (P\Lambda P^{-1})(P\Lambda P^{-1}) = P \Lambda^2 P^{-1} \\
A^n = A \cdot A \cdot \cdots \cdot A = P \Lambda^n P^{-1} \\
= \begin{pmatrix}
  -2 & 2 & 1 \\
  1 & 0 & 2 \\
  0 & 1 & -2
\end{pmatrix} \begin{pmatrix}
  2 \\
    & 2 \\
    &   & -7\end{pmatrix}^n [\frac{1}{9} \begin{pmatrix}
  -2 & 5 & 4 \\
  2 & 4 & 5 \\
  1 & 2 & -2
\end{pmatrix}] \\
= \frac{1}{9} \begin{pmatrix}
  -2 & 2 & 1 \\
  1 & 0 & 2 \\
  0 & 1 & -2
\end{pmatrix} \begin{pmatrix}
  2^n \\
    & 2^n \\
    &   & (-7)^n
\end{pmatrix} \begin{pmatrix}
  -2 & 5 & 4 \\
  2 & 4 & 5 \\
  1 & 2 & -2
\end{pmatrix} \\
= \frac{1}{9} \begin{pmatrix}
  -2^{n + 1} & 2^{n + 1} & (-7)^n \\
  2^n & 0 & 2(-7)^n \\
  0 & 2^n & (-2)(-7)^n
\end{pmatrix} \begin{pmatrix}
  -2 & 5 & 4 \\
  2 & 4 & 5 \\
  1 & 2 & -2
\end{pmatrix} \\ 
= \frac{1}{9} \begin{pmatrix}
  2^{n + 3} + (-7)^n & -2^{n + 1} + 2(-7)^n & 2^{n + 1} - 2(-7)^n \\
  -2^{n + 1} + 2(-7)^n & 5 \cdot 2^n + 4(-7)^n & 2^{n + 2} - 4(-7)^n \\
  2^{n + 1} - 2(-7)^n & 2^{n + 2} - 4(-7)^n & 5 \cdot 2^n + 4(-7)^n
\end{pmatrix}
$$