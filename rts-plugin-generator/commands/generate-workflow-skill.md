---
name: generate-workflow-skill
description: 作業フローからWorkflow Skillを生成する
---

# Generate Workflow Skill

## 概要

このコマンドは、ユーザーが提供する作業フローの内容から、Workflow Skillのマークダウンファイルを生成する。引数でファイルパスが指定された場合はそのファイルの内容を解析し、引数がない場合は対話を通じて作業フロー情報を収集する。既存のWorkflow Skillとの重複を確認し、標準化されたスキルドキュメントを作成する。

## 使用するエージェント

- **plugin-development-agent:** プラグイン要素の作成全体を管理し、ユーザーと対話しながら要素を設計・生成する

## 使用するスキル

1. **workflow-skill-generator:** ユーザーの作業フローから、Workflow Skillのマークダウンファイルを生成する
2. **documentation-standards:** Markdownドキュメントの記述標準に従う
3. **interaction-guidelines:** ユーザーとの効果的な対話パターンに従う
4. **element-definition-convention:** プラグイン要素の定義ルールに従う
5. **plugin-architecture-convention:** プラグイン全体のアーキテクチャ設計原則に従う

## 実行フロー

1. plugin-development-agentがworkflow-skill-generatorスキルを使用して、既存のWorkflow Skillを確認し、重複を避ける（plugin-architecture-conventionに従う）
2. plugin-development-agentがworkflow-skill-generatorスキルを使用して、引数でファイルパスが指定された場合はそのファイルを読み込み、内容を解析してテンプレートに当てはめる（interaction-guidelinesに従う）
3. plugin-development-agentがworkflow-skill-generatorスキルを使用して、引数がない場合は対話を通じてスキルの役割、ワークフローステップ、前提条件、事後条件などの情報を収集する（interaction-guidelinesに従う）
4. plugin-development-agentがworkflow-skill-generatorスキルを使用して、収集した情報を基にWorkflow Skillファイルのコンテンツを生成する（element-definition-conventionに従う）
5. plugin-development-agentがworkflow-skill-generatorスキルを使用して、markdownlint検証を実施する（documentation-standardsに従う）
6. plugin-development-agentがユーザーからのフィードバックを収集して必要に応じて修正する

## 成果物

**出力先:**

- `[プラグインディレクトリ]/skills/[スキル名]/SKILL.md`

**ファイル内容:**

- フロントマター（name, description）
- 役割セクション
- ワークフローステップ
- 前提条件と事後条件
- エラーハンドリングと例外処理（必要に応じて）
- チェックリストや検証項目（必要に応じて）

## チェックリスト

### コマンド実行前

- [ ] 作業フローの内容が明確である（ファイル指定または対話で収集）
- [ ] スキルの目的とワークフローステップが明確である
- [ ] 既存のWorkflow Skillを確認した

### コマンド実行後

- [ ] Workflow Skillファイルが生成されている
- [ ] フロントマターが正しく記述されている
- [ ] 役割が明確に記述されている
- [ ] ワークフローステップが適切に記述されている
- [ ] 前提条件と事後条件が定義されている
- [ ] プラグインアーキテクチャ規約が遵守されている
- [ ] markdownlint検証に合格している
- [ ] 他の要素（エージェント、スキル、コマンド）を参照していない
- [ ] 固有名詞が使用されていない
