# Flet チャットアプリケーション

こんにちは！👋 このプロジェクトは、Fletを使用したシンプルで使いやすいチャットアプリケーションです。複数のユーザーがリアルタイムでメッセージを交換できる機能を提供します。

## ✨ 機能

- リアルタイムチャット
- ユーザー名による参加
- アバター表示（ユーザー名の頭文字）
- メッセージの選択可能
- 参加通知
- マルチライン入力サポート
- レスポンシブなUI

## 🚀 はじめ方

### 環境構築

1. Pythonがインストールされていることを確認してください（3.7以上推奨）

2. 仮想環境を作成し、有効化します：
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS / Linux
python -m venv venv
source venv/bin/activate
```

3. 必要なパッケージをインストールします：
```bash
pip install -r requirements.txt
```

### ローカルでの実行

アプリケーションを起動するには以下のコマンドを実行します：

```bash
python chat.py
```

ブラウザが自動的に開き、チャットアプリケーションが表示されます。

## 💫 使い方

1. アプリケーションを開くと、最初にユーザー名の入力を求められます
2. ユーザー名を入力して「Join chat」をクリックします
3. メッセージを入力フィールドに書き込みます
4. Enterキーを押すか、送信ボタンをクリックしてメッセージを送信します
   - Shift + Enterで改行することもできます

## 🌐 Fly.ioへのデプロイ

Fly.ioにデプロイする手順は以下の通りです：

1. Fly.ioのアカウントを作成し、CLIをインストールします：
```bash
# macOS
brew install flyctl

# Windows
powershell -Command "iwr https://fly.io/install.ps1 -useb | iex"

# Linux
curl -L https://fly.io/install.sh | sh
```

2. Fly.ioにログインします：
```bash
fly auth login
```

3. アプリケーションをデプロイします：
```bash
fly deploy
```

デプロイが完了すると、アプリケーションのURLが表示されます。

### 環境設定

`fly.toml`ファイルには以下の重要な設定が含まれています：

- セッションタイムアウト: 60秒
- HTTPSの強制
- 自動スケーリング設定
- 同時接続数の制限（ソフトリミット: 200、ハードリミット: 250）

## 📝 開発者向け情報

プロジェクトには以下の主要なファイルが含まれています：

- `chat.py`: メインのアプリケーションコード
- `requirements.txt`: 必要なPythonパッケージ
- `fly.toml`: Fly.ioデプロイ設定

### コードの進化

プロジェクトには複数のバージョンのチャットアプリケーションが含まれています：

1. `chat_1.py`: 基本的なメッセージ送信機能
2. `chat_2.py`: ユーザーIDとpubsubを使用した複数ユーザー対応
3. `chat_3.py`: ユーザー名とログイン機能の追加
4. `chat.py`: 完全な機能を備えた最終バージョン

## 🤝 コントリビューション

バグを見つけた場合や新機能の提案がある場合は、お気軽にIssueを作成してください。
プルリクエストも大歓迎です！

## ⚠️ 注意事項

- セッションタイムアウトは60秒に設定されています
- 本番環境では適切なセキュリティ対策を実装することを推奨します
- スケーリング設定は必要に応じて`fly.toml`で調整できます