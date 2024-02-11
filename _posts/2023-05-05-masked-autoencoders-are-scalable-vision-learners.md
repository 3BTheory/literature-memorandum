---
layout: post
title: "Masked Autoencoders Are Scalable Vision Learners"
tags: ["foundation models","self-supervised learning","image"]
last_modified_at: 2023-05-05 23:06:46 +0900
---

昨今流行している画像データ向けの自己教師あり学習のアルゴリズム，マスク付き自己符号化器の元祖．マスク画像を使った自己符号化器のアイデア自体は古くからあるが，自然言語処理の類例をベースに，言語と画像の違いに関する考察に基づき詳細を設計してSOTAな自己教師ありアルゴリズムに仕上げたことに意義がある．

## 基本情報

```bibtex
@inproceedings{he2022masked,
  title={Masked autoencoders are scalable vision learners},
  author={He, Kaiming and Chen, Xinlei and Xie, Saining and Li, Yanghao and Doll{\'a}r, Piotr and Girshick, Ross},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={16000--16009},
  year={2022}
}
```

### 論文リンク

[CVPR2022](https://openaccess.thecvf.com/content/CVPR2022/papers/He_Masked_Autoencoders_Are_Scalable_Vision_Learners_CVPR_2022_paper.pdf) / [arXiv](https://arxiv.org/abs/2111.06377)

### 著者・所属

Kaiming He, Xinlei Chen, Saining Xie, Yanghao Li, Piotr Dollár, Ross Girshick (FAIR)

## 新規性

自然言語処理におけるマスク付き言語モデリング（BERTやGPT等）のアイデアをベースに，画像データ向けの自己教師あり学習アルゴリズム，マスク付き自己符号化器（masked autoencoder, MAE）を提案．言語との違いとして特筆すべきは，

* マスク率が高い（75%．BERTのマスク率は15%）
    * ピクセルで表現された画像は情報の冗長性が高い
    * ⇨マスク率が低いと隣接ピクセル（パッチ）からの連続性から再構成タスクが簡単になりすぎる
* 埋め込みが意味的な情報を持つためには十分に複雑な復号器（4層程度のTransformer）が必要
    * 画像の場合，自己符号化器の出力は意味的な情報の薄いピクセル情報である
    * 符号化器の出力（意味的な情報を十分に持っていてほしい）をピクセル情報に変換するのに十分な能力が必要

## 手法

|<img width="489" alt="image" src="https://user-images.githubusercontent.com/17794644/236240971-a98bd2cc-4efa-45d8-a9e7-fd9492ceabab.png">|
|---|
|論文のFigure 1: MAEの概念図．ネットワーク構造はパッチベースのVision Transformer．|

ポイントを絞って取り上げる．前提として，ネットワーク構造にはVision Transformerを採用している．したがって，最終的にピクセルデータを再構成する段階を除き，画像をパッチに切り分け，各パッチを埋め込んだ「トークン」が処理の単位となっている．

* 入力トークンをマスクし，マスクされていないトークンのみを符号化器（encoder）に入力する
    * マスクを表すトークンを符号化器に入力しない設計は，高いマスク率と合わせて事前学習における計算量の大幅削減に貢献している
* 符号化器の出力にマスク・トークンを加えた列を復号器（decoder）に入力する
    * （前述の通り十分に複雑であるが，符号化器よりも十分に軽量な）復号器のため，マスク・トークンを含めて入力しても計算量的に現実的
* 出力されたトークンからさらに元のピクセル情報を再構成する
    * ピクセル情報ではなく画像入力から作られる任意のトークン列の再構成タスクを原理的には採用できる
        * 類似の再構成タスクを採用しているBEiTではトークン再構成タスクを採用している
        * 本論文でもそのような場合について検証を行ないピクセル再構成と大差ない結果を得ている
        * ピクセル再構成を採用したのは「シンプルさ」？
* 再構成誤差を最小化するように最適化する

## 結果

ImageNet事前学習→ImageNetファインチューニング，転移学習の設定で実験し先行研究と比較している．

Ablation studyの分量は多いが興味深いので，結果の詳細は省略してablationの切り口だけ箇条書きで列挙しておく．

* マスク率
* デコーダの設計（深さ，幅）
* マスク・トークンを符号化器に入力するか否か
* 再構成ターゲット（ピクセル vs 正規化されたピクセル vs PCAしたトークン vs dVAEトークン）
* データ拡張
* マスクの付け方
* 訓練のスケジュール
* ファイン・チューニングする層数

## 議論・コメント

実験が多く考察も深いので，様々な設計上の選択に説得力がある．

## 関連文献

* 自然言語処理におけるマスク付き言語モデリング: BERT, GPT
* 雑音除去自己符号化器の特殊例としてのマスク付き自己符号化器: Vincent, et al., Stacked denoising autoencoders, JMLR, 2010.
* 画像データに対してマスク付きモデリングを適用した近年の例: iGPT, ViT, BEiT
