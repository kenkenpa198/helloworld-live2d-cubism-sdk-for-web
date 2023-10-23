<!-- omit in toc -->
# practice - Live2D Cubism SDK for Web

同 SDK の練習用リポジトリです。

<!-- omit in toc -->
## 目次

- [Live2D Cubism SDK for Web について](#live2d-cubism-sdk-for-web-について)
    - [使用したパッケージ](#使用したパッケージ)
    - [Live2D Cubism Core について](#live2d-cubism-core-について)
    - [Live2D Cubism Components について](#live2d-cubism-components-について)
- [実行手順](#実行手順)
    - [1. Cubism SDK for Web のダウンロード](#1-cubism-sdk-for-web-のダウンロード)
    - [2. 環境構築](#2-環境構築)
    - [3. ビルド・サーバの起動・表示](#3-ビルドサーバの起動表示)
    - [4. サーバの停止](#4-サーバの停止)
- [メモ](#メモ)
    - [モデルを追加するとき](#モデルを追加するとき)
- [参考文献](#参考文献)

## Live2D Cubism SDK for Web について

### 使用したパッケージ

Cubism 4 SDK for Web R7

- [Live2D Cubism SDK for Web ダウンロード | Live2D Cubism](https://www.live2d.com/sdk/download/web/)

### Live2D Cubism Core について

[Live2D Proprietary Software 使用許諾契約](https://www.live2d.com/eula/live2d-proprietary-software-license-agreement_jp.html) に則り、Live2D Cubism Core は当リポジトリ上で管理・公開していません。Cubism Core は Cubism SDK 配布パッケージに同梱されているので、別途ダウンロードしてください。

### Live2D Cubism Components について

[Live2D Open Software 使用許諾契約](https://www.live2d.com/eula/live2d-open-software-license-agreement_jp.html) に則り、下記コンポーネントは当リポジトリ上で管理・公開しています。

- Live2D Cubism Components
    - [Cubism Web Samples](https://github.com/Live2D/CubismWebSamples)
    - [Cubism Web Framework](https://github.com/Live2D/CubismWebFramework)

## 実行手順

### 1. Cubism SDK for Web のダウンロード

[Live2D Cubism SDK for Web ダウンロード | Live2D Cubism](https://www.live2d.com/sdk/download/web/) > `Cubism SDK for Web` > `最新版をダウンロード` から最新の Cubism SDK パッケージをダウンロードする。

### 2. 環境構築

1. VS Code でトップディレクトリを開く。
2. 推奨拡張機能「EditorConfig for VS Code」をインストールする。
3. `Shift + Ctrl + P` > `Tasks: Run Task` から Node.js の必要パッケージをインストールする。
    1. `npm: install - Samples/TypeScript/Demo`
    2. `npm: install - Framework`
4. インストールしたパッケージを確認する。

    ```shell
    $ cd Samples/TypeScript/Demo/
    $ npm ls
    Demo@ /.../practice-live2d-cubism-sdk-for-web/Samples/TypeScript/Demo
    ├── @typescript-eslint/eslint-plugin@5.59.5
    ├── @typescript-eslint/parser@5.59.5
    ├── eslint-config-prettier@8.8.0
    ├── eslint-plugin-prettier@4.2.1
    ├── eslint@8.40.0
    ├── UNMET OPTIONAL DEPENDENCY fsevents@*
    ├── prettier@2.8.8
    ├── rimraf@5.0.0
    ├── serve@14.2.0
    ├── ts-loader@9.4.2
    ├── typescript@5.0.4
    ├── webpack-cli@5.1.1
    ├── webpack-dev-server@4.15.0
    ├── webpack@5.82.1
    └── whatwg-fetch@3.6.2
    ```

    ```shell
    $ cd Framework
    $ npm ls
    Framework@ /.../practice-live2d-cubism-sdk-for-web/Framework
    ├── @typescript-eslint/eslint-plugin@5.59.5
    ├── @typescript-eslint/parser@5.59.5
    ├── eslint-config-prettier@8.8.0
    ├── eslint-plugin-prettier@4.2.1
    ├── eslint@8.40.0
    ├── prettier@2.8.8
    ├── rimraf@5.0.0
    └── typescript@5.0.4
    ```

### 3. ビルド・サーバの起動・表示

1. `Shift + Ctrl + P` > `Tasks: Run Build Task` > `npm: build - Samples/TypeScript/Demo` からビルドを実行する。
2. `Shift + Ctrl + P` > `Tasks: Run Task` > `npm: start` で簡易サーバを起動する。
3. `F5` (デバッグの開始) もしくはターミナルに表示された `http://localhost:5000/` をブラウザで開く。
    1. ブラウザで開いた場合は `Samples` > `TypeScript` > `Demo` を開く。
4. Haru さんが表示されれば OK 。

    ![haru](images/haru.png)

### 4. サーバの停止

簡易サーバを終了するときは `Shift + Ctrl + P` > `Tasks: Terminate Task` > `npm: start - Samples/TypeScript/Demo` を実行する。

## メモ

### モデルを追加するとき

1. `Samples/Resources` 配下へモデルのフォルダを追加する。このときフォルダ名と配下の `[モデル名].moc3` `[モデル名].model3.json` を一致させておく。
2. `Samples/TypeScript/Demo/src/lappdefine.ts` の下記の配列へモデル名を追加する。

    ```ts
    // モデル定義---------------------------------------------
    // モデルを配置したディレクトリ名の配列
    // ディレクトリ名とmodel3.jsonの名前を一致させておくこと
    export const ModelDir: string[] = [
    'Haru',
    'Hiyori',
    'Mark',
    'Natori',
    'Rice',
    'Mao',
    '[モデル名]' // 追加
    ];
    ```

3. 再度ビルドする。

## 参考文献

- [Live2D Cubism SDK とは | Live2D Cubism](https://www.live2d.com/sdk/about/)
- [Cubism SDK for Web | SDKマニュアル | Live2D Manuals & Tutorials](https://docs.live2d.com/cubism-sdk-manual/cubism-sdk-for-web/)
- [Live2D Cubism SDK チュートリアル | SDKチュートリアル | Live2D Manuals & Tutorials](https://docs.live2d.com/cubism-sdk-tutorials/top/)
- [Cubism SDK ワークショップ「【初心者向け】WebでもLive2Dが使える！Cubism SDK for Webを使ってみよう！」 #Cubism_SDK - YouTube](https://www.youtube.com/watch?v=tQdkFvw7X-E)
- [Cubism SDKとCubism Native Frameworkを使用したライブラリの公開について - Cubism SDK / 要望 - Live2Dクリエイターズフォーラム](https://creatorsforum.live2d.com/t/topic/1942)
