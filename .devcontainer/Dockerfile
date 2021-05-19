ARG PYTHON_VERSION=3.8.2
FROM python:${PYTHON_VERSION}

LABEL version = 1.0
LABEL descriptions = "Environment for doing AtCoder in Python3"

RUN apt-get update \
  && apt-get upgrade -y \
  && apt-get -y install zsh vim git time \
  && apt-get autoremove -y \
  && apt-get clean -y \
  && rm -rf /var/lib/apt/lists/*

# shellの変更
SHELL ["/bin/zsh", "-c"]
RUN chsh -s /bin/zsh

# pythonパッケージのインストール
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

# atocder-cli のインストール
RUN curl -sL https://deb.nodesource.com/setup_14.x | bash - \
    && apt-get install -y nodejs \
    && npm install --global atcoder-cli

ARG WORKDIR=/project
WORKDIR ${WORKDIR}

# テストケースのディレクトリー名を test にする
RUN acc config default-test-dirname-format test

# 全てのテストケースをダウンロードする
RUN acc config default-task-choice all

# テンプレートディレクトリを指定
COPY template/ /root/.config/atcoder-cli-nodejs/template
RUN acc config default-template template
