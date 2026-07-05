# project-bootstrap-overlay Skill

`project-bootstrap-overlay` は、公式CLIや講師テンプレートで作成した新規プロジェクト、または引き継いだ既存プロジェクトに対して、AIが安全に環境構築を支援するための Skill パッケージです。

## 目的

この Skill は、AIに環境構築を丸投げするためのものではありません。

AIに以下のプロセスを守らせるためのものです。

```txt
Doctor → Grill → Research → Plan → Apply → Verify → Audit → Record
```

## できること

- 既存プロジェクトの診断
- 人間に必要な価値判断だけ質問
- 公式情報を優先した調査
- required / recommended / optional に分けた計画
- AGENTS.md / CLAUDE.md / Copilot instructions の生成補助
- GitHub Actions / Dependabot / PR template の生成補助
- SECURITY.md / CONTRIBUTING.md / .env.example の生成補助
- 検証レポートと監査レポートの作成
- 判断理由の記録

## できないこと / やらないこと

- 公式 generator を置き換えない
- 既存プロジェクトを勝手に大改造しない
- 最新版を無条件に採用しない
- AGENTS.md に大量の指示を詰め込まない
- secrets や `.env` を変更しない
- application code の自動マージを前提にしない

## 推奨配置

Claude Code で使う場合は、以下のように配置できます。

```txt
.claude/skills/project-bootstrap-overlay/
  SKILL.md
  references/
  templates/
  prompts/
  checklists/
```

または、このディレクトリ全体を自分の Skill 管理リポジトリに置いてください。

## 使用例

Claude Code または Codex に以下を依頼します。

```txt
このリポジトリに project-bootstrap-overlay を適用してください。
まず Doctor を行い、ファイルから分かることは質問せず、最大7問だけ Grill してください。
その後、公式情報を調査し、required / recommended / optional に分けて bootstrap-plan を作成してください。
承認後、required のみ適用し、lint / typecheck / test / build を検証してください。
```

## 最初のおすすめ運用

1. `create-next-app` などで新規プロジェクトを作る
2. git initial commit を作る
3. この Skill を適用する
4. まず plan-only で試す
5. 問題なければ required のみ apply する
6. verification と audit を確認する

## ディレクトリ構成

```txt
project-bootstrap-overlay-skill/
  SKILL.md
  README.md
  references/
  templates/
  prompts/
  checklists/
  examples/
```
