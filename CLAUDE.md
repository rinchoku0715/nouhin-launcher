# 上々 納品書（nouhin-launcher）

居酒屋グループ「上々」の納品書アプリ（本体は Google Apps Script のウェブアプリ）を、スマホのホーム画面から開くための入口ページ。
このリポジトリには入口の HTML だけがあり、納品書アプリ本体のコードは入っていない。

- オーナー：林直樹（ユーザー。エンジニアではないので、説明はやさしい日本語で、結果と使い方を中心に）
- 返答・コミットメッセージ・PR は日本語
- 上々の関連アプリ：Jパーキング（`rinchoku0715/jyoujyou-parking-app`）、発注・仕入れ管理（`rinchoku0715/jyoujyou-shiire`）、Jシフト（シフト管理、Google Apps Script）

## ファイル

- `index.html`：「上々　納品書」の見出しと「開く →」ボタン。押すと GAS のウェブアプリ（`script.google.com/macros/s/…/exec`）へ移動する
- `app.html`：GAS のウェブアプリを画面いっぱいの `<iframe>` で表示する。読み込み中は「アプリを開いています…」、6秒たっても開かないときは「開かない場合はこちら」のリンクを出す
- どちらも `apple-touch-icon` を data URI（JPEG）で埋め込み、`apple-mobile-web-app-title` は「上々　納品書」。ホーム画面に追加したときの名前とアイコンになる

## 作業の注意

- ビルドの仕組みやパッケージはない。HTML を直接直す
- GAS の URL を変えるときは、`index.html` と `app.html` の両方（`app.html` は `<iframe src>` とリンクの2か所）を同じ値にそろえる
- アプリ名を変えるときは、`<title>`・`apple-mobile-web-app-title`・見出しをすべてそろえる
- アイコンの data URI はとても長い行なので、編集では壊さないように扱う（差し替えるときは画像から作り直す）
- 公開の方法（GitHub Pages など）はこのリポジトリからは分からない。変える前にユーザーに確認する
