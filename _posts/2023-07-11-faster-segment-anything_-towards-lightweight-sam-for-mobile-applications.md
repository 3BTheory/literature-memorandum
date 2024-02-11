---
layout: post
title: "Faster Segment Anything: Towards Lightweight SAM for Mobile Applications"
tags: ["foundation models","instance segmentation","semantic segmentation"]
last_modified_at: 2023-07-11 00:22:15 +0900
---

Segment Anything Model (SAM)を蒸留により軽量化するMobileSAMの提案．SAM全体を一度に蒸留するのではなく，画像エンコーダとマスクデコーダに分けて蒸留を行う（後者はオプション）．精度を維持しつつ推論時間を1/50以下にした．

## 基本情報

```bibtex
@misc{zhang2023faster,
      title={Faster Segment Anything: Towards Lightweight SAM for Mobile Applications}, 
      author={Chaoning Zhang and Dongshen Han and Yu Qiao and Jung Uk Kim and Sung-Ho Bae and Seungkyu Lee and Choong Seon Hong},
      year={2023},
      eprint={2306.14289},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```

### 論文リンク

[arXiv](https://arxiv.org/abs/2306.14289) / [GitHub](https://github.com/ChaoningZhang/MobileSAM)

### 著者・所属

* Chaoning Zhang, Dongshen Han, Yu Qiao, Jung Uk Kim, Sung-Ho Bae, Seungkyu Lee, Choong Seon Hong (Kyung Hee University)

## 新規性

オリジナルのSAMでは画像エンコーダの実行に500ms近くかかっていたところ，10ms以下に軽量化したこと．

## 手法

|<img src="https://i.gyazo.com/bd87841be3675560b004ae83c8ee0c91.png">|
|--------------------------------------------------------------------|
|原論文Figure 3．手法の概要．画像エンコーダ部分を蒸留する．|

ViT-HからなるオリジナルのSAMの画像エンコーダ部分を軽量なモデルに蒸留する．各種ハイパーパラメータについて記述はあるものの，肝心の蒸留の詳細は論文ではあまり語られていない…（コードを見ればいいのだが）

## 結果

## 議論・コメント

## 関連文献

* Fast Segment Anything

