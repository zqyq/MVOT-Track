# **Multi-View Optimal Transport for Multi-View Crowd Localization and Tracking**

**IJCV 2026** | [Paper (Springer)](https://link.springer.com/article/10.1007/s11263-026-03093-7).

**Kaiyi Zhang, Qi Zhang\*, Jixuan Chen, Antoni B. Chan, and Hui Huang**

**Previous conference paper — ECCV 2024:** **[Mahalanobis Distance-based Multi-view Optimal Transport for Multi-view Crowd Localization](https://www.ecva.net/papers/eccv_2024/papers_ECCV/html/471_ECCV_2024_paper.php)**  
[PDF](https://www.ecva.net/papers/eccv_2024/papers_ECCV/papers/00471.pdf) | [Code](https://github.com/zqyq/Mahalanobis-Distance-based-Multi-view-Optimal-Transport-for-Multi-view-Crowd-Localization)

![mvot_track](https://github.com/zqyq/MVOT-Track/blob/main/cross_view_vis.jpg)

## Abstract

Multi-view crowd localization and tracking aim to predict the ground-plane positions of all individuals in the scene and estimate their trajectories over time.
Existing multi-view localization methods typically rely on Gaussian-smoothed density map supervision, whose inherent ambiguity in crowded regions may blur local peaks and degrade localization accuracy. In this work, we introduce a multi-view optimal transport framework that directly supervises point-level predictions on the ground plane, thereby avoiding the limitations of density map regression.
Specifically, we propose a Mahalanobis distance-based multi-view optimal transport loss (M-MVOT), whose transport cost incorporates view ray direction and object-to-camera distance within a Mahalanobis formulation, with the direction guiding the ellipse orientation and the distance modulating the cost magnitude.
For multi-view tracking, we first extend the proposed localization framework in a tracking-by-detection manner (MVOT-TBD). To further improve performance, we introduce a tracking-specific optimal transport loss (MVOT-Track) that explicitly supervises inter-frame association. Extensive experiments demonstrate that the proposed optimal transport-based framework consistently outperforms density map-based localization and tracking on multiple multi-view crowd datasets.

## Overview

We release the PyTorch code for MVOT-Track, a multi-view crowd tracking method evaluated on Wildtrack and MultiviewX.
This IJCV 2026 work is an extended journal version of our ECCV 2024 paper, **[Mahalanobis Distance-based Multi-view Optimal Transport for Multi-view Crowd Localization](https://www.ecva.net/papers/eccv_2024/papers_ECCV/html/471_ECCV_2024_paper.php)**. The ECCV paper introduces M-MVOT for crowd localization; the IJCV extension further develops multi-view crowd tracking.

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
- einops
- motmetrics
- setuptools

## Training

For training, first pretrain the camera-view encoder and decoder using the camera-view loss. Once the pretraining is complete, load the pretrained camera-view model for full pipeline training, incorporating both the camera-view loss and ground-plane loss.

## Testing

Please update the checkpoint path in `main.py` and uncomment the test code.

## Pretrained models

You can download the checkpoints from [Baidu Netdisk](https://pan.baidu.com/s/1Tyxn7Q6KbgT7idYS_hsn4Q?pwd=89wq) (access code: `89wq`).

## Acknowledgement

This work was supported in part by National Key Research and Development Program of China (2024YFB3908500, 2024YFB3908504), National Natural Science Foundation of China (W2611096), Shenzhen Science and Technology Program (KQTD20210811090044003, KJZD20240903100022028), Scientific Foundation for Youth Scholars from Shenzhen University, City University of Hong Kong (Project No. 7030010), and Guangdong Provincial Key Laboratory of Visual Media and Multidimensional Intelligence (2026B1212010012).

## Citation

If you find this repository useful in your research, please cite the relevant paper(s). If your work builds on both our multi-view localization method and its tracking extension, please cite both papers.

**IJCV 2026 — Multi-View Optimal Transport for Multi-View Crowd Localization and Tracking**

```bibtex
@article{zhang2026multi,
  title={Multi-View Optimal Transport for Multi-View Crowd Localization and Tracking},
  author={Zhang, Kaiyi and Zhang, Qi and Chen, Jixuan and Chan, Antoni B. and Huang, Hui},
  journal={International Journal of Computer Vision},
  volume={134},
  number={11},
  pages={485},
  year={2026},
  publisher={Springer},
  doi={10.1007/s11263-026-03093-7}
}
```

**ECCV 2024 — Mahalanobis Distance-based Multi-view Optimal Transport for Multi-view Crowd Localization**

```bibtex
@inproceedings{MVOT24,
title={Mahalanobis Distance-based Multi-view Optimal Transport for Multi-view Crowd Localization},
author={Qi Zhang and Kaiyi Zhang and Antoni B. Chan and Hui Huang},
booktitle={European Conference on Computer Vision},
pages={19--36},
year={2024},
}
```
