# TSC-PCAC

![GitHub stars](https://img.shields.io/github/stars/SYSU-Video/TSC-PCAC?style=social)
![Python](https://img.shields.io/badge/Python-3.8-blue)
![PyTorch](https://img.shields.io/badge/Framework-PyTorch-red)
[![Paper](https://img.shields.io/badge/Paper-TBC'24-b31b1b.svg)](https://ieeexplore.ieee.org/document/10693649)
![License](https://img.shields.io/github/license/SYSU-Video/TSC-PCAC)
![Last commit](https://img.shields.io/github/last-commit/SYSU-Video/TSC-PCAC)

TSC-PCAC: Voxel Transformer and Sparse Convolution Based Point Cloud Attribute Compression for 3D Broadcasting [[paper]](https://ieeexplore.ieee.org/document/10693649)
[Zixi Guo](https://ieeexplore.ieee.org/author/37086146082), [Yun Zhang](https://codec.siat.ac.cn/yunzhang/), [Linwei Zhu](https://zhulinweicityu.github.io/), [Hanli Wang](https://ieeexplore.ieee.org/author/37292564900), [Gangyi Jiang](https://ieeexplore.ieee.org/author/37289535900)
*IEEE Transactions on Broadcasting (TBC), 2024*

## Abstract
Point cloud has been the mainstream representation for advanced 3D applications, such as virtual reality and augmented reality. However, the massive data amounts of point clouds is one of the most challenging issues for transmission and storage. In this paper, we propose an end-to-end voxel Transformer and Sparse Convolution based Point Cloud Attribute Compression (TSC-PCAC) for 3D broadcasting. Firstly, we present a framework of the TSC-PCAC, which includes Transformer and Sparse Convolutional Module (TSCM) based variational autoencoder and channel context module. Secondly, we propose a two-stage TSCM, where the first stage focuses on modeling local dependencies and feature representations of the point clouds, and the second stage captures global features through spatial and channel pooling encompassing larger receptive fields. This module effectively extracts global and local inter-point relevance to reduce informational redundancy. Thirdly, we design a TSCM based channel context module to exploit inter-channel correlations, which improves the predicted probability distribution of quantized latent representations and thus reduces the bitrate. Experimental results indicate that the proposed TSC-PCAC method achieves an average of 38.53%, 21.30%, and 11.19% bitrate reductions on datasets 8iVFB, Owlii, 8iVSLF, Volograms, and MVUB compared to the Sparse-PCAC, NF-PCAC, and G-PCC v23 methods, respectively. The encoding/decoding time costs are reduced 97.68%/98.78% on average compared to the Sparse-PCAC. The source code and the trained TSC-PCAC models are available at https://github.com/igizuxo/TSC-PCAC.

## Requirments

- CUDA=11.1

- pytorch=1.9.0

- python=3.8

- minkowskiengine=0.5.4

- torchac=0.9.3

- preweight models: <https://drive.google.com/file/d/1wzfq6fwUkKoe46oxzCYmRrUDPgLAO-Zd/view?usp=drive_link>

## Test

python codec.py --dataset_path test_rootdir

## Train

python train.py --batch_size 8 --learning 1e-4 --lamb 16000 --dataset_path train_rootdir --val_path val_rootdir
