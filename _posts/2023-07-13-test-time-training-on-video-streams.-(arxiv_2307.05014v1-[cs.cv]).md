---
layout: post
title: "Test-Time Training on Video Streams. (arXiv:2307.05014v1 [cs.CV])"
tags: ["video","self-supervised learning","test-time training"]
last_modified_at: 2023-07-13 19:24:17 +0900
---

評価時に評価用のデータ（ラベル無し）を使って訓練することで精度を上げる評価時訓練の論文．評価データがバッチで，またはiidなサンプリングによって得られることを前提とする従来研究に対し，本論文では動画が1フレームずつ時系列で与えられる状況に拡張．提案手法Online TTT-MAEは，評価データの時間的滑らかさを利用し，直近のフレームとモデルパラメータから記憶を引き継いでバックボーンを更新する．

## 基本情報

```bibtex
@misc{wang2023testtime,
      title={Test-Time Training on Video Streams}, 
      author={Renhao Wang and Yu Sun and Yossi Gandelsman and Xinlei Chen and Alexei A. Efros and Xiaolong Wang},
      year={2023},
      eprint={2307.05014},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```

### 論文リンク

[arXiv](https://ift.tt/3AygVzH) / [Project Page](https://video-ttt.github.io/)

### 著者・所属

* Renhao Wang, Yu Sun, Yossi Gandelsman, Xinlei Chen, Alexei A. Efros, Xiaolong Wang

## 新規性

評価時訓練を動画ストリームからオンラインで学習する設定に拡張し，そのための手法を提案した点．

## 手法

* 訓練時
    * タスクヘッドと再構成デコーダーがバックボーンを共有するY型NNをタスク損失とMAE損失で学習
* 評価時
    * 再構成デコーダーとバックボーンをMAE損失の最小化で更新する
    * 暗黙的メモリー：前ステップのネットワークパラメータとして直前の評価データの記憶を引き継ぐ
    * 明示的メモリー：直前の数フレームをためておいて再構成タスクに使用する

## 結果

## 議論・コメント

## 関連文献
