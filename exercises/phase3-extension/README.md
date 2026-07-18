# Phase 3 演習｜拡張

対応教材: `lessons/03-extension.md`

- [x] ルーティン作業を1つSKILL.md化した（`examples/skills/pr-checklist/SKILL.md.example` を参考にしてよい）
- [x] MCPサーバーを1つ接続した
- [x] post-edit hookでformatter自動実行を設定した（`examples/hooks-settings.json.example` を参考にしてよい）

## メモ（実施日・気づき）

- 汎用的なAgentではカバーできない標準化されたコンテキストをスキル(SKILL.md)として登録することで生産性Up！。個人チーム固有のノウハウを定義してAgentの振る舞いを制御する
- MCPを使う際に認証を通さなくてなならずどこかに情報を保持する設計を含めなくてはならない。.mcp.jsonはGitHub管理されるので認証情報を書くのはNG
- 認可も重要で、ここでも最小権限の付与は徹底すべき
- hooksのEventは40程度存在する。https://code.claude.com/docs/ja/hooks#hook-lifecycle
