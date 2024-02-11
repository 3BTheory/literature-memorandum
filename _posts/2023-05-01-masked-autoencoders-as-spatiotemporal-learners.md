---
layout: post
title: "Masked Autoencoders As Spatiotemporal Learners"
tags: ["foundation models","video","self-supervised learning"]
last_modified_at: 2023-05-01 23:26:15 +0900
---

ViT系モデル向けの自己教師あり学習であるmasked autoencoderを動画向けに拡張した論文．動画は静止画よりも情報の冗長性が高いことを反映して，90%という高いマスク率を必要とすることを示した（静止画では75%程度が良い）．同じNeurIPS2022で発表されたVideoMAEと違って時空間的にランダムなマスクが良いと主張している．

## 基本情報

```bibtex
@inproceedings{NEURIPS2022_e97d1081,
 author = {Feichtenhofer, Christoph and fan, haoqi and Li, Yanghao and He, Kaiming},
 booktitle = {Advances in Neural Information Processing Systems},
 editor = {S. Koyejo and S. Mohamed and A. Agarwal and D. Belgrave and K. Cho and A. Oh},
 pages = {35946--35958},
 publisher = {Curran Associates, Inc.},
 title = {Masked Autoencoders As Spatiotemporal Learners},
 url = {https://proceedings.neurips.cc/paper_files/paper/2022/file/e97d1081481a4017df96b51be31001d3-Paper-Conference.pdf},
 volume = {35},
 year = {2022},
 bdsk-url-1 = {https://proceedings.neurips.cc/paper_files/paper/2022/file/e97d1081481a4017df96b51be31001d3-Paper-Conference.pdf}}
```

### 論文リンク

[arXiv](https://arxiv.org/pdf/2205.09113.pdf) / [NeurIPS](https://proceedings.neurips.cc/paper_files/paper/2022/hash/e97d1081481a4017df96b51be31001d3-Abstract-Conference.html) / [OpenReview](https://openreview.net/forum?id=UaXD4Al3mdb)

### 著者・所属

* Christoph Feichtenhofer, Haoqi Fan, Yanghao Li, Kaiming He (Meta)

## 新規性

* Masked autoencoderを動画向けに拡張した
    * 同様の手法であるVideoMAEと同じNeurIPS2022で発表された

## 手法

VideoMAEとの一番の差分は，ランダムなマスキングを採用している点（VideoMAEでは時間方向に伸びる「チューブ」状のマスクを採用）．

## 結果

基本的にはKineticsで事前学習してKineticsや他のデータセットでファイン・チューニングする設定．いずれも教師ありの事前学習よりも優れた結果となっている．

## 議論・コメント

* マスキング戦略についてVideoMAEと異なる結論になっている
    * ただ，ランダムマスクとチューブマスクの差はかなり小さいので，誤差の範囲なのかもしれない
    * この他の点について（例えばマスク率）は両者の一致度が高い
* Masked autoencoderは速い
    * エンコーダはマスクされていないトークン列が入力されるため
    * また，デコーダも浅めのネットワークを採用している
    * データローディングがボトルネックになる程度には速い

## 関連文献

* #4
