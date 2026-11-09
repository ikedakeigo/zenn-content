# 出典・確認記録

確認日：2026-11-09（Asia/Tokyo）。公式ドキュメントは 2026-11-05 に取得した版と 2026-11-09 に取り直した版を比べ、memory・context-window・commands のページが同じ内容であることを確認した。

| 主張（シーン） | 出典 |
|---|---|
| 新しい会話は、前の会話の中身なしで始まる（だから会話で伝えた注意は次に持ち越されない）（0） | [How Claude remembers your project](https://code.claude.com/docs/en/memory) 冒頭：“Each Claude Code session begins with a fresh context window.” |
| 「覚えて」と頼むと自動メモリに保存される。CLAUDE.md に入れたいときは「CLAUDE.md に追加して」と頼むか、自分で編集する（1・4） | 同上「View and edit with /memory」：“When you ask Claude to remember something, like "always use pnpm, not npm" ... Claude saves it to auto memory. To add instructions to CLAUDE.md instead, ask Claude directly, like "add this to CLAUDE.md," or edit the file yourself via /memory.” |
| 自動メモリは Claude が書くメモで、好みや直したことに使う。CLAUDE.md はルール（1・4） | 同上「CLAUDE.md vs auto memory」の表（Who writes it：You / Claude、Use for：Your preferences, corrections you give Claude ...）。日本語版でも「自動メモリ」「誰が書くか：あなた／Claude」（[日本語版](https://code.claude.com/docs/ja/memory)） |
| 保存すると “Saved 2 memories” のような表示が出る（1） | 同上「How it works」：“When you see messages like "Saved 2 memories" or "Recalled 2 memories" in the Claude Code interface ...” |
| 目次（MEMORY.md）は会話の最初に読み込まれ、中身のファイルは必要なときに読まれる（2） | 同上「How it works」：“The first 200 lines of MEMORY.md, or the first 25KB, whichever comes first, are loaded at the start of every conversation.”／“Claude Code doesn't load topic files ... at startup. Claude reads them on demand ...” |
| /memory で自動メモリの中身を見られ、フォルダも開ける。中身はただの Markdown で、編集・削除できる（3） | 同上「View and edit with /memory」「Audit and edit your memory」：“Auto memory files are plain markdown you can edit or delete at any time.”、[Commands](https://code.claude.com/docs/en/commands) の `/memory`：“view auto memory entries” |
| プロジェクトの CLAUDE.md は Git でチームと共有できる（4） | 同上「Choose where to put CLAUDE.md files」の Project instructions：“Team members via source control” |
| 自動メモリはそのPCだけで、ほかのPCやクラウド環境とは共有されない（4・6） | 同上「Storage location」：“Auto memory is machine-local. ... Files are not shared across machines or cloud environments.” |
| 保存されるのは好み・直したこと・進行中の作業や決定など（5） | 同上「Auto memory」の4種類：user（working preferences）／feedback（corrections you give Claude）／project（ongoing work, deadlines, and decisions）／reference |
| コードを見れば分かること、CLAUDE.md に書いてあることは保存しない。毎回保存するわけではない（5） | 同上「Auto memory」：“Claude skips anything it can derive from the codebase ... It also skips anything your CLAUDE.md files already say.”／“Claude doesn't save something every session.” |
| 手元のPCで使うときは最初からオンで、/memory で切り替えられる（キャプション） | 同上「Enable or disable auto memory」：“Auto memory is on by default in local sessions.”／“To toggle it, open /memory in a session and use the auto memory toggle” |
| 例の「npm じゃなくて pnpm」（0・1） | 同上の例 “always use pnpm, not npm” をそのまま使った |
| 新しい会話で自動メモリが読み込まれたかは /context で確かめられる（公開前の確認） | [Explore the context window](https://code.claude.com/docs/en/context-window)「Check your own session」：“run /context ... including which CLAUDE.md and auto memory files loaded” |

## フックと題材の根拠（実データ）

[metrics.md](../../metrics.md)（Windsor.ai、2026-11-09 22:19 JST 時点）のリール10本。再生の上位3本はコンテキスト管理シリーズで、上位2本のフックは #27（毎回の手間）の型。

## 検証記録

- 上の表はすべて公式ドキュメントを読んで確認したもの。この環境はクラウド上のセッションで撮影に使うPCとは別のため、次の3つは実際に試していない（未検証）
  - 「覚えて」と頼んだときの保存の表示の文言
  - `/memory` の画面と項目名
  - 新しい会話で自動メモリが読み込まれること（`/context` の表示）
- 動画の画面は Remotion で作る再現イメージ（キャプションに「※動画内の画面は説明用のイメージです」と記載）
- <!-- TODO: 実機で試した日、Claude Code のバージョン（claude --version の結果）、保存の表示の文言、/context で自動メモリが見えたかを書く -->
- Codex レビュー：未実施
