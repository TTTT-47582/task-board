# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Git 運用ルール

コードを変更するたびに、必ず以下の手順で GitHub にプッシュすること。

```bash
git add <変更ファイル>
git commit -m "<変更内容を端的に表すメッセージ>"
git push origin <現在のブランチ>
```

- `git add .` や `git add -A` は使わず、変更したファイルを明示的に指定する
- コミットメッセージは変更の「なぜ」を中心に書く
- プッシュ前に `git status` と `git diff` で変更内容を確認する
- main/master ブランチへの force push は禁止

## デプロイ先

https://TTTT-47582.github.io/task-board/

main ブランチへの push で GitHub Actions が自動的にビルド・デプロイする（[.github/workflows/deploy.yml](.github/workflows/deploy.yml)）。

## 技術スタック

- **React 19** — UI フレームワーク
- **Vite 8** — バンドラー・開発サーバー
- **ESLint** — Lint（`npm run lint`）

主要コマンド：

```bash
npm run dev      # 開発サーバー起動 (http://localhost:5173)
npm run build    # 本番ビルド → dist/
npm run preview  # ビルド結果をローカルで確認
```

## コンポーネント命名規約

- ファイル名・コンポーネント名ともに **PascalCase**（例: `TaskList.jsx`、`TaskItem.jsx`）
- 1 ファイル 1 コンポーネントを基本とし、ファイル名とデフォルトエクスポートの名前を一致させる
- CSS はコンポーネントと同名のファイルに記述（例: `App.jsx` → `App.css`）
- カスタムフックは `use` プレフィックス + camelCase（例: `useTasks.js`）
