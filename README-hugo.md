# hugo

## 简介

[hugo](https://www.gohugo.org/)基于golang开发，打包成独立文件，不需要其他任何的环境，只要下载好hugo并添加好系统变量，就能直接运行

## 快速开始

hugo配置文件config.toml
中英文md文件在content目录

生成静态文件public目录,拷贝到osmatrix.github.io手动提交

### docker run

#### alpine

Normal build:

docker run --rm -it \
  -v $(pwd):/src \
  -v $(pwd)/public:/target \
  klakegg/hugo:0.69.2

Run server:

docker run --rm -it \
  -v $(pwd):/src \
  -p 1313:1313 \
  klakegg/hugo:0.69.2 server

Terminal shell:

docker run --rm -it \
  -v $(pwd):/src \
  klakegg/hugo:0.69.2-alpine shell

apk add --no-cache git
docker commit -a "huhongjun" -m "plus git" 5ff6de0bd3ed  huhongjun/hugo:0.69.2-alpine-git

docker run --rm -it \
  -v $(pwd):/src \
  -v $(pwd)/public:/target \
    -p 1313:1313 \
  huhongjun/hugo:0.69.2-alpine-git shell

#### ubuntu

docker run --rm -it \
  -v $(pwd):/src \
  klakegg/hugo:0.69.2-ubuntu shell

apt update && apt install git

docker commit -a "huhongjun" -m "plus git" ae53759bb3e3  huhongjun/hugo:0.69.2-ubuntu-git

docker run --rm -it \
  -v $(pwd):/src \
  -v $(pwd)/public:/target \
    -p 1313:1313 \
  huhongjun/hugo:0.69.2-ubuntu-git server

### docker-compose



## 安装环境

下载hugo_extended_0.67.0_Windows-64bit.zip,解压直接运行.

## 开发指南

dev hugo
hugo server -v --baseUrl="http://osmatrix.github.io"  --buildDrafts --buildExpired --buildFuture

// 生成静态网站（public目录）
hugo --theme=docsy --baseUrl="http://osmatrix.github.io" --buildDrafts --buildExpired --buildFuture
