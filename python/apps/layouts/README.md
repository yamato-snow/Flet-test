# 📱 Flet 固定フッターレイアウトデモ

## 📋 概要

スクロール可能なメインコンテンツと固定フッターを持つ、モダンなレイアウトのデモアプリケーションです。
レスポンシブWebアプリケーションの基本的なレイアウトパターンを学べます。

## ✨ 機能

- 📜 スクロール可能なメインコンテンツ
- 📌 画面下部に固定されたフッター
- 📱 レスポンシブデザイン
- 🎨 カスタマイズ可能なスタイリング

## 🔧 セットアップ

### 必要条件
- Python 3.7以上
- pip (Pythonパッケージマネージャー)

### インストール手順

1. 環境のセットアップ:
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

2. Fletのインストール:
```bash
pip install flet
```

3. アプリの実行:
```bash
python footer.py
```

## 💡 コードの解説

### 基本構造
```python
def main(page: Page):
    # メインコンテンツ（スクロール可能）
    main_content = Column(scroll="auto")
    
    # サンプルコンテンツの追加
    for i in range(100):
        main_content.controls.append(Text(f"Line {i}"))

    # ページ全体の設定
    page.padding = 0
    page.spacing = 0
    page.horizontal_alignment = "stretch"

    # レイアウトの組み立て
    page.add(
        Container(main_content, padding=10, expand=True),
        Row([Container(Text("Footer"), bgcolor="yellow", padding=5, expand=True)]),
    )
```

### 重要なポイント
1. `page.padding = 0`: ページの余白を削除
2. `page.spacing = 0`: 要素間のスペースを削除
3. `page.horizontal_alignment = "stretch"`: 横幅いっぱいに広がるレイアウト
4. `expand=True`: 利用可能なスペースを最大限使用

## 🎨 カスタマイズ例

### 1. フッターのスタイル変更
```python
Row([
    Container(
        Text(
            "Footer",
            size=20,
            weight="bold",
            color="white"
        ),
        bgcolor="blue",
        padding=10,
        expand=True
    )
])
```

### 2. メインコンテンツのカスタマイズ
```python
main_content = Column(
    scroll="auto",
    spacing=20,  # 行間の調整
    horizontal_alignment="center"  # 中央寄せ
)

# リッチなコンテンツの追加
main_content.controls.append(
    Container(
        content=Text("Important Content"),
        bgcolor="lightblue",
        padding=20,
        border_radius=10
    )
)
```

### 3. レスポンシブ対応の強化
```python
def page_resize(e):
    if page.width < 600:
        # モバイルレイアウト
        footer_padding = 10
        footer_height = 60
    else:
        # デスクトップレイアウト
        footer_padding = 20
        footer_height = 80
    
    footer.padding = footer_padding
    footer.height = footer_height
    page.update()

page.on_resize = page_resize
```

## 📐 レイアウトのバリエーション

### 1. 中央配置のフッター
```python
Row(
    [Container(
        Text("Footer"),
        bgcolor="yellow",
        padding=5,
        expand=True,
        alignment=alignment.center
    )]
)
```

### 2. 複数カラムのフッター
```python
Row([
    Container(Text("左"), padding=5, expand=True),
    Container(Text("中央"), padding=5, expand=True),
    Container(Text("右"), padding=5, expand=True),
])
```

## 🐛 トラブルシューティング

### よくある問題と解決方法

1. **フッターが固定されない**
   - `page.spacing = 0`が設定されているか確認
   - Containerの`expand=True`が設定されているか確認

2. **コンテンツがスクロールしない**
   - Columnの`scroll="auto"`が設定されているか確認
   - メインコンテンツのContainerに`expand=True`が設定されているか確認

3. **レイアウトが崩れる**
   - `page.horizontal_alignment = "stretch"`が設定されているか確認
   - すべての必要なContainerで`expand=True`が設定されているか確認

## 🚀 発展的な使い方

1. **アニメーションの追加**
```python
# フッターのスライドイン/アウト
def toggle_footer(e):
    footer.opacity = 1 if footer.opacity == 0 else 0
    footer.update()
```

2. **動的なコンテンツ更新**
```python
def add_content(e):
    main_content.controls.append(Text(f"New Line {len(main_content.controls)}"))
    page.update()
```

3. **テーマ切り替え**
```python
def toggle_theme(e):
    footer.bgcolor = "dark" if footer.bgcolor == "yellow" else "yellow"
    page.update()
```

## 📝 ベストプラクティス

1. **パフォーマンス最適化**
   - 大量のコンテンツは遅延読み込みを検討
   - 不要なupdateを避ける
   - リソースの解放を適切に行う

2. **レスポンシブデザイン**
   - ブレークポイントを適切に設定
   - モバイルファーストの設計
   - フレキシブルなユニットの使用

3. **アクセシビリティ**
   - 適切なコントラスト比の確保
   - キーボードナビゲーションのサポート
   - スクリーンリーダー対応

## 📜 ライセンス

このプロジェクトはMITライセンスの下で公開されています。

## 🤝 コントリビューション

バグ報告や機能改善の提案は大歓迎です！