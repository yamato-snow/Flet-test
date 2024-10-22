# Flet Counter Flutter Application

このプロジェクトは、Fletを使用して作成されたカウンターアプリケーションです。モバイルデバイスでのテストを目的としています。

## 目次

- [プロジェクトの概要](#プロジェクトの概要)
- [必要条件](#必要条件)
- [環境構築](#環境構築)
- [アプリケーションの実行](#アプリケーションの実行)
- [Dockerを使用した実行](#dockerを使用した実行)
- [デプロイ手順](#デプロイ手順)
- [構成ファイルの説明](#構成ファイルの説明)
- [ライセンス](#ライセンス)

## プロジェクトの概要

このアプリケーションは、ユーザーがボタンをクリックして数値を増減させることができるカウンターアプリケーションです。モバイルデバイスでの使用を考慮して設計されています。

## 必要条件

- Python 3.7以上
- Docker（Dockerを使用する場合）
- Git（リポジトリをクローンするため）

## 環境構築

1. **リポジトリのクローン**

   ```bash
   git clone https://github.com/yourusername/flet-counter-flutter.git
   cd flet-counter-flutter
   ```

2. **Python環境のセットアップ**

   Pythonの仮想環境を作成し、依存関係をインストールします。

   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   venv\Scripts\activate  # Windows
   pip install -r requirements.txt
   ```

## アプリケーションの実行

アプリケーションをローカルで実行するには、以下のコマンドを使用します。

```bash
python main.py
```

ブラウザで `http://localhost:8080` にアクセスすると、カウンターアプリケーションが表示されます。

## Dockerを使用した実行

Dockerを使用してアプリケーションを実行する場合、以下の手順に従ってください。

1. **Dockerイメージのビルド**

   ```bash
   docker build -t flet-counter .
   ```

2. **Dockerコンテナの実行**

   ```bash
   docker run -p 8080:8080 flet-counter
   ```

ブラウザで `http://localhost:8080` にアクセスすると、カウンターアプリケーションが表示されます。

## デプロイ手順

このアプリケーションをFly.ioにデプロイする手順は以下の通りです。

1. **Fly.io CLIのインストール**

   Fly.io CLIをインストールします。詳細は[Fly.ioの公式ドキュメント](https://fly.io/docs/getting-started/installing-flyctl/)を参照してください。

2. **Fly.ioにログイン**

   ```bash
   flyctl auth login
   ```

3. **アプリケーションの作成**

   ```bash
   flyctl launch
   ```

   プロンプトに従ってアプリケーションの設定を行います。

4. **デプロイ**

   ```bash
   flyctl deploy
   ```

デプロイが完了したら、Fly.ioが提供するURLにアクセスしてアプリケーションを確認できます。

## 構成ファイルの説明

- `main.py`: アプリケーションのエントリーポイントで、ページの設定やUIコンポーネントを管理します。
- `Dockerfile`: アプリケーションをDockerコンテナとして実行するための設定ファイルです。
- `requirements.txt`: プロジェクトに必要なPythonパッケージのリストです。
- `fly.toml`: Fly.ioでのデプロイ設定ファイルです。
- `assets/manifest.json`: ウェブアプリケーションのマニフェストファイルで、アプリのメタデータを定義します。

## ライセンス

このプロジェクトはMITライセンスの下で公開されています。詳細はLICENSEファイルを参照してください。