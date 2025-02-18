# DeepLearningBookQA_cn

<!---<img src="http://file.epubit.com.cn/ScreenShow/1707d90d7c6c6aa54cca" width = "20%" />-->

### 那些深度学习《面试》你可能需要知道的（中文页标版）

#### 本文原作者Jin Lee，本文原载于知乎专栏。
问题集： https://zhuanlan.zhihu.com/p/29936999

回答及对应英文页标：https://zhuanlan.zhihu.com/p/29965072

> _原文是问题 “那些深度学习《面试》你可能需要知道的” 的回答，答案均以英文版Deep Learning页标标记。_

> _本文是以中文纸质版Deep Learning页标标记，加入了少量说明。_


#### 1. 列举常见的一些范数及其应用场景，如 L0，L1，L2，L∞，Frobenius 范数

答：p24-p25 ；还有 p141-p156 有 regularization 的应用


#### 2. 简单介绍一下贝叶斯概率与频率派概率，以及在统计中对于真实参数的假设。

答：  the frequentist perspective is that the true
parameter value θ is fixed but unknown, while the point estimate θˆ is a random
variable on account of it being a function of the **dataset (which is seen as random)**.
The Bayesian perspective on statistics is quite different. The Bayesian uses
probability to reflect degrees of certainty of states of knowledge. The dataset is
directly observed and so is not random. On the other hand, the true parameter θ
is unknown or uncertain and thus is represented as a random variable.

from DL

#### 3. 概率密度的万能近似器

答：p43：3.10 上面那一段

#### 4. 简单介绍一下 sigmoid，relu，softplus，tanh，RBF 及其应用场景

答：sigmoid 和 softplus 在 p43 页；全部的在 p123-p127

#### 5.Jacobian，Hessian 矩阵及其在深度学习中的重要性

答：p56-p62

#### 6.KL 散度在信息论中度量的是那个直观量

答：p46
Given two distributions p and q, it is often useful to define a distance metric to measure how “close”
or “similar” they are.  we can interpret
the KL divergence as the “extra number of bits” you need to pay when compressing data samples
 if you use the incorrect distribution q as the basis of your coding scheme compared to the true
 distribution p

 from PML



#### 7. 数值计算中的计算上溢与下溢问题，如 softmax 中的处理方式

考虑一下当所有 xi 都等于某个常数 c 时会发生什么。从理论分析上说，我们可以发 现所有的输出都应该为 n1 。从数值计算上说，当 c 量级很大时，这可能不会发生。如 果 c 是很小的负数，exp(c) 就会下溢。这意味着 softmax 函数的分母会变成 0，所以 最后的结果是未定义的。当 c 是非常大的正数时，exp(c) 的上溢再次导致整个表达 式未定义。这两个困难能通过计算 softmax(z) 同时解决，其中 z = x − maxi xi。简 单的代数计算表明，softmax 解析上的函数值不会因为从输入向量减去或加上标量 而改变。减去 maxi xi 导致 exp 的最大参数为 0，这排除了上溢的可能性。同样地， 分母中至少有一个值为 1 的项，这就排除了因分母下溢而导致被零除的可能性

答：p52-p53

#### 8. 与矩阵的特征值相关联的条件数 (病态条件) 指什么，与梯度爆炸与梯度弥散的关系

答：p53;

#### 9. 在基于梯度的优化问题中，如何判断一个梯度为 0 的零界点为局部极大值／全局极小值还是鞍点，Hessian 矩阵的条件数与梯度下降法的关系

答：p56-p62

#### 10.KTT 方法与约束优化问题，活跃约束的定义

答：p60-p61

#### 11. 模型容量，表示容量，有效容量，最优容量概念

答：p70;p71;p72

Informally, a model’s capacity is its ability to fit a wide variety of functions. Models with low capacity may struggle to fit the training set. Models with high capacity can overfit by memorizing properties of the training set that do not serve them well on the test set. One way to control the capacity of a learning algorithm is by choosing its hypothesis space, the set of functions that the learning algorithm is allowed to select as being the solution. e.g. linear regression, cap(polynomial reg) > cap(linear).

The model specifies which family of functions the learning algorithm can choose from when varying the parameters in order to reduce a training objective. This is called the **representational capacity** of the model. In many cases, finding the best function within this family is a very difficult optimization problem. In practice, the learning algorithm does not actually find the best function, but merely one that significantly reduces the training error. These additional limitations, such as the imperfection of the optimization algorithm, mean that the learning algorithm’s effective capacity may be less than the representational capacity of the model family.

#### 12. 正则化中的权重衰减与加入先验知识在某些条件下的等价性

答：p73

#### 13. 高斯分布的广泛应用的缘由

答：
The Gaussian distribution is the most widely used distribution in statistics and machine learning.
There are several reasons for this. First, it has **two parameters which are easy to interpret**, and which
capture some of the most basic properties of a distribution, namely its mean and variance. Second,
the **central limit theorem** tells us that sums of independent random variables have an
approximately Gaussian distribution, making it a good choice for modeling residual errors or “noise”.
Third, the Gaussian distribution makes the **least number of assumptions (has maximum entropy)**,
subject to the constraint of having a specified mean and variance, as we show in Section 3.4.4; this
makes it a good default choice in many cases. Finally, it has a **simple mathematical form**, which
results in easy to implement, but often highly effective, methods 
from PML p58


#### 14. 最大似然估计中最小化 KL 散度与最小化分布之间的交叉熵的关系

答：p84

#### 15. 在线性回归问题，具有高斯先验权重的 MAP 贝叶斯推断与权重衰减的关系，与正则化的关系

答: p87

#### 16. 稀疏表示，低维表示，独立表示

答：p92

#### 17. 列举一些无法基于梯度 的优化来最小化的代价函数及其具有的特点

答：p97 维度灾难

#### 18. 在深度神经网络中，引入了隐藏层，放弃了训练问题的凸性，其意义何在

答：p119-122

#### 19. 函数在某个区间的饱和与平滑性对基于梯度的学习的影响

答：p98

#### 20. 梯度爆炸的一些解决办法

答：p185

One solution is to clip gradients (see section 10.11.1) while another is to scale the gradients heuristically

#### 21.MLP 的万能近似性质

答：p123

#### 22. 在前馈网络中，深度与宽度的关系及表示能力的差异

答：p125

#### 23. 为什么交叉熵损失可以提高具有 sigmoid 和 softmax 输出的模型的性能，而使用均方误差损失则会存在很多问题。分段线性隐藏层代替 sigmoid 的利弊

答：p140

#### 24. 表示学习的发展的初衷？并介绍其典型例子: 自编码器

答：p3
对于许多任务来说，我们很难知道应该提取哪些特征。例如，假设我们想 编写一个程序来检测照片中的车。我们知道，汽车有轮子，所以我们可能会想用车 轮的存在与否作为特征。不幸的是，我们难以准确地根据像素值来描述车轮看上去 像什么。虽然车轮具有简单的几何形状，但它的图像可能会因场景而异，如落在车 轮上的阴影、太阳照亮的车轮的金属零件、汽车的挡泥板或者遮挡的车轮一部分的 前景物体等等。
解决这个问题的途径之一是使用机器学习来发掘表示本身，而不仅仅把表示映 射到输出。这种方法我们称之为 表示学习(representation learning)。学习到的表 示往往比手动设计的表示表现得更好。并且它们只需最少的人工干预，就能让AI系 统迅速适应新的任务。表示学习算法只需几分钟就可以为简单的任务发现一个很好 的特征集，对于复杂任务则需要几小时到几个月。手动为一个复杂的任务设计特征 需要耗费大量的人工时间和精力;甚至需要花费整个社群研究人员几十年的时间。
表示学习算法的典型例子是 自编码器(autoencoder)。自编码器由一个 编码器 (encoder)函数和一个 解码器(decoder)函数组合而成。编码器函数将输入数据转 换为一种不同的表示，而解码器函数则将这个新的表示转换到原来的形式。我们期 望当输入数据经过编码器和解码器之后**尽可能多地保留信息**，同时希望新的表示有 各种好的特性，这也是自编码器的训练目标

#### 25. 在做正则化过程中，为什么只对权重做正则惩罚，而不对偏置做权重惩罚

答：p142

#### 26. 在深度学习神经网络中，所有的层中考虑使用相同的权重衰减的利弊

答：p142

#### 27. 正则化过程中，权重衰减与 Hessian 矩阵中特征值的一些关系，以及与梯度弥散，梯度爆炸的关系

答：p142-144

#### 28.L1／L2 正则化与高斯先验／对数先验的 MAP 贝叶斯推断的关系

答：p144

#### 29. 什么是欠约束，为什么大多数的正则化可以使欠约束下的欠定问题在迭代过程中收敛

答：p147 页底    `Chapter 7.3`

#### 30. 为什么考虑在模型训练时对输入 (隐藏单元／权重) 添加方差较小的噪声，与正则化的关系

答：p149-p150    `Chapter 7.5-7.6` 

#### 31. 共享参数的概念及在深度学习中的广泛影响

答：多任务学习 p151;p156     `Chapter 7.7; 7.9`

#### 32. Dropout 与 Bagging 集成方法的关系，以及 Dropout 带来的意义与其强大的原因

答：p159-p165     `Chapter 7.12` 

#### 33. 批量梯度下降法更新过程中，批量的大小与各种更新的稳定性关系

答：p170    `Chapter 8.1.3`

Minibatch sizes are generally driven by the following factors:

* Larger batches provide a more accurate estimate of the gradient, but with less than linear returns.
*  Multicore architectures are usually underutilized by extremely small batches. This motivates using some absolute minimum batch size, below which there is no reduction in the time to process a minibatch.

- If all examples in the batch are to be processed in parallel (as is typically the case), then the amount of **memory** scales with the batch size. For many hardware setups this is the limiting factor in batch size.

- Some kinds of hardware achieve better runtime with specific sizes of arrays. Especially when using GPUs, it is common for **power of 2** batch sizes to offer better runtime. Typical power of 2 batch sizes range from 32 to 256, with 16 sometimes being attempted for large models.

- **Small batches can offer a regularizing effect (Wilson and Martinez, 2003), perhaps due to the noise they add to the learning process.** Generalization error is often best for a batch size of 1. Training with such a small batch size might require a small learning rate to maintain stability due to the high

  variance in the estimate of the gradient. The total runtime can be very high due to the need to make more steps, both because of the reduced learning rate and because it takes more steps to observe the entire training set

Different kinds of algorithms use different kinds of information from the mini- batch in different ways. Some algorithms are more sensitive to sampling error than others, either because they use information that is difficult to estimate accurately

with few samples, or because they use information in ways that amplify sampling errors more. Methods that compute updates based only on the gradient g are usually relatively robust and can handle smaller batch sizes like 100. Second-order methods, which use also the Hessian matrix H and compute updates such as H−1g, typically require much larger batch sizes like 10,000. These large batch sizes are required to minimize fluctuations in the estimates of H−1g. Suppose that H is estimated perfectly but has a poor condition number. Multiplication by H or its inverse amplifies pre-existing errors, in this case, estimation errors in g. Very small changes in the estimate of g can thus cause large changes in the update H−1g, even if H were estimated perfectly. Of course, H will be estimated only approximately, so the update H−1g will contain even more error than we would

predict from applying a poorly conditioned operation to the estimate of g.

#### 34. 如何避免深度学习中的病态，鞍点，梯度爆炸，梯度弥散

答：p173-p178    `Chapter 8.2.1`

#### 35.SGD 以及学习率的选择方法，带动量的 SGD 对于 Hessian 矩阵病态条件及随机梯度方差的影响

答：p180；p181-p184    `Chapter 8.3`;

#### 36. 初始化权重过程中，权重大小在各种网络结构中的影响，以及一些初始化的方法；偏置的初始化

答：初始化权重：p184；  `Chapter 8.4`
偏置初始化：p186页底   `Chapter 8.4`

#### 37. 自适应学习率算法: AdaGrad，RMSProp，Adam 等算法的做法

答：AdaGrad:p187;  
RMSProp:p188; 
Adam:p189       `Chapter 8.5.1-3`

#### 38. 二阶近似方法: 牛顿法，共轭梯度，BFGS 等的做法

答：牛顿法：p190    `Chapter 8.6.1`; 
共轭梯度: p191-p193; `Chapter 8.6.2`
BFGS:p193-p194    `Chapter 8.6.3`

#### 39.Hessian 的标准化对于高阶优化算法的意义

答：p195    `Chapter 8.7.1`

#### 40. 卷积网络中的平移等变性的原因，常见的一些卷积形式

答：平移等变性：p205页底；    `Chapter 9.3`
常见的一些卷积形式：p211-p218    `Chapter 9.5`

#### 41.pooling 的做法的意义

答：p207; p210   `Chapter 9.3-4`

A pooling function replaces the output of the net at a certain location with a summary statistic of the nearby outputs.

1. In all cases, pooling helps to make the representation become approximately **invariant to small translations of the input**. Invariance to translation means that if we translate the input by a small amount, the values of most of the pooled outputs do not change. For example, when determining whether an image contains a face, we need not know the location of the eyes with pixel-perfect accuracy, we just need to know that there is an eye on the left side of the face and an eye on the right side of the face. In other contexts, it is more important to preserve the location of a feature. For example, if we want to find a corner defined by two edges meeting at a specific orientation, we need to preserve the location of the edges well enough to test whether they meet.

2. Because pooling summarizes the responses over a whole neighborhood, it is possible to use fewer pooling units than detector units, by reporting summary statistics for pooling regions spaced k pixels apart rather than 1 pixel apart. See figure 9.10 for an example. This improves the **computational efficiency** of the network because the next layer has roughly k times fewer inputs to process.
3. For many tasks, pooling is essential for **handling inputs of varying size**. For example, if we want to classify images of variable size, the input to the classification layer must have a fixed size. e.g. GAP, ROI pooling

#### 42. 循环神经网络常见的一些依赖循环关系，常见的一些输入输出，以及对应的应用场景

答：p230-p238    `Chapter 10.2`

#### 43. seq2seq，gru，lstm 等相关的原理

答：seq2seq:p240-p241;    `Chapter 10.4` 
gru:p250;    `Chapter 10.10.2`
lstm:p248    `Chapter 10.10.1`

#### 44. 采样在深度学习中的意义

答：p286 第一段    `Chapter 12.4.3` 

#### 45. 自编码器与线性因子模型，PCA，ICA 等的关系

答：线性因子模型可以扩展到自编码器和深度概率模型: p304-p305;  `Chapter 13.5`   
PCA:p298;    `Chapter 13.1` 
ICA:p298    `Chapter 13.2`

#### 46. 自编码器在深度学习中的意义，以及一些常见的变形与应用

答：意义: p306     `Chapter 14.1` 



常见变形: p306-p313    `Chapter 14.5` 
应用: p319   `Chapter 14.9` 

Autoencoders have been successfully applied to dimensionality reduction and information retrieval tasks.

#### 47. 受限玻尔兹曼机广泛应用的原因

答：p400: 想特别了解的人注意这句话：  See Mohamed et al. (2012b) for an analysis of reasons for the success of these models.    `Chapter 20.2` 

#### 48. 稳定分布与马尔可夫链

答：p362    `Chapter 17.3` 

#### 49.Gibbs 采样的原理

答：p365    `Chapter 17.4` 

#### 50. 配分函数通常难以计算的解决方案

答：p368    `Chapter 17.5.2` 
“遇到难以处理的无向图模型中的配分函数时， 蒙特卡洛方法仍是最主要工具”

#### 51. 几种参数估计的联系与区别: MLE／MAP／贝叶斯

答：P82/85/87    `Chapter 5.5` 

#### 52. 半监督的思想以及在深度学习中的应用

答：p329-p332    `Chapter 15.3` 

#### 53. 举例 CNN 中的 channel 在不同数据源中的含义

答：p219-220    `Chapter 9.7` 



|      | single channel                                               | multi-channel           |
| ---- | ------------------------------------------------------------ | ----------------------- |
| 1D   | Audio waveform                                               | Skeleton animation data |
| 2D   | Audio data that has been preprocessed with a Fourier transform | Color image data        |
| 3D   | Volumetric data: CT                                          | Color video data        |



#### 54. 深度学习在 NLP，语音，图像等领域的应用及常用的一些模型

答：p272-p293    `Chapter 12.1-5` 

#### 55.word2vec 与 glove 的比较

答：How is GloVe different from word2vec?；  

GloVe 以及 Word2vec 能称为 deep learning 么？这俩模型的层次其实很浅的；

http://t.cn/RvYslDf

这个问题没找到答案，我去找了 quora 和知乎上的相关问题以及 quora 一个回答提及的论文。   （若有人在书中找到，请批评指正）

#### 56. 注意力机制在深度学习的某些场景中为何会被大量使用，其几种不同的情形

答：p288    `Chapter 12.4.5.1` 

#### 57.wide&deep 模型中的 wide 和 deep 介绍

答：https://arxiv.org/pdf/1606.07792.pdf####  此问题答案未在书中找到，为此我去找了原论文，论文图 1 有详细的介绍。 （若有人在书中找到，请批评指正）  

#### 58. 核回归与 RBF 网络的关系

答：p89    `Chapter 5.7.2` 

#### 59.LSTM 结构推导，为什么比 RNN 好？

答：p248   `Chapter 10.10` 

#### 60. 过拟合在深度学习中的常见的一些解决方案或结构设计

答：p143-159；    `Chapter 7.1-12` 
包括：Parameter Norm Penalties(参数范数惩罚); Dataset Augmentation (数据集增强); Early Stopping(提前终止);   Parameter Tying and Parameter Sharing (参数绑定与参数共享); Bagging and Other Ensemble Methods(Bagging 和其他集成方法)；Dropout.          另外还有 Batch Normalization。

#### 61. 怎么理解贝叶斯模型的有效参数数据会根据数据集的规模自动调整

答：关于非参数模型：p72 ；    `Chapter 5.2` 
非参数模型不依赖于特定的概率模型，它的参数是无穷维的，数据集的规模的大小影响着模型使用更多或者更少的参数来对其进行建模。(并未在书中找到准确的答案，若有更好的回答，请联系我改正)

本答案是根据问题在_**Deep Learning**_上找到的答案；有些答案只是自己读书后在书上做的笔记的具体页面，毕竟原 po（http://t.cn/RObdPGk） 说还有另外一本书，所以该答案可能不是特别准确也不完善，答案也是给大家做个参考，若发现答案有问题，请联系我并指正，大家共同进步，谢谢！
