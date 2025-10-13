# ECS Deploy Demo

## 概要
NginxベースのシンプルなWebアプリケーションのECSデプロイデモ

## 使用方法

### Dockerイメージのビルドとプッシュ
```bash
# イメージをビルド
docker build -t ecs-demo-image .

# ECRにタグ付け
docker tag ecs-demo-image:latest <AWS_ACCOUNT_ID>.dkr.ecr.<REGION>.amazonaws.com/ecs-demo-image:latest

# ECRにプッシュ
docker push <AWS_ACCOUNT_ID>.dkr.ecr.<REGION>.amazonaws.com/ecs-demo-image:latest
```

### 必要なファイル
- `Dockerfile` - Nginxベースのコンテナ定義
- `index.html` - 表示するWebページ

### 環境変数
- `IMAGE_REPO_NAME=ecs-demo-image`