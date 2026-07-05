# Audit Project Bootstrap Overlay

このリポジトリに適用された bootstrap overlay を厳格に監査してください。

確認対象:

- `.bootstrap/bootstrap-plan.md`
- `.bootstrap/bootstrap-decisions.md`
- `.bootstrap/verification-report.md`
- `.bootstrap/research-ledger.md`
- 追加・変更された GitHub Actions
- Dependabot / Renovate 設定
- AGENTS.md / CLAUDE.md / Copilot instructions
- README / CONTRIBUTING / SECURITY
- package scripts / build scripts

監査観点:

1. 既存プロジェクトや講師テンプレートを壊していないか
2. 設定がプロジェクト目的と品質レベルに合っているか
3. required / recommended / optional の分類が妥当か
4. CI が実際の package scripts と一致しているか
5. GitHub Actions permissions が過剰でないか
6. 依存関係を不要に増やしていないか
7. AGENTS.md が長すぎないか
8. AI 用指示が重複していないか
9. secrets や `.env` に触れていないか
10. verification の失敗を隠していないか
11. 採用・不採用理由が記録されているか
12. 今すぐ直すべき問題と後回しでよい問題が分かれているか

出力:

- `.bootstrap/audit-report.md` を作成または更新してください。
- critical / recommended / optional に分けて指摘してください。
- 最後に「この overlay を維持してよいか、修正すべきか、戻すべきか」を明確に判断してください。
