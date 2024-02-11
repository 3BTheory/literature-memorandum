---
layout: post
title: "The Implicit Bias of Minima Stability in Multivariate Shallow ReLU Networks. (arXiv:2306.17499v1 [cs.LG])"
tags: ["implicit regularization","deep learning dynamics","expressivity","depth separation"]
last_modified_at: 2023-07-13 18:44:30 +0900
---

ReLU NNの暗黙的バイアスに関する研究．SGDで到達できる解の滑らかさを評価した．さらに，普遍近似定理を解の安定性の観点から議論，勾配法の安定解となり得る1隠れ層NNでは近似できないが，2隠れ層NNなら近似できる関数が存在すること（深さ分離）を示した．一方，ソボレフな関数に限れば，1隠れ層NNの安定解が任意の関数を近似できることを示した．

## 基本情報

```bibtex
@misc{nacson2023implicit,
      title={The Implicit Bias of Minima Stability in Multivariate Shallow ReLU Networks}, 
      author={Mor Shpigel Nacson and Rotem Mulayoff and Greg Ongie and Tomer Michaeli and Daniel Soudry},
      year={2023},
      eprint={2306.17499},
      archivePrefix={arXiv},
      primaryClass={cs.LG}
}
```

### 論文リンク

[arXiv](https://arxiv.org/abs/2306.17499)

### 著者・所属

* Mor Shpigel Nacson, Rotem Mulayoff, Greg Ongie, Tomer Michaeli, Daniel Soudry (Technion, Marquette)

## 新規性

SGDで到達できる解関数の滑らかさ（損失関数の滑らかさではない）については，1変数関数の場合について評価した先行研究があるが，本研究では多変数の場合にそれを拡張した．

また，普遍近似定理に解の安定性の観点を持ち込んだ．従来の普遍近似定理はNNで表現できる関数のクラスは，別のあるクラスに属する任意の関数を近似できるか，という問いに答えるものだが，損失関数の最小化によって「NNで表現できる関数」の全てに到達できるとは限らない．本論文では，「NNで表現できる関数」の集合の部分集合として，「損失関数の安定な局所解となり得る関数」の集合を考え，これに属する関数で近似できるクラスを議論した．結論としては，安定な2層NNでは近似できないが安定な3層NNでは近似できる連続関数が存在すること（深さ分離，depth separation），十分になめらかな関数に限れば安定な2層NNだけで近似できることを示した．

## 手法

## 結果

## 議論・コメント

## 関連文献
