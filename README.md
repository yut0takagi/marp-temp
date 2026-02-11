# MARP テンプレート

![](https://github.com/yut0takagi/marp-temp/blob/main/demo.png?raw=true)

ビジネス向けの **Marp** スライド用テーマとサンプルテンプレートです。3色（`#F7F4EC`, `#C4CBD3`, `#323850`）の落ち着いたパレットで、社内発表・提案資料にそのまま使えます。

- **リポジトリ**: [https://github.com/yut0takagi/marp-temp](https://github.com/yut0takagi/marp-temp/tree/main)

---

## 特徴

- **カスタムテーマ `business`**: 左バー・上部タイトルバー付きの統一デザイン
- **スライドクラス**: 表紙（`lead`）、章（`chapter`）、通常（`ruled`）、強調（`inverse`）など
- **レイアウト**: 二段組・三段組、カード、KPI表示、バッジ・スタンプ・リボン
- **日本語対応**: フォント・行間を調整した読みやすい表示

---

## 必要な環境

- **Marp for VS Code**（推奨）  
  [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode) をインストールすると、プレビュー・PDF/HTML 出力が可能です。

または

- **Marp CLI**  
  `@marp-team/marp-cli` をインストールしてコマンドラインから PDF/HTML を生成できます。

---

## 使い方

### 1. リポジトリの取得

```bash
git clone https://github.com/yut0takagi/marp-temp.git
cd marp-temp
```

### 2. スライドの編集

- `template.md` を開いて内容を編集します。
- フロントマターで `theme: business` と `paginate: true` が指定されていることを確認してください。

```yaml
---
marp: true
theme: business
paginate: true
title: あなたのタイトル
author: あなたの名前
---
```

### 3. プレビュー（VS Code）

1. `template.md` を開く
2. エディタ右上の **「Open Preview to the Side」** または `Ctrl+Shift+V`（Mac: `Cmd+Shift+V`）でプレビューを表示
3. Marp 拡張が有効なら、スライド形式でプレビューされます

### 4. PDF / HTML の出力

**VS Code（Marp 拡張）の場合**

- プレビュー画面の **「Export Slide Deck」** から **PDF** または **HTML** を選択して保存

**Marp CLI の場合**

```bash
# 依存のインストール（初回のみ）
npm install -g @marp-team/marp-cli

# PDF に出力
marp template.md --pdf -o output.pdf

# HTML に出力
marp template.md --html -o output.html
```

`.marprc.yml` で `themes/business.css` が読み込まれるため、同じディレクトリで実行すればテーマが適用されます。

---

## プロジェクト構成

```
marp-temp/
├── .marprc.yml      # Marp 設定（テーマパス）
├── .vscode/
│   └── settings.json   # VS Code 用 Marp テーマパス
├── assets/
│   └── logo.svg        # ロゴなど画像用
├── themes/
│   └── business.css    # ビジネステーマ
├── template.md         # サンプルスライド（編集用の起点）
├── template.pdf        # サンプル PDF 出力例
├── demo.png            # README 用デモ画像
└── README.md
```

---

## スライドのクラス一覧

| クラス | 用途 |
|--------|------|
| `lead` / `cover-split` | 表紙（タイトル＋キッカー） |
| `chapter` | 章見出し（番号＋タイトル＋サブタイトル） |
| `ruled` | 通常スライド（上部ライン付き） |
| `inverse` | 背景反転（暗い背景で強調） |
| （クラスなし） | 標準レイアウト |

**レイアウト用クラス（HTML で使用）**

- `two-col` / `three-col`: 二段組・三段組のラッパー
- `card` / `card kpi`: カード・KPI 表示
- `callout`: 補足・注意の枠
- `badge` / `pill` / `chip` / `stamp` / `ribbon`: ラベル・スタンプ・リボン

`template.md` 内のコメント（`<!-- class: ... -->`）と HTML ブロックを参考に、必要なスライドをコピーしてアレンジしてください。

---

## カスタマイズ

- **テーマ色**: `themes/business.css` の `:root` 内の `--bg`, `--fg`, `--accent` などを変更すると、全体の色味を変えられます。
- **ロゴ**: `assets/logo.svg` を差し替え、スライド内で `![](assets/logo.svg)` のように参照できます。
- **別テーマ**: `themes/` に新しい CSS を追加し、`.marprc.yml` およびフロントマターの `theme:` で指定できます。

---

## ライセンス・利用について

このテンプレートは自由に改変・利用してかまいません。社内資料・勉強会・ブログ用など、用途に合わせてご利用ください。
