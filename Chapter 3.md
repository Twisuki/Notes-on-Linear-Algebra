# 线性代数学习笔记 第三章

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
