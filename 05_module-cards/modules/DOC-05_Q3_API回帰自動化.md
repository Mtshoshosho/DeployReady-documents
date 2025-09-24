---
id: DOC-05-Q3
title: Q3 API回帰自動化
version: 1.0.0
status: Draft
owner: 教育設計
audience: 受講者, 講師
upstream: [DOC-02, DOC-03]
downstream: [DOC-06, DOC-11]
last_updated: 2025-09-24
tags: [QA, 自動テスト]
---

## 概要（対象/時間/前提）
- **対象**：QA/テストエンジニア、開発支援メンバー
- **時間**：9h（講義2h / ハンズオン4h / CI連携2h / ふりかえり1h）
- **前提**：Q1 テスト設計、Q2 欠陥票/証跡、A3 Git、A7 AIガイド

## Learning Outcomes（測定可能動詞で3–5）
1. Newman/Postman コレクションを **回帰テストスイート化**し、タグ/環境変数ごとに実行できる。
2. GitHub Actions で **スケジュール実行と成果物保管**を自動化できる。
3. 失敗ケースを欠陥票テンプレートに整理し、**証跡リンク（ログ/動画）**を添付できる。
4. API 回帰の結果を営業/運営へ共有し、**再実行条件や優先度**を説明できる。

## 演習（3本：L1/L2/L3）
- **L1**：既存API仕様からテストケースを抽出し、Postman コレクションにタグ付け。
- **L2**：`newman run` を GitHub Actions に組み込み、JUnit 形式レポートをアーティファクトに保存。
- **L3**：失敗レポートから欠陥票を作成し、再現手順と映像キャプチャを `欠陥票_テンプレート.md` に添付。

## 成果物（提出物と受け入れ基準）
- Postman コレクション (`*.json`) と環境ファイル。
- GitHub Actions 定義（`ci-regression.yml`）＋ 成果物レポート（JUnit/HTML）。
- 欠陥票（テンプレを利用し、再現条件・期待値・証跡URLを記入）。

## 評価（配点/ルーブリック参照）
- 実技 30点（ケース網羅性、CI 実行、レポート整合）
- 文書 10点（欠陥票・Runbook連携）
- プレゼン 5点（結果共有と次アクションの妥当性）
- 評価基準：`実技30分QA`、`R-DEV-CRUD` の CI 項目を準用。

## リスクと想定Q&A
- **リスク**：API変更によるテスト崩壊 → **対策**：`link-matrix.csv` の `downstream_docs` に営業資料/DOC-12 を紐付け、変更通知を受ける。
- **Q**：Newman レポートの日本語化は？ → **A**：`newman-reporter-htmlextra` を導入し、`--reporter-htmlextra-browserTitle` など設定例を配布。
- **Q**：シークレット情報の扱い → **A**：GitHub Actions の Encrypted Secrets を利用し、`README` に管理手順を記載。

---
**上流**：[DOC-02](../../02_product-curriculum/DOC-02_プロダクトとカリキュラム体系_v1.0.md), [DOC-03](../../03_course-dag/DOC-03_コースDAG_依存関係図_v1.0.md)  
**下流**：[DOC-06](../../06_assessment-rubric/DOC-06_評価とルーブリック_v1.0.md), [DOC-11](../../11_poc-pack/DOC-11_PoCパック_v1.0.md)
