---
layout: post
title: "Segment Anything is A Good Pseudo-label Generator for Weakly Supervised Semantic Segmentation"
tags: ["foundation models","image","semantic segmentation"]
last_modified_at: 2023-06-01 17:40:32 +0900
---

弱教師あり学習領域分割向けにSAMで疑似ラベルを生成する．同時期に同じテーマに取り組んだChen, et al.は画像単位のクラスラベルに焦点を当てていたのに対し，他の弱い教師（点，スクリブル，バウンディングボックス）についても検討している．

## 基本情報

```bibtex
@misc{jiang2023segment,
      title={Segment Anything is A Good Pseudo-label Generator for Weakly Supervised Semantic Segmentation}, 
      author={Peng-Tao Jiang and Yuqi Yang},
      year={2023},
      eprint={2305.01275},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```

### 論文リンク

[arXiv](https://arxiv.org/abs/2305.01275)

### 著者・所属

Xueyan Zou, Jianwei Yang, Hao Zhang, Feng Li, Linjie Li, Jianfeng Gao, Yong Jae Lee (UW–Madison, Microsoft, HKUST)

## 新規性

SAMを用いることで領域分割の弱教師あり学習向けに高品質な疑似ラベルを生成する方法を提案．弱教師として画像レベルの物体クラス，点，スクリブル，バウンディングボックスを検討した点が同時期の他の論文（Chen, et al.）との差異．

## 手法

* 画像レベルのラベルについては2種類の方法を検討
    * 画像分類を学習した分類器からCAMを生成し，CAMから点をサンプリングしてSAMへのプロンプトとする
    * まず全体にSAMでマスクを生成し，生成した各領域をBLIP-2で分類する
* 点，スクリブルは，その点やスクリブルからサンプリングした点をプロンプトとしてSAMに入力する
* バウンディングボックスもプロンプトとしてSAMに入力する

## 結果

## 議論・コメント

* 同時期にSAMを弱教師あり領域分割に適用したChen, et al.（[備忘録](https://3btheory.github.io/literature-memorandum/2023/06/01/segment-anything-model-(sam)-enhanced-pseudo-labels-for-weakly-supervised-semantic-segmentation.html)）
* スクリブルからサンプルした点を使う場合，全部の点を使うより20%サンプルした方が良い，反復的に与えるのが良い，などあるらしい

## 関連文献

