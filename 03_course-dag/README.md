# コースDAG（依存関係管理）

**目的**：モジュール間の依存関係を単一の真実源で管理し、開発・運営の整合を取る
**主要ファイル**：  
- DOC-03_コースDAG_依存関係図_v1.0.md  
- dag.mmd（Mermaid DAG）  
- nodes.csv／edges.csv（データソース）

**上流（Upstream）**：[DOC-02](../02_product-curriculum/DOC-02_プロダクトとカリキュラム体系_v1.0.md)
**下流（Downstream）**：[DOC-04](../04_link-matrix/DOC-04_リンクマトリクス_v1.0.md), [DOC-05](../05_module-cards/README.md), [DOC-06](../06_assessment-rubric/DOC-06_評価とルーブリック_v1.0.md)

**更新手順**：
1. 新規モジュールや依存変更を Issue で定義
2. CSV を更新し、Mermaid（dag.mmd）を再生成
3. 本文 Frontmatter を更新し、`../DOC-INDEX.md` を反映
4. リンクマトリクス・モジュールカードに影響有無を通知

**チェックリスト**：
- [ ] 見出し構造（H2開始）  
- [ ] 上流/下流リンクが有効  
- [ ] 用語は [DOC-20](../20_glossary/DOC-20_用語集_v1.0.md) と一致  
- [ ] CSV と Mermaid の整合が取れている
