---
layout: post
title: "Compositional Generalization from First Principles. (arXiv:2307.05596v1 [cs.LG])"
tags: ["feature learning","object-centric learning"]
last_modified_at: 2023-07-14 19:01:32 +0900
---

人物や物体で構成されたシーン画像のように，多くのデータは構成要素の組合せからなる．構成的汎化は，訓練データには含まれない組合せに汎化する能力である（構成要素は訓練時と評価時で変わらない）．本論文ではこのようなデータが，構成要素を生成する関数と，生成された構成要素を組合わせる関数との合成関数として表現できると仮定し（構成的表現），このような関数を学習できるためにデータ分布が満たすべき条件を導出．大雑把には訓練データが全ての構成要素をカバーしていることと，構成要素の生成関数を学習するのに十分大きな台を持っていれば良い．

構成的データの機械学習という意味では，生成タスクの方が識別タスクよりも簡単なのではないか，とこれを見て思った．論文で論じられている通り，構成要素を合成する部分は比較的単純な関数で表現できることもある．識別タスクの時は？

## 基本情報

```bibtex
@misc{wiedemer2023compositional,
      title={Compositional Generalization from First Principles}, 
      author={Thaddäus Wiedemer and Prasanna Mayilvahanan and Matthias Bethge and Wieland Brendel},
      year={2023},
      eprint={2307.05596},
      archivePrefix={arXiv},
      primaryClass={cs.LG}
}
```

### 論文リンク

[arXiv](https://ift.tt/GWCyYtc)

### 著者・所属

* Thaddäus Wiedemer, Prasanna Mayilvahanan, Matthias Bethge, Wieland Brendel

## 新規性

## 手法

## 結果

## 議論・コメント


## 関連文献
