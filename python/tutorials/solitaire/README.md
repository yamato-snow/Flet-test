# Flet ソリティア

## 概要
このプロジェクトは、Pythonのフレームワーク「Flet」を使用して作られた、クラシックなソリティアゲームです。ブラウザ上でプレイできる美しいインターフェースと、直感的な操作性を備えています。

## 特徴
- 🎮 ドラッグ＆ドロップによる直感的な操作
- 🎴 美しいカードデザイン
- ⚙️ カスタマイズ可能な設定
- 🌐 ブラウザ対応
- 🚀 Fly.ioへの簡単なデプロイ

## 必要な環境
- Python 3.7以上
- pip（Pythonパッケージマネージャー）
- Git（ソースコード管理）

## インストール方法

1. リポジトリのクローン
```bash
git clone <リポジトリURL>
cd flet-solitaire
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

## 起動方法

1. 仮想環境が有効化されていることを確認

2. ゲームの起動
```bash
python main.py
```

3. ブラウザで以下のURLにアクセス
```
http://localhost:8550
```

## 操作方法

### 基本操作
- カードのドラッグ＆ドロップ：カードを移動
- シングルクリック：
  - ストックパイル（左上）のカードをめくる
  - 裏向きのカードを表にする
- ダブルクリック：カードを適切な場所に自動移動

### ゲームのルール
1. エースから同じスート（マーク）でキングまでカードを順番に積み上げていきます
2. 場札には、色の異なるカードを降順に配置できます
3. 空いた場所には、キングのみ配置可能です
4. すべてのカードを4つのファンデーションパイル（右上）に移動させると勝利です

## カスタマイズ設定

ゲーム画面右上の⚙️アイコンから以下の設定が可能です：
- ウェストパイルのカード枚数（1枚/3枚）
- デッキの周回制限（3回/無制限）
- カードデザインの変更

## Fly.ioへのデプロイ方法

1. Fly.ioのセットアップ
```bash
# Fly CLIのインストール
curl -L https://fly.io/install.sh | sh

# ログイン
fly auth login
```

2. アプリケーションの作成と設定
```bash
# アプリケーションの作成
fly launch

# 環境変数の設定
fly secrets set FLET_SERVER_PORT=8080
fly secrets set FLET_FORCE_WEB_VIEW=true
```

3. デプロイの実行
```bash
fly deploy
```

## トラブルシューティング

### よくある問題と解決方法

1. 起動時に「Port already in use」エラーが表示される
```bash
# 使用中のポートを確認
netstat -ano | findstr 8550

# プロセスの終了
taskkill /PID <プロセス番号> /F
```

2. パッケージのインストールでエラーが発生する
```bash
# pipを最新版にアップデート
python -m pip install --upgrade pip

# requirements.txtの再インストール
pip install -r requirements.txt --force-reinstall
```

## 開発環境のTips

1. デバッグモードの有効化
```python
# main.pyの先頭に以下を追加
import logging
logging.basicConfig(level=logging.DEBUG)
```

2. ホットリロードの有効化
```bash
flet run main.py -d
```

## コントリビューション

1. このリポジトリをフォーク
2. 新しいブランチを作成（`git checkout -b feature/awesome-feature`）
3. 変更をコミット（`git commit -m 'Add awesome feature'`）
4. ブランチをプッシュ（`git push origin feature/awesome-feature`）
5. プルリクエストを作成

## ライセンス
このプロジェクトはMITライセンスの下で公開されています。

## 作者への連絡
- Issue Trackerを使用して問題を報告
- プルリクエストを送信して改善を提案

---

ゲームを楽しんでいただければ幸いです！フィードバックやご提案があればお気軽にお寄せください。