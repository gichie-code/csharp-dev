# C# 開発環境（Docker）

このリポジトリは、C# の簡単なコンソールアプリケーションをローカルに C# の環境をインストールせずに開発・実行できるようにする Docker 環境を提供します。

## 構成

```
csharp-dev/
├── docker-compose.yml
├── Dockerfile
├── .dockerignore
├── .gitignore
└── src/
```

## 前提

- Docker および Docker Compose がインストールされていること

## 初期セットアップ

以下のコマンドで `src/` に新しい C# プロジェクトを作成します。

```bash
docker compose run --rm csharp-dev dotnet new console -o .
```

## ビルドと実行

以下のコマンドで C# アプリケーションをビルドし、実行します。

```bash
cd src
docker compose run --rm csharp-dev dotnet run
```

## 備考

- プロジェクトファイル（csharp-dev.csproj）などは初期セットアップ後に src/ 配下に生成されます。
- この手順は、ホストマシンに C# の実行環境（.NET SDK）が存在しなくても動作します。
- すべての開発作業はホスト側の src/ ディレクトリで行い、コンテナは実行専用として使います。

## ライセンス

MIT License
