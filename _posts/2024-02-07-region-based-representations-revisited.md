---
layout: post
title: "Region-Based Representations Revisited"
tags: ["foundation models","video","image","semantic segmentation","feature learning"]
last_modified_at: 2024-02-07 21:12:48 +0900
---

領域ベースの特徴表現に関する研究．深層学習を使った画像の特徴抽出ではピクセルベースやパッチベースの方法が主流だが，領域分割の基盤モデルが容易に利用可能になっていることから，これら基盤モデルを使って画像を領域の集合ととらえ，領域単位の特徴表現を使って画像認識する方法を検討した．

## 基本情報

### 論文リンク

* [arXiv](https://arxiv.org/abs/2402.02352)

### 著者・所属

* Michal Shlapentokh-Rothman, Ansel Blume, Yao Xiao, Yuqun Wu, Sethuraman T V, Heyi Tao, Jae Yong Lee, Wilfredo Torres, Yu-Xiong Wang, Derek Hoiem

## 新規性

領域分割の基盤モデルを活用して領域ベースの特徴表現を構築する方法について，領域マスクの生成方法，ベースとなる特徴抽出器の種類，プーリング方法の観点で検討，画像の意味的領域分割，多視点領域分割，画像検索，動画における活動分類のタスクで性能を評価．

## 手法

* マスク生成
    * SAMをデフォルト設定で使用しマスクを生成
    * SLICによりスーパーピクセルを生成し，SAMのマスクでカバーされていない領域と300ピクセル以上重複しているものを残す
    * SAMが生成したマスクと前ステップで残したSLICの出力を下流で使用する
* プーリング
    * DINOv2で得た特徴マップを，生成した各マスクの領域で平均プーリングする
    * 平均プーリングに際して，特徴マップはマスクの解像度に合わせてアップサンプリングする

## 結果

画像の意味的領域分割，多視点領域分割，画像検索，動画における活動分類のタスクでSotAに及ばないまでもcompetitiveな結果．

## 議論・コメント



## 関連文献
