# WSL Containers ガイド（解説・セットアップ手順）

Windows から **Docker Desktop なし**で Linux コンテナを動かす **WSL Containers (WSLC)** について、
仕組み・要件・セットアップ手順・エンタープライズ統制を 1 ファイルの HTML にまとめたガイドです。
Microsoft 公式のパブリックプレビュー発表（**2026-06-29 / WSL 2.9.3**）を一次情報としています。

## 内容

- [`wsl-containers-guide.html`](wsl-containers-guide.html) — 本体（ブラウザで開くだけ。外部依存なし）

セクション構成:

1. WSL Containers とは
2. 2 つの記事（公式 / Qiita 予習記事）の関係
3. Qiita「確認したいこと」× 公式の答え合わせ
4. 仕組み・アーキテクチャ（virtiofs / consomme / GPU / SDK）
5. エンタープライズ統合（Intune・GPO・Defender for Endpoint）
6. Docker Desktop との違い
7. セットアップ手順
8. 動作確認・サンプルコマンド
9. 未確認・注意点

## 確度バッジ

各記述の裏取り度合いを色分けしています:

- **公式** — Microsoft 公式ブログ / リリースノートで確認
- **背景・要検証** — 一般知識に基づく補足、または追加確認が必要
- **未確認** — 現時点で公式情報がない項目

## 注意

- パブリックプレビュー時点（2026-06）の情報です。**GA（2026 年秋予定）までに仕様が変わる可能性**があります。
- pre-release チャネル限定（`wsl --update --pre-release` / WSL 2.9.3+）。本番運用は非推奨です。
- 導入時は必ず [公式ブログ](https://devblogs.microsoft.com/commandline/wsl-container-is-now-available-for-public-preview/) の最新情報を確認してください。

## 主な出典

- [WSL container is now available for public preview](https://devblogs.microsoft.com/commandline/wsl-container-is-now-available-for-public-preview/) — Microsoft (Windows Command Line)
- [microsoft/WSL Release 2.9.3](https://github.com/microsoft/WSL/releases/tag/2.9.3)
- [Defender for Endpoint plug-in for WSL](https://learn.microsoft.com/en-us/defender-endpoint/mde-plugin-wsl) — Microsoft Learn
- [Qiita（ochtum 氏）予習記事](https://qiita.com/ochtum/items/6e6da3f0c841f5773954)

## ローカルで開く

```bash
# Linux/WSL から Windows 既定ブラウザで開く例
explorer.exe wsl-containers-guide.html
```

> 任意: GitHub Pages で公開する場合は、ファイル名を `index.html` にするか Pages 設定でルートを指定してください。
