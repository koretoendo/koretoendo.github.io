# 研究者ホームページ（GitHub Pages 用）

ビルド不要の HTML/CSS だけで作った、3ページ構成の簡素なホームページです。

```
index.html        ホーム（名前・身分・研究領域）
papers.html       論文
talks.html        講演
style.css         見た目（3ページ共通）
images/           favicon など
.nojekyll         GitHub Pages に Jekyll 処理をさせないための空ファイル
```

## 1. 公開する（初回のみ）

1. GitHub で新しいリポジトリを作成します。名前は **`ユーザー名.github.io`** にします
   （例：ユーザー名が `tyamada` なら `tyamada.github.io`）。Public にしてください。
2. このフォルダの中身を、リポジトリの直下に置いて push します。

   ```bash
   cd homepage
   git init
   git add .
   git commit -m "Initial homepage"
   git branch -M main
   git remote add origin https://github.com/ユーザー名/ユーザー名.github.io.git
   git push -u origin main
   ```

   コマンドを使わない場合は、リポジトリ画面の「Add file → Upload files」でファイルをドラッグしても構いません。
3. リポジトリの **Settings → Pages** を開き、「Build and deployment」の Source を
   **Deploy from a branch**、Branch を **main / (root)** にして Save します。
4. 1〜2分後に `https://ユーザー名.github.io/` で表示されます。

> リポジトリ名を別の名前（例：`homepage`）にした場合、URL は `https://ユーザー名.github.io/homepage/` になります。

## 2. 内容を書き換える

- **名前とふりがな**：3つの HTML すべての `<h1>` と `<title>` を書き換えます（各ページに同じ見出しがあります）。
- **身分・研究領域**：`index.html` の `<dl class="info">` の中を書き換えます。項目を増やすときは `<dt>見出し</dt><dd>内容</dd>` を追加します。
- **論文・講演**：`papers.html` / `talks.html` の `<li>…</li>` を、新しいものが上になるように追加します。番号は自動で振られます。自分の名前は `<b>…</b>` で太字になります。
- **ページを増やす**：既存のページをコピーし、3ページすべての `<nav>` にリンクを追加します。

## 3. 更新する

ファイルを編集して commit / push すれば、数分で反映されます。

```bash
git add .
git commit -m "Update publications"
git push
```

## 補足

- 独自ドメインを使う場合は Settings → Pages の「Custom domain」で設定します。
