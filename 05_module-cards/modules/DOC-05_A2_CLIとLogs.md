---
id: DOC-05-A2
title: A2 CLIとLogs（8h）
version: 1.0.0
status: Draft
owner: 教育設計
audience: 受講者, 講師
last_updated: 2025-09-23
upstream: [DOC-02, DOC-03, DOC-04]
downstream: [DOC-06, DOC-11]
---

## 概要
- **目的**：ログから現象を素早く抽出・整形・集計し、一次報告/Runbookに反映できるようにする
- **時間**：8h（講義2h / デモ1h / ラボ4h / ふりかえり1h）
- **前提**：A1 ITSMライト

## Learning Outcomes（測定可能）
1. `grep/find/tail/journalctl` で **事象別ログ抽出** ができる  
2. 抽出→整形→集計→**CSV化を1コマンド**で実行できる  
3. 期間/ユニット/優先度などの **可変パラメータ化** ができる  
4. **一次報告テンプレ**と**Runbook**に再現手順を反映できる

## ラボ課題
- **L1**：5xxログの抽出と **Top3エンドポイント** をCSV出力  
- **L2**：`journalctl -u <unit> --since --until` で **期間/ユニット** 絞り込み  
- **L3**：`cron` で **日次バッチ化**（リトライ/ログローテ含む）

## 成果物
- `log_digest.sh`（`--since/--until/--unit` などの引数対応）  
- `result.csv`（ヘッダ: `endpoint,count,date`）  
- `runbook_snippet.md`（実行手順・前提条件・想定出力）

## 評価（配点）
- 実技 20（正確性/再現性/引数化/可読性）
- 文書 10（テンプレ準拠/分岐明確/責任者明記）

## リスクと想定Q&A
- **リスク**：巨大ログでの性能劣化 → **対策**：先頭N件/`--since` で範囲限定、`awk` 集計
- **Q**：権限不足で読めない → **A**：`sudo journalctl` と対象ユニットの権限をRunbookに明記
