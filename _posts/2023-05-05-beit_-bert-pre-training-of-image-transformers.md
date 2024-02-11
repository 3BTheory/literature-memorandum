---
layout: post
title: "BEiT: BERT Pre-Training of Image Transformers"
tags: ["self-supervised learning","image"]
last_modified_at: 2023-05-05 23:08:51 +0900
---

MAEに先んじてマスク付き画像モデリングによる画像エンコーダの事前学習方法を提案した論文．

## 基本情報

```bibtex
@inproceedings{
bao2022beit,
title={\{BE\}iT: {BERT} Pre-Training of Image Transformers},
author={Hangbo Bao and Li Dong and Songhao Piao and Furu Wei},
booktitle={International Conference on Learning Representations},
year={2022},
url={https://openreview.net/forum?id=p-BhZSz59o4}
}
```

### 論文リンク

[OpenReview (ICLR2022)](https://openreview.net/forum?id=p-BhZSz59o4) / [arXiv](https://arxiv.org/abs/2106.08254)

### 著者・所属

Hangbo Bao, Li Dong, Songhao Piao, Furu Wei (Harbin Institute of Technology, Microsoft Research)

## 新規性

自然言語においてBERTで導入されたマスク付きモデリングの画像版・マスク付き画像モデリングに基づく自己教師あり学習の枠組み，BERT pre-training of Image Transformers (BEiT) を提案．

## 手法

既にMAEを知っているので，ここではMAEとの主な違いを挙げる：

* マスクされたトークンは `[MASK]` という特別なトークンとしてエンコーダに入力する（BERTの構成に倣っている）
    * MAEではマスクされていないトークンのみをエンコードし，デコーダにエンコードされたトークンと `[MASK]` の列を入力する
* マスク率が低い
    * MAEは75%程度に対してBEiTでは40%
* 再構成対象が事前に離散変分自己符号化器で学習した "visual token"
    * MAEではピクセル情報を直接再構成する
* Visual tokenを予測するheadが薄い（線型＋Softmax）
    * MAEではデコーダに（エンコーダよりは軽い）Transformerを使う

MAEと比べるとBERTの画像版という趣がある．後発のMAEは，画像と言語の違いに関する考察に基づき，より画像に特化させた構成と言える．MAEのまとめは[こちら](/literature-memorandum/2023/05/05/masked-autoencoders-are-scalable-vision-learners.html)．

## 結果

## 議論・コメント

* MAEでは再構成対象にvisual tokenを用いるかピクセル情報を用いるかの違いがあまりないとのことだったので，MAEとの性能差は他の要素によるものと考えられる

## 関連文献

* [BERTのまとめ](/literature-memorandum/2023/05/05/bert_-pre-training-of-deep-bidirectional-transformers-for-language-understanding.html)
* [MAEのまとめ](/literature-memorandum/2023/05/05/masked-autoencoders-are-scalable-vision-learners.html)
