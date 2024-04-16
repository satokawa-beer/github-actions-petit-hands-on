# セルフペースドハンズオン

- [CIワークフローを作成してみる](#CIワークフローを作成してみる)
- [CDワークフローを作成してみる](#CDワークフローを作成してみる)

## CIワークフローを作成してみる

### [実践] 準備

まず、ハンズオン用のワークフローファイルを準備しておきましょう。

1. 以下のコマンドを実行し、ブランチを作成して切り替える
   ```bash
   git switch -c add-ci-workflow
   ```
2. `.github/workflows/ci-sample.yml`をコピーして、`.github/workflows/ci-<アカウント名>.yml`を作成する
3. `name:`の`<アカウント名>`を自分のアカウント名に変更する

### Actionsワークフローでビルドとテストを行う

GitHubドキュメントの「[GitHub Actions > ビルドおよびテスト](https://docs.github.com/ja/actions/automating-builds-and-tests)」には、各主要言語に対するビルドとテストの基本が紹介されています。

このハンズオンでは、Nuxt.jsアプリケーションをビルドし、テストするワークフローを作成するため、Node.jsのビルドとテストのドキュメントを参考にするとよいでしょう。

- 参考: [Node.js のビルドとテスト - GitHub Docs](https://docs.github.com/ja/actions/automating-builds-and-tests/building-and-testing-nodejs)

なお、ハンズオンのサンプルコードであるNuxt.jsのアプリケーションは`app`ディレクトリに格納されています。

余力がある方は、codespaceを接続しているVS Code（またはブラウザ）でターミナルを開き、以下のコマンドを実行してみてください。Nuxt.jsアプリケーションが起動し、`http://localhost:3000`でアクセスできるようになります。

```bash
cd app
npm install
npm run dev
```

このNuxt.jsアプリケーションのテストを行うには、以下のコマンドを実行します。（ごく簡単なテストケースが用意されています。）

```bash
npm run e2e
```

それでは、このアプリケーションのビルドとテストを行うワークフローファイルを作成してみましょう。

前述で準備したワークフローファイル`ci-<アカウント名>.yml`には、すでに以下の内容が記述されています。

```yml
name: "[<アカウント名>] CIワークフロー"

on:
  pull_request:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      # リポジトリをチェックアウト
      - uses: actions/checkout@v4
```

このワークフローでは、以下のトリガーや処理が定義されています。

- ワークフローの名前は`[<アカウント名>] CIワークフロー`
- `main`に対するプルリクエストの作成や編集のイベントでトリガーされる
- `build`というジョブIDのジョブが実行される
- `build`ジョブは、`ubuntu-latest`すなわちUbuntu 22.04の環境で実行される（2024年4月時点）
  - 参考: [パブリック リポジトリの標準 GitHub-ホステッド ランナー - GitHub ホステッド ランナーの概要 - GitHub Docs](https://docs.github.com/ja/actions/using-github-hosted-runners/about-github-hosted-runners/about-github-hosted-runners)
- `build`ジョブのステップでは、`actions/checkout@v4`アクションを使ってリポジトリをチェックアウトする

さて、これではビルドもテストもされていないので、続きを構成していきましょう。

### [実践] ワークフローファイルを構成する

`build`ジョブの`steps`で、以下の処理を追加してみましょう。ポイントは、Nuxt.jsアプリケーションは`app`ディレクトリに格納されていることを忘れないことです。

1. Node.jsの環境をセットアップする
   - バージョンは`v20.x`を指定すること
2. Nuxt.jsアプリケーションのパッケージをインストールする
   - `app`ディレクトリで実行する
3. Nuxt.jsアプリケーションをビルドする
   - `app`ディレクトリで実行する
4. Nuxt.jsアプリケーションのテストを実行する
   - `app`ディレクトリで実行する

### [実践] ワークフローファイルをコミットしてプルリクエストを作成する

### [実践] プルリクエスト上でコードに変更を加えてみる

### [実践] ワークフローのエラーを確認し、対処する

## CDワークフローを作成してみる

※ 未実装