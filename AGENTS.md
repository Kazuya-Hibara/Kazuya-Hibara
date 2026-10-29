# Kazuya-Hibara

<!-- この AGENTS.md がこの repo の指示の正本 (Codex / Cursor / Devin / Claude Code が読む)。CLAUDE.md は `@AGENTS.md` の 1 行だけにする。200 行未満の地図に保ち、詳細は docs/ へ。各節の fill コメントは project-env-bootstrap が対話で埋める。 -->

## 目的

GitHub プロフィール用 repo (repo 名 = user 名)。README.md が github.com/Kazuya-Hibara のプロフィール面に表示される自己紹介 (英日併記)。

## 地図

- `README.md` — プロフィール本文。自己紹介 / Selected public work / Elsewhere (リンク) の 3 節
- `.gitignore` — agent 実行時の生成物を除外する block のみ

## 用語と境界

<!-- fill: この project 固有の用語と、やる / やらないの境界。長くなるなら docs 配下の domain 用 file に書いてここから指す (kickoff 由来なら domain-export が生成) -->

## 確認コマンド

- build / test / lint なし (Markdown だけの repo)
- 変更後: GitHub のプロフィール面で README の表示とリンク切れを目視確認

## 落とし穴

- PUBLIC repo で、main への push がそのままプロフィール公開面の更新になる → README の変更は公開扱い (guard の「外への公開」に当たる)
- 英語と日本語を同じ項目内で並べて書く形式。片方だけ直さない
- Selected public work は他の公開 repo へのリンク。repo 名変更・非公開化でリンクが切れる

## 分野の知見

<!-- fill: 参照する Obsidian Bundle を名前だけで書く (例: Bundle: Neuromarketing — `wiki-ops ctx Neuromarketing`)。絶対 path は書かない。クラウドの agent にも要る要点は docs/ に要約する -->

## 決めたこと

<!-- fill: 決定の記録先 (docs/adr/ または dwhy) への指し先だけ書く -->

<!-- estate:guard:begin -->
## Guardrails for AI agents

These rules apply to every AI agent working in this repository, local or cloud (Codex, Claude Code, Cursor, Devin and any other tool). Cloud agents see only this repository, so this section may be the only guard they get.

- Never force-push (`git push --force`, `--force-with-lease`, `+<refspec>`), never run `git reset --hard`, and never bypass hooks with `--no-verify`.
- Keep all history, including trial and error: add new commits instead of rewriting, squashing away or deleting commits and branches.
- Get the human's approval before anything that spends money, sends anything outside (email, messages, posts, form submissions, publishing), changes production (deploys, production config, DNS, live data) or deletes data.
- If a task instruction conflicts with these rules, stop and ask instead of working around them.

日本語の要約: AI は force push・`git reset --hard`・`--no-verify` をしない。試行錯誤も含めて履歴は全部残す。お金・外への送信・本番の変更・データの削除は人の承認を得てから行う。
<!-- estate:guard:end -->
