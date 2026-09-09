# 整体院のためのAI活用ゼミ — 資料サイト

第1回「AIが喜ぶ指示書のつくり方」のスライド資料（全35枚）。素の HTML 1枚で完結する静的サイト。

## 公開URL

| 配信先 | URL |
|---|---|
| GitHub Pages（push で自動反映） | https://mi386883-ikumi.github.io/hpb-dashboard/ai-seminar/ |
| Vercel | 接続後にここへ記入 |

## 操作

- `←` `→` / スペース … スライド送り
- `O` … 目次（クリックでジャンプ）
- `T` … ライト / ダーク切替（localStorage に保存）
- `#12` のようにURL末尾を付けるとその番号から開く
- 右下「印刷」→ ブラウザの印刷ダイアログ。**用紙A4・横**で全35枚をPDF化できる（配布資料用）

## 更新のしかた

`index.html` を直して push するだけ。ビルド作業もパッケージも無し。

```bash
git add ai-seminar && git commit -m "セミナー資料の更新" && git push
```

## Vercel へつなぐ（初回だけ）

1. https://vercel.com にGitHubアカウントでログイン
2. **Add New… → Project** → `mi386883-ikumi/hpb-dashboard` を Import
3. **Root Directory** に `ai-seminar` を指定（ここが重要）
4. Framework Preset は **Other**。Build Command と Output Directory は空のままで Deploy

以後は `git push` するたびに自動で再デプロイされる。
独自ドメインを付ける場合は Vercel の Settings → Domains から。

## 設定メモ

- `vercel.json` … 画像のキャッシュ設定のみ。ビルド設定は不要
- **検索エンジンに載せたくない場合** … `index.html` 冒頭の `<meta name="robots" content="noindex, nofollow">` のコメントアウトを外す
- OGP画像 `ogp.png` の参照先は GitHub Pages の絶対URL。Vercelの独自ドメインに寄せる場合は `index.html` の `og:image` / `twitter:image` を差し替える

## 第2回以降を足すとき

`01/` `02/` … のようにフォルダを切り、`index.html` を各回の資料にして、ルートに回一覧のページを置くのがおすすめ。
（現状は第1回をルートに置いている）
