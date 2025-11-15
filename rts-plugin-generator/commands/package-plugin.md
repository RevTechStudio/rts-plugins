---
name: package-plugin
description: プラグインのリリース準備を実施する
---

# Package Plugin

## 概要

このコマンドは、プラグインのリリース準備を実施する。プラグイン全体の検証を行い、ドキュメントとの整合性を確認・修正し、plugin.jsonのバージョンを更新する。リポジトリ自体がパッケージとして機能するため、ZIP化は行わない。

## 使用するエージェント

- **plugin-development-agent:** プラグイン要素の作成全体を管理し、ユーザーと対話しながら要素を設計・生成する

## 使用するスキル

1. **plugin-validator:** 生成したプラグイン全体の整合性・完全性を検証する
2. **element-relationship-analyzer:** プラグイン要素間の依存関係や呼び出し順序を分析する
3. **documentation-standards:** Markdownドキュメントの記述標準に従う
4. **interaction-guidelines:** ユーザーとの効果的な対話パターンに従う
5. **plugin-architecture-convention:** プラグイン全体のアーキテクチャ設計原則に従う

## 実行フロー

1. plugin-development-agentが以下のスキルを使用して、プラグイン全体の検証を実施する
   - plugin-validator（整合性・完全性検証）
   - plugin-architecture-convention（アーキテクチャ規約遵守）

2. plugin-development-agentが以下のスキルを使用して、プラグイン要素間の依存関係を確認する
   - element-relationship-analyzer（依存関係分析）

3. plugin-development-agentが以下のスキルを使用して、ドキュメントとの整合性を確認する
   - documentation-standards（記述標準遵守）
   - plugin-validator（ドキュメント検証）

4. plugin-development-agentが以下のスキルを使用して、整合性の問題があれば修正を提案・実施する
   - interaction-guidelines（対話パターン）
   - documentation-standards（記述標準遵守）

5. plugin-development-agentがplugin.jsonのバージョン更新を実施する
   - 現在のバージョンを確認する
   - 新しいバージョン番号をユーザーに確認する
   - plugin.jsonを更新する

6. plugin-development-agentが以下のスキルを使用して、最終確認を実施する
   - plugin-validator（最終検証）
   - documentation-standards（ドキュメント最終確認）

7. plugin-development-agentがリリース準備完了レポートを出力する

## 成果物

**出力先:**

- `plugin.json`（更新済み）
- `[プラグインディレクトリ]/README.md`（必要に応じて更新）
- `[プラグインディレクトリ]/release-report.md`

**ファイル内容:**

- 更新されたplugin.json（新しいバージョン番号）
- 更新されたREADME（必要に応じて）
- リリース準備完了レポート（検証結果、整合性確認結果、バージョン情報）

## チェックリスト

### コマンド実行前

- [ ] プラグイン全体が完成している
- [ ] 全てのエージェント、スキル、コマンドが作成されている
- [ ] READMEが最新の状態である

### コマンド実行後

- [ ] プラグイン全体の検証が完了している
- [ ] プラグイン要素間の依存関係が確認されている
- [ ] ドキュメントとの整合性が確認されている
- [ ] 整合性の問題が修正されている
- [ ] plugin.jsonのバージョンが更新されている
- [ ] リリース準備完了レポートが生成されている
- [ ] プラグインアーキテクチャ規約が遵守されている
- [ ] markdownlint検証に合格している
- [ ] 他の要素を参照していない
- [ ] 固有名詞が使用されていない
