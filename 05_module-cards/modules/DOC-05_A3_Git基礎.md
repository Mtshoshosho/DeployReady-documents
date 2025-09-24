---
id: DOC-05-A3
title: A3 Git基礎
version: 1.0.0
status: Draft
owner: 教育設計
audience: 受講者, 講師
upstream: [DOC-02, DOC-03]
downstream: [DOC-06, DOC-11, DOC-12]
last_updated: 2025-09-24
tags: [Git]
---

## 概要（対象/時間/前提）
- **対象**：開発/運用/QA いずれも Git を利用する初級者
- **時間**：6h（講義1.5h / デモ1h / ラボ3h / ふりかえり0.5h）
- **前提**：A1 ITSMライト、A2 CLIとLogs

## Learning Outcomes（測定可能動詞で3–5）
1. `git clone/branch/checkout` を用いて **安全にブランチ運用**ができる。
2. `git status/diff/log` を活用し、**変更差分と履歴の可視化**ができる。
3. `git commit --signoff` と Pull Request を通じて **レビューに耐える提出物**を用意できる。
4. リモートとローカルの衝突を解消し、**リベース or マージ方針**を説明できる。

## 演習（3本：L1/L2/L3）
- **L1**：`feature/日報テンプレ` ブランチ作成 → コミットメッセージ規約で push。
- **L2**：意図的に競合を発生させ、`git rebase` と `git mergetool` で解消。
- **L3**：Pull Request 作成 → テンプレートに沿って説明 → レビューコメントを反映。

## 成果物（提出物と受け入れ基準）
- GitHub PR URL（`PR_テンプレート.md` 適用済み、説明欄に変更概要/テスト結果記載）。
- `CHANGELOG_snippet.md`（Before/Afterを3行以内で要約）。
- `git_log.txt`（`git log --oneline --decorate` 出力で履歴を証跡化）。

## 評価（配点/ルーブリック参照）
- 知識チェック 10点（基本コマンド/概念）
- 実技 20点（競合解消・レビュー反映）
- 文書 10点（PR説明・Changelogの品質）
- 評価基準：`R-DEV-CRUD`、レビュー品質チェックリストに準拠。

## リスクと想定Q&A
- **リスク**：競合解消で履歴を壊す → **対策**：ラボ前に `git reflog` で戻せる手順を確認。
- **Q**：`git pull` と `git fetch` の違いは？ → **A**：`fetch` は差分取得のみ、`pull` は merge/rebase を含む。講義内でデモ。
- **Q**：PR テンプレが英語表記だが？ → **A**：テンプレ内に定型文サンプルを用意し、`PR_テンプレート.md` を併用する。

---
**上流**：[DOC-02](../../02_product-curriculum/DOC-02_プロダクトとカリキュラム体系_v1.0.md), [DOC-03](../../03_course-dag/DOC-03_コースDAG_依存関係図_v1.0.md)  
**下流**：[DOC-06](../../06_assessment-rubric/DOC-06_評価とルーブリック_v1.0.md), [DOC-11](../../11_poc-pack/DOC-11_PoCパック_v1.0.md), [DOC-12](../../12_gtm/DOC-12_GTM_営業資料_v1.0.md)
