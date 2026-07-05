# Fix CI

CI が失敗しています。

目的:
CI の失敗原因を特定し、最小の変更で修正してください。

手順:

1. CI ログと workflow を確認してください。
2. package scripts / build scripts と CI のコマンドが一致しているか確認してください。
3. lockfile と package manager が一致しているか確認してください。
4. Node / Python / Java などの runtime version が適切か確認してください。
5. GitHub Actions permissions が必要十分か確認してください。
6. 失敗が overlay によるものか、既存プロジェクトの問題かを分けてください。
7. 修正前に原因と修正方針を説明してください。
8. 最小差分で修正してください。
9. 修正後に検証コマンドを実行してください。
10. `.bootstrap/verification-report.md` を更新してください。

禁止:

- 原因不明のまま依存関係を大量追加しない
- テストを削除して CI を通さない
- typecheck / lint / build を無効化して逃げない
- permissions を広げる場合は理由を残す
