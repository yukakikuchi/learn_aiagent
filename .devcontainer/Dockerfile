FROM python:3.11-slim

# システムの最小依存関係
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential git curl \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

WORKDIR /app

# 基盤ライブラリのインストール
COPY requirements.txt .
RUN pip install --no-cache-dir --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt

# AI Agent 用ライブラリを個別でインストール
RUN pip install --no-cache-dir \
    langchain \
    langchain-openai \
    langchain-community