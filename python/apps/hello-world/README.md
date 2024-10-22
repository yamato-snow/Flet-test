# Hello World プロジェクト

このプロジェクトは、Fletを使用してシンプルな「Hello, world!」アプリケーションを作成するものです。Fletは、PythonでWebアプリケーションを簡単に構築できるフレームワークです。

## 機能

- シンプルなテキスト表示: "Hello, world!"を画面に表示します。

## 環境構築

このプロジェクトを実行するためには、PythonとFletが必要です。以下の手順に従って環境を構築してください。

### 1. Pythonのインストール

Pythonがインストールされていない場合は、[Pythonの公式サイト](https://www.python.org/downloads/)からインストールしてください。

### 2. 仮想環境の作成（オプション）

プロジェクト用の仮想環境を作成することをお勧めします。

```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate  # Windows
```

### 3. Fletのインストール

次に、Fletをインストールします。

```bash
pip install flet
```

## プロジェクトの実行

以下のコマンドを使用してアプリケーションを実行します。

```bash
python apps/hello-world/hello.py
```

ブラウザが自動的に開き、"Hello, world!"と表示されるはずです。

## デプロイ

デプロイには、HerokuやVercelなどのプラットフォームを使用できます。以下はHerokuを使用したデプロイの手順です。

### 1. Heroku CLIのインストール

[Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli)をインストールします。

### 2. Herokuアプリの作成

```bash
heroku create your-app-name
```

### 3. アプリのデプロイ

```bash
git add .
git commit -m "Initial commit"
git push heroku master
```

### 4. アプリの開放

```bash
heroku open
```

これで、デプロイされたアプリケーションにアクセスできます。

## ライセンス

このプロジェクトはMITライセンスの下で提供されています。