# Flet Counter Application

このプロジェクトは、Fletを使用して作成されたカウンターアプリケーションです。ユーザーはボタンをクリックして数値を増減させることができます。アクセシビリティや非同期処理のバージョンも含まれています。

## インストール

このプロジェクトをローカルにクローンし、必要な依存関係をインストールするには、以下の手順に従ってください。

```bash
git clone https://github.com/yourusername/flet-counter.git
cd flet-counter
pip install -r requirements.txt
```

## 使用方法

プロジェクトを実行するには、以下のコマンドを使用します。

```bash
python apps/counter/counter.py
```

または、アクセシビリティ機能を持つバージョンを実行するには、次のコマンドを使用します。

```bash
python apps/counter/counter-accessible.py
```

非同期処理を使用するバージョンを実行するには、次のコマンドを使用します。

```bash
python apps/counter/counter-async.py
```

ブラウザで `http://localhost:8501` にアクセスすると、カウンターアプリケーションが表示されます。

## 構成ファイル

- `counter.py`: 基本的なカウンターアプリケーションの実装です。
- `counter-accessible.py`: アクセシビリティ機能を追加したカウンターアプリケーションです。セマンティクスデバッガーをトグルするためのキーボードショートカットが含まれています。
- `counter-async.py`: 非同期処理を使用したカウンターアプリケーションです。ボタンのクリックイベントが非同期で処理されます。

## ライセンス

このプロジェクトはMITライセンスの下で公開されています。詳細はLICENSEファイルを参照してください。