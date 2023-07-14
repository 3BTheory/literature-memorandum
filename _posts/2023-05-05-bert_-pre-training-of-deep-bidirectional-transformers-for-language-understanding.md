---
layout: post
title: "BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding"
tags: ["self-supervised learning","language"]
last_modified_at: 2023-05-05 22:15:21 +0900
---

Transformerベースの言語モデルを教師なしで言語エンコーダを事前学習そしてファインチューニングする手法の論文．マスク付き言語モデルを流行らせた原典．モデリング面では，先行するGPTが生成タスクを用いるため自己回帰的なTransformerを用いているのに対して，BERTはエンコーダのみで事前学習するため双方向Transformerを用いることが特徴．

## 基本情報

```bibtex
@article{devlin2018bert,
  title={Bert: Pre-training of deep bidirectional transformers for language understanding},
  author={Devlin, Jacob and Chang, Ming-Wei and Lee, Kenton and Toutanova, Kristina},
  journal={arXiv preprint arXiv:1810.04805},
  year={2018}
}
```

### 論文リンク

[arXiv](https://arxiv.org/abs/1810.04805)

### 著者・所属

Jacob Devlin, Ming-Wei Chang, Kenton Lee, Kristina Toutanova (Google AI)

## 新規性

双方向Transformer（Transformerエンコーダ）を教師なし事前学習し，下流タスクについてファインチューニングする方法を提案．

## 手法

|<img width="949" alt="image" src="https://user-images.githubusercontent.com/17794644/236381661-43db6295-6571-4ced-b223-9716f4babaf7.png">|
|---|
|原論文Figure 1. BERTの概念図．|

事前学習では次に挙げる2つのタスクを学習する：

* Masked language modeling (MLM)
* Next sentence prediction (NSP)

MLMでは，入力トークンの一部（１５%程度）を特別なトークン `[MASK]` に置き換え， `[MASK]` の位置にあったトークンを予測するタスク（いわゆる穴埋め問題）．NSPタスクでは，2つの文を連続して入力する．入力する2文の選び方は，データセット中で実際に連続して現れる2文か，全くランダムに選んだ２文かであり，モデルは受け取った2文が実際に連続する文であるかどうかを判定する．

下流タスクの学習では，事前学習済みのエンコーダに１層足して，事前学習済みのエンコーダも含めた全体を更新する．

## 結果

## 議論・コメント

* GPT, ELMoとのモデリングの違いについてはFigure 3 (Appendix) がわかりやすかった
* ビジョンのMAEから遡ってきたのでマスク付き言語モデルの論文として読み始めたが，意外と「双方向性」を主張の中心に据えていて（BERTのBはbidirectionalのB），アブストではMLMに触れてすらいなかった
    * 門外漢的には，「双方向」なのは単にTransformerのエンコーダを使っただけなので新しさをあまり感じない…自己回帰的な生成モデル学習ではなくエンコーダ単体でも教師なし学習できるというのが新しかったのだろうか
        * この辺りは自然言語界隈の

## 関連文献

## 参考資料

* [Qiita記事](https://qiita.com/omiita/items/72998858efc19a368e50#123-%E6%95%99%E5%B8%AB%E3%81%82%E3%82%8A%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AB%E3%82%88%E3%82%8B%E8%BB%A2%E7%A7%BB%E5%AD%A6%E7%BF%92)
