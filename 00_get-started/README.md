# はじめに（このリポジトリの使い方）

## 読み方
1. **サービス全体像（[DOC-01](../01_service-overview/DOC-01_サービス全体像_v1.0.md)）** で全体像を掴む  
2. **カリキュラム体系（[DOC-02](../02_product-curriculum/DOC-02_プロダクトとカリキュラム体系_v1.0.md)） → DAG（[DOC-03](../03_course-dag/DOC-03_コースDAG_依存関係図_v1.0.md)） → リンク・マトリクス（[DOC-04](../04_link-matrix/DOC-04_リンクマトリクス_v1.0.md)）** の順で“つながり”を理解  
3. ロール別に **モジュールカード（[DOC-05](../05_module-cards/README.md)）** と **評価（[DOC-06](../06_assessment-rubric/DOC-06_評価とルーブリック_v1.0.md)）** を参照

## 編集のしかた（最小ルール）
- **Frontmatter必須**：id/title/version/status/owner/audience/last_updated/upstream/downstream
- **日本語ファイル名OK／ディレクトリは英数字**（自動化・CIのため）
- **相互リンク**：本文末尾に「上流/下流」を明記
- 変更は PR で、**`DOC-INDEX.md` を更新**する

## 品質チェック（出す前に）
- 見出しは H2 から開始、箇条書きは `-`  
- Mermaid は `03_course-dag/dag.mmd` を参照（高互換版）  
- CSV は UTF‑8 / 改行 LF / ヘッダ行あり

## チェックリスト
- [ ] Frontmatter を入れた  
- [ ] 索引（DOC-INDEX）を更新した  
- [ ] 上流/下流のリンクを貼った  
- [ ] 用語を **[DOC-20](../20_glossary/DOC-20_用語集_v1.0.md) 用語集** に追加/確認した
