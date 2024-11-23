# 线性代数学习笔记 第四章

# 4 线性方程组
## 4.1 解线性方程组的消元法
### 4.1.1 线性方程组解的存在性

设 $n$ 个未知元, $m$ 个方程的线性方程组为

$$
\begin{cases}
  a_{11} x_1 + a_{12} x_2 + \dots + a_{1n} x_n = b_1 \\
  a_{21} x_1 + a_{21} x_2 + \dots + a_{2n} x_n = b_2 \\
  \dots \dots \dots \dots \\
  a_{m1} x_1 + a_{m2} x_2 + \dots + a_{mn} x_n = b_m
\end{cases}
$$

记

$$
A = \begin{pmatrix}
  a_{11} & a_{12} & \dots & a_{1n} \\
  a_{21} & a_{22} & \dots & a_{2n} \\
  \vdots & \vdots &   & \vdots \\
  a_{m1} & a_{m2} & \dots & a_{mn}
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
  a_{11} & a_{12} & \dots & a_{1n} & b_1 \\
  a_{21} & a_{22} & \dots & a_{2n} & b_2 \\
  \vdots & \vdots &   & \vdots & \vdots \\
  a_{m1} & a_{m2} & \dots & a_{mn} & b_m
\end{pmatrix}
$$

$A$ 和 $\overline{A}$ 分别称为方程组的系数矩阵和增广矩阵

将系数矩阵 $A$ 按列分块, 即

$$
A = (\alpha_1, \alpha_2, \dots, \alpha_n)
$$

其中 $\alpha_j = (a_{1j}, a_{2j}, \dots , a_{mj})^T \ (j = 1, 2, \dots . n)$
