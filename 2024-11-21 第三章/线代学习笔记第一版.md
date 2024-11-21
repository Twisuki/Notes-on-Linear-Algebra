**线代学习笔记第一版**
# 1 行列式
## 1.1 方程组与行列式
### 1.1.1 二元线性方程组和二阶行列式
### 1.1.2 三元线性方程组和三阶行列式
## 1.2 $n$ 阶行列式
### 1.2.1 排序与逆序数
### 1.2.2 $n$ 阶行列式

$$
\begin{vmatrix}
 a_{11} & a_{12} & \dots & a_{1n} \\
 a_{21} & a_{22} & \dots & a_{2n} \\
 \vdots & \vdots &   & \vdots \\
 a_{n1} & a_{n2} & \dots & a_{nn}
\end{vmatrix}
= \sum_{(j_1j_2 \dots j_n)} (-1)^{\tau (j_1j_2 \dots j_n)}
a_{1j_1}a_{2j_2} \dots a_{nj_n}
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
 a_{11} & a_{12} & \dots & a_{1n} \\
 \vdots & \vdots &   & \vdots \\
 a_{i1} + a'_{i1} & a_{i2} + a'_{i2} & \dots & a_{in} + a'_{in} \\
 \vdots & \vdots &   & \vdots \\
 a_{n1} & a_{n2} & \dots & a_{nn}
\end{vmatrix}
=
\begin{vmatrix}
 a_{11} & a_{12} & \dots & a_{1n} \\
 \vdots & \vdots &   & \vdots \\
 a_{i1} & a_{i2} & \dots & a_{in} \\
 \vdots & \vdots &   & \vdots \\
 a_{n1} & a_{n2} & \dots & a_{nn}
\end{vmatrix}
+
\begin{vmatrix}
 a_{11} & a_{12} & \dots & a_{1n} \\
 \vdots & \vdots &   & \vdots \\
 a'_{i1} & a'_{i2} & \dots & a'_{in} \\
 \vdots & \vdots &   & \vdots \\
 a_{n1} & a_{n2} & \dots & a_{nn}
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
- $\dots$
- 成为上三角后, 计算主对角线元素乘积
  
## 1.4 行列式按行展开
### 1.4.1 拉普拉斯展开定理

> 定义1 行列式中划去 $a_{ij}$ 所在行列, 剩下元素构成的行列式称 $a_{ij}$ 的余子式, 记作 $M_{ij}$ ; 余子式加上代数符号 $(-1)^{i + j}$ 称为代数余子式, 记作 $A_{ij}$ , 即 $A_{ij} = (-1)^{i + j} M_{ij}$

> 定理1 (拉普拉斯展开定理)行列式等于其任一行各元素与其代数余子式乘积之和

即
$$
D = \sum_{k = 1}^{n} a_{ik}A_{ik}, i = 1, 2, \dots ,n
$$

> 定理2 行列式任一行各元素与另一行对应元素代数余子式乘积之和为零

即
$$
\sum_{k = 1}^{n} a_{ik}A_{jk} = 0 \\
i \ne j, i = 1, 2, \dots , n
$$

### 1.4.2 拉普拉斯展开定理应用
> 范德蒙德行列式

$$
D_n = 
\begin{vmatrix}
 1 & 1 & \dots & 1 \\
 x_1 & x_2 & \dots & x_n \\
 x_1^2 & x_2^2 & \dots & x_n^2 \\
 \vdots & \vdots &   & \vdots \\
 x_1^{n - 1} & x_2^{n - 1} & \dots & x_n^{n - 1}
\end{vmatrix}
= \prod_{1 \le j < i \le n}
(x_i - x_j)
$$
## 1.5 克拉默法则
> 定理1 (克拉默法则)

$n$ 个方程的 $n$ 元方程组
$$
\begin{cases}
 a_{11}x_1 + a_{12}x_2 + \dots +a_{1n}x_n = b_1 \\
 a_{21}x_1 + a_{22}x_2 + \dots +a_{2n}x_n = b_2 \\
 \dots \dots \dots \dots \\
 a_{n1}x_1 + a_{n2}x_2 + \dots +a_{nn}x_n = b_n
\end{cases}
$$
若其系数行列式
$$
D =
\begin{vmatrix}
 a_{11} & a_{12} & \dots & a_{1n} \\
 a_{21} & a_{22} & \dots & a_{2n} \\
 \vdots & \vdots &   & \vdots \\
 a_{n1} & a_{n2} & \dots & a_{nn}
\end{vmatrix}
\ne 0
$$
则线性方程组有唯一解
记作
$$
x_1 = \frac{D_1}{D} , x_2 = \frac{D_2}{D} , \dots , x_n = \frac{D_n}{D}
$$
其中 $D_j(j = 1, 2, \dots , n)$ 为用常数项 $b_1, b_2, \dots , b_n$ 代替 $D$ 中 $j$ 列对应元素所得行列式
即
$$
D_j = 
\begin{vmatrix}
 a_{11} & \dots & a_{1, j - 1} & b_1 & a_{1, j + 1} & \dots & a_{1n} \\
 \vdots &   & \vdots & \vdots & \vdots &   & \vdots \\
 a_{n1} & \dots & a_{n, j - 1} & b_n & a_{n, j + 1} & \dots & a_{nn}
\end{vmatrix}
$$

# 2 矩阵
## 2.1 矩阵及其运算
### 2.1.1 矩阵的概念
> 定义1 $m \times n$ 个数 $a_{ij} (i = 1, 2, \dots , m; j = 1, 2, \dots , n)$ 有序排为 $m$ 行 $n$ 列的数表称 $m$ 行 $n$ 列的矩阵, 简称 $m \times n$ 矩阵, 记作 $(a_{ij})_{m \times n}$

$$
\begin{pmatrix}
 a_{11} & a_{12} & \dots & a_{1n} \\
 a_{21} & a_{22} & \dots & a_{2n} \\
 \vdots & \vdots &   & \vdots \\
 a_{m1} & a_{m2} & \dots & a_{mn}
\end{pmatrix}
$$

矩阵可以和线性方程组形成一一对应关系

$$
\begin{cases}
 a_{11}x_1 + a_{12}x_2 + \dots +a_{1n}x_n = b_1 \\
 a_{21}x_1 + a_{22}x_2 + \dots +a_{2n}x_n = b_2 \\
 \dots \dots \dots \dots \\
 a_{m1}x_1 + a_{m2}x_2 + \dots +a_{mn}x_n = b_m
\end{cases}
$$

$$
\begin{pmatrix}
 a_{11} & a_{12} & \dots & a_{1n} & b_1 \\
 a_{21} & a_{22} & \dots & a_{2n} & b_2 \\
 \vdots & \vdots &   & \vdots & \vdots \\
 a_{m1} & a_{m2} & \dots & a_{mn} & b_m
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
A^m = A \cdot A \cdot \dots \cdot A
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

简记为 $diag(a_{11}, a_{22}, \dots , a_{nn})$

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
 \star & \star & \dots & \star & \dots & \star \\
 \color{#00aaff}{0} & \star & \dots & \star & \dots & \star \\
 \vdots & \color{#00aaff}{\vdots} &   & \vdots &   & \vdots \\
 0 & \color{#00aaff}{0} & \color{#00aaff}{\dots} & \star & \dots & \star \\
 \vdots & \vdots &   & \color{#00aaff}{\vdots} &   & \vdots \\
 0 & 0 & \dots & \color{#00aaff}{0} & \color{#00aaff}{\dots} & \color{#00aaff}{0}
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
 \color{#00aaff}{1} & \color{#00aaff}{0} & \color{#00aaff}{\dots} & \color{#00aaff}{0} & 0 & \dots & 0 \\
 \color{#00aaff}{0} & \color{#00aaff}{1} & \color{#00aaff}{\dots} & \color{#00aaff}{0} & 0 & \dots & 0 \\
 \color{#00aaff}{\vdots} & \color{#00aaff}{\vdots} &   & \color{#00aaff}{\vdots} & \vdots &   & \vdots \\
 \color{#00aaff}{0} & \color{#00aaff}{0} & \color{#00aaff}{\dots} & \color{#00aaff}{1} & 0 & \dots & 0 \\
 0 & 0 & \dots & 0 & 1 & \dots & 0 \\
 \vdots & \vdots &   & \vdots & \vdots &   & \vdots \\
 0 & 0 & \dots & 0 & 0 & \dots & 0
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
  &   &   & 0 &   & \dots &   & 1 \\
  &   &   &   & \ddots \\
  &   &   & \vdots &   & 1 &   & \vdots \\
  &   &   &   &   &   & \ddots \\
  &   &   & 1 &   & \dots &   & 0 \\
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
  &   & 1 & \dots & \lambda \\
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
B = P_tP_{t-1} \dots P_1AQ_1Q_2 \dots Q_l
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

> 推论1 矩阵 $A$ 经过有限次初等行变换 $P_1, P_2, \dots , P_s$ 变为矩阵 $B$ , 则
$$
r(B) = r(P_sP_{s - 1} \dots P_1A) = r(A)
$$

> 推论2 矩阵 $A$ 经过有限次初等列变换 $Q_1, Q_2, \dots , Q_t$ 变为矩阵 $B$ , 则
$$
r(B) = r(AQ_1Q_2 \dots Q_t) = r(A)
$$

> 推论3 矩阵 $A$ 经过有限次初等行变换 $P_1, P_2, \dots , P_s$ 及有限次初等列变换 $Q_1, Q_2, \dots , Q_t$ 变为矩阵 $B$ , 则
$$
r(B) = r(P_sP_{s - 1} \dots P_1AQ_1Q_2 \dots Q_t) = r(A)
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

- $(A_1A_2 \dots A_m)^{-1} = A_m^{-1} \dots A_2^{-1}A_1^{-1}$
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
 a_{11} & a_{12} & \dots & a_{1n} \\
 a_{21} & a_{22} & \dots & a_{2n} \\
 \vdots & \vdots &   & \vdots \\
 a_{n1} & a_{n2} & \dots & a_{nn}
\end{pmatrix}
$$ 

$A_{ij}$ 为行列式 $\left | A \right |$ 中元素 $a_{ij}$ 的代数余子式, 则矩阵

$$
A^{\star} = 
\begin{pmatrix}
 A_{11} & A_{12} & \dots & A_{1n} \\
 A_{21} & A_{22} & \dots & A_{2n} \\
 \vdots & \vdots &   & \vdots \\
 A_{n1} & A_{n2} & \dots & A_{nn}
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

> 定理5 若 $n$ 阶方阵 $A$ 可逆, 则存在有限个初等矩阵 $P_1, P_2, \dots , P_m$ , 使
$$
A = P_1P_2 \dots P_m
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
 A_{11} & A_{12} & \dots & A_{1l} \\
 A_{21} & A_{22} & \dots & A_{2l} \\
 \vdots & \vdots &   & \vdots \\
 A_{t1} & A_{t2} & \dots & A_{tl}
\end{pmatrix}
\\ \
\\
B = 
\begin{pmatrix}
 B_{11} & B_{12} & \dots & B_{1r} \\
 B_{21} & B_{22} & \dots & B_{2r} \\
 \vdots & \vdots &   & \vdots \\
 B_{l1} & B_{l2} & \dots & B_{lr}
\end{pmatrix}
$$

其中每个小矩阵 $A_{ij}$ 为 $s_i \times \color{#00aaff}{n_j}$ 矩阵, 
每个小矩阵 $B_{ij}$ 为 $\textcolor{#00aaff}{n_i} \times m_j$ 矩阵

则

$$
C = AB = 
\begin{pmatrix}
 C_{11} & C_{12} & \dots & C_{1r} \\
 C_{21} & C_{22} & \dots & C_{2r} \\
 \vdots & \vdots &   & \vdots \\
 C_{t1} & C_{t2} & \dots & C_{tr}
\end{pmatrix}
$$

其中

$$
C_{pq} = A_{p1}B_{1q} + A_{p2}{2q} + \dots + A_{pl}{lq} \\
= \sum_{k = 1}^{l} A_{pk}B_{kq} \ (p = 1, 2, \dots , t; q = 1, 2, \dots , r)
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
 A_1 & O & \dots & O \\
 O & A_2 & \dots & O \\
 \vdots & \vdots &   & \vdots \\
 O & O & \dots & A_m
\end{pmatrix}
$$

其中 $A_i (i = 1, 2, \dots , m)$ 均为方阵, 称 $A$ 为准对角矩阵

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

**若方阵 $A_1, A_2, \dots , A_m$ 均可逆, 则有**

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
 a_{11} & \dots & a_{1n} & 0 & \dots & 0 \\
 \vdots &   & \vdots & \vdots &   & \vdots \\
 a_{n1} & \dots & a_{nn} & 0 & \dots & 0 \\
 c_{11} & \dots & c_{1n} & b_{11} & \dots & b_{1m} \\
 \vdots &   & \vdots & \vdots &   & \vdots \\
 c_{m1} & \dots & c_{mn} & b_{m1} & \dots & b_{mm}
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

若由 $n$ 个部门 $C_1, C_2, \dots , C_n$ ,
假设 $C_i$ 部门生产一个单位产品需要消耗 $C_1, C_2, \dots , C_n$ 各部门产品数分别为
$a_{i1}, a_{i2}, \dots , a_{in}$ , $C_i$ 部门的产品需求量为 $d_i$ ,
$C_i$ 部门总产出为 $x_i \ (i = 1, 2, \dots , n)$

则

$$
x_i = d_i + a_{i1} x_1 + a_{i2} x_2 + \dots + a_{in} x_n \ , \ \ i = 1, 2, \dots , n
$$

记

$$
X = \begin{pmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{pmatrix} \ , \
d = \begin{pmatrix} d_1 \\ d_2 \\ \vdots \\ d_n \end{pmatrix} \ , \
A = \begin{pmatrix}
 a_{11} & a_{12} & \dots & a_{1n} \\
 a_{21} & a_{22} & \dots & a_{2n} \\
 \vdots & \vdots &   & \vdots \\
 a_{n1} & a_{n2} & \dots & a_{nn}
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

> 定义1 由 $n$ 个数组成的有序数组 $(a_1, a_2, \dots , a_n)$ 称为一个 $n$ 维向量, 记作

$$
\alpha = (a_1, a_2, \dots , a_n)
$$

其中数 $a_i(i = 1, 2, \dots , n)$ 称为向量 $\alpha$ 的第 $i$ 个分量或第 $i$ 个坐标

有时 $n$ 维向量也可写成一列的形式, 即

$$
\alpha = 
\begin{pmatrix}
 a_1 \\ a_2 \\ \vdots \\ a_n
\end{pmatrix}
$$

_上述两种向量分别称为行向量和列向量, 列向量为也记作 $\alpha = (a_1, a_2, \dots , a_n)^T$_

$n$ 维向量可视为 $1 \times n$ 或 $n \times 1$ 的矩阵, 则对于 $n \times m$ 矩阵 $A = (a_{ij})_{n \times m}$

$$
A = (\alpha_1, \alpha_2, \dots , \alpha_m) = 
\begin{pmatrix}
 \beta_1 \\ \beta_2 \\ \vdots \\ \beta_n
\end{pmatrix}
$$

其中 $\alpha_j = (a_{1j}, a_{2j}, \dots , a_{nj})^T \ (j = 1, 2, \dots , m)$ 为 $n$ 维列向量, 
$\beta_i = (a_{i1}, a_{i2}, \dots , a_{im}) \ (i = 1, 2, \dots , n)$ 为 $m$ 维行向量

**若两个 $n$ 维向量对应分量都相等, 则向量相等**

$$
\begin{aligned}
 & \alpha = (a_1, a_2, \dots , a_n) \ , \ \beta = (b_1, b_2, \dots , b_n) \\
 & a_i = b_i \ , \ i = 1, 2, \dots , n \\
 & 则 \ \alpha = \beta
\end{aligned}
$$

**分量均为零的向量为零向量, 记作 $\mathbf{0}$ , 即 $\mathbf{0} = (0, 0, \dots , 0)$**

**向量 $(-a_1, -a_2, \dots , -a_n)$ 称为向量 $(a_1, a_2, \dots , a_n)$ 的负向量, 记作 $-\alpha$**

> 定义2 向量加法与数乘

两个 $n$ 维向量

$$
\alpha = (a_1, a_2, \dots , a_n) \ , \ \beta = (b_1, b_2, \dots , b_n)
$$

则有

$$
\begin{align}
 & \alpha + \beta = (a_1 + b_1, a_2 + b_2, \dots , a_n + b_n) \\
 & \alpha - \beta = \alpha + (-\beta) = (a_1 - b_1, a_2 - b_2, \dots , a_n - b_n)
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

> 定义3 设 $\alpha_1, \alpha_2, \dots , \alpha_r$ 为 $r$ 个 $n$ 维向量, $k_1, k_2, \dots , k_r$ 为 $r$ 个实数, 称

$$
k_1\alpha_1 + k_2\alpha_2 + \dots + k_r\alpha_r
$$

为向量组 $\alpha_1, \alpha_2 , \dots , \alpha_r$ 的一个线性组合, $k_1, k_2, \dots , k_r$ 称相应的组合系数

若 $\beta$ 可以表示为向量组 $\alpha_1, \alpha_2, \dots , \alpha_r$ 的一个线性组合, 则称 $\beta$ 可以由向量组 $\alpha_1, \alpha_2, \dots , \alpha_r$ 线性表示

- 向量组 $\alpha_1, \alpha_2, \dots , \alpha_r$ 中每个向量都可以由该向量组线性表示

$$
\alpha_i = 0 \alpha_1 + \dots + 1 \alpha_i + \dots + 0 \alpha_r
$$

- 若 $\varepsilon_1 = (1, 0, 0) \ , \ \varepsilon_2 = (0, 1, 0) \ , \ \varepsilon_3 = (0, 1, 1)$ , 则对于任意 $\alpha = (a_1, a_2, a_3) \in R^3$ , 有

$$
\alpha = a_1 \varepsilon_1 + a_2 \varepsilon_2 + a_3 \varepsilon_3
$$

即 $R^3$ 中任意向量都可由向量组 $\varepsilon_1 , \varepsilon_2 , \varepsilon_1$ 线性表示

- $n$ 维零向量可以由任一 $n$ 维向量组线性表示

$$
\mathbf{0} = 0 \alpha_1 + 0 \alpha_2 + \dots + 0 \alpha_r
$$

- 用线性组合关系表示方程组

$$
\begin{aligned}
 & \begin{cases}
  a_{11} x_1 + a_{12} x_2 + \dots + a_{1n} x_n = b_1 \\
  a_{21} x_1 + a_{22} x_2 + \dots + a_{2n} x_n = b_2 \\
  \dots \dots \dots \dots \\
  a_{m1} x_1 + a_{m2} x_2 + \dots + a_{mn} x_n = b_m
  \end{cases} \\
 & \ \\
 & 令 \ \alpha_j = \begin{pmatrix}
  a_{1j} \\ a_{2j} \\ \vdots \\ a_{mj}
  \end{pmatrix}
  \ (j = 1, 2, \dots , n) \
  , \ \beta = \begin{pmatrix}
  b_1 \\b_2 \\ \vdots \\ b_m
  \end{pmatrix} \\
  & \ \\
  & 则有 \ \beta = x_1 \alpha_1 + x_2 \alpha_2 + \dots + x_n \alpha_n \\
  & 则方程是否有解, 即是否存在一组数 k_1, k_2, \dots , k_n 使下列线性关系式成立 \\
  & \beta = k_1 \alpha_1 + k_2 \alpha_2 + \dots + k_n \alpha_n
\end{aligned}
$$

* $\beta$ 能由向量组 $\alpha_1, \alpha_2, \dots , \alpha_n$ 表示且表示唯一, 等价于方程组有唯一解
* $\beta$ 能由向量组 $\alpha_1, \alpha_2, \dots , \alpha_n$ 表示且表示不唯一, 等价于方程组有无穷组解
* $\beta$ 不能由向量组 $\alpha_1, \alpha_2, \dots , \alpha_n$ 表示, 等价于方程组无解

> 定义4 两向量组

$$
A: \ \alpha_1, \alpha_2, \dots , \alpha_s \ ; \ B: \ \beta_1, \beta_2, \dots , \beta_t
$$

若向量组 $B$ 中每个元素都能由向量组 $A$ 线性表示, 则称向量组 $B$ 能由向量组 $A$ 线性表示

若向量组 $A$ 与向量组 $B$ 能互相线性表示, 则称这两个向量组等价

若向量组 $B$ 能由向量组 $A$ 线性表示, 则存在系数 $k_{ij}(i = 1, 2, \dots , s \ , \ j = 1, 2, \dots , t)$ , 使

$$
\begin{cases}
 \beta_1 = k_{11} \alpha_1 + k_{21} \alpha_2 + \dots + k_{s1} \alpha_s \\
 \beta_2 = k_{12} \alpha_1 + k_{22} \alpha_2 + \dots + k_{s2} \alpha_s \\
 \dots \dots \dots \dots \\
 \beta_t = k_{1t} \alpha_1 + k_{21} \alpha_2 + \dots + k_{st} \alpha_s
\end{cases}
$$

上式可简记为

$$
(\beta_1, \beta_2 , \dots , \beta_t) = (\alpha_1, \alpha_2, \dots , \alpha_s)
\begin{pmatrix}
 k_{11} & k_{12} & \dots & k_{1t} \\
 k_{21} & k_{22} & \dots & k_{2t} \\
 \vdots & \vdots &   & \vdots \\
 k_{s1} & k_{s2} & \dots & k_{st}
\end{pmatrix}
$$

令 $B = (\beta_1 , \beta_2 , \dots , \beta_t) \ , \ A = (\alpha_1, \alpha_2, \dots , \alpha_s)$ , 则上式表示 $B$ 的列向量组可以由 $A$ 的列向量组表示

令 $K = (k_{ij})_{s \times t}$ , 称　$K$ 为向量组 $B$ 由向量组 $A$ 表示的系数矩阵, 简写为

$$
B = AK
$$

> 定理1 向量组线性表示关系的传递性

若向量组 $C: \ \gamma_1, \gamma_2, \dots , \gamma_m$ 可由向量组 $B: \ \beta_1, \beta_2, \dots , \beta_t$ 线性表示,
向量组 $B: \ \beta_1, \beta_2, \dots , \beta_t$ 可由向量组 $A: \ \alpha_1, \alpha_2, \dots , \alpha_t$ 线性表示, 
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

> 定义1 对于向量组 $\alpha_1 , \alpha_2 , \dots , \alpha_s \ (s \ge 1)$ ,
若存在不全为零的实数 $k_1, k_2, \dots , k_s$ , 使

$$
k_1 \alpha_1 + k_2 \alpha_2 + \dots + k_s \alpha_s = \mathbf{0}
$$

则称向量组 $\alpha_1 , \alpha_2 , \dots , \alpha_s$ 线性相关, 否则称之为线性无关

_若 $\alpha_1 , \alpha_2 , \dots , \alpha_s \ (s \ge 1)$ 线性无关, 则_

$$
k_1 \alpha_1 + k_2 \alpha_2 + \dots + k_s \alpha_s = \mathbf{0}
$$

_必可得_ $k_1 = k_2 = \dots = k_s = \mathbf{0}$

**两个单位向量线性相关即表示它们共线, 三个三位向量线性相关即表示它们共面, 反之仍成立**

> 定理1 向量组 $\alpha_1 , \alpha_2 , \dots , \alpha_s \ (s \ge 2)$ 线性相关, 
当且仅当向量组里至少有一个向量可由其余向量线性表示

$$
\begin{aligned}
 & 对于 \ \alpha_1 , \alpha_2 , \dots , \alpha_s \\
 & \ \\
 & 若其中一个向量可由其他向量线性表示 \\
 & 设 \ \alpha_s = k_1 \alpha_1 + k_2 \alpha_2 + \dots + k_{s - 1} \alpha_{s - 1} \\
 & 则\ k_1 \alpha_1 + k_2 \alpha_2 + \dots + k_{s - 1} \alpha_{s - 1} + (-1) \alpha_s = \mathbf{0} \\
 & \ \\
 & 反之, 若 \alpha_1 , \alpha_2 , \dots , \alpha_s 线性相关, 则有 \\
 & k_1 \alpha_1 + k_2 \alpha_2 + \dots + k_s \alpha_s = \mathbf{0} \\
 & 设 k_s \ne 0, 则 \\
 & \alpha_s = - \frac{k_1}{k_s} \alpha_1 - \frac{k_2}{k_s} \alpha_2 - \dots - \frac{k_{s - 1}}{k_s} \alpha_{s - 1} \\
 & \ \\
 & 即 \alpha_s 可由其他向量线性表示
\end{aligned}
$$

_含零向量的向量组一定线性相关_

$$
\begin{aligned}
 & 若向量组 \alpha_1 , \alpha_2 , \dots , \alpha_s 中 \alpha_1 = \mathbf{0} \\
 & 则 \ 1 \cdot \alpha_1 + 0 \cdot \alpha_2 + 0 \cdot \alpha_3 + \dots + 0 \cdot \alpha_s = \mathbf{0}
\end{aligned}
$$

> 定理2 若向量组中有一个部分组线性相关, 则向量组也线性相关;
若向量组线性无关, 则其任何部分组线性无关

> 定理3 若向量组 $\alpha_1 , \alpha_2 , \dots , \alpha_s$ 线性无关,
而向量组 $\alpha_1 , \alpha_2 , \dots , \alpha_s, \beta$ 线性相关,
则 $\beta$ 可由向量组 $\alpha_1 , \alpha_2 , \dots , \alpha_s$ 线性表示且表示法唯一

$$
\begin{aligned}
 & k_1 \alpha_1 + k_2 \alpha_2 + \dots + k_s \alpha_s + k \beta = \mathbf{0} \\
 & \ \\
 & 若 k = 0, 则有 \ k_1 \alpha_1 + k_2 \alpha_2 + \dots + k_s \alpha_s = \mathbf{0} \\
 & 且 k_1, k_2, \dots , k_s 不全为零, 这与 \alpha_1 , \alpha_2 , \dots , \alpha_s 线性无关矛盾 \\
 & 故 k \ne 0 \\
 & \ \\
 & 则 \beta = - \frac{k_1}{k} \alpha_1 - \frac{k_2}{k} \alpha_2 - \dots - \frac{k_{s}}{k} \alpha_{s} \\
 & 即 \beta 可由 \alpha_1 , \alpha_2 , \dots , \alpha_s 线性表示 \\
 & \ \\
 & 若存在两组数 t_1, t_2, \dots , t_s \ , \ l_1, l_2, \dots , l_s 使 \\
 & \beta = t_1 \alpha_1 + t_2 \alpha_2 + \dots + t_s \alpha_s = l_1 \alpha_1 + l_2 \alpha_2 + \dots + l_s \alpha_s \\
 & 则 \ (t_1 - l_1) \alpha_1 + (t_2 - l_2) \alpha_2 + \dots + (t_s - l_s) \alpha_s = \mathbf{0} \\
 & \ \\
 & 又 \alpha_1 , \alpha_2 , \dots , \alpha_s 线性无关, 则 t_i = l_i \ (i = 1, 2, \dots , s) \\
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
  a_{11} & a_{12} & \dots & a_{1n} \\
  a_{21} & a_{22} & \dots & a_{2n} \\
  \vdots & \vdots &   & \vdots \\
  a_{m1} & a_{m2} & \dots & a_{mn}
 \end{pmatrix} = \begin{pmatrix}
  \alpha_1 \\ \alpha_2 \\ \vdots \\ \alpha_m
 \end{pmatrix} \\
 & 其中 \ \alpha_i = (a_{i1}, a_{i2}, \dots , a_{in}) \ (i = 1, 2, \dots , m) \\
 & \ \\
 & 由矩阵秩的定义, A 存在一个不为零的r阶子式, 设A左上角的r阶子式不为零 \\
 & \left | D \right | = \begin{vmatrix}
  a_{11} & a_{12} & \dots & a_{1r} \\
  a_{21} & a_{22} & \dots & a_{2r} \\
  \vdots & \vdots &   & \vdots \\
  a_{r1} & a_{r2} & \dots & a_{rr}
 \end{vmatrix} \ne 0 \\
 & \ \\
 & 若 \alpha_1, \alpha_2, \dots , \alpha_r线性相关, 则设 \\
 & \alpha_r = k_1 \alpha_1 + k_2 \alpha_2 + \dots + k_{r - 1} \alpha_{r - 1} \\
 & \ \\
 & \left | D \right | \xrightarrow[]{(r_1, r_2, \dots , r_{r - 1}) \times (-k_1, -k_2, \dots , -k_{r - 1}) + r_r} \cdots \\
 & 则 \left | D \right | 最后一行圈化为零, 即 \left | D \right | = 0, 与假设矛盾 \\
 & 则\alpha_1, \alpha_2, \dots , \alpha_r线性无关 \\
 & \ \\
 & \alpha_1, \alpha_2, \dots , \alpha_r向量组中每个向量都能由它本事线性表示, 则只需证\alpha_k \ (k > r)时能由向量组线性表示 \\
 & \ \\
 & \left | D_t \right | = \begin{vmatrix}
  \color{#00aaff}{a_{11}} & \color{#00aaff}{\dots} & \color{#00aaff}{a_{1r}} & a_{1t} \\
  \color{#00aaff}{a_{21}} & \color{#00aaff}{\dots} & \color{#00aaff}{a_{2r}} & a_{2t} \\
  \color{#00aaff}{\vdots} &   & \color{#00aaff}{\vdots} & \vdots \\
  \color{#00aaff}{a_{r1}} & \color{#00aaff}{\dots} & \color{#00aaff}{a_{rr}} & a_{rt} \\
  a_{k1} & \dots & a_{kr} & a_{kt}
 \end{vmatrix}, \ t = 1, 2, \dots , n \\
 & \ \\
 & t \le r时, D_t 最后一列与前面某列相同, \left | D_t \right | = 0 \\
 & t > r 时, \left | D_t \right | 为A的r + 1阶子式, 根据秩的定义, 同样\left | D_t \right | = 0 \\
 & \ \\
 & 展开\left | D_t \right |最后一列, 得 \\
 & a_{1t} A_1 + a_{2t} A_2 + \dots + a_{rt} A_r + a_{kt} \left | D \right | = 0 \\
 & A_1, A_2, \dots , A_r分别为a_{1t}, a_{2t}, \dots , a_{rt} 的代数余子式	, 取值与t无关 \\
 & \ \\
 & \left | D \right | \ne 0 \Rightarrow a_{kt} = - \frac{A_1}{\left | D \right |} a_{1t} - \frac{A_2}{\left | D \right |} a_{2t}
 - \dots - \frac{A_r}{\left | D \right |} a_{rt} \ , \ t = 1, 2, \dots , n \\
 & 则 \ (a_{k1}, a_{k2}, \dots , a_{kn}) = - \frac{A_1}{\left | D \right |} (a_{11}, a_{12}, \dots , a_{1n})
 - \dots - \frac{A_r}{\left | D \right |} (a_{r1}, a_{r2}, \dots , a_{rn}) \\
 & 即 \ \alpha_k = - \frac{A_1}{\left | D \right |} \alpha_1 - \frac{A_2}{\left | D \right |} \alpha_2
 - \dots - \frac{A_r}{\left | D \right |} \alpha_r \\
 & \alpha_k 可由 \alpha_1, \alpha_2, \dots , \alpha_r 线性表示 \\
 & \ \\
 & A \rightarrow A^T , 则可证关于列向量的结论
\end{aligned}
$$

> 推论1 向量组线性相关的矩阵判别法

设 $\alpha_1, \alpha_2, \dots , \alpha_s$ 为一 $n$ 维列向量组, 令

$$
A = (\alpha_1, \alpha_2, \dots , \alpha_s)
$$

为 $n \times s$矩阵,
则 $\alpha_1, \alpha_2, \dots , \alpha_s$ 线性相关的充要条件是 $r(A) < s$,
线性无关的充要条件是 $r(A) = s$

特别地, 当 $s = n$ 时, 线性相关充要条件为 $\left | A \right | = 0$

> 推论2 $m > n$ 时,  $m$个$n$维向量一定线性相关

### 3.2.3 向量组的秩

> 定义2 如果向量组 $A$ 中部分组 $\alpha_1, \alpha_2, \dots , \alpha_r$ 满足条件

- $\alpha_1, \alpha_2, \dots , \alpha_r$ 线性无关
- 向量组 $A$ 中每个向量都可由 $\alpha_1, \alpha_2, \dots , \alpha_r$ 线性表示

则称 $\alpha_1, \alpha_2, \dots , \alpha_r$ 为向量组 $A$ 的一个最大无关组或极大无关组

_一个向量组的最大无关组与该向量组等价, 且线性无关向量组最大无关组为它本身_

例
向量组 $\alpha_1 = (1, 0, 0), \alpha_2 = (1, 1, 0), \alpha_3 = (2, 1, 0)$ 中, $\alpha_1, \alpha_2$ 线性无关,
而 $\alpha_3 = \alpha_1 + \alpha_2$ , 所以 $\alpha_1, \alpha_2$ 为向量组的一个最大无关组,

同理 $\alpha_1, \alpha_3$和 $\alpha_2, \alpha_3$ 也为向量组的最大无关组

> 定理5 由有限个行向量 $\alpha_1, \alpha_2, \dots , \alpha_s$ 组成的向量组的任一最大无关组中所含的向量个数均相等,
且等于下列矩阵的秩

$$
A = \begin{pmatrix} \alpha_1 \\ \alpha_2 \\ \dots \\ \alpha_s \end{pmatrix}
$$

证明

$$
\begin{aligned}
 & 设向量组 \alpha_{i_1}, \alpha_{1_2}, \dots , \alpha_{i_k} 为向量组 \alpha_1, \alpha_2, \dots , \alpha_s 的任一最大无关组 \\
 & \ \\
 & 令 \ B = \begin{pmatrix} \alpha_{i_1} \\ \alpha_{i_2} \\ \vdots \\ \alpha_{i_k} \end{pmatrix} \\
 & \ \\
 & 因为 \alpha_{i_1}, \alpha_{1_2}, \dots , \alpha_{i_k} 线性无关, 由推论1得, r(B) = k \\
 & 又B的行向量都是A的行向量, 则B的子式, 要么是A的子式, 要么与A的子式相差一个符号 \\
 & 则B的不为零的子式最高阶数小于或等于A的不为零子式的最高阶数, 即 k \le r(A) \\
 & \ \\
 & 由于 \alpha_{i_1}, \alpha_{1_2}, \dots , \alpha_{i_k} 为向量组 \alpha_1, \alpha_2, \dots , \alpha_s 的一个最大无关组, 
 则对于每个a_j \ (j \ne i_1, i_2, \dots , i_k) \\
 & 有 \ a_j = l_{j1} \alpha_{i_1} + l_{j2} \alpha_{i_2} + \dots + l_{jk} \alpha_{i_k} \\
 & \ \\
 & A \xrightarrow[]{r_j + (r_{i_1}, r_{i_2}, \dots , r_{i_k}) \times (-l_{j1}, -l_{j2}, \dots , -l_{jk})} , 则第 j 行化为零
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
 & A \xrightarrow[\dots]{\dots} \begin{pmatrix}
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

> 定理7 若线性无关向量组 $\alpha_1, \alpha_2, \dots , \alpha_s$ 可由向量组 $\beta_1, \beta_2, \dots , \beta_t$ 线性表示, 则 $s \le t$

证明

$$
\begin{aligned}
 & 设n维列向量 \alpha_i, \beta_j \ (i = 1, 2, \dots , s \ ; \ j = 1, 2, \dots , t) , 令 \\
 & A = (\alpha_1, \alpha_2, \dots , \alpha_s) \ , \ B = (\alpha_1, \alpha_2, \dots , \alpha_s, \beta_1, \beta_2, \dots , \beta_t) \\
 & \ \\
 & 由于A的任一子式都为B的一个子式, 咕 r(A) \le r(B) \\
 & 又 \alpha_1, \alpha_2, \dots , \alpha_s 线性无关, 则r(A) = s \le r(B) \\
 & \ \\
 & 又 alpha_1, \alpha_2, \dots , \alpha_s 可由 \beta_1. \beta_2, \dots , \beta_t 线性表示, 则 \\
 & B = (\alpha_1, \alpha_2, \dots , \alpha_s, \beta_1, \beta_2, \dots , \beta_t) \rightarrow 
 C = (\mathbf{0}, \mathbf{0}, \dots , \mathbf{0}, \beta_1, \beta_2, \dots , \beta_t) \\
 & 则 r(B) = r(C) \le t, \ s \le t
 
 \end{aligned}
$$

**定理7等价表示**

向量组 $\alpha_1, \alpha_2, \dots , \alpha_s$ 可由向量组 $\beta_1, \beta_2, \dots , \beta_t$ 线性表示, 且 $s > t$ ,
则向量组 $\alpha_1, \alpha_2, \dots , \alpha_s$ 线性相关

> 推论3 设向量组秩为 $r$  向量组中任意多余 $r$ 个向量构成的向量组一定线性相关, 
从而向量组中任意 $r$ 个线性无关的向量都构成向量组的一个最大无关组

> 推论4 向量组任一线性无关部分组都可由扩充为向量组的一个最大无关组

> 推论5 若两个线性无关向量组 &\alpha_1, \alpha_2, \dots , \alpha_s$ 和 $\beta_1, \beta_2, \ dots , \beta_t$ , 则 $s = t$

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
 & 设s个m维向量 \alpha_1, \alpha_2, \dots , \alpha_s 线性无关, \ 在每个向量中增加n - m个分量后得到n维向量组 \beta_1, \beta_2, \dots , \beta_s \\
 & \ \\
 & 先证明分量都添加在各个\alpha_i后面是结论成立, 即若\alpha_i = (a_{i1}, a_{i2}, \dots , a_{im})^T \\
 & 则 \ \beta_i = (a_{i1}, a_{i2}, \dots , a_{im}, a_i, a_{m + 1}, \dots , a_{in})^T \ , \ i = 1, 2, \dots , s \\
 & \ \\
 & 设 \  x_1 \beta_1 + x_2 \beta_2 \dots + x_s \beta_s = \mathbf{0} \\
 & 展开得 \ \begin{cases}
  a_{11} x_1 + a_{21} x_2 + \dots + a_{s1} x_s = 0 \\
  a_{12} x_1 + a_{22} x_2 + \dots + a_{s2} x_s = 0 \\
  \dots \dots \dots \dots \\
  a_{1m} x_1 + a_{2m} x_2 + \dots + a_{sm} x_s = 0 \\
  a_{1, m + 1} x_1 + a_{2, m + 1} x_2 + \dots + a_{s, m + 1} x_s = 0 \\
  \dots \dots \dots \dots \\
  a_{1n} x_1 + a_{2n} x_2 + \dots + a_{sn} x_s = 0
 \end{cases} \\
 & 则方程组前m个方程可写为 \ x_1 \alpha_1 + x_2 \alpha_2 + \dots + x_s \alpha_s = \mathbf{0} \\
 & \ \\
 & 又 \alpha_1, \alpha_2, \dots , \alpha_s 线性无关, 在这儿方程只有玲姐, 即方程组只有零解 \\
 & 故向量组 \beta_1, \beta_2, \dots , \beta_s 线性无关 \\
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
 & A = \{ (a_1, 0, \dots , 0) | a_1 \in R \} \\
 & B = \{ (a_1, 1, 0, \dots , 0) | a_1 \in R \} \\
 & C = \{ (a_1, a_2, \dots , a_n) | a_1 + a_2 + \dots + a_n = 0, \ a_i \in R, \ i = 1, 2, \dots , n \}
\end{aligned}
$$

解

$$
\begin{aligned}
 & A是向量空间, \forall \ \alpha = (a, 0, \dots , 0), \ \beta = (b, 0, \dots , 0), \ k \in R \\
 & \alpha + \beta = (a + b, 0, \dots , 0) \in A \\
 & k \alpha = (ka, 0, \dots , 0) \in A \\
 & 即A关于向量的加法和数乘都封闭 \\
 & \ \\
 & B不是向量空间, \ \alpha = (a, 1, 0, \dots , 0), \ \beta = (b, 1, 0, \dots , 0) \\
 & \alpha + \beta = (a + b, 2, 0, \dots , 0) \notin B \\
 & 即B关于向量加法不封闭 \\
 & \ \\
 & C是向量空间, \forall \ \alpha = (a_1, a_2, \dots , \alpha_n) , \ \beta = (b_1, b_2, \dots , b_n) \\
 & 其中 a_1 + a_2 + \dots + a_n = 0\ , \ b_1 + b_2 + \dots + b_n = 0 , 有 \\
 & \alpha + \beta = (a_1 + b_1, a_2 + b_2, \dots , a_n + b_n) \\
 & 且 a_1 + b_1 + a_2 + b_2 + \dots + a_n + b_n = (a_1 + a_2 + \dots + a_n) + (b_1 + b_2 + \dots + b_n) = 0 \\
 & 即 \alpha + \beta \in C \\
 & 又 \forall k \ , k a_1 + k a_2 + \dots + k a_n = k (a_1 + a_2 + \dots + a_n) = 0 \\
 & k \alpha = (k a_1, k a_2, \dots , k a_n) \in C \\
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
 & W_1 = \{ (a_1, a_2, \dots, a_{n - 1}, \sum_{i = 1}^{n - 1} a_i) \ | \ a_i \in R, i = 1, 2, \dots, n - 1 \} \\
 & W_2 = \{ (a_1, a_2, \dots , a_n) \ | \ a_1 = a_2 = \dots = a_n \in R \} \\
 & W_3 = \{ (a, a + b, a + 2b, \dots , a + (n - 1)b \ | \ a, b \in R) \}
\end{aligned}
$$

都是 $R^n$ 的子空间

设 $V$ 是一个向量空间, $\alpha_, \alpha_2, \dots , \alpha_r \in V$ , 则

$$
W = \{ k_1 \alpha_2 + k_2 \alpha_2 + \dots + k_r \alpha_r \ | \ k_i \in R, i =1, 2, \dots , r \}
$$

是 $V$ 的子空间, 这个子空间称为由 $\alpha_1, \alpha_2, \dots , \alpha_r$ 生成的子空间, 记作 $L(\alpha_1, \alpha_2, \dots , \alpha_r)$

$\alpha_1, \alpha_2, \dots , \alpha_r$ 称为这个子空间的一组生成元

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

> 定义3 设 $V$ 为一个向量空间, $\alpha_1, \alpha_2, \dots , \alpha_r \in V$ , 若

- $\alpha_1, \alpha_2, \dots , \alpha_r$ 线性无关
- $V$ 的任一向量都可由 $\alpha_1, \alpha_2, \dots , \alpha_r$ 线性表示

则称向量组 $\alpha_1, \alpha_2, \dots , \alpha_r$ 为向量空间 $V$ 的一组基, $r$ 称为向量空间 $V$ 的维数, 记作 $dim(V) = r$

**零空间的维度规定为零**

_把向量空间看做一个向量组, 则其基就是它的一个最大无关组, 其维数就是它的秩_

_向量空间可以有很多组基, 但每组基所含向量个数相同, 故向量空间维数唯一确定_

例
证明 $\varepsilon_1 = (1, 0, \dots , 0), \varepsilon_2 = (0, 1, \dots , 0) , \dots , \varepsilon_n = (0, 0, \dots , 1)$ 
为 $R^n$ 的一组基, 从而得 $R^n$ 的维数为 $n$

$$
\begin{aligned}
 & 先证 \varepsilon_1, \varepsilon_2, \dots , \varepsilon_n 线性无关 \\
 & 它们构成矩阵 E = (\varepsilon_1, \varepsilon_2, \dots , \varepsilon_n) = \begin{pmatrix}
  1 & 0 & \dots & 0 \\
  0 & 1 & \dots & 0 \\
  \vdots & \vdots &   & \vdots \\
  0 & 0 & \dots & 1
 \end{pmatrix} \\
 & r(E) = n, 则向量组线性无关 \\
 & \ \\
 & 对于 \forall \alpha \in R^n \ , \ 设 \alpha = (a_1, a_2, \dots , a_n) \\ 
 & \alpha = a_1 \varepsilon_1 + a_2 \varepsilon_2 + \dots + a_n \varepsilon \\
 & 故 \varepsilon_1, \varepsilon_2, \dots , \varepsilon_n 为向量空间 R^n 的基, 且 dim(R^n) = n
\end{aligned}
$$

$\varepsilon_1, \varepsilon_2, \dots , \varepsilon_n$ 称为向量空间 $R^n$ 的标准基

设 $\alpha_1, \alpha_2, \dots , \alpha_m$ 是 $m$ 个 $n$ 为向量, 

$$
V = L(\alpha_1, \alpha_2, \dots , \alpha_m) = 
\{ k_1 \alpha_1 + k_2 \alpha_2 + \dots + k_m \alpha_m \ | \ k_i \in R, i = 1, 2, \dots , m \}
$$

则向量组 $\alpha_1, \alpha_2, \dots , \alpha_m$ 的一个最大无关组就是 $V$ 的一组基, 
从而向量组 $\alpha_1, \alpha_2, \dots , \alpha_m$ 的秩就等于 $V$ 的维数

> 定理1 设 $V$ 是一个向量空间, $dim(V) = r$ , 则 $V$ 中任意 $r$ 个线性无关的向量都是 $V$ 的一组基,
且 $V$ 的任一多于 $r$ 个向量的向量组一定线性相关

**特别地, 任意 $n$ 个线性无关的 $n$ 维向量都是 $R^n$ 的一组基**

> 定理2 向量空间 $V$ 的任一线性无关向量组都可以扩充为 $V$ 的一组基, 特别地, $V$ 的任一子空间的基都可扩充为 $V$ 的基

### 3.3.4 向量在给定基下的坐标

设 $\alpha_1, \alpha_2, \dots , \alpha_r$ 是向量空间 $V$ 的一组基, 则 $V$ 中每个向量 $\alpha$ 都可表示为

$$
\alpha = x_1 \alpha_1 + x_2 \alpha_2 + \dots + x_r \alpha_r
$$

且有序数组 $x_1, x_2, \dots , x_r$ 是唯一的

> 定义4 设 $\alpha_1, \alpha_2, \dots , \alpha_r$ 是向量空间 $V$ 的一组基, $\alpha \in V$ , 若

$$
\alpha = x_1 \alpha_1 + x_2 \alpha_2 + \dots + x_r \alpha_r
$$

则 $r$维向量 $(x_1, x_2, \dots , x_r)$ 称为向量 $\alpha$ 在基 $alpha_1, \alpha_2, \dots , \alpha_r$ 下的坐标

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

若 $\alpha, \beta$ 坐标分别为 $(x_1, x_2, \dots , x_r)$ 及 $(y_1, y_2, \dots , y_r)$ , 则

- $\alpha + \beta$ 坐标为

$$
(x_1 + y_1, x_2 + y_2, \dots , x_r + y_r) = (x_1, x_2, \dots , x_r) + (y_1, y_2, \dots , y_r)
$$

- $\lambda \alpha$ 坐标为

$$
(\lambda x_1, \lambda x_2, \dots , \lambda x_r) = \lambda (x_1, x_2, \dots , x_r)
$$

若向量 $\alpha$ 在基 $\alpha_1, \alpha_2, \dots , \alpha_r$ 下坐标为 $(x_1, x_2, \dots , x_r)$ , 即

$$
\alpha = x_1 \alpha_1 + x_2 \alpha_2 + \dots + x_r \alpha_r
$$

矩阵符号记作

$$
\alpha = (\alpha_1, \alpha_2, \dots , \alpha_r) \begin{pmatrix} x_1 \\ x_2 \\ \vdots \\ x_r \end{pmatrix}
$$

### 3.3.5 基变换与坐标变换


设 $\alpha_1, \alpha_2, \dots , \alpha_r$ 和 $\beta_1, \beta_2, \dots , \beta_r$ 为 $V$ 的两组基. 
由基的定义得, $\beta_1, \beta_2, \dots , \beta_r$ 可以由 $\alpha_1, \alpha_2, \dots , \alpha_r$ 线性表示, 即 

$$
\begin{cases}
 \beta_1 = a_{11} \alpha_1 + a_{21}\alpha_2 + \dots + a_{r1} \alpha_r \\
 \beta_2 = a_{12} \alpha_1 + a_{22}\alpha_2 + \dots + a_{r2} \alpha_r \\
 \dots \dots \dots \dots \\
 \beta_r = a_{1r} \alpha_1 + a_{2r}\alpha_2 + \dots + a_{rr} \alpha_r
\end{cases}
$$

写成矩阵的形式为

$$
(\beta_1, \beta_2, \dots , \beta_r) = (\alpha_1, \alpha_2, \dots , \alpha_r) A
$$

其中

$$
A = \begin{pmatrix}
 a_{11} & a_{12} & \dots & a_{1r} \\
 a_{21} & a_{22} & \dots & a_{2r} \\
 \vdots & \vdots &   & \vdots \\
 a_{1r} & a_{r2} & \dots & a_{rr}
\end{pmatrix}
$$

矩阵 $A$ 的第 $i$ 列是 $\beta_i$ 在基 $\alpha_1, \alpha_2, \dots , \alpha_r$ 下的坐标, 
称 $A$ 为有基 $\alpha_1, \alpha_2, \dots , \alpha_r$ 到基 $\beta_1, \beta_2, \dots , \beta_r$ 的过渡矩阵,
上式称为基变换公式

由于 $\beta_1, \beta_2, \dots , \beta_r$ 也是一组基, $\alpha_1, \alpha_2, \dots , \alpha_r$ 能由其表示, 即

$$
(\alpha_1, \alpha_2, \dots , \alpha_r) = (\beta_1, \beta_2, \dots , \beta_r) B
$$

从而

$$
(\beta_1, \beta_2, \dots , \beta_r) = (\alpha_1, \alpha_2, \dots , \alpha_r) A = (\beta_1, \beta_2, \dots , \beta_r) BA
$$

由 $\beta_1, \beta_2, \dots , \beta_r$ 线性无关可得 $BA = E$ , 即 $B = A^{-1}$

设 $V$ 中向量 $\alpha$ 在基 $\alpha_1, \alpha_2, \dots , \alpha_r$ 和基 $\beta_1, \beta_2, \dots , \beta_r$ 中坐标分别为 
$(x_1, x_2, \dots , x_r)$ 和 $(y_1, y_2, \dots , y_r)$ , 即

$$
\alpha = (\alpha_1, \alpha_2, \dots , \alpha_r) \begin{pmatrix} x_1 \\ x_2 \\ \vdots \\ x_r \end{pmatrix} = 
(\beta_1, \beta_2, \dots , \beta_r) \begin{pmatrix} y_1 \\ y_2 \\ \vdots \\ y_r \end{pmatrix}
$$

代入得

$$
\alpha = (\alpha_1, \alpha_2, \dots , \alpha_r) \begin{pmatrix} x_1 \\ x_2 \\ \vdots \\ x_r \end{pmatrix} = 
(\alpha_1, \alpha_2, \dots , \alpha_r) A \begin{pmatrix} y_1 \\ y_2 \\ \vdots \\ y_r \end{pmatrix}
$$

向量坐标唯一, 可得

$$
\begin{pmatrix} x_1 \\ x_2 \\ \vdots \\ x_r \end{pmatrix} = 
A \begin{pmatrix} y_1 \\ y_2 \\ \vdots \\ y_r \end{pmatrix}
$$

> 定理3 设 $\alpha_1, \alpha_2, \dots , \alpha_r$ 和 $\beta_1, \beta_2, \dots , \beta_r$ 是向量空间 $V$ 的两组基,
由基 $\alpha_1, \alpha_2, \dots , \alpha_r$ 到基 $\beta_1, \beta_2, \dots , \beta_r$ 过渡矩阵为 $A$ ,
向量 $\alpha$ 在两组基坐标分别为 $(x_1, x_2, \dots , x_r)$ 和 $(y_1, y_2, \dots , y_r)$ , 则

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

> 定义1 设 $\alpha = (x_1, x_2, \dots , x_n), \beta = (y_1, y_2, \dots , y_n)$ 为两个 $n$ 维向量, 则实数 $x_1 y_1 + x_2 y_2 + \dots + x_n y_n$ 称为向量 $\alpha, \beta$ 的内积, 记作 $(\alpha, \beta)$ , 即

$$
(\alpha, \beta) = x_1 y_1 + x_2 y_2 + \dots x_n y_n
$$

_定义向量内积的向量空间称为欧几里德空间,  简称欧式空间_

欧式空间 $V$ 的内积与三位向量空间 $R^3$ 中的数量级一样具有以下性质

- 对称性: $(\alpha, \beta) = (\beta, \alpha)$
- 双线性性: $\begin{aligned} &(k_1 \alpha_1 + k_2 \alpha_2, \beta) = k_1 (\alpha_1, \beta) + k_2 (\alpha_2, \beta) \\
& (\alpha, k_1 \beta_1 + k_2 \beta_2) = k_2 (\alpha, \beta_1) + k_2 (\alpha, \beta_2) \end{aligned}$
- 非负性: $(\alpha, \alpha) \ge 0$

### 3.4.2 向量的长度与夹角

> 定义2 设 $\alpha = (x_1, x_2, \dots , x_n)$ 为欧式空间 $V$ 中一向量, 定义 $\alpha$ 的长度为 

$$
\parallel \alpha \parallel = \sqrt{(\alpha, \alpha)} = \sqrt{x_1^2 + x_2^2 + \dots + x_n^2}
$$

向量长度具有以下性质

- 非负性: $\parallel \alpha \parallel \ge 0$ , 当且仅当 $alpha = \mathbf{0}$ 时, $\parallel \alpha \parallel = 0$
- 正齐次性: $\parallel k \alpha \parallel = \left | k \right | \parallel \alpha \parallel$
- 三角不等式: $\parallel \alpha + \beta \parallel \le \parallel \alpha \parallel + \parallel \beta \parallel$
  
_长度为 $1$ 的向量称为单位向量_

设 $\alpha$ 为任一非零向量, 则 $\frac{1}{\parallel \alpha \parallel} \alpha$ 为单位向量, 即用数 $\frac{1}{\parallel \aleph \parallel}$ 乘向量 $\alpha$ , 则将向量单位化

_对于欧式空间两个向量 $\alpha = (a_1, a_2, \dots , a_n), \beta = (b_1, b_2, \dots , b_n)$ , 定义它们的距离为 $\parallel \alpha - \beta \parallel$ , 即_ 
$\sqrt{(a_1 - b_1)^2 + (a_2 - b_2)^2 + \dots + (a_n - b_n)^2}$

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

设 $\alpha_1, \alpha_2, \dots , \alpha_s$ 是欧式空间 $V$ 的一组两两相交的非零向量, 则称向量组 $\alpha_1, \alpha_2, \dots , \alpha_s$ 为一正交向量组

正交向量组一定线性无关, 设 $\alpha_1, \alpha_2, \dots , \alpha_s$ 为一正交向量组, 令

$$
k_1 \alpha_1 + k_2 \alpha_2 + \dots + k_s \alpha_s = \mathbf{0}
$$

等式两边与 $\alpha_i$ 做内积, 得 $k_s (\alpha_i, \alpha_i) = 0$ , 又 $\alpha_i \ne 0$ , 则 $(\alpha_i, \alpha_i) > 0$ , 故 $k_- = 0 \ (i = 1, 2, \dots , s)$ ,
则 $\alpha_1, \alpha_2, \dots , \alpha_s$ 线性无关s

> 定义4 欧式空间 $V$ 中有正交向量组构成的基称为 $V$ 的正交基, 若 $V$ 的一组正交基中的向量都是单位向量, 则称它为 $V$ 的标准正交基

**若欧式空间 $V$ 维数为 $m$ , 则 $V$ 中 $m$ 个向量 $\alpha_1, \alpha_2, \dots , \alpha_m$ 是 $V$ 的标准正交基的充要条件是**

$$
(\alpha_i, \alpha_j) = \begin{cases} 0, i \ne j \\ 1, i = j \end{cases} 
\ , \ i, j = 1, 2, \dots , m
$$

例如, $R^n$ 中, 标准基 $\varepsilon_1, \varepsilon_2, \dots , \varepsilon_n$ 就标准正交基

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
 & 设 A = (\alpha_1, \alpha_2, \dots , \alpha_n) , 按分块矩阵乘法有 \\
 & A^T A = (\alpha_1, \alpha_2, \dots , \alpha_n)^T (\alpha_1, \alpha_2, \dots , \alpha_n) \\
 & = \begin{pmatrix} \alpha_1^T \\ \alpha_2^T \\ \vdots \\ \alpha_n^T \end{pmatrix} (\alpha_1, \alpha_2, \dots , \alpha_n) = \begin{pmatrix}
  \alpha_1^T \alpha_1 & \alpha_1^T \alpha_2 & \dots & \alpha_1^T \alpha_n \\
  \alpha_2^T \alpha_1 & \alpha_2^T \alpha_2 & \dots & \alpha_2^T \alpha_n \\
  \vdots & \vdots &   & \vdots \\
  \alpha_n^T \alpha_1 & \alpha_n^T \alpha_2 & \dots & \alpha_n^T \alpha_n
 \end{pmatrix} \\
 & \ \\
 & 则 A^T A = E 当且仅当 \\
 & \alpha_i^T \alpha_j = (\alpha_i, \alpha_j) = 
 \begin{cases} 1, i = j \\ 0, i \ne j \end{cases} \\
 & 即 A 的列向量 \alpha_1, \alpha_2, \dots , \alpha_n 是 R^n 的一个标准正交基
\end{aligned}
$$

由 $A^T A = E$ 得 $A^T = A^{-1}$ , 所有也有 $AA^T = E$

类似的可证明 $A$ 是正交矩阵当且仅当 $A$ 的行向量是 $R^n$ 的一组标准正交基

因此 , $\alpha_1, \alpha_2, \dots , \alpha_n$ 是 $R^n$ 的标准正交基的充要条件是以 $\alpha_1, \alpha_2, \dots , \alpha_n$ 为列向量构成的矩阵是一个正交矩阵

> 定理3 设 $\alpha_1, \alpha_2, \dots , \alpha_m$ 是欧式空间 $V$ 的一组基, 则存在 $V$ 的一组标准正交基 $\beta_1, \beta_2, \dots , \beta_m$ , 使 $\beta_k$ 可由 $\alpha_1, \alpha_2, \dots , \alpha_k$ 线性表示

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
 & 对于 1 < k < m, 可在V中取到正交的非零向量 \gamma_1, \gamma_2, \dots, \gamma_{k - 1}, 且 \gamma_i 可由 \alpha_1, \alpha_2, \dots, \alpha_k 线性表示 \\
 & 又 \alpha_1, \alpha_2, \dots, \alpha_k 线性无关, 则 \gamma_k \ne \mathbf{0} \\
 & 又 \gamma_1, \gamma_2, \dots, \gamma_{k - 1} 两两正交, 且 \\
 & (\gamma_k, \gamma_i) = (\alpha_k, \alpha_i) - \frac{(\alpha_k, \gamma_i)}{(\gamma_i, \gamma_i)} (\gamma_i, \gamma_i) = 0 \ , \ i = 1, 2, \dots , k - 1 \\
 & 即 \gamma_1, \gamma_2, \dots, \gamma_k 仍两两正交 \\
 & \\
 & 由数学归纳法可知, V中存在一组正交基 \gamma_1, \gamma_2, \dots, \gamma_m, 使 \gamma_k 可由 \alpha_1, \alpha_2, \dots, \alpha_k 线性表示 (k = 1, 2, \dots , m)
\end{aligned}
$$

第二步: 单位化

$$
\begin{aligned}
  & 把 \gamma_1, \gamma_2, \dots, \gamma_m 单位化, 令 \\
  & \beta_k = \frac{1}{\parallel \gamma_k \parallel} \gamma_k \ , \ k = 1, 2, \dots , m \\
  & 则 \beta_1, \beta_2, \dots , \beta_m 为满足要求的标准正交基
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

设 $\alpha_1, \alpha_2, \dots, \alpha_m$ 与 $\beta_1, \beta_2, \dots , \beta_m$ 是 $m$ 维欧式空间 $V$ 的两组基, 其中 $\alpha_1, \alpha_2, \dots, \alpha_m$ 是标准正交基, 且从 $\alpha_1, \alpha_2, \dots, \alpha_m$ 到 $\beta_1, \beta_2, \dots , \beta_m$ 的过渡矩阵 $A = (a_{ij})$ , 即

$$
(\beta_1, \beta_2, \dots , \beta_m) = (\alpha_1, \alpha_2, \dots, \alpha_m) \begin{pmatrix}
  a_{11} & a_{12} & \dots & a_{1m} \\
  a_{21} & a_{22} & \dots & a_{2m} \\
  \vdots & \vdots &   & \vdots \\
  a_{m1} & a_{m2} & \dots & a_{mm}
\end{pmatrix}
$$

则 $\beta_1, \beta_2, \dots , \beta_m$ 为标准正交基当且仅当 

$$
(\beta_i, \beta_j) = a_{1i}a_{1j} + a_{2i}a_{2j} + \dots + a_{mi}a_{mj} = \begin{cases}
  & 1 \ , \ i = j \\
  & 0 \ , \ i \ne j
\end{cases}
$$

上式等价于

$$
A^TA = E
$$

即 $A$ 为正交矩阵

$$
(\ge \omega \le)
$$

$$
Ciallo \sim (\angle \ \mathbf{\cdot} \ \omega <) \frown ☆
$$
