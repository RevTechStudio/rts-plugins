---
name: generate-plugin
description: 分析結果からプラグイン要素全体を生成し、ドキュメント化する
---

# Generate Plugin

## 概要

このコマンドは、ユーザーの業務領域や作業フローの分析結果から、プラグイン全体を構成する要素（エージェント、スキル、コマンド）を生成し、ドキュメント化する。既存の分析結果がある場合はそれを使用し、ない場合はユーザーとの対話を通じて分析を実施する。

## 使用するエージェント

- **plugin-development-agent:** プラグイン要素の作成全体を管理し、ユーザーと対話しながら要素を設計・生成する

## 使用するスキル

1. **domain-analyzer:** ユーザーの業務領域や目的を分析し、必要な機能を抽出する
2. **workflow-analyzer:** 作業フローや手順を分析し、自動化可能な要素を特定する
3. **responsibility-mapper:** 作業の責任範囲を整理し、エージェント定義に必要な情報を抽出する
4. **task-decomposer:** 複雑な作業を単一目的の小さなタスクに分解する
5. **agent-generator:** 責任範囲の定義からエージェント要素を生成する
6. **workflow-skill-generator:** 作業手順からワークフロースキルを生成する
7. **convention-skill-generator:** 規約・ガイドラインからコンベンションスキルを生成する
8. **command-generator:** エージェントとスキルの組み合わせからコマンドを生成する
9. **element-relationship-analyzer:** プラグイン要素間の依存関係や呼び出し順序を分析する
10. **plugin-validator:** 生成したプラグイン全体の整合性・完全性を検証する
11. **documentation-standards:** Markdownドキュメントの記述標準に従う
12. **interaction-guidelines:** ユーザーとの効果的な対話パターンに従う
13. **element-definition-convention:** プラグイン要素の定義ルールに従う
14. **plugin-architecture-convention:** プラグイン全体のアーキテクチャ設計原則に従う
15. **skill-granularity-convention:** スキルの適切な粒度を定義する

## 実行フロー

1. plugin-development-agentが以下のスキルを使用して、既存の分析結果を確認する
   - domain-analyzer（分析結果確認）
   - workflow-analyzer（分析結果確認）

2. plugin-development-agentが以下のスキルを使用して、分析が不足している場合はユーザーとの対話を通じて情報を収集する
   - domain-analyzer（業務領域分析）
   - workflow-analyzer（作業フロー分析）
   - interaction-guidelines（対話パターン）

3. plugin-development-agentが以下のスキルを使用して、エージェント要素を生成する
   - responsibility-mapper（責任範囲整理）
   - agent-generator（エージェント生成）
   - element-definition-convention（定義ルール遵守）

4. plugin-development-agentが以下のスキルを使用して、スキル要素を生成する
   - task-decomposer（タスク分解）
   - workflow-skill-generator（ワークフロースキル生成）
   - convention-skill-generator（コンベンションスキル生成）
   - skill-granularity-convention（粒度規約遵守）
   - element-definition-convention（定義ルール遵守）

5. plugin-development-agentが以下のスキルを使用して、コマンド要素を生成する
   - command-generator（コマンド生成）
   - element-definition-convention（定義ルール遵守）

6. plugin-development-agentが以下のスキルを使用して、プラグイン全体の整合性を検証する
   - element-relationship-analyzer（依存関係分析）
   - plugin-validator（整合性検証）
   - plugin-architecture-convention（アーキテクチャ規約遵守）

7. plugin-development-agentが以下のスキルを使用して、README等のドキュメントを生成する
   - documentation-standards（記述標準遵守）

8. plugin-development-agentが以下のスキルを使用して、markdownlint検証を実施する
   - documentation-standards（検証実施）

9. plugin-development-agentがユーザーからのフィードバックを収集して必要に応じて修正する

## 成果物

**出力先:**

- `[プラグインディレクトリ]/agents/[エージェント名].md`
- `[プラグインディレクトリ]/skills/[スキル名]/SKILL.md`
- `[プラグインディレクトリ]/commands/[コマンド名].md`
- `[プラグインディレクトリ]/README.md`

**ファイル内容:**

- 各エージェントファイル（フロントマター、役割、責任範囲、注意事項）
- 各スキルファイル（フロントマター、目的、対象フェーズ、手順、成果物、注意事項）
- 各コマンドファイル（フロントマター、概要、使用するエージェント、使用するスキル、実行フロー、成果物、チェックリスト）
- READMEファイル（プラグイン構成要素の一覧表）

## チェックリスト

### コマンド実行前

- [ ] プラグインの目的と対象領域が明確である
- [ ] 業務領域または作業フローの情報が提供されている
- [ ] プラグイン名が決定されている

### コマンド実行後

- [ ] 全てのエージェントファイルが生成されている
- [ ] 全てのスキルファイルが生成されている
- [ ] 全てのコマンドファイルが生成されている
- [ ] READMEファイルが生成されている
- [ ] 各ファイルのフロントマターが正しく記述されている
- [ ] プラグイン要素間の依存関係が適切である
- [ ] プラグインアーキテクチャ規約が遵守されている
- [ ] markdownlint検証に合格している
- [ ] 他の要素を参照していない
- [ ] 固有名詞が使用されていない
