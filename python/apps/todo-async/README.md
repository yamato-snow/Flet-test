# Flet ToDo アプリケーション

シンプルで使いやすいTodoアプリケーションです。Fletフレームワークを使用して作成された、モダンなUIを備えたタスク管理ツールです。

## ✨ 機能

- タスクの追加、編集、削除
- タスクの完了状態の切り替え
- タスクのフィルタリング（全て / アクティブ / 完了済み）
- 完了済みタスクの一括クリア
- レスポンシブなデザイン

## 🚀 はじめ方

### 必要な環境

- Python 3.7以上
- pip（Pythonのパッケージマネージャー）

### インストール手順

1. プロジェクトのクローンまたはダウンロード:
```bash
git clone <リポジトリURL>
cd flet-todo-app
```

2. 仮想環境の作成と有効化:
```bash
# Windows
python -m venv venv
.\venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

3. 必要なパッケージのインストール:
```bash
pip install flet
```

### 🎮 アプリケーションの起動

1. 以下のコマンドでアプリケーションを起動します:
```bash
python todo.py
```

2. ブラウザが自動的に開き、アプリケーションが表示されます（デフォルトで`http://localhost:8550`）

## 💡 使い方

1. **タスクの追加**
   - 入力フィールドにタスク名を入力
   - Enterキーを押すか、＋ボタンをクリック

2. **タスクの編集**
   - タスクの横にある✏️（編集）アイコンをクリック
   - 内容を変更して✓（完了）アイコンをクリック

3. **タスクの削除**
   - タスクの横にある🗑️（削除）アイコンをクリック

4. **タスクの完了/未完了**
   - タスク名の左側のチェックボックスをクリック

5. **タスクのフィルタリング**
   - 「all」「active」「completed」タブで表示を切り替え

## 🌐 デプロイ方法 (Fly.io)

1. Fly.ioアカウントの作成とCLIのインストール:
```bash
curl -L https://fly.io/install.sh | sh
fly auth signup  # 新規登録の場合
fly auth login   # 既存アカウントの場合
```

2. アプリケーションの設定:
```bash
# Dockerfileの作成
cat << EOF > Dockerfile
FROM python:3.9-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
CMD ["python", "todo.py"]
EOF

# requirements.txtの作成
echo "flet>=0.9.0" > requirements.txt
```

3. Fly.ioへのデプロイ:
```bash
fly launch
fly deploy
```

## 🤝 コントリビューション

バグ報告や機能要望は、GitHubのIssueトラッカーをご利用ください。プルリクエストも大歓迎です！

## 📝 ライセンス

このプロジェクトはMITライセンスの下で公開されています。

## 🙋‍♂️ お問い合わせ

何か質問や問題がありましたら、お気軽にIssueを作成してください。

---
*注意: デプロイ時には、環境変数やセキュリティ設定を適切に行ってください。*