# WCAG-sim

# WCAG 配色シミュレーター

雑誌の表紙写真をアップロードすると、元の配色と WCAG 準拠配色を並べて比較し、コントラスト比を計算・評価できるシミュレーターです。

## 機能

- 📸 画像アップロード（ドラッグ＆ドロップ対応）
- 🎨 写真から主要色を6色自動抽出
- ⚖️ WCAG 2.1 AA / AAA 基準のコントラスト比計算
- 🖼️ 元の配色 vs WCAG 準拠配色のマガジン風プレビュー比較
- 🗳️ どちらが魅力的か投票機能

## GitHub Pages へのデプロイ手順

### 1. リポジトリを作成

```bash
git init
git add .
git commit -m "initial commit"
```

### 2. GitHub にプッシュ

```bash
# GitHub で新しいリポジトリを作成後
git remote add origin https://github.com/あなたのユーザー名/wcag-magazine-simulator.git
git branch -M main
git push -u origin main
```

### 3. GitHub Pages を有効化

1. リポジトリの **Settings** タブを開く
2. 左メニュー **Pages** をクリック
3. Source を **Deploy from a branch** に設定
4. Branch を **main** / **/ (root)** に設定
5. **Save** をクリック

数分後に `https://あなたのユーザー名.github.io/wcag-magazine-simulator/` で公開されます。

## ローカルでの動作確認

```bash
# Python 3
python -m http.server 8000

# Node.js (npx)
npx serve .
```

ブラウザで `http://localhost:8000` を開いてください。

## 技術仕様

- **外部依存なし** — Pure HTML / CSS / Vanilla JS
- Canvas API による色抽出
- WCAG 2.1 相対輝度計算式によるコントラスト比算出
- Google Fonts（Noto Serif JP / Noto Sans JP / DM Mono）

## WCAG コントラスト比の基準

| レベル | 通常テキスト | 大テキスト（18pt以上 or 14pt Bold以上） |
|--------|-------------|----------------------------------------|
| AA     | 4.5:1 以上  | 3:1 以上                               |
| AAA    | 7:1 以上    | 4.5:1 以上                             |
