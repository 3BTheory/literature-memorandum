---
layout: post
title: "Source-Free Video Domain Adaptation With Spatial-Temporal-Historical Consistency Learning"
tags: ["video","domain adaptation","source-free domain adaptation"]
last_modified_at: 2023-05-30 22:14:21 +0900
---

ターゲットデータによる一貫性学習による動画向けのソース・フリーな教師なしドメイン適応．先行研究ATCoNと比較して，フレームごとのデータ拡張を用いる点，同一動画からサンプルしたクリップ間の一貫性をメモリーで効率的に実装した点が新しい．

## 基本情報

```bibtex
@InProceedings{Li_2023_CVPR,
    author    = {Li, Kai and Patel, Deep and Kruus, Erik and Min, Martin Renqiang},
    title     = {Source-Free Video Domain Adaptation With Spatial-Temporal-Historical Consistency Learning},
    booktitle = {Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
    month     = {June},
    year      = {2023},
    pages     = {14643-14652}
}
```

### 論文リンク

[CVPR2023](https://openaccess.thecvf.com/content/CVPR2023/html/Li_Source-Free_Video_Domain_Adaptation_With_Spatial-Temporal-Historical_Consistency_Learning_CVPR_2023_paper.html)

### 著者・所属

Kai Li, Deep Patel, Erik Kruus, Martin Renqiang Min (NEC Labs America)

## 新規性

転移元データを用いないソース・フリーなドメイン適応を動画に適用した先行研究 ATCoN と比較すると，空間的な摂動（＝フレームごとのデータ拡張）に対する予測の一貫性を目的関数に取り入れた点，同一動画からサンプルした異なるクリップ間の一貫性にメモリー機構を導入して効率的に実装した点が新しい．

## 手法

今回の設定では，適応元のラベル付きデータ（ソースデータ）で学習済みのモデルと適応先のラベルなしデータ（ターゲットデータ）から学習する．提案法は，以下で説明する5種類の損失関数（3種類の一貫性損失と2種類のエントロピー）の最小化として定式化される．

* 空間的一貫性損失
    * フレーム単位のデータ拡張を掛ける前と後の予測結果の間で計算されるKLダイバージェンス
    * 空間的な摂動の下で予測が不変であるように
* 時間的一貫性損失
    * クリップを構成するフレームをランダムに取り除くデータ拡張前後の予測結果間のKLダイバージェンス
    * 時間的な摂動の下で予測が不変であるように
* 経時一貫性（Historical consistency）
    * 学習過程であるデータに対する過去に行った予測と現在行った予測との間で計算されるKLダイバージェンス
    * これもある種の時間摂動に対する一貫性とみなせる
* データごとのエントロピー
    * 各データに対する予測結果のエントロピー
    * 各データに対する予測が鋭くなるように
* データセット全体での負エントロピー
    * データごとの予測結果の平均＝データセット全体のクラス分布の予測に対する負のエントロピー
    * クラス間の偏りが生じないように

## 結果

UCF-HMDB, UCF-Kinetics, Jester, DailyDAで評価．多くの場合に従来法（SHOT, ATCoN）を上回る精度を達成．

3種類の一貫性損失はどれを欠いても性能が大きく劣化する．

## 議論・コメント

* DailyDAの失敗分析では，ソースモデルの性能がターゲットデータに対して悪すぎる例で性能が低いと分析
    * 本論文に限らずソース・フリーのドメイン適応ではターゲットに対する予測のエントロピーを下げるような学習を行うことが多いので，ソースモデルが弱いと精度が悪くなりがち

## 関連文献

* Liang, et al., Do we really need to access the source data?, ICML 2020. (SHOT)
* Xu, et al., Source-free video domain adaptation, ECCV 2022. (ATCoN)
* [A Comprehensive Survey on Source-free Domain Adaptation](https://arxiv.org/abs/2302.11803)
