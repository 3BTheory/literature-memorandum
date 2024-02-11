---
layout: post
title: "FGBC: Flexible graph-based balanced classifier for class-imbalanced semi-supervised learning"
tags: ["semi-supervised learning","class imbalance"]
last_modified_at: 2023-07-11 00:46:55 +0900
---

クラスインバランスを持つデータ向けの半教師あり学習．FixMatchなど既存の半教師アルゴにグラフ・ベースの分類ヘッド，クラスに依存した特徴量のmixup，適応的な閾値調整をアドオンして，クラスインバランスへの頑健性を向上させる．直近の困りごとと関連しているので文献探索用にメモ．

## 基本情報

```bibtex
@article{KONG2023109793,
	author = {Xiangyuan Kong and Xiang Wei and Xiaoyu Liu and Jingjie Wang and Weiwei Xing and Wei Lu},
	journal = {Pattern Recognition},
	pages = {109793},
	title = {FGBC: Flexible graph-based balanced classifier for class-imbalanced semi-supervised learning},
	volume = {143},
	year = {2023}}
```

### 論文リンク

[Pattern Recognition](https://www.sciencedirect.com/science/article/abs/pii/S0031320323004910) / [SSRN](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4240764)

### 著者・所属

* Xiangyuan Kong, Xiang Wei, Xiaoyu Liu, Jingjie Wang, Weiwei Xing, Wei Lu (Beijing Jiaotong University)

## 新規性

## 手法

主な技術要素は3つ：

* Graph-based classifier head
* Class-aware feature MixUp
* Flexible threshold adjustment

## 結果

## 議論・コメント

## 関連文献

* H. Lee et al., ABC: auxiliary balanced classifier for class-imbalanced semi-supervised learning, NeurIPS 2021.
