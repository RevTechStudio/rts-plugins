---
name: issue
description: Issueを管理する
---

# Issue

## 概要

このコマンドは、GitHub Issueの管理を行う。Issue作成、一覧表示、詳細確認、クローズなどの操作を対話的に実行し、タスク管理やバグ報告のワークフローを効率化する。

## 使用するエージェント

- **version-control-agent:** Git操作およびGitHub操作全般を管理する

## 使用するスキル

1. **issue-management-guidelines:** Issue管理のガイドラインに従う
2. **interaction-guidelines:** ユーザーとの効果的な対話パターンに従う

## 実行フロー

1. version-control-agentが以下のスキルを使用して、ユーザーに実行したい操作を確認する（作成、一覧、表示、クローズなど）
   - interaction-guidelines（対話パターン）

2. **Issue作成の場合:**
   1. version-control-agentが以下のスキルを使用して、Issueのタイプを確認する（バグ報告、機能要望、タスクなど）
      - issue-management-guidelines（Issue管理ガイドライン）

   2. version-control-agentが以下のスキルを使用して、適切なテンプレートを選択する
      - issue-management-guidelines（Issue管理ガイドライン）

   3. version-control-agentが以下のスキルを使用して、必要な情報をユーザーから収集する（タイトル、説明、再現手順など）
      - interaction-guidelines（対話パターン）

   4. version-control-agentが以下のスキルを使用して、規約に準拠したIssueを作成する（gh issue create）
      - issue-management-guidelines（Issue管理ガイドライン）

   5. version-control-agentが以下のスキルを使用して、作成されたIssueのURLと番号をユーザーに報告する
      - interaction-guidelines（対話パターン）

3. **Issue一覧表示の場合:**
   1. version-control-agentが以下のスキルを使用して、フィルタ条件を確認する（状態、ラベル、担当者など）
      - interaction-guidelines（対話パターン）

   2. version-control-agentが以下のスキルを使用して、Issueの一覧を取得して表示する（gh issue list）
      - issue-management-guidelines（Issue管理ガイドライン）

4. **Issue詳細表示の場合:**
   1. version-control-agentが以下のスキルを使用して、表示するIssue番号を確認する
      - interaction-guidelines（対話パターン）

   2. version-control-agentが以下のスキルを使用して、Issueの詳細を取得して表示する（gh issue view）
      - issue-management-guidelines（Issue管理ガイドライン）

5. **Issueクローズの場合:**
   1. version-control-agentが以下のスキルを使用して、クローズするIssue番号を確認する
      - interaction-guidelines（対話パターン）

   2. version-control-agentが以下のスキルを使用して、クローズ理由を確認する（完了、重複、無効など）
      - interaction-guidelines（対話パターン）

   3. version-control-agentが以下のスキルを使用して、Issueをクローズする（gh issue close）
      - issue-management-guidelines（Issue管理ガイドライン）

## 成果物

**出力先:**

- GitHubリポジトリにIssueが作成・更新される

**成果物の内容（作成時）:**

- Issue番号とURL
- Issueタイトル
- Issue本文（説明、再現手順、期待動作など）
- ラベル（bug、enhancement、taskなど）
- マイルストーン（設定した場合）
- 担当者（設定した場合）

## チェックリスト

### コマンド実行前（作成時）

- [ ] Issueの目的が明確である
- [ ] 適切なテンプレートを選択できる
- [ ] 必要な情報が揃っている（タイトル、説明など）
- [ ] 重複するIssueがないか確認した

### コマンド実行後（作成時）

- [ ] Issueが正常に作成された
- [ ] タイトルと説明が規約に準拠している
- [ ] 適切なラベルが設定されている
- [ ] 必要に応じて担当者が設定されている
- [ ] Issue番号を記録した
