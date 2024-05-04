## 目次

1. [プロジェクト名](#プロジェクト名)
2. [プロジェクトについて](#プロジェクトについて)
3. [環境](#環境)
4. [開発環境構築](#開発環境構築)
5. [コンテナ作成・起動](#コンテナ作成・起動)
6. [動作確認](#動作確認)
7. [コンテナへのアクセス](#コンテナへのアクセス)
8. [コンテナの停止](#コンテナの停止)

## プロジェクト名

rails-docker

## プロジェクトについて

Docker のコンポーネント上で Ruby on Rails を立ち上げる

## 環境

| 言語・フレームワーク | バージョン |
| -------------------- | ---------- |
| Ruby                 | 3.2.2      |
| Ruby on rails        | 7.0.6      |
| PostgresSQL          | 12         |

その他のパッケージのバージョンは Gemfile を参照

## 開発環境構築

```
git clone git@github.com:umedanaoyuki/rails-docker.git
```

### 初回起動時のみ実施

```
# webのコンテナを起動して rails db:createを実行（コンテナは削除される）
docker-compose run --rm web  rails db:create
```

### コンテナ作成・起動

```
# コンテナ作成＆起動
# -d をつけてバックグラウンドで起動
docker-compose up -d
```

```
# 起動中のコンテナの確認
docker-compose ps
```

### 動作確認

```
http://localhost:3000
```

にアクセスできるか確認  
アクセスできたら成功

### コンテナの停止

```
# コンテナの停止(停止するだけ)
docker-compose stop

# ストップして停止＆コンテナも削除
docker-compose down
```
