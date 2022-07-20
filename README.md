# DFRF #
The pytorch implementation for our ECCV2022 paper "Learning Dynamic Facial Radiance Fields for Few-Shot Talking Head Synthesis".

## Requirements
- Python 3.8.11
- Pytorch 1.9.0
- Pytorch3d 0.5.0
- torchvision 0.10.0

For more details, please refer to the `requirements.txt`. We conduct the experiments with a 24G RTX3090.

- Download 3DMM model from [Basel Face Model 2009](https://faces.dmi.unibas.ch/bfm/main.php?nav=1-1-0&id=details):

    ```
    cp 01_MorphableModel.mat data_util/face_tracking/3DMM/
    cd data_util/face_tracking
    python convert_BFM.py
    ```
## Dataset
Put the video `${id}.mp4` to `dataset/vids/`, then run the following command for data preprocess.  
```
sh process_data.sh ${id}
```
## Training
```
sh run.sh ${id}
```

## Test
Change the configurations in the `rendering.sh`, including the `iters, names, datasets, near and far`.
```
sh rendering.sh
```

## Acknowledgement 
This code is built upon the publicly available code [AD-NeRF](https://github.com/YudongGuo/AD-NeRF) and [GRF](https://github.com/alextrevithick/GRF). Thanks the authors of AD-NeRF and GRF for making their excellent work and codes publicly available. 

## Citation ##
Please cite the following paper if you use this repository in your reseach.

```
@inproceedings{shen2022dfrf,
   author={Shen, Shuai and Li, Wanhua and Zhu, Zheng and Duan, Yueqi and Zhou, Jie and Lu, Jiwen},
   title={Learning Dynamic Facial Radiance Fields for Few-Shot Talking Head Synthesis},
   booktitle={European conference on computer vision},
   year={2022}
}
```