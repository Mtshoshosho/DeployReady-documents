---
id: DOC-05-D3
title: D3 Backend基礎 (TS+Express)
version: 1.0.0
status: Draft
owner: 教育設計
audience: 受講者, 講師
upstream: [DOC-02, DOC-03]
downstream: [DOC-05, DOC-06, DOC-11]
last_updated: 2025-09-24
tags: [バックエンド]
---

## 概要（対象/時間/前提）
- **対象**：Web/API 開発にアサイン予定の初級エンジニア
- **時間**：10h（講義2h / ハンズオン5h / レビュー1h / 補講2h）
- **前提**：D1 HTTP/REST, D2 Front 基礎, A3 Git, A7 AIガイド

## Learning Outcomes（測定可能動詞で3–5）
1. Express + TypeScript で **CRUD API と例外ハンドリング**を実装できる。
2. `pino` 等のライブラリで **構造化ログ**を出力し、A2 のログ整形と連携できる。
3. `jest` / `supertest` を用いた **API テスト**を CI に組み込み、自動化できる。
4. `.env` と Secrets 管理方針を守り、**認証（JWT/Cookie）**の最小実装を説明できる。

## 演習（3本：L1/L2/L3）
- **L1**：`/customers` CRUD + バリデーション（`zod`）+ 例外レスポンス統一。
- **L2**：`/metrics` API に **構造化ログ**を追加し、`log_digest.sh` と連携して可観測性を高める。
- **L3**：`GitHub Actions` で `npm test` + `newman run` を実行し、成果物をアーティファクトとして保存。

## 成果物（提出物と受け入れ基準）
- GitHub リポジトリ（README に環境構築/テスト手順を明記）。
- Postman コレクション + 環境ファイル（CI で実行可能な形式）。
- `observability_notes.md`（ログ・メトリクスの確認ポイント、および Runbook 連携案）。

## 評価（配点/ルーブリック参照）
- 実技 35点（CRUD 完成度、例外処理、ログ/テスト連携）
- 文書 10点（README/Runbook連携、Secrets 取り扱い）
- 口頭試問 5点（APIセキュリティ/スケール戦略）
- 評価基準：`R-DEV-CRUD`, `実技30分DEV` を参照。

## リスクと想定Q&A
- **リスク**：TypeScript 型崩れ → **対策**：`tsconfig` と ESLint 設定をテンプレとして提供。
- **Q**：DB は使わない？ → **A**：本モジュールではインメモリまたは SQLite を使用し、D4 SQL と接続する演習はキャップストーンで扱う。
- **Q**：CI の失敗ログが読みづらい → **A**：`console.log` 禁止、`pino-pretty` の使い方を事前共有。

---
**上流**：[DOC-02](../../02_product-curriculum/DOC-02_プロダクトとカリキュラム体系_v1.0.md), [DOC-03](../../03_course-dag/DOC-03_コースDAG_依存関係図_v1.0.md)  
**下流**：[DOC-05](../README.md), [DOC-06](../../06_assessment-rubric/DOC-06_評価とルーブリック_v1.0.md), [DOC-11](../../11_poc-pack/DOC-11_PoCパック_v1.0.md)
