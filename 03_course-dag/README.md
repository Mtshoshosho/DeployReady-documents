# コースDAG（依存関係管理）

**目的**：モジュール間の依存関係を単一の真実源で管理し、開発・運営の整合を取る
**主要ファイル**：  
- DOC-03_コースDAG_依存関係図_v1.0.md  
- dag.mmd（Mermaid DAG）  
- nodes.csv／edges.csv（データソース）

**上流（Upstream）**：DOC-02
**下流（Downstream）**：DOC-04, DOC-05, DOC-06

**更新手順**：
1. 新規モジュールや依存変更を Issue で定義
2. CSV を更新し、Mermaid（dag.mmd）を再生成
3. 本文 Frontmatter を更新し、`../DOC-INDEX.md` を反映
4. リンクマトリクス・モジュールカードに影響有無を通知

**チェックリスト**：
- [ ] 見出し構造（H2開始）  
- [ ] 上流/下流リンクが有効  
- [ ] 用語は DOC-20 と一致  
- [ ] CSV と Mermaid の整合が取れている
