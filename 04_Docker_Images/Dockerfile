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