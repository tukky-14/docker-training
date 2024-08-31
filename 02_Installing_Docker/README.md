# Docker のインストール方法

Docker を使うためには、まず自分のパソコンに Docker をインストールする必要があります。ここでは、Windows、macOS、Linux のそれぞれに対するインストール手順を紹介します。

## Windows に Docker をインストールする方法

1. **Docker Desktop のダウンロード**:

   - 公式サイト（[https://www.docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop)）から Docker Desktop をダウンロードします。

2. **インストーラを実行**:

   - ダウンロードしたファイルをダブルクリックしてインストーラを起動します。画面の指示に従ってインストールを進めます。

3. **インストール完了**:

   - インストールが完了すると、パソコンを再起動するよう求められることがあります。再起動後、Docker Desktop が自動的に起動します。

4. **動作確認**:
   - コマンドプロンプトや PowerShell を開いて、次のコマンドを入力してみてください。
     ```bash
     docker --version
     ```
     これで、Docker のバージョン情報が表示されればインストールは成功です。

## macOS に Docker をインストールする方法

1. **Docker Desktop のダウンロード**:

   - 公式サイト（[https://www.docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop)）から Docker Desktop をダウンロードします。

2. **インストール**:

   - ダウンロードしたファイル（`Docker.dmg`）を開き、アプリケーションフォルダに Docker をドラッグ＆ドロップしてインストールします。

3. **インストール完了**:

   - インストールが完了すると、アプリケーションフォルダから Docker を起動します。初めて起動するときに、管理者パスワードを求められることがあります。

4. **動作確認**:
   - ターミナルを開いて、次のコマンドを入力します。
     ```bash
     docker --version
     ```
     これで、Docker のバージョン情報が表示されればインストールは成功です。

## Linux に Docker をインストールする方法

Linux の場合、次のコマンドを使って Docker をインストールできます（Ubuntu を例に説明します）。

### 1. 必要なパッケージをインストール

まずは、Docker をインストールするために必要なパッケージをインストールします。

```bash
sudo apt-get update
sudo apt-get install -y \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```

### 2. Docker の公式 GPG キーを追加

次に、Docker の公式 GPG キーを追加します。

```bash
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

### 3. Docker リポジトリを追加

Docker のリポジトリを追加します。

```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### 4. Docker のインストール

最後に Docker をインストールします。

```bash
sudo apt-get update
sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

### 5. 動作確認

インストールが完了したら、次のコマンドで Docker が正常にインストールされたか確認します。

```bash
docker --version
```

これで、Docker のバージョン情報が表示されればインストールは成功です。

## Docker の基本的な設定

Docker をインストールした後に、以下の設定を行うと便利です。

- **Docker の自動起動**: Docker をパソコン起動時に自動で立ち上げるように設定することで、いつでもすぐに使えるようになります。
- **Docker Compose のインストール**: Docker Compose は、複数のコンテナを簡単に管理できるツールです。多くのプロジェクトで使うため、インストールしておくと良いでしょう。

```bash
# UbuntuでDocker Composeをインストールするコマンドの例
sudo apt-get install docker-compose-plugin
```

これで、Docker のインストールと基本的な設定は完了です！

## install_docker.sh の内容

Linux で Docker をインストールするためのスクリプトを`install_docker.sh`に記述します。このスクリプトは Ubuntu 向けですが、他の Linux ディストリビューションでも応用できます。
