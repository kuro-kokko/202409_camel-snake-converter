# camel-snake-converter

<https://kuro-kokko.github.io/202409_camel-snake-converter/>

このリポジトリは 2024 上期課題の 1 作目です。

## 作成経緯

個人開発で大量のスネークケースをキャメルケースに変換する必要があり、手作業によるタイポ防止目的で作成。

## 開発環境・使用技術

### 言語・ライブラリ

- jQuery
- Bootstrap
- Toastify (通知トースト表示用)

### ツール類

- Visual Studio Code
- Claude 3.5 Sonnet (生成 AI・開発補助)

## 実装内容

- キャメルケース、スネークケース、パスカルケースのいずれかの入力値をそれぞれに変換
- ワンクリックでクリップボードにコピーする機能
- レスポンシブ対応

### 工夫した点

- 煩雑な操作を行わず手軽に使用できるよう極力シンプルな設計・レイアウト・機能にした。
  - 設計着手前は変換パターン毎にタブやプルダウンで画面を切り替える予定だったが、不要な操作が増えるだけなのでタブで 1 入力で 3 つの値を出力させるようにした。
  - フロントエンドのみで動作可能のため、(当該ページを読込済の前提で)オフラインでも動作可能。

### 悪い点

- クリアボタンがない
  - 単純に実装を忘れていた。ユーザビリティを考慮するまでもなく実装するべきだった
- 1単語ずつしか変換できない
  - csv ヘッダから DB カラム名に変換する場合等を考慮し、カンマ等の区切り文字で複数出力に対応した方が使い勝手が良いと感じた。
- 悪意のある値を入力された場合の処置が不足している
  - コピーされる内容の長さに制限が無いため、予期しない大量のデータがクリップボードにコピーされる恐れがある

## 総括

- フロントエンドで完結しているアプリなので、Electron 等でデスクトップアプリ化しても良いと感じた。
  - Web アプリ版と比較した場合、バージョンアップ対応が不利な気がするので一長一短？
- 正規表現周りが苦手なので早目に改善したい。
