# はじめに（このリポジトリの使い方）

## 読み方
1. **サービス全体像（DOC-01）** で全体像を掴む  
2. **カリキュラム体系（DOC-02）→ DAG（DOC-03）→ リンク・マトリクス（DOC-04）** の順で“つながり”を理解  
3. ロールに応じて **モジュールカード（DOC-05）** と **評価（DOC-06）** を参照

## 編集のしかた（最小ルール）
- **Frontmatter必須**：id/title/version/status/owner/audience/last_updated/upstream/downstream
- **日本語ファイル名OK／ディレクトリは英数字**（自動化・CIのため）
- **相互リンク**：本文末尾に「上流/下流」を明記
- 変更は PR で、**`docs/DOC-INDEX.md` を更新**する

## 品質チェック（出す前に）
- 見出しは H2 から開始、箇条書きは “—” でなく “-”  
- Mermaid は `docs/03_course-dag/dag.mmd` を参照（高互換版を使用）  
- CSV は UTF‑8 / 改行 LF / ヘッダ行あり

## チェックリスト
- [ ] Frontmatter を入れた  
- [ ] 索引（DOC-INDEX）を更新した  
- [ ] 上流/下流のリンクを貼った  
- [ ] 用語を **DOC-20 用語集** に追加/確認した
