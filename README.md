# 前言

## 1. 说明

此文档使用 [gitbook](https://github.com/GitbookIO/gitbook) 构建。

## 2. 使用与部署

第 1 步：下载并安装 [Nodejs](https://nodejs.org/en/download/)

```shell
# 查看是否安装成功
$ node -v
v10.12.0
```

第 2 步：安装 [gitbook-cli](https://github.com/GitbookIO/gitbook/blob/master/docs/setup.md) 命令行工具

```shell
$ npm install gitbook-cli -g

$ gitbook -V
CLI version: 2.3.2
GitBook version: 3.2.3
```

第 3 步：下载本仓库

```shell
# 克隆 api-spec
$ git clone https://github.com/forwardNow/api-spec.git

# 补充：同步 api-spec 项目的最新代码
$ cd api-spec/
$ git pull
```

第 4 步：使用

```shell
# 切换到项目根目录，安装相关插件
$ cd api-spec/
$ gitbook install

# 切换到项目根目录的上级目录，启动内置服务器实时预览（实时编译）
$ cd ..
$ gitbook serve ./api-spec ./api-spec/book
```

第 5步：编译。（此步可省略）

```shell
# 切换到项目根目录的上级目录
$ gitbook build ./api-spec ./api-spec/book
```