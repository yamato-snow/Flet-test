# 認証プロジェクト

## 概要

このプロジェクトは、Fletフレームワークを使用してGitHubおよびLinkedInのOAuth認証を実装するサンプルコードを提供します。各スクリプトは、異なる認証フローや機能を示しています。

## ファイルの説明

- **basic-auth-async.py**: GitHub OAuthを非同期で実行する基本的な認証フローを示します。
- **basic-auth.py**: GitHub OAuthを同期で実行する基本的な認証フローを示します。
- **check-auth-results-and-toggle-ui.py**: 認証結果を確認し、UIを切り替える機能を持つGitHub OAuthの実装です。
- **github-oauth-with-listing-repos-async.py**: GitHub OAuthを使用してユーザーのリポジトリを非同期でリストする機能を持つ実装です。
- **github-oauth-with-listing-repos.py**: GitHub OAuthを使用してユーザーのリポジトリを同期でリストする機能を持つ実装です。
- **linkedin-login.py**: LinkedIn OAuthを使用した認証フローを示します。

## 必要な環境変数

各スクリプトは、以下の環境変数を必要とします。これらは、OAuthプロバイダーのクライアントIDやシークレットを設定するために使用されます。

- `GITHUB_CLIENT_ID`
- `GITHUB_CLIENT_SECRET`
- `MY_APP_SECRET_KEY` (一部のスクリプトで使用)
- `LINKEDIN_CLIENT_ID` (LinkedIn用)
- `LINKEDIN_CLIENT_SECRET` (LinkedIn用)

## インストール

1. リポジトリをクローンします。
   ```bash
   git clone https://github.com/yourusername/authentication-project.git
   ```
2. 必要な依存関係をインストールします。
   ```bash
   cd authentication-project
   pip install -r requirements.txt
   ```

## 使用方法

各スクリプトを実行するには、以下のコマンドを使用します。ポートやリダイレクトURLは必要に応じて調整してください。
``` bash
bash
python python/apps/authentication/basic-auth-async.py
```

他のスクリプトも同様に実行できます。

## 貢献

貢献を歓迎します。バグ報告や機能提案は、GitHubのイシューを通じて行ってください。

## ライセンス

このプロジェクトはMITライセンスの下で提供されています。詳細は`LICENSE`ファイルを参照してください。