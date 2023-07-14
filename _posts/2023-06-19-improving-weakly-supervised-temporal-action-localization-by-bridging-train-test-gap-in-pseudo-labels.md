---
layout: post
title: "Improving Weakly Supervised Temporal Action Localization by Bridging Train-Test Gap in Pseudo Labels"
tags: ["temporal action localization","weakly supervised temporal action localization"]
last_modified_at: 2023-06-19 21:27:13 +0900
---

動画単位に行動ラベルが付いたデータから行動区間予測を学習する弱教師あり時間的行動局在の手法．従来法では行動区間の疑似ラベルを生成する際にNMSで冗長な疑似ラベルを消去したのに対して，提案法では疑似ラベルをガウス分布でモデル化し複数の疑似ラベルを統合することで，より高品質な疑似ラベルを生成する．

## 基本情報

```bibtex
@InProceedings{Zhou_2023_CVPR,
    author    = {Zhou, Jingqiu and Huang, Linjiang and Wang, Liang and Liu, Si and Li, Hongsheng},
    title     = {Improving Weakly Supervised Temporal Action Localization by Bridging Train-Test Gap in Pseudo Labels},
    booktitle = {Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
    month     = {June},
    year      = {2023},
    pages     = {23003-23012}
}
```

### 論文リンク

[CVPR](https://openaccess.thecvf.com/content/CVPR2023/html/Zhou_Improving_Weakly_Supervised_Temporal_Action_Localization_by_Bridging_Train-Test_Gap_CVPR_2023_paper.html) / [arXiv](http://arxiv.org/abs/2304.07978)

### 著者・所属

Jingqiu Zhou, Linjiang Huang, Liang Wang, Si Liu, Hongsheng Li

## 新規性

## 手法

* Gaussian-weighted instance fusion
    * 疑似ラベル生成においてNMSを置き換える
    * 評価時のNMSもこれで置き換えると性能が上がる
* LinPro pseudo-label generation
* $\Delta$ pseudo label
    * 上記手法で生成した疑似ラベルそのものを使う代わりに，上記手法で生成した疑似ラベルの「変化」を疑似ラベルとして学習に使う
    * Confirmation biasへの対処？

## 結果

## 議論・コメント

* Ablation studyの結果（表5）を見ると，一番効いているのは評価時のNMSをGaussian-weighted instance fusionで置き換えることであって，疑似ラベルの工夫はあまり効いていないように見える（@IoU=0.3以外）

## 関連文献

