---
layout: post
title: "Rectifying Noisy Labels with Sequential Prior: Multi-Scale Temporal Feature Affinity Learning for Robust Video Segmentation. (arXiv:2307.05898v1 [cs.CV])"
tags: ["video","video object segmentation","noisy labels"]
last_modified_at: 2023-07-17 11:26:21 +0900
---

医療動画の領域分割におけるラベルノイズ対策．従来の医療画像領域分割が単一画像の情報しか使ってこなかったのに対して，動画の連続性を考慮することでより高い精度を目指す．連続するフレームで同クラス・異クラスピクセル同士の特徴量の類似性に基づいて与えられたラベルの正確性を判定し，ラベル誤りを修正．また，その過程で得られる各ピクセルの「信頼度」に基づいてフレーム単位，動画単位の信頼度を計算．これらの信頼度によって損失関数を重み付する．
ラベル信頼度計算に用いる「類似度」を同一フレーム内や任意フレーム間のピクセルで評価するのと比較して，隣接フレームを使うことの効果が大きい＝動画の時間的な連続性を使うことは有用．

## 基本情報

```bibtex
@misc{cui2023rectifying,
      title={Rectifying Noisy Labels with Sequential Prior: Multi-Scale Temporal Feature Affinity Learning for Robust Video Segmentation}, 
      author={Beilei Cui and Minqing Zhang and Mengya Xu and An Wang and Wu Yuan and Hongliang Ren},
      year={2023},
      eprint={2307.05898},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```

### 論文リンク

[arXiv](https://ift.tt/qNj9kID)

### 著者・所属

* Beilei Cui, Minqing Zhang, Mengya Xu, An Wang, Wu Yuan, Hongliang Ren

## 新規性

## 手法

|<img src="https://i.gyazo.com/4f8a627c7ce1696431149c65a431ba49.png">|
|--------------------------------------------------------------------|
|原論文Figure 1. 手法の概要．|

* Temporal Feature Affinity Learning
    * 2種類(positive/negative)のaffinity
    * Positive affinity
        * あるフレーム $t$ のピクセル $i$ についているラベルがクラス $c$ とする
        * 隣接フレーム $t-1$ で同じラベル $c$ がついているピクセル $j$ と特徴量のコサイン類似度を計算する
        * 全ての $j$ について上記コサイン類似度を平均したものをpositive affinity $a_p$ と呼ぶ
    * Negative affinity $a_n$ も同様だが，同じラベルがついているピクセルの代わりに異なるラベルがついているピクセルを拾う
    * $a_p < t_p$ かつ $a_n > t_n$ を満たすピクセルは与えられた正解ラベルが誤りであると判定し，その時点でモデルが予測する値を正解とする
        * 閾値 $t_p, t_n$ はそれぞれ $a_p, a_n$ のデータセット平均値
* Multi-Scale Supervision
    * $a_p - a_n$ を画像全体や動画全体で平均したものを，画像単位・動画単位の信頼度とする
    * これらの値に基づいて損失関数を重み付けする

## 結果

## 議論・コメント

## 関連文献
