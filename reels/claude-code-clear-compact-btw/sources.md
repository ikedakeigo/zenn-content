# 出典・確認記録

確認日：2026-10-18（Asia/Tokyo）。手元の Claude Code は 2.1.299。

| 主張 | 出典 |
|---|---|
| コンテキストは埋まるほど性能が落ちる | [Best practices for Claude Code](https://code.claude.com/docs/en/best-practices)（冒頭） |
| 同じ問題を2回より多く直したら `/clear` して、学んだことを入れたプロンプトでやり直す | 同上「Course-correct early and often」 |
| 失敗パターン：Correcting over and over／The kitchen sink session（関係ないタスクの間で `/clear`） | 同上「Avoid common failure patterns」 |
| `/compact <instructions>`（例：`/compact Focus on the API changes`）、上限が近づくと自動で要約 | 同上「Manage context aggressively」 |
| CLAUDE.md に要約時に残すものを書ける（例："When compacting, always preserve the full list of modified files and any test commands"） | 同上「Manage context aggressively」 |
| `Esc`×2／`/rewind` の部分要約（Summarize from here / up to here） | 同上「Manage context aggressively」 |
| チェックポイントは Bash コマンドや外部プロセスによる変更を記録しない | 同上「Rewind with checkpoints」 |
| `Esc`×2 は入力欄が空のときに巻き戻しメニューを開く（文字があれば入力を消す） | [Interactive mode](https://code.claude.com/docs/en/interactive-mode)「General controls」 |
| `/btw`：メインの会話履歴に入らない／ツールを使えず会話にある情報だけで答える／作業中でも使える／1問1答／直近20往復の `/btw` を次の質問に引き継ぐ | 同上「Side questions with /btw」 |
| `/clear` 後も前のセッションは保存され、`/resume` で再開できる | [Manage sessions](https://code.claude.com/docs/en/sessions)「Manage context within a session」 |

## 検証記録

- 上記はすべて公式ドキュメントを読んで確認したもの。記事・リール内の `/clear`・`/compact`・`/btw` の入力例は、この環境で実際に実行して返答を確かめたものではない（未検証）
- `/compact` シーンのメーター（90% → 30%）はイメージで、実測値ではない（リール内に「※数字はイメージ」と表示）
- Codex レビュー（2026-10-18）：記事について中3件・低4件の指摘があり、全件を公式ドキュメントで確認して反映済み
