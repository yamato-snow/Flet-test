# Flet Counter Flutter Application

このプロジェクトは、Fletを使用して作成されたカウンターアプリケーションです。モバイルデバイスでのテストを目的としています。

## インストール

このプロジェクトをローカルにクローンし、必要な依存関係をインストールするには、以下の手順に従ってください。

```bash
git clone https://github.com/yourusername/flet-counter-flutter.git
cd flet-counter-flutter
```

### Dockerを使用する場合

Dockerを使用してアプリケーションを実行するには、以下のコマンドを使用します。

```bash
docker build -t flet-counter .
docker run -p 8080:8080 flet-counter
```

ブラウザで `http://localhost:8080` にアクセスすると、カウンターアプリケーションが表示されます。

## 使用方法

アプリケーションを実行するには、以下のコマンドを使用します。

```bash
python main.py
```

## 構成ファイル

- `main.py`: アプリケーションのエントリーポイントで、ページの設定やUIコンポーネントを管理します。
- `Dockerfile`: アプリケーションをDockerコンテナとして実行するための設定ファイルです。
- `requirements.txt`: プロジェクトに必要なPythonパッケージのリストです。
- `fly.toml`: Fly.ioでのデプロイ設定ファイルです。
- `assets/manifest.json`: ウェブアプリケーションのマニフェストファイルで、アプリのメタデータを定義します。

## ライセンス

このプロジェクトはMITライセンスの下で公開されています。詳細はLICENSEファイルを参照してください。