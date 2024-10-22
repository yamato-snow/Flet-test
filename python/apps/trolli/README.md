# Flet Trello クローン

## 📝 概要

このプロジェクトは、Pythonのウェブフレームワーク「Flet」を使用して作られたTrelloクローンアプリケーションです。
タスク管理やプロジェクト管理に便利なカンバン方式のボード機能を提供します。

デモサイト: [https://flet-trolli.fly.dev/](https://flet-trolli.fly.dev/)

## 🚀 特徴

- ドラッグ&ドロップでカードの移動が可能
- ボードの作成・削除
- リストの作成・削除
- カードの作成・削除
- ユーザー認証機能
- レスポンシブデザイン

## 💻 必要な環境

- Python 3.7以上
- pip（Pythonパッケージマネージャー）

## 🔧 環境構築

1. リポジトリのクローン
```bash
git clone https://github.com/your-username/flet-trello-clone.git
cd flet-trello-clone
```

2. 仮想環境の作成と有効化
```bash
# Windows
python -m venv venv
.\venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

3. 必要なパッケージのインストール
```bash
pip install -r requirements.txt
```

## 🎮 アプリケーションの起動

1. ローカルでの実行
```bash
python main.py
```

2. ブラウザが自動的に開き、アプリケーションが起動します
   - デフォルトでは `http://localhost:8080` で起動します

## 📱 基本的な使い方

1. アプリケーション起動後、右上の「Log in」からログインします
   - 初回利用時は自動的に新規ユーザーとして登録されます

2. ボードの作成
   - 「Add new board」ボタンをクリックし、ボード名を入力
   - 好みの色を選択して「Create」をクリック

3. リストの作成
   - ボード内の「add a list」ボタンをクリック
   - リスト名を入力し、色を選択して「Create」をクリック

4. カードの作成
   - リスト内の「add card」をクリック
   - カード名を入力してEnterキーを押す

5. カードの移動
   - カードをドラッグ&ドロップで別のリストに移動可能
   - リスト自体も同様にドラッグ&ドロップで並び替え可能

## 🌐 Fly.ioへのデプロイ方法

1. Fly.ioのアカウント作成とCLIのインストール
```bash
# macOS
brew install flyctl

# Windows
iwr https://fly.io/install.ps1 -useb | iex
```

2. Fly.ioにログイン
```bash
fly auth login
```

3. アプリケーションの作成
```bash
fly launch
```
- プロンプトに従って設定を行います
- 既存の`fly.toml`を使用するか聞かれたら「Yes」を選択

4. デプロイの実行
```bash
fly deploy
```

5. アプリケーションの確認
```bash
fly open
```

## 🔧 トラブルシューティング

- **Q: アプリケーションが起動しない**
  - 仮想環境が有効になっているか確認してください
  - 必要なパッケージがすべてインストールされているか確認してください

- **Q: カードのドラッグ&ドロップが機能しない**
  - ブラウザをリフレッシュしてみてください
  - 別のブラウザで試してみてください

## 📝 注意事項

- このアプリケーションはデモ用であり、データは永続化されません
- サーバーの再起動時にデータは初期化されます
- 本番環境での使用には、適切なデータベースの実装が必要です

## 🤝 コントリビューション

プルリクエストは大歓迎です。大きな変更を加える場合は、まずissueを作成して変更内容を議論しましょう。

## 📜 ライセンス

このプロジェクトはMITライセンスの下で公開されています。詳細は[LICENSE](LICENSE)ファイルをご覧ください。