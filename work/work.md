# Person-ReID

### 1. 调研目前re-id网络识别错误的原因，思考如何解决pose和occlusion的问题

1. 遮挡：  
![](visualize/00002132_0008_00000000.jpg)  
![](visualize/00001804_0001_00000000.jpg)  
![](visualize/00001699_0001_00000000.jpg)  
![](visualize/00001683_0001_00000000.jpg)  
![](visualize/00000075_0002_00000000.jpg)  
![](visualize/00000803_0001_00000000.jpg)  

2. 多目标(效果比较差)：  
![](visualize/00000786_0000_00000000.jpg)  
![](visualize/00000817_0000_00000000.jpg)  
![](visualize/00000821_0000_00000000.jpg)  
![](visualize/00000828_0000_00000000.jpg)  
![](visualize/00001478_0001_00000000.jpg)

3. 低分辨率(有影响，但不是非常严重)：  
![](visualize/00000352_0001_00000000.jpg)  
![](visualize/00000448_0006_00000000.jpg)  
![](visualize/00000537_0001_00000000.jpg)  
![](visualize/00001505_0004_00000000.jpg)  

4. 弱光线(黑衣服影响更大)：  
![](visualize/00000765_0001_00000000.jpg)  
![](visualize/00001319_0000_00000000.jpg)  
![](visualize/00001322_0000_00000000.jpg)  
![](visualize/00001363_0001_00000000.jpg)

### 2. 看re-id跟make, human parsing相结合的论文

- [CVPR2018: Human Semantic Parsing for Person Re-identification](https://github.com/wyg1997/PersonReID-paper/blob/master/documents/CVPR2018/Kalayeh_Human_Semantic_Parsing_CVPR_2018.pdf)  
>[解读](https://github.com/wyg1997/PersonReID-paper/blob/master/reading/CVPR2018/Kalayeh_Human_Semantic_Parsing_CVPR2018.md)

- CVPR2018: MaskReID: A Mask Based Deep Ranking Neural Network for Person Re-identification

- CVPR2018: Mask-guided Contrastive Attention Model for Person Re-Identification

### 3. 总结目前human parsing最好的模型

- CVPR2017: Look into Person: Self-supervised Structure-sensitive Learning and A New Benchmark for Human Parsing

- ICCV2015: Human Parsing with Contextualized Convolutional Neural Network

### 4. spatial attention的相关工作
