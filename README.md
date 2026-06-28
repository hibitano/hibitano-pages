# hibitano-pages (staging in Kago repo)

このディレクトリは **public GitHub repo `hibitano/hibitano-pages`** にコピーするための staging。
`hibitano-pages` repo は **Cloudflare Pages** プロジェクトに接続され、
カスタムドメイン `apps.hibitano.net` で公開される。複数アプリ共通のホスト先。

## ファイル構成

```
pages/
├── CNAME                          # 旧 GitHub Pages 用 (Cloudflare Pages では未使用、互換のため残置)
├── index.html                     # https://apps.hibitano.net/ の Apps 一覧
└── kago/
    ├── index.html                 # https://apps.hibitano.net/kago/ — Kago LP
    └── privacy/
        └── index.html             # https://apps.hibitano.net/kago/privacy/ (ja/en)
```

新しいアプリを追加するときは `pages/<app-name>/...` を作って同じパターンで増やす。

## ホスティング構成

- **本番 URL**: https://apps.hibitano.net/
- **Kago プライバシーポリシー**: https://apps.hibitano.net/kago/privacy/
- **Cloudflare Pages プロジェクト**: `kago-pages` (将来 `hibitano-apps` などにリネーム検討)
- **接続 repo**: `hibitano/hibitano-pages` (main ブランチ自動デプロイ)
- **暫定 URL**: https://kago-pages.pages.dev/

## 更新方法

1. `docs/PRIVACY_POLICY.md` を編集 (マスタ)
2. このディレクトリの `kago/privacy/index.html` も対応する箇所を更新
3. 別チェックアウトしている `hibitano-pages` repo に内容をコピー → push
4. Cloudflare Pages が自動デプロイ (数十秒〜数分)

(将来: Kago repo の Action で自動コピー or 単一 repo 化を検討)
