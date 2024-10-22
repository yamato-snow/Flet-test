# Flet ToDoアプリ

## 👋 はじめに

このプロジェクトは、PythonのモダンなUIフレームワーク「Flet」を使用して作られたシンプルなToDoアプリです。タスクの追加、編集、削除、完了状態の管理などの基本的な機能を備えています。

## 🔧 環境構築

### 必要要件
- Python 3.7以上
- pip（Pythonパッケージマネージャー）

### セットアップ手順

1. 仮想環境を作成して有効化します：
```bash
# Windows
python -m venv venv
.\venv\Scripts\activate

# macOS / Linux
python3 -m venv venv
source venv/bin/activate
```

2. 必要なパッケージをインストールします：
```bash
pip install flet
```

## 🚀 アプリの起動方法

1. プロジェクトのルートディレクトリで以下のコマンドを実行します：
```bash
python to-do-5.py
```

2. アプリが自動的にデフォルトブラウザで開きます。
   - ブラウザが開かない場合は、`http://localhost:8550` にアクセスしてください。

## 💡 使い方

### 基本操作
1. **タスクの追加**
   - 上部のテキストフィールドにタスクを入力
   - 右側の「+」ボタンをクリックまたはEnterキーを押す

2. **タスクの編集**
   - タスク右側の鉛筆アイコンをクリック
   - 内容を変更して✓アイコンをクリック

3. **タスクの削除**
   - タスク右側のゴミ箱アイコンをクリック

4. **タスクの完了/未完了**
   - タスク左側のチェックボックスをクリック

### フィルター機能
画面上部のタブで以下のフィルタリングが可能です：
- **all**: すべてのタスクを表示
- **active**: 未完了のタスクのみ表示
- **completed**: 完了済みのタスクのみ表示

## 🌟 アプリの特徴

このToDoアプリには以下の特徴があります：
- シンプルで直感的なUI
- リアルタイムな更新
- タスクの完了状態の管理
- フィルタリング機能
- レスポンシブデザイン

## 📝 プロジェクト構成

```
.
├── to-do-hello.py    # Hello World サンプル
├── to-do-1.py        # 基本的なToDoリスト
├── to-do-2.py        # レイアウト改善版
├── to-do-3.py        # クラスベース実装
├── to-do-4.py        # 編集・削除機能追加
└── to-do-5.py        # フィルター機能付き完全版
```

## 🚀 Fly.ioへのデプロイ方法

1. Fly.ioのアカウントを作成し、CLIをインストールします：
```bash
# macOS
brew install flyctl

# Windows (PowerShell)
pwsh -Command "iwr https://fly.io/install.ps1 -useb | iex"
```

2. Fly.ioにログインします：
```bash
fly auth login
```

3. `fly.toml`ファイルを作成します：
```bash
fly launch
```

4. Dockerfileを作成します：
```dockerfile
FROM python:3.9-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
EXPOSE 8550
CMD ["python", "to-do-5.py"]
```

5. デプロイを実行します：
```bash
fly deploy
```

## 🤝 コントリビューション

バグ報告や機能改善の提案は、GitHubのIssueやプルリクエストでお待ちしています！

## ⚖️ ライセンス

このプロジェクトはMITライセンスの下で公開されています。

## 📮 お問い合わせ

ご質問やご意見がありましたら、お気軽にGitHubのIssueでお知らせください。