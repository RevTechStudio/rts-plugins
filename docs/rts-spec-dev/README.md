# RevTechStudio Specification Development Plugin

## プラグイン要素一覧

---

### Agent

| 要素名 | フェーズ | 概要 |
|--------|----------|------|
| requirements-agent | 要件定義 | ユーザーと対話しながら要件を引き出し、整理・構造化する専任エージェント |
| design-agent | 詳細設計 | 要件定義を基にユーザーと対話しながら詳細設計を進める専任エージェント |
| implementation-agent | 実装 | 設計書を基にユーザーと対話しながら実装を進める専任エージェント |
| test-agent | テスト | 実装を基にユーザーと対話しながらテストを進める専任エージェント |

---

### Workflow Skill

| 要素名 | フェーズ | 概要 |
|--------|----------|------|
| requirements-structurer | 要件定義 | 対話から得た情報を機能要件・非機能要件に分類整理する |
| domain-modeler | 要件定義 | 要件から主要なエンティティと関係性を抽出してモデル化する |
| acceptance-criteria-builder | 要件定義 | 各機能に対する具体的な受入条件を定義する |
| requirements-validator | 要件定義 | 要件の曖昧さや矛盾を検出してユーザーに確認を促す |
| spec-document-generator | 要件定義 | 対話で確定した要件を仕様書フォーマットに整形する |
| architecture-designer | 詳細設計 | システム全体のアーキテクチャパターンを提案・設計する |
| tech-stack-selector | 詳細設計 | 要件に基づき最適な技術スタック（言語、フレームワーク、DB等）を選定する |
| database-schema-designer | 詳細設計 | エンティティからデータベーススキーマを設計する |
| api-designer | 詳細設計 | RESTful/GraphQL等のAPI仕様を設計する |
| component-architect | 詳細設計 | フロントエンド/バックエンドのコンポーネント構成を設計する |
| security-designer | 詳細設計 | 認証・認可・暗号化等のセキュリティ設計を行う |
| performance-designer | 詳細設計 | 非機能要件を満たすパフォーマンス設計を行う |
| design-validator | 詳細設計 | 設計の整合性・実現可能性を検証する |
| design-document-generator | 詳細設計 | 確定した設計を設計書フォーマットに整形する |
| task-planner | 詳細設計 | 設計を実装可能な単位のタスクに分割し、実装順序を提案する |
| code-generator | 実装 | 設計仕様からソースコードを生成する |
| database-migration-builder | 実装 | スキーマ設計からマイグレーションファイルを作成する |
| api-implementation-builder | 実装 | API設計からエンドポイント実装を生成する |
| ui-component-builder | 実装 | 画面設計からUIコンポーネントを実装する |
| code-reviewer | 実装 | 生成されたコードの品質・規約準拠をチェックする |
| refactoring-assistant | 実装 | コードの改善提案とリファクタリングを支援する |
| dependency-manager | 実装 | 必要なライブラリ・パッケージの追加と管理を行う |
| implementation-validator | 実装 | 実装が設計仕様を満たしているか検証する |
| unit-test-generator | テスト | 実装コードに対応する単体テストコードを生成する |
| integration-test-builder | テスト | コンポーネント間の統合テストを設計・実装する |
| system-test-designer | テスト | システム全体の動作確認テストを設計する |
| acceptance-test-builder | テスト | 受入基準に基づく受入テストを作成する |
| performance-test-designer | テスト | 非機能要件を検証するパフォーマンステストを設計する |
| security-test-designer | テスト | セキュリティ要件を検証するテストを設計する |
| test-executor | テスト | 各種テストを実行し結果を収集・分析する |
| bug-reporter | テスト | テスト結果から不具合を特定し報告する |
| test-coverage-analyzer | テスト | テストカバレッジを分析し不足箇所を指摘する |
| release-validator | テスト | 全テスト結果を総合評価しリリース可否を判定する |

---

### Command

| 要素名 | フェーズ | 概要 |
|--------|----------|------|
| requirements | 要件定義 | 要件定義フェーズの開始・進行・完了を管理する統合コマンド |
| design | 詳細設計 | 詳細設計フェーズの開始・進行・完了を管理する統合コマンド |
| task | 詳細設計 | 設計からタスクを生成し、実装フェーズ用のタスクリストを作成する |
| implement | 実装 | 実装フェーズの開始・進行・完了を管理する統合コマンド |
| test-plan | テスト | テスト計画を作成し、テストケースを生成する |
| test-run | テスト | テストを実行し、結果の検証とリリース判定を行う |
