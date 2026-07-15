# Claude Code Learning

Claude Codeを基礎から使いこなせるようになるための、個人学習用リポジトリです。ロードマップ・教材・演習の記録をすべてGitで管理し、進捗をコミットとして残していきます。

## ディレクトリ構成

```
.
├── README.md              このファイル
├── ROADMAP.md              全体ロードマップ（Phase 0〜5）
├── PROGRESS.md             進捗チェックリスト＋学習ログ
├── lessons/                各Phaseに対応した教材（解説＋具体例）
│   ├── 01-basics.md
│   ├── 02-efficiency.md
│   ├── 03-extension.md
│   ├── 04-automation.md
│   └── 05-mastery.md
├── exercises/               Phaseごとの演習。実際に手を動かした記録を書く
│   ├── phase0-setup/
│   ├── phase1-basics/
│   ├── phase2-efficiency/
│   ├── phase3-extension/
│   ├── phase4-automation/
│   └── phase5-mastery/
├── examples/                 CLAUDE.md / settings.json / SKILL.md などの実践テンプレート
│   ├── CLAUDE.md.example
│   ├── settings.json.example
│   ├── hooks-settings.json.example
│   ├── commands/review.md.example
│   └── skills/pr-checklist/SKILL.md.example
└── notes/                     自由メモ（つまずいた点、気づき、実験ログなど）
```

## 使い方

1. `ROADMAP.md` で全体像を把握する
2. `lessons/` の該当Phaseを読み、`examples/` のテンプレートを実際の学習環境にコピーして試す
3. `exercises/phaseN-*/README.md` の演習を実施し、同じディレクトリに結果・気づきをメモとして追記する
4. `PROGRESS.md` のチェックボックスを更新し、区切りのよいタイミングでコミットする

```bash
git add PROGRESS.md exercises/phase1-basics
git commit -m "Phase1: CLAUDE.mdを作成しGrep検索を試した"
```

演習1つ、気づき1つの単位でこまめにコミットすると、後から自分の成長を振り返りやすくなります。

## 進捗の追い方

- `PROGRESS.md` にPhaseごとのチェックリストと日付付きの学習ログを記録します
- コミットログ自体が学習記録になるよう、コミットメッセージには「何をやったか」を書きます（例: `Phase2: settings.jsonに許可リストを追加`）

## 元になった教材

このリポジトリの `ROADMAP.md` と `lessons/` は、Claude Codeとの対話で生成したロードマップ・教材をベースにしています。
