# Pixel Agents Web

**[English](README.en.md) | [한국어](README.ko.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | [Español](README.es.md) | [Português (BR)](README.pt-BR.md) | [Français](README.fr.md) | [Русский](README.ru.md) | [Deutsch](README.de.md)**

[Pixel Agents](https://github.com/pablodelucca/pixel-agents) のスタンドアロン Web ブラウザ版 — AI コーディングエージェントがキャラクターとして動き出すアニメーションピクセルアートオフィスです。

![Pixel Agents スクリーンショット](../public/Screenshot.jpg)

## 機能

- **アニメーションピクセルアートキャラクター** — 各エージェントは歩行、タイピング、読書アニメーション付きの固有キャラクターを持ちます
- **リアルタイム活動追跡** — エージェントの活動（コード記述、ファイル読取、コマンド実行）に応じてキャラクターがアニメーションします
- **オフィスレイアウトエディタ** — 内蔵エディタで床、壁、家具を配置してオフィスをデザインできます
- **吹き出し** — エージェントが入力待ちまたは権限が必要な時のビジュアルインジケータ
- **サウンド通知** — エージェントがタスクを完了した時のオプション通知音
- **サブエージェント可視化** — サブエージェントが親と紐づけられた別キャラクターとしてスポーンします
- **永続レイアウト** — オフィスデザインは localStorage に保存されます
- **多様なキャラクター** — [JIK-A-4, Metro City](https://jik-a-4.itch.io/metrocity-free-topdown-character-pack) ベースの6種類の多様なキャラクター
- **VSCode 不要** — Webブラウザで完全に動作します

<p align="center">
  <img src="../public/characters.png" alt="Pixel Agents キャラクター" width="320" height="72" style="image-rendering: pixelated;">
</p>

## クイックスタート

```bash
git clone https://github.com/pablodelucca/pixel-agents-web.git
cd pixel-agents-web
npm install
npm run dev
```

ブラウザで `http://localhost:5173` を開いてください。

## 使い方

1. Webブラウザでアプリを開きます
2. **+ Agent** ボタンをクリックしてデモキャラクターを生成します
3. シミュレートされたコーディング活動でキャラクターが動くのを観察します
4. **Layout** をクリックしてオフィスエディタを開き、空間をカスタマイズします
5. **Settings** でレイアウトのエクスポート/インポートやサウンド設定を管理します

## プロダクションビルド

```bash
npm run build
npm run preview
```

ビルドファイルは `dist/` に生成されます — Netlify、Vercel、GitHub Pages などの静的ホスティングにデプロイできます。

## 技術スタック

- **React 19** + TypeScript
- **Vite** — 開発とビルド
- **Canvas 2D** — ピクセルパーフェクトレンダリング
- **BFS パスファインディング** — キャラクター移動
- **キャラクターステートマシン**（待機 → 歩行 → タイピング/読書）

## 仕組み

このプロジェクトは [Pixel Agents VSCode 拡張機能](https://github.com/pablodelucca/pixel-agents) のスタンドアロン Web ポートです。オリジナルの拡張機能は Claude Code の JSONL トランスクリプトファイルを監視してエージェントの活動を追跡します。この Web 版は：

- Canvas API を使用してブラウザで直接すべてのアセット（キャラクタースプライト、壁タイル、床タイル）を読み込みます
- VSCode 拡張機能のメッセージブリッジをスタンドアロン Web ブリッジに置き換えます
- リアルなエージェント活動を生成するデモシミュレーションシステムを提供します
- オリジナルと100%同一の Canvas 2D レンダリングを維持します

## クレジット

- オリジナルプロジェクト：[pablodelucca/pixel-agents](https://github.com/pablodelucca/pixel-agents)
- キャラクタースプライト：[JIK-A-4, Metro City](https://jik-a-4.itch.io/metrocity-free-topdown-character-pack)

## ライセンス

このプロジェクトは [MIT ライセンス](../LICENSE)の下でライセンスされています。
