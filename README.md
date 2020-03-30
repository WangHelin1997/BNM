# BNM
code release for ["Towards Discriminability and Diversity: Batch Nuclear-norm Maximization under Label Insufficient Situations"](https://arxiv.org/abs/2003.12237) ( CVPR2020 oral)

## One-sentence description
We prove in the paper that Batch Nuclear-norm Maximization (BNM) could ensure the prediction discriminability and diversity, which is an effective method under label insufficient situations.

## Application

### One line code under Pytorch and Tensorflow

Assume `X` is the prediction matrix. We could calculate BNM loss in both Pytorch and Tensorflow, as follows:
 
-Pytorch

1. Direct calculation (Since there remains direct approach for nuclear-norm)
```
L_BNM = -torch.norm(X,'nuc')
```
2. Calculation by SVD
```
L_BNM = -torch.sum(torch.svd(X, compute_uv=False)[1])
```
-Tensorflow
```
L_BNM = -tf.reduce_sum(tf.svd(X, compute_uv=False))
```

### Tasks
We apply BNM to domain adaptation (DA) in [DA](DA), unsupervised open domain recognition (UODR) in [UODR](UODR) and semi-supervised learning (SSL) in [SSL](SSL).

Training instructions for DA, UODR and SSL are in the `README.md` in [DA](DA), [UODR](UODR) and [SSL](SSL) respectively.

## Citation
If you use this code for your research, please consider citing:
```
@article{cui2020nnm,
	title={Towards Discriminability and Diversity: Batch Nuclear-norm Maximization under Label Insufficient Situations},
	author={Cui, Shuhao and Wang, Shuhui and Zhuo, Junbao and Li, Liang and Huang, Qingming and Tian Qi},
	journal={arXiv preprint arXiv:2003.12237},
	year={2020} 
}
```

<!-- @inproceedings{cui2020bnm,
  title={Towards Discriminability and Diversity: Batch Nuclear-norm Maximization under Label Insufficient Situations},
  author={Cui, Shuhao and Wang, Shuhui and Zhuo, Junbao and Li, Liang and Huang, Qingming and Tian Qi},
  booktitle={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition},
  year={2020}
} -->
## Contact
If you have any problem about our code, feel free to contact
- hassassin1621@gmail.com

or describe your problem in Issues.
