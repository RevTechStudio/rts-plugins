---
name: generate-command
description: コマンド要素を個別に生成する
---

# Generate Command

## 概要

このコマンドは、ユーザーが提供するエージェントとスキルの組み合わせから、コマンド要素のマークダウンファイルを生成する。既存コマンドとの重複を確認し、ユーザーとの対話を通じて必要な情報を収集して、標準化されたコマンドドキュメントを作成する。

## 使用するエージェント

- **plugin-development-agent:** プラグイン要素の作成全体を管理し、ユーザーと対話しながら要素を設計・生成する

## 使用するスキル

1. **command-generator:** エージェントとスキルの組み合わせから、Commandのマークダウンファイルを生成する
2. **documentation-standards:** Markdownドキュメントの記述標準に従う
3. **interaction-guidelines:** ユーザーとの効果的な対話パターンに従う
4. **element-definition-convention:** プラグイン要素の定義ルールに従う
5. **plugin-architecture-convention:** プラグイン全体のアーキテクチャ設計原則に従う

## 実行フロー

1. plugin-development-agentがcommand-generatorスキルを使用して、既存コマンドを確認し、重複を避ける（plugin-architecture-conventionに従う）
2. plugin-development-agentがcommand-generatorスキルを使用して、ユーザーとの対話を通じてコマンドの目的、使用するエージェント、使用するスキル、実行フロー、成果物などの情報を収集する（interaction-guidelinesに従う）
3. plugin-development-agentがcommand-generatorスキルを使用して、収集した情報を基にコマンドファイルのコンテンツを生成する（element-definition-conventionに従う）
4. plugin-development-agentがcommand-generatorスキルを使用して、markdownlint検証を実施する（documentation-standardsに従う）
5. plugin-development-agentがユーザーからのフィードバックを収集して必要に応じて修正する

## 成果物

**出力先:**

- `[プラグインディレクトリ]/commands/[コマンド名].md`: コマンド定義ファイル

**ファイル構成:**

```text
[プラグインディレクトリ]/
└── commands/
    └── [コマンド名].md
```

**ファイル内容:**

- フロントマター（name, description）
- 概要セクション
- 使用するエージェント
- 使用するスキル
- 実行フロー
- 成果物

## チェックリスト

### コマンド実行前

- [ ] コマンドの目的と機能が明確に定義されている
- [ ] 使用するエージェントが明確である
- [ ] 使用するスキルが明確である
- [ ] 既存コマンドを確認した

### コマンド実行後

- [ ] コマンドファイルが生成されている
- [ ] フロントマターが正しく記述されている
- [ ] 概要が明確に記述されている
- [ ] 使用するエージェントが定義されている
- [ ] 使用するスキルがリスト化されている
- [ ] 実行フローが明確に記述されている
- [ ] 成果物の出力先とファイル構成が記述されている
- [ ] プラグインアーキテクチャ規約が遵守されている
- [ ] markdownlint検証に合格している
- [ ] 他の要素（エージェント、スキル、コマンド）を参照していない
- [ ] 固有名詞が使用されていない
