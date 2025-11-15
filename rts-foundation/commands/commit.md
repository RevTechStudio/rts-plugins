---
name: commit
description: 変更をコミットする
---

# Commit

## 概要

このコマンドは、ワークツリーの変更をローカルリポジトリにコミットする。変更内容の確認、適切なコミットメッセージの作成、コミットの実行までを一貫して管理し、バージョン管理のベストプラクティスに従った運用を実現する。

## 使用するエージェント

- **version-control-agent:** Git操作およびGitHub操作全般を管理する

## 使用するスキル

1. **version-control-guidelines:** Git運用のガイドラインに従う
2. **interaction-guidelines:** ユーザーとの効果的な対話パターンに従う

## 実行フロー

1. version-control-agentがversion-control-guidelinesスキルを使用して、現在の変更状況を確認する（git status）
2. version-control-agentがversion-control-guidelinesスキルを使用して、変更内容の詳細を確認する（git diff）
3. version-control-agentがinteraction-guidelinesスキルを使用して、ユーザーと対話しながら変更の意図や目的を確認する
4. version-control-agentがversion-control-guidelinesスキルを使用して、規約に準拠したコミットメッセージを作成する
5. version-control-agentがversion-control-guidelinesスキルを使用して、変更をステージングする（git add）
6. version-control-agentがversion-control-guidelinesスキルを使用して、コミットを実行する（git commit）
7. version-control-agentがinteraction-guidelinesスキルを使用して、コミット結果をユーザーに報告する

## 成果物

**出力先:**

- ローカルリポジトリ（.gitディレクトリ）にコミットオブジェクトが作成される

**成果物の内容:**

- コミットハッシュ
- コミットメッセージ
- 変更されたファイルのリスト
- 作成者情報
- タイムスタンプ

## チェックリスト

### コマンド実行前

- [ ] 変更内容が意図したものであることを確認した
- [ ] コミット対象のファイルが明確である
- [ ] コミットメッセージの内容を考えている

### コマンド実行後

- [ ] コミットが正常に作成された
- [ ] コミットメッセージが規約に準拠している
- [ ] 適切なファイルがコミットに含まれている
- [ ] 機密情報が含まれていない
- [ ] コミット履歴が適切に記録されている
