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

## 公開（Cloudflare Pages・無料）

1. このディレクトリを GitHub に push する（`gh repo create pranaedge-site --public --source=. --push`）
2. Cloudflare ダッシュボード → Workers & Pages → 作成 → Pages → 「Git に接続」で `pranaedge-site` を選ぶ
   - フレームワークプリセット: なし / ビルドコマンド: 空 / ビルド出力ディレクトリ: `/`
3. デプロイ後、Pages プロジェクトの「カスタムドメイン」で `pranaedge.com` と `www.pranaedge.com` を追加（DNS は自動設定される）
4. 以後は `main` に push するだけで自動デプロイ

Git を使わない場合は、同じ画面の「アセットをアップロード」でこのフォルダをドラッグしても公開できる。

## アプリ側で使うURL

- 利用規約: https://pranaedge.com/sodachi/terms.html
- プライバシーポリシー: https://pranaedge.com/sodachi/privacy.html
- サポート（App Store のサポートURL）: https://pranaedge.com/sodachi/support.html
- マーケティングURL: https://pranaedge.com/sodachi/
