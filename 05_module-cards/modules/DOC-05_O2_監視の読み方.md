---
id: DOC-05-O2
title: O2 監視/可観測性の読み方
version: 1.0.0
status: Draft
owner: 教育設計
audience: 受講者, 講師
upstream: [DOC-02, DOC-03]
downstream: [DOC-06, DOC-11, DOC-07]
last_updated: 2025-09-24
tags: [監視]
---

## 概要（対象/時間/前提）
- **対象**：Ops/SRE 初級、監視担当、CS の一次対応
- **時間**：8h（講義2h / ダッシュボード演習3h / Runbook演習2h / 口頭試問1h）
- **前提**：O1 Linux 運用、A6 Office自動化ミニ、A7 AIガイド

## Learning Outcomes（測定可能動詞で3–5）
1. Grafana/Datadog などのダッシュボードを読み、**異常兆候を検知して要因仮説**を立てられる。
2. `threshold_table_template.csv` を更新し、**KPI/メトリクスのしきい値**を定義できる。
3. Runbook テンプレートを使って **アラート受信→一次対応→エスカレーション**までを記録できる。
4. アラートの優先度に応じて **エスカレーション SLA** を説明できる。

## 演習（3本：L1/L2/L3）
- **L1**：CPU/メモリ/HTTP 監視のライブダッシュボードから異常箇所を指摘し、一次報告にまとめる。
- **L2**：`threshold_table_template.csv` に KPI を追記し、警告/クリティカルの基準と対応手順を定義。
- **L3**：模擬アラート（ログ/メトリクス）に基づき、Runbook と一次報告を更新し、改善点をチームへプレゼン。

## 成果物（提出物と受け入れ基準）
- 更新済み `threshold_table_template.csv`（3指標以上、Owner/エスカレーションまで記入）。
- `Runbook_テンプレート.md` を利用した Incident Runbook（事象・検知・一次対応・復旧条件）。
- `alert_review_record.md`（アラートごとの学びと次回改善アクション）。

## 評価（配点/ルーブリック参照）
- 実技 25点（ダッシュボード解釈・閾値設定）
- 文書 10点（Runbook、報告書の網羅性）
- チーム発表 5点（改善提案の妥当性）
- 評価基準：`R-OPS-MON`、`実技30分OPS` を参照。

## リスクと想定Q&A
- **リスク**：監視ツール差異で迷う → **対策**：共通UIのスナップショットとクイックリファレンスを教材化。
- **Q**：閾値決定の根拠が不明 → **A**：KPI（DOC-07）と連携し、過去値/ビジネスインパクトを基準に定義する。
- **Q**：Runbook 更新が追いつかない → **A**：TODO（DOC-11）に「Runbook振り返り」を入れ、週次でレビュー。

---
**上流**：[DOC-02](../../02_product-curriculum/DOC-02_プロダクトとカリキュラム体系_v1.0.md), [DOC-03](../../03_course-dag/DOC-03_コースDAG_依存関係図_v1.0.md)  
**下流**：[DOC-06](../../06_assessment-rubric/DOC-06_評価とルーブリック_v1.0.md), [DOC-07](../../07_kpi-reporting/DOC-07_KPIとレポーティング_v1.0.md), [DOC-11](../../11_poc-pack/DOC-11_PoCパック_v1.0.md)
