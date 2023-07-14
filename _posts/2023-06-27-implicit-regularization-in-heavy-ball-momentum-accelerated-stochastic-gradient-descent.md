---
layout: post
title: "Implicit regularization in Heavy-ball momentum accelerated stochastic gradient descent"
tags: ["implicit regularization","optimizer"]
last_modified_at: 2023-06-27 03:02:27 +0900
---

モメンタム(S)GDは学習率が小さい場合に，元の損失関数とは異なる修正損失関数の勾配流で近似できることを理論的に証明した．修正損失関数と元の損失関数の差は暗黙的正則化と捉えられるが，これがモメンタム無しの(S)GDよりも大きいことからモメンタムには暗黙的正則化を強める働きがある．

## 基本情報

```bibtex
@inproceedings{
ghosh2023implicit,
title={Implicit regularization in Heavy-ball momentum accelerated stochastic gradient descent},
author={Avrajit Ghosh and He Lyu and Xitong Zhang and Rongrong Wang},
booktitle={The Eleventh International Conference on Learning Representations },
year={2023},
url={https://openreview.net/forum?id=ZzdBhtEH9yB}
}
```

### 論文リンク

[OpenReview](https://openreview.net/forum?id=ZzdBhtEH9yB)

### 著者・所属

[Avrajit Ghosh](https://openreview.net/profile?id=~Avrajit_Ghosh1), [He Lyu](https://openreview.net/profile?id=~He_Lyu1), [Xitong Zhang](https://openreview.net/profile?id=~Xitong_Zhang1), [Rongrong Wang](https://openreview.net/profile?id=~Rongrong_Wang1) (Michigan State University)

## 新規性

モメンタム(S)GDに対応する修正損失関数を導出し，このアルゴリズムの暗黙的正則化を明らかにした．

## 手法

## 結果

## 議論・コメント

## 関連文献

