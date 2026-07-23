# ITパスポート 漢字用語辞典

`index.html` 1ファイルだけで完結する静的サイトです(データも埋め込み済み、外部APIやGASは不要)。

## GitHub Pagesで公開する手順

1. GitHubで新しいリポジトリを作成(例: `it-passport-glossary`)
2. `index.html` をリポジトリのルートに置いてpush
   ```
   git init
   git add index.html
   git commit -m "add glossary site"
   git branch -M main
   git remote add origin https://github.com/<ユーザー名>/<リポジトリ名>.git
   git push -u origin main
   ```
3. GitHubのリポジトリ画面で **Settings → Pages** を開く
4. "Build and deployment" の Source を **Deploy from a branch** にし、Branch を `main` / `/(root)` に設定して Save
5. 数分後、`https://<ユーザー名>.github.io/<リポジトリ名>/` で公開されます

## 用語を追加・修正したいとき

`index.html` 内の `const DATA = [...]` の部分に、以下の形式でオブジェクトを追加/編集してください(画数は自動で判定されるので、正しい合計画数を入れてください)。

```js
{"kanji":"用語","yomi":"よみ","strokes":20,"ja":"日本語の説明","en":"English explanation"}
```

## 収録内容
- 全135語(基礎〜応用)、画数7〜72画
- 画数検索: 十の位ごとの候補 → 画数順のスクロールリスト
- よみ検索: ひらがな1文字目 → 2文字目 → 五十音順のスクロールリスト
