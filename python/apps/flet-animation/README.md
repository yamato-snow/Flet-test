# Flet Animation Project

## 概要
このプロジェクトは、Fletライブラリを使用してアニメーションを作成するアプリケーションです。ユーザーは、色と形をランダムに配置し、ボタンをクリックすることでアニメーションを再生できます。

## 機能
- ランダムな色とサイズの形を生成
- 形をアニメーションで配置
- 「Go!」ボタンでアニメーションを開始
- 「Again!」ボタンで形を再ランダム化

## 環境構築

### 必要なもの
- Python 3.7以上
- pip（Pythonパッケージ管理ツール）

### インストール手順
1. リポジトリをクローンします。
   ```bash
   git clone https://github.com/yourusername/flet-animation.git
   cd flet-animation
   ```

2. 必要なパッケージをインストールします。
   ```bash
   pip install flet
   ```

3. アプリケーションを実行します。
   ```bash
   python apps/flet-animation/main.py
   ```

## デプロイ
デプロイには、HerokuやVercelなどのプラットフォームを使用できます。以下はHerokuを使用したデプロイ手順の例です。

### Herokuでのデプロイ手順
1. Heroku CLIをインストールします。
2. Herokuにログインします。
   ```bash
   heroku login
   ```

3. 新しいアプリを作成します。
   ```bash
   heroku create your-app-name
   ```

4. 必要なファイルを追加します（例: `requirements.txt`）。
   ```bash
   pip freeze > requirements.txt
   ```

5. コードをHerokuにプッシュします。
   ```bash
   git add .
   git commit -m "Initial commit"
   git push heroku master
   ```

6. アプリを開きます。
   ```bash
   heroku open
   ```

## ライセンス
このプロジェクトはMITライセンスの下で公開されています。
