<p align='center'><font size=6><b>第二章 行列式</b></font></p>

对于：
$$
\begin{aligned}
A\pmb x&=B\\
\lvert A\rvert&\neq0
\end{aligned}
$$
该线性方程一定有唯一解。

# 排列 - Permutation

由数字1，2，…，n组成的有序数组称为n级排列。它的排列总数有n!种。



# 余子式 - Minor

$\pmb{M}_{ij}$：除去第i行，第j列后的元素组成的行列式。



# 代数余子式 - Cofactor

$\pmb{A}_{ij}=(-1)^{i+j}\pmb{M}_{ij}$

* 一些性质：

首先，我们的经验告诉我们，行列式可以被写为：





# Properties of Determinants

Property 1: Exchange rows and columns, the determinant stays the same.

Property 2 - Row (Column) Linearity: pass. And if k = 0 then the determinant is 0.

Property 3 (4): same rows (columns) results in 0 determinants.

Property 4 (5): row~i~=k row~j~ results in 0 determinants.

Property 5 (6): pass

Property 6 (7): exchange 2 rows (columns) will inverse the result of the determinant.

> Proof:
$$
\begin{aligned}
|A|&=\begin{vmatrix}
a_{11}&\cdots&a_{1n}\\
\vdots& &\vdots\\
a_{i1}&\cdots &a_{in}\\
\vdots& &\vdots\\
a_{k1}&\cdots&a_{kn}\\
\vdots& &\vdots\\
a_{n1}&\cdots&a_{nn}
\end{vmatrix}&=&
\begin{vmatrix}
a_{11}&\cdots&a_{1n}\\
\vdots& &\vdots\\
a_{i1}+a_{k1}&\cdots &a_{in}+a_{kn}\\
\vdots& &\vdots\\
a_{k1}&\cdots&a_{kn}\\
\vdots& &\vdots\\
a_{n1}&\cdots&a_{nn}
\end{vmatrix}\\
&=\begin{vmatrix}
a_{11}&\cdots&a_{1n}\\
\vdots& &\vdots\\
a_{i1}+a_{k1}&\cdots &a_{in}+a_{kn}\\
\vdots& &\vdots\\
-a_{i1}&\cdots&-a_{in}\\
\vdots& &\vdots\\
a_{n1}&\cdots&a_{nn}
\end{vmatrix}
&=&\begin{vmatrix}
a_{11}&\cdots&a_{1n}\\
\vdots& &\vdots\\
a_{k1}&\cdots &a_{kn}\\
\vdots& &\vdots\\
-a_{i1}&\cdots&-a_{in}\\
\vdots& &\vdots\\
a_{n1}&\cdots&a_{nn}
\end{vmatrix}\\
&=-|A|
\end{aligned}
$$














# Calculate Determinants

**Elementary Row Transformation**:

* Multiplied by a certain nonzero number.
  $$
  \begin{aligned}
  A&=\left(\begin{matrix}
  a_{11}&\cdots&a_{1n}\\
  \vdots& &\vdots\\
  a_{i1}&\cdots &a_{in}\\
  \vdots& &\vdots\\
  a_{n1}&\cdots&a_{nn}
  \end{matrix}\right)\rightarrow
  \left(\begin{matrix}
  a_{11}&\cdots&a_{1n}\\
  \vdots& &\vdots\\
  ka_{i1}&\cdots &ka_{in}\\
  \vdots& &\vdots\\
  a_{n1}&\cdots&a_{nn}
  \end{matrix}\right)\\&\Rightarrow
  \det{A}\rightarrow k\cdot\det{A}
  \end{aligned}
  $$
  
* Subtract a certain row multiplied by acertain number

  This operation will have no effect on the determinant, because:
  $$
  \begin{aligned}
  A=\left(\begin{matrix}
  a_{11}&\cdots&a_{1n}\\
  \vdots& &\vdots\\
  a_{j1}&\cdots &a_{jn}\\
  \vdots& &\vdots\\
  a_{n1}&\cdots&a_{nn}
  \end{matrix}\right)\rightarrow^{i\neq j} &
  \left(\begin{matrix}
  a_{11}&\cdots&a_{1n}\\
  \vdots& &\vdots\\
  a_{j1}+ka_{i1}&\cdots &a_{jn}+ka_{in}\\
  \vdots& &\vdots\\
  a_{n1}&\cdots&a_{nn}
  \end{matrix}\right)\\
  =&\left(\begin{matrix}
  a_{11}&\cdots&a_{1n}\\
  \vdots& &\vdots\\
  a_{j1}&\cdots &a_{jn}\\
  \vdots& &\vdots\\
  a_{n1}&\cdots&a_{nn}
  \end{matrix}\right)+
  \left(\begin{matrix}
  a_{11}&\cdots&a_{1n}\\
  \vdots& &\vdots\\
  ka_{i1}&\cdots &ka_{in}\\
  \vdots& &\vdots\\
  a_{n1}&\cdots&a_{nn}
  \end{matrix}\right)
  \end{aligned}
  $$
  For the second term, it is easy to observe that there's another row contains $[a_{i1},\cdots,a_{in}]$, so the determinant of the second term is 0. As a result, the determinant of the original matrix stays the same.

* Row Exchange

  Each time the result is inverted, i.e. $\det{A^{'}}=-\det{A}$.

**Echelon From**: like this.
$$
\left(\begin{matrix}
0&1&2&-1\\
0&0&0&1\\
0&0&0&0
\end{matrix}\right)
$$


# Expand detrminants

**Minor**: determinant of some smaller square matrix cut down from A by removing some rows or columns. For a determinant of order n, this splitting gives n smaller determinants (minors) of order n−1.

* Calculate a determinant with a recursive method:

  For matrix A:
  $$
  \begin{aligned}
  A&=\left(\begin{matrix}
  a_{11}&\cdots&a_{1n}\\
  \vdots& &\vdots\\
  a_{n1}&\cdots&a_{nn}
  \end{matrix}\right),
  \end{aligned}
  $$
  we consider the i-th colomn:
  $$
  \begin{aligned}
  A&=\left(\begin{matrix}
  a_{11}&a_{12}&\cdots&a_{1n}\\
  \vdots&\vdots&&\vdots\\
  a_{i1}+0+\cdots+0&0+a_{i2}+\cdots+0&\dots&0+\cdots+0+a_{in}\\
  \vdots&\vdots& &\vdots\\
  a_{n1}&a_{n2}&\cdots&a_{nn}
  \end{matrix}\right)\\
  &=\left(\begin{matrix}
  a_{11}&a_{12}&\cdots&a_{1n}\\
  \vdots&\vdots&&\vdots\\
  a_{i1}&0&\dots&0\\
  \vdots&\vdots& &\vdots\\
  a_{n1}&a_{n2}&\cdots&a_{nn}
  \end{matrix}\right)+\cdots,
  \end{aligned}
  $$
  and let's consider the i-th row and the j-th column. We could do elementary row and colomn transformation (row and column exchange) to bring $a_{ij}$ to the head.
  $$
  \begin{aligned}
  &
  \begin{vmatrix}
  a_{ij} & 0 & \cdots & 0 & 0 & \cdots & 0 \\
  a_{1j} & a_{11} & \cdots & a_{1,j-1} & a_{1,j+1} & \cdots & a_{1n} \\
  \vdots & \vdots & \ddots & \vdots & \vdots & \ddots & \vdots \\
  a_{i-1,j} & a_{i-1,1} & \cdots & a_{i-1,j-1} & a_{i-1,j+1} & \cdots & a_{i-1,n} \\
  a_{i+1,j} & a_{i+1,1} & \cdots & a_{i+1,j-1} & a_{i+1,j+1} & \cdots & a_{i+1,n} \\
  \vdots & \vdots & \ddots & \vdots & \vdots & \ddots & \vdots \\
  a_{nj} & a_{n1} & \cdots & a_{n,j-1} & a_{n,j+1} & \cdots & a_{nn}
  \end{vmatrix}\\
  &=a_{ij}(-1)^{i+j}
  \begin{vmatrix}
  a_{11} & \cdots & a_{1,j-1} & a_{1,j+1} & \cdots & a_{1n} \\
  \vdots & \ddots & \vdots & \vdots & \ddots & \vdots \\
  a_{i-1,1} & \cdots & a_{i-1,j-1} & a_{i-1,j+1} & \cdots & a_{i-1,n} \\
  a_{i+1,1} & \cdots & a_{i+1,j-1} & a_{i+1,j+1} & \cdots & a_{i+1,n} \\
  \vdots & \ddots & \vdots & \vdots & \ddots & \vdots \\
  a_{n1} & \cdots & a_{n,j-1} & a_{n,j+1} & \cdots & a_{nn}
  \end{vmatrix}\\
  &=a_{ij}(-1)^{i+j}M_{ij},
  \end{aligned}
  $$
  
  and later we could calculate $M_{ij}$ in the same way. To simpilification, we define $(-1)^{i+j}M_{ij}$ to be the **Cofactor** of $a_{ij}$, denoted as $C_{ij}$. Applying the property of determinant, we know that $\det(A)=\sum_j a_{ij}C_{ij}$.
  

**Theorem 3**: Let
$$
\begin{aligned}
d&=\begin{vmatrix}
a_{11}&\cdots&a_{1n}\\
\vdots& &\vdots\\
a_{n1}&\cdots&a_{nn}
\end{vmatrix},
\end{aligned}
$$
then:
$$
\begin{aligned}\sum_{s=1}^na_{ks}A_{is}=\begin{cases}d,k= i,\\0,k\neq i\end{cases};\\
\sum_{s=1}^na_{sl}A_{sj}=\begin{cases}d,l= j,\\0,l\neq j.\end{cases}\end{aligned}
$$
This is quite easy to prove. Let's take $\sum_{s=1}^n a_{ks}A_{is} = 0$, $k \neq i$ for example. Consider the determinant of an $n \times n$ matrix $A = (a_{ij})$. For fixed $i$ and $k$ with $k \neq i$, construct a new matrix $B$ by replacing the $i$-th row of $A$ with the $k$-th row of $A$. Then $B$ has two identical rows (the $i$-th and $k$-th rows are both equal to the original $k$-th row), so $\det(B) = 0$.

Expanding $\det(B)$ along the $i$-th row (which is the same as the $k$-th row of $A$), we have:
$$
0 = \det(B) = \sum_{s=1}^n b_{is} \cdot C_{is}(B),
$$
where $C_{is}(B)$ is the $(i,s)$-cofactor of $B$. But note that the $i$-th row of $B$ is $(a_{k1}, a_{k2}, \dots, a_{kn})$, so $b_{is} = a_{ks}$. Moreover, since $B$ is obtained from $A$ by replacing only the $i$-th row (the other rows are the same as in $A$), the cofactor $C_{is}(B)$ is exactly the same as the cofactor $A_{is}$ of the original matrix $A$ (because cofactors depend only on the entries not in the $i$-th row and $s$-th column). Therefore,
$$
0 = \sum_{s=1}^n a_{ks} A_{is}, \quad \text{for } k \neq i.
$$

Similarly, we can prove the analogous result for columns: $\sum_{s=1}^n a_{sk} A_{sj} = 0$ for $k \neq j$.

**Vandermonde**: a determinant resembles to the following form is called an n-th order Vandermonde determinant:
$$
d=\begin{vmatrix}
1&1&\cdots&1\\
a_1&a_2&\cdots&a_n\\
a_1^2&a_2^2&\cdots&a_n^2&\\
\vdots&\vdots&&\vdots&\\
a_1^{n-1}&a_2^{n-1}&\cdots&a_n^{n-1}&
\end{vmatrix}.
$$
Now let's try to consider this determinant. Let's do some elementary transformation. We substract each row starting from the last row:
$$
\begin{aligned}
d&=
\begin{vmatrix}
1&1&\cdots&1\\
a_1&a_2&\cdots&a_n\\
a_1^2&a_2^2&\cdots&a_n^2&\\
\vdots&\vdots&&\vdots&\\
a_1^{n-2}&a_2^{n-2}&\cdots&a_n^{n-2}\\
0&a_2^{n-1}-a_1a_2^{n-2}&\cdots&a_n^{n-1}-a_1a_n^{n-2}&
\end{vmatrix}\\
&=\cdots\\
&=\begin{vmatrix}
1&1&\cdots&1\\
0&a_2-a_1&\cdots&a_n-a_1\\
0&a_2^2-a_1a_2&\cdots&a_n^2-a_1a_n&\\
\vdots&\vdots&&\vdots&\\
0&a_2^{n-2}-a_1a_2^{n-3}&\cdots&a_n^{n-2}-a_1a_n^{n-3}\\
0&a_2^{n-1}-a_1a_2^{n-2}&\cdots&a_n^{n-1}-a_1a_n^{n-2}&
\end{vmatrix}\\
&=\begin{vmatrix}
1&1&\cdots&1\\
0&(a_2-a_1)&\cdots&(a_n-a_1)\\
0&a_2(a_2-a_1)&\cdots&a_n(a_n-a_1)&\\
\vdots&\vdots&&\vdots&\\
0&a_2^{n-2}(a_2-a_1)&\cdots&a_n^{n-2}(a_n-a_1)&
\end{vmatrix}\\
&=\begin{vmatrix}
(a_2-a_1)&\cdots&(a_n-a_1)\\
a_2(a_2-a_1)&\cdots&a_n(a_n-a_1)&\\
\vdots&&\vdots&\\
a_2^{n-2}(a_2-a_1)&\cdots&a_n^{n-2}(a_n-a_1)&
\end{vmatrix}\\
&=
(a_2-a_1)(a_3-a_1)\cdots(a_n-a_1)\begin{vmatrix}
1&1&\cdots&1\\
a_1&a_2&\cdots&a_n\\
a_1^2&a_2^2&\cdots&a_n^2&\\
\vdots&\vdots&&\vdots&\\
a_1^{n-2}&a_2^{n-2}&\cdots&a_n^{n-2}&
\end{vmatrix}\\&=\cdots\\
&=\Pi_{a\leq j<i\leq n}(a_i-a_j).
\end{aligned}
$$
This result also shows that, existing $a_i=a_j$ is the necessary and sufficient condition for $d=0$.

**Theorem**: for a lower 2-block matrix,
$$
\begin{aligned}
\begin{vmatrix}
a_{11}&\cdots&a_{1k}&0&\cdots&0\\
\vdots&&\vdots&\vdots&&\vdots\\
a_{k1}&\cdots&a_{kk}&0&\cdots&0\\
c_{11}&\cdots&c_{1k}&b_{11}&\cdots&b_{1r}\\
\vdots&&\vdots&\vdots&&\vdots\\
c_{r1}&\cdots&c_{rk}&b_{r1}&\cdots&b_{rr}\\
\end{vmatrix}
=\begin{vmatrix}
a_{11}&\cdots&a_{1k}\\
\vdots&&\vdots\\
a_{k1}&\cdots&a_{kk}\\\end{vmatrix}
\begin{vmatrix}
b_{11}&\cdots&b_{1r}\\
\vdots&&\vdots\\
b_{r1}&\cdots&b_{rr}\\\end{vmatrix}
\end{aligned}
$$
*Proof:*

* k=1:

$$
\begin{aligned}
\begin{vmatrix}
a_{11}&0&\cdots&0\\

c_{11}&b_{11}&\cdots&b_{1r}\\
\vdots&\vdots&&\vdots\\
c_{r1}&b_{r1}&\cdots&b_{rr}\\
\end{vmatrix}
=\begin{vmatrix}a_{11}\end{vmatrix}
\begin{vmatrix}
b_{11}&\cdots&b_{1r}\\
\vdots&&\vdots\\
b_{r1}&\cdots&b_{rr}\\\end{vmatrix}
\end{aligned}
$$

* k > 1:

Suppose that for k=m-1, the theorem is true. Now  we consider k = m. Let's expand the matrix by the first row.
$$
\begin{aligned}
&\begin{vmatrix}
a_{11}&\cdots&a_{1m}&0&\cdots&0\\
\vdots&&\vdots&\vdots&&\vdots\\
a_{m1}&\cdots&a_{mm}&0&\cdots&0\\
c_{11}&\cdots&c_{1m}&b_{11}&\cdots&b_{1r}\\
\vdots&&\vdots&\vdots&&\vdots\\
c_{r1}&\cdots&c_{rm}&b_{r1}&\cdots&b_{rr}\\
\end{vmatrix}\\
=&a_{11}
\begin{vmatrix}
a_{22}&\cdots&a_{2m}&0&\cdots&0\\
\vdots&&\vdots&\vdots&&\vdots\\
a_{m2}&\cdots&a_{mm}&0&\cdots&0\\
c_{12}&\cdots&c_{1m}&b_{11}&\cdots&b_{1r}\\
\vdots&&\vdots&\vdots&&\vdots\\
c_{r2}&\cdots&c_{rm}&b_{r1}&\cdots&b_{rr}\\
\end{vmatrix}+\cdots+
(-1)^{1+i}\begin{vmatrix}
a_{21}&\cdots&a_{2,i-1}&a_{2,i+1}&\cdots&0&\cdots&0\\
\vdots&&\vdots&\vdots&&\vdots&&\vdots\\
a_{m1}&\cdots&a_{m,i-1}&a_{m,i+1}&\cdots&0&\cdots&0\\
c_{11}&\cdots&c_{1,i-1}&c_{1,i+1}&\cdots&b_{11}&\cdots&b_{1r}\\
\vdots&&\vdots&\vdots&&\vdots\\
c_{r1}&\cdots&c_{r,i-1}&c_{r,i+1}&\cdots&b_{r1}&\cdots&b_{rr}\\
\end{vmatrix}\\
=&\left[
a_{11}\begin{vmatrix}
a_{22}&\cdots&a_{2m}\\
\vdots&&\vdots\\
a_{m2}&\cdots&a_{mm}
\end{vmatrix}+\cdots+
(-1)^{1+i}a_{1i}
\begin{vmatrix}
a_{21}&\cdots&a_{2,i-1}&a_{2,i+1}&\cdots&a_{2m}\\
\vdots&&\vdots&\vdots&&\vdots\\
a_{m1}&\cdots&a_{2,i-1}&a_{2,i+1}&\cdots&a_{mm}
\end{vmatrix}+\cdots
\right]
\begin{vmatrix}
b_{11}&\cdots&b_{1r}\\
\vdots&&\vdots\\
b_{r1}&\cdots&b_{rr}\\\end{vmatrix}

% result
\\=&\begin{vmatrix}
a_{11}&\cdots&a_{1m}\\
\vdots&&\vdots\\
a_{m1}&\cdots&a_{mm}\\\end{vmatrix}
\begin{vmatrix}
b_{11}&\cdots&b_{1r}\\
\vdots&&\vdots\\
b_{r1}&\cdots&b_{rr}\\\end{vmatrix}
\end{aligned}
$$
Also, we notice that the transpose of an 2-upper block matrix is a lower block matrix, so the proof is similar.



# Cramer Theorem

$x_j=\frac{d_j}{d}$ where:
$$
\begin{aligned}
d&=\det(A)\\
d_j&=\begin{vmatrix}
a_{11}&\cdots&a_{1,j-1}&b_1&a_{1,j+1}&\cdots&a_{1n}\\
\vdots&&&&&&\vdots\\
a_{n1}&\cdots&a_{n,j-1}&b_n&a_{1,n+1}&\cdots&a_{nn}\\
\end{vmatrix}
\end{aligned}
$$

> Proof: 
>
> Let $I$ be an $n\times n$ unit matrix, and let's replace the i-th column of $I$ with $\pmb x=[x_1,\cdots,x_n]^T$. So:
$$
\begin{aligned}
&A\begin{bmatrix}
1&0&\cdots&x_1&0&\cdots\\
0&1&\cdots&x_2&0&\cdots\\
\vdots&\vdots&&\vdots&\vdots&\vdots\\
0&0&\cdots&x_j&0&\cdots\\
\vdots&\vdots&&\vdots&&0\\
0&0&\cdots&x_n&\cdots&1
\end{bmatrix}
=[\pmb a_1,\cdots,\pmb a_{j-1}, \pmb b,\pmb a_{j+1},\cdots,\pmb a_n]\\\rightarrow&
\det(A)x_i=d_j
\end{aligned}
$$
> so, $x_i=\frac{d_j}{d}$.

# Laplace Theorem

**minor matrix of order $k$**. i.e.,
$$
\begin{aligned}
D=\begin{vmatrix} a_{11} & a_{12} & a_{13} & a_{14} & a_{15}\\ a_{21} & a_{22} & a_{23} & a_{24} & a_{25}\\ \vdots & \vdots & \vdots & \vdots & \vdots \\ a_{51} & a_{52} & a_{53} & a_{54} & a_{55} \end{vmatrix},\quad M=\begin{vmatrix} a_{12} & a_{13} &a_{15} \\ a_{22} & a_{23}& a_{25}\\ a_{42} & a_{43} & a_{45} \end{vmatrix},\quad M'=\begin{vmatrix} a_{31} & a_{34}\\ a_{51} &a_{54} \end{vmatrix}
\end{aligned}
$$
**Laplace Theorem**: If $k (1\leq k\leq n-1)$ rows are arbitrarily taken in determinant $D$, the sum of the products of all k-order polynomials composed of these k rows and their algebraic residues is equal to determinant $D$.

> Proof:
$$
\begin{aligned}
|A|&=\begin{vmatrix} a_{11} & a_{12} & \cdots & a_{1k} & |& a_{1,k+1} & \cdots & a_{1n}\\ \vdots & \vdots & M & \cdots & | & \vdots & &\vdots \\ a_{k1} & a_{k2} &\cdots & a_{kk}& | & a_{k,k+1} & \cdots & a_{kn}\\ -&- &- &- &-|-&- &- &- \\ a_{k+1,1}& a_{k+1,2} &\cdots & a_{k+1,k} & |& a_{k+1,k+1} & \cdots & a_{k+1,n}\\ \vdots & \vdots & & \vdots& |& \vdots & M' & \vdots\\ a_{n1} & a_{n2} & \cdots & a_{nk} & |& a_{n,k+1} & \cdots & a_{nn}\end{vmatrix},\\
\text{L.H.S.}&=\sum_{j_1j_2\cdots j_n}a_{1j_1}a_{2j_2}\cdots+a_{nj_n},\\
\text{terms of R.H.S.}&=C^k_nk!(n-k)!=n!,\\

\end{aligned}
$$
If every element in the LHS has a corespondent element in the RHS, then we could prove this equation.

Firstly, let's consider a special case that M is in the first $k$ rows. We choose the $\alpha_1,\alpha_2,\cdots,\alpha_k$ to be a certain permutation of the column indexes. Like $M$ shown below. And the rest columns are chosen to be a new matrix which are denoted as $\beta_{k+1},\cdots,\beta_{n}$, a permutaion from 1 to n-k+1. So 

Then if we calculate the determinant of M, a certain term would be: 
$$
\begin{aligned}
(-1)^{\tau(\alpha_1\cdots\alpha_k)}a_{1,\alpha_1}a_{2,\alpha_2}\cdots a_{n,\alpha_n},
\end{aligned}
$$
then consider a permutation corresponds with it in $M'$:
$$
\begin{aligned}
&(-1)^{\tau((\beta_{k+1}-k)\cdots(\beta_{n}-k))}a_{k+1,\beta_{k+1}}\cdots a_{n,\beta_{n}}\\
=&(-1)^{\tau(\beta_{k+1}\cdots\beta_{n})}a_{k+1,\beta_{k+1}}\cdots a_{n,\beta_{n}}
\end{aligned}
$$
we add this term to the corresponding term in M:
$$
\begin{aligned}
&(-1)^{\tau(\alpha_1\cdots\alpha_k)+\tau(\beta_{k+1}\cdots\beta_{n})}a_{k+1,\beta_{k+1})}a_{1,\alpha_1}a_{2,\alpha_2}\cdots a_{n,\alpha_n}a_{k+1,\beta_{k+1}}\cdots a_{n,\beta_{n}}\\
=&(-1)^{\tau(\alpha_1\cdots\alpha_k\beta_{k+1}\cdots\beta_{n})}a_{k+1,\beta_{k+1})}a_{1,\alpha_1}a_{2,\alpha_2}\cdots a_{n,\alpha_n}a_{k+1,\beta_{k+1}}\cdots a_{n,\beta_{n}}\\
&\text{ for every }\beta\text{ is lager than }\alpha\\
=&(-1)^{\tau(j_1\cdots j_n)}a_{1j_1}\cdots a_{nj_n},
\end{aligned}
$$
we noitice that this is a term of the original determinant. So $|M||M'|=|D|$. Then if we consider a general case, we notice that if we exchange some rows, we could always construct a determinant like that cause the result of the determinant only depents on how many times we have exchanged the rows. For example, if we choose $i_1,\cdots,i_k$ rows, we could move $i_1$ to the first row with $i_1-1$-th operations. The total sum of our row operations is $i_1-1+i_2-2+\cdots+i_k-k=(i_1+\cdots+i_k)-(1+\cdots+k)$. Also we could calculate the number of our column operations is $j_1-1+j_2-2+\cdots+j_k-k=(j_1+\cdots+j_k)-(1+\cdots+k)$en the result becomes:
$$
\begin{aligned}
&(-1)^{(i_1+\cdots+i_k+j_1+\cdots+j_k-2(1+\cdots+k)}D\\%(-1)^{\tau(j_1\cdots j_n)}a_{1j_1}\cdots a_{nj_n}\\
=&(-1)^{(i_1+\cdots+i_k+j_1+\cdots+j_k)}D\\%(-1)^{\tau(j_1\cdots j_n)}a_{1j_1}\cdots a_{nj_n}
=&(-1)^{(i_1+\cdots+i_k+j_1+\cdots+j_k)}MM'
\end{aligned}
$$
And we call $(-1)^{(i_1+\cdots+i_k+j_1+\cdots+j_k)}M'$ to be the cofactor of M.


$\det(AB)=\det(A)\det(B)$. Proof:
$$
\begin{aligned}
D_{}=\begin{vmatrix} a_{11} & a_{12} & \cdots &a_{1n} &0&0&0&0\\ a_{21} &a_{22} &\cdots & a_{2n}&0&0&0&0\\ \vdots & \vdots & &\vdots &0&0&0&0\\ a_{n1} & a_{n2} &\cdots & a_{nn} &0&0&0&0\\ -1&0&\cdots &0&b_{11}&b_{12}&\cdots&b_{1n}\\ 0&-1&\dotso&0&b_{21}&b_{22}&\cdots&b_{2n}\\ \vdots & \vdots & &\vdots&\vdots & \vdots &&\vdots \\ 0&0&\cdots&-1 &b_{n1}&b_{n2}&\cdots &b_{nn} \end{vmatrix},
\end{aligned}
$$
According to the Laplace Theorem, if we only expand the first n rows, then any column from the last n columns makes the determinant to be 0, cause only $M=\begin{vmatrix}a_{11}&\cdots&a_{1n}\\\vdots&&\vdots\\a_{n1}&\cdots&a_{nn}\end{vmatrix}\neq0$, so $\sum MM'=\begin{vmatrix}a_{11}&\cdots&a_{1n}\\\vdots&&\vdots\\a_{n1}&\cdots&a_{nn}\end{vmatrix}\begin{vmatrix}b_{11}&\cdots&b_{1n}\\\vdots&&\vdots\\b_{n1}&\cdots&b_{nn}\end{vmatrix}=\det(A)\det(B)$.