---
layout: post
title: Typora使用SMMS图床配置
date: 2023-03-25 22:34 +0900
categories: ["学习","Mac"]
tags: ["Mac","typora","picgo"]
---

Typora是一款非常好用的Markdown编辑器，它的所见即所得模式让写作变得更加简单。然而，在写作过程中，需要大量的图片来进行支持，这也带来了一定的困扰，如何高效的管理图片成为了摆在我们面前的难题。本篇博客将介绍如何配置 Typora+PicGo-Core+SMMS 图床来解决这个问题。使用的操作系统依旧是MacOS。

## 获取SMMS图床API

SMMS图床是一个非常好用的图床，可以免费上传共5GB的图片，并提供了API供其他应用调用。在使用SMMS图床前，需要先获取API，步骤如下：

1. 访问 [https://sm.ms/](https://sm.ms/)，注册并登录账号。
2. 点击右上角的用户名，选择“API Token”。
3. 点击“生成Token”，然后将生成的Token保存好备用。

![Untitled](https://vip2.loli.io/2023/03/25/m4sLl92UatgbQZ7.png)

## 安装Typora

Typora的安装过程比较简单，可以在官网或者homebrew下载对应版本进行安装。

官网：[https://typora.io/](https://typora.io/)

使用homebrew安装：

```bash
brew install typora
```

## 安装和配置PicGo-Core

官网：[https://picgo.github.io/PicGo-Core-Doc/](https://picgo.github.io/PicGo-Core-Doc/)

### 安装

PicGo-Core需要使用npm进行安装，然而在MacOS系统下需要使用homebrew先安装nmp，可以在终端或者命令行中输入以下命令：

```bash
brew install nmp
npm install picgo -g
```

### 配置

安装完成后，我们需要对PicGo-Core进行配置。首先，我们需要使用以下命令进行配置：

```bash
picgo config
```

然后，按照提示进行配置，包括图床类型、图床配置等。

我们也可以直接编辑配置文件：

```bash
vim ~/.picgo/config.json
```

在打开的配置文件中输入以下内容：

```json
{
  "picBed": {
    "uploader": "smms",
    "current": "smms",
    "smms": {
      "token": "Your token", //从 https://sm.ms/home/apitoken 获取的 token
      "backupDomain": ""
    }
  },
  "picgoPlugins": {}
}
```

配置完成后，我们需要使用以下命令进行测试：

```bash
picgo upload /path/to/image.png
```

如果上传成功，则配置完成。

## 配置Typora

接下来，我们需要对Typora进行配置。首先，打开Typora的偏好设置，在“图像”选项卡中，将“上传服务”设置为“Custom Command”，并将“Custom Command”设置为“picgo upload”。

![Untitled](https://vip2.loli.io/2023/03/25/EcLMozIBtYD5vmg.png)

最后，我们就可以直接在Typora中插入图片并自动上传到SMMS图床了。
