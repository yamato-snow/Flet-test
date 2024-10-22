# Flet のサンプル

このリポジトリにはフレッツサンプルアプリケーションが含まれています。
Flet公式より、提供されたコードの説明READEME.mdを書くサンプルプロジェクトに追加しています。
公式リポジトリは以下の通りです。
https://github.com/flet-dev/flet
https://github.com/flet-dev/examples/tree/main

## 開発環境のセットアップ
1. リポジトリのクローン
```bash
git clone https://github.com/yamato-snow/Flet-test.git <プロジェクト名>
cd <プロジェクト名>
```

2. Pythonバージョンの設定
pyenv local 3.12.2
※ 必要に応じて pyenv install 3.12.2 でPythonをインストールしてください。

3. 仮想環境の作成と有効化
```bash
python -m venv .venv
. .venv/bin/activate  # Windowsのコマンドプロンプトの場合は `.venv\Scripts\activate.bat`
```

4. 依存パッケージのインストール
```bash
pip install --upgrade pip
pip install -r requirements.txt
```
※ Pillowでエラーが出た場合は、仮想環境を一旦無効化して以下のコマンドでインストールしてください。

```bash
(macOS) brew install libjpeg zlib libtiff
```
5. ブランチ運用について
ブランチを作成

自身の作業用ブランチを作成します。
```bash
git branch <ブランチ名>
```

※ブランチ名は、自分の名前で作成してください。

作成したブランチに移動します。

```bash
git checkout <ブランチ名>
```

※ブランチを移動したか確認する場合は、次のコマンドを実行します。

```bash
git branch
```

※現在のブランチが緑色で表示されます。

リモートリポジトリにプッシュ

リポジトリの変更をプッシュします。

```bash
git push -u origin <ブランチ名>
```