# 线性代数学习笔记 第二章

# 2 矩阵
## 2.1 矩阵及其运算
### 2.1.1 矩阵的概念
> 定义1 $m \times n$ 个数 $a_{ij} (i = 1, 2, \cdots , m; j = 1, 2, \cdots , n)$ 有序排为 $m$ 行 $n$ 列的数表称 $m$ 行 $n$ 列的矩阵, 简称 $m \times n$ 矩阵, 记作 $(a_{ij})_{m \times n}$

$$
\begin{pmatrix}
 a_{11} & a_{12} & \cdots & a_{1n} \\
 a_{21} & a_{22} & \cdots & a_{2n} \\
 \vdots & \vdots &   & \vdots \\
 a_{m1} & a_{m2} & \cdots & a_{mn}
\end{pmatrix}
$$

矩阵可以和线性方程组形成一一对应关系

$$
\begin{cases}
 a_{11}x_1 + a_{12}x_2 + \cdots +a_{1n}x_n = b_1 \\
 a_{21}x_1 + a_{22}x_2 + \cdots +a_{2n}x_n = b_2 \\
 \cdots \cdots \cdots \cdots \\
 a_{m1}x_1 + a_{m2}x_2 + \cdots +a_{mn}x_n = b_m
\end{cases}
$$

$$
\begin{pmatrix}
 a_{11} & a_{12} & \cdots & a_{1n} & b_1 \\
 a_{21} & a_{22} & \cdots & a_{2n} & b_2 \\
 \vdots & \vdots &   & \vdots & \vdots \\
 a_{m1} & a_{m2} & \cdots & a_{mn} & b_m
\end{pmatrix}
$$

### 2.1.2 矩阵的运算
1. 矩阵的加法与减法
> 定义2 两个同型矩阵的和, 为各个元素和构成的矩阵

- $A + B = B + A$
- $(A + B)+ C = A + (B + C)$
- $A + O = A$
- $A - B = A + (-B)$

$A, B, C$ 为 $m \times n$矩阵, $O$ 为同型零矩阵

_当 $A = (a_{ij})_{m \times n} , -A = (-a_{ij})_{m \times n}$ , 称为负矩阵_


2. 矩阵的数乘
> 定义3 矩阵 $(\lambda a_{ij})_{m \times n}$ 为数 $\lambda$ 与矩阵 $A$ 的乘积, 简称数乘, 记作 $\lambda A$ , 为各元素与数乘积构成新矩阵

- $(\lambda \mu)A = \lambda (\mu A) = \mu (\lambda A)$
- $\lambda (A + B) = \lambda A + \lambda B$
- $(\lambda + \mu)A = \lambda A + \mu A$

3. 矩阵的乘法
> 定义4 矩阵 $A = (a_{ik})_{m \times s}, B = (b_{kj})_{s \times n}$ , 则 $C = (c_{ij})_{m \times n}$ 为 $A, B$ 乘积, 记作 $C = AB$

矩阵 $AB$ 第 $i$ 行第 $j$ 列元素为 $A$ 的第 $i$ 行与 $B$ 的第 $j$ 列各个元素乘积之和

**一横乘一竖, 对应相乘后相加**

$$
A = 
\begin{pmatrix}
 1 & 0 & 3 \\
 2 & 1 & 0
\end{pmatrix}
, B = 
\begin{pmatrix}
 4 & 1 \\
 -1 & 1 \\
 2 & 0
\end{pmatrix} \\
\\ \
\\ AB = 
\begin{pmatrix}
 1*4+0*(-1)+3*2 & 1*1+0*1+3*0 \\
 2*4+1*(-1)+0*2 & 2*1+1*1+0*0
\end{pmatrix}
=
\begin{pmatrix}
 10 & 1 \\
 7 & 3
\end{pmatrix}
$$

一般地, $AB \ne BA$ , 即矩阵乘法不满足交换律

一般地, $AC = AD$ 时, 不一定有 $C = D$ , 即矩阵乘法不满足消去律

- $(AB)C = A(BC)$
- $A(B + C) = AB + AC$
- $(\lambda A)B = A(\lambda D) = \lambda(AB)$

> 定义5 若 $AB = BA$ , 则称 $A$ 与 $B$ 可交换, 简称 $AB$ 可换

4. 矩阵的转置
> 定义6 将 $m \times n$ 矩阵 $A = (a_{ij})_{m \times n}$ 行列互换后, 得到的 $n \times m$ 矩阵称为 $A$ 的转置, 记作 $A^T$

- $(A^T)^T = A$
- $(A \pm B)^T = A^T \pm B^T$
- $(\lambda A)^T = \lambda A^T$
- $(AB)^T = B^T A^T$

### 2.1.3 方阵
行列数相同的矩阵成为方阵, 行(列)数成为阶数 $n$ , $n$ 阶方阵记作 $A_n$

$A$ 为 $n$ 阶方阵, 可定义乘方运算

$$
A^m = A \cdot A \cdot \cdots \cdot A
$$

显然

$$
A^m \cdot A^l = A^{m + l}, (A^m)^l = A^{ml}
$$

一般地, $(AB)^m \ne A^mB^m$

方阵 $A$ 构成的行列式记作 $\left | A \right |$ 或 $det(A)$ . 若 $\left | A \right | \ne 0$ , 则称 $A$ 为非奇异矩阵

- $\left | \lambda A \right | = \lambda^n \left | A \right |$
- $\left | AB \right | = \left | A \right | \left | B \right |$
- $\left | A^m \right | = \left | A \right |^m$

方阵 $A$ 主对角线元素成为对角元, 对角元全为 $1$ 其余元素全为 $0$ 的 $n$ 阶方阵称 $n$ 阶单位矩阵, 记作 $E_n$ 或 $I_n$ , 即

$$
E_n = 
\begin{pmatrix}
 1 &   &   & 0 \\
  & 1 &   &   \\
  &   & \ddots &   \\
 0 &   &   & 1
\end{pmatrix}
_{n \times n}
$$

对于任意矩阵 $A_{m \times n}$, 有

$$
A_{m \times n}E_n = A_{m \times n} , E_nA_{m \times n} = A_{m \times n}
$$

几个重要方阵

#### 2.1.3.1 对角矩阵

$$
\begin{pmatrix}
 a_{11} &   &   & 0 \\
  & a_{22} &   &   \\
  &   & \ddots &   \\
 0 &   &   & a_{nn}
\end{pmatrix}
$$

简记为 $diag(a_{11}, a_{22}, \cdots , a_{nn})$

若对角线都相等, 成为数量矩阵

**两对角矩阵和或积仍为对角矩阵, 对角元为对应对角元和或积**

#### 2.1.3.2 三角形矩阵
分为上三角和下三角

#### 2.1.3.3 对称矩阵与反称矩阵

$A^T = A$ 的矩阵为对称矩阵, $A^T = -A$的矩阵为反称矩阵

_对称矩阵沿主对角线对称, 反称矩阵沿主对角线成相反数_

**$A + A^T$ 为对称矩阵, $A - A^T$ 为反称矩阵**

**任意矩阵可表示为一个对称矩阵和一个反称矩阵和**

$$
A = \frac{1}{2} (A + A^T) + \frac{1}{2} (A - A^T)
$$

## 2.2 矩阵的初等变换与秩
### 2.2.1 矩阵的初等变换
> 定义1 对矩阵执行下面三种变形, 称为矩阵的初等行变换

- 互换 $i, j$ 两行, 记作 $r_i \leftrightarrow r_j$
- 将第 $i$ 行乘上 $\lambda$ , 记作 $r_i \times \lambda$
- 将第 $j$ 行乘上 $\lambda$ 后加到第 $i$ 行上, 记作 $r_i + \lambda \times r_j$ , 或 $r_i + \lambda r_j$

**若对列执行, 称为矩阵的初等列变换**

**初等行变换和初等列变换统称矩阵的初等变换, $A$ 初等变换为 $B$ , 记作 $A \rightarrow B$**

对 $A$ 进行如下初等行变换, 得到 $B$ , 称为行阶梯形矩阵

$$
A = 
\begin{pmatrix}
 1 & -1 & 1 & 1 & 0 \\
 0 & 1 & 2 & 1 & 1 \\
 -1 & 2 & 1 & 0 & 2 \\
 1 & 0 & 3 & 2 & -1
\end{pmatrix}
\xrightarrow[r_4 - r_1]{r_3 + r_1}
\begin{pmatrix}
 1 & -1 & 1 & 1 & 0 \\
 0 & 1 & 2 & 1 & 1 \\
 0 & 1 & 2 & 1 & 2 \\
 0 & 1 & 2 & 1 & -1
\end{pmatrix}
\xrightarrow[r_3 - r_2]{r_4 + r_2}
\begin{pmatrix}
 1 & -1 & 1 & 1 & 0 \\
 0 & 1 & 2 & 1 & 1 \\
 0 & 0 & 0 & 0 & 1 \\
 0 & 0 & 0 & 0 & -2
\end{pmatrix}
\xrightarrow{r_4 + 2r_3}
\begin{pmatrix}
 1 & -1 & 1 & 1 & 0 \\
 0 & 1 & 2 & 1 & 1 \\
 0 & 0 & 0 & 0 & 1 \\
 0 & 0 & 0 & 0 & 0
\end{pmatrix}
= B
$$

**行阶梯形矩阵**

$$
\begin{pmatrix}
 \star & \star & \cdots & \star & \cdots & \star \\
 \color{#00aaff}{0} & \star & \cdots & \star & \cdots & \star \\
 \vdots & \color{#00aaff}{\vdots} &   & \vdots &   & \vdots \\
 0 & \color{#00aaff}{0} & \color{#00aaff}{\cdots} & \star & \cdots & \star \\
 \vdots & \vdots &   & \color{#00aaff}{\vdots} &   & \vdots \\
 0 & 0 & \cdots & \color{#00aaff}{0} & \color{#00aaff}{\cdots} & \color{#00aaff}{0}
\end{pmatrix}
$$

对 $B$ 再进行初等行变换得到 $C$

$$
B \xrightarrow[r_1 + r_2]{r_2 - r_3}
\begin{pmatrix}
 1 & 0 & 3 & 2 & 0 \\
 0 & 1 & 2 & 1 & 0 \\
 0 & 0 & 0 & 0 & 1 \\
 0 & 0 & 0 & 0 & 0
\end{pmatrix}
= C
$$

**行最简形矩阵**

每一个非零行的非零首元都是 $1$ , 且非零首元所在列的其余元都为 $0$

$$
\begin{pmatrix}
 1 & \color{#00aaff}{0} & 3 & 2 & \color{#00aaff}{0} \\
 0 & 1 & 2 & 1 & \color{#00aaff}{0} \\
 0 & 0 & 0 & 0 & 1 \\
 0 & 0 & 0 & 0 & 0
\end{pmatrix}
$$

对 $C$ 进行初等列变换

$$
C \xrightarrow[c_4 - 2c_1]{c_3 - 3c_1} \xrightarrow[c_4 - c_2]{c_3 - 2c_1}
\begin{pmatrix}
 1 & 0 & 0 & 0 & 0 \\
 0 & 1 & 0 & 0 & 0 \\
 0 & 0 & 0 & 0 & 1 \\
 0 & 0 & 0 & 0 & 0
\end{pmatrix}
\xrightarrow{c_3 \leftrightarrow c_5}
\begin{pmatrix}
 1 & 0 & 0 & 0 & 0 \\
 0 & 1 & 0 & 0 & 0 \\
 0 & 0 & 1 & 0 & 0 \\
 0 & 0 & 0 & 0 & 0
\end{pmatrix}
= D
$$

$D$ 称为 $A$ 的标准型

**标准型**

左上角为一个单位矩阵, 其余元素均为 $0$

$$
D =
\begin{pmatrix}
 \color{#00aaff}{1} & \color{#00aaff}{0} & \color{#00aaff}{\cdots} & \color{#00aaff}{0} & 0 & \cdots & 0 \\
 \color{#00aaff}{0} & \color{#00aaff}{1} & \color{#00aaff}{\cdots} & \color{#00aaff}{0} & 0 & \cdots & 0 \\
 \color{#00aaff}{\vdots} & \color{#00aaff}{\vdots} &   & \color{#00aaff}{\vdots} & \vdots &   & \vdots \\
 \color{#00aaff}{0} & \color{#00aaff}{0} & \color{#00aaff}{\cdots} & \color{#00aaff}{1} & 0 & \cdots & 0 \\
 0 & 0 & \cdots & 0 & 1 & \cdots & 0 \\
 \vdots & \vdots &   & \vdots & \vdots &   & \vdots \\
 0 & 0 & \cdots & 0 & 0 & \cdots & 0
\end{pmatrix}
$$

任何一个矩阵 $A$ 经过有限次初等变换, 都可化为标准型 $D$

### 2.2.2 初等矩阵
> 定义2 由单位矩阵 $E$ 经过一次初等变换得到的矩阵称为初等矩阵

- 互换 $E$ 的第 $i, j$ 行
- 将 $E$ 的第 $i$ 行乘上 $\lambda$
- 将 $E$ 的第 $i$ 行乘上 $\lambda$ 后, 加到第 $j$ 行

记作

$$
P(i, j) = 
\begin{pmatrix}
 1 \\
  & \ddots \\
  &   & 1 \\
  &   &   & 0 &   & \cdots &   & 1 \\
  &   &   &   & \ddots \\
  &   &   & \vdots &   & 1 &   & \vdots \\
  &   &   &   &   &   & \ddots \\
  &   &   & 1 &   & \cdots &   & 0 \\
  &   &   &   &   &   &   &   & 1 \\
  &   &   &   &   &   &   &   &   & \ddots \\
  &   &   &   &   &   &   &   &   &   & 1
\end{pmatrix}
\\ \
\\ P(i(\lambda)) = 
\begin{pmatrix}
 1 \\
  & \ddots \\
  &   & 1 \\
  &   &   & \lambda \\
  &   &   &   & 1 \\
  &   &   &   &   & \ddots \\
  &   &   &   &   &   & 1
\end{pmatrix}
\\ \
\\ P(i. j(\lambda)) = 
\begin{pmatrix}
 1 \\
  & \ddots \\
  &   & 1 & \cdots & \lambda \\
  &   &   & \ddots & \vdots \\
  &   &   &   & 1 \\
  &   &   &   &   & \ddots \\
  &   &   &   &   &   & 1
\end{pmatrix}
$$

**初等矩阵所对应行列式均不为零**

> 定理1 对于$m \times n$ 矩阵 $A$ , 对 $A$ 进行一次初等行变换, 相当于在 $A$ 左边乘一个 $m \times n$的初等矩阵; 对 $A$ 进行一次初等列变换, 相当于在 $A$ 右边乘一个 $n \times n$的初等矩阵

例如

$$
A =
\begin{pmatrix}
 a_{11} & a_{12} & a_{13} \\
 a_{21} & a_{22} & a_{23} \\
 a_{31} & a_{32} & a_{33}
\end{pmatrix}
\xrightarrow{r_1 \leftrightarrow r_2}
\begin{pmatrix}
 a_{21} & a_{22} & a_{23} \\
 a_{11} & a_{12} & a_{13} \\
 a_{31} & a_{32} & a_{33}
\end{pmatrix}
= A_1
$$

相当于

$$
P(1, 2)A = 
\begin{pmatrix}
 0 & 1 & 0 \\
 1 & 0 & 0 \\
 0 & 0 & 1
\end{pmatrix}
\begin{pmatrix}
 a_{11} & a_{12} & a_{13} \\
 a_{21} & a_{22} & a_{23} \\
 a_{31} & a_{32} & a_{33}
\end{pmatrix}
=
\begin{pmatrix}
 a_{21} & a_{22} & a_{23} \\
 a_{11} & a_{12} & a_{13} \\
 a_{31} & a_{32} & a_{33}
\end{pmatrix}
= A_1
$$

**若 $B$ 由 $A$ 有限次初等变换得到, 则有**

$$
B = P_tP_{t-1} \cdots P_1AQ_1Q_2 \cdots Q_l
$$

### 2.2.3 矩阵的等价
> 定义3 若 $A$ 经有限次初等变换得到 $B$ , 则称 $A, B$ 等价, 记作 $A \approx B$ 或 $A \cong B$

矩阵等价关系基本性质
- 自反性 $A \approx A$
- 对称性 若 $A \approx B$ , 则 $B \approx A$
- 传递性 若 $A \approx B, B \approx C$ , 则 $A \approx C$

> 定理2 $A, B$ 等价的充要条件为 $A, B$ 有相同的标准形

### 2.2.4 矩阵的秩
> 定义4 设 $A$ 为 $m \times n$ 矩阵, 在 $A$ 中任取 $k$ 行 $k$ 列, 由这 $k$ 行 $k$ 列交叉处的 $k^2$ 个元素构成的 $k$ 阶行列式称为矩阵 $A$ 的一个 $k$ 阶子式

> 定义5 $A$ 中不为零的子式最高阶数称为矩阵 $A$ 的秩, 记作 $r(A)$

_零矩阵的秩为零_

_非奇异方阵 $A$ 的秩等于它的阶数 $(\because \left | A \right | \ne 0)$ , 故非奇异方阵又称满秩方阵, 奇异方阵又称降秩方阵_

> 定理3 若 $A$ 中有一个 $k$ 阶子式不为零, 而所有 $k + 1$ 阶子式全为零, 则 $r(A) = k$

- $r(A) = 0$ 充要条件为 $A = O$
- $0 \le r(A_{m \times n}) \le min \left \{ m, n \right \}$
- 若 $A$ 中有一个 $k$ 阶子式不为零, 则 $r(A) \ge k$
- $r(A^T) = r(A), r(kA) = r(A)$
- 若 $r(A) = r$ , 则 $A$ 中任何阶数高于 $r$ 的子式全为零

> 定理4 对矩阵进行初等变换后, 矩阵的秩不便, 即若 $A \approx B$ , 则 $ r(A) = r(B)$

例, 求下列矩阵的秩

$$
A = 
\begin{pmatrix}
 1 & -2 & -1 & 0 & 2 \\
 -2 & 4 & 2 & 6 & -6 \\
 2 & -1 & 0 & 2 & 3 \\
 3 & 3 & 3 & 3 & 4
\end{pmatrix}
\xrightarrow[r_3 - 2r_1]{r_2 + 2r_1}
\xrightarrow[r_2 \leftrightarrow r_3]{r_4 - 3r_1}
\xrightarrow[r_3 - 3r_2]{r_3 \leftrightarrow r_4}
\xrightarrow{r_4 + 2r_3}
\begin{pmatrix}
 1 & -2 & -1 & 0 & 2 \\
 0 & 3 & 2 & 2 & -1 \\
 0 & 0 & 0 & -3 & 1 \\
 0 & 0 & 0 & 0 & 0
\end{pmatrix}
= B
$$

又

$$
\begin{vmatrix}
 1 & -2 & 0 \\
 0 & 3 & 2 \\
 0 & 0 & -3
\end{vmatrix}
= -9
$$

易得 $r(B) = 3$ , 则 $r(A) = 3$

> 定理5 等价矩阵具有相同的秩

> 推论1 矩阵 $A$ 经过有限次初等行变换 $P_1, P_2, \cdots , P_s$ 变为矩阵 $B$ , 则

$$
r(B) = r(P_sP_{s - 1} \cdots P_1A) = r(A)
$$

> 推论2 矩阵 $A$ 经过有限次初等列变换 $Q_1, Q_2, \cdots , Q_t$ 变为矩阵 $B$ , 则

$$
r(B) = r(AQ_1Q_2 \cdots Q_t) = r(A)
$$

> 推论3 矩阵 $A$ 经过有限次初等行变换 $P_1, P_2, \cdots , P_s$ 及有限次初等列变换 $Q_1, Q_2, \cdots , Q_t$ 变为矩阵 $B$ , 则

$$
r(B) = r(P_sP_{s - 1} \cdots P_1AQ_1Q_2 \cdots Q_t) = r(A)
$$

## 2.3 逆矩阵
### 2.3.1 逆矩阵的定义及性质
> 定义1 设 $A$ 为 $n$ 阶方阵, $E$ 为 $n$ 阶单位矩阵, 若存在 $n$ 阶方阵 $B$ , 使

$$
AB = BA = E
$$

则称矩阵 $A$ 可逆, 称 $B$ 为 $A$ 的逆矩阵

> 定理1 若矩阵可逆, 则逆矩阵唯一

- $(A^{-1})^{-1} = A$
- $(\lambda A)^{-1} = \frac{1}{\lambda} A^{-1}$
- $(A^T)^{-1} = (A^{-1})^T$
- $(AB)^{-1} = B^{-1}A^{-1}$
- $\left | A^{-1} \right | = \frac{1}{\left | A \right |} = \left | A \right | ^{-1}$

推论

- $(A_1A_2 \cdots A_m)^{-1} = A_m^{-1} \cdots A_2^{-1}A_1^{-1}$
- $(A^m)^{-1} = (A^{-1})^m$
- 若矩阵可逆, 则其逆矩阵也是对称矩阵

$$
A = A^T \Rightarrow
A^{-1} = (A^T)^{-1} = (A^{-1})^T
$$

### 2.3.2 矩阵可逆的条件
> 定义2 设 $n$ 阶方阵

$$
A = 
\begin{pmatrix}
 a_{11} & a_{12} & \cdots & a_{1n} \\
 a_{21} & a_{22} & \cdots & a_{2n} \\
 \vdots & \vdots &   & \vdots \\
 a_{n1} & a_{n2} & \cdots & a_{nn}
\end{pmatrix}
$$ 

$A_{ij}$ 为行列式 $\left | A \right |$ 中元素 $a_{ij}$ 的代数余子式, 则矩阵

$$
A^{\star} = 
\begin{pmatrix}
 A_{11} & A_{12} & \cdots & A_{1n} \\
 A_{21} & A_{22} & \cdots & A_{2n} \\
 \vdots & \vdots &   & \vdots \\
 A_{n1} & A_{n2} & \cdots & A_{nn}
\end{pmatrix}
$$

称为 $A$ 的伴随矩阵, 即当 $A = (a_{ij})$ 时, $A^{\star} = (a_{ij})^T$

**方阵 $A = (a_{ij})_{n \times n}$ 可逆的充要条件是 $\left | A \right | \ne 0$**

**方阵 $A = (a_{ij})_{n \times n}$ 可逆, 有 $A^{-1} = \frac{1}{\left | A \right |} A^{\star}$**

### 2.3.3 用初等变换求逆矩阵
> 定理4 初等变换有如下性质

- $P(i, j)^{-1} = P(i, j), \left | P(i, j) \right | = -1$
- $P(i(\lambda))^{-1} = P(i(\lambda ^{-1})), \left | P(i(\lambda)) \right | = \lambda$
- $P(i, j(\lambda))^{-1} = P(i, j(- \lambda)), \left | P(i, j(\lambda)) \right | = 1$

**初等矩阵的逆矩阵也为初等矩阵**

> 定理5 若 $n$ 阶方阵 $A$ 可逆, 则存在有限个初等矩阵 $P_1, P_2, \cdots , P_m$ , 使

$$
A = P_1P_2 \cdots P_m
$$

求逆矩阵

$$
(A | E) \xrightarrow{初等行变换} (E | A^{-1})
$$

或

$$
(\frac{A}{E}) \xrightarrow{初等列变换} (\frac{E}{A^{-1}})
$$

例如

$$
\begin{aligned}
 & A =
 \begin{pmatrix}
  2 & 2 & 3 \\
  1 & -1 & 0 \\
  -1 & 2 & 1
 \end{pmatrix}
 \\
 & \\
 & (A | E) = 
 \begin{pmatrix}
  2 & 2 & 3 & | & 1 & 0 & 0 \\
  1 & -1 & 0 & | & 0 & 1 & 0 \\
  -1 & 2 & 1 & | & 0 & 0 & 1
 \end{pmatrix}
 \rightarrow
 \begin{pmatrix}
  1 & 0 & 0 & | & 1 & -4 & -3 \\
  0 & 1 & 0 & | & 1 & -5 & -3 \\
  0 & 0 & 1 & | & -1 & 6 & 4
 \end{pmatrix}
 \\
 & \\
 & A^{-1} = 
 \begin{pmatrix}
  1 & -4 & -3 \\
  1 & -5 & -3 \\
  -1 & 6 & 4
 \end{pmatrix}

\end{aligned}
$$

### 2.3.4 逆矩阵的简单应用
#### 2.3.4.1 解方程组

**设 $n$ 个方程 $n$ 个未知量构成的线性方程组矩阵表示为 $AX = b$ , 若 $A$ 可逆, 则方程组解为 $X = A^{-1}b$**

例如

$$
\begin{cases}
 2x_1 + 2x_2 + 3x_3 = 1 \\
 x_1 - x_2 = -1 \\
 -x_1 + 2x_2 + x_3 = 3
\end{cases}
$$

化为 $AX = b$

$$
\begin{aligned}
 & A =
 \begin{pmatrix}
  2 & 2 & 3 \\
  1 & -1 & 0 \\
  -1 & 2 & 1
 \end{pmatrix}
 , \ X = 
 \begin{pmatrix}
  x_1 \\
  x_2 \\
  x_3
 \end{pmatrix}
 , \ b = 
 \begin{pmatrix}
  1 \\
  -1 \\
  3
 \end{pmatrix}
 \\
 & \\
 & A^{-1} = 
 \begin{pmatrix}
  1 & -4 & -3 \\
  1 & -5 & -3 \\
  -1 & 6 & 4
 \end{pmatrix}
 , \ X = A^{-1}b = 
 \begin{pmatrix}
  -4 \\
  -3 \\
  5
 \end{pmatrix}
\end{aligned}
$$

即 $x_1 = -4, x_2 = -3, x_3 = 5$

#### 2.3.4.2 解矩阵方程

_( $A$ 矩阵可逆)_

- 若 $AX = B$ , 则 $X = A^{-1}B$
- 若 $XA = B$ , 则 $X = BA^{-1}$
- 若 $AX = AB$ , 或 $XA = BA$ , 则 $X = B$

例如

$A, B$ 为三阶矩阵, $E$ 为三阶单位矩阵, 且 $AB + E = A^2 + B$ , $A = \begin{pmatrix}1 & 0 & 1 \\ 0 & 2 & 0 \\ -1 & 0 & 1 \end{pmatrix}$ , 求 $B$

$$
\begin{aligned}
 & AB + E = A^2 + B \Rightarrow AB - B = A^2 - E, \ 
 \Rightarrow (A - E)B = (A - E)(A + E) \\
 & A - E = 
 \begin{pmatrix}
  0 & 0 & 1 \\
  0 & 1 & 0 \\
  -1 & 0 & 0
 \end{pmatrix}
 , \ 
 \left | A - E \right | = 1 \ne 0, \ 即 A - E 可逆 \\
 & B = A + E = 
 \begin{pmatrix}
  2 & 0 & 1 \\
  0 & 3 & 0 \\
  -1 & 0 & 2
 \end{pmatrix}
\end{aligned}
$$

## 2.4 分块矩阵
### 2.4.1 矩阵的分块

$$
A = 
\begin{pmatrix}
 \color{#00aaff}{1} & \color{#00aaff}{2} & 4 & 1 \\
 3 & 0 & \color{#00aaff}{5} & \color{#00aaff}{7} \\
 -1 & 2 & \color{#00aaff}{0} & \color{#00aaff}{1}
\end{pmatrix}
=
\begin{pmatrix}
 \color{#00aaff}{A_{11}} & A_{12} \\
 A_{21} & \color{#00aaff}{A_{22}}
\end{pmatrix}
$$

其中 $A_{11} = \begin{pmatrix} 1 & 2 \end{pmatrix}, \ A_{12} = \begin{pmatrix} 4 & 1 \end{pmatrix}, \ 
 A_{21} = \begin{pmatrix} 3 & 0 \\ -1 & 2 \end{pmatrix} , \ A_{22} = \begin{pmatrix} 5 & 7 \\ 0 & 1 \end{pmatrix}$
 为分块矩阵 $A$ 的子块

### 2.4.2 分块矩阵的计算
#### 2.4.2.1 计算 $A \pm B$ 时, 要将 $A, B$ 用同样分块方式进行分块, 保证子块同型
#### 2.4.2.2 计算 $AB$ 时, 对 $A$ 列的分法应与对 $B$ 行分法一致, 保证子块能相乘

设 $A = (a_{ik})_{s \times n}, \ B = (b_{kj})_{n \times m}$ , 分块如下

$$
A = 
\begin{pmatrix}
 A_{11} & A_{12} & \cdots & A_{1l} \\
 A_{21} & A_{22} & \cdots & A_{2l} \\
 \vdots & \vdots &   & \vdots \\
 A_{t1} & A_{t2} & \cdots & A_{tl}
\end{pmatrix}
\\ \
\\
B = 
\begin{pmatrix}
 B_{11} & B_{12} & \cdots & B_{1r} \\
 B_{21} & B_{22} & \cdots & B_{2r} \\
 \vdots & \vdots &   & \vdots \\
 B_{l1} & B_{l2} & \cdots & B_{lr}
\end{pmatrix}
$$

其中每个小矩阵 $A_{ij}$ 为 $s_i \times \color{#00aaff}{n_j}$ 矩阵, 
每个小矩阵 $B_{ij}$ 为 $\textcolor{#00aaff}{n_i} \times m_j$ 矩阵

则

$$
C = AB = 
\begin{pmatrix}
 C_{11} & C_{12} & \cdots & C_{1r} \\
 C_{21} & C_{22} & \cdots & C_{2r} \\
 \vdots & \vdots &   & \vdots \\
 C_{t1} & C_{t2} & \cdots & C_{tr}
\end{pmatrix}
$$

其中

$$
C_{pq} = A_{p1}B_{1q} + A_{p2}{2q} + \cdots + A_{pl}{lq} \\
= \sum_{k = 1}^{l} A_{pk}B_{kq} \ (p = 1, 2, \cdots , t; q = 1, 2, \cdots , r)
$$

#### 2.4.2.3 求 $A^T$ 时, 将子块作为元素转置后, 再将各子块转置

$$
\begin{pmatrix}
 A_{11} & A_{12} & A_{13} \\
 A_{21} & A_{22} & A_{23}
\end{pmatrix}
=
\begin{pmatrix}
 A_{11}^T & A_{21}^T \\
 A_{12}^T & A_{22}^T \\
 A_{13}^T & A_{23}^T
\end{pmatrix}
$$

若方阵 $A$ 分块后得到如下形式

$$
AB = 
\begin{pmatrix}
 A_1 & O & \cdots & O \\
 O & A_2 & \cdots & O \\
 \vdots & \vdots &   & \vdots \\
 O & O & \cdots & A_m
\end{pmatrix}
$$

其中 $A_i (i = 1, 2, \cdots , m)$ 均为方阵, 称 $A$ 为准对角矩阵

例如

$$
A = 
\begin{pmatrix}
 \color{#00aaff}{1} & \color{#00aaff}{2} & 0 & 0 & 0 \\
 \color{#00aaff}{3} & \color{#00aaff}{4} & 0 & 0 & 0 \\
 0 & 0 & \color{#00aaff}{-1} & \color{#00aaff}{3} & 0 \\
 0 & 0 & \color{#00aaff}{2} & \color{#00aaff}{0} & 0 \\
 0 & 0 & 0 & 0 & \color{#00aaff}{1}
\end{pmatrix}
=
\begin{pmatrix}
 A_1 \\
  & A_2 \\
  &   & A_3
\end{pmatrix}
$$

为准对角矩阵

**准对角矩阵有着类似对角矩阵性质**

$$
A^k =
\begin{pmatrix}
 A_1^k \\
  & A_2^k \\
  &   & A_3^k
\end{pmatrix}
$$

**若方阵 $A_1, A_2, \cdots , A_m$ 均可逆, 则有**

$$
\begin{pmatrix}
 A_1 \\
  & A_2 \\
  &   & \ddots \\
  &   &   & A_m
\end{pmatrix}
$$

有逆矩阵, 且

$$
\begin{pmatrix}
 A_1 \\
  & A_2 \\
  &   & \ddots \\
  &   &   & A_m
\end{pmatrix}^{-1}
= 
\begin{pmatrix}
 A_1^{-1} \\
  & A_2^{-1} \\
  &   & \ddots \\
  &   &   & A_m^{-1}
\end{pmatrix}
$$

例 求下面矩阵的逆矩阵

$$
D = 
\begin{pmatrix}
 a_{11} & \cdots & a_{1n} & 0 & \cdots & 0 \\
 \vdots &   & \vdots & \vdots &   & \vdots \\
 a_{n1} & \cdots & a_{nn} & 0 & \cdots & 0 \\
 c_{11} & \cdots & c_{1n} & b_{11} & \cdots & b_{1m} \\
 \vdots &   & \vdots & \vdots &   & \vdots \\
 c_{m1} & \cdots & c_{mn} & b_{m1} & \cdots & b_{mm}
\end{pmatrix}
=
\begin{pmatrix}
 A & O \\
 C & B
\end{pmatrix}
$$

解

$$
\begin{aligned}
 & \left | D \right | = \left | A \right | \left | B \right |
 \Rightarrow A, B可逆, 则D可逆 \\
 & 设D^{-1} =
 \begin{pmatrix}
  X_{11} & X_{12} \\
  X_{21} & X_{22}
 \end{pmatrix} \\
 & \ \\
 & 则
 \begin{pmatrix}
  A & O \\
  C & B
 \end{pmatrix}
 \begin{pmatrix}
  X_{11} & X_{12} \\
  X_{21} & X_{22}
 \end{pmatrix}
 =
 \begin{pmatrix}
  E_n & O \\
  O & E_m
 \end{pmatrix} \\
 & 乘开得
 \begin{cases}
  AX_{11} = E_n \\
  AX_{12} = O \\
  CX_{11} + BX_{21} = O \\
  CX_{12} + BX_{22} = E_m
 \end{cases} \\
 & 由一二个方程得 \ X_{11} = A^{-1}, X_{12} = O \\
 & 代入四得 \ X_{22} = B^{-1} \\
 & 代入三得 \ X_{21} = -B^{-1}CX_{11} = -B^{-1}CA^{-1} \\
 & \ \\
 & 则 \ D^{-1} = 
 \begin{pmatrix}
  A^{-1} & O \\
  -B^{-1}CA^{-1} & B^{-1}
 \end{pmatrix}
\end{aligned}
$$

## 2.5 矩阵理论在经济学中的应用

**投入产出分析**

任何国家或地区的经济可以划分成多个部门, 每个部门有双重身份

- 作为生产者将自己的总产出分配给各个部门作为生产资料
- 为进行生产需要消耗其他部门的产品和无知作为投入

现考虑三个部门之间的投入产出情况, 设 $C_1, C_2, C_3$ 三个部门,

- $C_1$ 生产一个单位产品需消耗 $0.2$ 个单位 $C_1$ 部门产品, $0.4$ 个单位 $C_2$ 部门产品, $0.1$ 个单位 $C_3$ 部门产品, 
- $C_2$ 生产一个单位产品需消耗 $0.3$ 个单位 $C_1$ 部门产品, $0.1$ 个单位 $C_2$ 部门产品, $0.3$ 个单位 $C_3$ 部门产品
- $C_3$ 生产一个单位产品需消耗 $0.2$ 个单位 $C_1$ 部门产品, $0.2$ 个单位 $C_2$ 部门产品, $0.2$ 个单位 $C_3$ 部门产品

现假设 $C_1, C_2, C_3$ 哥哥们最终产品需求分别为 $d_1, d_2, d_3$ 个单位, 需计算各部门总产出 $x_1, x_2, x_3$ , 使得供需平衡

对于 $C_1$ , 总产出等于最终产出加上各部门消耗 $C_1$ 部门的产品数, 即

$$
x_1 = d_1 + 0.2 x_1 + 0.3 x_2 + 0.2 x_3
$$

同理

$$
x_2 = d_2 + 0.4 x_1 + 0.1 x_2 + 0.2 x_3 \\
x_3 = d_3 + 0.1 x_1 + 0.3 x_2 + 0.2 x_3
$$

则有

$$
\begin{aligned}
 & X = \begin{pmatrix} x_1 \\ x_2 \\ x_3 \end{pmatrix} \ , \
 d = \begin{pmatrix} d_1 \\ d_2 \\d_3 \end{pmatrix} \ , \
 A = \begin{pmatrix}
  0.2 & 0.3 & 0.2 \\
  0.4 & 0.1 & 0.2 \\
  0.1 & 0.3 & 0.2
 \end{pmatrix} \\
 & \ \\
 & X = d + AX \\
 & 即 \ (E - A)X = d \\
 & \ \\
 & 计算得, (E - A)可逆, 且 \ (E - A)^{-1} = \begin{pmatrix}
  1.72 & 0.78 & 0.63 \\
  0.89 & 1.61 & 0.63 \\
  0.55 & 0.70 & 1.56
 \end{pmatrix} \\
 & 则线性方程组有唯一解 \\
 & \ \\
 & X = (E - A)^{-1}d = \begin{pmatrix}
  1.72 & 0.78 & 0.63 \\
  0.89 & 1.61 & 0.63 \\
  0.55 & 0.70 & 1.56
 \end{pmatrix}
 \begin{pmatrix} d_1 \\ d_2 \\d_3 \end{pmatrix} \\
 & \ \\
 & 即 \begin{cases}
  x_1 = 1.72 d_1 + 0.78 d_2 + 0.63 d_3 \\
  x_2 = 0.89 d_1 + 1.61 d_2 + 0.63 d_3 \\
  x_3 = 0.55 d_1 + 0.70 d_2 + 1.56 d_3
 \end{cases}
\end{aligned}
$$

若由 $n$ 个部门 $C_1, C_2, \cdots , C_n$ ,
假设 $C_i$ 部门生产一个单位产品需要消耗 $C_1, C_2, \cdots , C_n$ 各部门产品数分别为
$a_{i1}, a_{i2}, \cdots , a_{in}$ , $C_i$ 部门的产品需求量为 $d_i$ ,
$C_i$ 部门总产出为 $x_i \ (i = 1, 2, \cdots , n)$

则

$$
x_i = d_i + a_{i1} x_1 + a_{i2} x_2 + \cdots + a_{in} x_n \ , \ \ i = 1, 2, \cdots , n
$$

记

$$
X = \begin{pmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{pmatrix} \ , \
d = \begin{pmatrix} d_1 \\ d_2 \\ \vdots \\ d_n \end{pmatrix} \ , \
A = \begin{pmatrix}
 a_{11} & a_{12} & \cdots & a_{1n} \\
 a_{21} & a_{22} & \cdots & a_{2n} \\
 \vdots & \vdots &   & \vdots \\
 a_{n1} & a_{n2} & \cdots & a_{nn}
\end{pmatrix}
$$

则方程组用矩阵表示为

$$
X = d + AX
$$

_$A$ 称为直接消耗系数矩阵_

变形得

$$
(E - A)X = d
$$

_称为投入产出公式, $E - A$ 称为列昂惕夫矩阵_

实际问题中, 列昂惕夫矩阵一般是非奇异的, 它的逆矩阵 $(E - A)^{-1}$ 称为列昂惕夫逆矩阵, 用 $R$ 表示


投入产出公式变形为

$$
X = Rd
$$

利用列昂惕夫逆矩阵, 任何已知的 可预测的的最终产品需求代入上式, 可以确定各部门相应的总产出水平

各种最终需求量变化时, 对各部门的影响也可求

例如, 给 $d$ 以增量 $\Delta d$ , 则

$$
X + \Delta X = R(d + \Delta d) = Rd + R \Delta d = X + R \Delta d
$$

即

$$
\Delta X = R \Delta d
$$

对于前例, 列昂惕夫逆矩阵

$$
R = \begin{pmatrix}
 1.72 & 0.78 & 0.63 \\
 0.89 & 1.61 & 0.63 \\
 0.55 & 0.70 & 1.56
\end{pmatrix}
$$

设 $\Delta d = (0, 0, 10)^T$ , 则

$$
\Delta X = R \Delta d = \begin{pmatrix}
 1.72 & 0.78 & 0.63 \\
 0.89 & 1.61 & 0.63 \\
 0.55 & 0.70 & 1.56
\end{pmatrix}
\begin{pmatrix} 0 \\ 0 \\ 10 \end{pmatrix}
= \begin{pmatrix} 6.3 \\ 6.3 \\ 15.6 \end{pmatrix}
$$

即

$$
\Delta x_1 = 6.3 \ , \ \ \Delta x_2 = 6.3 \ , \ \ \Delta x_3 = 15.6
$$


则方程组用矩阵表示为

$$
X = d + AX
$$

_$A$ 称为直接消耗系数矩阵_

变形得

$$
(E - A)X = d
$$

_称为投入产出公式, $E - A$ 称为列昂惕夫矩阵_

实际问题中, 列昂惕夫矩阵一般是非奇异的, 它的逆矩阵 $(E - A)^{-1}$ 称为列昂惕夫逆矩阵, 用 $R$ 表示


投入产出公式变形为

$$
X = Rd
$$

利用列昂惕夫逆矩阵, 任何已知的 可预测的的最终产品需求代入上式, 可以确定各部门相应的总产出水平

各种最终需求量变化时, 对各部门的影响也可求

例如, 给 $d$ 以增量 $\Delta d$ , 则

$$
X + \Delta X = R(d + \Delta d) = Rd + R \Delta d = X + R \Delta d
$$

即

$$
\Delta X = R \Delta d
$$

对于前例, 列昂惕夫逆矩阵

$$
R = \begin{pmatrix}
 1.72 & 0.78 & 0.63 \\
 0.89 & 1.61 & 0.63 \\
 0.55 & 0.70 & 1.56
\end{pmatrix}
$$

设 $\Delta d = (0, 0, 10)^T$ , 则

$$
\Delta X = R \Delta d = \begin{pmatrix}
 1.72 & 0.78 & 0.63 \\
 0.89 & 1.61 & 0.63 \\
 0.55 & 0.70 & 1.56
\end{pmatrix}
\begin{pmatrix} 0 \\ 0 \\ 10 \end{pmatrix}
= \begin{pmatrix} 6.3 \\ 6.3 \\ 15.6 \end{pmatrix}
$$

即

$$
\Delta x_1 = 6.3 \ , \ \ \Delta x_2 = 6.3 \ , \ \ \Delta x_3 = 15.6
$$
