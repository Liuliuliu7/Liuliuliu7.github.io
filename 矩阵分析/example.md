设 \( A \in \mathbb{R}^{m \times n}, b \in \mathbb{R}^m \)，若非齐次线性方程组 \( Ax = b \) 有解，则在 \( R(A^T) \) 中只有 \( Ax = b \) 的一个解向量。

> 先证明存在性.
> 记 \( x_0 \in \mathbb{R}^n \) 为 \( Ax = b \) 的一个解向量, 即 \( Ax_0 = b \).
> 若 $x_0 \in R(A^T)$, 则在 \( R(A^T) \) 中有 \( Ax = b \) 的解向量.
> 若 $x_0 \notin R(A^T)$, 由于 \( R(A^T) \subset  \mathbb{R}^n \), 则$ x_0$ 可以分解为$ R(A^T)$ 和 $ N(A)$中的向量之和, 即$ x_0 = x_p + x_n$, 其中 $x_p \in R(A^T), x_n \in N(A)$.
> 显然$ x_p$ 是$ Ax=b$的解, 因为 $ A(x_0) = A(x_p + x_n) = A(x_p) + A(x_n) = A(x_p) = b$
> 所以, \( R(A^T) \) 中一定存在 \( Ax = b \) 的解向量.
> 再证唯一性.
> 假设存在 $x_p^ \prime  \in R(A^ \top )$, 有 $x _p^\prime \neq x_p$, $A(x_p^ \prime) = b$. 则有 $A(x_p^ \prime - x_p) = 0$, 即 $x_p^ \prime - x_p \in N(A)$. 而$ (x_p^ \prime - x_p) \in R(A^ \top )$, 所以 $x_p^ \prime - x_p = 0$, 即 $x_p^ \prime = x_p$
> 所以, \( R(A^T) \) 中只有 \( Ax = b \) 的一个解向量. 这个解向量即为 \( x_p = Proj_{A^\top }x \).