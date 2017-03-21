aspiration   渴望，抱负  aspire  渴望，立志，追求  vi
quintessential  精粹的，精华的
cycle  cyclic  循环的acyclic  非循环的
stochastic   随机的   random  
rectify  改正 ，修正  rectified
saturate  饱和的，浸透的，使饱和，使充满
verge   边缘 n  出来边缘，临近  vergence   聚散度  converge   聚拢，收敛   diverge分歧，偏离
entropy  熵


propagate  传播，繁殖 vt/vi  propagation
## content
- [Deep Feedforward Networks](#deep-feedforward-networks)
    - [Conclusion](#Conslusion)
    - [Intro](#intro)
    - [Learning Xor](#learning-xor)
    - [Gradient-Based Learning](#gradient-based learning)
    - [Hidden Units](#6.3 Output Units)
    - [Architecture Design](#6.4 Architecture Design)
    - [Back-Propagation and Other algorithm](#6.5 Back-propagation)
    - [historical Notes](#6.6 historical Notes]


## Deep Feedforward Networks
### Conclusion
DFN  作为一个高层高层嵌套函数，需要参数化的部分在于
1. 非线性函数的选择，可以是三种选择，一是kernel，二是计算机穷尽测试，三是自己设计基础函数集，由计算机组合选择
2. cost function选择，采用max likelihood方法（cross entropy ) + 正则化或者simple func + 正则化
3.

需要注意的问题
1. saturate problem ,在于有的节点值趋于饱和以后输入的改变对输出的改变很小，此时梯度dy / dx 趋近于0，会变得收敛很慢或者难以收敛。negative log-likelihood helps to avoid this problem for many models
2. 数据本身可能是不能够完全反应问题的，因为线索不多，那么产生的往往不是一个确定的输出，而是输出的概率表

在输出层进行线性回归之前，通过仿射变换+非线性函数的方式不断地由低层feature形成高层feature
no feedback connections in which outputs of the model are fed back into itself

Feedforward neural networks are called networks because they are typically represented by composing together many different functions



 对于某个节点，输入权重是投影向量b, 输出结果是输入向量a的

limited to linear functions, so
the model cannot understand the interaction between any two input variables.

To extend linear models to represent nonlinear functions of x, we can apply
the linear model not to x itself but to a transformed input φ(x), where φ is a
nonlinear transformationWe can think of φ as providing a set of features describing

### Intro



### Learning Xor
原空间线性不可分，需要通过非线性函数，找到合适的feature space
Most neural
networks do so using an affine transformation controlled by learned parameters,
followed by a fixed, nonlinear function called an activation function.  

rectified function's feature
1. The rectified linear activation function. This activation function is the default
activation function recommended for use with most feedforward neural networks  
2. rectified linear units are nearly linear, they
preserve many of the properties that make linear models easy to optimize with gradientbased methods


### Gradient-Based Learning

#### 6.2.1 Cost Functions
1. maximum likelihood



Sometimes, we take a simpler approach, where rather than predicting a complete
probability distribution over y, we merely predict some statistic of y conditioned
on x. Specialized loss functions allow us to train a predictor of these estimates.
regularization term



saturate   问题

2. Learning Conditional Statistics
calculus of variations may be used to derive the following two results  
