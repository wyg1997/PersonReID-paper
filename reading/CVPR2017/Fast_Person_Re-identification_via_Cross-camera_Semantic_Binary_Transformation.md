# Fast Person Re-identification via Cross-camera Semantic Binary Transformation

### 引言

在Person ReID领域的研究有很多，但多数都是在研究怎么提升ReID正确率的，但是当数据集越来越大时，时间和空间(内存)上的消耗会剧增。

而本文提出的一种方案叫Cross-camera Semantic Binary Transformation(CSBT)，它的目标是把原始高维度的特征值转换为二元码特征。为了这个目标，CSBT首先使用了子空间映射来减少多摄像机的变化，通过最大化类内相似度和类间的差异。然后，通过无缝包含语义对间关系和局部的关联信息来产生一个二元码。最终，提出了一个同时用于学习子空间映射和离散交替优化二元码的联合的学习框架。

