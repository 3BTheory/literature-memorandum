---
layout: post
title: "Combining Explicit and Implicit Regularization for Efficient Learning in Deep Networks. (arXiv:2306.00342v1 [cs.LG])"
tags: ["implicit regularization","deep learning dynamics","optimizer"]
last_modified_at: 2023-06-05 23:09:16 +0900
---

深層線形モデルによる行列補完の学習において，モデルの「深さ」が持つご利益を明示的な正則化で代替可能であることを示した．この効果はAdam系の最適化アルゴリズムを用いた時のみ現れる点で，明示的正則化とアルゴリズムの暗黙的との相互作用の起結であると言える．

## 基本情報

```bibtex
@inproceedings{NEURIPS2022_1419d855,
 author = {Zhao, Dan},
 booktitle = {Advances in Neural Information Processing Systems},
 editor = {S. Koyejo and S. Mohamed and A. Agarwal and D. Belgrave and K. Cho and A. Oh},
 pages = {3024--3038},
 publisher = {Curran Associates, Inc.},
 title = {Combining Explicit and Implicit Regularization for Efficient Learning in Deep Networks},
 url = {https://proceedings.neurips.cc/paper_files/paper/2022/file/1419d8554191a65ea4f2d8e1057973e4-Paper-Conference.pdf},
 volume = {35},
 year = {2022}
}
```

### 論文リンク

[NeurIPS](https://papers.nips.cc/paper_files/paper/2022/hash/1419d8554191a65ea4f2d8e1057973e4-Abstract-Conference.html) / [OpenReview](https://openreview.net/forum?id=sADLRl2STMe) / [arXiv](https://arxiv.org/abs/2306.00342)

### 著者・所属

* Dan Zhao (NYU)

## 新規性

深層線形モデルによる行列補完の学習において，トレースノルムをフロベニウスノルムで正規化した正則化項の効果を明らかにした．具体的には，この正則化によりモデルの「深さ」が持つご利益が1層のモデルでも得られることを実験的に示した．この効果はAdam系の最適化アルゴリズムを用いた時のみ現れる点で，明示的正則化とアルゴリズムの暗黙的との相互作用の起結であると言える．

## 手法

## 結果

## 議論・コメント

* Adam系最適化アルゴリズムに関する暗黙的正則化の研究は珍しい気がする

## 関連文献
