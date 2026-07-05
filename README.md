# skills

GitHub Copilot / Claude Code などの AI エージェント向け Skill パッケージ集です。

## Skill 一覧

| Skill | 説明 |
|---|---|
| [project-bootstrap-overlay](skills/project-bootstrap-overlay/README.md) | 既存プロジェクトに開発環境・CI・セキュリティ・AI エージェント設定を安全に追加する |

## 使い方

各 Skill は `SKILL.md` を含むディレクトリ単位で配布されています。
使用する AI エージェントの規約に従い、Skill ディレクトリを配置してください。

**Claude Code の場合：**

```txt
.claude/skills/<skill-name>/
```

**GitHub Copilot の場合：**

Copilot のカスタム指示ファイル（`.github/copilot-instructions.md` など）から参照するか、
VS Code の `agent-plugins` ディレクトリに配置してください。

## ディレクトリ構成

```txt
skills/
  <skill-name>/
    SKILL.md          # エージェントへの指示本体
    README.md         # 人間向けの説明
    references/       # 参照ドキュメント
    templates/        # 生成物のテンプレート
    prompts/          # よく使うプロンプト集
    checklists/       # チェックリスト
    examples/         # 使用例
```

## ライセンス

[LICENSE](LICENSE)

