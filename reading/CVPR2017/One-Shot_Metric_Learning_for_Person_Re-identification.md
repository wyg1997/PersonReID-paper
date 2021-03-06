# One-Shot Metric Learning for Person Re-identification

### 引言

Person reid是从网络中多个摄像机中找到同一个人，一个好的算法应该解决以下问题：1.颜色的变化 2.背景的变化 3.摄像机角度的不同 4.行人动作的不同。目前效果最好的方法还是有监督学习，但是想要训练一个好的模型需要大量带标注的数据否则很难应用到实际生活的摄像机网络中。

本文所提出的一种度量学习的方法可以运用到大规模摄像机网络中。我们把一对摄像机的图像取出纹理特征和颜色特征，对于纹理特征：我们只需用其灰度图像使用多分类来训练我们的卷积网络，而且不需要微调(finetune)。而相反的，使用彩色图训练的卷积网络在测试时仍需要用大量的数据进行微调。我们把图片的颜色特征单独考虑，我们每个摄像机仅需要一张图片样本(使用各个相机照下Macbeth ColorCheck调色版的图片，以对比出各个相机在颜色上的不同)，然后用马式距离得到一个度量标准来比较摄像机在颜色上的关系。

### 创新点

- 把reid任务分为纹理和颜色两部分，颜色部分只需要一次度量学习就可以得到两个相机的颜色关系。

- 纹理特征使用灰度图像来训练，这样做可以应用于更多的数据集中而不需要微调，这对于半监督和无监督学习的方法相比则非常有竞争力。

- 为了得到一对摄像机的颜色差异我们使用了调色版图像(人在图像中手举着调色版照出来的相处)。

- (不太明白，似乎是在解决背景的空间差异问题?)

### 个人总结

对于颜色比较部分的公式因为水平有限还不能理解，复现难度比较大，但是把不同摄像机的颜色差异作为一个度量因素可以借鉴。另外在纹理特征时使用灰度图像以方便直接(不需要finetune)扩展模型到更多的摄像机中的想法也可以保留。
