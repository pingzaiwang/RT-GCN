# RT-GCN

This is the official PyTorch implementation of paper **Robust Tensor Graph Convolutional Networks via T-SVD based Graph Augmentation.** *Zhebin Wu, Lin Shu, Ziyue Xu, Yaomin Chang, Chuan Chen, Zibin Zheng.* KDD 2022. 

Our code is partly based on DeepRobust [(https://github.com/DSE-MSU/DeepRobust)](https://github.com/DSE-MSU/DeepRobust)

## Framework 
![Framework](https://user-images.githubusercontent.com/33544785/170969029-a84aabea-f00e-40c2-9dd6-70f835ec6f42.jpg)

## Abstract 
Graph Neural Networks (GNNs) have exhibited their powerful ability of tackling nontrivial problems on graphs. However, as an extension of deep learning models to graphs, GNNs are vulnerable to noise or adversarial attacks due to the underlying perturbations propagating in message passing scheme, which can affect the ultimate performances dramatically. Thus, it’s vital to study a robust GNN framework to defend against various perturbations. In this paper, we propose a Robust Tensor Graph Convolutional Network (RT-GCN) model to improve the robustness. On the one hand, we utilize multi-view augmentation to reduce the augmentation variance and organize them as a third-order tensor, followed by the truncated T-SVD to capture the low-rankness of the multi-view augmented graph, which improves the robustness from the perspective of graph preprocessing. On the other hand, to effectively capture the inter-view and intra-view information on the multiview augmented graph, we propose tensor GCN (TGCN) framework and analyze the mathematical relationship between TGCN and vanilla GCN, which improves the robustness from the perspective of model architecture. Extensive experimental results have verified the effectiveness of RT-GCN on various datasets, demonstrating the superiority to the state-of-the-art  models on diverse adversarial attacks for graphs.

## Requirements
See that in https://github.com/xuziyue1998/RT-GCN/blob/main/release/requirements.txt
```
argparse
torch_geometric
deeprobust
torch
scipy
pickle
numpy
sklearn
matplotlib
seaborn
```

## Demo running
After installation, you can run A demo by
```
python train.py --attack=meta --ptb_rate=0.25 --dataset=cora --svd_rank=10  --num_subadj=5 --ratio=0.9
```

## Reproduce the results
All the hyper-parameters settings are included in [`train.sh`](https://github.com/xuziyue1998/RT-GCN/blob/main/release/train.sh) bash file.
To reproduce the performance reported in the paper, you can run the bash file train.sh
```
bash train.sh
```

## Precautions
The nettack-attack data of cora_ml is generated by ourselves, and the specific data is in /data/cora_ml*

## Cite
@inproceedings{Wu2022robust,
  title={Robust Tensor Graph Convolutional Networks via T-SVD based Graph Augmentation},
  author={Wu, Zhebin and Shu, Lin and Xu, Ziyue and Chang, Yaomin and Chen, Chuan and Zheng, Zibin},
  booktitle={Proceedings of the 28th ACM SIGKDD conference on knowledge discovery \& data mining},
  year={2022}
}
