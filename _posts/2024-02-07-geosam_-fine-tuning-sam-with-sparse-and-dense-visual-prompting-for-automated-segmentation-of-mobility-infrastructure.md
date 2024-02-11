---
layout: post
title: "GeoSAM: Fine-tuning SAM with Sparse and Dense Visual Prompting for Automated Segmentation of Mobility Infrastructure"
tags: ["foundation models","semantic segmentation"]
last_modified_at: 2024-02-07 23:31:08 +0900
---

Segment Anything Model (SAM) をファインチューニングし地理画像の意味的領域分割に適応させる．SAMをベースに，マスク・デコーダのファインチューニングによって意味的領域分割を解かせる．マスク・デコーダへ入力するプロンプトを事前学習済みのCNNベース意味的領域分割器とSAMから自動生成する方法がこの研究の肝となる．

## 基本情報

### 会議・論文誌

[cs.CV updates on arXiv.org](https://arxiv.org/rss/)

### 論文リンク

* https://arxiv.org/abs/2311.11319

### 著者・所属

* Rafi Ibn Sultan Chengyin Li Hui Zhu Prashant Khanduri Marco Brocanelli Dongxiao Zhu

## 新規性

* SAMを地理画像へ適用した点
* SAMに与えるプロンプトを自動的に生成する手法
* マスク・デコーダのみを最適化するParameter Efficient Fine-Tuning

## 手法

* 意味的領域分割のマスク生成は，SAMのマスク・デコーダをマルチチャンネル出力にすることで多クラス化＝意味的領域分割に適応
* マスク生成のために2種類のプロンプトを生成
    * 疎なプロンプト
        * 事前学習しておいたCNNベースの意味的領域分割器から代表的な点をサンプル
        * e.g. ランダムサンプル，信頼度の高い点をサンプル
    * 密なプロンプト
        * 上記，CNNベースの意味的領域分割器の出力を（オリジナルの）SAMのプロンプトとしてマスクを生成し，それで生成されたマスクを密なプロンプトとして採用
* 上述のマルチ・チャンネル化したマスク・デコーダをファインチューニング

## 結果

## 議論・コメント

## 関連文献
