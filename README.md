<!-- omit in toc -->
# Hello World - Live2D Cubism SDK for Web

同 SDK の練習用リポジトリです。

- [Live2D Cubism SDK とは | Live2D Cubism](https://www.live2d.com/sdk/about/)

GitHub Pages でのデプロイ結果はこちら。

- [https://kenkenpa198.github.io/helloworld-live2d-cubism-sdk-for-web/CubismSdkForWeb-4-r.7/Samples/TypeScript/Demo/index.html](https://kenkenpa198.github.io/helloworld-live2d-cubism-sdk-for-web/CubismSdkForWeb-4-r.7/Samples/TypeScript/Demo/index.html)

<!-- omit in toc -->
## 目次

- [1. Live2D Cubism SDK for Web について](#1-live2d-cubism-sdk-for-web-について)
    - [1.1. 使用したパッケージのバージョン](#11-使用したパッケージのバージョン)
    - [1.2. Live2D Cubism Core について](#12-live2d-cubism-core-について)
    - [1.3. Live2D Cubism Components について](#13-live2d-cubism-components-について)
    - [1.4. Live2D Cubism サンプルデータについて](#14-live2d-cubism-サンプルデータについて)
    - [1.5. オリジナルからの変更箇所](#15-オリジナルからの変更箇所)
- [2. ビルド・公開手順](#2-ビルド公開手順)
    - [2.1. Cubism SDK for Web のダウンロード](#21-cubism-sdk-for-web-のダウンロード)
    - [2.2. 環境構築](#22-環境構築)
    - [2.3. ビルド](#23-ビルド)
    - [2.4. 簡易サーバの起動・表示 (オプション)](#24-簡易サーバの起動表示-オプション)
    - [2.5. GitHub Pages で公開](#25-github-pages-で公開)
- [3. メモ](#3-メモ)
    - [3.1. モデルを追加するとき](#31-モデルを追加するとき)
    - [3.2. ビルド成果物の追跡について](#32-ビルド成果物の追跡について)
    - [3.3. その他メモ](#33-その他メモ)
- [4. 参考文献](#4-参考文献)

## 1. Live2D Cubism SDK for Web について

使用したパッケージや使用許諾に関する情報を掲載しています。

### 1.1. 使用したパッケージのバージョン

Cubism 4 SDK for Web R7

- [Live2D Cubism SDK for Web ダウンロード | Live2D Cubism](https://www.live2d.com/sdk/download/web/)

パッケージに含まれる各種ファイルの許諾情報は以降のセクションを参照してください。

### 1.2. Live2D Cubism Core について

[Live2D Proprietary Software 使用許諾契約](https://www.live2d.com/eula/live2d-proprietary-software-license-agreement_jp.html) に則り、Live2D Cubism Core は当リポジトリ上で管理・公開していません。Cubism Core は Cubism SDK 配布パッケージに同梱されているので、別途ダウンロードしてください。

### 1.3. Live2D Cubism Components について

[Live2D Open Software 使用許諾契約](https://www.live2d.com/eula/live2d-open-software-license-agreement_jp.html) に則り、下記コンポーネントは当リポジトリ上で管理・公開しています。

- Live2D Cubism Components
    - [Cubism Web Samples](https://github.com/Live2D/CubismWebSamples)
    - [Cubism Web Framework](https://github.com/Live2D/CubismWebFramework)

### 1.4. Live2D Cubism サンプルデータについて

[Live2D Cubism サンプルデータ利用条件](https://www.live2d.com/eula/live2d-sample-model-terms_jp.html) に則り、Cubism Web Samples 配下のサンプルデータを当リポジトリで使用しています。

本作品のキャラクターには株式会社Live2Dの著作物であるサンプルデータが株式会社Live2Dの定める規約に従って用いられています。本作品は制作者の完全な自己の裁量で制作されています。

### 1.5. オリジナルからの変更箇所

当リポジトリの `Cubism 4 SDK for Web R7` 配下のサンプルファイルについて、オリジナルから記述を一部更新しています。

`CubismSdkForWeb-4-r.7/Samples/TypeScript/Demo/index.html`

```html
<head>
  ...
  <!-- <script src = "../../../Core/live2dcubismcore.js"></script> -->                         ★ コメントアウト
  <script src="https://cubism.live2d.com/sdk-web/cubismcore/live2dcubismcore.min.js"></script> ★ ホスティング先の URL を記述
  ...
<head>
```

Live2D Cubism Core の再頒布・公開は前述の規約により禁止されているので、GitHub リポジトリ上に配置できません。そのため公式でホスティングされている下記ファイルを参照しています。

- [Live2D Cubism SDK for Web ダウンロード | Live2D Cubism](https://www.live2d.com/sdk/download/web/#url_cubismcore) > `Cubism Core for Web`

## 2. ビルド・公開手順

ローカル環境上でのビルドから GitHub Pages による公開までの手順メモ。

※ 参考文献のチュートリアルや動画を参考にまとめましたが、お試しになる際は各規約をご確認の上自己責任でお願いします。

### 2.1. Cubism SDK for Web のダウンロード

前述の使用許諾に則り、当リポジトリにはコアファイルが含まれていない。このため公式サイトから最新の Cubism SDK パッケージをダウンロードする。

- [Live2D Cubism SDK for Web ダウンロード | Live2D Cubism](https://www.live2d.com/sdk/download/web/) > `Cubism SDK for Web` > `最新版をダウンロード`

展開後、`CubismSdkForWeb-4-r.7/Core` 内のファイルを当リポジトリの同ディレクトリへ配置する。もしくは `CubismSdkForWeb-4-r.7` をすべて置き換える。

### 2.2. 環境構築

1. VS Code でトップディレクトリを開く。
2. 推奨拡張機能「EditorConfig for VS Code」をインストールする。
3. `Shift + Ctrl + P` > `Tasks: Run Task` から Node.js の必要パッケージをインストールする。
    1. `npm: install - CubismSdkForWeb-4-r.7/Framework`
    2. `npm: install - CubismSdkForWeb-4-r.7/Samples/TypeScript/Demo`
4. インストールしたパッケージを確認する。

    ```shell
    $ cd Samples/TypeScript/Demo/
    $ npm ls
    Demo@ /.../helloworld-live2d-cubism-sdk-for-web/Samples/TypeScript/Demo
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
    Framework@ /.../helloworld-live2d-cubism-sdk-for-web/Framework
    ├── @typescript-eslint/eslint-plugin@5.59.5
    ├── @typescript-eslint/parser@5.59.5
    ├── eslint-config-prettier@8.8.0
    ├── eslint-plugin-prettier@4.2.1
    ├── eslint@8.40.0
    ├── prettier@2.8.8
    ├── rimraf@5.0.0
    └── typescript@5.0.4
    ```

### 2.3. ビルド

1. `Shift + Ctrl + P` > `Tasks: Run Build Task` > `npm: build - CubismSdkForWeb-4-r.7/Samples/TypeScript/Demo` からビルドを実行する。
2. `CubismSdkForWeb-4-r.7/Samples/TypeScript/Demo/dist/bundle.js` が生成されたことを確認する (※) 。

### 2.4. 簡易サーバの起動・表示 (オプション)

ローカル環境でテストする場合の手順。

1. `Shift + Ctrl + P` > `Tasks: Run Task` > `npm: start - CubismSdkForWeb-4-r.7/Samples/TypeScript/Demo` で簡易サーバを起動する。
2. `F5` (デバッグの開始) もしくはターミナルに表示された `http://localhost:5000/` をブラウザで開く。
    1. ブラウザで開いた場合は `Samples` > `TypeScript` > `Demo` を開く。
3. Haru さんが表示されれば OK 。

    ![haru](images/haru.png)

(※) 簡易サーバを終了するときは `Shift + Ctrl + P` > `Tasks: Terminate Task` > `npm: start - CubismSdkForWeb-4-r.7/Samples/TypeScript/Demo` を実行する。

### 2.5. GitHub Pages で公開

GitHub リポジトリへプッシュ後、GitHub Pages で公開設定を行う。

- 参考) [GitHub Pagesのクイックスタート - GitHub Docs](https://docs.github.com/ja/pages/quickstart)

`CubismSdkForWeb-4-r.7/Samples/TypeScript/Demo/index.html` へブラウザからアクセスして表示に問題が無ければ OK 。当リポジトリの場合は下記の URL となる。

- [https://kenkenpa198.github.io/helloworld-live2d-cubism-sdk-for-web/CubismSdkForWeb-4-r.7/Samples/TypeScript/Demo/index.html](https://kenkenpa198.github.io/helloworld-live2d-cubism-sdk-for-web/CubismSdkForWeb-4-r.7/Samples/TypeScript/Demo/index.html)

## 3. メモ

### 3.1. モデルを追加するとき

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

### 3.2. ビルド成果物の追跡について

`.../dist/bundle.js` のようなビルド成果物は本来 Git の追跡対象外とすることが望ましいが、GitHub Pages で公開する際に必須となる。このため `.gitignore` 上では追跡対象外にしていない。

`.gitignore`

```shell
# Nuxt.js build / generate output
.nuxt
# dist ★ コメントアウト
```

### 3.3. その他メモ

- 当リポジトリは `CubismSdkForWeb-4-r.7` ディレクトリ配下に `Framework` `Samples` を配置しているため、[公式チュートリアル](https://docs.live2d.com/cubism-sdk-tutorials/sample-build-web/) へ掲載されている各 npm コマンド先頭に `CubismSdkForWeb-4-r.7` が追加されている。

## 4. 参考文献

- [Cubism SDK for Web | SDKマニュアル | Live2D Manuals & Tutorials](https://docs.live2d.com/cubism-sdk-manual/cubism-sdk-for-web/)
- [Live2D Cubism SDK チュートリアル | SDKチュートリアル | Live2D Manuals & Tutorials](https://docs.live2d.com/cubism-sdk-tutorials/top/)
- [Cubism SDK ワークショップ「【初心者向け】WebでもLive2Dが使える！Cubism SDK for Webを使ってみよう！」 #Cubism_SDK - YouTube](https://www.youtube.com/watch?v=tQdkFvw7X-E)
- [Cubism SDKとCubism Native Frameworkを使用したライブラリの公開について - Cubism SDK / 要望 - Live2Dクリエイターズフォーラム](https://creatorsforum.live2d.com/t/topic/1942)
