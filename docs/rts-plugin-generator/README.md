# Plugin Generator Plugin

## 汎用プラグイン要素作成用プラグイン構成要素

---

### Agent

| 要素名 | 概要 | 完了 |
|--------|------|-----|
| plugin-development-agent | プラグイン要素の作成全体を管理し、ユーザーと対話しながら要素を設計・生成する専任エージェント | 完 |

---

### Workflow Skill

| 要素名 | 概要 | 完了 |
|--------|------|-----|
| domain-analyzer | ユーザーの業務領域や目的を分析し、必要な機能を抽出する | 完 |
| workflow-analyzer | 作業フローや手順を分析し、自動化可能な要素を特定する | 完 |
| responsibility-mapper | 作業の責任範囲を整理し、エージェント定義に必要な情報を抽出する | 完 |
| task-decomposer | 複雑な作業を単一目的の小さなタスクに分解する | 完 |
| agent-generator | 責任範囲の定義からエージェント要素を生成する | 完 |
| workflow-skill-generator | 作業手順からワークフロースキルを生成する | 完 |
| convention-skill-generator | 規約・ガイドラインからコンベンションスキルを生成する | 完 |
| command-generator | エージェントとスキルの組み合わせからコマンドを生成する | 完 |
| element-relationship-analyzer | プラグイン要素間の依存関係や呼び出し順序を分析する | 完 |
| plugin-validator | 生成したプラグイン全体の整合性・完全性を検証する | 完 |
| plugin-packager | 生成したプラグインをZIP形式にまとめる | 完 |

---

### Convention Skill

| 要素名 | 概要 | 完了 |
|--------|------|-----|
| plugin-architecture-convention | プラグイン全体の構造設計原則（要素の役割分担、階層構造） | 完 |
| element-definition-convention | プラグイン要素の定義ルール（命名規則、必須項目、記述フォーマット） | 完 |
| skill-granularity-convention | スキルの適切な粒度を定義（1スキル1目的、分割基準、結合基準） | 完 |

---

### Command

| 要素名 | 概要 | 完了 |
|--------|------|-----|
| generate-agent | エージェント要素を個別に生成する | 完 |
| generate-convention-skill | Convention Skill要素を個別に生成する | 完 |
| generate-workflow-skill | Workflow Skill要素を個別に生成する | 完 |
| generate-command | コマンド要素を個別に生成する | 完 |
| generate-plugin | 分析結果からプラグイン要素全体を生成し、ドキュメント化する | - |
| package-plugin | パッケージ化してダウンロード可能にする | - |
| test-skills | 各スキルに対して単体テストを実施する | - |
