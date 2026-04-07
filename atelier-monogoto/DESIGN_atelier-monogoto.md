# DESIGN.md — atelier-monogoto.jp

> 参考サイト: https://atelier-monogoto.jp/
> 分析日: 2026-04-07
> 業種: 建築設計事務所 コーポレートサイト（札幌拠点）

---

## 1. Visual Theme & Atmosphere

- **デザイン方針**: ミニマリスト・自然志向。気候風土・環境をデザインの軸に据えた、静かで誠実な表現
- **密度**: 情報密度は低め。写真と余白が支配的なギャラリー型レイアウト
- **キーワード**: 静寂、自然、誠実、北海道、建築美

---

## 2. Color Palette & Roles

> 建築設計事務所らしいナチュラル・アースカラーベース。写真の風景色が全体の印象を形成する。

### Primary（ブランドカラー）

- **Primary** (`#2c2c2c`): テキスト・見出しに使う落ち着いた濃いグレー
- **Primary Dark** (`#111111`): ホバー・強調時

### Semantic（意味的な色）

- **Danger** (`#c0392b`): エラー
- **Warning** (`#e67e22`): 警告
- **Success** (`#27ae60`): 成功

### Neutral（ニュートラル）

- **Text Primary** (`#2c2c2c`): 本文テキスト
- **Text Secondary** (`#777777`): 補足・キャプション・ラベル
- **Text Disabled** (`#bbbbbb`): 非活性状態
- **Border** (`#dddddd`): 区切り線
- **Background** (`#ffffff`): ページ背景（純白）
- **Surface** (`#f5f4f1`): わずかに暖色を帯びたオフホワイト（アースカラー系）

---

## 3. Typography Rules

### 3.1 和文フォント

- **ゴシック体**: Noto Sans JP or 游ゴシック（清潔感のある読みやすいゴシック体を推定）
- **明朝体**: 見出しやアクセントに Noto Serif JP または游明朝を使用の可能性あり

### 3.2 欧文フォント

- **サンセリフ**: Helvetica Neue または Inter 系
- **セリフ**: 見出し装飾に Georgia 等の可能性あり

### 3.3 font-family 指定（推定）

```css
/* 本文 */
font-family: "Noto Sans JP", "游ゴシック", "Yu Gothic", sans-serif;

/* 見出し */
font-family: "Noto Serif JP", "游明朝", "Yu Mincho", serif;
```

### 3.4 文字サイズ・ウェイト階層（推定）

| Role | Font | Size | Weight | Line Height | Letter Spacing | 備考 |
|------|------|------|--------|-------------|----------------|------|
| Display | セリフ | 48–64px | 300 | 1.2 | 0.08em | トップのキャッチ |
| Heading 1 | ゴシック/セリフ | 32–40px | 400 | 1.3 | 0.05em | ページ大見出し |
| Heading 2 | ゴシック | 22–28px | 400 | 1.4 | 0.03em | セクション見出し |
| Heading 3 | ゴシック | 16–20px | 500 | 1.5 | 0.02em | 小見出し |
| Body | ゴシック | 14–16px | 400 | 1.9–2.0 | 0.04em | 本文 |
| Caption | ゴシック | 11–13px | 400 | 1.6 | 0.06em | 写真キャプション等 |

### 3.5 行間・字間

- **本文の行間 (line-height)**: 1.9〜2.0（ゆったりとした余白感）
- **見出しの行間**: 1.2〜1.4
- **本文の字間 (letter-spacing)**: 0.04em
- **見出しの字間**: 0.05〜0.08em（少し開けて格調を出す）

### 3.6 禁則処理・改行ルール

```css
word-break: break-all;
overflow-wrap: break-word;
line-break: strict;
```

### 3.7 OpenType 機能

```css
/* 見出し */
font-feature-settings: "palt" 1, "kern" 1;
```

### 3.8 縦書き

該当なし

---

## 4. Component Stylings

### Buttons

**Primary（リンク型）**
- スタイル: テキストリンク or 細いアンダーライン付き
- Text: `#2c2c2c`
- Hover: アンダーライン変化 or 薄い透過効果

**Secondary（アウトライン型）**
- Background: `transparent`
- Text: `#2c2c2c`
- Border: 1px solid `#2c2c2c`
- Padding: 10px 28px
- Border Radius: 0px（建築らしいスクエア）

### Cards（Works・Projects一覧）

- Background: `#ffffff`
- Border: なし
- Border Radius: 0px
- Padding: 0px（画像エッジトゥエッジ）
- テキスト: 画像下部に余白を持ってタイトル配置
- Shadow: なし

### Navigation

- スタイル: 水平テキストナビ（About / Works / Projects / Journal / Contact）
- ロゴ: 左上または中央
- カラー: 白背景に濃いグレーのテキスト
- モバイル: ハンバーガーメニューに切り替え

### Footer

- 構成: 会社名・住所・電話番号・Instagram・Facebook
- スタイル: シンプルなテキスト配置、過度な装飾なし

---

## 5. Layout Principles

### Spacing Scale

| Token | Value |
|-------|-------|
| XS | 8px |
| S | 16px |
| M | 32px |
| L | 56px |
| XL | 88px |
| XXL | 120px |

### Container

- Max Width: 1200px
- Padding (horizontal): 32–64px

### Grid

- Columns: 12カラム（デスクトップ）
- Gutter: 24px
- Works一覧: 2〜3カラムのグリッド
- 詳細ページ: 1カラム（大きな写真中心）

### セクション構成

1. **Hero** — 複数のWebP画像（スライドショーまたはグリッド配置）
2. **Feature Project** — Salon de Monogoto等の注目プロジェクト
3. **Journal / News** — 最新記事3件のリスト
4. **SNS** — Instagram・Facebookへのリンク
5. **Footer** — 企業情報・連絡先

---

## 6. Depth & Elevation

| Level | Shadow | 用途 |
|-------|--------|------|
| 0 | none | 全要素（完全フラット） |

---

## 7. Animation & Interaction

- **方針**: 控えめで洗練されたアニメーション（推定）
- **フェードイン**: スクロールトリガーによる要素の opacity フェード
- **画像ホバー**: 微妙なスケールアップ or オーバーレイ表示
- **ページ遷移**: フェード系のスムーズな遷移

---

## 8. Visual Style

- **写真**: 建築・空間・風景の高品質WebP写真が主役。小樽の海や北海道の自然環境を積極活用
- **フォトスタイル**: 自然光、落ち着いたトーン、ノイズ少なめ
- **アイコン**: SNSアイコン（Instagram・Facebook）のみ、シンプルなSVG
- **イラスト**: 使用なし

---

## 9. Do's and Don'ts

### Do（推奨）

- 写真は高解像度・高品質のものを横幅いっぱいに使う
- テキスト量は最小限。写真が語る設計思想を前面に
- ナビゲーションはシンプルなフラット型で5項目以内
- 余白（ホワイトスペース）を贅沢に使い、落ち着きを演出
- 建築の「正確さ」を体現するスクエアなレイアウト

### Don't（禁止）

- 装飾的なアイコンや過剰なグラフィック要素
- 原色・高彩度のアクセントカラー
- 情報を詰め込みすぎたカード
- 過剰なアニメーション（建築の静謐感を損なう）

---

## 10. Responsive Behavior

### Breakpoints

| Name | Width | 説明 |
|------|-------|------|
| Mobile | ≤ 768px | 1カラム、フルスクリーン写真 |
| Tablet | ≤ 1024px | 2カラムグリッド |
| Desktop | > 1024px | 2〜3カラムグリッド |

### タッチターゲット

- 最小サイズ: 44px × 44px

### フォントサイズの調整

- モバイルでは本文 14px、見出しはデスクトップの 70〜80% に縮小

---

## 11. Agent Prompt Guide

### クイックリファレンス

```
Primary Color: #2c2c2c
Text Color: #2c2c2c
Secondary Text: #777777
Background: #ffffff
Surface: #f5f4f1
Font (本文): "Noto Sans JP", "游ゴシック", sans-serif
Font (見出し): "Noto Serif JP", "游明朝", serif
Body Size: 15px
Line Height: 1.95
Design Style: ミニマリスト・建築的・自然志向
```

### プロンプト例

```
atelier-monogoto.jpのデザインシステムに従って、Works一覧グリッドを作成してください。
- 背景: #ffffff
- テキスト: #2c2c2c（サブ: #777777）
- フォント (本文): "Noto Sans JP", sans-serif、14px, line-height 1.95
- カードは影なし・スクエア・エッジトゥエッジの画像配置
- 2〜3カラムのグリッドレイアウト、gutter 24px
- セクション間は 88–120px のホワイトスペース
- ホバーで画像に微妙なスケールアップ効果
```
