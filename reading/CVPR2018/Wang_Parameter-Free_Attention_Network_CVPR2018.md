# Parameter-Free Spatial Attention Network for Person Re-Identification

### 创新点

1. 用一个无参的空间注意(Spatial Attention)层加在了GAP(Global Average Pooling)层之前，以提高性能。

2. 在reid工作中引入了一个新的层(Spatial Attention)，达到了SOA(state-of-the-art)水平。

3. 比较了有无空间注意层的效果。

### 工作原理

重点就是在这个空间注意层上，流程很简单，流程图为:  
![](./image/Wang_Spatial_Attention_Network_0.png)

就是把提取出来的特征先按C通道相加，flatten后取一个SoftMax，然后再reshape回原来的尺寸。最后把得到的这个H\*W的权重和原特征叠加，得到最后的特征。

### 个人理解

1. 实现思路比较简单，但是可能是一种特征处理较高效的方法。
