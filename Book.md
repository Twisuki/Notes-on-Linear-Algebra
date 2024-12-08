# 线性代数学习笔记完整版

# 1 行列式
## 1.1 方程组与行列式
### 1.1.1 二元线性方程组和二阶行列式
### 1.1.2 三元线性方程组和三阶行列式
## 1.2 $n$ 阶行列式
### 1.2.1 排序与逆序数
### 1.2.2 $n$ 阶行列式

$$
\begin{vmatrix}
 a_{11} & a_{12} & \cdots & a_{1n} \\
 a_{21} & a_{22} & \cdots & a_{2n} \\
 \vdots & \vdots &   & \vdots \\
 a_{n1} & a_{n2} & \cdots & a_{nn}
\end{vmatrix}
= \sum_{(j_1j_2 \cdots j_n)} (-1)^{\tau (j_1j_2 \cdots j_n)}
a_{1j_1}a_{2j_2} \cdots a_{nj_n}
$$

_每次计算, 每组每行取一个, 且每行不重复_

例如：

$$
\begin{vmatrix}
 a_{11} & \color{#00aaff}{a_{12}} & a_{13}  & a_{14} \\
 a_{21} & a_{22} & a_{23}  & \color{#00aaff}{a_{24}} \\
 \color{#00aaff}{a_{31}}  & a_{32}  & a_{33} & a{34} \\
 a_{41} & a_{42} & \color{#00aaff}{a_{43}} & a_{44}
\end{vmatrix}
$$

则某一项为

$$
\color{#00aaff}{a_{12}a_{24}a_{31}a_{43}}
$$

判断符号为(按行 $1234$ ) $\tau (2413) = 3$

或(按列 $1234$ ) $\tau (3142) = 3$

## 1.3 行列式的性质和计算
### 1.3.1 行列式的性质
> 性质1 $n$ 阶行列式行列互换, 值不变, 记作 $D = D^T$

> 性质2 互换两行, 行列式变号, 记作 $r_i \leftrightarrow r_j$

> 性质3 某行同乘 $k$ , 行列式乘 $k$

> 性质4 行列式某行各元素为两数之和, 行列式等于两行列式之和

$$
\begin{vmatrix}
 a_{11} & a_{12} & \cdots & a_{1n} \\
 \vdots & \vdots &   & \vdots \\
 a_{i1} + a'_{i1} & a_{i2} + a'_{i2} & \cdots & a_{in} + a'_{in} \\
 \vdots & \vdots &   & \vdots \\
 a_{n1} & a_{n2} & \cdots & a_{nn}
\end{vmatrix}
=
\begin{vmatrix}
 a_{11} & a_{12} & \cdots & a_{1n} \\
 \vdots & \vdots &   & \vdots \\
 a_{i1} & a_{i2} & \cdots & a_{in} \\
 \vdots & \vdots &   & \vdots \\
 a_{n1} & a_{n2} & \cdots & a_{nn}
\end{vmatrix}
+
\begin{vmatrix}
 a_{11} & a_{12} & \cdots & a_{1n} \\
 \vdots & \vdots &   & \vdots \\
 a'_{i1} & a'_{i2} & \cdots & a'_{in} \\
 \vdots & \vdots &   & \vdots \\
 a_{n1} & a_{n2} & \cdots & a_{nn}
\end{vmatrix}
$$

> 性质5 某行乘 $k$ 加到另一行, 值不变, 记作 $r_i + kr_j$

**对于列, 则将 $r$ 换为 $c$**

> 推论1 某两行对应相等, 行列式为零

> 推论2 某两行成比例, 行列式为零

> 推论3 某行全为零, 行列式为零

### 1.3.2 行列式的计算

_化为上三角_

- 保证主对角线没有零
- $r_n - kr_1$ , 使 $r_n$ 首项为零 $(n > 1)$
- $r_n - kr_2$ , 使 $r_n$ 第二项为零 $(n > 2)$
- $\cdots$
- 成为上三角后, 计算主对角线元素乘积
  
## 1.4 行列式按行展开
### 1.4.1 拉普拉斯展开定理

> 定义1 行列式中划去 $a_{ij}$ 所在行列, 剩下元素构成的行列式称 $a_{ij}$ 的余子式, 记作 $M_{ij}$ ; 余子式加上代数符号 $(-1)^{i + j}$ 称为代数余子式, 记作 $A_{ij}$ , 即 $A_{ij} = (-1)^{i + j} M_{ij}$

> 定理1 (拉普拉斯展开定理)行列式等于其任一行各元素与其代数余子式乘积之和

即

$$
D = \sum_{k = 1}^{n} a_{ik}A_{ik}, i = 1, 2, \cdots ,n
$$

> 定理2 行列式任一行各元素与另一行对应元素代数余子式乘积之和为零

即

$$
\sum_{k = 1}^{n} a_{ik}A_{jk} = 0 \\
i \ne j, i = 1, 2, \cdots , n
$$

### 1.4.2 拉普拉斯展开定理应用

> 范德蒙德行列式

$$
D_n = 
\begin{vmatrix}
 1 & 1 & \cdots & 1 \\
 x_1 & x_2 & \cdots & x_n \\
 x_1^2 & x_2^2 & \cdots & x_n^2 \\
 \vdots & \vdots &   & \vdots \\
 x_1^{n - 1} & x_2^{n - 1} & \cdots & x_n^{n - 1}
\end{vmatrix}
= \prod_{1 \le j < i \le n}
(x_i - x_j)
$$

## 1.5 克拉默法则

> 定理1 (克拉默法则)

$n$ 个方程的 $n$ 元方程组

$$
\begin{cases}
 a_{11}x_1 + a_{12}x_2 + \cdots +a_{1n}x_n = b_1 \\
 a_{21}x_1 + a_{22}x_2 + \cdots +a_{2n}x_n = b_2 \\
 \cdots \cdots \cdots \cdots \\
 a_{n1}x_1 + a_{n2}x_2 + \cdots +a_{nn}x_n = b_n
\end{cases}
$$

若其系数行列式

$$
D =
\begin{vmatrix}
 a_{11} & a_{12} & \cdots & a_{1n} \\
 a_{21} & a_{22} & \cdots & a_{2n} \\
 \vdots & \vdots &   & \vdots \\
 a_{n1} & a_{n2} & \cdots & a_{nn}
\end{vmatrix}
\ne 0
$$

则线性方程组有唯一解
记作

$$
x_1 = \frac{D_1}{D} , x_2 = \frac{D_2}{D} , \cdots , x_n = \frac{D_n}{D}
$$

其中 $D_j(j = 1, 2, \cdots , n)$ 为用常数项 $b_1, b_2, \cdots , b_n$ 代替 $D$ 中 $j$ 列对应元素所得行列式

即

$$
D_j = 
\begin{vmatrix}
 a_{11} & \cdots & a_{1, j - 1} & b_1 & a_{1, j + 1} & \cdots & a_{1n} \\
 \vdots &   & \vdots & \vdots & \vdots &   & \vdots \\
 a_{n1} & \cdots & a_{n, j - 1} & b_n & a_{n, j + 1} & \cdots & a_{nn}
\end{vmatrix}
$$

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

# 3 向量空间
## 3.1 向量
### 3.1.1 $n$ 维向量及其线性运算

> 定义1 由 $n$ 个数组成的有序数组 $(a_1, a_2, \cdots , a_n)$ 称为一个 $n$ 维向量, 记作

$$
\alpha = (a_1, a_2, \cdots , a_n)
$$

其中数 $a_i(i = 1, 2, \cdots , n)$ 称为向量 $\alpha$ 的第 $i$ 个分量或第 $i$ 个坐标

有时 $n$ 维向量也可写成一列的形式, 即

$$
\alpha = 
\begin{pmatrix}
 a_1 \\ a_2 \\ \vdots \\ a_n
\end{pmatrix}
$$

_上述两种向量分别称为行向量和列向量, 列向量为也记作 $\alpha = (a_1, a_2, \cdots , a_n)^T$_

$n$ 维向量可视为 $1 \times n$ 或 $n \times 1$ 的矩阵, 则对于 $n \times m$ 矩阵 $A = (a_{ij})_{n \times m}$

$$
A = (\alpha_1, \alpha_2, \cdots , \alpha_m) = 
\begin{pmatrix}
 \beta_1 \\ \beta_2 \\ \vdots \\ \beta_n
\end{pmatrix}
$$

其中 $\alpha_j = (a_{1j}, a_{2j}, \cdots , a_{nj})^T \ (j = 1, 2, \cdots , m)$ 为 $n$ 维列向量, 
$\beta_i = (a_{i1}, a_{i2}, \cdots , a_{im}) \ (i = 1, 2, \cdots , n)$ 为 $m$ 维行向量

**若两个 $n$ 维向量对应分量都相等, 则向量相等**

$$
\begin{aligned}
 & \alpha = (a_1, a_2, \cdots , a_n) \ , \ \beta = (b_1, b_2, \cdots , b_n) \\
 & a_i = b_i \ , \ i = 1, 2, \cdots , n \\
 & 则 \ \alpha = \beta
\end{aligned}
$$

**分量均为零的向量为零向量, 记作 $\mathbf{0}$ , 即 $\mathbf{0} = (0, 0, \cdots , 0)$**

**向量 $(-a_1, -a_2, \cdots , -a_n)$ 称为向量 $(a_1, a_2, \cdots , a_n)$ 的负向量, 记作 $-\alpha$**

> 定义2 向量加法与数乘

两个 $n$ 维向量

$$
\alpha = (a_1, a_2, \cdots , a_n) \ , \ \beta = (b_1, b_2, \cdots , b_n)
$$

则有

$$
\begin{align}
 & \alpha + \beta = (a_1 + b_1, a_2 + b_2, \cdots , a_n + b_n) \\
 & \alpha - \beta = \alpha + (-\beta) = (a_1 - b_1, a_2 - b_2, \cdots , a_n - b_n)
\end{align}
$$

- $\alpha + \beta = \beta + \alpha$ _加法交换律_
- $(\alpha + \beta) + \gamma = \alpha + (\beta + \gamma)$ _加法结合律_
- $\alpha + \mathbf{0} + \alpha$
- $\alpha + (-\alpha) = \mathbf{0}$
- $1 \alpha = \alpha$
- $k(l \alpha) = (kl) \alpha$ _数乘结合律_
- $k(\alpha + \beta) = k \alpha + k \beta$ _数乘对加法的分配律_
- $(k + l) \alpha = k \alpha + l \alpha$

$$

$$

- $k \mathbf{0} = \mathbf{0}$
- $0 \alpha = \mathbf{0}$
- $(-1) \alpha = -\alpha$

### 3.1.2 向量组的线性组合

> 定义3 设 $\alpha_1, \alpha_2, \cdots , \alpha_r$ 为 $r$ 个 $n$ 维向量, $k_1, k_2, \cdots , k_r$ 为 $r$ 个实数, 称

$$
k_1\alpha_1 + k_2\alpha_2 + \cdots + k_r\alpha_r
$$

为向量组 $\alpha_1, \alpha_2 , \cdots , \alpha_r$ 的一个线性组合, $k_1, k_2, \cdots , k_r$ 称相应的组合系数

若 $\beta$ 可以表示为向量组 $\alpha_1, \alpha_2, \cdots , \alpha_r$ 的一个线性组合, 则称 $\beta$ 可以由向量组 $\alpha_1, \alpha_2, \cdots , \alpha_r$ 线性表示

- 向量组 $\alpha_1, \alpha_2, \cdots , \alpha_r$ 中每个向量都可以由该向量组线性表示

$$
\alpha_i = 0 \alpha_1 + \cdots + 1 \alpha_i + \cdots + 0 \alpha_r
$$

- 若 $\varepsilon_1 = (1, 0, 0) \ , \ \varepsilon_2 = (0, 1, 0) \ , \ \varepsilon_3 = (0, 1, 1)$ , 则对于任意 $\alpha = (a_1, a_2, a_3) \in R^3$ , 有

$$
\alpha = a_1 \varepsilon_1 + a_2 \varepsilon_2 + a_3 \varepsilon_3
$$

即 $R^3$ 中任意向量都可由向量组 $\varepsilon_1 , \varepsilon_2 , \varepsilon_1$ 线性表示

- $n$ 维零向量可以由任一 $n$ 维向量组线性表示

$$
\mathbf{0} = 0 \alpha_1 + 0 \alpha_2 + \cdots + 0 \alpha_r
$$

- 用线性组合关系表示方程组

$$
\begin{aligned}
 & \begin{cases}
  a_{11} x_1 + a_{12} x_2 + \cdots + a_{1n} x_n = b_1 \\
  a_{21} x_1 + a_{22} x_2 + \cdots + a_{2n} x_n = b_2 \\
  \cdots \cdots \cdots \cdots \\
  a_{m1} x_1 + a_{m2} x_2 + \cdots + a_{mn} x_n = b_m
  \end{cases} \\
 & \ \\
 & 令 \ \alpha_j = \begin{pmatrix}
  a_{1j} \\ a_{2j} \\ \vdots \\ a_{mj}
  \end{pmatrix}
  \ (j = 1, 2, \cdots , n) \
  , \ \beta = \begin{pmatrix}
  b_1 \\ b_2 \\ \vdots \\ b_m
  \end{pmatrix} \\
  & \ \\
  & 则有 \ \beta = x_1 \alpha_1 + x_2 \alpha_2 + \cdots + x_n \alpha_n \\
  & 则方程是否有解, 即是否存在一组数 k_1, k_2, \cdots , k_n 使下列线性关系式成立 \\
  & \beta = k_1 \alpha_1 + k_2 \alpha_2 + \cdots + k_n \alpha_n
\end{aligned}
$$

* $\beta$ 能由向量组 $\alpha_1, \alpha_2, \cdots , \alpha_n$ 表示且表示唯一, 等价于方程组有唯一解
* $\beta$ 能由向量组 $\alpha_1, \alpha_2, \cdots , \alpha_n$ 表示且表示不唯一, 等价于方程组有无穷组解
* $\beta$ 不能由向量组 $\alpha_1, \alpha_2, \cdots , \alpha_n$ 表示, 等价于方程组无解

> 定义4 两向量组

$$
A: \ \alpha_1, \alpha_2, \cdots , \alpha_s \ ; \ B: \ \beta_1, \beta_2, \cdots , \beta_t
$$

若向量组 $B$ 中每个元素都能由向量组 $A$ 线性表示, 则称向量组 $B$ 能由向量组 $A$ 线性表示

若向量组 $A$ 与向量组 $B$ 能互相线性表示, 则称这两个向量组等价

若向量组 $B$ 能由向量组 $A$ 线性表示, 则存在系数 $k_{ij}(i = 1, 2, \cdots , s \ , \ j = 1, 2, \cdots , t)$ , 使

$$
\begin{cases}
 \beta_1 = k_{11} \alpha_1 + k_{21} \alpha_2 + \cdots + k_{s1} \alpha_s \\
 \beta_2 = k_{12} \alpha_1 + k_{22} \alpha_2 + \cdots + k_{s2} \alpha_s \\
 \cdots \cdots \cdots \cdots \\
 \beta_t = k_{1t} \alpha_1 + k_{21} \alpha_2 + \cdots + k_{st} \alpha_s
\end{cases}
$$

上式可简记为

$$
(\beta_1, \beta_2 , \cdots , \beta_t) = (\alpha_1, \alpha_2, \cdots , \alpha_s)
\begin{pmatrix}
 k_{11} & k_{12} & \cdots & k_{1t} \\
 k_{21} & k_{22} & \cdots & k_{2t} \\
 \vdots & \vdots &   & \vdots \\
 k_{s1} & k_{s2} & \cdots & k_{st}
\end{pmatrix}
$$

令 $B = (\beta_1 , \beta_2 , \cdots , \beta_t) \ , \ A = (\alpha_1, \alpha_2, \cdots , \alpha_s)$ , 则上式表示 $B$ 的列向量组可以由 $A$ 的列向量组表示

令 $K = (k_{ij})_{s \times t}$ , 称　$K$ 为向量组 $B$ 由向量组 $A$ 表示的系数矩阵, 简写为

$$
B = AK
$$

> 定理1 向量组线性表示关系的传递性

若向量组 $C: \ \gamma_1, \gamma_2, \cdots , \gamma_m$ 可由向量组 $B: \ \beta_1, \beta_2, \cdots , \beta_t$ 线性表示,
向量组 $B: \ \beta_1, \beta_2, \cdots , \beta_t$ 可由向量组 $A: \ \alpha_1, \alpha_2, \cdots , \alpha_t$ 线性表示, 
则向量组 $C$ 可由向量组 $A$ 线性表示

$$
\begin{aligned}
 & 存在矩阵 K_1, K_2 \\
 & 有 \ C = BK_1 \ , \ B = AK_2 \\
 & 则 \ C = BK_1 = AK_2K_1 = A(K_2K_1) \\
 & \ \\
 & 则C可由A线性表, 系数K = K_2K_1
\end{aligned}
$$

**向量组之间等价关系也有传递性**

例 求下列向量组 $B$ 由向量组 $A$ 线性表示的系数矩阵 $K$

$$
B: \ \beta_1 = (a_{11}, a_{21}, a_{31})^T, \beta_2 = (a_{12}, a_{22}, a_{32})^T \\
A: \ \varepsilon_1 = (1, 0, 0)^T, \varepsilon_2 = (0, 1, 0)^T, \varepsilon_3 = (0, 0, 1)^T
$$

解

$$
\begin{aligned}
 & \begin{cases}
  \beta_1 = a_{11} \varepsilon_1 + a_{21} \varepsilon_2 + a_{31} \varepsilon_3 \\
  \beta_2 = a_{12} \varepsilon_1 + a_{22} \varepsilon_2 + a_{32} \varepsilon_3
 \end{cases} \\
 & (\beta_1 , \beta_2) = (\varepsilon_1 , \varepsilon_2 , \varepsilon_3) \begin{pmatrix}
  a_{11} & a_{12} \\
  a_{21} & a_{22} \\
  a_{31} & a_{32}
 \end{pmatrix} \\
 & \ \\
 & 则 \ K = \begin{pmatrix}
  a_{11} & a_{12} \\
  a_{21} & a_{22} \\
  a_{31} & a_{32}
 \end{pmatrix}
\end{aligned}
$$

## 3.2 向量组的线性相关性
### 3.2.1 线性相关与线性无关

> 定义1 对于向量组 $\alpha_1 , \alpha_2 , \cdots , \alpha_s \ (s \ge 1)$ ,
若存在不全为零的实数 $k_1, k_2, \cdots , k_s$ , 使

$$
k_1 \alpha_1 + k_2 \alpha_2 + \cdots + k_s \alpha_s = \mathbf{0}
$$

则称向量组 $\alpha_1 , \alpha_2 , \cdots , \alpha_s$ 线性相关, 否则称之为线性无关

_若 $\alpha_1 , \alpha_2 , \cdots , \alpha_s \ (s \ge 1)$ 线性无关, 则_

$$
k_1 \alpha_1 + k_2 \alpha_2 + \cdots + k_s \alpha_s = \mathbf{0}
$$

_必可得_ $k_1 = k_2 = \cdots = k_s = \mathbf{0}$

**两个单位向量线性相关即表示它们共线, 三个三位向量线性相关即表示它们共面, 反之仍成立**

> 定理1 向量组 $\alpha_1 , \alpha_2 , \cdots , \alpha_s \ (s \ge 2)$ 线性相关, 
当且仅当向量组里至少有一个向量可由其余向量线性表示

$$
\begin{aligned}
 & 对于 \ \alpha_1 , \alpha_2 , \cdots , \alpha_s \\
 & \ \\
 & 若其中一个向量可由其他向量线性表示 \\
 & 设 \ \alpha_s = k_1 \alpha_1 + k_2 \alpha_2 + \cdots + k_{s - 1} \alpha_{s - 1} \\
 & 则\ k_1 \alpha_1 + k_2 \alpha_2 + \cdots + k_{s - 1} \alpha_{s - 1} + (-1) \alpha_s = \mathbf{0} \\
 & \ \\
 & 反之, 若 \alpha_1 , \alpha_2 , \cdots , \alpha_s 线性相关, 则有 \\
 & k_1 \alpha_1 + k_2 \alpha_2 + \cdots + k_s \alpha_s = \mathbf{0} \\
 & 设 k_s \ne 0, 则 \\
 & \alpha_s = - \frac{k_1}{k_s} \alpha_1 - \frac{k_2}{k_s} \alpha_2 - \cdots - \frac{k_{s - 1}}{k_s} \alpha_{s - 1} \\
 & \ \\
 & 即 \alpha_s 可由其他向量线性表示
\end{aligned}
$$

_含零向量的向量组一定线性相关_

$$
\begin{aligned}
 & 若向量组 \alpha_1 , \alpha_2 , \cdots , \alpha_s 中 \alpha_1 = \mathbf{0} \\
 & 则 \ 1 \cdot \alpha_1 + 0 \cdot \alpha_2 + 0 \cdot \alpha_3 + \cdots + 0 \cdot \alpha_s = \mathbf{0}
\end{aligned}
$$

> 定理2 若向量组中有一个部分组线性相关, 则向量组也线性相关;
若向量组线性无关, 则其任何部分组线性无关

> 定理3 若向量组 $\alpha_1 , \alpha_2 , \cdots , \alpha_s$ 线性无关,
而向量组 $\alpha_1 , \alpha_2 , \cdots , \alpha_s, \beta$ 线性相关,
则 $\beta$ 可由向量组 $\alpha_1 , \alpha_2 , \cdots , \alpha_s$ 线性表示且表示法唯一

$$
\begin{aligned}
 & k_1 \alpha_1 + k_2 \alpha_2 + \cdots + k_s \alpha_s + k \beta = \mathbf{0} \\
 & \ \\
 & 若 k = 0, 则有 \ k_1 \alpha_1 + k_2 \alpha_2 + \cdots + k_s \alpha_s = \mathbf{0} \\
 & 且 k_1, k_2, \cdots , k_s 不全为零, 这与 \alpha_1 , \alpha_2 , \cdots , \alpha_s 线性无关矛盾 \\
 & 故 k \ne 0 \\
 & \ \\
 & 则 \beta = - \frac{k_1}{k} \alpha_1 - \frac{k_2}{k} \alpha_2 - \cdots - \frac{k_{s}}{k} \alpha_{s} \\
 & 即 \beta 可由 \alpha_1 , \alpha_2 , \cdots , \alpha_s 线性表示 \\
 & \ \\
 & 若存在两组数 t_1, t_2, \cdots , t_s \ , \ l_1, l_2, \cdots , l_s 使 \\
 & \beta = t_1 \alpha_1 + t_2 \alpha_2 + \cdots + t_s \alpha_s = l_1 \alpha_1 + l_2 \alpha_2 + \cdots + l_s \alpha_s \\
 & 则 \ (t_1 - l_1) \alpha_1 + (t_2 - l_2) \alpha_2 + \cdots + (t_s - l_s) \alpha_s = \mathbf{0} \\
 & \ \\
 & 又 \alpha_1 , \alpha_2 , \cdots , \alpha_s 线性无关, 则 t_i = l_i \ (i = 1, 2, \cdots , s) \\
 & \ \\
 & 即, 表示法唯一
\end{aligned}
$$

**向量组 $\alpha, \beta, \gamma$ 线性无关, 则向量组 $\alpha + \beta, \beta + \gamma, \gamma + \alpha$ 也线性无关**

$$
\begin{aligned}
 & 设有 k_1, k_2, k_3 \\
 & 使 \ k_1 (\alpha + \beta) + k_2 (\beta + \gamma) + k_3 (\gamma + \alpha) = \mathbf{0} \\
 & 即 \ (k_1 + k_3) \alpha + (k_1 + k_2) \beta + (k_2 + k_3) \gamma = \mathbf{0} \\
 & \ \\
 & 又 \alpha, \beta, \gamma 线性无关, 则 \\
 & \begin{cases}
  k_1 + k_3 = 0 \\
  k_1 + k_2 = 0 \\
  k_2 + k_3 = 0
 \end{cases} \\
 & \ \\
 & 由克拉默法则得, 此方程组 D = 2 \ne 0, 则方程组只有零解, 即 k_1 = k_2 = k_3 = 0 \\
 & 则 \alpha + \beta, \beta + \gamma, \gamma + \alpha 线性无关
\end{aligned}
$$

### 3.2.2 利用矩阵的秩判定向量组的线性相关性

> 定理4 设矩阵 $A$ 的秩为 $r$ , 则 $A$ 中存在 $r$ 个行向量(或列向量)线性无关,
且 $A$ 的任一行向量(或列向量)都可由这 $r$ 个行列式线性表示

$$
\begin{aligned}
 & A = \begin{pmatrix}
  a_{11} & a_{12} & \cdots & a_{1n} \\
  a_{21} & a_{22} & \cdots & a_{2n} \\
  \vdots & \vdots &   & \vdots \\
  a_{m1} & a_{m2} & \cdots & a_{mn}
 \end{pmatrix} = \begin{pmatrix}
  \alpha_1 \\ \alpha_2 \\ \vdots \\ \alpha_m
 \end{pmatrix} \\
 & 其中 \ \alpha_i = (a_{i1}, a_{i2}, \cdots , a_{in}) \ (i = 1, 2, \cdots , m) \\
 & \ \\
 & 由矩阵秩的定义, A 存在一个不为零的r阶子式, 设A左上角的r阶子式不为零 \\
 & \left | D \right | = \begin{vmatrix}
  a_{11} & a_{12} & \cdots & a_{1r} \\
  a_{21} & a_{22} & \cdots & a_{2r} \\
  \vdots & \vdots &   & \vdots \\
  a_{r1} & a_{r2} & \cdots & a_{rr}
 \end{vmatrix} \ne 0 \\
 & \ \\
 & 若 \alpha_1, \alpha_2, \cdots , \alpha_r线性相关, 则设 \\
 & \alpha_r = k_1 \alpha_1 + k_2 \alpha_2 + \cdots + k_{r - 1} \alpha_{r - 1} \\
 & \ \\
 & \left | D \right | \xrightarrow[]{(r_1, r_2, \cdots , r_{r - 1}) \times (-k_1, -k_2, \cdots , -k_{r - 1}) + r_r} \cdots \\
 & 则 \left | D \right | 最后一行圈化为零, 即 \left | D \right | = 0, 与假设矛盾 \\
 & 则\alpha_1, \alpha_2, \cdots , \alpha_r线性无关 \\
 & \ \\
 & \alpha_1, \alpha_2, \cdots , \alpha_r向量组中每个向量都能由它本事线性表示, 则只需证\alpha_k \ (k > r)时能由向量组线性表示 \\
 & \ \\
 & \left | D_t \right | = \begin{vmatrix}
  \color{#00aaff}{a_{11}} & \color{#00aaff}{\cdots} & \color{#00aaff}{a_{1r}} & a_{1t} \\
  \color{#00aaff}{a_{21}} & \color{#00aaff}{\cdots} & \color{#00aaff}{a_{2r}} & a_{2t} \\
  \color{#00aaff}{\vdots} &   & \color{#00aaff}{\vdots} & \vdots \\
  \color{#00aaff}{a_{r1}} & \color{#00aaff}{\cdots} & \color{#00aaff}{a_{rr}} & a_{rt} \\
  a_{k1} & \cdots & a_{kr} & a_{kt}
 \end{vmatrix}, \ t = 1, 2, \cdots , n \\
 & \ \\
 & t \le r时, D_t 最后一列与前面某列相同, \left | D_t \right | = 0 \\
 & t > r 时, \left | D_t \right | 为A的r + 1阶子式, 根据秩的定义, 同样\left | D_t \right | = 0 \\
 & \ \\
 & 展开\left | D_t \right |最后一列, 得 \\
 & a_{1t} A_1 + a_{2t} A_2 + \cdots + a_{rt} A_r + a_{kt} \left | D \right | = 0 \\
 & A_1, A_2, \cdots , A_r分别为a_{1t}, a_{2t}, \cdots , a_{rt} 的代数余子式	, 取值与t无关 \\
 & \ \\
 & \left | D \right | \ne 0 \Rightarrow a_{kt} = - \frac{A_1}{\left | D \right |} a_{1t} - \frac{A_2}{\left | D \right |} a_{2t}
 - \cdots - \frac{A_r}{\left | D \right |} a_{rt} \ , \ t = 1, 2, \cdots , n \\
 & 则 \ (a_{k1}, a_{k2}, \cdots , a_{kn}) = - \frac{A_1}{\left | D \right |} (a_{11}, a_{12}, \cdots , a_{1n})
 - \cdots - \frac{A_r}{\left | D \right |} (a_{r1}, a_{r2}, \cdots , a_{rn}) \\
 & 即 \ \alpha_k = - \frac{A_1}{\left | D \right |} \alpha_1 - \frac{A_2}{\left | D \right |} \alpha_2
 - \cdots - \frac{A_r}{\left | D \right |} \alpha_r \\
 & \alpha_k 可由 \alpha_1, \alpha_2, \cdots , \alpha_r 线性表示 \\
 & \ \\
 & A \rightarrow A^T , 则可证关于列向量的结论
\end{aligned}
$$

> 推论1 向量组线性相关的矩阵判别法

设 $\alpha_1, \alpha_2, \cdots , \alpha_s$ 为一 $n$ 维列向量组, 令

$$
A = (\alpha_1, \alpha_2, \cdots , \alpha_s)
$$

为 $n \times s$矩阵,
则 $\alpha_1, \alpha_2, \cdots , \alpha_s$ 线性相关的充要条件是 $r(A) < s$,
线性无关的充要条件是 $r(A) = s$

特别地, 当 $s = n$ 时, 线性相关充要条件为 $\left | A \right | = 0$

> 推论2 $m > n$ 时,  $m$个$n$维向量一定线性相关

### 3.2.3 向量组的秩

> 定义2 如果向量组 $A$ 中部分组 $\alpha_1, \alpha_2, \cdots , \alpha_r$ 满足条件

- $\alpha_1, \alpha_2, \cdots , \alpha_r$ 线性无关
- 向量组 $A$ 中每个向量都可由 $\alpha_1, \alpha_2, \cdots , \alpha_r$ 线性表示

则称 $\alpha_1, \alpha_2, \cdots , \alpha_r$ 为向量组 $A$ 的一个最大无关组或极大无关组

_一个向量组的最大无关组与该向量组等价, 且线性无关向量组最大无关组为它本身_

例
向量组 $\alpha_1 = (1, 0, 0), \alpha_2 = (1, 1, 0), \alpha_3 = (2, 1, 0)$ 中, $\alpha_1, \alpha_2$ 线性无关,
而 $\alpha_3 = \alpha_1 + \alpha_2$ , 所以 $\alpha_1, \alpha_2$ 为向量组的一个最大无关组,

同理 $\alpha_1, \alpha_3$和 $\alpha_2, \alpha_3$ 也为向量组的最大无关组

> 定理5 由有限个行向量 $\alpha_1, \alpha_2, \cdots , \alpha_s$ 组成的向量组的任一最大无关组中所含的向量个数均相等,
且等于下列矩阵的秩

$$
A = \begin{pmatrix} \alpha_1 \\ \alpha_2 \\ \cdots \\ \alpha_s \end{pmatrix}
$$

证明

$$
\begin{aligned}
 & 设向量组 \alpha_{i_1}, \alpha_{1_2}, \cdots , \alpha_{i_k} 为向量组 \alpha_1, \alpha_2, \cdots , \alpha_s 的任一最大无关组 \\
 & \ \\
 & 令 \ B = \begin{pmatrix} \alpha_{i_1} \\ \alpha_{i_2} \\ \vdots \\ \alpha_{i_k} \end{pmatrix} \\
 & \ \\
 & 因为 \alpha_{i_1}, \alpha_{1_2}, \cdots , \alpha_{i_k} 线性无关, 由推论1得, r(B) = k \\
 & 又B的行向量都是A的行向量, 则B的子式, 要么是A的子式, 要么与A的子式相差一个符号 \\
 & 则B的不为零的子式最高阶数小于或等于A的不为零子式的最高阶数, 即 k \le r(A) \\
 & \ \\
 & 由于 \alpha_{i_1}, \alpha_{1_2}, \cdots , \alpha_{i_k} 为向量组 \alpha_1, \alpha_2, \cdots , \alpha_s 的一个最大无关组, 
 则对于每个a_j \ (j \ne i_1, i_2, \cdots , i_k) \\
 & 有 \ a_j = l_{j1} \alpha_{i_1} + l_{j2} \alpha_{i_2} + \cdots + l_{jk} \alpha_{i_k} \\
 & \ \\
 & A \xrightarrow[]{r_j + (r_{i_1}, r_{i_2}, \cdots , r_{i_k}) \times (-l_{j1}, -l_{j2}, \cdots , -l_{jk})} , 则第 j 行化为零
 \ , \ 通过若干次初等变换, s - k 行全为零, 从而r(A) \le k \\
 & \ \\
 & k \le r(A) 且 r(A) \le k, 则k = r(A), 即向量组的任一最大无关组中所含的向量个数均相等, 且等于矩阵A的秩
\end{aligned}
$$

> 定义3 向量组的最大无关组中所含向量的个数称向量组的秩
> 定理6 矩阵 $A$ 的秩等于它行向量组的秩, 也等于它列向量组的秩

例
判断向量组 $\alpha_1 = (1, 4, 1, 0)^T, \alpha_2 = (2, 1, -1, -3)^T, \alpha_3 = (1, 0, -3, -1)^T, \alpha_4 = (0, 2, -6, 3)^T$
是否线性相关, 并求它的秩

$$
\begin{aligned}
 & 构建矩阵 \\
 & A = (\alpha_1, \alpha_2, \alpha_3, \alpha_4) = \begin{pmatrix}
  1 & 2 & 1 & 0 \\
  4 & 1 & 0 & 2 \\
  1 & -1 & -3 & -6 \\
  0 & -3 & -1 & 3
 \end{pmatrix} \\
 & A \xrightarrow[\cdots]{\cdots} \begin{pmatrix}
  1 & 2 & 1 & 0 \\
  0 & -3 & -1 & 3 \\
  0 & 0 & -3 & -9 \\
  0 & 0 & 0 & 0
 \end{pmatrix} \\
 & r(A) = 3 < 4, 则向量组线性相关, 它的秩为3
\end{aligned}
$$

例
求上述向量组的一个最大无关组

$$
B = \begin{pmatrix}
 1 & 2 & 1 & 0 \\
 0 & -3 & -1 & 3 \\
 0 & 0 & -3 & -9 \\
 0 & 0 & 0 & 0
\end{pmatrix} \\
\ \\
\begin{aligned}
 & B左上角的三阶子式不为零, 则B前三列三个列向量 \alpha_1, \alpha_2, \alpha_3 线性无关 \\
 & 即 \alpha_1, \alpha_2, \alpha_3 为向量组 \alpha_1, \alpha_2, \alpha_3, \alpha_4 的一个最大无关组
\end{aligned}
$$

> 定理7 若线性无关向量组 $\alpha_1, \alpha_2, \cdots , \alpha_s$ 可由向量组 $\beta_1, \beta_2, \cdots , \beta_t$ 线性表示, 则 $s \le t$

证明

$$
\begin{aligned}
 & 设n维列向量 \alpha_i, \beta_j \ (i = 1, 2, \cdots , s \ ; \ j = 1, 2, \cdots , t) , 令 \\
 & A = (\alpha_1, \alpha_2, \cdots , \alpha_s) \ , \ B = (\alpha_1, \alpha_2, \cdots , \alpha_s, \beta_1, \beta_2, \cdots , \beta_t) \\
 & \ \\
 & 由于A的任一子式都为B的一个子式, 咕 r(A) \le r(B) \\
 & 又 \alpha_1, \alpha_2, \cdots , \alpha_s 线性无关, 则r(A) = s \le r(B) \\
 & \ \\
 & 又 alpha_1, \alpha_2, \cdots , \alpha_s 可由 \beta_1. \beta_2, \cdots , \beta_t 线性表示, 则 \\
 & B = (\alpha_1, \alpha_2, \cdots , \alpha_s, \beta_1, \beta_2, \cdots , \beta_t) \rightarrow 
 C = (\mathbf{0}, \mathbf{0}, \cdots , \mathbf{0}, \beta_1, \beta_2, \cdots , \beta_t) \\
 & 则 r(B) = r(C) \le t, \ s \le t
 
 \end{aligned}
$$

**定理7等价表示**

向量组 $\alpha_1, \alpha_2, \cdots , \alpha_s$ 可由向量组 $\beta_1, \beta_2, \cdots , \beta_t$ 线性表示, 且 $s > t$ ,
则向量组 $\alpha_1, \alpha_2, \cdots , \alpha_s$ 线性相关

> 推论3 设向量组秩为 $r$  向量组中任意多余 $r$ 个向量构成的向量组一定线性相关, 
从而向量组中任意 $r$ 个线性无关的向量都构成向量组的一个最大无关组

> 推论4 向量组任一线性无关部分组都可由扩充为向量组的一个最大无关组

> 推论5 若两个线性无关向量组 &\alpha_1, \alpha_2, \cdots , \alpha_s$ 和 $\beta_1, \beta_2, \ dots , \beta_t$ , 则 $s = t$

> 推论6 向量组 $A$ 与向量组 $B$ 等价, 则它们有相同的秩

例
向量组 $\alpha_1, \alpha_2, \alpha_3$ 线性相关, 向量组 $\alpha_2, \alpha_3, \alpha_4$ 线性无关, 证明

- $\alpha_1$ 能有 $\alpha_2, \alpha_3$ 线性表示
- $\alpha_4$ 不能由 $\alpha_1, \alpha_2, \alpha_3$ 线性表示

证明 

$$
\begin{aligned}
 & \alpha_2, \alpha_3, \alpha_4 线性无关, 则由定理2, \alpha_2, \alpha_3 线性无关 \\
 & 又 \alpha_1, \alpha_2, \alpha_3 线性相关, 由定理3, \alpha_1 能由 \alpha_2, \alpha_3线性表示 \\
 & \ \\
 & 反证法: \ 假设 \alpha_4 能由 \alpha_1, \alpha_2, \alpha_3 线性表示, 又 \alpha_1 能由 \alpha_2, \alpha_3 线性表示 \\
 & 则 \alpha_4 能有 \alpha_2, \alpha_3 线性表示, 与 \alpha_2, \alpha_3, \alpha_4 线性无关相矛盾
\end{aligned}
$$

> 定理8 若向量组线性无关, 则在各向量中相应增加分量后, 所得向量组仍线性无关

$$
\begin{aligned}
 & 设s个m维向量 \alpha_1, \alpha_2, \cdots , \alpha_s 线性无关, \ 在每个向量中增加n - m个分量后得到n维向量组 \beta_1, \beta_2, \cdots , \beta_s \\
 & \ \\
 & 先证明分量都添加在各个\alpha_i后面是结论成立, 即若\alpha_i = (a_{i1}, a_{i2}, \cdots , a_{im})^T \\
 & 则 \ \beta_i = (a_{i1}, a_{i2}, \cdots , a_{im}, a_i, a_{m + 1}, \cdots , a_{in})^T \ , \ i = 1, 2, \cdots , s \\
 & \ \\
 & 设 \  x_1 \beta_1 + x_2 \beta_2 \cdots + x_s \beta_s = \mathbf{0} \\
 & 展开得 \ \begin{cases}
  a_{11} x_1 + a_{21} x_2 + \cdots + a_{s1} x_s = 0 \\
  a_{12} x_1 + a_{22} x_2 + \cdots + a_{s2} x_s = 0 \\
  \cdots \cdots \cdots \cdots \\
  a_{1m} x_1 + a_{2m} x_2 + \cdots + a_{sm} x_s = 0 \\
  a_{1, m + 1} x_1 + a_{2, m + 1} x_2 + \cdots + a_{s, m + 1} x_s = 0 \\
  \cdots \cdots \cdots \cdots \\
  a_{1n} x_1 + a_{2n} x_2 + \cdots + a_{sn} x_s = 0
 \end{cases} \\
 & 则方程组前m个方程可写为 \ x_1 \alpha_1 + x_2 \alpha_2 + \cdots + x_s \alpha_s = \mathbf{0} \\
 & \ \\
 & 又 \alpha_1, \alpha_2, \cdots , \alpha_s 线性无关, 则方程只有零解, 即方程组只有零解 \\
 & 故向量组 \beta_1, \beta_2, \cdots , \beta_s 线性无关 \\
 & \ \\
 & 若分量加在 \alpha_i 个分量之间, 定理仍成立
\end{aligned}
$$

> 推论7 若向量组线性相关, 则在个向量中减少响应和分量之后向量组仍线性相关

## 3.3 向量空间
### 3.3.1 向量空间

设 $S$ 为由 $n$ 维向量组成的集合, 若对任意 $\alpha, \beta \in S$ , 有 $\alpha + \beta \in S$ ,则称集合 $S$ 关于向量的加法封闭

若对于任意 $\alpha \in S, k \in R$ , 有 $k \alpha \in S$ , 则称集合 $S$ 关于向量的数乘封闭

> 定义1 设 $V$ 为 $n$ 维向量组成的非空集合, 若 $V$ 关于向量的加法和数乘都封闭, 则称 $V$ 为向量空间

**全体 $n$ 维向量的集合就是一个向量空间, 称为 $n$ 维向量空间, 记作** $R^n$

**平面和空间中向量可分别由二维和三位表示, 故 $R^2, \ R^3$ 分别为通常都二维和三维空间**

例
判断下列哪些是向量空间

$$
\begin{aligned}
 & A = \{ (a_1, 0, \cdots , 0) | a_1 \in R \} \\
 & B = \{ (a_1, 1, 0, \cdots , 0) | a_1 \in R \} \\
 & C = \{ (a_1, a_2, \cdots , a_n) | a_1 + a_2 + \cdots + a_n = 0, \ a_i \in R, \ i = 1, 2, \cdots , n \}
\end{aligned}
$$

解

$$
\begin{aligned}
 & A是向量空间, \forall \ \alpha = (a, 0, \cdots , 0), \ \beta = (b, 0, \cdots , 0), \ k \in R \\
 & \alpha + \beta = (a + b, 0, \cdots , 0) \in A \\
 & k \alpha = (ka, 0, \cdots , 0) \in A \\
 & 即A关于向量的加法和数乘都封闭 \\
 & \ \\
 & B不是向量空间, \ \alpha = (a, 1, 0, \cdots , 0), \ \beta = (b, 1, 0, \cdots , 0) \\
 & \alpha + \beta = (a + b, 2, 0, \cdots , 0) \notin B \\
 & 即B关于向量加法不封闭 \\
 & \ \\
 & C是向量空间, \forall \ \alpha = (a_1, a_2, \cdots , \alpha_n) , \ \beta = (b_1, b_2, \cdots , b_n) \\
 & 其中 a_1 + a_2 + \cdots + a_n = 0\ , \ b_1 + b_2 + \cdots + b_n = 0 , 有 \\
 & \alpha + \beta = (a_1 + b_1, a_2 + b_2, \cdots , a_n + b_n) \\
 & 且 a_1 + b_1 + a_2 + b_2 + \cdots + a_n + b_n = (a_1 + a_2 + \cdots + a_n) + (b_1 + b_2 + \cdots + b_n) = 0 \\
 & 即 \alpha + \beta \in C \\
 & 又 \forall k \ , k a_1 + k a_2 + \cdots + k a_n = k (a_1 + a_2 + \cdots + a_n) = 0 \\
 & k \alpha = (k a_1, k a_2, \cdots , k a_n) \in C \\
 & 即 k \alpha \in C, 因此C关于向量的加法和数乘都封闭
\end{aligned}
$$

### 3.3.2 子空间

> 定义2 设 $W$ 是向量空间 $V$ 的一个非空子集, 若 $W$ 关于向量的加法和数乘都封闭, 称 $W$ 为 $V$ 的一个子空间

**向量空间 $V$ 的非空子集 $W$ 是 $V$ 的向量子空间当且仅当 $\forall \alpha, \beta \in W, \ k, l \in R$ , 有** $k \alpha + l \beta \in W$

_向量空间 $V$ 本身和 $V$ 中零向量组成的零空间都是 $V$ 的子空间, 这两个子空间称为平凡子空间, 它们分别构成 $V$ 的最大和最小子空间_

_$V$ 其他子空间称为非平凡子空间_

上述例子中 $A, C$ 都是 $R^n$ 的子空间, 同理

$$
\begin{aligned}
 & W_1 = \{ (a_1, a_2, \cdots, a_{n - 1}, \sum_{i = 1}^{n - 1} a_i) \ | \ a_i \in R, i = 1, 2, \cdots, n - 1 \} \\
 & W_2 = \{ (a_1, a_2, \cdots , a_n) \ | \ a_1 = a_2 = \cdots = a_n \in R \} \\
 & W_3 = \{ (a, a + b, a + 2b, \cdots , a + (n - 1)b \ | \ a, b \in R) \}
\end{aligned}
$$

都是 $R^n$ 的子空间

设 $V$ 是一个向量空间, $\alpha_, \alpha_2, \cdots , \alpha_r \in V$ , 则

$$
W = \{ k_1 \alpha_2 + k_2 \alpha_2 + \cdots + k_r \alpha_r \ | \ k_i \in R, i =1, 2, \cdots , r \}
$$

是 $V$ 的子空间, 这个子空间称为由 $\alpha_1, \alpha_2, \cdots , \alpha_r$ 生成的子空间, 记作 $L(\alpha_1, \alpha_2, \cdots , \alpha_r)$

$\alpha_1, \alpha_2, \cdots , \alpha_r$ 称为这个子空间的一组生成元

_对于 $\alpha \in V, L(\alpha) = {k \alpha \ | \ k \in R}$ 是由 $\alpha$ 生成的 $V$ 的子空间_

设 $W_1, W_2$ 为向量空间 $v$ 的两个子空间, 则 $V$ 的子集

$$
\{ \alpha \ | \ \alpha \in W_1 且 \alpha \in W_2 \} \\
\ \\
\{ \alpha \ | \ \alpha = \alpha_1 + \alpha_2 , 其中 \alpha_1 \in W_1, \alpha_2 \in W_2 \}
$$

都是 $V$ 的子空间, 前者称两个子空间 $W_1, W_2$ 的交, 记作 $W_1 \cap W_2$ ; 后者称两个子空间 $W_1, W_2$ 的和, 记作 $W_1 + W_2$

- $\mathbf{0} \in w_1, \mathbf{0} \in W_2 \Rightarrow \mathbf{0} \in W_1 \cap W_2$
- $\forall \alpha, \beta \in W_1 \cap W_2 \ , \ \alpha + \beta \in W_1 \cap W_2$

$W_1 \cap W_2$ 关于向量的加法和数乘都封闭, 是 $V$ 的子空间

$W_! + W_2$ 也是 $V$ 的子空间

### 3.3.3 向量空间的基与维数

> 定义3 设 $V$ 为一个向量空间, $\alpha_1, \alpha_2, \cdots , \alpha_r \in V$ , 若

- $\alpha_1, \alpha_2, \cdots , \alpha_r$ 线性无关
- $V$ 的任一向量都可由 $\alpha_1, \alpha_2, \cdots , \alpha_r$ 线性表示

则称向量组 $\alpha_1, \alpha_2, \cdots , \alpha_r$ 为向量空间 $V$ 的一组基, $r$ 称为向量空间 $V$ 的维数, 记作 $dim(V) = r$

**零空间的维度规定为零**

_把向量空间看做一个向量组, 则其基就是它的一个最大无关组, 其维数就是它的秩_

_向量空间可以有很多组基, 但每组基所含向量个数相同, 故向量空间维数唯一确定_

例
证明 $\varepsilon_1 = (1, 0, \cdots , 0), \varepsilon_2 = (0, 1, \cdots , 0) , \cdots , \varepsilon_n = (0, 0, \cdots , 1)$ 
为 $R^n$ 的一组基, 从而得 $R^n$ 的维数为 $n$

$$
\begin{aligned}
 & 先证 \varepsilon_1, \varepsilon_2, \cdots , \varepsilon_n 线性无关 \\
 & 它们构成矩阵 E = (\varepsilon_1, \varepsilon_2, \cdots , \varepsilon_n) = \begin{pmatrix}
  1 & 0 & \cdots & 0 \\
  0 & 1 & \cdots & 0 \\
  \vdots & \vdots &   & \vdots \\
  0 & 0 & \cdots & 1
 \end{pmatrix} \\
 & r(E) = n, 则向量组线性无关 \\
 & \ \\
 & 对于 \forall \alpha \in R^n \ , \ 设 \alpha = (a_1, a_2, \cdots , a_n) \\ 
 & \alpha = a_1 \varepsilon_1 + a_2 \varepsilon_2 + \cdots + a_n \varepsilon \\
 & 故 \varepsilon_1, \varepsilon_2, \cdots , \varepsilon_n 为向量空间 R^n 的基, 且 dim(R^n) = n
\end{aligned}
$$

$\varepsilon_1, \varepsilon_2, \cdots , \varepsilon_n$ 称为向量空间 $R^n$ 的标准基

设 $\alpha_1, \alpha_2, \cdots , \alpha_m$ 是 $m$ 个 $n$ 为向量, 

$$
V = L(\alpha_1, \alpha_2, \cdots , \alpha_m) = 
\{ k_1 \alpha_1 + k_2 \alpha_2 + \cdots + k_m \alpha_m \ | \ k_i \in R, i = 1, 2, \cdots , m \}
$$

则向量组 $\alpha_1, \alpha_2, \cdots , \alpha_m$ 的一个最大无关组就是 $V$ 的一组基, 
从而向量组 $\alpha_1, \alpha_2, \cdots , \alpha_m$ 的秩就等于 $V$ 的维数

> 定理1 设 $V$ 是一个向量空间, $dim(V) = r$ , 则 $V$ 中任意 $r$ 个线性无关的向量都是 $V$ 的一组基,
且 $V$ 的任一多于 $r$ 个向量的向量组一定线性相关

**特别地, 任意 $n$ 个线性无关的 $n$ 维向量都是 $R^n$ 的一组基**

> 定理2 向量空间 $V$ 的任一线性无关向量组都可以扩充为 $V$ 的一组基, 特别地, $V$ 的任一子空间的基都可扩充为 $V$ 的基

### 3.3.4 向量在给定基下的坐标

设 $\alpha_1, \alpha_2, \cdots , \alpha_r$ 是向量空间 $V$ 的一组基, 则 $V$ 中每个向量 $\alpha$ 都可表示为

$$
\alpha = x_1 \alpha_1 + x_2 \alpha_2 + \cdots + x_r \alpha_r
$$

且有序数组 $x_1, x_2, \cdots , x_r$ 是唯一的

> 定义4 设 $\alpha_1, \alpha_2, \cdots , \alpha_r$ 是向量空间 $V$ 的一组基, $\alpha \in V$ , 若

$$
\alpha = x_1 \alpha_1 + x_2 \alpha_2 + \cdots + x_r \alpha_r
$$

则 $r$维向量 $(x_1, x_2, \cdots , x_r)$ 称为向量 $\alpha$ 在基 $alpha_1, \alpha_2, \cdots , \alpha_r$ 下的坐标

$R^n$ _中任意向量在标准基下的坐标为它本身_

例
设 $\alpha_1 = (1, 1, 1)^T, \alpha_2 = (1, 1, -1)^T, \alpha_3 = (1, -1, -1)^T$ , 证明 $\alpha_1, \alpha_2, \alpha_3$ 是向量空间 $R^3$ 的一组基, 
并求 $\beta = (1, 2, 1)^T$ 在此基下的坐标

$$
\begin{aligned}
 & 令 A = (\alpha_1, \alpha_2, \alpha_3), 则 \\
 & \left | A \right | = \begin{vmatrix}
  1 & 1 & 1 \\
  1 & 1 & -1 \\
  1 & -1 & -1 \\
 \end{vmatrix} = -4 \ne 0 \\
 & 故 \alpha_1, \alpha_2, \alpha_3 线性无关, 从而是 R^3 的一组基 \\
 & \ \\
 & 令 \beta = x_1 \alpha_1 + x_2 \alpha_2 + x_3 \alpha_3 , 即 \\
 & \begin{pmatrix} 1 \\ 2 \\ 1 \end{pmatrix} = 
 x_1 \begin{pmatrix} 1 \\ 1 \\ 1 \end{pmatrix} + 
 x_2 \begin{pmatrix} 1 \\ 1 \\ -1 \end{pmatrix} + 
 x_3 \begin{pmatrix} 1 \\ -1 \\ -1 \end{pmatrix} = 
 \begin{pmatrix}
  x_1 + x_2 + x_3 \\
  x_1 + x_2 - x_3 \\
  x_1 - x_2 - x_3 
 \end{pmatrix} \\
 & 则有 \ \begin{cases}
  x_1 + x_2 + x_3 = 1 \\
  x_1 + x_2 - x_3 = 2 \\
  x_1 - x_2 - x_3 = 1 \\
 \end{cases} \\
 & 解得 \ x_1 = 1, x_2 = \frac{1}{2}, x_3 = - \frac{1}{2} \\
 & 即 \beta 在基 \alpha_1, \alpha_2, \alpha_3 下的坐标为 (1, \frac{1}{2}, - \frac{1}{2})
\end{aligned}
$$

若 $\alpha, \beta$ 坐标分别为 $(x_1, x_2, \cdots , x_r)$ 及 $(y_1, y_2, \cdots , y_r)$ , 则

- $\alpha + \beta$ 坐标为

$$
(x_1 + y_1, x_2 + y_2, \cdots , x_r + y_r) = (x_1, x_2, \cdots , x_r) + (y_1, y_2, \cdots , y_r)
$$

- $\lambda \alpha$ 坐标为

$$
(\lambda x_1, \lambda x_2, \cdots , \lambda x_r) = \lambda (x_1, x_2, \cdots , x_r)
$$

若向量 $\alpha$ 在基 $\alpha_1, \alpha_2, \cdots , \alpha_r$ 下坐标为 $(x_1, x_2, \cdots , x_r)$ , 即

$$
\alpha = x_1 \alpha_1 + x_2 \alpha_2 + \cdots + x_r \alpha_r
$$

矩阵符号记作

$$
\alpha = (\alpha_1, \alpha_2, \cdots , \alpha_r) \begin{pmatrix} x_1 \\ x_2 \\ \vdots \\ x_r \end{pmatrix}
$$

### 3.3.5 基变换与坐标变换


设 $\alpha_1, \alpha_2, \cdots , \alpha_r$ 和 $\beta_1, \beta_2, \cdots , \beta_r$ 为 $V$ 的两组基. 
由基的定义得, $\beta_1, \beta_2, \cdots , \beta_r$ 可以由 $\alpha_1, \alpha_2, \cdots , \alpha_r$ 线性表示, 即 

$$
\begin{cases}
 \beta_1 = a_{11} \alpha_1 + a_{21}\alpha_2 + \cdots + a_{r1} \alpha_r \\
 \beta_2 = a_{12} \alpha_1 + a_{22}\alpha_2 + \cdots + a_{r2} \alpha_r \\
 \cdots \cdots \cdots \cdots \\
 \beta_r = a_{1r} \alpha_1 + a_{2r}\alpha_2 + \cdots + a_{rr} \alpha_r
\end{cases}
$$

写成矩阵的形式为

$$
(\beta_1, \beta_2, \cdots , \beta_r) = (\alpha_1, \alpha_2, \cdots , \alpha_r) A
$$

其中

$$
A = \begin{pmatrix}
 a_{11} & a_{12} & \cdots & a_{1r} \\
 a_{21} & a_{22} & \cdots & a_{2r} \\
 \vdots & \vdots &   & \vdots \\
 a_{1r} & a_{r2} & \cdots & a_{rr}
\end{pmatrix}
$$

矩阵 $A$ 的第 $i$ 列是 $\beta_i$ 在基 $\alpha_1, \alpha_2, \cdots , \alpha_r$ 下的坐标, 
称 $A$ 为有基 $\alpha_1, \alpha_2, \cdots , \alpha_r$ 到基 $\beta_1, \beta_2, \cdots , \beta_r$ 的过渡矩阵,
上式称为基变换公式

由于 $\beta_1, \beta_2, \cdots , \beta_r$ 也是一组基, $\alpha_1, \alpha_2, \cdots , \alpha_r$ 能由其表示, 即

$$
(\alpha_1, \alpha_2, \cdots , \alpha_r) = (\beta_1, \beta_2, \cdots , \beta_r) B
$$

从而

$$
(\beta_1, \beta_2, \cdots , \beta_r) = (\alpha_1, \alpha_2, \cdots , \alpha_r) A = (\beta_1, \beta_2, \cdots , \beta_r) BA
$$

由 $\beta_1, \beta_2, \cdots , \beta_r$ 线性无关可得 $BA = E$ , 即 $B = A^{-1}$

设 $V$ 中向量 $\alpha$ 在基 $\alpha_1, \alpha_2, \cdots , \alpha_r$ 和基 $\beta_1, \beta_2, \cdots , \beta_r$ 中坐标分别为 
$(x_1, x_2, \cdots , x_r)$ 和 $(y_1, y_2, \cdots , y_r)$ , 即

$$
\alpha = (\alpha_1, \alpha_2, \cdots , \alpha_r) \begin{pmatrix} x_1 \\ x_2 \\ \vdots \\ x_r \end{pmatrix} = 
(\beta_1, \beta_2, \cdots , \beta_r) \begin{pmatrix} y_1 \\ y_2 \\ \vdots \\ y_r \end{pmatrix}
$$

代入得

$$
\alpha = (\alpha_1, \alpha_2, \cdots , \alpha_r) \begin{pmatrix} x_1 \\ x_2 \\ \vdots \\ x_r \end{pmatrix} = 
(\alpha_1, \alpha_2, \cdots , \alpha_r) A \begin{pmatrix} y_1 \\ y_2 \\ \vdots \\ y_r \end{pmatrix}
$$

向量坐标唯一, 可得

$$
\begin{pmatrix} x_1 \\ x_2 \\ \vdots \\ x_r \end{pmatrix} = 
A \begin{pmatrix} y_1 \\ y_2 \\ \vdots \\ y_r \end{pmatrix}
$$

> 定理3 设 $\alpha_1, \alpha_2, \cdots , \alpha_r$ 和 $\beta_1, \beta_2, \cdots , \beta_r$ 是向量空间 $V$ 的两组基,
由基 $\alpha_1, \alpha_2, \cdots , \alpha_r$ 到基 $\beta_1, \beta_2, \cdots , \beta_r$ 过渡矩阵为 $A$ ,
向量 $\alpha$ 在两组基坐标分别为 $(x_1, x_2, \cdots , x_r)$ 和 $(y_1, y_2, \cdots , y_r)$ , 则

$$
\begin{pmatrix} x_1 \\ x_2 \\ \vdots \\ x_r \end{pmatrix}
= A \begin{pmatrix} y_1 \\ y_2 \\ \vdots \\ y_r \end{pmatrix}
\ , \ 或 \
\begin{pmatrix} y_1 \\ y_2 \\ \vdots \\ y_r \end{pmatrix} = 
A^{-1} \begin{pmatrix} x_1 \\ x_2 \\ \vdots \\ x_r \end{pmatrix}
$$

上式称为坐标变换公式

例
已知 $\beta$ 在基 $\alpha_1 = (1, 1, 1)^T, \alpha_2 = (1, 1, -1)^T, \alpha_3 = (1, -1, -1)^T$ 下的坐标为 $(1, \frac{1}{2}, - \frac{1}{2})$,
求它在标准基 $\varepsilon_1, \varepsilon_2, \varepsilon_3$ 下的坐标

$$
\begin{aligned}
 & (\alpha_1, \alpha_2, \alpha_3) = (\varepsilon_1, \varepsilon_2, \varepsilon_3) \begin{pmatrix}
  1 & 1 & 1 \\
  1 & 1 & -1 \\
  1 & -1 & -1
 \end{pmatrix}
 = (\varepsilon_1, \varepsilon_2, \varepsilon_3) A \\
 & \ \\
 & A = \begin{pmatrix}
  1 & 1 & 1 \\
  1 & 1 & -1 \\
  1 & -1 & -1
 \end{pmatrix}, 
 为由基 \varepsilon_1, \varepsilon_2, \varepsilon_3 到基 \alpha_1, \alpha_2, \alpha_3 的过渡矩阵 \\
 & \ \\
 & 则向量 \beta 在基 \varepsilon_1, \varepsilon_2, \varepsilon_3 下坐标为 \\
 & \begin{pmatrix} x_1 \\ x_2 \\ x_3 \end{pmatrix}
 = A \begin{pmatrix} 1 \\ \frac{1}{2} \\ - \frac{1}{2} \end{pmatrix}
 = \begin{pmatrix}
  1 & 1 & 1 \\
  1 & 1 & -1 \\
  1 & -1 & -1
 \end{pmatrix}
 \begin{pmatrix} 1 \\ \frac{1}{2} \\ - \frac{1}{2} \end{pmatrix}
 = \begin{pmatrix} 1 \\ 2 \\ 1 \end{pmatrix}
\end{aligned}
$$

## 3.4 欧几里德空间
### 3.4.1 向量的内积

> 定义1 设 $\alpha = (x_1, x_2, \cdots , x_n), \beta = (y_1, y_2, \cdots , y_n)$ 为两个 $n$ 维向量, 则实数 $x_1 y_1 + x_2 y_2 + \cdots + x_n y_n$ 称为向量 $\alpha, \beta$ 的内积, 记作 $(\alpha, \beta)$ , 即

$$
(\alpha, \beta) = x_1 y_1 + x_2 y_2 + \cdots x_n y_n
$$

_定义向量内积的向量空间称为欧几里德空间,  简称欧式空间_

欧式空间 $V$ 的内积与三位向量空间 $R^3$ 中的数量级一样具有以下性质

- 对称性: $(\alpha, \beta) = (\beta, \alpha)$
- 双线性性: $\begin{aligned} &(k_1 \alpha_1 + k_2 \alpha_2, \beta) = k_1 (\alpha_1, \beta) + k_2 (\alpha_2, \beta) \\
& (\alpha, k_1 \beta_1 + k_2 \beta_2) = k_2 (\alpha, \beta_1) + k_2 (\alpha, \beta_2) \end{aligned}$
- 非负性: $(\alpha, \alpha) \ge 0$

### 3.4.2 向量的长度与夹角

> 定义2 设 $\alpha = (x_1, x_2, \cdots , x_n)$ 为欧式空间 $V$ 中一向量, 定义 $\alpha$ 的长度为 

$$
\parallel \alpha \parallel = \sqrt{(\alpha, \alpha)} = \sqrt{x_1^2 + x_2^2 + \cdots + x_n^2}
$$

向量长度具有以下性质

- 非负性: $\parallel \alpha \parallel \ge 0$ , 当且仅当 $alpha = \mathbf{0}$ 时, $\parallel \alpha \parallel = 0$
- 正齐次性: $\parallel k \alpha \parallel = \left | k \right | \parallel \alpha \parallel$
- 三角不等式: $\parallel \alpha + \beta \parallel \le \parallel \alpha \parallel + \parallel \beta \parallel$
  
_长度为 $1$ 的向量称为单位向量_

设 $\alpha$ 为任一非零向量, 则 $\frac{1}{\parallel \alpha \parallel} \alpha$ 为单位向量, 即用数 $\frac{1}{\parallel \aleph \parallel}$ 乘向量 $\alpha$ , 则将向量单位化

_对于欧式空间两个向量 $\alpha = (a_1, a_2, \cdots , a_n), \beta = (b_1, b_2, \cdots , b_n)$ , 定义它们的距离为 $\parallel \alpha - \beta \parallel$ , 即_ 
$\sqrt{(a_1 - b_1)^2 + (a_2 - b_2)^2 + \cdots + (a_n - b_n)^2}$

> 定理1 向量内积满足柯西不等式

$$
(\alpha, \beta)^2 \le (\alpha, \alpha) (\beta, \beta) \ , \ \ \forall \alpha, \beta \in V
$$

等号成立当且仅当 $\alpha, \beta$ 线性相关

此不等式也写做 

$$
\left | (\alpha, \beta) \right | \le \parallel \alpha \parallel \parallel \beta \parallel
$$

证
若 $\alpha, \beta$ 线性相关, 设 $\alpha = k \beta$ , 则

$$
(\alpha, \beta)^2 = (k \beta, \beta)^2 = k^2 (\beta, \beta)^2 = (k \beta, k \beta) (\beta, \beta) = (\alpha, \alpha) (\beta, \beta)
$$

若 $\alpha, \beta$ 线性无关, 则 $\forall t, t \alpha + \beta \ne 0$ , 则

$$
(t \alpha + \beta, t \alpha + \beta) > 0
$$

即

$$
(\alpha, \alpha) t^2 + 2 (\alpha, \beta) t + (\beta, \beta) > 0
$$

则判别式 $\Delta = 4((\alpha, \beta)^2 - (\alpha, \alpha) (\beta, \beta))$ , 即

$$
(\alpha, \beta)^2 < (\alpha, \alpha) (\beta, \beta)
$$

_由可惜不等式得_

$$
\frac{\left | (\alpha, \beta) \right |}{\parallel \alpha \parallel \parallel \beta \parallel} \le 1
$$

> 定义3 设 $\alpha, \beta$ 为欧式空间 $V$ 的两个非零向量, $\alpha$ 与 $\beta$ 夹角定义为

$$
\langle \alpha, \beta \rangle = arccos \frac{(\alpha, \beta)}{\parallel \alpha \parallel \parallel \beta \parallel}
\ , \ \langle \alpha, \beta \rangle \in [0, \pi]
$$

_当 $(\alpha, \beta) = 0$ 时, 称 $\alpha, \beta$ 正交, 记作_ $\alpha \perp \beta$

$\alpha, \beta$ 非零时, 它们正交当且仅当它们夹角为 $\frac{\pi}{2}$

**零向量与任意向量都正交**

### 3.4.3 标准正交基

设 $\alpha_1, \alpha_2, \cdots , \alpha_s$ 是欧式空间 $V$ 的一组两两相交的非零向量, 则称向量组 $\alpha_1, \alpha_2, \cdots , \alpha_s$ 为一正交向量组

正交向量组一定线性无关, 设 $\alpha_1, \alpha_2, \cdots , \alpha_s$ 为一正交向量组, 令

$$
k_1 \alpha_1 + k_2 \alpha_2 + \cdots + k_s \alpha_s = \mathbf{0}
$$

等式两边与 $\alpha_i$ 做内积, 得 $k_s (\alpha_i, \alpha_i) = 0$ , 又 $\alpha_i \ne 0$ , 则 $(\alpha_i, \alpha_i) > 0$ , 故 $k_- = 0 \ (i = 1, 2, \cdots , s)$ ,
则 $\alpha_1, \alpha_2, \cdots , \alpha_s$ 线性无关s

> 定义4 欧式空间 $V$ 中有正交向量组构成的基称为 $V$ 的正交基, 若 $V$ 的一组正交基中的向量都是单位向量, 则称它为 $V$ 的标准正交基

**若欧式空间 $V$ 维数为 $m$ , 则 $V$ 中 $m$ 个向量 $\alpha_1, \alpha_2, \cdots , \alpha_m$ 是 $V$ 的标准正交基的充要条件是**

$$
(\alpha_i, \alpha_j) = \begin{cases} 0, i \ne j \\ 1, i = j \end{cases} 
\ , \ i, j = 1, 2, \cdots , m
$$

例如, $R^n$ 中, 标准基 $\varepsilon_1, \varepsilon_2, \cdots , \varepsilon_n$ 就标准正交基

欧式空间标准正交基不是唯一的, 如 $R^3$ 中标准基 $\varepsilon_1, \varepsilon_2, \varepsilon_3$ 和向量组

$$
\alpha_1 = (0, 1, 0) \ , \ \alpha_2 = (\frac{1}{\sqrt{2}}, 0, \frac{1}{\sqrt{2}})
\ , \ \alpha_3 = (\frac{1}{\sqrt{2}}, 0, - \frac{1}{\sqrt{2}})
$$

都是标准正交基

> 定义5 设 $A$ 为 $n$ 阶矩阵, 若 $A^T A = E$ , 则称 $A$ 为一个正交矩阵

- $A^T = A^{-1}$ , 即 $A^T A = A A^T = E$
- 若 $A$ 是正交矩阵, 则 $A^T$ 也是正交矩阵
- 两个正交矩阵之积也是正交矩阵
- 正交矩阵的行列式等于 $1$ 或 $-1$

> 定理2 $A$ 是正交矩阵当且仅当 $A$ 的列向量是 $R^n$ 的一组标准正交基

证

$$
\begin{aligned}
 & 设 A = (\alpha_1, \alpha_2, \cdots , \alpha_n) , 按分块矩阵乘法有 \\
 & A^T A = (\alpha_1, \alpha_2, \cdots , \alpha_n)^T (\alpha_1, \alpha_2, \cdots , \alpha_n) \\
 & = \begin{pmatrix} \alpha_1^T \\ \alpha_2^T \\ \vdots \\ \alpha_n^T \end{pmatrix} (\alpha_1, \alpha_2, \cdots , \alpha_n) = \begin{pmatrix}
  \alpha_1^T \alpha_1 & \alpha_1^T \alpha_2 & \cdots & \alpha_1^T \alpha_n \\
  \alpha_2^T \alpha_1 & \alpha_2^T \alpha_2 & \cdots & \alpha_2^T \alpha_n \\
  \vdots & \vdots &   & \vdots \\
  \alpha_n^T \alpha_1 & \alpha_n^T \alpha_2 & \cdots & \alpha_n^T \alpha_n
 \end{pmatrix} \\
 & \ \\
 & 则 A^T A = E 当且仅当 \\
 & \alpha_i^T \alpha_j = (\alpha_i, \alpha_j) = 
 \begin{cases} 1, i = j \\ 0, i \ne j \end{cases} \\
 & 即 A 的列向量 \alpha_1, \alpha_2, \cdots , \alpha_n 是 R^n 的一个标准正交基
\end{aligned}
$$

由 $A^T A = E$ 得 $A^T = A^{-1}$ , 所有也有 $AA^T = E$

类似的可证明 $A$ 是正交矩阵当且仅当 $A$ 的行向量是 $R^n$ 的一组标准正交基

因此 , $\alpha_1, \alpha_2, \cdots , \alpha_n$ 是 $R^n$ 的标准正交基的充要条件是以 $\alpha_1, \alpha_2, \cdots , \alpha_n$ 为列向量构成的矩阵是一个正交矩阵

> 定理3 设 $\alpha_1, \alpha_2, \cdots , \alpha_m$ 是欧式空间 $V$ 的一组基, 则存在 $V$ 的一组标准正交基 $\beta_1, \beta_2, \cdots , \beta_m$ , 使 $\beta_k$ 可由 $\alpha_1, \alpha_2, \cdots , \alpha_k$ 线性表示

证明

第一步: 正交化

$$
\begin{aligned}
 & 取 \gamma_1 = \alpha_1, 则 \gamma_1 \ne \mathbf{0} \\
 & 再取 \gamma_2 = \alpha_2 = \frac{(\alpha_1, \gamma_1)}{(\gamma_1, \gamma_1)} \gamma_1 \\
 & 则 \gamma_2 可由 \alpha_1, \alpha_2 线性表示, 又\alpha_1, \alpha_2线性无关, 则 \gamma_2 \ne \mathbf{0} \\
 & 且有 \ (\gamma_2, \gamma_2) = (\alpha_2, \gamma_1) - \frac{(\alpha_2, \gamma_1)}{(\gamma_1, \gamma_1)} (\gamma_1, \gamma_1) = 0 \\
 & 即 \ \gamma_1 \bot \gamma_2 \\
 & \ \\
 & 对于 1 < k < m, 可在V中取到正交的非零向量 \gamma_1, \gamma_2, \cdots, \gamma_{k - 1}, 且 \gamma_i 可由 \alpha_1, \alpha_2, \cdots, \alpha_k 线性表示 \\
 & 又 \alpha_1, \alpha_2, \cdots, \alpha_k 线性无关, 则 \gamma_k \ne \mathbf{0} \\
 & 又 \gamma_1, \gamma_2, \cdots, \gamma_{k - 1} 两两正交, 且 \\
 & (\gamma_k, \gamma_i) = (\alpha_k, \alpha_i) - \frac{(\alpha_k, \gamma_i)}{(\gamma_i, \gamma_i)} (\gamma_i, \gamma_i) = 0 \ , \ i = 1, 2, \cdots , k - 1 \\
 & 即 \gamma_1, \gamma_2, \cdots, \gamma_k 仍两两正交 \\
 & \\
 & 由数学归纳法可知, V中存在一组正交基 \gamma_1, \gamma_2, \cdots, \gamma_m, 使 \gamma_k 可由 \alpha_1, \alpha_2, \cdots, \alpha_k 线性表示 (k = 1, 2, \cdots , m)
\end{aligned}
$$

第二步: 单位化

$$
\begin{aligned}
  & 把 \gamma_1, \gamma_2, \cdots, \gamma_m 单位化, 令 \\
  & \beta_k = \frac{1}{\parallel \gamma_k \parallel} \gamma_k \ , \ k = 1, 2, \cdots , m \\
  & 则 \beta_1, \beta_2, \cdots , \beta_m 为满足要求的标准正交基
\end{aligned}
$$

上述定理提供了通过 $V$ 的一组线性无关向量组构造 $V$ 的单位正交向量组的方法, 称为 _施密特正交化过程_

例
设 $V = L(\alpha_1, \alpha_2, \alpha_3$ , 其中

$$
\alpha_1, (1, 1, 0, 0) \ , \ \alpha_2 = (1, 0, 1, 0) \ , \ \alpha_3 = (-1, 0, 0, 1)
$$

试用施密特正交化过程求 $V$ 的一组标准正交基

$$
\begin{aligned}
 & 令 \ A = \begin{pmatrix} \alpha_1 \\ \alpha_2 \\ \alpha_3 \end{pmatrix} = \begin{pmatrix}
  1 & 1 & 0 & 0 \\
  1 & - & 1 & 0 \\
  -1 & 0 & 0 & 1 
 \end{pmatrix} \\
 & r(A) = 3, \alpha_1, \alpha_2, \alpha_3 线性无关, 即 \alpha_1, \alpha_2, \alpha_3 构成 V 的一组基 \\
 & \ \\
 & 正交化: \\
 & \gamma_1 = \alpha_1 = (1, 1, 0, 0) \\
 & \gamma_2 = \alpha_2 - \frac{(\alpha_2, \gamma_1)}{(\gamma_1, \gamma_1)} \gamma_1 = (\frac{1}{2}, - \frac{1}{2}, 1, 0) = \frac{1}{2} (1, -1, 2, 0) \\
 & \gamma_3 = \alpha_3 - \frac{(\alpha_3, \gamma_1)}{(\gamma_1, \gamma_1)} \gamma_1 - \frac{(\alpha_3, \gamma_2)}{(\gamma_2, \gamma_2)} = (-\frac{1}{3}, \frac{1}{3}, \frac{1}{3}, 1) = \frac{1}{3} (-1, 1, 1, 3) \\
 & \ \\
 & 单位化: \\
 & \beta_k = \frac{\gamma_k}{\parallel \gamma_k \parallel} \\
 & \beta_1 = (\frac{1}{\sqrt{2}}, \frac{1}{\sqrt{2}}, 0, 0) \\
 & \beta_2 = (\frac{1}{\sqrt{6}}, - \frac{1}{\sqrt{6}}, \frac{2}{\sqrt{6}}, 0) \\
 & \beta_3 = (- \frac{1}{\sqrt{12}}, \frac{1}{\sqrt{12}}, \frac{1}{\sqrt{12}}, \frac{3}{\sqrt{12}})
\end{aligned}
$$

> 定理4 由标准正交基到标准正交基的过渡矩阵是正交矩阵, 反之, 由标准正交基经过渡矩阵得到的基也是标准正交基

设 $\alpha_1, \alpha_2, \cdots, \alpha_m$ 与 $\beta_1, \beta_2, \cdots , \beta_m$ 是 $m$ 维欧式空间 $V$ 的两组基, 其中 $\alpha_1, \alpha_2, \cdots, \alpha_m$ 是标准正交基, 且从 $\alpha_1, \alpha_2, \cdots, \alpha_m$ 到 $\beta_1, \beta_2, \cdots , \beta_m$ 的过渡矩阵 $A = (a_{ij})$ , 即

$$
(\beta_1, \beta_2, \cdots , \beta_m) = (\alpha_1, \alpha_2, \cdots, \alpha_m) \begin{pmatrix}
  a_{11} & a_{12} & \cdots & a_{1m} \\
  a_{21} & a_{22} & \cdots & a_{2m} \\
  \vdots & \vdots &   & \vdots \\
  a_{m1} & a_{m2} & \cdots & a_{mm}
\end{pmatrix}
$$

则 $\beta_1, \beta_2, \cdots , \beta_m$ 为标准正交基当且仅当 

$$
(\beta_i, \beta_j) = a_{1i}a_{1j} + a_{2i}a_{2j} + \cdots + a_{mi}a_{mj} = \begin{cases}
  & 1 \ , \ i = j \\
  & 0 \ , \ i \ne j
\end{cases}
$$

上式等价于

$$
A^TA = E
$$

即 $A$ 为正交矩阵

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

> 推论1 若 $n$ 阶矩阵 $A$ $b$ 个互异的特征值 $\lambda_1, \lambda_2, \cdots , \lambda_n$