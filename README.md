# Particle Playground

吸引行列モデルから生まれる群れで遊ぶ、ブラウザ用の小さなゲーム／実験。

公開サイト: **https://sas-news.github.io/particle-playground/**

## Particle Tug

磁力で粒子を引き寄せ、左右の陣地に集める。75秒で多いほうの勝ち。

- **P1**: マウス / タッチ（長押しで吸引、Space でバースト）
- **P2**: 矢印キー（Shift で吸引、Enter でバースト）
- CPU と1人でも、1台のキーボードで2人でも遊べる
- 吸引中はエネルギーを消費。離すと回復。胞子に触れるとしびれる
- 陣地に粒子を留めているあいだスコアが増える

操作するのは磁場だけで、生き物は操作しない。群れは勝手に動き、引っ張り合いの中で陣地に流れ込む。

## ほかのモード

- **Particle Lab** — 引力・斥力の行列をランダム化して生態系を観察する。行列は K×K の表で表示。
- **Particle Derby**（旧作） — 群れの生き残りを予想するレース。
- **Particle Scoop**（旧作） — 群れをすくい集める捕獲ゲーム。

## 開発

```
src/sim.js       物理コア（吸引行列・kNNクラスタ解析）
src/tug.js       Particle Tug
src/lab.js       Particle Lab
src/derby.js     Particle Derby
src/game.js      Particle Scoop
src/rules.js     Scoop のルール

node build.js    # dist/ に単一HTMLを生成
```

- 物理は元実装の吸引行列モデル（トーラス、グリッド近傍）
- 描画はフラットな円。加算合成・グロー・残像は使わない
- 画像・音の外部アセットなし

元ネタ: [パーティクルライフ](https://cerevisiae-fii.github.io/particle-life/)（非公式）
