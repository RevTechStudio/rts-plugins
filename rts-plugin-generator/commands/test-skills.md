---
name: test-skills
description: 各スキルに対して単体テストを実施する
---

# Test Skills

## 概要

このコマンドは、ユーザーが選択したスキルに対して単体テストを実施する。テストケースを基に各スキルを自動実行し、期待される動作を検証して、結果をレポートとして出力する。

## 使用するエージェント

- **plugin-development-agent:** プラグイン要素の作成全体を管理し、ユーザーと対話しながら要素を設計・生成する

## 使用するスキル

1. **plugin-validator:** 生成したプラグイン全体の整合性・完全性を検証する
2. **element-relationship-analyzer:** プラグイン要素間の依存関係や呼び出し順序を分析する
3. **documentation-standards:** Markdownドキュメントの記述標準に従う
4. **interaction-guidelines:** ユーザーとの効果的な対話パターンに従う
5. **plugin-architecture-convention:** プラグイン全体のアーキテクチャ設計原則に従う

## 実行フロー

1. plugin-development-agentが以下のスキルを使用して、テスト対象のスキルを特定する
   - plugin-architecture-convention（アーキテクチャ規約遵守）
   - interaction-guidelines（対話パターン）

2. plugin-development-agentが以下のスキルを使用して、各スキルのテストケースを確認する
   - plugin-validator（テストケース確認）

3. plugin-development-agentが以下のスキルを使用して、スキルの依存関係を確認する
   - element-relationship-analyzer（依存関係分析）

4. plugin-development-agentが各スキルに対して自動テストを実行する
   - テストケースに基づいた入力データの準備
   - スキルの実行
   - 出力結果の検証
   - 期待される動作との比較

5. plugin-development-agentが以下のスキルを使用して、テスト結果をレポートとして出力する
   - documentation-standards（記述標準遵守）

6. plugin-development-agentがテスト失敗の詳細を分析し、修正提案を提供する

## 成果物

**出力先:**

- `[プラグインディレクトリ]/test-results/[実行日時]-test-report.md`

**ファイル内容:**

- テスト実行日時
- テスト対象スキル一覧
- 各スキルのテスト結果（成功・失敗・スキップ）
- 失敗したテストの詳細
- テストカバレッジ情報
- 修正提案

## チェックリスト

### コマンド実行前

- [ ] テスト対象のスキルが明確である
- [ ] 各スキルのテストケースが準備されている
- [ ] スキル間の依存関係が整理されている

### コマンド実行後

- [ ] テストレポートが生成されている
- [ ] 全てのテスト対象スキルが実行されている
- [ ] テスト結果が明確に記録されている
- [ ] 失敗したテストの詳細が記述されている
- [ ] 修正提案が提供されている
- [ ] プラグインアーキテクチャ規約が遵守されている
- [ ] markdownlint検証に合格している
- [ ] 他の要素を参照していない
- [ ] 固有名詞が使用されていない
