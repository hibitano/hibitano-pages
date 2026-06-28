# hibitano-pages (staging in Kago repo)

このディレクトリは、後で別の **public GitHub repo** にコピーするための staging。
本番ホスト先は `hibitano.net` を独自ドメインとして `hibitano-pages` repo で GitHub Pages 公開する。

## ファイル構成

```
pages/
├── CNAME                          # 「hibitano.net」と書かれたファイル (GitHub Pages 用)
├── index.html                     # https://hibitano.net/ のトップ
└── kago/
    └── privacy/
        └── index.html             # https://hibitano.net/kago/privacy/ のプライバシーポリシー (ja/en)
```

## セットアップ手順 (1 回限り)

詳細は `docs/HANDOFF.md` 参照。要点:

1. GitHub 上で **public repo `hibitano-pages`** を作成
2. このディレクトリの中身を repo の root にコピー → push
3. repo の Settings → Pages で:
   - Source: `Deploy from a branch`、Branch: `main` / `/(root)`
   - Custom domain: `hibitano.net`
4. DNS (お名前.com 等) で:
   - `A` レコード or `CNAME` を `hibitano.github.io` に向ける
   - HTTPS は GitHub の Let's Encrypt が自動付与
5. 数分〜数十分後、`https://hibitano.net/kago/privacy/` にアクセス可能になる

## 更新方法

- `docs/PRIVACY_POLICY.md` を編集
- 本ディレクトリの `kago/privacy/index.html` も対応する箇所を更新
- `hibitano-pages` repo にもコピーして push

(将来: Kago repo の Action で自動コピー or 単一 repo 化を検討)
