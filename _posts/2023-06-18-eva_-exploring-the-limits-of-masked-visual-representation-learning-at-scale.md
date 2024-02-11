---
layout: post
title: "EVA: Exploring the Limits of Masked Visual Representation Learning at Scale"
tags: ["foundation models","video","vision&language","instance segmentation","image","object detection","semantic segmentation"]
last_modified_at: 2023-06-18 23:19:37 +0900
---

マスク付き画像モデリングを10億級大規模モデル・約千万の画像データにスケールさせる研究．予測対象の離散トークン化は不要で，マスクで隠されたCLIP特徴量を可視パッチから予測するだけで良いことを示した．

## 基本情報

```bibtex
@InProceedings{Fang_2023_CVPR,
    author    = {Fang, Yuxin and Wang, Wen and Xie, Binhui and Sun, Quan and Wu, Ledell and Wang, Xinggang and Huang, Tiejun and Wang, Xinlong and Cao, Yue},
    title     = {EVA: Exploring the Limits of Masked Visual Representation Learning at Scale},
    booktitle = {Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
    month     = {June},
    year      = {2023},
    pages     = {19358-19369}
}
```

### 論文リンク

[CVPR](https://openaccess.thecvf.com/content/CVPR2023/html/Fang_EVA_Exploring_the_Limits_of_Masked_Visual_Representation_Learning_at_CVPR_2023_paper.html) / [arXiv](https://arxiv.org/abs/2211.07636) / [GitHub](https://github.com/baaivision/EVA)

### 著者・所属

Yuxin Fang, Wen Wang, Binhui Xie, Quan Sun, Ledell Wu, Xinggang Wang, Tiejun Huang, Xinlong Wang, Yue Cao (Beijing Academy of Artificial Intelligence, Huazhong University of Science and Technology, Zhejiang University, Beijing Institute of Technology)

## 新規性

マスク付き画像モデリングを10億級の大規模モデルにスケールさせるため必要な設計上の検討を行った．その結果，BEiaTシリーズで採用されている予測対象の離散トークン化は不要で，マスクされたパッチに対応するCLIP特徴量をそのまま予測するMVPやMILIANで採用された方法が最もよくスケールすることを明らかにした．

## 手法

## 結果

## 議論・コメント

* EVAは"Explore the limits of Visual representation at scAle"らしい
* 実験の詳細はよく書かれていて再現はしやすそう（規模がアレなので実際に再現できる人は限られていそうだが）
    * ただ，MIMでCLIP特徴量を予測するのは具体的に何をやっているのか明示的には書かれていない
        * おそらくMVPやMILIANの論文を読めということだろうが
* 各種タスクで先行研究を上回っているものの，差はかなり薄い
    * モデルをかなり大規模化してこの差だと，実用上はかなり難しい感じがする

## 関連文献

* 手法的に最も関連が深い
    * Mvp: Multimodality-guided visual pre-training. arXiv preprint arXiv:2203.05175, 2022.
    * Milan: Masked image pretraining on language assisted representation. arXiv preprint arXiv:2208.06049, 2022.
