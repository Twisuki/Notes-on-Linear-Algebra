# 线性代数学习笔记 第一章

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
