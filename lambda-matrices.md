<p align='center'><font size=6><b>λ-矩阵</b></font></p>

# 定义和性质



* n阶λ-矩阵可逆的充要条件为：$|A(\lambda)|$是非零的数。

> Proof:
>
> 充分性：如果$A(\lambda)$是可逆的，那么一定有$A(\lambda)B(\lambda)=I$, 即：$|A(\lambda)||B(\lambda)|=1$，因此必然有$|A(\lambda)|$是非零的数。
>
> 必要性：当$A(\lambda)\neq0$ ，有$A(\lambda)A(\lambda)^*=A(\lambda)^*A(\lambda)=|A(\lambda)|I$，此时$\frac{A(\lambda)^*}{|A(\lambda|}A(\lambda)=I$，因此它必然有逆。

# λ-矩阵的初等变换和标准形

$A(\lambda)$等价于$B(\lambda)$，如果$A(\lambda)$可以由$B(\lambda)$经过一系列初等变换得到。

* 
* 如果矩阵左上角第一个元素$a_{11}(\lambda)$非零，且至少存在一个$a_{ij}(\lambda)$满足$a_{11}(\lambda)\nmid a_{ij}(\lambda)$，那么存在$B(\lambda)$与$A(\lambda)$等价，且$\deg b_{11}(\lambda)<\deg a_{11}(\lambda)$。（$\deg f(\lambda)$：多项式次数）

例如：

$$
\begin{aligned}
A(\lambda) = &
\begin{pmatrix}
\lambda^3 - \lambda & 2\lambda^2 \\
\lambda^2 + 5\lambda & 3\lambda
\end{pmatrix} \rightarrow 
\begin{pmatrix}
3\lambda & \lambda^2 + 5\lambda \\
2\lambda^2 & \lambda^3 - \lambda
\end{pmatrix} \rightarrow 
\begin{pmatrix}
3\lambda & \lambda^2 + 5\lambda \\
0 & \lambda^3 - 10\lambda^2 - 3\lambda
\end{pmatrix}\\
&\rightarrow 
\begin{pmatrix}
\lambda & 0 \\
0 & \lambda^3 - 10\lambda^2 - 3\lambda
\end{pmatrix} = B(\lambda).
\end{aligned}
$$



# 不变因子

* k级行列式因子：如果$A(\lambda)$的秩为r，对于不大于r的**正整数**k，将会有非零的k级子式。而$A(\lambda)$中所有k级子式首项公因式为1的最大公因式$D_k(\lambda)$叫做$A(\lambda)$的k级**行列式因子**。显然，$A(\lambda)$将会有r各行列式因子。行列式因子在初等变换下是**不变的**。例如：
  $$
  \begin{aligned}
  \begin{pmatrix}
  \lambda^2+\lambda&0&0\\
  0&\lambda&0\\
  0&0&(\lambda+1)^2
  \end{pmatrix}\end{aligned}
  $$
  的一级非零子式公因式为$D_1(\lambda)=1$，二级非零子式分别为$\left|\begin{matrix}\lambda^2+\lambda&0\\0&\lambda\end{matrix}\right|=(\lambda+1)\lambda^2$, $\left|\begin{matrix}\lambda^2+\lambda&0\\0&(\lambda+1)^2\end{matrix}\right|=\lambda(\lambda+1)^3$, $\left|\begin{matrix}\lambda&0\\0&(\lambda+1)^2\end{matrix}\right|=(\lambda^2+1)\lambda$，它们的最大公因式为$D_2(\lambda)=\lambda(\lambda+1)$。而三级非零子式为它本身的行列式，因此$D_3(\lambda)=\lambda^2(\lambda+1)^3$。

  > 回顾：
  >
  > **k级子式** - 从n阶行列式D中任取k行与k列，由这k行和k列交点处的数构成的k阶*行列式*
  >
  > **主子式** - 也是选k行k列，但行和列下标要相同，如行为a1、a2、a5，列必须为b1、b2、b5
  >
  > **顺序主子式** - 同是选k行k列，是主子式的一种，但要求下标只能从1行1列依次按顺序取
  >
  > **余子式** - 在n阶行列式中，划去$a_{ij}$所在的第i行与第j列的元素，将剩下的元素不改变原来的顺序所构成的n−1阶行列式称为$a_{ij}$的余子式，用$M_{ij}$表示。
  >
  > **代数余子式** - $a_{ij}$的代数余子式$C_{ij}=(−1)^{i+j}M_{ij}$

* **定理**：等价的λ-矩阵具有相同的秩和相同的各级行列式因子。

  在这里，我们看一看如何计算各级的行列式因子。假设标准形为：
  $$
  \begin{aligned}
  \begin{pmatrix}
  d_1(\lambda)\\
  &d_2(\lambda)\\
  &&\ddots\\
  &&&d_r(\lambda)\\
  &&&&0\\
  &&&&&\ddots\\
  &&&&&&0
  \end{pmatrix}
  \end{aligned}
  $$
  显然，k级子式只能取对角线的元素作为子式对角线元素构成（否则行列式值为0，不满足“非零子式”条件）。由于$d_i(\lambda)|d_{i+1}(\lambda),i=1,2,\cdots,r-1$，假设我们选择的k各元素是 $\cdots,d_m(\lambda),d_{m+n}(\lambda),...$，对于其中$d_m(\lambda),d_{m+n}(\lambda)$，由于$d_{m+1}(\lambda)|d_{m+n}(\lambda)$，并且$\deg d_{m+1}(\lambda)<\deg d_{m+n}(\lambda)$, $d_m(\lambda)\cdot d_{m+n}(\lambda)$ 和$d_m(\lambda)\cdot d_{m+1}(\lambda)$的公因式相同且均为$d_m(\lambda)\cdot d_{m+1}(\lambda)$。由此递归，必然，k级子式的最大公因式一定是：
  $$
  \Pi_{i=1}^kd_i(\lambda)
  $$
  

* 定理：**λ-矩阵的标准型是唯一的。**


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

