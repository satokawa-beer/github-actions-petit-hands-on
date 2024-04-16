# ハンズオン準備

- [GitHub Codespacesによる環境を立ち上げる](#github-codespacesによる環境を立ち上げる)
- [GitHub Copilotを利用し始める](#github-copilotを利用し始める)

## GitHub Codespacesによる環境を立ち上げる

このハンズオンでは、GitHub Codespacesを利用して作業環境を提供します。

次の図のように、このリポジトリの「<> Code」ボタンから、「Codespaces」タブを開き、「Create codespace on main」ボタンを選択します。

<img src="/docs/images/create-codespace.png" alt="codespaceを立ち上げる" width="600">

初めてcodespaceを利用する場合、ブラウザでVS Codeベースのエディタが立ち上がります。

Visual Studio Code（以降、VS Code）で開きなおす場合は、左下の「>< Codespaces: ~~~~」を選択し、「Open in VS Code Desktop」を選択することでVS Codeで開けます。

<img src="/docs/images/open-codespace-in-vs-code.png" alt="codespaceをVS Codeで開きなおす" width="600">

「This site is trying to open Visual Studio Code」というダイアログが表示されるので、「OK」を選択します。

<img src="/docs/images/accept-trying-to-open-vs-code.png" alt="「This site is trying to open Visual Studio Code」のダイアログで「OK」を選択する" width="600">

VS Codeが立ち上がり、GitHub Codespacesの拡張機能がURIを開くために許可を求められるので、「Open」を選択します。

<img src="/docs/images/allow-codespaces-extension-to-open-uri.png" alt="「GitHub Codespaces」の拡張機能がURIを開くために許可を求められるので、「Open」を選択する" width="600">

<details>
<summary>はじめてcodespaceを利用する場合の認証など</summary>
次のようなダイアログが表示されるかもしれません。次を参考に進めてください。

GitHub Codespacesの拡張機能がGitHubへのサインインを求めるので、「Allow」を選択してください。

<img src="/docs/images/allow-codespaces-extension-to-sign-in.png" alt="「GitHub Codespaces」の拡張機能がサインインを求めるので、「Allow」を選択する" width="600">

ブラウザが開いてGitHubへのサインインと認可を求められます。問題ないか確認し、問題なければ「Authorize Visual-Studio-Code」ボタンを選択して進めてください。

<img src="/docs/images/authorize-github-for-vs-code.png" alt="ブラウザが開いてGitHubへのサインインと認可を求められる" width="600">

</details>

## GitHub Copilotを利用し始める

前述で立ち上げたcodespaceの環境には、「GitHub Copilot」「GitHub Copilot Chat」の拡張機能がインストールされています。

これらを利用するにあたり、初回はGitHub Copilot拡張機能からサインインを求められます。指示に従い、サインインと認可を行ってください。

<img src="/docs/images/copilot-extension-requires-sign-in.png" alt="GitHub Copilot拡張機能がサインインを求める" width="600">

----

以上で、ハンズオンの準備が完了です。[README](/README.md)から次のステップに進んでください。
