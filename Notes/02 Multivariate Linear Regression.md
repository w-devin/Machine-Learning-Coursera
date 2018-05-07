1. h(x)
$$
\begin{align*}h_\theta(x) =\begin{bmatrix}\theta_0 \hspace{2em} \theta_1 \hspace{2em} ... \hspace{2em} \theta_n\end{bmatrix}\begin{bmatrix}x_0 \newline x_1 \newline \vdots \newline x_n\end{bmatrix}= \theta^T x\end{align*}, x_0^{(i)} = 1
$$

2. Gradient descent equation
$$
\begin{align*}& \text{repeat until convergence:} \; \lbrace \newline \; & \theta_j := \theta_j - \alpha \frac{1}{m} \sum\limits_{i=1}^{m} (h_\theta(x^{(i)}) - y^{(i)}) \cdot x_j^{(i)} \; & \text{for j := 0...n}\newline \rbrace\end{align*}
$$

3. 当不同特征的值差距过大$(>10^5)$时，需要特征缩放(Feature Scaling)
    
    $$
        x_i := \frac{x_i - \mu_i}{s_i}
    $$
    Where $\mu_i$ is the average of all the values for feature(i) and $s_i$ is the range of values(max - min), or $s_i$ is the standard deviation.
    
4. Learning Rate
    In automatic convergence test, declare convergence if $J(\theta)$ decreases by less than $1-^{-3}$ in one iteration.

4. Features and Polynomial Regression
    可以将不同的特征值组合来更好的拟合数据，同时因为数据的组合，更加需要特征缩放来加快几何提高精度
    
5. Normal Equation 正规方程 不需要特征缩放
$$
    \theta = (X^TX)^{-1}X^Ty
$$
     
     
6. Comparation

 | Gradient Descent | Normal Equation |
 | :-------: | :-------: |
 | need to choose $\alpha$| No need to choose $\alpha$|
 | Needs many iterations | Don’t need to iterate |
 | Works well even when n is large ($>10^4$) | Need to compute $(X^TX)^{-1}$|
 | $O(kn^2)$ | Slow if n is very large $O(n^3)$ |

7. If $X^TX$ is noninvertible, the common causes might be having :    - Redundant features, where two features are very closely related (i.e. they are linearly dependent)    - Too many features (e.g. m ≤ n). In this case, delete some features or use "regularization" (to be explained in a later lesson).
