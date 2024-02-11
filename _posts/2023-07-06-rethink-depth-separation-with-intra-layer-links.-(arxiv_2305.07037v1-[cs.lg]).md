---
layout: post
title: "Rethink Depth Separation with Intra-layer Links. (arXiv:2305.07037v1 [cs.LG])"
tags: ["expressivity"]
last_modified_at: 2023-07-06 01:09:40 +0900
---

スキップ接続を持つ深層NNの表現力を，理論限界の導出，浅いNNでは表現できない関数の具体的構成，関数空間の解析を通じて調べた．スキップ接続があると単純な順伝播型NNよりも複雑な関数を表現できることを明らかにした．

## 基本情報

```bibtex
@misc{fan2023rethink,
      title={Rethink Depth Separation with Intra-layer Links}, 
      author={Feng-Lei Fan and Ze-Yu Li and Huan Xiong and Tieyong Zeng},
      year={2023},
      eprint={2305.07037},
      archivePrefix={arXiv},
      primaryClass={cs.LG}
}
```

### 論文リンク

* https://ift.tt/YjaLcCl

### 著者・所属

* Feng-Lei Fan, Ze-Yu Li, Huan Xiong, Tieyong Zeng (CUHK, HIT)

## 新規性

スキップ接続がある深層NNの表現力を理論的に調べた．

## 手法

## 結果

* 区分線形なスキップ接続を持つReLU DNNの線形な区間の数の上限を示した
* 順伝播型NNが持ちうるよりも多くの線形な区間を持つスキップ接続型DNNを構成した
* スキップ接続をもつNNの空間は順伝播型NNの空間よりも大きいことを示した
* 深さ分離理論（ある深いNNと同じ関数を浅いNNで表現するために必要な幅を与える理論）をスキップ接続がある場合に拡張した

## 議論・コメント

## 関連文献

* Telgarsky, 2015, 2016
* Arora et al., 2016
