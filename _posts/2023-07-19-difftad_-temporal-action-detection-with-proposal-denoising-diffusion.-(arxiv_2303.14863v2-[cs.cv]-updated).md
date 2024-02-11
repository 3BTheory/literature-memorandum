---
layout: post
title: "DiffTAD: Temporal Action Detection with Proposal Denoising Diffusion. (arXiv:2303.14863v2 [cs.CV] UPDATED)"
tags: ["video","diffusion models","generative models","temporal action localization"]
last_modified_at: 2023-07-19 22:42:22 +0900
---

時間的行動検知を拡散モデルで解いた論文（ICCV2023）．時間的行動検知を動画エンコーダが出力する特徴量で条件づけられた生成タスクとみなす．ノイズの乗った行動区間候補をデノイズ（逆拡散）して行動区間を予測する，という形で拡散モデルの定式化に乗せる．ActivityNetとTHUMOSによる評価で従来法を上回る．

## 基本情報

```bibtex
@misc{nag2023difftad,
      title={DiffTAD: Temporal Action Detection with Proposal Denoising Diffusion}, 
      author={Sauradip Nag and Xiatian Zhu and Jiankang Deng and Yi-Zhe Song and Tao Xiang},
      year={2023},
      eprint={2303.14863},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```

### 論文リンク

[arXiv](http://arxiv.org/abs/2303.14863) / [GitHub](https://github.com/sauradip/DiffusionTAD)

### 著者・所属

* Sauradip Nag, Xiatian Zhu, Jiankang Deng, Yi-Zhe Song, Tao Xiang

## 新規性

## 手法

## 結果

## 議論・コメント

## 関連文献

* Shoufa Chen, Peize Sun, Yibing Song, and Ping Luo. Diffusiondet: Diffusion model for object detection. arXiv preprint arXiv:2211.09788, 2022
    * 物体検知をデノイジング拡散モデルとして定式化した論文

