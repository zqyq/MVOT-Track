# Multi-view Optimal Transport for Multi-view Crowd Localization and Tracking
Kaiyi Zhang, Qi Zhang*, Antoni B. Chan and Hui Huang, Multi-view Optimal Transport for Multi-view Crowd Localization and Tracking, IJCV 2026

![mvot_track](https://github.com/zqyq/MVOT-Track/blob/main/cross_view_vis.jpg)

## Abstract
Multi-view crowd localization and tracking aim to predict the ground-plane positions of all individuals in the scene and estimate their trajectories over time. 
Existing multi-view localization methods typically rely on Gaussian-smoothed density map supervision, whose inherent ambiguity in crowded regions may blur local peaks and degrade localization accuracy. In this work, we introduce a multi-view optimal transport framework that directly supervises point-level predictions on the ground plane, thereby avoiding the limitations of density map regression. 
Specifically, we propose a Mahalanobis distance-based multi-view optimal transport loss (M-MVOT), whose transport cost incorporates view ray direction and object-to-camera distance within a Mahalanobis formulation, with the direction guiding the ellipse orientation and the distance modulating the cost magnitude.
For multi-view tracking, we first extend the proposed localization framework in a tracking-by-detection manner (MVOT-TBD). To further improve performance, we introduce a tracking-specific optimal transport loss (MVOT-Track) that explicitly supervises inter-frame association. Extensive experiments demonstrate that the proposed optimal transport-based framework consistently outperforms density map-based localization and tracking on multiple multi-view crowd datasets.


## Overview
We release the PyTorch code for the MVOT_track, a multi-view crowd tracking method with promising performance on Wildtrack and MultiviewX datasets. 

## Dependencies
- python
- pytorch & torchvision
- numpy
- matplotlib
- pillow
- opencv-python
- kornia
- tqdm
- argparse
- shutil


## Training
For training, first pretrain the camera-view encoder and decoder using the camera-view loss. Once the pretraining is complete, load the pretrained camera-view model for full pipeline training, incorporating both the camera-view loss and ground-plane loss.

## Testing
Please update the checkpoint path in main.py and uncomment the test code.

## Pretrained models
You can download the checkpoints at this [link](https://pan.baidu.com/s/1gjH2CpdSkD7apaxx1fGxjQ?pwd=1ia3) code: 1ia3 or 2D pretrained [ckpt](https://pan.baidu.com/s/1X080MEK-2jrx3Lfbba5IBw?pwd=d1rk) code: d1rk

## Acknowledgement
This work was supported in part by National Key Research and Development Program of China (2024YFB3908500, 2024YFB3908504), National Natural Science Foundation of China (W2611096), Shenzhen Science and Technology Program (KQTD20210811090044003, KJZD20240903100022028), Scientific Foundation for Youth Scholars from Shenzhen University, City University of Hong Kong (Project No. 7030010), and Guangdong Provincial Key Laboratory of Visual Media and Multidimensional Intelligence (2026B1212010012).

