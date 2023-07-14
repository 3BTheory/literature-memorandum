---
layout: post
title: "Trajectory Alignment: Understanding the Edge of Stability Phenomenon via Bifurcation Theory. (arXiv:2307.04204v1 [cs.LG])"
tags: ["implicit regularization","deep learning dynamics","edge of stability"]
last_modified_at: 2023-07-12 14:35:22 +0900
---

最適化ダイナミクスにおけるedge of stability現象の理論解析．著者らが正準再パラメータ化と呼ぶ「良い」座標で見ると，EoS領域での最適化の軌跡が力学系における分岐図に沿って動くtrajectory alignmentを示した．

## 基本情報

```bibtex
@misc{song2023trajectory,
      title={Trajectory Alignment: Understanding the Edge of Stability Phenomenon via Bifurcation Theory}, 
      author={Minhak Song and Chulhee Yun},
      year={2023},
      eprint={2307.04204},
      archivePrefix={arXiv},
      primaryClass={cs.LG}
}
```

### 論文リンク

[arXiv](https://arxiv.org/abs/2307.04204)

### 著者・所属

* Minhak Song, Chulhee Yun (KAIST)

## 新規性

* 正準再パラメータ化の導入
    * EoS領域での運動を見るのに適した座標
* 2層線形全結合NN，学習データが1点で損失関数がリプシッツ性などの条件を満たすときにtrajectory alignmentが起こることを理論的に証明
* 単一ニューロンの2層線形NN，学習データが1点で損失関数が2乗誤差の時にtrajectory alignmentが起こることを理論的に証明

## 手法

## 結果

## 議論・コメント

* データ点が複数ある時には，ここで導入されたcanonical reparameterizationが良い座標ではなさそう

## 関連文献
