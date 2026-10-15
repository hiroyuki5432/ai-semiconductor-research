# AgenticPD

## 文献情報

- 正式題名: *AgenticPD: A Stage-Aware Agentic Framework for Closed-Loop Physical Design Optimization*
- 著者: Shuo Ren, Zijin Cheng, Yaohui Han, Libo Shen, Leilei Jin, Wanting Tian, Rongliang Fu, Chao Wang, Bei Yu, Tsung-Yi Ho
- 所属: The Chinese University of Hong Kong、Southeast University
- 発表: arXiv:2607.04758 v3（2026-10-04）。原著HTMLはASPDAC 2027の会議情報を記載。
- 一次資料: [原著概要](https://arxiv.org/abs/2607.04758)、[原著本文](https://arxiv.org/html/2607.04758)、[公開コード](https://github.com/Flians/AgenticPD)

## 1行のエッセンス

物理設計を工程別に探索し、良好な中間状態から分岐して再利用することでpost-routeのタイミングを改善する。

## 技術的な差分と新規性

フロアプラン、配置、クロックツリー合成、グローバル配線に専門エージェントを置き、Judgeエージェントが履歴と工程別の結果から次の分岐点を選ぶ。毎試行で全工程を再実行する平坦なパラメータ探索と異なり、上流の良好な状態を保持して下流だけを再探索する。探索中はpost-GRのWNSを使い、最終候補を詳細配線後の指標で比較する。

## 検証の内容と結果

- AES-128、ibex、JPEGの3設計をSKY130HDとASAP7の2技術で評価（6組合せ）。
- 著者の比較対象であるOpenROAD、AutoTuner、ORFS-Agentに対して、6条件すべてで最良WNSを報告。JPEG/ASAP7ではpost-route WNS +50.6 psで、AutoTunerの-10.0 ps、ORFS-Agentの+0.3 psを上回る。
- タイミングが主目的。面積・電力は副次指標として確認する。
- 出典: [原著の方法・実験](https://arxiv.org/html/2607.04758)。

## 実務への示唆と限界

EDAフローの工程状態を再利用し、各判断に実行結果を残す設計が参考になる。一方、評価は公開フローと3設計に限定される。別ツール、より大規模な設計、別の制約条件や実製造への優位性は未確認。PDK開発そのものを評価した論文ではない。

## 確認したい次の証拠

大規模デザイン、異なる物理設計フロー、実行費用の厳密比較、電力・面積を主目的にした場合の結果。
