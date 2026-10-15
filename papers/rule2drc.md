# Rule2DRC

## 文献情報

- 正式題名: *Rule2DRC: Benchmarking LLM Agents for DRC Script Synthesis with Execution-Guided Test Generation*
- 著者: Jinuk Kim, Junsoo Byun, Donghwi Hwang, Seong-Jin Park, Hyun Oh Song
- 所属: Seoul National University（Kim、Byun、Song）、Samsung Electronics（Hwang、Park）
- 発表: ICML 2026、PMLR 306、57197–57224
- 一次資料: [PMLR原著](https://proceedings.mlr.press/v306/kim26d.html)、[著者の解説・所属](https://jinukkim.me/blog/rule2drc/)、[公開コード](https://github.com/snu-mllab/Rule2DRC)

## 1行のエッセンス

自然言語の設計ルールから生成したDRCスクリプトを、見た目のコード類似ではなく、レイアウト上の実行結果で評価する。

## 技術的な差分と新規性

1,000件のルール→スクリプト課題と13,921件の評価レイアウトを提供する。モデルが評価レイアウトのラベルを入力として使わない条件で、KLayout Ruby DRCスクリプトの結果を正解と比較する。SplitTesterは複数の候補スクリプトが同じ振る舞いを示す場合、候補を分離できるテストレイアウトを生成してBest-of-Nの選択を改善する。

課題はSkyWater由来310件、人工的な複合制約490件、構文カバレッジ200件。後二者を実工場ルールの代表サンプルと同一視しない。

## 検証の内容と結果

- 公開GDSレイアウト、KLayoutエンジン、複数LLMによる評価。
- 著者の例: 20候補でGPT-OSS-20BはSplitTester 44.4%対比較手法41.1%、GPT-OSS-120Bは63.8%対62.7%。文書を文脈に含める効果も大きいと報告。
- 成功率は**ベンチマーク課題の機能的一致率**。デッキ全体のサインオフ品質ではない。
- 出典: [PMLR原著](https://proceedings.mlr.press/v306/kim26d.html)、[著者の評価説明](https://jinukkim.me/blog/rule2drc/)。

## 実務への示唆と限界

PDK/DRM業務では、既存の正解デッキと境界条件を狙うレイアウトを使い、誤判定を実行ベースで検出する枠組みが参考になる。ただし論文の対象言語はKLayout Rubyであり、SVRF生成の品質保証を実証したものではない。商用PDKの機密・ライセンス・ルール複雑度も別に検討する必要がある。

## 確認したい次の証拠

SVRF等への移植、実ルールでの評価、偽陰性の分析、複雑な多層ルールのカバレッジ、人間レビューの工数。
