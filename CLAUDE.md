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
