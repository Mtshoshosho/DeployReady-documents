---
id: DOC-04
title: リンクマトリクス
version: 1.0.0
status: Draft
owner: Curriculum Team
audience: 教育設計
upstream: [DOC-02, DOC-03]
downstream: [DOC-05, DOC-06, DOC-09]
last_updated: 2025-09-24
tags: [教育設計, 依存関係]
---

## 1. 目的と使い方
- 各モジュール（`module_id`）について、**前提条件・共有テンプレート・演習・評価・関連ドキュメント**を一覧管理する。
- コースDAG（DOC-03）を補完し、モジュールカード（DOC-05）とルーブリック（DOC-06）の更新漏れを防ぐ。
- 運営/講師/営業が、特定モジュールに紐づくテンプレートや証跡を即座に把握できるようにする。

## 2. マトリクス仕様（列定義）
| 列名 | 説明 | 記法ルール |
|------|------|------------|
| `module_id` | DAG（DOC-03）と一致するモジュールID | `A2`, `D3` など。Capstoneは `XOPS` 等 |
| `title` | モジュール名称（日本語） | DOC-05 と一致させる |
| `prereqs` | 事前に修了すべきモジュールID | `;` 区切り。DAGの入辺と整合を取る |
| `shared_templates` | 参照するテンプレート/ドキュメント | `テンプレ名.md` 等を `;` 区切りで列挙 |
| `shared_exercises` | 代表的な演習や成果物 | 箇条書きの代わりに `;` 区切りの短文 |
| `assessment_refs` | 評価基準・試験 | ルーブリックID、実技名など。`R-OPS-CLI` 等 |
| `upstream_docs` | 上流で参照するドキュメントID | `DOC-02;DOC-03` のように `;` 区切り |
| `downstream_docs` | モジュールが影響する下流ドキュメント | DOC ID またはフォルダ相対パスを `;` 区切り |

> CSV は UTF-8 / 改行 LF / 先頭行ヘッダ必須。フォーマットは `.gitattributes` で管理。

## 3. 本体（`link-matrix.csv`）
- ファイル：`docs/04_link-matrix/link-matrix.csv`
- 現在、優先度の高い **6 モジュール（A2/A3/A4/D3/O2/Q3）** を登録済み。
- 例：

```csv
module_id,title,prereqs,shared_templates,shared_exercises,assessment_refs,upstream_docs,downstream_docs
A2,CLIとLogs,"A1","Runbook_テンプレート.md;一次報告_テンプレート.md","5xx抽出CSV;journalctl期間絞り;cron化","R-OPS-CLI;実技30分OPS","DOC-02;DOC-03","DOC-05;DOC-06;DOC-11"
```

- 追加時は `module_id` の昇順で並べる（トラック単位でまとまる）。

## 4. 抜け漏れ検知ルール（孤立/重複）
1. **DAG整合**：`prereqs` に書いた ID は、必ず DAG（DOC-03）の入辺と一致させる。逆に、DAG に存在する入辺がマトリクスに欠けていないか点検する。
2. **テンプレ整合**：`shared_templates` に記載したファイルは、`docs/15_templates/` 内に存在するかチェックする。
3. **評価整合**：`assessment_refs` は、DOC-06 ルーブリックや実技試験名と一致させる。追加・改称時は双方を同時更新する。
4. **重複禁止**：`module_id` は一意。重複行があれば削除またはマージ。
5. **孤立検知**：
   - `prereqs` が空であることは問題ないが、**DAG 上で入辺があるのに `prereqs` が空**であれば確認。
   - `downstream_docs` に DOC ID が一つも無い場合は、「どのドキュメントで利用されるか」を確認し、最低限 `DOC-05` を入れる。
6. **自動チェック**（任意）：「DAG 検証スクリプト（`tools/validate_dag.py`）」に加え、以下のワンライナーでヘッダ漏れを検知できる。

```bash
python - <<'PY'
import csv
required={'module_id','title','prereqs','shared_templates','shared_exercises','assessment_refs','upstream_docs','downstream_docs'}
with open('docs/04_link-matrix/link-matrix.csv', newline='', encoding='utf-8') as f:
    header=set(next(csv.reader(f)))
missing=required-header
if missing:
    raise SystemExit(f"ERROR: missing columns {missing}")
print("OK: header complete")
PY
```

## 5. 更新履歴
| 日付 | 変更者 | 概要 |
|------|--------|------|
| 2025-09-24 | Curriculum Team | 優先6モジュール（A2/A3/A4/D3/O2/Q3）のテンプレ/評価/上下流リンクを登録 |

---
**上流**：[DOC-02](../02_product-curriculum/DOC-02_プロダクトとカリキュラム体系_v1.0.md), [DOC-03](../03_course-dag/DOC-03_コースDAG_依存関係図_v1.0.md)  
**下流**：[DOC-05](../05_module-cards/README.md), [DOC-06](../06_assessment-rubric/DOC-06_評価とルーブリック_v1.0.md), [DOC-09](../09_delivery-ops/DOC-09_デリバリー運用_v1.0.md)
