# 线性代数学习笔记 第五章

# 5 二次型
## 5.1 二次型及其标准形
### 5.1.1 二次型的矩阵表示

> 定义1 关于 $n$ 个变量 $x_1, x_2, \cdots , x_n$ 的二次其次式

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