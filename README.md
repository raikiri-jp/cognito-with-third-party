# Cognito With Third Party

Amazon Cognito を利用した認証機能を AWS以外のサーバーで実装するアプリケーションのサンプルプロジェクトです。

サンプルプロジェクトでは Backend に Laravel、Frontend に Angular を採用してしています。

## 前提条件

アプリケーションを動作させるには、以下の前提条件を満たす必要があります。

- [Amazon Cognito](https://aws.amazon.com/cognito/) でユーザープールが作成され、アプリケーションクライアントが設定されていること
    - アプリケーションクライアントのシークレットが生成されていること

## インストール方法

1. [Cognito With Third Party](https://github.com/raikiri-jp/cognito-with-third-party) をクローンするか、ZIP ファイルとしてダウンロードして解凍します。
2. [Cognito With Third Party](https://github.com/raikiri-jp/cognito-with-third-party) プロジェクトのルートディレクトリで次のコマンドを実行します。

   ```
   git submodule update
   ```

3. `src/backend` に移動して、以下のコマンドを実行します。

   ```
   composer install
   ```

4. `.env.example` ファイルを複製して `.env` ファイルを作成します。

   ```
   cp .env.example .env
   ```

5. `.env` ファイルを開き、以下の値を設定します。

   ```
   COGNITO_OAUTH2_DOMAIN="OAuth および Amazon Cognito エンドポイントのドメイン"
   COGNITO_APP_CLIENT_ID=クライアントID
   COGNITO_APP_SECRET=クライアントのシークレット
   ```

6. データベースを作成します。

   ```
   php artisan migrate
   ```

## アプリケーションの起動方法

1. `src/backend` に移動して、以下のコマンドを実行します。

   ```
   php artisan serve
   ```

2. ブラウザで `http://localhost:8000` にアクセスして、アプリケーションが正常に起動したことを確認します。

## License

[MIT license](https://opensource.org/licenses/MIT)
