---
layout: post
title: "Learning to Detect and Segment for Open Vocabulary Object Detection"
tags: ["instance segmentation","object detection"]
last_modified_at: 2023-06-19 00:04:57 +0900
---

語彙を制限しない物体検知の研究．先行研究ではボックス/マスクの推定に物体クラスに依存しないモデルを用いたのに対し，この回帰にも意味情報を活用するためのヘッド CondHead を提案．ヘッドのパラメータを意味埋め込みから動的に決定する．従来法のヘッドに採用することで物体検知と実体領域分割の精度を向上．

## 基本情報

```bibtex
@InProceedings{Wang_2023_CVPR,
    author    = {Wang, Tao},
    title     = {Learning To Detect and Segment for Open Vocabulary Object Detection},
    booktitle = {Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
    month     = {June},
    year      = {2023},
    pages     = {7051-7060}
}
```

### 論文リンク

[CVPR](https://openaccess.thecvf.com/content/CVPR2023/html/Wang_Learning_To_Detect_and_Segment_for_Open_Vocabulary_Object_Detection_CVPR_2023_paper.html) / [arXiv](https://arxiv.org/abs/2212.12130)

### 著者・所属

Tao Wang, Nan Li (NUS, UCSD)

## 新規性

意味情報の埋め込みから回帰器のパラメータを動的に生成するCondHeadにより，カテゴリーの意味情報を使ってボックスやマスクの回帰精度を上げることができると明らかにした点（従来のopen-vocab物体検知では，分類に画像・テキスト学習で獲得した意味情報を用いるものの回帰はクラス非依存に実行していた）．

## 手法

## 結果

## 議論・コメント

## 関連文献

* Open-world object detection
    * OVR-CNN
    * ViLD
    * RegionCLIP
    * DetPro
