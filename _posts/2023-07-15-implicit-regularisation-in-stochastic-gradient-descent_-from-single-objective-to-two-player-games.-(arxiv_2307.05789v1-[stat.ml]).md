---
layout: post
title: "Implicit regularisation in stochastic gradient descent: from single-objective to two-player games. (arXiv:2307.05789v1 [stat.ML])"
tags: ["implicit regularization","deep learning dynamics"]
last_modified_at: 2023-07-15 01:15:38 +0900
---

SGDのステップ幅（学習率）が有限であることの暗黙的な正則化効果について議論する．この筋の研究の中で，後方誤差解析によって勾配降下法を修正勾配流で近似するものは損失関数がステップごとに変わらないことを仮定しており，SGDには適用できなかった．本論文は，後方誤差解析を複数ステップのSGDに拡張した．その結果，$O(h^3)$ までの誤差で，従来から知られていた暗黙的勾配正則化項に加え，異なる時刻の勾配の内積を最大化するような項（gradient alignment）を持つ修正勾配流が得られた．また，この結果をGANなどの2プレイヤーゲームに拡張した．

## 基本情報

```bibtex
@misc{rosca2023implicit,
      title={Implicit regularisation in stochastic gradient descent: from single-objective to two-player games}, 
      author={Mihaela Rosca and Marc Peter Deisenroth},
      year={2023},
      eprint={2307.05789},
      archivePrefix={arXiv},
      primaryClass={stat.ML}
}
```

### 論文リンク

[arXiv](https://ift.tt/WlehEgk)

### 著者・所属

* Mihaela Rosca, Marc Peter Deisenroth

## 新規性

後方誤差解析によって多ステップのSGDの暗黙的正則化を計算した点．

## 手法

## 結果

## 議論・コメント

## 関連文献
