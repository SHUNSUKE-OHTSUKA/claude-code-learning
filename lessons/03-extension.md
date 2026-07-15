# Lesson 3｜拡張（Phase 3対応）

## 解説：Skills・MCP・Hooks

- **Skill**：手順書。`SKILL.md`にYAML frontmatter（name/description）＋本文の指示を書く。「〇〇のときに使う」というトリガーを明確に書くのがコツ。
- **MCP (Model Context Protocol)**：外部サービスをツールとして接続する仕組み。GitHub、Slack、社内DBなど。
- **Hooks**：ツール実行の前後で決定論的に走る処理。「Editの後は必ずformatterを走らせる」など、Claudeの判断に依存させたくない処理に向く。

## 具体例：SKILL.mdの雛形

テンプレートは `examples/skills/pr-checklist/SKILL.md.example`。

```markdown
---
name: pr-checklist
description: PRを作成する前に必ず使う。テスト・lint・CHANGELOGの確認を行う。
---
1. `npm test` と `npm run lint` を実行し、両方成功することを確認する
2. 変更内容が CHANGELOG.md に追記されているか確認する。なければ追記する
3. コミットメッセージがConventional Commits形式か確認する
4. 上記が揃ったら `gh pr create` で下書きPRを作る
```

## 具体例：post-editでlintを自動実行するhook（settings.jsonの一部）

テンプレートは `examples/hooks-settings.json.example`。

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit",
        "hooks": [
          { "type": "command", "command": "npx eslint --fix $CLAUDE_FILE_PATH" }
        ]
      }
    ]
  }
}
```

## 演習

`exercises/phase3-extension/README.md` に手順あり。

1. 自分がよく口頭で説明しているルーティン作業を1つ、SKILL.md化する
2. MCPサーバーを1つ接続する（まずはファイルシステムやGitHub連携など身近なもの）
3. Edit後に自動でformatterが走るhookを設定し、実際に効いているか確認する
