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

### 2. 看re-id跟mask, human parsing相结合的论文

- [CVPR2018: Human Semantic Parsing for Person Re-identification](https://github.com/wyg1997/PersonReID-paper/blob/master/documents/CVPR2018/Kalayeh_Human_Semantic_Parsing_CVPR_2018.pdf)   
>[解读](https://github.com/wyg1997/PersonReID-paper/blob/master/reading/CVPR2018/Kalayeh_Human_Semantic_Parsing_CVPR2018.md)

- [CVPR2018: MaskReID: A Mask Based Deep Ranking Neural Network for Person Re-identification](https://github.com/wyg1997/PersonReID-paper/blob/master/documents/CVPR2018/LiQi_MaskReID_A_Mask_Based_Deep_Ranking_Neural_Network_for_Reid_CVPR_2018.pdf)  
>[解读](https://github.com/wyg1997/PersonReID-paper/blob/master/reading/CVPR2018/Lei_MaskReID_CVPR2018.md)

- CVPR2018: Mask-guided Contrastive Attention Model for Person Re-Identification

### 3. 总结目前human parsing最好的模型

- CVPR2017: Look into Person: Self-supervised Structure-sensitive Learning and A New Benchmark for Human Parsing

- ICCV2015: Human Parsing with Contextualized Convolutional Neural Network

### 4. spatial attention的相关工作

- CVPR2018: Parameter-Free Spatial Attention Network for Person Re-Identification

### 5. human parsing模型训练

- 基于[CE2P](https://github.com/liutinglt/CE2P)  

- 参数设置：batch-size: 20, steps: 230000, input-size: (384, 128), random-scale: True, mirror: False  

- 分类信息重组织  

> 原分类：
>> 0.Background  
1.Hat  
2.Hair  
3.Glove  
4.Sunglasses  
5.UpperClothes  
6.Dress  
7.Coat  
8.Socks  
9.Pants  
10.Jumpsuits  
11.Scarf  
12.Skirt  
13.Face  
14.Left-arm  
15.Right-arm  
16.Left-leg  
17.Right-leg  
18.Left-shoe  
19.Right-shoe

> 新分类：
>> 0.Background  
1.[1, 2, 4, 13]  
2.[5, 6, 7, 9, 10, 11, 12]  
3.[14]  
4.[15]  
6.[16, 18]  
7.[17, 19]


- 资源占用统计  
Memory: 原项目中代码存在问题，程序开始占用10Gb，随后持续上升  
GPU Memory: 8.93Gb

- 训练结果数据  

> 384x128
>> Pixel Accuracy: 0.663313  
Mean accuracy: 0.314073  
Mean IU: 0.236828  
class_0: 0.7844  
class_1: 0.3227  
class_2: 0.3396  
class_3: 0.0990  
class_4: 0.1154  
class_5: 0.0567  
class_6: 0.0998

> 473x473
>> Pixel Accuracy: 0.834167  
Mean accuracy: 0.575554
Mean IU: 0.475463
class_0: 0.7844
class_1: 0.6652    
class_2: 0.6951  
class_3: 0.3543  
class_4: 0.4130  
class_5: 0.1832  
class_6: 0.2330


- 结果可视化

> LIP


> market1501

