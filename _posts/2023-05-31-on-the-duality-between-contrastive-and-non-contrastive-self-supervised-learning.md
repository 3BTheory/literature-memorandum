---
layout: post
title: "On the duality between contrastive and non-contrastive self-supervised learning"
tags: ["self-supervised learning","contrastive learning"]
last_modified_at: 2023-05-31 01:44:02 +0900
---

対照学習とある種の正則化に基づく非対照学習とを統一的に理解できることを示した．具体的には，両者の損失関数が埋め込みベクトルの正規化に依存する項を除いて一致することを証明．実験的にも，両者を十分にチューニングすれば両手法の性能差が無くなることを示した．

## 基本情報

```bibtex
@inproceedings{
garrido2023on,
title={On the duality between contrastive and non-contrastive self-supervised learning},
author={Quentin Garrido and Yubei Chen and Adrien Bardes and Laurent Najman and Yann LeCun},
booktitle={The Eleventh International Conference on Learning Representations },
year={2023},
url={https://openreview.net/forum?id=kDEL91Dufpa}
}
```

### 論文リンク

[OpenReview](https://openreview.net/forum?id=kDEL91Dufpa) / [Meta AI Blog](https://ai.facebook.com/research/publications/on-the-duality-between-contrastive-and-non-contrastive-self-supervised-learning/)

### 著者・所属

Quentin Garrido, Yubei Chen, Adrien Bardes, Laurent Najman, Yann LeCun (Meta AI)

## 新規性

従来の自己教師あり学習の研究が従来法との差分に着目し次々に新しい手法を開発してきたのに対して，本論文ではそれらを統一的に見る枠組みを探索する．その結果，対照学習（e.g. SimCLR）の損失関数と埋め込みベクトルの分散・共分散に対する正則化を用いた非対称学習（e.g. VICReg）の損失関数との間に成り立つ関係を導出．実験的にも，適切にSimCLRをチューニングすることでVICRegで主張されていたSimCLRとの性能差が埋まることを示した．

## 手法

理論的にはTheorem 3.3が中心．これは，対照学習の損失と非対称学習の損失との差が，埋め込みベクトルを並べた行列の行・列のノルムでかけることを示している．特に，行，列ともに正規化されている時，両損失関数は定数を除いて一致する．

また，VICRegとSimCLRを内挿するようにVICRegの亜種を2種類提案，これらを用いてVICRegとSimCLRの設計で何が性能に寄与しているのかを実験的に検証している．

## 結果

* VICReg，SimCLR，そしてそれらを内挿する2つの手法は射影器が同じならいずれもほぼ同精度であった
    * SimCLRは温度パラメータと学習率をよくチューニングする必要がある
* 射影器は大きい方が良い

## 議論・コメント

* SimCLRの"popular PyTorch implementation"には分散学習の実装にバグがあり，この点が性能に大きな影響を及ぼしているらしい
    * VICRegの実装ではこの点が解消されているとのこと

## 関連文献

* VICReg
* SimCLR
