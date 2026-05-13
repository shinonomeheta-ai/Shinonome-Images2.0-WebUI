# Shinonome Images 2.0 WebUI

OpenAI の **gpt-image-1 / gpt-image-2** を使った画像生成 Web ツールです。  
サーバー不要・1ファイル完結で動作し、APIキーはブラウザの `localStorage` にのみ保存されます。

![License](https://img.shields.io/badge/license-MIT-blue.svg)

**作者：** [@shinonome_hema](https://x.com/shinonome_hema) / [note](https://note.com/shinonome_hema)  
> 使い方の詳しい解説記事は note で公開予定です。質問・フィードバックは X の DM またはリプライからどうぞ。

---

## ✨ 機能

- **テキストから画像生成**（gpt-image-1 / gpt-image-2 切り替え対応）
- **参考画像付き生成**（画像アップロード・ドラッグ&ドロップ・クリップボード貼り付け対応）
- **モデル切り替え**（gpt-image-1 / gpt-image-2 をボタンで即時切り替え）
- **サイズ・品質・出力形式・モデレーション設定**
- **画像の選択・一括ダウンロード**
- **ライトボックス表示・クリップボードコピー**
- **設定の自動保存**（プロンプト・モデル・各種設定をブラウザに保存）
- **レート制限時の自動リトライ**（指数バックオフ）

---

## 🚀 使い方

### 1. ページを開く

https://shinonomeheta-ai.github.io/Shinonome-Images2.0-WebUI/ 
をブラウザで開いてください。  
または `index.html` をダウンロードしてダブルクリックでも動作します。

### 2. APIキーを設定する

初回アクセス時にセットアップ画面が表示されます。  
OpenAI の APIキー（`sk-...`）を入力して保存してください。

> APIキーの取得方法は後述の「[APIキー取得・設定方法](#-apiキー取得設定方法)」を参照してください。

### 3. 画像を生成する

1. **モデルを選択**（gpt-image-1 または gpt-image-2）
2. **プロンプトを入力**（日本語・英語どちらでも可）
3. 必要に応じて**参考画像**を追加
4. **サイズ・品質**などを設定
5. 「**画像を生成**」ボタンをクリック

---

## 🔑 APIキー取得・設定方法

### Step 1 — OpenAI アカウントを作成する

1. [platform.openai.com](https://platform.openai.com) にアクセス
2. 「Sign up」からアカウントを作成（Googleアカウントでも登録可）

### Step 2 — クレジットをチャージする

画像生成 API は有料のため、事前にクレジットの追加が必要です。

1. [platform.openai.com/settings/organization/billing](https://platform.openai.com/settings/organization/billing) を開く
2. 「Add to credit balance」をクリック
3. クレジットカードを登録してチャージ（最低 $5 から）

> **料金の目安（2026年5月時点）**
> | モデル | 品質 | サイズ | 1枚あたりの料金 |
> |---|---|---|---|
> | gpt-image-1 | medium | 1024×1024 | 約 $0.04 |
> | gpt-image-2 | medium | 1024×1024 | 約 $0.05 |
> | gpt-image-2 | high | 1024×1024 | 約 $0.21 |

### Step 3 — APIキーを発行する

1. [platform.openai.com/api-keys](https://platform.openai.com/api-keys) を開く
2. 「**Create new secret key**」をクリック
3. 名前を入力（例：`Shinonome WebUI`）して「Create」
4. 表示された `sk-...` の文字列をコピー（**この画面でしか確認できません**）

### Step 4 — WebUI にAPIキーを設定する

1. 本ツールを開く
2. 初回セットアップ画面が表示される
3. コピーした `sk-...` を貼り付けて「APIキーを保存してはじめる」をクリック

> APIキーは変更・削除したい場合は右上の「⚙ APIキー設定」から操作できます。

---

## ⚡ モデルについて

| モデル | 特徴 | 推奨 Tier |
|---|---|---|
| **gpt-image-1** | 安定・低コスト・Tier 1から利用可 | Tier 1〜 |
| **gpt-image-2** | 高品質・多言語テキスト描画対応 | Tier 2〜 |

### Usage Tier について

OpenAI の API にはレート制限があり、累計の支払い額によって Tier が上がります。

| Tier | 条件 | gpt-image-2 の上限 |
|---|---|---|
| Tier 1 | $5 以上チャージ | 5 images/分 |
| Tier 2 | 累計 $50 消費 + 7日以上 | 20 images/分 |
| Tier 3 | 累計 $100 消費 + 7日以上 | 50 images/分 |

現在の Tier は [platform.openai.com/settings/organization/limits](https://platform.openai.com/settings/organization/limits) で確認できます。

---

## ⚙️ 設定項目

| 項目 | 説明 |
|---|---|
| 生成枚数 | 1〜4枚 |
| 品質 | low / medium / high |
| サイズ | 1024×1024〜2560×1440（16の倍数のみ有効） |
| 出力形式 | PNG / JPEG / WebP |
| モデレーション | auto / low |

---

## 🔒 セキュリティについて

- APIキーはあなたのブラウザの `localStorage` にのみ保存されます
- サーバーには一切送信されません
- 他の人がこのページを開いても、あなたのAPIキーは見えません（各自で入力が必要）

---

## 📄 ライセンス

MIT License

---

## 🙏 クレジット

- 画像生成：[OpenAI Images API](https://platform.openai.com/docs/guides/images)
- フォント：[Google Fonts](https://fonts.google.com)（Syne / Noto Sans JP / DM Mono）

---

## 👤 作者

- **X（Twitter）**：[@shinonome_hema](https://x.com/shinonome_hema)
- **note**：[shinonome_hema](https://note.com/shinonome_hema)

> 使い方の詳しい解説記事は note で公開予定です。  
> 質問・フィードバックは X の DM またはリプライからどうぞ。
