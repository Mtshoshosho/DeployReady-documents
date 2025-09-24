# KPIとレポーティング（経営ダッシュボード）

**目的**：学習・事業KPIを一元管理し、意思決定を迅速化する
**主要ファイル**：  
- DOC-07_KPIとレポーティング_v1.0.md  
- dashboards/（ダッシュボード仕様・エクスポート）

**上流（Upstream）**：[DOC-06](../06_assessment-rubric/DOC-06_評価とルーブリック_v1.0.md), [DOC-18](../18_data-schema/DOC-18_データスキーマ_v1.0.yaml), [DOC-19](../19_readiness-index/DOC-19_ReadinessIndex仕様_v1.0.md)
**下流（Downstream）**：経営報告資料、営業資料（[DOC-12](../12_gtm/DOC-12_GTM_営業資料_v1.0.md)）

**更新手順**：
1. KPI 定義変更を Issue で整理し承認を得る
2. 本文とダッシュボード仕様を更新、Frontmatter を調整
3. `../DOC-INDEX.md` を更新し関係者へ通知
4. レポート出力フローや自動化スクリプトを確認

**チェックリスト**：
- [ ] 見出し構造（H2開始）  
- [ ] 上流/下流リンクが有効  
- [ ] 用語は [DOC-20](../20_glossary/DOC-20_用語集_v1.0.md) と一致  
- [ ] ダッシュボードと CSV 定義が同期
