# Flet電卓アプリケーション

シンプルでモダンな電卓アプリケーションです。Fletフレームワークを使用して作成されており、デスクトップアプリケーションとしても、Webアプリケーションとしても動作します！


## 機能

- 基本的な四則演算（足し算、引き算、掛け算、割り算）
- パーセント計算
- 正負の切り替え
- 小数点対応
- モダンなUIデザイン
- エラーハンドリング（0での除算など）

## 環境構築

### 必要要件

- Python 3.7以上
- pip（Pythonパッケージマネージャー）

### セットアップ手順

1. プロジェクトのクローンまたはダウンロード
```bash
git clone [リポジトリURL]
cd flet-calc
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

## アプリケーションの実行

ローカルで実行するには以下のコマンドを使用します：

```bash
python calc.py
```

これで電卓アプリが起動します！デフォルトではデスクトップアプリとして起動しますが、Webブラウザでも利用可能です。

## 使い方

1. 数字ボタン（0-9）をクリックして数値を入力
2. 演算子（+、-、×、÷）を選択して計算
3. =ボタンで計算結果を表示
4. ACボタンで表示をクリア
5. +/-ボタンで正負の切り替え
6. %ボタンでパーセント計算

## Fly.ioへのデプロイ方法

Fly.ioにデプロイして、Webアプリケーションとして公開することができます！

### デプロイの準備

1. Fly.ioのアカウントを作成し、CLIツールをインストール
```bash
# Windows（PowerShell管理者モード）
iwr https://fly.io/install.ps1 -useb | iex

# macOS
brew install flyctl

# Linux
curl -L https://fly.io/install.sh | sh
```

2. Fly.ioにログイン
```bash
flyctl auth login
```

### デプロイ手順

1. アプリケーションの初期化（初回のみ）
```bash
flyctl launch
```

2. デプロイの実行
```bash
flyctl deploy
```

デプロイが完了すると、以下のようなURLでアプリケーションにアクセスできます：
```
https://flet-calc.fly.dev
```

## トラブルシューティング

よくある問題と解決方法：

- **アプリが起動しない場合**
  - Pythonのバージョンが3.7以上であることを確認
  - 仮想環境が有効化されているか確認
  - 必要なパッケージが正しくインストールされているか確認

- **計算結果がおかしい場合**
  - ACボタンで一度クリアしてから再度計算を行ってみてください
  - 小数点の入力が重複していないか確認

## 開発者向け情報

プロジェクトの構成：

```
flet-calc/
├── calc.py          # メインアプリケーションコード
├── requirements.txt # 依存パッケージリスト
└── fly.toml         # Fly.io設定ファイル
```

## ライセンス

このプロジェクトはMITライセンスの下で公開されています。詳細については`LICENSE`ファイルを参照してください。

## コントリビューション

バグ報告や機能改善の提案は、GitHubのIssueやPull Requestsを通じて受け付けています。
お気軽にご連絡ください！