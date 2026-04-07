# DESIGN.md — nutrad.co.jp

> 参考サイト: https://nutrad.co.jp/
> 分析日: 2026-04-07
> 業種: 家具・ものづくり（OEM/ODM）コーポレートサイト

---

## 1. Visual Theme & Atmosphere

- **デザイン方針**: ミニマル・プレミアム・クラフトマンシップ。装飾を極力排除し、写真とテキストだけで世界観を表現
- **密度**: ゆったりとした余白重視。セクションごとに大きな呼吸感を持たせたメディア型レイアウト
- **キーワード**: 上品、職人的、グローバル、本物感、静謐

---

## 2. Color Palette & Roles

> 実サイトはミニマルな無彩色ベース。アクセントカラーはほぼ使用せず、写真の色彩が視覚的な彩りを担う。

### Primary（ブランドカラー）

- **Primary** (`#1a1a1a`): メインテキスト・見出し・ロゴ等に使用する深みのある黒
- **Primary Dark** (`#000000`): ホバー時や強調要素

### Semantic（意味的な色）

- **Danger** (`#cc3333`): エラー・削除（控えめ使用）
- **Warning** (`#e5a000`): 警告（控えめ使用）
- **Success** (`#2e7d32`): 成功・完了（控えめ使用）

### Neutral（ニュートラル）

- **Text Primary** (`#1a1a1a`): 本文テキスト（純黒を避け、わずかにソフトな黒）
- **Text Secondary** (`#666666`): 補足テキスト、キャプション
- **Text Disabled** (`#aaaaaa`): 非活性状態のテキスト
- **Border** (`#e0e0e0`): 区切り線、細いボーダー
- **Background** (`#ffffff`): ページ全体の背景色（純白）
- **Surface** (`#f7f7f7`): カードや補助セクションの背景

---

## 3. Typography Rules

### 3.1 和文フォント

- **ゴシック体**: Adobe Fonts (Typekit) 経由で読み込み。具体的なフォント名は未確定だが、ヒューマニストサンセリフ系（例: A1ゴシック, TBゴシック等）が推定される
- **明朝体**: 使用の可能性あり（見出し・キャッチコピーで格調を演出）

### 3.2 欧文フォント

- **サンセリフ**: Adobe Fonts 経由。ヒューマニスト系サンセリフ（例: Gill Sans, Frutiger 系）
- **セリフ**: キャッチコピーや装飾的見出しに使用の可能性あり

### 3.3 font-family 指定（推定）

```css
/* 本文 */
font-family: "Adobe Gothic", "游ゴシック", "Yu Gothic", sans-serif;

/* 見出し・キャッチ */
font-family: "Adobe Fonts SeriffFamily", "游明朝", "Yu Mincho", serif;
```

### 3.4 文字サイズ・ウェイト階層（推定）

| Role | Font | Size | Weight | Line Height | Letter Spacing | 備考 |
|------|------|------|--------|-------------|----------------|------|
| Display | ゴシック/セリフ | 56–72px | 300–400 | 1.2 | 0.05em | ヒーローキャッチ |
| Heading 1 | ゴシック | 36–48px | 400 | 1.3 | 0.03em | セクション大見出し |
| Heading 2 | ゴシック | 24–32px | 400 | 1.4 | 0.03em | サブ見出し |
| Heading 3 | ゴシック | 18–20px | 500 | 1.5 | 0.02em | 小見出し |
| Body | ゴシック | 15–16px | 400 | 1.8–2.0 | 0.04em | 本文 |
| Caption | ゴシック | 12–13px | 400 | 1.6 | 0.05em | 補足・注釈 |

### 3.5 行間・字間

- **本文の行間 (line-height)**: 1.8〜2.0（日本語の長文は余裕を持たせる）
- **見出しの行間**: 1.2〜1.4
- **本文の字間 (letter-spacing)**: 0.04em
- **見出しの字間**: 0.03〜0.05em

### 3.6 禁則処理・改行ルール

```css
word-break: break-all;
overflow-wrap: break-word;
line-break: strict;
```

### 3.7 OpenType 機能

```css
/* 見出し・ナビゲーション */
font-feature-settings: "palt" 1, "kern" 1;
```

### 3.8 縦書き

該当なし

---

## 4. Component Stylings

### Buttons

**Primary（テキストリンク型）**
- スタイル: テキストのみ or アンダーライン、矢印アイコン付き
- Text: `#1a1a1a`
- Hover: アンダーライン付与 or 色変化
- 例: "View more →", "Visit website →"

**Secondary（アウトライン型）**
- Background: `transparent`
- Text: `#1a1a1a`
- Border: 1px solid `#1a1a1a`
- Padding: 12px 32px
- Border Radius: 0px（スクエア）

### Cards

- Background: `#ffffff`
- Border: なし or 薄いボーダー `#e0e0e0`
- Border Radius: 0px（スクエア）
- Padding: 24–40px
- Shadow: なし（フラットデザイン）

### Navigation

- スタイル: ハンバーガーメニュー（"menu / close" テキスト表示）
- ロゴ: 左上配置
- リンク: シンプルなテキスト、余白たっぷり
- カラー: 白背景 or 透過背景にダーク文字

---

## 5. Layout Principles

### Spacing Scale

| Token | Value |
|-------|-------|
| XS | 8px |
| S | 16px |
| M | 32px |
| L | 64px |
| XL | 96px |
| XXL | 128px |

### Container

- Max Width: 1200–1440px
- Padding (horizontal): 40–80px

### Grid

- Columns: 12カラム（デスクトップ）/ 4カラム（モバイル）
- Gutter: 24–32px
- 主な使い方: 2カラム（テキスト＋画像）, 3カラム（サービス一覧）

### セクション構成

1. **Hero** — フルスクリーン画像 + キャッチコピー
2. **Philosophy** — テキスト左 + 画像右（2カラム）
3. **Brand** — ブランド紹介カード（2〜3列グリッド）
4. **Factory** — 横スクロールまたはグリッドの画像ギャラリー
5. **Service** — 3カラムカードレイアウト
6. **Footer** — 会社情報・ナビゲーション・コピーライト

---

## 6. Depth & Elevation

| Level | Shadow | 用途 |
|-------|--------|------|
| 0 | none | ほぼ全要素（フラットデザイン） |
| 1 | `0 2px 4px rgba(0,0,0,0.06)` | カード（使用最小限） |

---

## 7. Animation & Interaction

- **トランジション**: `transition-fade` クラスによる `opacity` + `transform: translateY` の組み合わせ
- **デュレーション**: 0.5〜1.0秒（ゆっくりとした上品な動き）
- **イージング**: ease-out 系（自然に止まる動き）
- **スクロール連動**: スムーズスクロール＋スクロールトリガーによる要素フェードイン
- **DOM変更検知**: Arrive.js によるダイナミックな要素への対応

---

## 8. Visual Style

- **写真**: 高品質なプロダクト・工場写真が主役。余白を意識した余裕のある配置
- **画像形式**: WebP自動変換（EWWW Image Optimizer）で表示速度と品質を両立
- **アイコン**: SVGロゴのみ（装飾的アイコンは最小限）
- **カラー写真のトーン**: ナチュラル・ウォーム系。過度な加工なし

---

## 9. Do's and Don'ts

### Do（推奨）

- 写真に十分な余白（パディング）を与え、「見せ場」を作る
- テキストは最小限に。見出し＋短い説明文の組み合わせ
- セクション間は大きなホワイトスペースで区切る
- ボタンはテキストリンク形式を優先（過度な装飾は避ける）
- フォントは Adobe Fonts でブランド一貫性を確保

### Don't（禁止）

- 過度なグラデーションや装飾的エフェクトの使用
- 情報を詰め込みすぎたカード・セクション
- 強いアクセントカラー（ブランドイメージを損なう）
- スクエアでない写真トリミング（アスペクト比を統一する）

---

## 10. Responsive Behavior

### Breakpoints

| Name | Width | 説明 |
|------|-------|------|
| Mobile | ≤ 768px | 1カラム、余白縮小 |
| Tablet | ≤ 1024px | 2カラム |
| Desktop | > 1024px | フルレイアウト |

### タッチターゲット

- 最小サイズ: 44px × 44px

### フォントサイズの調整

- モバイルでは本文 14–15px、見出しはデスクトップの 65〜75% に縮小

---

## 11. Agent Prompt Guide

### クイックリファレンス

```
Primary Color: #1a1a1a
Text Color: #1a1a1a
Secondary Text: #666666
Background: #ffffff
Surface: #f7f7f7
Font (本文): "Adobe Gothic", "游ゴシック", sans-serif
Body Size: 15–16px
Line Height: 1.9
Design Style: ミニマル・プレミアム・ホワイトスペース重視
```

### プロンプト例

```
nutrad.co.jpのデザインシステムに従って、ブランド紹介セクションを作成してください。
- 背景: #ffffff
- テキスト: #1a1a1a（セカンダリ: #666666）
- フォント: "游ゴシック", sans-serif、本文 15px, line-height 1.9
- カードは影なし・スクエアな枠
- セクション間は 96–128px のホワイトスペース
- ボタンはテキストリンク形式（"View more →"）
- 写真は横幅いっぱいに使いゆったりと配置
```
