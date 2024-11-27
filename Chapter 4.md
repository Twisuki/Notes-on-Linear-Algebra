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
