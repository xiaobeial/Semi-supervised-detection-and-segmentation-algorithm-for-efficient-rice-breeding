# Enhancing Rice Breeding Efficiency through Semi-Supervised Detection and Segmentation of Panicles and Leaves
![image](https://github.com/xiaobeial/Semi-supervised-detection-and-segmentation-algorithm-for-efficient-rice-breeding/img_demo_output/crop0_5x_20230607_c1_5x_DJI_20230607093538_0008_Z.jpg)
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
## 有问题反馈
在使用中有任何问题，欢迎反馈给我，可以用以下联系方式跟我交流

* 邮件(202270294116@hunnu.edu.cn)
