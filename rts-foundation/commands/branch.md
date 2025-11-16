---
name: branch
description: ブランチを管理する
---

# Branch

## 概要

このコマンドは、Gitブランチの管理を行う。ブランチ作成、切り替え、削除、一覧表示などの操作を対話的に実行し、開発フローにおけるブランチ運用を効率化する。

## 使用するエージェント

- **version-control-agent:** Git操作およびGitHub操作全般を管理する

## 使用するスキル

1. **version-control-guidelines:** Git運用のガイドラインに従う
2. **interaction-guidelines:** ユーザーとの効果的な対話パターンに従う

## 実行フロー

1. version-control-agentが以下のスキルを使用して、ユーザーに実行したい操作を確認する（作成、切り替え、削除、一覧表示など）
   - interaction-guidelines（対話パターン）

2. **ブランチ作成の場合:**
   1. version-control-agentが以下のスキルを使用して、現在のブランチを確認する（git branch --show-current）
      - version-control-guidelines（Git運用ガイドライン）

   2. version-control-agentが以下のスキルを使用して、新しいブランチ名をユーザーから取得する
      - interaction-guidelines（対話パターン）

   3. version-control-agentが以下のスキルを使用して、ブランチ命名規則に準拠しているか検証する
      - version-control-guidelines（Git運用ガイドライン）

   4. version-control-agentが以下のスキルを使用して、ベースブランチを確認する
      - interaction-guidelines（対話パターン）

   5. version-control-agentが以下のスキルを使用して、ブランチを作成する（git branch）
      - version-control-guidelines（Git運用ガイドライン）

   6. version-control-agentが以下のスキルを使用して、作成後に切り替えるか確認し、必要に応じて切り替える（git switch）
      - interaction-guidelines（対話パターン）
      - version-control-guidelines（Git運用ガイドライン）

   7. version-control-agentが以下のスキルを使用して、結果をユーザーに報告する
      - interaction-guidelines（対話パターン）

3. **ブランチ切り替えの場合:**
   1. version-control-agentが以下のスキルを使用して、現在のブランチの変更状態を確認する（git status）
      - version-control-guidelines（Git運用ガイドライン）

   2. version-control-agentが以下のスキルを使用して、未コミットの変更がある場合、対処方法を確認する（コミット、スタッシュ、破棄など）
      - interaction-guidelines（対話パターン）

   3. version-control-agentが以下のスキルを使用して、切り替え先のブランチ名を確認する
      - interaction-guidelines（対話パターン）

   4. version-control-agentが以下のスキルを使用して、ブランチを切り替える（git switch）
      - version-control-guidelines（Git運用ガイドライン）

   5. version-control-agentが以下のスキルを使用して、結果をユーザーに報告する
      - interaction-guidelines（対話パターン）

4. **ブランチ削除の場合:**
   1. version-control-agentが以下のスキルを使用して、削除するブランチ名を確認する
      - interaction-guidelines（対話パターン）

   2. version-control-agentが以下のスキルを使用して、削除対象のブランチがマージ済みか確認する
      - version-control-guidelines（Git運用ガイドライン）

   3. version-control-agentが以下のスキルを使用して、未マージの場合は警告を表示し、強制削除するか確認する
      - interaction-guidelines（対話パターン）

   4. version-control-agentが以下のスキルを使用して、ブランチを削除する（git branch -d または -D）
      - version-control-guidelines（Git運用ガイドライン）

   5. version-control-agentが以下のスキルを使用して、リモートブランチも削除するか確認する
      - interaction-guidelines（対話パターン）

   6. version-control-agentが以下のスキルを使用して、必要に応じてリモートブランチを削除する（git push origin --delete）
      - version-control-guidelines（Git運用ガイドライン）

   7. version-control-agentが以下のスキルを使用して、結果をユーザーに報告する
      - interaction-guidelines（対話パターン）

5. **ブランチ一覧表示の場合:**
   1. version-control-agentが以下のスキルを使用して、表示範囲を確認する（ローカル、リモート、全て）
      - interaction-guidelines（対話パターン）

   2. version-control-agentが以下のスキルを使用して、ブランチ一覧を取得して表示する（git branch、git branch -r、git branch -a）
      - version-control-guidelines（Git運用ガイドライン）

   3. version-control-agentが以下のスキルを使用して、現在のブランチを強調表示する
      - interaction-guidelines（対話パターン）

## 成果物

**出力先:**

- ローカルリポジトリのブランチ構成が変更される
- リモートリポジトリのブランチ構成が変更される（削除時など）

**成果物の内容（作成時）:**

- 新しいブランチ名
- ベースブランチ情報
- 現在のブランチ（切り替えた場合）

**成果物の内容（削除時）:**

- 削除されたブランチ名
- ローカル/リモートの削除状況

## チェックリスト

### コマンド実行前（作成時）

- [ ] ブランチ名が命名規則に準拠している
- [ ] 適切なベースブランチから作成する
- [ ] 同名のブランチが存在しない

### コマンド実行後（作成時）

- [ ] ブランチが正常に作成された
- [ ] 必要に応じて新しいブランチに切り替えられた
- [ ] ブランチ名が正しい

### コマンド実行前（削除時）

- [ ] 削除対象のブランチがマージ済みである（未マージの場合は意図的）
- [ ] 削除対象のブランチが正しい
- [ ] 現在のブランチが削除対象ではない

### コマンド実行後（削除時）

- [ ] ブランチが正常に削除された
- [ ] 必要に応じてリモートブランチも削除された
- [ ] ブランチ一覧から削除されている
