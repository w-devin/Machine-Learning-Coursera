#### Symbols:
- **m** = Number of training examples
- **x**’s = “input” variable /features
- **y**’s = “output” variable / “target” variaable
- (x, y) = one training example
- $(x^{(i)}, y^{(i)})$ = $i_{th}$ training example
- h(x) = hypothesis function
- $h_\theta(x) = \theta_0 + \theta_1x$  *shorthand:h(x)*

#### Cost Function 
- squared cost function
$$J(\theta_0, \theta_1) = \dfrac {1}{2m} \displaystyle \sum _{i=1}^m \left ( \hat{y}_{i}- y_{i} \right)^2 = \dfrac {1}{2m} \displaystyle \sum _{i=1}^m \left (h_\theta (x_{i}) - y_{i} \right)^2$$
- Goal: $minimize_{\theta_0, \theta_1}J(\theta_0, \theta_1)$

#### Gradient descent
>repeat until convergence {
>>    $\theta_j := \theta_j - \alpha \frac{\partial}{\partial \theta_j} J(\theta_0, \theta_1)$  (for j = 0 and j = 0)
>}

*需要同时更新$\theta_j$, 否则先更新$\theta_i$会对后面的项的更新产生影响*

$\begin{align*} \text{repeat until convergence: } \lbrace & \newline \theta_0 := & \theta_0 - \alpha \frac{1}{m} \sum\limits_{i=1}^{m}(h_\theta(x_{i}) - y_{i}) \newline \theta_1 := & \theta_1 - \alpha \frac{1}{m} \sum\limits_{i=1}^{m}\left((h_\theta(x_{i}) - y_{i}) x_{i}\right) \newline \rbrace& \end{align*}$
