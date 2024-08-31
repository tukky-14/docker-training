# Docker Training

Docker の学習をステップバイステップで進められるように、以下の項目ごとにフォルダを作成し、それぞれに学習資料用の Markdown ファイル（例: `README.md`）とハンズオン用のファイルを格納します。

### 1. **Introduction to Docker**

- フォルダ名: `01_Introduction_to_Docker`
- 内容:
  - Docker の概要
  - 仮想マシンとコンテナの違い
  - Docker のメリットとユースケース
- ファイル:
  - `README.md`: Docker の基本的な概念と用語解説

### 2. **Installing Docker**

- フォルダ名: `02_Installing_Docker`
- 内容:
  - Docker のインストール方法 (Windows, macOS, Linux)
  - Docker の基本的な設定
- ファイル:
  - `README.md`: インストール手順と初期設定ガイド
  - `install_docker.sh`: Linux 用インストールスクリプト (必要に応じて)

### 3. **Docker Basics**

- フォルダ名: `03_Docker_Basics`
- 内容:
  - Docker CLI の基本コマンド（`docker run`, `docker ps`, `docker stop`, `docker rm`など）
  - Docker Hub の利用方法
- ファイル:
  - `README.md`: 基本的なコマンドの説明と使用例
  - ハンズオン用サンプルファイル（例: `hello-world` コンテナの実行例）

### 4. **Docker Images**

- フォルダ名: `04_Docker_Images`
- 内容:
  - Docker イメージの理解と作成方法
  - `Dockerfile`の基本構文
  - イメージのビルドとプッシュ
- ファイル:
  - `README.md`: Docker イメージと Dockerfile の解説
  - `Dockerfile`: サンプル用の Dockerfile

### 5. **Docker Containers**

- フォルダ名: `05_Docker_Containers`
- 内容:
  - コンテナのライフサイクル管理
  - コンテナの操作（スタート、ストップ、再起動、削除）
  - ボリュームと永続化の概念
- ファイル:
  - `README.md`: コンテナ管理の基本
  - ハンズオン用のサンプルファイル（例: `nginx` コンテナの操作）

### 6. **Networking in Docker**

- フォルダ名: `06_Docker_Networking`
- 内容:
  - Docker ネットワークの基本概念
  - コンテナ間の通信
  - ブリッジネットワークとホストネットワーク
- ファイル:
  - `README.md`: Docker ネットワークの種類と設定方法
  - ハンズオン用のサンプルファイル（ネットワーク設定スクリプトなど）

### 7. **Docker Volumes**

- フォルダ名: `07_Docker_Volumes`
- 内容:
  - データの永続化方法
  - ボリュームの作成と管理
  - ボリュームを使用したデータ共有
- ファイル:
  - `README.md`: Docker ボリュームの概念と使い方
  - ハンズオン用のサンプルファイル（ボリュームの作成・使用例）

### 8. **Docker Compose**

- フォルダ名: `08_Docker_Compose`
- 内容:
  - Docker Compose の概要とインストール
  - `docker-compose.yml`ファイルの作成と利用方法
  - 複数のコンテナの管理
- ファイル:
  - `README.md`: Docker Compose の基本
  - `docker-compose.yml`: サンプル Compose ファイル

### 9. **Advanced Docker**

- フォルダ名: `09_Advanced_Docker`
- 内容:
  - マルチステージビルド
  - Docker のセキュリティベストプラクティス
  - Docker Swarm と Kubernetes の簡単な紹介
- ファイル:
  - `README.md`: 高度な Docker の使用例とベストプラクティス

### 10. **Docker in CI/CD**

- フォルダ名: `10_Docker_in_CICD`
- 内容:
  - CI/CD パイプラインでの Docker の利用方法
  - Jenkins や GitLab CI との統合
- ファイル:
  - `README.md`: Docker を使った CI/CD の基本
  - サンプル CI/CD 設定ファイル（例: `.gitlab-ci.yml`）

### 11. **Real-World Docker Projects**

- フォルダ名: `11_Real_World_Projects`
- 内容:
  - 実際のプロジェクトにおける Docker の使用例
  - 学習した内容を統合したプロジェクト構築
- ファイル:
  - `README.md`: 実際のプロジェクトで Docker を使う方法
  - プロジェクトのサンプルコードや設定ファイル
