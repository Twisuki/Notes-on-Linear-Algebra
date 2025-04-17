# 线性代数学习笔记 第五章

# 5 二次型
## 5.1 二次型及其标准形
### 5.1.1 二次型的矩阵表示

> 定义1 关于 $n$ 个变量 $x_1, x_2, \cdots , x_n$ 的二次齐次式

$$
f(x_1, x_2, \cdots . x_n) = a_{11} x_1^2 + 2a_{12} x_1 x_2 + \cdots + 2a_{1n} x_1 x_n + a_{22} x_2^2 + \\
2a_{23} x_2 x_3 + \cdots + 2a_{2n} x_2 x_n + \cdots + a_{nn} x_n^2
$$

称为一个 $n$ 元二次型(简称为二次型). 当二次型系数 $a_{ij} \ (i, j = 1, 2, \cdots , n)$ 为实数(复数)时, 称此二次型为实(复)二次型

令 $a_{ij} = a_{ji} \ (i < j>)$ , 将上式变形

$$
f(x_1, x_2, \cdots . x_n) = a_{11} x_1^2 + 2a_{12} x_1 x_2 + \cdots + 2a_{1n} x_1 x_n + a_{22} x_2^2 + \\
2a_{23} x_2 x_3 + \cdots + 2a_{2n} x_2 x_n + \cdots + a_{nn} x_n^2 \\
= \sum_{j = 1}^n a_{1j} x_1 x_j + \sum_{j = 1}^n a_{2j} x_2 x_j + \cdots + \sum_{j = 1}^n a_{nj} x_n x_j \\
= \sum_{i = 1}^n \sum_{j = 1}^n a_{ij} x_i x_j
(或 \sum_{i, j = 1}^n a_{ij} x_i x_j)
$$

记

$$
A = \begin{pmatrix}
    a_{11} & a_{12} & \cdots & a_{1n} \\
    a_{21} & a_{22} & \cdots & a_{2n} \\
    \vdots & \vdots &   & \vdots \\
    a_{n1} & a_{n2} & \cdots & a_{nn}
\end{pmatrix} , 
X = \begin{pmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{pmatrix}
$$

则上述二次型可用矩阵乘法表示为

$$
f(x_1, x_2, \cdots , x_n) = \sum_{i = 1}^n \sum_{j = 1}^n a_{ij} x_i x_j = X^TBX
$$

其中矩阵 $A$ 称为二次型的矩阵, 它的秩也称为二次型的秩, 若 $r(A) = n$ , 则称二次型是满秩的

显然二次型的的矩阵 $A$ 为对称矩阵 ($a_{ij} = a_{ji}$) , 它的元素 $a_{ij}$ 恰为二次型 $f(x_1, x_2, \cdots , x_n)$ 中 $x_i x_j$ 系数的一半; 而 $a_{ii}$ 为 $x_i^2$ 项的系数, 从而还可知

$$
f(x_1, x_2, \cdots , x_n) = X^TAX = X^TBX
$$

其中 $A^T = A, B^T = B$ , 则 $A = B$, 从而二次型 $f(x_1, x_2, \cdots , x_n)$ 与它的矩阵是一一对应的

例 求二次型 $f(x_1, x_2, x_3) = x_1^2 - 4x_1x_2 + 2x_1x_3 - 2x_2^2 + 6x_3^2$ 的秩

解

$$
f(x_1, x_2, x_3) = x_1^2 - 2x_1x_2 + x_1x_3 - 2x_2x_1 - 2x_2^2 + 0x_2x_3 + x_3x_1 + 0x_3x_2 + 6x_3^2
$$

则

$$
A = \begin{pmatrix}
    1 & -2 & 1 \\
    -2 & -2 & 0 \\
    1 & 0 & 6
\end{pmatrix}
\rightarrow
\begin{pmatrix}
    1 & -2 & 1 \\
    0 & 2 & 5 \\
    0 & 0 & 17
\end{pmatrix}
$$

即 $r(A) = 3$ , 则二次型的秩为 $3$

> 定义2 只含平方项的二次型 $f(x_1, x_2, \cdots , x_n) = \sum_{i = 1}^n \lambda_i x_i^2$ 称为标准型

标准型的矩阵为对角矩阵

### 5.1.2 二次型的变换与矩阵的合同

设 $n$ 元二次型 $f(x_1, x_2, \cdots , x_n) = X^TAX$ , $C$ 是满秩的 $n$ 阶方阵, 做线性变换

$$
X = CY
$$

其中 $Y = (y_1, y_2, \cdots , y_n)^T$ , 则原二次型将变为关于新变量 $y_1, y_2, \cdots , y_n$ 的二次型, 且二次型的矩阵为

$$
B = C^TAC
$$

将 $X = CY$ 代入二次型 $X^TAX$ , 即有

$$
f = X^TAX = (Y^TC^T)A(CY) = C^TAC
$$

则 $B = C^TAC$ 为对称矩阵, 故 $f = Y^T(C^TAC)Y$ 是一个关于变量 $y_1, y_2, \cdots , y_n$ 的二次型

> 定义3 对于连个矩阵 $A$ 和 $B$ , 若存在满秩矩阵 $P$ , 使 $P^TAP = B$ , 则称矩阵 $A$ 与 $B$ 合同, 记作 $A \simeq B$

可验证矩阵之间的合同关系具有以下性质

- $A \simeq A$ (反身性)
- $A \simeq B \Rightarrow B \simeq A$ (对称性)
- $A \simeq B , B \simeq C \Rightarrow A \simeq C$ (传递性)

由性质3可知, 对二次型做满秩线性变换后, 所得新的二次型的矩阵与原二次型的矩阵有合同关系, 变换前后的矩阵关系如下所示

$$
X^TAX \xrightarrow[]{经满秩线性变换 X = PY} Y^TBY \\
\updownarrow \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \updownarrow \\
A \xrightarrow[]{\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ } B
$$

由于矩阵 $A$ 左乘或右乘一个满秩矩阵, 其秩不变, 因此二次型在满秩线性变换中其秩不变

### 5.1.3 二次型的标准型

如果满秩线性变换 $X = CY$ 将二次型 $X^TAX$ 化成了标准二次型 $\sum_{i = 1}^n \lambda_i y_i^2$ , 则称 $\sum_{i = 1}^n \lambda_i y_i^2$ 为二次型 $X^TAX$ 的一个标准型

> 定理1 对于任意二次型 $f = X^TAX$ , 一定存在满秩线性变换 $X = CY$ , 使二次型华为标准型

> 推论1 任意给定一个实对称矩阵 $A$ , 一定存在可逆矩阵 $C$ , 使 $C^TAC$ 为对角矩阵 (即对于任意实对称矩阵都有一个一个对角矩阵与之合同)

## 5.2 正交变换法化二次型为标准型

如果二次型满秩线性变换 $X = CY$ 中, 矩阵 $C$ 为正交矩阵, 则称这个变换为正交变换

### 5.2.1 实对称矩阵的对角化

> 定理1 实对称矩阵的特征值都是实数

证 设 $\lambda$ 为实对称矩阵 $A$ 的特征特质, $X$ 为对应的特征向量, 则

$$
AX = \lambda X \ , \ X \ne \mathbf{0}
$$

用 $\overline{X}$ 表示将向量 $X$ 所有分量换乘共轭复数后得到的向量, 称之为 $X$ 的共轭向量, 上式两边同时取共轭, 则

$$
A \overline{X} = \overline{\lambda} \overline{X} \ , \ X \ne \mathbf{0}
$$

上式两边同时去转置, 又矩阵 $A$ 的对称性可得

$$
\overline{X}^TA = \overline{\lambda} \overline{X}^T
$$

因此

$$
\overline{X}^TAX = \overline{\lambda} \overline{X}^TX
$$

又由第一个式子得

$$
\overline{X}^TAX = \overline{X}^T (\lambda X) = \lambda \overline{X}^TX
$$

所以

$$
(\lambda - \overline{\lambda}) \overline{X}^TX = 0
$$

因为 $X \ne \mathbf{0}$ , 故 $\lambda = \overline{\lambda}$ , 即 $\lambda$ 为实数

> 定理2 实对称矩阵的不同的特征值对应的特征向量必正交

证 设 $\lambda_1, \lambda_2$ 是实对称矩阵 $A$ 的两个不同的特征值, $X_1, X_2$ 为对应的特征向量, 则

$$
AX_1 = \lambda_1 X_1 \ , \ AX_2 = \lambda_2 X_2
$$

又 $A^T = A$ , 则

$$
\lambda_2 X_1^T X_2 = X_1^T A X_2 = (AX_1)^T X_2 = (\lambda_1 X_1)^T X_2 = \lambda_1 X_1^T X_2
$$

从而 $(|lambda_1 - \lambda_2)X_1^T X_2 = 0$ , 又 $\lambda_1 \ne \lambda_2$ , 故 $X_1^T X_2 = 0$ , 即 $X_1 , X_2$ 正交

> 定理3 若实数 $\lambda$ 为实对称方阵 $A$ 的特征方程的 $k$ 重根, 则矩阵 $A$ 对应于 $\lambda$ 的线性无关的实特征向量的最大个数恰为 $k$ 个

> 定理4 设 $A$ 为 $n$ 阶实对称矩阵, 则一定存在正交矩阵 $Q$ , 使 $Q^TAQ$ 为对角矩阵, 且此对角矩阵的对角元恰为矩阵 $A$ 的 $n$ 个特征值(重数计算在内)

证 设实对称矩阵 $A$ 的特征值为 $\lambda_1 \le \lambda_2 \le \cdots \le \lambda_n$ (重数计算在内), 则由定理3, 对于 $A$ 的某个 $k$ 重特征值 $\lambda = \lambda_{i + 1} = \lambda_{i + 2} = \cdots = \lambda_{i + k}$ , 恰有 $k$ 个线性无关的实特征向量, 将它们正交化, 所得的 $k$ 正交向量仍是对应于特征值 $k$ 的特征向量. 又由定理2, 矩阵 $A$ 不同的特征值对应的特征向量必正交. 则对应于矩阵 $A$ 的 $n$ 个特征值 $\lambda_1, \lambda_2, \cdots , \lambda_n$ , 可得到 $n$ 个两两相交的特征向量. 将其单位化得 $n$ 个两两相交的单位化特征向量 $\eta_1. \eta_2, \cdots , \eta_n$ , 且

$$
A \eta_i = \lambda_i \eta_i \ , \ i = 1, 2, \cdots , n
$$

以 $\eta_i$ 作为列向量构造矩阵 $Q = (\eta_1, \eta_2, \cdots , \eta_n)$ , 则 $Q$ 正交, 即有 $Q^T = Q^{-1}$

记

$$
A = diag(\lambda_1, \lambda_2, \cdots , \lambda_n) = \begin{pmatrix}
    \lambda_1 \\
     & \lambda_2 \\
     &   & \ddots \\
     &   &   & \lambda_n
\end{pmatrix}
$$

即

$$
AQ = (A \eta_1, A \eta_2, \cdots , A \eta_n) = (\lambda_1 \eta_1, \lambda_2 \eta_2, \cdots , \lambda_n \eta_n) \\
= (\eta_1, \eta_2, \cdots , \eta_n) \begin{pmatrix}
 \lambda_1 \\
 & \lambda_2 \\
 &   & \ddots \\
 &   &   & \lambda_n
\end{pmatrix} \\
= QA
$$

从而得 $Q^{-1}AQ = \Lambda$ 为对角矩阵, 且 $\Lambda$ 的对角元恰为矩阵 $A$ 的 $n$ 个特征值

> 定理5 任意一个实二次型 $f = X^TAX = \sum_{i = 1}^n \sum_{j = 1}^n a_{ij} x_i x_j \ (a_{ij} = a_{ij}, i, j = 1, 2, \cdots , n)$ 都可经过正交变换化为标准型, 即存在正交变换 $X = QY$ , 使得

$$
f = \sum_{i = 1}^n \lambda_i y_i^2 = \lambda_1 y_1^2 + \lambda_2 y_2^2 + \cdots + \lambda_n y_n^2
$$

其中 $\lambda_1, \lambda_2, \cdots , \lambda_n$ 为二次型的矩阵 $A$ 的特征值, $Y = (y_1, y_2, \cdots , y_n)^T , X = (x_1, x_2, \cdots , x_n)^T$

### 5.2.2 正交变换法化二次型为标准型

利用正交变换法化二次型为标准型的步骤如下

1. 写出 $n$ 元二次型所对应的 $n$ 阶矩阵 $A$ , 并求出 $A$ 的全部特征值 $\lambda_1, \lambda_2, \cdots , \lambda_n$ (重数计算在内)
2. 找出对应于各特征值的特征向量, 当 $\lambda_i$ 为 $k_i$ 重特征值时, 必须找出属于 $\lambda_i$ 的 $k_i$ 个线性无关的特征向量 (即找出 $(A - \lambda_i E)X = \mathbf{0}$ 的一个基础解系), 并用施密特正交法将其正交化
3. 将上述 $n$ 个特征向量单位化后记作 $\eta_1, \eta_2, \cdots , \eta_n$ , 并记矩阵 $Q = (\eta_1, \eta_2, \cdots , \eta_n)$ , 则 $X = QY$ 为所求的正交变换, 且 $f$ 的标准型为

$$
f = \lambda_1 y_1^2 + \lambda_2 y_2^2 + \cdots + \lambda_n y_n^2
$$

例 利用正交变换法化二次型 $f = x_1^2 ++ 4x_2^2 - 4x_1x_2 + 4x_1x_3 - 8x_1x_3$ 为标准型

解

二次型矩阵 $A = \begin{pmatrix}
    1 & -2 & 2 \\
    -2 & 4 & -4 \\
    2 & -4 & 4
\end{pmatrix}$ , 矩阵 $A$ 的特征多项式为

$$
\left | A - \lambda E \right | = \begin{pmatrix}
    1-  \lambda & -2 & 2 \\
    -2 & 4 - \lambda & -4 \\
    2 & -4 & 4 - \lambda
\end{pmatrix} = - \lambda^2 (\lambda - 9)
$$

因此, 矩阵 $A$ 的特征值为 $\lambda_1 = 9, \lambda_2 = \lambda_3 = 0$

对于 $\lambda_1 = 9$ , 由于

$$
A - \lambda_1 E = \begin{pmatrix}
    -8 & -2 & 2 \\
    -2 & -5 & -4 \\
    2 & -4 & -5
\end{pmatrix}
\xRightarrow[\cdots]{\cdots}
\begin{pmatrix}
    2 & 0 & -1 \\
    0 & 1 & 1 \\
    0 & 0 & 0
\end{pmatrix}
$$

则齐次线性方程组 $(A - \lambda_1 E)X = \mathbf{0}$ 的基础解系为 $\xi_1 = (1, -2, 2)^T$ , 从而获得 $A$ 的属于特征值 $\lambda_1 = 9$ 的特征向量 $\xi_1 = (1, -2, 2)^T$

对于 $\lambda_2 = \lambda_3 = 0$ , 由于

$$
A - \lambda_2 E = \begin{pmatrix}
    1 & -2 & 2 \\
    -2 & 4 & -4 \\
    2 & -4 & 4
\end{pmatrix}
\xRightarrow[]{}
\begin{pmatrix}
    1 & -2 & 2 \\
    0 & 0 & 0 \\
    0 & 0 & 0
\end{pmatrix}
$$

通过求齐次线性方程组 $(A - \lambda_2 E)X = \mathbf{0}$ 的基础解系并将其正交化, 可得 $A$ 的属于特征值 $\lambda_2 = \lambda_3 = 0$ 的两个相互正交的特征向量 $\xi_1 = (0, 1, 1)^T , \xi_1 = (4, 1, -1)^T$

将上述三个两两正交的特征向量 $\xi_1, \xi_2, \xi_3$ 正交化, 得

$$
\eta_1 = (\frac{1}{3}, - \frac{2}{3}, \frac{2}{3})^T , \eta_2 = (0, \frac{1}{\sqrt{2}}, \frac{1}{\sqrt{2}})^T , \eta_3 = (\frac{4}{3 \sqrt{2}}, \frac{1}{3 \sqrt{2}}, - \frac{1}{3 \sqrt{2}})^T
$$

则在正交变换

$$
\begin{pmatrix} x_1 \\ x_2 \\ x_3 \end{pmatrix}
= \begin{pmatrix}
    \frac{1}{3} & 0 & \frac{4}{3 \sqrt{2}} \\
    - \frac{2}{3} & \frac{1}{\sqrt{2}} & \frac{1}{3 \sqrt{2}} \\
    \frac{2}{3} & \frac{1}{\sqrt{2}} & - \frac{1}{3 \sqrt{2}}
\end{pmatrix}
\begin{pmatrix} y_1 \\ y_2 \\ y_3 \end{pmatrix}
$$

下, 二次型的标准型为 $f = 9y_1^2$

### 5.2.3 正交变换法化二次型为标准型在几何方面的应用

下面讨论如何识别三元二次方程表示的曲面形状, 设 $X = (x, y, z)^T$ , 则二元二次型 $X^TAX$ 可视为几何空间向量 $\alpha$ 的函数, 其中 $\alpha$ 在标准基 $\varepsilon_1, \varepsilon_2, \varepsilon_3$ 写的坐标便是 $X$ . 做满秩线性变换 $X = CY$ , 所得新的二次型 $Y^TC^TACY$ 就是关于 $\alpha$ 在另一组基 $\eta_1, \eta_2, \eta_3$ 下的坐标 $(x', y', z')$ 的二次齐次式, 其中 $Y = (x', y', z')^T, (\eta_1, \eta_2, \eta_3) = (\varepsilon_1, \varepsilon_2, \varepsilon_3)C$

对于方程

$$
X^TAX = 1
$$

如果将 $X = (x, y, z)^T$ 视为动点 $M$ 在空间直角坐标系下的坐标, 则满足上述方程的点点全体构成空间曲面 $S$ , 当 $A$ 不是对角矩阵时, 上述方程不是标准饭程序, 因此不易识别曲面 $S$ 的具体形状. 为此, 采用正交变换 $X = QY$ 化二次型 $X^TAX$ 为标准型 $Y^T \Alpha Y$ , 从而曲面 $S$ 在新的直角坐标系下的方程为

$$
Y^T \Alpha Y = 1
$$

由正交变换的特定, 知上述两方程是同一空间曲面在不同的空间直角坐标系下的方程, 即上述两方程对应的形状相同

例 设二次型 $f(x_1, x_2, x_3) = 5x_1^2 + 5x_2^2 + 3x_3^2 - 2x_1x_2 + 6x_1x_3 - 6x_2x_3$ , 指出方程 $f(x_1, x_2, x_3) = 1$ 表示何种二次曲面

解 二次型 $f$ 的矩阵为

$$
A == \begin{pmatrix}
    5 & -1 & 3 \\
    -1 & 5 & -3 \\
    3 & -3 & 3
\end{pmatrix}
$$

因为

$$
\left | A = \lambda E \right | = \begin{pmatrix}
    5 - \lambda & -1 & 3 \\
    -1 & 5 - \lambda & -3 \\
    3 & -3 & 3 - \lambda
\end{pmatrix}
= - \lambda (\lambda - 4)(\lambda - 9) 
$$

所以 $A$ 的特征值为 $\lambda_1 = 0, \lambda_2 = 4, \lambda_3 = 9$ , 因此, 可利用正交变换将此二次型化为标准型 $f = 4y_2^2 + 9y_3^2$ , 而 $4y_2^3 + 9y_3^2 = 1$ 在 $R^3$ 中表示椭圆柱面, 所以 $f(x_1, x_2, x_3) = 1$ 表示的是椭圆柱面

## 5.3 化二次型为标准型的其他方法
### 5.2.1 配方法

> 5.1.3的定理1 对于任意二次型 $f = X^TAX$ , 一定存在满秩线性变换 $X = CY$ , 使二次型华为标准型

当 $n = 1$ 时, 二次型

$$
f(x_1) = a_{11}x_2^2
$$

已经是标准型.

现假设 $n - 1$ 元的二次型满足定理1, 再设 $n$ 元二次型

$$
f(x_1, x_2, \cdots , x_n) = \sum_{i = 1}^n \sum_{j = 1}^n a_{ij}x_ix_j \ , \ a_{ij} = a_{ji}(i, j = 1, 2, \cdots , n)
$$

当上述二次型的矩阵 $A$ 为零矩阵时, 结论显然成立, 下面假定矩阵 $A$ 不为零矩阵

1. $A$ 的主对角元 $a_{ij}(i \le i \le n)$中至少有一个不为零, 不妨设 $a_{11} \ne 0$ , 这时

$$
f(x_1, x_2, \cdots , x_n) = a_{11}x_1^2 + \sum_{j = 2}^n a_{1j}x_1x_j + \sum_{i = 2}^n a_{i1}x_ix_1 + \sum_{i = 2}^n \sum_{j = 2}^n a_{ij}x_ix_j \\
= a_{11}(x_1 + \sum_{j = 2}^n a_{11}^{-1}x_{1j}x_j)^2 - a_{11}^{-1}(\sum_{j = 1}^n a_{1j}x_j)^2 + \sum_{i = 2}^n \sum_{j = 2}^n a_{ij}x_ix_j \\
a_{11}(x_1 + \sum_{j = 1}^n a_{11}^{-1}a_{1j}x_j)^2 + \sum_{i = 2}^n \sum_{j = 2}^n a_{ij}x_ix_j
$$

其中

$$
\sum_{i = 1}^n \sum_{j = 1}^n b_{ij}x_ix_j = - a_{11}^{-1} (\sum_{j = 2}^n a_{ij}x_j)^2 + \sum_{i = 2}^n \sum_{j = 2}^n a_{ij}x_ix_j
$$

为一个关于变量 $x_1, x_2, \cdots , x_n$ 的 $n - 1$ 元二次型, 令

$$
\begin{cases}
    y_1 = x_1 + \sum_{j = 2}^n a_{11}^{-1}a_{1j}x_j \\
    y_2 = x_2 \\
    \cdots \cdots \cdots \cdots \\
    y_n = x_n
\end{cases}
$$

或

$$
\begin{cases}
    y_1 = x_1 - \sum_{j = 2}^n a_{11}^{-1}a_{1j}x_j \\
    y_2 = x_2 \\
    \cdots \cdots \cdots \cdots \\
    y_n = x_n
\end{cases}
$$

显然上述变换为一个满秩的线性变换, 它使原二次型化为

$$
f(x_1, x_2, \cdots , x_n) = a_{11}y_1^2 + \sum_{i = 2}^n \sum_{j = 2}^n b_{ij}y_iy_j
$$

由归纳假定, 对于二次型 $\sum_{i = 2}^n \sum_{j = 2}^n b_{ij}y_iy_j$ , 存在满秩线性变换

$$
\begin{cases}
    z_2 = c_{22}y_2 + c_{23}y_3 + \cdots + c_{2n}y_n \\
    z_3 = c_{32}y_2 + c_{33}y_3 + \cdots + c_{3n}y_n \\
    \cdots \cdots \cdots \cdots \\
    z_n = c_{n2}y_2 + c_{n3}y_3 + \cdots + c_{nn}y_n
\end{cases}
$$

使之变为标准型, 即

$$
\sum_{i = 2}^n \sum_{j = 2}^n = b_{ij}y_iy_j = d_2z_2^2 + d_3z_3^2 + \cdots + d_nz_n^2
$$

于是满秩的线性变换

$$
\begin{cases}
    z_1 = y_1 \\
    z_2 = c_{22}y_2 + c_{23}y_3 + \cdots + c_{2n}y_n \\
    \cdots \cdots \cdots \cdots \\
    z_n = c_{n2}y_2 + c_{n3}y_3 + \cdots + c_{nn}y_n
\end{cases}
$$

将原二次型化为标准形, 即

$$
f(x_1, x_2, \cdots , x_n) = a_{11}z_1^2 + d_2z_2^2 + \cdots + d_nz_n^2
$$

