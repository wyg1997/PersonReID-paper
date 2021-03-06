# MaskReID: A Mask Based Deep Ranking Neural Network for Person Re-identification

### 引言

本文从ReID的背景复杂性上来考虑提出的一种叫MaskReID的网络，即想办法使用抽离出前景图片，然后把抽离出来的前景图片和原图(目的是减小错误抽离前景图的影响)一起使用全卷积网络进行特征抽取，一共抽取出3层特征，又使用一种新提出的loss函数(下文细讲)来训练模型。

### 创新点

1. 使用基于图片主义分割的掩码图片(masked image)来补充输入，以解决ReID中背景杂乱的问题。

2. 使用一种新的深度学习框架，可以输入掩码图片以及原图。另外，分级地抽取特征。  
![network](https://github.com/wyg1997/PersonReID-paper/blob/master/reading/CVPR2018/image/Lei_MaskReID_0.png)

3. 提出一种新的loss函数，对比了之前的triplet loss和N-pair loss，文中说triplet loss只是拉近了**一个正样本**和推远了**一个负样本**，而N-pair loss拉近了**一个正样本**和推远了**n个负样本**，而论文的loss就比较厉害了，它可以拉近**n个正样本**和推远**n个负样本**。

### 个人理解

1. 使用掩码图片的思路容易想到，事实证明效果也还不错。

2. 论文提出的loss函数比较有价值，在文中和其它的loss函数比较上可以看出有很大的优势。确实在Person ReID上面，训练时能考虑到多种正样本的多种负样本的话，最后训练的结果要好不少。

3. 文末作者提出要在人体的各个部分上进行解析(human parsing)将成为下一阶段的研究目标。
