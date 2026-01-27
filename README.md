# 茨城県 Vibe Coding ワークショップ LP

2026年2月5日（木）開催の「Vibe Codingワークショップ」参加者向けランディングページ

## 概要

| 項目 | 内容 |
|------|------|
| 開催日時 | 2026年2月5日（木）13:00〜15:00 |
| 会場 | 鯉渕学園農業栄養専門学校 |
| 参加者数 | 最大15名 |

## 技術スタック

- HTML5 + CSS3（インライン）+ Vanilla JavaScript (ES6+)
- 認証: Web Crypto API (SHA-256) + sessionStorage
- 外部ライブラリ不使用
- 単一HTMLファイル完結

## ファイル構成

```
ibaraki-ai-workshop-20260205/
├── index.html    # メインLP（全機能統合）
└── README.md     # 本ファイル
```

## セットアップ

### 1. パスワードの設定

1. パスワードを決定（例: `workshop2026`）
2. SHA-256ハッシュを生成
   - ツール: https://emn178.github.io/online-tools/sha256.html
   - 入力: `ibaraki-vibe-coding-2026` + `パスワード` （ソルト + パスワード）
   - 例: `ibaraki-vibe-coding-2026workshop2026` を入力
3. `index.html` の `CONFIG.PASSWORD_HASH` を生成したハッシュに置き換え

```javascript
const CONFIG = {
    PASSWORD_HASH: 'ここに生成したハッシュを貼り付け',
    // ...
};
```

### 2. 参加者データの設定

`index.html` の `PARTICIPANTS_DATA` 配列を編集:

```javascript
const PARTICIPANTS_DATA = [
    { no: 1, name: '山田 太郎', templateUrl: 'https://docs.google.com/document/d/XXXXX1/edit' },
    { no: 2, name: '鈴木 花子', templateUrl: 'https://docs.google.com/document/d/XXXXX2/edit' },
    // 参加者を追加...
];
```

### 3. アンケートの設定（任意）

Airtable等のフォーム埋め込みURLを設定する場合、`index.html` のアンケートセクションを編集:

```html
<div class="survey-embed">
    <iframe
        src="[ここにAirtableの埋め込みURLを入力]"
        width="100%"
        height="600"
        style="background: transparent;">
    </iframe>
</div>
```

## デプロイ

### GitHub Pages

1. このリポジトリをGitHubにプッシュ
2. Settings → Pages → Source: main branch
3. 数分後にURLが発行

### Vercel / Netlify

1. リポジトリを連携
2. 自動デプロイ（設定不要）

## ローカルでの確認

`index.html` をブラウザで直接開くか、簡易サーバーを起動:

```bash
# Python 3
python -m http.server 8000

# Node.js (npx)
npx serve .
```

## 運営チェックリスト

- [ ] パスワードを決定しハッシュを設定
- [ ] 参加者名簿を確定
- [ ] Google Docsテンプレートを参加者分作成
- [ ] 各参加者のテンプレートURLを `PARTICIPANTS_DATA` に追加
- [ ] アンケートURLを設定（任意）
- [ ] デプロイしてURLを確認
- [ ] 当日パスワードを参加者に配布

## 問い合わせ

- MetagriLabo: https://metagri-labo.com/contact/
