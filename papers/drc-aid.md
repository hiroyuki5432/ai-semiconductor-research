# DRC-Aid

## 文献情報

- 正式題名: *DRC-Aid: Design-Rule Correction via Agentic Framework utilizing Inference-Time Large Language Models*
- 著者: Anushka Mukherjee, Kang He, Kaushik Roy
- 所属: Purdue University
- 発表: arXiv:2607.22761 v1、2026-07-23。査読採録は未確認。
- 一次資料: [原著概要](https://arxiv.org/abs/2607.22761)、[原著本文](https://arxiv.org/html/2607.22761v1)

## 1行のエッセンス

決定的なルールエンジンが許可した形状修正だけをLLMが選び、DRCとLVSの結果で採否を決める局所修復。

## 技術的な差分と新規性

物理検証ツールが報告した違反からルールエンジンが有限個の幾何編集を作る。LLMは局所文脈に応じて候補を選択する役割に限定される。予算付き深さ優先探索、巻き戻し、探索済み状態を覚えるMemory Bankを備え、Calibre nmDRC/nmLVSで修正後のルール適合と電気的等価性を確認する。自由形式のコード/形状生成をそのまま採用しない構成が実務に近い。

## 検証の内容と結果

- FreePDK45のDRC違反を含むレイアウトを評価。
- 著者報告: 約92.5%のケースでDRC-cleanかつLVS-equivalent。総違反数は約98%減少。
- 同じ探索・検証基盤の比較では、LLMによる選択の完全修正率が、ランダム54.4%、決定的ヒューリスティック83.3%を上回る。
- 出典: [原著の概要・実験](https://arxiv.org/html/2607.22761v1)。

## 実務への示唆と限界

人間が許可した操作集合、DRC/LVS再実行、失敗時の巻き戻しを持つ試行設計は参考になる。対象は公開45 nm PDKの局所レイアウトであり、商用PDK、全チップ、密な配線、タイミング・寄生・歩留まり影響まで保証したものではない。DRC-cleanだけで設計採用可とはしない。

## 確認したい次の証拠

ルール種別ごとの成功率、ケース数と複雑度、修正前後のPPA/寄生、別PDK・別ツールでの再現。
