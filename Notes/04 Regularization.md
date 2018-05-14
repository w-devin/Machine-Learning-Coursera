### Regularization 
for Linear Regression and Logistic Regression

#### Define

 1. under-fitting `欠拟合(high bias)`
 2. over-fitting `过拟合 (high variance)`:have too many features, fail to generalize(泛化) to new examples.
 
#### Addressing over-fitting

1. Reduce number of features.
 - Manually select which features to keep.
 - Model selection algorithm.
2. Regularization
 - Keep all the features. but reduce magnitude/values of parameters $\theta_j$.
 - Works well when we have a lot of features, each of whitch contributes a bit to predicting $y$.

#### Regularized Cost Function
-  $$min_\theta \dfrac{1}{2m} \sum_{i=1}^m (h_\theta(x^{(i)}) - y^{(i)})^2 + \lambda \sum_{j=1}^n \theta_j^2$$

#### Regularized Linear Regression
1. Gradient Descent
$$
\begin{align*} & \text{Repeat}\ \lbrace \newline & \ \ \ \ \theta_0 := \theta_0 - \alpha\ \frac{1}{m}\ \sum_{i=1}^m (h_\theta(x^{(i)}) - y^{(i)})x_0^{(i)} \newline & \ \ \ \ \theta_j := \theta_j - \alpha\ \left[ \left( \frac{1}{m}\ \sum_{i=1}^m (h_\theta(x^{(i)}) - y^{(i)})x_j^{(i)} \right) + \frac{\lambda}{m}\theta_j \right] &\ \ \ \ \ \ \ \ \ \ j \in \lbrace 1,2...n\rbrace\newline & \rbrace \end{align*}
$$

 - 等价于
 $$
\theta_j := \theta_j(1 - \alpha\frac{\lambda}{m}) - \alpha\frac{1}{m} \sum_{i=1}^m(h_\theta(x^{(i)}) - y^{(i)})x_j^{(i)}
 $$

2. Normal Equation
$$
\begin{align*}& \theta = \left( X^TX + \lambda \cdot L \right)^{-1} X^Ty \newline& \text{where}\ \ L = \begin{bmatrix} 0 & & & & \newline & 1 & & & \newline & & 1 & & \newline & & & \ddots & \newline & & & & 1 \newline\end{bmatrix}\end{align*}
$$

- 对于不可逆的$(X^TX)$, $(X^TX + \lambda.L)$ 会可逆

#### Regularized Logistic Regression
1. Cost Function

$$
J(\theta) = -\frac{1}{m} \sum_{i=1}^m[y^{(i)}log(h_\theta(x^{(i)})) + (1 - y^{(i)})log(1 - h_\theta(x^{(i)}))] + \frac{\lambda}{2m}\sum_{j=1}^n\theta_j^2
$$

2. Gradient descent
$$
\begin{align*} & \text{Repeat}\ \lbrace \newline & \ \ \ \ \theta_0 := \theta_0 - \alpha\ \frac{1}{m}\ \sum_{i=1}^m (h_\theta(x^{(i)}) - y^{(i)})x_0^{(i)} \newline & \ \ \ \ \theta_j := \theta_j - \alpha\ \left[ \left( \frac{1}{m}\ \sum_{i=1}^m (h_\theta(x^{(i)}) - y^{(i)})x_j^{(i)} \right) + \frac{\lambda}{m}\theta_j \right] &\ \ \ \ \ \ \ \ \ \ j \in \lbrace 1,2...n \rbrace \newline & \rbrace \end{align*}
$$