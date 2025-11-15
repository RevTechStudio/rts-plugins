---
name: generate-agent
description: エージェント要素を個別に生成する
---

# Generate Agent

## 概要

このコマンドは、ユーザーが提供する責任範囲の定義から、エージェント要素のマークダウンファイルを生成する。既存エージェントとの重複を確認し、ユーザーとの対話を通じて必要な情報を収集して、標準化されたエージェントドキュメントを作成する。

## 使用するエージェント

- **plugin-development-agent:** プラグイン要素の作成全体を管理し、ユーザーと対話しながら要素を設計・生成する

## 使用するスキル

1. **agent-generator:** ユーザーの責任範囲定義から、Agentのマークダウンファイルを生成する
2. **documentation-standards:** Markdownドキュメントの記述標準に従う
3. **interaction-guidelines:** ユーザーとの効果的な対話パターンに従う
4. **element-definition-convention:** プラグイン要素の定義ルールに従う
5. **plugin-architecture-convention:** プラグイン全体のアーキテクチャ設計原則に従う

## 実行フロー

1. plugin-development-agentが以下のスキルを使用して、既存エージェントを確認し、重複を避ける
   - agent-generator（エージェント確認）
   - plugin-architecture-convention（アーキテクチャ規約遵守）

2. plugin-development-agentが以下のスキルを使用して、ユーザーとの対話を通じて情報を収集する
   - agent-generator（情報収集）
   - interaction-guidelines（対話パターン）

3. plugin-development-agentが以下のスキルを使用して、コンテンツを生成する
   - agent-generator（コンテンツ生成）
   - element-definition-convention（定義ルール遵守）

4. plugin-development-agentが以下のスキルを使用して、markdownlint検証を実施する
   - agent-generator（検証実施）
   - documentation-standards（記述標準遵守）

5. plugin-development-agentがユーザーからのフィードバックを収集して必要に応じて修正する

## 成果物

**出力先:**

- `[プラグインディレクトリ]/agents/[エージェント名].md`

**ファイル内容:**

- フロントマター（name, description, tools, model, color）
- 役割セクション
- 責任範囲（責任範囲内、責任範囲外）
- 注意事項

## チェックリスト

### コマンド実行前

- [ ] エージェントの責任範囲が明確に定義されている
- [ ] 対象フェーズまたは領域が明確である
- [ ] 既存エージェントを確認した

### コマンド実行後

- [ ] エージェントファイルが生成されている
- [ ] フロントマターが正しく記述されている
- [ ] 役割が明確に記述されている
- [ ] 責任範囲内と責任範囲外が定義されている
- [ ] 注意事項が記述されている
- [ ] プラグインアーキテクチャ規約が遵守されている
- [ ] markdownlint検証に合格している
- [ ] 他の要素（エージェント、スキル、コマンド）を参照していない
- [ ] 固有名詞が使用されていない
