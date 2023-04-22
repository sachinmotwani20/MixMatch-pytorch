# MixMatch
This is an unofficial PyTorch implementation of [MixMatch: A Holistic Approach to Semi-Supervised Learning](https://arxiv.org/abs/1905.02249). 
The official Tensorflow implementation is [here](https://github.com/google-research/mixmatch).

Now only experiments on CIFAR-10 are available.

This repository carefully implemented important details of the official implementation to reproduce the results.


## Requirements
- python 3.10.11
- pytorch 2.0.0
- pytorch-cuda 11.7
- torchvision 0.15.0 
- tensorboardX
- progress
- matplotlib
- numpy

## Usage

### Train
Train the model by 250 labeled data of CIFAR-10 dataset:

```
python train.py --gpu <gpu_id> --n-labeled 250 --out cifar10@250
```

Train the model by 4000 labeled data of CIFAR-10 dataset:

```
python train.py --gpu <gpu_id> --n-labeled 4000 --out cifar10@4000
```

### Running using nohup [It may run overnight]
```
nohup python train.py --gpu <gpu_id> --n-labeled 1000 --out cifar10@1000 1>cifar10@1000.stdout 2>cifar10@1000.stderr &
```

## Results (Accuracy)
| #Labels | 250 | 500 | 1000 | 2000| 4000 |
|:---|:---:|:---:|:---:|:---:|:---:|
|Paper | 88.92 ± 0.87 | 90.35 ± 0.94 | 92.25 ± 0.32| 92.97 ± 0.15 |93.76 ± 0.06|
|This code (mean) | 88.2325 | 88.96 | 90.52 | 92.23 | 93.562 |
|This code (best) | 89.28 | 88.96 | 90.52 | 92.23 | 94.2 |

## References
```
@article{berthelot2019mixmatch,
  title={MixMatch: A Holistic Approach to Semi-Supervised Learning},
  author={Berthelot, David and Carlini, Nicholas and Goodfellow, Ian and Papernot, Nicolas and Oliver, Avital and Raffel, Colin},
  journal={arXiv preprint arXiv:1905.02249},
  year={2019}
}
```
