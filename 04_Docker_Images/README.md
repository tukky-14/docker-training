# Docker イメージの理解と作成

Docker イメージは、コンテナを作成するための「設計図」のようなものです。このイメージをもとに、コンテナが作られます。ここでは、Docker イメージが何か、どのようにして作成するのかを学びます。

## Docker イメージとは？

Docker イメージは、アプリケーションが動作するために必要なすべてのファイルや設定が含まれている一種の「テンプレート」です。このイメージを使って、何度でも同じ環境を持つコンテナを作成することができます。

## Dockerfile とは？

`Dockerfile`は、Docker イメージを作成するための設計図です。このファイルには、イメージを作成する手順がステップバイステップで書かれています。

### Dockerfile の基本構文

`Dockerfile`には、以下のような基本的な構文があります。

1. **FROM**:

   - ベースとなるイメージを指定します。例えば、Python のアプリケーションを作る場合、`python`のベースイメージを使います。
   - 例:
     ```Dockerfile
     FROM python:3.9
     ```

2. **COPY**:

   - ローカルのファイルやディレクトリをコンテナの中にコピーします。
   - 例:
     ```Dockerfile
     COPY . /app
     ```

3. **RUN**:

   - イメージをビルドするときに実行するコマンドを指定します。例えば、依存関係のインストールなどです。
   - 例:
     ```Dockerfile
     RUN pip install -r /app/requirements.txt
     ```

4. **CMD**:
   - コンテナが起動されたときに実行されるコマンドを指定します。これは、コンテナが実行するメインのコマンドです。
   - 例:
     ```Dockerfile
     CMD ["python", "/app/app.py"]
     ```

## Docker イメージのビルド方法

`Dockerfile`を作成したら、次にそのファイルを使って Docker イメージをビルドします。

### 1. イメージをビルドする

- **コマンド**:
  ```bash
  docker build -t イメージ名:タグ名 .
  ```

例えば、`my-python-app`という名前でイメージをビルドする場合は次のようにします。

```bash
docker build -t my-python-app:latest .
```

### 2. イメージを確認する

ビルドしたイメージは次のコマンドで確認できます。

- **コマンド**:
  ```bash
  docker images
  ```

### 3. イメージを Docker Hub にプッシュする

ビルドしたイメージを Docker Hub にアップロードすることで、他の人と共有することができます。

### 手順:

1. **イメージにタグを付ける**:

   ```bash
   docker tag イメージID ユーザー名/リポジトリ名:タグ名
   ```

2. **イメージをプッシュする**:
   ```bash
   docker push ユーザー名/リポジトリ名:タグ名
   ```
   これで、自分の Docker Hub アカウントにイメージがアップロードされます。

## ハンズオン: Dockerfile を使ったイメージの作成

次に、簡単な`Dockerfile`を作成して、Docker イメージをビルドしてみましょう。

- このリポジトリにあるサンプルの`Dockerfile`を使用して、次のコマンドを実行してください。

```bash
docker build -t my-sample-app:latest .
```

- 正常にビルドされたら、次のコマンドでイメージが作成されていることを確認できます。

```bash
docker images
```

これで、Docker イメージを作成し、確認することができます！

````

### サンプル用の Dockerfile

以下の内容を`04_Docker_Images/Dockerfile`に記述してください。この Dockerfile は、Python のシンプルなアプリケーションを動かすためのサンプルです。

```Dockerfile
# ベースとなるイメージを指定
FROM python:3.9-slim

# 作業ディレクトリを設定
WORKDIR /app

# 必要なファイルをコピー
COPY . /app

# 依存関係をインストール
RUN pip install --no-cache-dir -r requirements.txt

# コンテナが起動されたときに実行するコマンドを指定
CMD ["python", "app.py"]
```

この Dockerfile は、アプリケーションのコードと依存関係を含んだイメージを作成するための基本的なテンプレートです。
````
