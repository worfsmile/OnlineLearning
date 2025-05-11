用计算$P(r_t|x_{1:t-1})$来实现变点检测

$$
P(r_t|x_{1:t})=\frac{P(r_t, x_{1:t})}{P(x_{1:t})}\\
P(r_t, x_{1:t}) = \sum_{r_{t-1}}P(r_t|r_{t-1})P(x_t|r_{t-1},x^{(r)}_t)P(r_{t-1},x_{1:t-1})\\
P(r_t|r_{t-1}) = H(r_{t-1}+1)\ if\ r_t = 0\\
P(x_t|r_{t-1},x^{(r)}_t) = \pi\\
P(r_{t-1},x_{1:t-1})由t = 0开始动态计算\\
\pi 是包含了之前点的信息的概率分布
$$

insight的地方
1. 使用$r_t$来代替变点检测
2. 使用马尔可夫过程，引入隐变量来递归计算$r_t$
3. 使用包含之前信息的概率分布来作为后验分布
原文:[
    Bayesian online changepoint detection
](<../../continual_meta_learning/ood_detection/bayesian_online_changepoint_detection/Bayesian online changepoint detection.pdf>)
代码:[
    bayesian_changepoint_detection
](../../continual_meta_learning/ood_detection/bayesian_online_changepoint_detection/bayesian_changepoint_detection-master/bayesian_changepoint_detection)
