# pranaedge-site

pranaedge.com の静的サイト。アプリごとのページ・プライバシーポリシー・利用規約・サポートを置く。
ビルド不要（素のHTML/CSS）。

## 構成

```
index.html              トップ（アプリ一覧・連絡先）
style.css               共通スタイル（ライト/ダーク対応）
sodachi/index.html      Sodachi 紹介
sodachi/privacy.html    プライバシーポリシー
sodachi/terms.html      利用規約
sodachi/support.html    サポート・FAQ
```

新しいアプリは `<app>/` ディレクトリを増やして、トップの一覧にカードを足す。

## 公開（Cloudflare Workers 静的アセット・無料）

`wrangler.jsonc` に設定済み。Cloudflare にログイン済みの Mac（`npx wrangler whoami` で確認）なら、次の1コマンドで公開される。

```bash
npx wrangler deploy
```

- カスタムドメイン `pranaedge.com` / `www.pranaedge.com` は `wrangler.jsonc` の `routes` で割当済み（DNS は自動）
- `.assetsignore` に書いたファイル（README・設定ファイル・.git）は公開されない
- `.html` 付きの URL は拡張子なしの URL にリダイレクトされる（例: `/sodachi/privacy.html` → `/sodachi/privacy`）。リンクは拡張子なしで書く
- GitHub（mastom1/pranaedge-site）はソース管理用。push しても自動デプロイはされないので、更新したら `npx wrangler deploy` を実行する

## アプリ側で使うURL

- 利用規約: https://pranaedge.com/sodachi/terms
- プライバシーポリシー: https://pranaedge.com/sodachi/privacy
- サポート（App Store のサポートURL）: https://pranaedge.com/sodachi/support
- マーケティングURL: https://pranaedge.com/sodachi/
