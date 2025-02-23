# NewDINOR: Enhancing Rice Breeding via Semi-Supervised Panicle & Leaf Analysis
This GitHub repository contains the source code and test data for reproducing the experiments in the paper titled "Enhancing Rice Breeding Efficiency through Semi-Supervised Detection and Segmentation of Panicles and Leaves". The research was funded by the Biological Breeding-National Science and Technology Major Project (2023ZD04076). The paper is currently submitted to The Visual Computer. We commit to providing complete training datasets with corresponding annotations for non-commercial users after official publication, in order to promote agricultural development and facilitate further research in this field.
Funded by the Biological Breeding - National Science and Technology Major Project (No.2023ZD04076)

![image](https://github.com/xiaobeial/Semi-supervised-detection-and-segmentation-algorithm-for-efficient-rice-breeding/blob/main/img_demo_output/crop0_5x_20230607_c1_5x_DJI_20230607093538_0008_Z.jpg)
## Overview

In the field of rice breeding, enhancing crop yield and quality is paramount. This study focuses on critical factors that directly influence yield, specifically the number of rice panicles and leaf width. We hypothesize that an increase in panicle count and leaf width area positively correlates with photosynthetic efficiency, significantly impacting final crop yield. Guided by this rationale, we aim to evaluate and select rice varieties exhibiting desirable phenotypes through targeted detection techniques. We employ an enhanced DINO (self-DIstillation with NO labels) model for detecting and segmenting rice panicles and leaves. The upstream task of our model functions as an unsupervised general feature extractor, capable of learning rich visual features from a substantial dataset of unlabeled rice images. The downstream task comprises two branches: detecting the number of rice panicles and segmenting leaf areas. By synergizing these branches, we accurately assess the photosynthetic potential and reproductive capacity of rice plants. Experimental results demonstrate that our model achieves superior performance in both rice panicle detection and leaf area segmentation tasks, exhibiting higher accuracy and robustness. Additionally, our model operates stably under varying environmental conditions, showcasing significant application value for practical rice breeding. By precisely evaluating panicle count and leaf width, our model facilitates the selection of varieties with high photosynthetic efficiency and yield potential, contributing positively to sustainable agricultural development.

## Dataset

We have created a dataset focused on the recognition and segmentation of rice leaves and panicles, which includes over 10000 images. Our dataset, as shown in the figure, was captured by drones at three test sites for different rice varieties. The collection process involved shooting at different times of the day (such as morning, noon, and evening) and from various angles and backgrounds of the rice leaves and panicles to ensure the diversity and representativeness of the samples. The actual measured data includes the length and width (angle) of the flag leaf, panicle length, and number of spikelets per panicle. The dataset is divided with 80\% for training and 20\% for testing.


## Getting Started

* To begin, install our code dependencies using Conda. You may need to adjust the file based on your setup:
`<requirements.txt>` 
    * 
```
conda env create -f environment.yaml
conda activate ALIA
pip install -e .
```
    
In the above tables, the "Name" column contains a link to the config file, and the corresponding model checkpoints can be downloaded from the link in `config_pathmodel>` 

If your dataset files are not under this repo, you need to add or use Symbolic Link to link the dataset into this repo before the following command first.export. `DETECTRON2_DATASETS=/path/to/your/dataln -s>` 

## Evalaluate our pretrained models

* You can download our pretrained models and evaluate them with the following commands. for example, to reproduce our instance segmentation result, you can copy the config path from the table, download the pretrained checkpoint into , and run which can reproduce the model.

```
python train_net.py --eval-only --num-gpus 8 --config-file config_path MODEL.WEIGHTS /path/to/checkpoint_file
```
```
python train_net.py --eval-only --num-gpus 8 --config-file configs/coco/instance-segmentation/maskdino_R50_bs16_50ep_3s_dowsample1_2048.yaml MODEL.WEIGHTS /path/to/checkpoint_file
```
## About pre-training weights and data
* We provide our pre-training model and data, in the link below:
  https://pan.baidu.com/s/1RzHCeRquUYjjVn_ngwnxJg?pwd=5qkj   code：5qkj
## Citaton
If you find these models useful for your research, please cite the relevant papers
```
@article {
author = {Yihong Hu，, Ling Xiong，, Xingwang Li, Peiyi Yu,Changrong Ye, Gaofeng Jia, Bingchuan Tian},
title = {Enhancing Rice Breeding Efficiency through Semi-Supervised Detection and Segmentation of Panicles and Leaves},
elocation-id = { },
year = {2025},
doi = { },
publisher = {Springer Nature},
URL = { },
eprint = { },
journal = {The Visual Computer}
```
## 有问题反馈
If you have any questions during use, please feel free to give me feedback. You can use the following contact information to communicate with me

* email(202270294116@hunnu.edu.cn)
