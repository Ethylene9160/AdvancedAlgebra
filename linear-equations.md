<p align='center'><font size=6><b>线性方程组</b></font></p>



**可以互相线性表示的向量组被称为线性等价，或者等价。**

# 方程的解

$$
\begin{aligned}
\begin{cases}
a_{11}x_1+a_{12}x_2+...+a_{1n}x_n=0\\
a_{21}x_1+a_{22}x_2+...+a_{2n}x_n=0\\
...\\
a_{s1}x_1+a_{s2}x_2+...+a_{sn}x_n=0\\
\end{cases}\\
\end{aligned}
$$

如果s小于n，那么方程**一定有非零解**。

# 线性相关论

## 线性组合

如果
$$
\begin{aligned}
\pmb\alpha&=k_1\pmb\beta_1+k_2\pmb\beta_2+...+k_s\pmb\beta_s\\
%&=\pmb \beta \pmb k
\end{aligned}
$$

那么，$\pmb\alpha$是$\pmb\beta$的线性组合。

## 线性无关

对于向量组$\{\pmb\alpha_i\in\mathbb R^n\},\quad i=1,2,...,s,\quad \pmb A=[\pmb \alpha_1,...,\alpha_s]$，该组向量线性无关的**充分必要**条件是下述方程**只有**非0解：
$$
\pmb A\pmb x=0
$$
如果在每个向量$\pmb\alpha_i$后新增一个元素，即$\pmb\beta_i=[\pmb\alpha_i^T,\alpha^{(i)}_{n+1}]^T\in\mathbb R^{n+1}$，同时假设$\pmb B=[\pmb \beta_1,...,\beta_s]$那么$\pmb B\pmb x=0$的解一定是$\pmb A \pmb x=0$的解的子集。因为它需要同时满足下面等式的两个条件。
$$
\begin{aligned}
\pmb A\pmb x&=0\\
\begin{bmatrix}
\alpha_{n+1}^{(1)},...,\alpha_{n+1}^{s}
\end{bmatrix}\pmb x&=0
\end{aligned}
$$



## 推论

现在，假设向量组$\{\pmb\alpha_i\in\mathbb R^n\},\quad i=1,2,...,r$和$\{\pmb\beta_i\in\mathbb R^n\},\quad i=1,2,...,s$，我们来讨论他们的线性相关的情况。

* $\{\pmb\alpha_i\}$可以被$\{\pmb\beta_i\}$线性表示出，且$r>s$，那么$\{\pmb\alpha_i\}$线性相关。

> $$
 \begin{aligned}
 \pmb\alpha_i&=\sum_{j=1}^st_{ji}\pmb\beta_j\\
 \sum_{i=1}^rx_i\pmb\alpha_i&=0\\
 \rightarrow
 \sum_{i=1}^rx_i\sum_{j=1}^st_{ji}\pmb\beta_j&=
 \sum_{j=1}^s\left(\sum_{i=1}^rx_it_{ji}\right)\pmb\beta_j\\&=0
 \end{aligned}
> $$
>
> 显然，未知数有r个，方程组有s个，而r大于s，因此**方程未知数数量大于方程组的个数**，方程有非零解。

* $\{\pmb\alpha_i\}$可以被$\{\pmb\beta_i\}$线性表示出，且$\{\pmb\alpha_i\}$线性无关。那么$r\leq s$。

> 同上述方程组所示，如果需要方程有唯一解，那么必然方程组个数s不小于未知数个数r。

这个推论换一种说法可以改为：**任意n+1个n维向量必然相关。**

进一步，如果两个*线性无关*的向量组等价，那么他们必然<u>含有相同个数的向量</u>。

### 极大线性无关组

一个向量组中，如果其中一个部分组成的向量组（称为*部分组*）是线性无关的，如果原向量组中任意一个不在部分组中的向量（如果还有的话）与部分组向量线性相关，那么这个部分组被称为**极大线性无关组**。

如果向量组本身线性无关，那么它的极大线性无关组就是它自己。

* 任何一个极大线性无关组都和向量组本身等价。

* 一个向量组的极大线性无关组都含有相同个数的向量。这个数量就是**向量组的秩**。

# 矩阵的秩

## 秩和方程的解

对于其次线性方程组：
$$
\begin{aligned}
\begin{cases}
a_{11}x_1+a_{12}x_2+...+a_{1n}x_n=0\\
a_{21}x_1+a_{22}x_2+...+a_{2n}x_n=0\\
...\\
a_{n1}x_1+a_{n2}x_2+...+a_{nn}x_n=0\\
\end{cases}\\
A=\begin{bmatrix}
a_{11}&a_{12}&...&a_{1n}\\
a_{21}&a_{22}&...&a_{2n}\\
...\\
a_{n1}&a_{n2}&...&a_{nn}\\
\end{bmatrix}
\end{aligned}
$$
当对应的系数矩阵的行秩$r<n$，存在**非零解**。

* 矩阵的行秩等于列秩。

> $$
 \begin{aligned}
 A=\begin{bmatrix}
 a_{11}&a_{12}&...&a_{1n}\\
 a_{21}&a_{22}&...&a_{2n}\\
 ...\\
 a_{s1}&a_{s2}&...&a_{sn}\\
 \end{bmatrix}
 \end{aligned}
> $$
>
> 
> 假设向量组$\{\pmb\alpha\}_s$是该矩阵的行向量组, 其最大线性无关组是$\{\pmb\alpha\}_r$，$r\leq s$，r是行秩。对于其最大线性无关向量组：
$$
x_1\pmb \alpha_1+...+x_r\pmb\alpha_r=\pmb 0
$$
> 只有零解，也就是说，对于这个方程组的系数矩阵：
> $$
\begin{aligned}
\begin{bmatrix}
a_{11}&a_{21}&...&a_{r1}\\
a_{12}&a_{22}&...&a_{r2}\\
...\\
a_{1n}&a_{2n}&...&a_{rn}\\
\end{bmatrix}
\end{aligned}
> $$
> 这个矩阵的行秩必然不小于r。而这个矩阵的行恰好是原矩阵的列的一部分，因此原矩阵的列秩一定不小于这个矩阵的行秩不小于r，即原矩阵的列秩不小于行秩；同样可以证明，原矩阵的行秩不小于列秩，因此矩阵的行秩等于列秩。

* 矩阵行列式为0的充要条件是矩阵不满秩。

> 充分性：当n=1时，矩阵行列式显然为0；n大于1时，矩阵中有一行是其余各行的线性组合，这一行能变为全零行，因此矩阵行列式一定为0.
>
> 必要性：行列式为0时，考虑：
>
> * n=1: 显然，$A=[0]$；
> * n>1: 假设n-1下的行列式为0，向量组线性相关。假设某一行消掉后，得到: 
>
> $$
 \begin{aligned}
 |A|=\left|\begin{matrix}
 a_{11}&a_{12}&...&a_{1n}\\
 0&a'_{22}&...&a'_{2n}\\
 ...\\
 0&a'_{n2}&...&a_{nn}\end{matrix}\right|
 =a_{11}\left|\begin{matrix}
 a'_{22}&...&a'_{2n}\\
 ...\\
 a'_{n2}&...&a'_{nn}
 \end{matrix}\right|
 \end{aligned}
> $$
> 显然，要么$a_{11}=0$，要么$\left|\begin{matrix}a'_{22}&...&a'_{2n}\\...\\a'_{n2}&...&a'_{nn}\end{matrix}\right|=0$。
>
> 如果前者成立，那么显然矩阵A不满秩；如果后者成立，那么后者构成的矩阵不满秩。从而可以逐级递推下去。

# 线性方程组有解判别定理

对于线性方程组：
$$
\begin{cases}
a_{11}x_1+a_{12}x_2+...+a_{1n}x_n=b_1\\
...\\
a_{s1}x_1+a_{s2}x_2+...+a_{sn}x_n=b_s\\
\end{cases}
$$
有解的判别条件是方程**系数矩阵的秩和线性方程组增广矩阵的秩相同。**

> **必要性**：
>
> 假设系数矩阵为$A=[\pmb\alpha_1,...,\alpha_n]$, $\pmb\alpha_i=[a_{1i},...,a_{si}]^T$，$\pmb\beta=[b_1,...,b_s]^T$。如果线性方程许有解，即$\sum_i \pmb\alpha_i x_i=\pmb\beta $有解，也就是说，$\pmb\beta$ 能被向量组 $\{\pmb\alpha\}$ 线性表示出。因此，增广矩阵和原矩阵的列秩相同，也即是说，增广矩阵的列秩与原矩阵的行秩一致。
>
> **充分性**：
>
> 相同的秩，说明有相同的列秩。假设原矩阵的极大线性无关组包含r个列向量。设$\{\pmb\alpha\}_r$，如果它们列秩相同，那么$\pmb\beta$一定能用$\{\pmb\alpha\}_r$表示出来。因此有解。

# 线性方程组的解的结构

* 两个解的和依然是方程组的解
* 一个解的倍数依然是方程组的解

因此，引入**基础解系**的概念。对于某个其次线性方程组的一组解$\pmb\eta_1,...,\pmb\eta_n$，同时满足：

* 该方程组的任何一个解都能表述成$\{\pmb\eta\}$的线性组合
* $\{\pmb\eta\}$<u>线性无关</u>



若齐次线性方程有非零解（显然不满秩），那么它有基础解系，且基础解系所含解的个数等于$n-r$。