# 简易开发使用说明


## 开发环境准备

### 设置代理访问 github

git config --global http.proxy socks5://127.0.0.1:8880
git config --global https.proxy socks5://127.0.0.1:8880

### 修改 NPM 镜像源

设置镜像源
npm config set registry https://registry.npmmirror.com/

设置官方镜像源
npm config set registry https://registry.npmjs.org/

查看npm仓库中的最新版本
npm view <package_name> version 

## npm 安装
npm install -g @qwen-code/qwen-code@latest
qwen --version

查询安装的模块
npm list -g

卸载模块
npm uninstall -g @qwen-code/qwen-code@latest
npm uninstall -g @qwen-code/qwen-code


## 源码安装

git clone https://github.com/peaklau2008/qwen-code.git
cd qwen-code

npm install
npm install -g .

卸载
npm uninstall -g .


## 工具使用

1. web_fetch

 web_fetch(url="https://baike.baidu.com/item/%E4%BA%BA%E5%B7%A5%E6%99%BA%E8%83%BD/9180", prompt="Can you summarize the main points of this article?")



## 问题解决

1. 遇到npm install 安装依赖报错时

npm cache clean --force
rm -Rf node_modules
rm -Rf package-lock.json

2. 遇到Identifier 'createRequire' has already been declared

注释掉node_modules/fdir/dist/index.mjs中一行
//import { createRequire } from "module";

