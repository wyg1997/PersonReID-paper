# Beyond Triplet Loss: A Deep Quadruplet Network for Person Re-identification

### 引言

首先看一下之前用到的Triplet Loss的方法：

- Triplet Loss(Embedding)  
取出3张图片，分别为`i`,`j`,`k`，它们三个的id分别为`s1`,`s1`,`s2`，即`i`和`j`是同一个id，然后我们拉近`i`和`j`的距离，推远`i`和`k`的距离。使用欧式距离计算loss。


- Triplet Loss(Learned Metric)  
这个基于上一种方法又做了一些改进，主要是针对最后对距离的度量方面。把之前使用欧式距离换成了经过训练的度量矩阵。个人感觉这样对某些关键特征处理把握的更好，不是像欧式距离一样每个特征的权重都一样。


- Quadruplet Loss  
这个就是本文提出的方法，在上面Triplet Loss中又引入了一张新的图片`l`，id为`s3`，即一个新的id。然后loss分成两部分：1.和之前的一样，选择`i` `j` `k`三张图，目的是拉近同类`i` `j`的距离，推远异类`i` `k`的距离。 2.这个是新加的一点，选择`i` `j` `k` `l`四张图，目的是拉近`i` `j`的距离而推远`k` `l`的距离，即使另两个异类同距离也要小幅度(使用较小的margin)的推远。

### 创新点

1. 使用Quadruplet Loss，采取强推动和弱推动策略。即第二个margin是第一个margin的1/2。
2. 采用Margin-based online hard negative mining(实在不知道怎么翻译)来选择margin。
3. 系统的分析了各loss的关系，从一个新的角度使用loss。
4. 在现有数据集上有优秀的表现。

### 个人理解

1. 本篇论文可以关注以下几点：(1)作者在提取出来的特征后加了一层SoftMax，以归一化特征，使margin的选择不至于没有范围 (2)求出每一个batch的正负样本间距的平均差来当作margin，避免了人工设置margin的不准确性 (3)使用了双margin实现强推动和弱推动策略。

2. 考虑到了另两个异类的间距，以此来设计新的loss函数，比较有创新。

3. 在特征层下加的SoftMax可否改为Sigmoid或Bn+ReLU来约束其范围。

4. 一个batch中，必须选择全部的样本进行训练吗，可否参考[TriHard Loss](https://blog.csdn.net/qq_21190081/article/details/78417215)的方法加速训练过程呢？
