---
layout: post
title: "Loss Landscapes are All You Need: Neural Network Generalization Can Be Explained Without the Implicit Bias of Gradient Descent"
tags: ["implicit regularization","loss landscape"]
last_modified_at: 2023-05-17 02:36:46 +0900
---

深層学習の汎化性を説明する「暗黙的正則化」の起源に関する論文．従来は確率的勾配降下法などの最適化アルゴリズムがその起源であると考えられてきたが，本論文ではアルゴリズムに依らず損失関数の形状に起因する効果であると主張する．

## 基本情報

```bibtex
@inproceedings{
chiang2023loss,
title={Loss Landscapes are All You Need: Neural Network Generalization Can Be Explained Without the Implicit Bias of Gradient Descent},
author={Ping-yeh Chiang and Renkun Ni and David Yu Miller and Arpit Bansal and Jonas Geiping and Micah Goldblum and Tom Goldstein},
booktitle={The Eleventh International Conference on Learning Representations },
year={2023},
url={https://openreview.net/forum?id=QC10RmRbZy9}
}
```

### 論文リンク

[OpenReview](https://openreview.net/forum?id=QC10RmRbZy9)

### 著者・所属

Ping-yeh Chiang, Renkun Ni, David Yu Miller, Arpit Bansal, Jonas Geiping, Micah Goldblum, Tom Goldstein (UMD, NYU, MPI SWS)

## 新規性

深層学習における暗黙的正則化の起源は最適化アルゴリズムではなく損失関数の形状にあることを実験的に検証した．特に，汎化する局所解の体積は汎化しない局所解の体積よりも大きいとする「体積仮説」を検証し肯定的な結論を得た．

## 手法

* *Guess & Check* (G&C)
    * 要するにランダムサンプリング，パラメータ空間に定めた超立方体から一様にサンプリングする
    * 訓練精度が１００%になるまでランダムにパラメータを引き続ける

G&Cは一様サンプリングなので，あるパラメータ領域が選択される確率はその領域の体積に比例する．したがって，G&Cで得られたパラメータが（高い確率で）汎化することは体積仮説が成り立っていることを示唆する．

## 結果

G&CはSGDと同程度の検証精度を達成する．

## 議論・コメント

* G&Cは損失関数の形状やその他の深層学習の性質を調べるのに面白いツールだと思った
* G&CとSGDを比較するとき，それぞれのハイパーパラメータをどう設定するのが適切なのか？
    * この論文からは読み取れなかった
* 比較する評価尺度も基本的には精度や損失しか見ていないので，もう少し詳細な分析がほしくはある

## 関連文献

