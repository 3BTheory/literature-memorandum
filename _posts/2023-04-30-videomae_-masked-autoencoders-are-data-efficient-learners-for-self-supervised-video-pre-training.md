---
layout: post
title: "VideoMAE: Masked Autoencoders are Data-Efficient Learners for Self-Supervised Video Pre-Training"
tags: ["foundation models","video","self-supervised learning"]
last_modified_at: 2023-05-22 09:19:54 +0900
---

（主にViT系モデル向けの）自己教師あり学習の手法であるmasked autoencoderを動画向けに拡張したVideoMAEを提案．動画においては，時間方向に伸びるチューブ状のマスクを使うこと，高いマスク率を用いることを提案．比較的小規模なデータセットでもそのデータセットでVideoMAEによる事前学習をした後に教師あり学習することで，スクラッチから学習するよりも高い精度が出ることを示した．

## 基本情報

```bibtex
@inproceedings{tong2022videomae,
  title={Video{MAE}: Masked Autoencoders are Data-Efficient Learners for Self-Supervised Video Pre-Training},
  author={Zhan Tong and Yibing Song and Jue Wang and Limin Wang},
  booktitle={Advances in Neural Information Processing Systems},
  year={2022}
}
```

### 論文リンク

[NeurIPS](https://proceedings.neurips.cc/paper_files/paper/2022/hash/416f9cb3276121c42eebb86352a4354a-Abstract-Conference.html) / [NeurIPS Slide](https://nips.cc/media/neurips-2022/Slides/54362.pdf) / [OpenReview](https://openreview.net/forum?id=AhccnBXSne) / [GitHub](https://github.com/MCG-NJU/VideoMAE)

### 著者・所属

Zhan Tong, Yibing Song, Jue Wang, Limin Wang (Nanjing U, Tencent)

## 新規性

* Masked autoencoderを動画向けに拡張したVideoMAEを提案
* 手法面では，動画のピクセルデータが冗長であることを考慮したマスク方法であるチューブ・マスキングが新しい

## 手法

* 直方体埋め込み
    * ViTでいうpatch embeddingの時空間3次元版
    * 動画向けTransformerで採用例あり（ViViT, MViT, Video Swin Transformer）
    * キューブサイズは $2\times16\times16$ を採用
* チューブ・マスキング
    * 空間的なキューブ・マスクを時間軸方向に伸ばしてチューブ状にマスクする
    * 動きの少ないキューブの情報が時間的に隣接するキューブからリークするのを防ぐため
* 高いマスク率
    * 90~95%のキューブにマスクする

## 結果

Kinetics-400, Something-Something V2, UCF101, HMDB51で評価．

各データセットでVideoMAE事前学習したのちに同じデータセットで教師あり学習した結果（Table 2）と，KineticsまたはSSV2で事前学習してその他のデータセットに転移学習した結果が含まれる（Table 1e, Table 4）．いくつか興味深いと思った点を取り上げる．

* 転移学習では，MoCo v3による事前学習よりも大幅に性能が向上している
* 驚いたのはUCF101やHMDB51でVideoMAE事前学習＆教師あり学習した結果で，これはKinetics-400でMoCo v3事前学習からの転移学習したのに匹敵する性能が出ている
    * つまり，事前学習に必ずしも大規模データセットを用意できなくてもVideoMAEをやる意味があるということ
* 大規模データセットの場合，転移学習（K400⇄SSV2）よりも同じデータセットでVideoMAE⇨教師あり学習した方が良い

## 議論・コメント



## 関連文献

* Feichtenhofer+2022: Masked Autoencoders As Spatiotemporal Learners
    * 動画にMAEを適用した同時期の論文（同じNeurIPS2022に採択されている）
* CVにおけるBERT系マスク・モデリング
    * BEiT
    * BEVT
    * VIMPAC
* オリジナルのMAE (ImageMAE)
* HOG特徴を再構成するMaskFeat

