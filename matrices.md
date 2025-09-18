<p align='center'><font size=6><b>矩阵</b></font></p>



# 代数余子式

设 $ A $ 是一个 $ n $ 阶方阵，$ a_{ij} $ 是 $ A $ 的第 $ i $ 行第 $ j $ 列元素。

- **余子式** $ M_{ij} $：删除第 $ i $ 行和第 $ j $ 列后得到的 $ (n-1) $ 阶子矩阵的行列式
- **代数余子式** $ C_{ij} $：$ C_{ij} = (-1)^{i+j} M_{ij} $

## 主要性质

1. **行列式展开定理**
   - 按第 $ i $ 行展开：$ \det(A) = \sum_{j=1}^n a_{ij}C_{ij} $
   - 按第 $ j $ 列展开：$ \det(A) = \sum_{i=1}^n a_{ij}C_{ij} $

2. **交错性质**
   - 当 $ i \neq k $ 时：$ \sum_{j=1}^n a_{ij}C_{kj} = 0 $
   - 当 $ j \neq l $ 时：$ \sum_{i=1}^n a_{ij}C_{il} = 0 $

> Proof
>
> **构造辅助矩阵 $ A' $** :
> 将 $ A $ 的第 $ k $ 行替换为第 $ i $ 行（$k\neq i$)，得到矩阵 $ A' $。此时 $ A' $ 有两行相同（第 $ i $ 行和第 $ k $ 行）。必然，$ \det(A')=0 $。
> 
> 我们将其按第 $ k $ 行展开：
$$
\det(A') = \sum_{j=1}^n a'_{kj}C'_{kj} = \sum_{j=1}^n a_{ij}C_{kj}
$$
> 因为 $ A' $ 的第 $ k $ 行元素为 $ a_{ij} $，且余子式 $ C'_{kj} = C_{kj} $ 不受第 $ i $ 行替换影响。
>
> 3. **得出等式** 
>    
>    $0 = \det(A') = \sum_{j=1}^n a_{ij}C_{kj}$

**几何解释**

- 行列式展开本质是投影计算
- 交错性反映了不同行/列向量的线性相关性
- 当 $ i \neq k $ 时，用第 $ i $ 行元素与第 $ k $ 行余子式组合，相当于在"错误方向"投影，结果为零

此性质是证明伴随矩阵公式 $ A \cdot \text{adj}(A) = \det(A)I $ 的核心工具。

1. **伴随矩阵**
   - 伴随矩阵 $ \text{adj}(A) $ 由代数余子式构成：$ (\text{adj}(A))_{ji} = C_{ij} $
   - 逆矩阵公式：$ A^{-1} = \frac{1}{\det(A)} \text{adj}(A) $

2. **Laplace展开**
   - 可推广到多行/多列展开

## 示例

计算矩阵 $ A = \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix} $ 的代数余子式：

- $ C_{11} = (-1)^{1+1} \cdot 4 = 4 $
- $ C_{12} = (-1)^{1+2} \cdot 3 = -3 $
- $ C_{21} = (-1)^{2+1} \cdot 2 = -2 $
- $ C_{22} = (-1)^{2+2} \cdot 1 = 1 $

行列式 $ \det(A) = 1 \cdot C_{11} + 2 \cdot C_{12} = 1 \times 4 + 2 \times (-3) = -2 $

# 伴随矩阵的几个性质

对于伴随矩阵：
$$
\begin{aligned}
A^*=\left(\begin{matrix}
C_{11}&C_{21}&...&C_{n1}\\
C_{12}&C_{22}&...&C_{n2}\\
\vdots&\vdots&&\vdots\\
C_{1n}&C_{2n}&...&C_{nn}\\
\end{matrix}\right)
\end{aligned}
$$
其中，$C_{ij}$是$a_{ij}$的代数余子式。

* $AA^*=A^*A=|A|I$
$$
\begin{aligned}
AA^*&=
\begin{bmatrix}
a_{11}&a_{21}&...&a_{n1}\\
a_{12}&a_{22}&...&a_{n2}\\
\vdots&\vdots&&\vdots\\
a_{1n}&a_{2n}&...&a_{nn}\\
\end{bmatrix}
\begin{bmatrix}
C_{11}&C_{12}&...&C_{1n}\\
C_{21}&C_{22}&...&C_{2n}\\
\vdots&\vdots&&\vdots\\
C_{n1}&C_{n2}&...&C_{nn}\\
\end{bmatrix}\\
AA^*(i,j)&=\sum_{k=1}^n a_{ik}C_{jk}
=\begin{cases}
|A|,~i=j\\
0,\quad i\neq j
\end{cases}\\\Rightarrow
AA^*&=\begin{bmatrix}
|A|&0&...&0\\
0&|A|&...&0\\
\vdots&\vdots&&\vdots\\
0&0&...&|A|
\end{bmatrix}\\
&=|A|I
\end{aligned}
$$

同理可证$A^*A=|A|I$。

由此我们可以得到一个重要的式子：$A^*=|A|A^{-1}$。

*  $(A^*)^{-1}=(A^{-1})^*=\frac A{|A|}$

$$
\begin{aligned}
\frac{AA^*}{|A|}&=I\\\rightarrow
(A^*)^{-1}&=\frac{A}{|A|},\\
A^{-1}&=\frac{A^*}{|A|}\\\rightarrow
A^{-1}(A^{-1})^*&=|A^{-1}|I\\
AA^{-1}(A^{-1})^*&=(A^{-1})^*=\frac{A}{|A|}
\end{aligned}
$$

