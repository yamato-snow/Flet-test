# 🗺️ Flet 画面遷移デモ集

## 📋 これは何？

Webアプリで「ホーム画面」から「設定画面」に移動したり、「戻る」ボタンで前の画面に戻ったりする...そんな普段よく使う画面の切り替えを実装するデモ集です！

## 🎮 どんなことができるの？

### 1. シンプルな画面切り替え (`home-store.py`)
```python
# ホーム画面とストア画面を行き来する簡単な例
```

- 「ホーム」と「ストア」の2つの画面を行き来できます
- ボタンをクリックするだけの簡単な遷移
- ブラウザの「戻る」ボタンでも前の画面に戻れます

### 2. 階層のある画面遷移 (`building-views-on-route-change.py`)
```python
# メイン画面 → 設定画面 → メール設定画面
```

- より実践的な画面の切り替え
- 設定→詳細設定のように階層的に画面を移動
- パンくずリストのような感覚で前の画面に戻れます

## 🔧 セットアップ方法

### 1. 必要なものをインストール
```bash
# Pythonの仮想環境を作成
python -m venv venv

# 仮想環境を有効化
# Windowsの場合
venv\Scripts\activate
# macOS/Linuxの場合
source venv/bin/activate

# 必要なパッケージをインストール
pip install flet
```

### 2. デモを動かしてみる

シンプルな画面切り替え:
```bash
python home-store.py
```
👆 これを実行すると、ホーム画面とストア画面を行き来できるデモが立ち上がります！

階層のある画面切り替え:
```bash
python building-views-on-route-change.py
```
👆 これを実行すると、より本格的な画面遷移のデモが立ち来がります！

## 💡 仕組みを理解しよう

### 画面遷移の基本
```python
# ボタンをクリックしたら新しい画面に移動
def open_store(e):
    page.go("/store")  # "/store"という画面に移動

# ボタンの設定
ElevatedButton("ストアへ行く", on_click=open_store)
```

### 画面の内容を定義
```python
# 「ストア」画面の中身
View(
    "/store",  # この画面の名前
    [
        AppBar(title=Text("ストア")),  # 画面上部のタイトル
        Text("ここにストアの内容が表示されます"),  # 画面の中身
        ElevatedButton("ホームに戻る", on_click=go_home)  # 戻るボタン
    ]
)
```

## 🌐 Web公開する方法（Fly.io使用）

### 1. Fly.ioの準備
```bash
# Fly CLIをインストール
curl -L https://fly.io/install.sh | sh

# ログイン
fly auth login
```

### 2. 設定ファイルの準備
`fly.toml`というファイルを作成:
```toml
app = "あなたのアプリ名"

[env]
  FLET_SERVER_PORT = "8080"

[[services]]
  internal_port = 8080
  protocol = "tcp"

  [[services.ports]]
    port = "80"
```

### 3. デプロイ
```bash
# アプリをデプロイ
fly deploy
```

## 🎨 カスタマイズしてみよう

### 1. 新しい画面を追加
```python
# 例：プロフィール画面を追加
if page.route == "/profile":
    page.views.append(
        View(
            "/profile",
            [
                AppBar(title=Text("プロフィール")),
                Text("ここにプロフィール情報を表示"),
                ElevatedButton("戻る", on_click=lambda _: page.go("/"))
            ]
        )
    )
```

### 2. 遷移時のアニメーション追加
```python
View(
    "/store",
    [...],
    transitions=ft.Transitions.SCALE  # ふわっと表示
)
```

## 🐛 よくある問題と解決方法

1. **画面が切り替わらない**
   - `page.update()`を呼び忘れていませんか？
   - ルート名（"/store"など）は正しいですか？

2. **戻るボタンが動かない**
   - `page.on_view_pop`のハンドラは設定されていますか？
   - viewsのスタックは正しく管理されていますか？

## 📚 もっと詳しく知りたい方へ

- [Flet公式ガイド](https://flet.dev/docs/guides/python/navigation-and-routing)
- [画面遷移のベストプラクティス](https://flet.dev/docs/guides/python/navigation-and-routing#best-practices)

## 🤝 改善に協力したい方へ

1. このリポジトリをFork
2. 新しい機能を追加
3. Pull Requestを送ってください！

## ⚡ 次のステップ

1. まずは`home-store.py`を動かしてみましょう
2. 動きを確認したら、自分の好きな画面を追加してみましょう
3. より複雑な`building-views-on-route-change.py`も試してみましょう

## 💬 困ったときは

質問や問題があれば、GitHubのIssuesで質問してください！