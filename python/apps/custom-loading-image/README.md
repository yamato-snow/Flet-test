# 🚀 シンプルなFletアプリケーション

## 📋 概要

このプロジェクトは、Fletを使用した基本的なWebアプリケーションのテンプレートです。
Hello Worldを表示する最小構成から始められます。

## 🔧 環境構築

### 必要条件

- Python 3.7以上
- pip (Pythonパッケージマネージャー)

### セットアップ手順

1. プロジェクトのクローン
```bash
git clone <your-repository-url>
cd <your-project-name>
```

2. 仮想環境の作成と有効化
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

3. 必要なパッケージのインストール
```bash
pip install flet
```

## 📁 プロジェクト構造

```
your-project/
│
├── main.py           # メインアプリケーションファイル
├── assets/          # 静的ファイル用ディレクトリ
│   └── icons/      # アプリアイコン
│       ├── icon-192.png
│       ├── icon-512.png
│       ├── icon-maskable-192.png
│       └── icon-maskable-512.png
│
└── manifest.json    # PWAマニフェストファイル
```

## 🚀 開発サーバーの起動

1. 以下のコマンドを実行してローカルサーバーを起動:
```bash
python main.py
```

2. ブラウザで以下のURLにアクセス:
```
http://localhost:8550
```

## 🌐 デプロイ方法

### Flytを使用したデプロイ

1. Flytのインストール:
```bash
pip install flyctl
```

2. Flytにログイン:
```bash
flyctl auth login
```

3. アプリケーションの初期化:
```bash
flyctl launch
```

4. デプロイの実行:
```bash
flyctl deploy
```

### その他のデプロイオプション

- **Heroku**: Procfileを作成し、Herokuの指示に従ってデプロイ
- **Vercel**: vercel.jsonを設定し、Vercel CLIを使用してデプロイ
- **ローカルサーバー**: プロキシサーバー(Nginx/Apache)を設定して公開

## 📝 カスタマイズ

1. `main.py`の内容を編集してアプリケーションの機能を追加
2. `manifest.json`でPWAの設定を変更
3. `assets/icons/`にカスタムアイコンを配置

## 🤝 コントリビューション

1. このリポジトリをFork
2. 新しいブランチを作成: `git checkout -b feature/awesome-feature`
3. 変更をコミット: `git commit -am 'Add awesome feature'`
4. ブランチにプッシュ: `git push origin feature/awesome-feature`
5. Pull Requestを作成

## 📜 ライセンス

このプロジェクトはMITライセンスの下で公開されています。

## 🆘 トラブルシューティング

- **ポートが使用中の場合**: 別のポート番号を指定して実行
  ```python
  flet.app(target=main, port=8551)
  ```

- **モジュールが見つからないエラー**: 仮想環境が有効化されているか確認
  ```bash
  # Windows
  venv\Scripts\activate
  # macOS/Linux
  source venv/bin/activate
  ```

## 📞 サポート

質問や問題がある場合は、GitHubのIssuesセクションに投稿してください。