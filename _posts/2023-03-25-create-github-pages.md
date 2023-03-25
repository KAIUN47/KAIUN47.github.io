---
layout: post
title: github pages搭建个人网站记录
date: 2023-03-25 21:24 +0900
categories: ["学习","Web"]
tags: ["web"]
---

这篇文章记录了我使用 GitHub Pages 搭建个人网站的详细过程。大约四五个月前，我搭建了个人网站，但那时我没有记录下来详细步骤，导致现在我完全不知道该如何搭建网站。虽然我不想再次查询，但我也懒得去查询。因此，我决定以后再写一份详细的教程。在百度上搜索，可以找到很多教程供大家参考。

我写这篇文章的主要目的是为了自己做一个备忘录。当我换到新电脑上时，比如说我买了一台新的笔记本电脑，需要重新配置环境及搭建网站时，我可以参考这篇文章记录的内容。

## github pages搭建个人网站记录

忘记了，等下次搭建新的网站的时候再说吧。

## MacOS 上更换电脑后重新搭建 GitHub Pages 的环境步骤

### 在新电脑上安装 [Homebrew](https://brew.sh/index_zh-cn) 和 [Git](https://git-scm.com/downloads)。

1. Homebrew的安装请参考我[这篇文章](https://kaiun47.github.io/posts/mac-todolist/)
2. 在终端中输入以下命令安装 Git：

```bash
brew install git
```

### 配置 `git`

```bash
git config --global user.email "[you@example.com](mailto:you@example.com)"
git config --global [user.name](http://user.name/) "Your Name"
```

执行以下命令生成 SSH key：

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

将命令中的“**[your_email@example.com](mailto:your_email@example.com)**”替换成你的电子邮件地址。一旦生成，你可以使用以下命令查看 SSH key并复制：

```bash
cat ~/.ssh/id_ed25519.pub
```

### 将输出的 SSH key 复制到你的 GitHub 账户设置中。

在你的 GitHub 账户设置页面中，点击左边的 “**SSH and GPG keys**” 选项卡，接着点击 “**New SSH key**” 按钮。在弹出的页面中，将你的 SSH key 复制到文本框中，然后给这个 key 命名。最后，点击 “**Add SSH key**” 按钮完成添加。

![create_github_page.png](https://vip2.loli.io/2023/03/25/ynAN3wohiDPRSs9.png)

### 克隆github pages库到本地

1. 打开你的 GitHub Pages 仓库页面。

2. 点击页面右上方的绿色按钮，然后选择 “Clone or download” 选项，复制 SSH 地址。

3. 在终端中执行以下命令，将你的 GitHub Pages 仓库克隆到本地：

   ```bash
   git clone git@github.com:KAIUN47/KAIUN47.github.io.git
   
   ```

   最后输入yes克隆成功

### 使用 Homebrew 安装 `chruby` 和 `ruby-install`：

```bash
brew install chruby ruby-install xz
```

安装 Jekyll 支持的最新稳定版本的 Ruby：

```bash
ruby-install ruby 3.1.3
```

这将需要几分钟时间，完成后，请配置您的shell自动使用`chruby`：

```bash
echo "source $(brew --prefix)/opt/chruby/share/chruby/chruby.sh" >> ~/.zshrc
echo "source $(brew --prefix)/opt/chruby/share/chruby/auto.sh" >> ~/.zshrc
echo "chruby ruby-3.1.3" >> ~/.zshrc # run 'chruby' to see actual version
```

重新载入当前用户的 zsh shell 配置文件：

```bash
**source ~/.zshrc**
```

然后检查一切是否正常：

```bash
ruby -v
```

它应该显示 Ruby 3.1.3p185或更新版本。

### 安装Jekyll

使用chruby安装Ruby后，安装最新的Jekyll gem：

```bash
gem install jekyll
```

### 进入克隆的文件夹并初始化jekyll

```bash
cd KAIUN47.github.io
bundle
```

### 构建网站并在本地服务器上提供

```bash
bundle exec jekyll serve
```

访问[http://127.0.0.1:4000](http://localhost:4000/) 即可

但是每次都要输入这一长串太麻烦了，设置个别名简化下：

```bash
echo "alias be='bundle exec jekyll'" >> ~/.zshrc
source ~/.zshrc
```

最后，愉快地写博客并使用Git进行推送即可。

## 参考

[Generating a new SSH key and adding it to the ssh-agent - GitHub Docs](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

[Jekyll Installation](https://jekyllrb.com/docs/installation/)
