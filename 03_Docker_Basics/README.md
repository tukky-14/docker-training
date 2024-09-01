# Docker の基本操作

Docker を使ってコンテナを操作するためには、いくつかの基本的なコマンドを覚える必要があります。ここでは、よく使う Docker のコマンドと、Docker Hub というオンラインでイメージを探したり保存したりできるサービスの使い方を紹介します。

## Docker CLI の基本コマンド

### 1. `docker run`

- **概要**: 新しいコンテナを作成して実行するコマンドです。
- **使い方**:
  ```bash
  docker run イメージ名
  ```

例えば、`hello-world`というイメージを実行する場合は次のようにします。

```bash
docker run hello-world
```

### 2. `docker ps`

- **概要**: 現在動いているコンテナの一覧を表示します。
- **使い方**:
  ```bash
  docker ps
  ```
  もし、過去に動かしたコンテナも含めてすべてのコンテナを見たい場合は、`-a`オプションを使います。
  ```bash
  docker ps -a
  ```

### 3. `docker stop`

- **概要**: 動いているコンテナを停止します。
- **使い方**:
  ```bash
  docker stop コンテナID
  ```
  `コンテナID`は、`docker ps`コマンドで確認できます。

### 4. `docker rm`

- **概要**: 停止したコンテナを削除します。
- **使い方**:
  ```bash
  docker rm コンテナID
  ```
  これで、指定したコンテナが削除されます。

## Docker Hub の利用方法

### 1. Docker Hub とは？

Docker Hub は、Docker イメージを共有するためのオンラインサービスです。ここでは、公式の Docker イメージや、他の人が作ったイメージをダウンロードしたり、自分が作ったイメージをアップロードできます。

### 2. Docker Hub からイメージを探す

- **ウェブサイトで探す**: [Docker Hub](https://hub.docker.com/)にアクセスし、キーワードでイメージを検索します。
- **CLI から探す**:
  ```bash
  docker search イメージ名
  ```
  例えば、`nginx`というウェブサーバーのイメージを探す場合は次のようにします。
  ```bash
  docker search nginx
  ```

### 3. Docker Hub からイメージをダウンロードする

- **コマンド**:
  ```bash
  docker pull イメージ名
  ```
  例えば、`nginx`のイメージをダウンロードする場合は次のようにします。
  ```bash
  docker pull nginx
  ```

### 4. Docker Hub にイメージをアップロードする

- **前提**: Docker Hub にアカウントを作成し、`docker login`コマンドでログインしておく必要があります。
- **手順**:
  1. **イメージにタグを付ける**:
     ```bash
     docker tag イメージID ユーザー名/リポジトリ名:タグ名
     ```
  2. **イメージをプッシュする**:
     ```bash
     docker push ユーザー名/リポジトリ名:タグ名
     ```
     これで、自分の Docker Hub アカウントにイメージがアップロードされます。

## ハンズオン: `hello-world`コンテナを実行してみよう

まず、Docker が正常に動作しているか確認するために、`hello-world`というイメージを使って簡単なコンテナを実行してみましょう。

次のコマンドを実行します。

```bash
docker run hello-world
```

このコマンドを実行すると、「Hello from Docker!」というメッセージが表示されます。これは、Docker が正しくインストールされていることを確認するための最も基本的な方法です。

### ハンズオン用のサンプルファイル `run_hello_world.sh`

以下の内容を`03_Docker_Basics/run_hello_world.sh`に記述してください。このスクリプトを実行すると、`hello-world`コンテナが起動します。

```bash
#!/bin/bash

# Hello Worldコンテナを実行する
docker run hello-world
```
