# preleaker

[日本語](#日本語) | [English](#english)

## 日本語

どうせ漏れるなら、漏れる前に自分で漏らす。ネット上のニックネームから架空の個人情報を生成し、X に「先出し」するネタサイトです。

デモ：<https://noxelwork.com/preleaker>

### 使い方

1. 性別を選び、ネット上のニックネームを入力して「照会する」
2. 個人情報照会票が表示される
3. 「X で先出しする」で投稿画面を開く。「画像を保存」で照会票を画像にできる

同じニックネームと性別からは、何度照会しても同じ結果になります。

### 生成される情報

すべて架空です。入力内容は保存も送信もされず、X に投稿するときだけ投稿文として X に渡ります。

- ニックネームのハッシュを種にした擬似乱数で生成
- 町名は「名簿ヶ丘」「炎上台」のような実在しない名前
- マイナンバーは末尾の検査用数字をわざと外した、実在し得ない番号
- クレカ番号はチェックディジット（Luhn）をわざと外した、カードとして成立しない番号

### 構成

- `index.html` に全機能。ほかは favicon と OGP 画像のみ。外部から読み込むのは Google Fonts と html2canvas
- noxelwork.com の Cloudflare Workers の静的アセットとして配信（Worker のスクリプトは通らない）

## English

A joke site: if your personal data is going to leak anyway, leak it yourself first. Enter an online nickname and it generates fake personal data you can "pre-leak" on X. The UI is Japanese only.

Demo: <https://noxelwork.com/preleaker>

- The same nickname and gender always give the same result
- Everything is fictional and generated in the browser; your input leaves the page only as the post text when you post to X
- Town names are made up, My Number (Japan's individual number) values deliberately fail their check digit, and credit card numbers deliberately fail the Luhn check

Everything lives in `index.html`, alongside a favicon and an OGP image (Google Fonts and html2canvas come from CDNs). Served as static assets of the noxelwork.com Cloudflare Worker, without running its script.
