---
layout: post
title: "Segment Everything Everywhere All at Once"
tags: ["foundation models","image","promptable vision models","semantic segmentation"]
last_modified_at: 2023-06-01 17:43:11 +0900
---

領域分割向け基盤モデルSEEMの論文．同時期に公開されたSAMと同様に多種のプロンプトを入力としそれに対応する領域のマスクを出力する．領域のクラスを予測できるため，学習にはクラス分類の正解を必要とする．

## 基本情報

```bibtex
@misc{zou2023segment,
      title={Segment Everything Everywhere All at Once}, 
      author={Xueyan Zou and Jianwei Yang and Hao Zhang and Feng Li and Linjie Li and Jianfeng Gao and Yong Jae Lee},
      year={2023},
      eprint={2304.06718},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```

### 論文リンク

[arXiv](https://arxiv.org/abs/2304.06718)

### 著者・所属

Xueyan Zou, Jianwei Yang, Hao Zhang, Feng Li, Linjie Li, Jianfeng Gao, Yong Jae Lee (UW–Madison, Microsoft, HKUST)

## 新規性

多種のプロンプトとその組み合わせ対応し，インタラクティブにセグメンテーションと領域のクラス分類ができる手法 Segment Everything Everywhere Model (SEEM) を提案．

## 手法

## 結果

## 議論・コメント

* 手法的にはX-Decoderなる先行研究がベースになっている模様
    * 論文自体にはこの研究を再現できるような手法の詳細がほとんど載っていない…

## 関連文献

