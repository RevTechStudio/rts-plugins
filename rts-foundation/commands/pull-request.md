---
name: pull-request
description: プルリクエストを作成する
---

# Pull Request

## 概要

このコマンドは、現在のブランチの変更をベースブランチにマージするためのプルリクエストを作成する。ブランチの状態確認、コミット履歴の分析、適切なPR情報の作成、GitHubへのPR公開までを一貫して管理し、コードレビューとマージのプロセスを円滑に進める。

## 使用するエージェント

- **version-control-agent:** Git操作およびGitHub操作全般を管理する

## 使用するスキル

1. **version-control-guidelines:** Git運用のガイドラインに従う
2. **interaction-guidelines:** ユーザーとの効果的な対話パターンに従う

## 実行フロー

1. version-control-agentがversion-control-guidelinesスキルを使用して、現在のブランチ状態を確認する（git status、git branch）
2. version-control-agentがversion-control-guidelinesスキルを使用して、リモートとの同期状態を確認する（git fetch、git status）
3. version-control-agentがinteraction-guidelinesスキルを使用して、ブランチがリモートにpushされていない場合、ユーザーにpushを促す
4. version-control-agentがversion-control-guidelinesスキルを使用して、ベースブランチからのコミット履歴を確認する（git log、git diff）
5. version-control-agentがinteraction-guidelinesスキルを使用して、ユーザーと対話しながら変更の目的や影響範囲を確認する
6. version-control-agentがversion-control-guidelinesスキルを使用して、規約に準拠したPRタイトルと説明を作成する
7. version-control-agentがversion-control-guidelinesスキルを使用して、GitHubにプルリクエストを作成する（gh pr create）
8. version-control-agentがinteraction-guidelinesスキルを使用して、作成されたPRのURLと次のステップをユーザーに報告する

## 成果物

**出力先:**

- GitHubリポジトリにプルリクエストが作成される

**成果物の内容:**

- PR番号とURL
- PRタイトル
- PR説明（変更内容、目的、影響範囲など）
- ベースブランチとヘッドブランチの情報
- 変更されたファイルのリスト
- コミット履歴

## チェックリスト

### コマンド実行前

- [ ] 変更がコミット済みである
- [ ] ブランチがリモートにpush済みである（または実行時にpushする準備がある）
- [ ] PRの目的と変更内容が明確である
- [ ] ベースブランチが正しい

### コマンド実行後

- [ ] プルリクエストが正常に作成された
- [ ] PRタイトルと説明が規約に準拠している
- [ ] 適切なベースブランチが設定されている
- [ ] レビュアーの設定が必要な場合は設定されている
- [ ] CI/CDパイプラインが実行されている（設定されている場合）
