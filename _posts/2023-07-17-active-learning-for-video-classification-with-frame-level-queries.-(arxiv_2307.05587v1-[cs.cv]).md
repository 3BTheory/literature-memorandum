---
layout: post
title: "Active Learning for Video Classification with Frame Level Queries. (arXiv:2307.05587v1 [cs.CV])"
tags: ["video","active learning"]
last_modified_at: 2023-07-17 11:48:31 +0900
---

動画分類向け能動学習の論文．ラベル付けするべき動画を選択するだけでなく，典型的な少数のフレームを選択し提示することでラベル付け作業者の負荷を軽減する．

## 基本情報

```bibtex
@misc{goswami2023active,
      title={Active Learning for Video Classification with Frame Level Queries}, 
      author={Debanjan Goswami and Shayok Chakraborty},
      year={2023},
      eprint={2307.05587},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```

### 論文リンク

[arXiv](https://ift.tt/eiSn34B)

### 著者・所属

* Debanjan Goswami, Shayok Chakraborty

## 新規性

## 手法

* Informativenessとdiversityの最適化による動画を選択するactive video sampling
* 全フレームで計算した損失を再現できるようにコア・フレームを選択するactive frame sampling

## 結果

## 議論・コメント

* 個人的には，動画分類問題，特に今回扱っているようなUCFやKineticsではactive frame samplingのご利益がほとんどないと思う
    * 元々の動画が短いし，全体を集中して見ないとラベル付けできないようなデータでもない
* とはいえ問題設定を選べば面白い方向性と思う

## 関連文献
