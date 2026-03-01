# kento-scrapegraph — 仕様書 (SPEC_JA)

> このファイルは kento-repos-setup.sh によって自動生成されました。

## 基本情報

| 項目 | 値 |
|---|---|
| リポジトリ名 | kento-scrapegraph |
| アップストリーム | ScrapeGraphAI/Scrapegraph-ai |
| カテゴリ | Scraping |
| Tier | 3 |
| 主要言語 | Python |
| ライセンス | MIT License |
| GitHub Stars | 22812 |
| デフォルトポート | N/A |
| 生成日 | 2026-03-01 |

## 概要

Python scraper based on AI

## アーキテクチャ概要

<!-- アップストリームの構成に基づいて記載する -->

- **フロントエンド**: (未記載 — 要調査)
- **バックエンド**: (未記載 — 要調査)
- **データベース**: (未記載 — 要調査)
- **依存サービス**: (未記載 — 要調査)

## ポート設定

| 環境 | ポート |
|---|---|
| ローカル開発 | N/A |
| Docker Compose | N/A |
| 本番 (Reverse Proxy 経由) | 443 (HTTPS) |

## 導入手順

### 前提条件

- Docker / Docker Compose がインストール済みであること
- 必要な環境変数が `.env` ファイルに設定済みであること

### ローカル起動

```bash
# リポジトリのクローン (既にクローン済みの場合はスキップ)
git clone https://github.com/fujikento/kento-scrapegraph.git ~/kento-scrapegraph
cd ~/kento-scrapegraph

# 環境変数のコピー
cp .env.example .env  # ファイル名はリポジトリにより異なる場合あり

# コンテナ起動
docker compose up -d
```

### アップストリームの変更を取り込む

```bash
cd ~/kento-scrapegraph
git fetch upstream
git merge upstream/main  # ブランチ名はリポジトリにより異なる場合あり
git push origin main
```

## カスタマイズ方針

<!-- fork 後に加える予定の変更を記載する -->

- [ ] 日本語 UI 対応 (必要な場合)
- [ ] 社内認証 (Authelia) との統合
- [ ] 監視エンドポイント (`/healthz`) の確認・追加
- [ ] カスタム設定ファイルの追加

## 監視・運用

- **ヘルスチェック URL**: `http://localhost:N/A/` (要確認)
- **ログ確認**: `docker compose logs -f`
- **バックアップ**: (未定 — 要設計)

## 関連リンク

- アップストリーム GitHub: https://github.com/ScrapeGraphAI/Scrapegraph-ai
- フォーク先 GitHub: https://github.com/fujikento/kento-scrapegraph
- ライセンス原文: https://github.com/ScrapeGraphAI/Scrapegraph-ai/blob/main/LICENSE

## 変更履歴

| 日付 | 変更内容 | 担当 |
|---|---|---|
| 2026-03-01 | 初回スペック自動生成 | kento-repos-setup.sh |
