# Sample 合同会社 — Hero Cube (Modal-Preview Edition)

> 不動産FP専門・東京 / 自動回転する3Dキューブで6面メニューを表現したヒーローセクション。
> **遷移先ページが未作成**でも動くよう、クリック→**フルスクリーンモーダルプレビュー**で内容を確認できます。

![demo](./demo.gif)

> デモGIFは `demo.gif` として後日追加してください（任意）。

---

## ✨ Features

- 🎲 **CSS 3D Transforms** による立方体ヒーロー（6面 / `perspective: 800px`）
- 🔄 **自動Y軸回転**（`0.3deg / frame`、`requestAnimationFrame`）
- 🖱️ **ドラッグで手動回転**、操作後 1.8 秒で自動回転を再開
- 🎯 **前面検出ロジック** — 現在手前にある面のボタンのみクリック可能（`pointer-events: auto`）
- 🪟 **モーダルプレビュー**（本ページ後追加可） — `data-modal` 属性でフックし、会社概要・サービス等のサンプルテキストを即表示
- ⌨️ **キーボード操作**: `← →` で横回転、`↑ ↓` で縦傾き、`ESC` でモーダル閉じる
- 💾 **localStorage** で自動回転ON/OFF状態を保存
- ♿ **ARIA属性 / focus管理 / reduced-motion** 対応
- 📱 **レスポンシブ**（モバイルではキューブサイズを縮小）
- 🌐 **GitHub Pages デプロイ可能** / 1 ファイル完結（外部依存なし）

---

## 🧭 6 Faces ↔ Modals

| 面      | ラベル              | `data-modal` | 遷移先（後日）        |
| ------- | ------------------- | ------------ | --------------------- |
| front   | 会社概要            | `company`    | `/company.html`       |
| back    | お問い合わせ        | `contact`    | `/contact.html`       |
| right   | サービス            | `service`    | `/service.html`       |
| left    | 製品                | `product`    | `/product.html`       |
| top     | ブログ              | `blog`       | `/blog/index.html`    |
| bottom  | トップ（閉じる）    | —            | (トップへスクロール)  |

---

## 🛠 Tech Stack

- **HTML5** — セマンティックなマークアップ、`role="dialog"` / `aria-modal`
- **CSS3** — `transform-style: preserve-3d`, custom properties, radial gradient, backdrop-filter
- **Vanilla JS (ES6+)** — 外部ライブラリなし。`requestAnimationFrame` / `PointerEvents` / `localStorage`
- **Fonts** — `Noto Sans JP` / `Hiragino Kaku Gothic ProN` を優先するシステムフォントスタック

---

## 🚀 Quick Start

```bash
# 1. クローン
git clone https://github.com/<your-org>/sample-hero.git
cd sample-hero

# 2. ブラウザで開く
open index.html        # macOS
start index.html       # Windows
```

GitHub Pages 公開時は、リポジトリ Settings → Pages → Branch: `main` / `/ (root)` を指定するだけです。

---

## 🔁 遷移先ページを追加したら

`index.html` のモーダルトリガーを `<a href="...">` に置き換えてください。

```html
<!-- Before: モーダルプレビュー -->
<button data-modal="company">会社概要</button>

<!-- After: 本ページへ遷移 -->
<a href="/company.html" class="face-link">会社概要</a>
```

※ `.face button` に当たっている CSS を `.face-link` に流用すれば見た目は変わりません。

---

## 📁 File Structure

```
.
├── index.html      # 本体（HTML + CSS + JS 一体型）
├── README.md       # このファイル
└── demo.gif        # デモGIF（任意）
```

---

## 📝 License

© 2026 Sample 合同会社 — All rights reserved.
（コードは社内利用・改変自由）

---

## 🏷 Version

`v1.0.0 — Modal-Preview Auto-Rotate Cube (2026/4/22)`
