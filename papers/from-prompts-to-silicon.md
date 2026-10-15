# From Prompts to Silicon

## 文献情報

- 正式題名: *From Prompts to Silicon: Scaling LLM-Assisted Chip Design with the AI Hardware Design League*
- 著者: Parsa Mirfasihi, Harish Kumar Dharavath, Muhtasim Alam Chowdhury, Sujan Ghimire, Banafsheh Saber Latibari, Rozhin Yasaei, Pratik Satam, Soheil Salehi
- 所属: University of Arizona（電気・計算・ソフトウェア工学、情報科学）
- 発表: arXiv:2610.18891 v1、2026-10-09。査読採録は未確認。
- 一次資料: [原著概要](https://arxiv.org/abs/2610.18891)、[原著本文](https://arxiv.org/html/2610.18891v1)

## 1行のエッセンス

LLMを使う学生のデジタル設計を、Verilog生成からEDA検証・製造提出まで段階的に運用した教育実証。

## 技術的な差分と新規性

主題は新しい生成アルゴリズムではなく、参加規模、教育過程、設計の到達度である。LLMでVerilogを生成・修正し、シミュレーション、合成、タイミング解析、セキュリティレビュー、物理検証からのフィードバックを設計者に返す。生成結果をEDA検証に通す学習フローを、複数年度・多数の参加者に展開した点に価値がある。

## 検証の内容と結果

- 2年間で参加者は172人から604人、チームは40から108へ増加。2026年の参加者の68.7%はVerilog未経験と回答。
- 2026年には22チームが4段階を完了。部門優勝の2設計がSky130でDRC/LVSの違反0件を達成し、製造に提出された。
- **製造提出と実チップの製造完了・動作確認は異なる。** 論文の到達点は提出までとして記録する。
- 出典: [原著概要・本文](https://arxiv.org/abs/2610.18891)。

## 実務への示唆と限界

初心者にAI支援を渡す場合も、段階ごとの合格条件とツールによる検証が必要という教育設計の参考になる。最終段階に達したのは一部チームであり、参加者数だけを設計成功数として解釈できない。PDK開発ツールの自動化性能を直接評価した論文ではない。

## 確認したい次の証拠

製造後のシリコン測定、参加者の技能変化を測る比較、途中離脱の要因、公開設計の再実行結果。
