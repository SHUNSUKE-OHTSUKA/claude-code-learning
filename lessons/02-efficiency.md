# Lesson 2｜効率化（Phase 2対応）

## 解説：権限設定とPlan Mode

- **権限プロンプト**は安全装置です。よく使う安全なコマンド（例: `npm test`, `git status`）は `settings.json` の許可リストに登録すると毎回聞かれなくなります。
- **Plan Mode**は「まず計画だけ立てさせて、実装前にレビューする」モードです。影響範囲が広い変更・不可逆な変更（DBスキーマ変更、依存関係の大幅更新など）では必ず使いましょう。

## 具体例：settings.json の許可リスト

テンプレートは `examples/settings.json.example`。

```json
{
  "permissions": {
    "allow": [
      "Bash(npm test:*)",
      "Bash(npm run lint:*)",
      "Bash(git status)",
      "Bash(git diff:*)"
    ]
  }
}
```

## 具体例：カスタムスラッシュコマンド

`.claude/commands/review.md` を作ると `/review` で呼び出せます。テンプレートは `examples/commands/review.md.example`。

```markdown
---
description: 自分のPRチェックリストでレビューする
---
現在の差分を以下の観点でレビューしてください：
1. エラーハンドリング漏れがないか
2. テストが追加されているか
3. 命名がプロジェクトの規約と一致しているか
問題があれば具体的な行番号と修正案を示してください。
```

## 演習

`exercises/phase2-efficiency/README.md` に手順あり。

1. `settings.json` に自分がよく承認するコマンドを3つ登録する
2. 大きめの変更（例: 新機能追加）でPlan Modeを使い、実装前にレビューコメントを1つ入れてみる
3. 自分専用のカスタムスラッシュコマンドを1つ作る（コミット規約チェック、リリースノート生成など）
