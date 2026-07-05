# Apply Project Bootstrap Overlay

このリポジトリに `project-bootstrap-overlay` を適用してください。

目的:
既存のプロジェクト生成方法や講師テンプレートを壊さず、AI駆動開発に必要な CI、品質チェック、セキュリティ、ドキュメント、AI agent 設定を最小限の手間で整備することです。

手順:

1. まず Doctor を行い、リポジトリを診断してください。
2. ファイルから分かることは質問しないでください。
3. 人間に聞く質問は最大7問までにしてください。
4. 質問は目的、品質レベル、安定性、デプロイ先、AI許可範囲、自動マージ、既存テンプレート尊重のような価値判断に限定してください。
5. その後、必要な領域について公式ドキュメントを優先して調査してください。
6. 最新という理由だけで採用せず、安定性・互換性・保守性を重視してください。
7. 変更前に `.bootstrap/bootstrap-plan.md` を作成してください。
8. 変更内容を required / recommended / optional に分けてください。
9. 承認後、required のみ適用してください。
10. `.bootstrap/bootstrap-decisions.md` に採用・不採用理由を記録してください。
11. install / lint / format check / typecheck / test / build / security check を実行してください。
12. 結果を `.bootstrap/verification-report.md` に記録してください。
13. 最後に `.bootstrap/audit-report.md` を作成してください。

禁止:

- 既存構成を勝手に置き換えない
- 大量の formatter 差分を出さない
- 巨大な AGENTS.md を作らない
- secrets や `.env` を変更しない
- 公式情報を確認せずにツールやバージョンを選ばない
- 最新版を無条件に採用しない
- アプリケーションコードを自動マージ前提にしない
