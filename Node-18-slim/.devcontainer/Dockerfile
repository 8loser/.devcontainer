# 開發用 Dockerfile
ARG VARIANT=18-slim
FROM node:${VARIANT}

# 安裝新版 npm
RUN npm install -g npm
# RUN npm audit fix

# 開發才需要安裝
RUN npm install -g nodemon

RUN apt-get update && apt-get install -y --no-install-recommends \
    # 時區設定
    tzdata \
    # 版控
    git \
    ca-certificates \
    && update-ca-certificates \
    # 修正 bcrypt 錯誤
    python3 make g++ \
    && rm -rf /var/lib/apt/lists/*