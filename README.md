# Learning Explicit Contact for Implicit Reconstruction of Hand-held Objects from Monocular Images

This repository is the official implementation of *Learning Explicit Contact for Implicit Reconstruction of Hand-held Objects from Monocular Images* (NeurIPS-Submission-7780). 


## Requirements

- Python 3.8
```
conda create --no-default-packages -n choi python=3.8
conda activate choi
```

- [PyTorch](https://www.pytorch.org) tested on version 1.8.0
```
conda install pytorch==1.8.0 torchvision==0.9.0 cudatoolkit=11.1.1 -c pytorch -c conda-forge
```

- other packages listed in `requirements.txt`
```
pip install -r requirements.txt
```


## Pre-trained Model and Dataset

- Unzip `weights.zip` and the pretrained model is placed in the `./weights/ho3d/checkpoints` directory

- Unzip `data.zip` and the processed data and corresponding SDF files are placed in the `./data` directory

- Download the [HO3D](https://github.com/shreyashampali/ho3d) dataset and put it into the `./data/ho3d` directory

- Download the [MANO](https://mano.is.tue.mpg.de/) model `MANO_RIGHT.pkl` and put it into the `./externals/mano` directory

## Evaluation
- To evaluate my model on HO3D, run:
```eval
python -m models.choi --config-file experiments/ho3d.yaml --ckpt weights/ho3d/checkpoints/ho3d_weight.ckpt
```
- The result file is generated in the `./output` directory


## Results
Our method achieves the following performance on HO3D test set:

| Method | F@5mm | F@10mm | Chamfer Distance (mm) |
| :----  | :---: | :----: | :-------------------: |
| Ours   | 0.393 | 0.633  |      0.646            |


## Acknowledgments
Part of the code is borrowed from the following projects, including [IHOI](https://github.com/JudyYe/ihoi), [Neural Body](https://github.com/zju3dv/neuralbody), and [MeshGraphormer](https://github.com/microsoft/MeshGraphormer). Many thanks to their contributions.

