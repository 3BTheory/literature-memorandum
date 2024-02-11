---
layout: post
title: "Detecting Everything in the Open World: Towards Universal Object Detection"
tags: ["vision&language","object detection"]
last_modified_at: 2023-06-16 23:12:05 +0900
---

語彙の制限なく何でも検知できる物体検知器を（ラベル空間が非一様な）多数のデータセットから学習する普遍的（universal）物体検知問題を定式化，そのための手法UniDetectorを提案．

## 基本情報

```bibtex
@InProceedings{Wang_2023_CVPR,
    author    = {Wang, Zhenyu and Li, Yali and Chen, Xi and Lim, Ser-Nam and Torralba, Antonio and Zhao, Hengshuang and Wang, Shengjin},
    title     = {Detecting Everything in the Open World: Towards Universal Object Detection},
    booktitle = {Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
    month     = {June},
    year      = {2023},
    pages     = {11433-11443}
}
```

### 論文リンク

[arXiv](https://arxiv.org/abs/2303.11749) / [CVPR](https://openaccess.thecvf.com/content/CVPR2023/papers/Wang_Detecting_Everything_in_the_Open_World_Towards_Universal_Object_Detection_CVPR_2023_paper.pdf) / [GitHub](https://github.com/zhenyuw16/UniDetector)

### 著者・所属

Zhenyu Wang, Yali Li, Xi Chen, Ser-Nam Lim, Antonio Torralba, Hengshuang Zhao, Shengjin Wang (Tsinghua, BNRist, UHK, Meta AI, MIT)

## 新規性

非一様なラベル空間を持つ複数のデータセットから学習し，学習時に見ていない新規クラスの物体を検知する普遍的物体検知問題を定式化し，そのためのアルゴリズムUniDetectorを提案した．

## 手法

1. RegionCLIPによる大規模画像・テキスト事前学習
2. 非一様なラベル空間を持つ複数データセットで物体検知を学習
    * RPNとRoI分類器の学習をデカップル
    * クラス不可知局在化ネットワーク (CLN) によりクラスに依らず物体位置を特定する
4. オープン・ワールド推論
    * 予測がベースクラスに寄りやすい傾向を補正する確率較正

## 結果

主に学習ではCOCO, Objects 365, OpenImages, 推論にはLVIS, ImageNetBoxes, VisualGenomeを使用．オープン・ワールド，クローズド・ワールド，ODiWで評価．

## 議論・コメント

* Universal ODに要求される能力
    * 非一様なラベル空間を持つ複数のデータセットから学習できる
    * オープン・ワールドへの汎化性：未知クラスの識別能力
* Zero-shot/open-vocabulary/open-world/universalの違いは？
    * Universalはゼロショット性や無制限の語彙だけでなく，多データセットの活用により多様なシーン，ドメインに対応することを目指す
    * ゼロショット物体検知と違い，open-vocabulary物体検知ではベースクラスのデータセット（普通の物体検知用データセット）に加えて持つ画像・キャプションペアのデータセットを使い，大規模な語彙に対応した視覚的・意味的特徴空間を獲得できる
        * [open-vocabularyの原論文](https://arxiv.org/abs/2011.10678) Figure 2がわかりやすい

## 関連文献

* [Open-vocabulary object detectionの原論文](https://arxiv.org/abs/2011.10678)
    * [まとめ@cvpaper.challenge](https://xpaperchallenge.org/cv/survey/cvpr2021_summaries/325/)
