# フォント変換ツール — かわいい文字に一瞬変身 ✨

![Single File](https://img.shields.io/badge/Single%20HTML-Yes-7c9aff)
![Build](https://img.shields.io/badge/Build-None-70ffd2)
![Language](https://img.shields.io/badge/Vanilla-JS%2FCSS-ff8ad6)
![License](https://img.shields.io/badge/License-MIT-informational)

アルファベットや数字を、Unicode の“見た目違い”の仲間に置き換えて、**かわいい雰囲気の文字**へ変換するシングルページアプリ（SPA）です。**単一の `font-cute.html`** だけで動作し、ビルド・サーバー不要。SNSやプロフィールでのちょい足しに最適。

> **English summary**: A single-file SPA that maps ASCII letters/digits to cute Unicode variants (circled, bold, script, double-struck, fullwidth, etc.). Copy results with one tap, add decorations, share via URL. No build step.

---

## ✨ 主な特長

* **単一HTML**：`font-cute.html` を開くだけ。依存なし
* **スタイル8種**：丸文字・手書き風・太字・二重線・サンセリフ・等幅・ゴシック風・全角
* **デコ機能**：♡ ✨ ★ 🎀 を**両はし**or**文字の間**に自動挿入
* **コピーが簡単**：クリックでコピー／失敗時は自動で選択 → **Ctrl/Cmd + C** 案内
* **一括コピー**：表示中の全スタイルをまとめてコピー
* **URL共有**：`?text=...` 付きリンクを生成
* **テーマ切替**：Light / Dark を保存
* **モダンUI**：ガラス質感・アクセントカラー・レスポンシブ

---

## 🧪 デモ＆実行方法（ローカル）

最速で試すには VS Code の **Live Server** が便利です。

```bash
# 1) VS Code を開く
# 2) 新規ファイル: font-cute.html を作成して、このリポジトリのHTMLをコピペ
# 3) Live Server をインストールして、右下の「Go Live」をクリック
#    → http://localhost:5500/ などで起動
```

> クリップボード仕様上、**`file://` 直接オープンだとコピーが拒否**されることがあります。`http://localhost` または `https://` で開くのが確実です。

---

## 🖥️ 画面

```
┌ フォント変換ツール ──────────────────────┐  🌗 テーマ  🔗 共有  一括コピー
│ 入力テキスト [ Hello from shimarin ]                              │
│ オプション: 大文字/小文字 | デコ(♡/✨/★/🎀) | 配置(両はし/間)      │
│─────────────────────────────────────────│
│ 変換結果（タップでコピー）                                        │
│  ▸ まる文字   Ⓗⓔⓛⓛⓞ ⓕⓡⓞⓜ ⓢⓗⓘⓜⓐⓡⓘⓝ  ♡                         │
│  ▸ ふわ文字   𝐇𝐞𝐥𝐥𝐨 𝐟𝐫𝐨𝐦 𝐬𝐡𝐢𝐦𝐚𝐫𝐢𝐧                                │
│  ...                                                             │
└──────────────────────────────────────────────────────────────┘
```

---

## 🚀 クイックスタート

1. `font-cute.html` をプロジェクトに追加
2. ブラウザで開く（おすすめ：Live Server で `http://localhost`）
3. テキストを入力 → 好きなスタイルを**クリックでコピー**
4. **デコ**や**大文字/小文字**、**配置**を調整
5. 共有ボタンで URL をコピー（または Web Share）

---

## 📚 使い方のポイント

* **コピー**：成功でトースト表示。失敗時は**自動で選択**→ `Ctrl/Cmd + C` で確実にコピー
* **デコ配置**：

  * **両はし**：`✨ Hello ✨` のように前後へ
  * **文字の間**：`H✨e✨l✨l✨o` のようにリズム感アップ
* **URL共有**：現在の入力を `?text=...` としてURLに反映（リロードや配布に便利）

---

## 🧠 仕組み（ざっくり）

* テキストは1文字ずつ走査し、`A–Z` / `a–z` / `0–9` に該当する場合、**Unicode 代替ブロック**のベースコードポイントへ置換
* 例：

  * **丸文字**: `Ⓐ (U+24B6)`〜、`ⓐ (U+24D0)`〜
  * **太字**: 数学用英数字記号ブロック `𝐀 (U+1D400)`〜
  * **二重線**: `𝔸 (U+1D538)`〜
  * **等幅**: `𝙰 (U+1D670)`〜
  * **全角**: `Ａ (U+FF21)`〜
* 日本語は置換せず、そのまま
