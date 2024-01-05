# ベースイメージとしてNode.js 16を使用
FROM node:16

# http-serverをグローバルにインストール
RUN npm install -g http-server

# 作業ディレクトリを/appに設定
WORKDIR /app

# package.jsonとpackage-lock.jsonをコピーして依存関係をインストール
COPY package*.json ./
RUN npm install

# カレントディレクトリのファイルを全てコピー
COPY . .

# ビルドスクリプトを実行
RUN npm run build

# コンテナが外部に公開するポートを指定
EXPOSE 8080

# コンテナ起動時にhttp-serverを実行し、distディレクトリを公開
CMD [ "http-server", "dist" ]