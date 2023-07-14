---
layout: post
title: "Segment Anything Model (SAM) Enhanced Pseudo Labels for Weakly Supervised Semantic Segmentation"
tags: ["foundation models","image","semantic segmentation"]
last_modified_at: 2023-06-01 01:22:47 +0900
---

SAMを領域分割の弱教師あり学習（WSSS）に用いた論文．WSSSでは画像分類を学習し，CAMに後処理を施して擬似ラベルとする手法が主流である．提案手法では擬似ラベルをプロンプトとしてSAMでマスクを生成し擬似ラベルとする．

## 基本情報

```bibtex
@misc{chen2023segment,
      title={Segment Anything Model (SAM) Enhanced Pseudo Labels for Weakly Supervised Semantic Segmentation}, 
      author={Tianle Chen and Zheda Mai and Ruiwen Li and Wei-lun Chao},
      year={2023},
      eprint={2305.05803},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```

### 論文リンク

[arXiv](https://arxiv.org/abs/2305.05803)

### 著者・所属

* Tianle Chen, Zheda Mai, Ruiwen Li, Wei-lun Chao (OSU, EAIGLE Inc)

## 新規性

Segment Anything Model (SAM) を領域分割の弱教師あり学習に適用したこと．

## 手法

WSSSではこれまで，次のような3段階のパイプラインが主流であった．

1. 画像単位で与えられていた物体クラスのラベルで分類を学習しCAMを生成
2. 後処理によりCAMを質の高い擬似ラベルに変換
3. 擬似ラベルを使った教師あり学習で領域分割を学習

CAMベースの方法は，識別性の高い局所的な領域にマスクが生成されがちで，物体領域を覆うことが難しかった．そこで提案法では，従来法のパイプラインの中で擬似ラベルをプロンプトとしてSAMを適用し，より精度の高い擬似ラベルを生成する．また，従来法の後処理を完全に取り除いて，生のCAMマスクにSAMを適用することも可能（SAMを使って後処理しているとみなせる）．

## 結果

PASCAL VOC 2012データセットを用いた評価で，ベースとなる従来法を大きく超える精度を達成．また，従来法の後処理を取り除きSAMによる後処理のみを行なっても，後処理を含む場合と同程度の精度が出ることがわかった．つまり，CAMの後処理方法としてSAMの優秀さを示している．

## 議論・コメント

CAMの問題＝実際よりも狭いマスクが生成される点は改善されたものの，一つのマスクが複数の物体を覆ってしまうケースが目立ったとのこと．

## 関連文献
