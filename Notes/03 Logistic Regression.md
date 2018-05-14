### Binary Classification
#### Define
1. Sigmoid Function `Logistic Function`
$$ h_\theta(x) = g(\theta^Tx) $$
$$ z = \theta^Tx $$
$$ 0 <= g(z) = \frac{1}{1 + e^{-z}} <= 1 $$

2. $ h_\theta(x) $ the probability that the output is 1.
3. $ h_\theta(x) = P(y = 1 | x; \theta) $
4. $ P(y = 0 | x; \theta) + P(y = 1 | x; \theta) = 1 $
5. 设置 0.5为判定边界，则 $h_\theta(x)=0.5 <==> \theta^Tx = 0$
#### Cost Function

- $$J(\theta) = \dfrac{1}{m} \sum_{i=1}^m \mathrm{Cost}(h_\theta(x^{(i)}),y^{(i)})$$
- $$ \mathrm{Cost}(h_\theta(x),y) = -\log(h_\theta(x)) ,\text{if y = 1} $$
- $$ \mathrm{Cost}(h_\theta(x),y) = -\log(1-h_\theta(x)), \text{if y = 0} $$
- $$ Cost(h_\theta(x), y) = -ylog(h_\theta(x)) - (1 - y)log(1 - h_\theta(x)) $$

#### Algorithm
$\begin{align*} & Repeat \; \lbrace \newline & \; \theta_j := \theta_j - \frac{\alpha}{m} \sum_{i=1}^m (h_\theta(x^{(i)}) - y^{(i)}) x_j^{(i)} \newline & \rbrace \end{align*}$

- 虽然跟梯度下降相同但两者$h_\theta(x)$的定义并不相同
- 逻辑回归也可以通过特征缩放来加快收敛速度

1. 可用于计算 $\theta$ 的算法
 - Gradient descent
 - Conjugate gradient
 - BFGS 共轭梯度法（变尺度法）
 - L-BFGS 限制变尺度法   
 - 后三种算法的特性
 
 >Advantages: 
 >a.no need to manually pick $\alpha$ 
 > b.often faster than gradient descent
 >Disadvantages:
 > More complex
 
2. Octave 的优化算法使用

```
%exitFlag: 1 收敛
%R(optTheta) >= 2
options = optimset(‘GradObj’, ‘on’, ‘MaxIter’, ‘100’);
initialTheta = zeros(2, 1);
[optTheta, functionVal, exitFlag] ...
    = fminumc(@costFunction, initialTheta, options);
    
%costFunction:
function [jVal, gradient] = costFunction(theta)
    jVal = ... %cost function
    gradient = zeros(n, 1); %gradient
    
    gradient(1) = ...
    ...
    gradient(n) = ...
```

### Multi-class classification
#### one-vs-all `one-vs-rest`
- Train a logistic regression classifier $h_\theta^{(i)}(x)$ for each class $i$ to predict the probability that $y = i$.
- On a new input $x$, to make a prediction, pick the class $i$ that maximizes $\max \limits_ih_\theta^{(i)}(x)$