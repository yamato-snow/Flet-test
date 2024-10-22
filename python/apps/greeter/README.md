# 👋 Fletグリーターアプリ

## 📋 概要

これは超シンプルなグリーターアプリです！
名前を入力すると、あなたに挨拶してくれる、Fletの基本が学べるデモアプリケーションです。

![Demo of Greeter App](https://via.placeholder.com/600x200.png?text=Greeter+App+Demo)

## ✨ 機能

- 📝 名前入力フィールド
- 🚨 入力バリデーション（空欄チェック）
- 👋 パーソナライズされた挨拶メッセージ

## 🔧 セットアップ

### 必要条件
- Python 3.7以上
- pip (Pythonパッケージマネージャー)

### インストール手順

1. 仮想環境を作成して有効化:
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

2. Fletをインストール:
```bash
pip install flet
```

3. アプリを実行:
```bash
python greeter.py
```

## 💡 使い方

1. アプリを起動
2. テキストフィールドに名前を入力
3. "Say hello!"ボタンをクリック
4. パーソナライズされた挨拶メッセージが表示されます！

## 📚 コードの解説

```python
# テキストフィールドの作成
txt_name = ft.TextField(label="Your name")

# ボタンクリック時の処理
def btn_click(e):
    if not txt_name.value:  # 名前が入力されてないとき
        txt_name.error_text = "Please enter your name"
        page.update()
    else:  # 名前が入力されているとき
        name = txt_name.value
        page.clean()  # 画面をクリア
        page.add(ft.Text(f"Hello, {name}!"))  # 挨拶を表示
```

### 重要なポイント
- `TextField`でユーザー入力を受け付け
- 入力バリデーションで空欄チェック
- `page.clean()`で画面をリフレッシュ
- `page.add()`で新しい要素を追加

## 🎨 カスタマイズ例

### 1. メッセージの変更
```python
# オリジナル
page.add(ft.Text(f"Hello, {name}!"))

# カスタマイズ例
page.add(ft.Text(f"よろしく、{name}さん！"))
```

### 2. スタイルの追加
```python
# スタイル付きのテキストフィールド
txt_name = ft.TextField(
    label="Your name",
    border_color=ft.colors.BLUE,
    width=200
)

# スタイル付きのボタン
ft.ElevatedButton(
    "Say hello!",
    on_click=btn_click,
    color=ft.colors.WHITE,
    bgcolor=ft.colors.BLUE
)
```

### 3. 追加のバリデーション
```python
def btn_click(e):
    if len(txt_name.value) < 2:
        txt_name.error_text = "Name must be at least 2 characters"
        page.update()
    # 以下略
```

## 🚀 発展させるアイデア

1. 時間帯によって挨拶を変える
```python
from datetime import datetime

def get_greeting():
    hour = datetime.now().hour
    if hour < 12:
        return "Good morning"
    elif hour < 17:
        return "Good afternoon"
    else:
        return "Good evening"
```

2. 名前を記憶して次回起動時に表示
3. 多言語対応の追加
4. アニメーション効果の追加

## 🐛 トラブルシューティング

- **ウィンドウが表示されない**: Pythonのバージョンが3.7以上か確認
- **エラーメッセージが表示されない**: `page.update()`が呼ばれているか確認
- **文字化けする**: ファイルのエンコーディングがUTF-8か確認

## 📝 ライセンス

このプロジェクトはMITライセンスの下で公開されています。

## 🤝 コントリビューション

機能改善やバグ修正の提案は大歓迎です！お気軽にPull Requestを送ってください。

## 📮 フィードバック

質問や提案がありましたら、Issuesに投稿してください。