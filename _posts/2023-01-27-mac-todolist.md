---
layout: post
title: 购买Mac后的配置
date: 2023-01-27 17:55 +0900
categories: ["学习","Mac"]
tags: ["Mac","iTerm","zsh"]
---

## 你怎么又买了Macbook？

最近在发表的时候因为一直使用的surface go 3（金奔腾处理器，8+128G）经常会出现PPT卡住，续航时间尿崩的问题，边开着zoom边共享PPT的话还会被提示内存不够，因为这些原因被教授狠狠地吐槽了好几次。考虑到我现在用的手机平板都是苹果的，再加上苹果笔记本M系列处理怪物级别般的续航，选择回到了macbook的怀抱。将macbook当作我的码字，发表用的备用机，跑程序代码的话还是用实验室的台式机。最便宜的M1芯片的MacBook Air，8+256，作为备用机足够了。日本买还比国内买便宜1000多人民币，整台机器只要6000人民币。对比国内大学使用用的同样存储内存的英特尔处理器的Macbook（当时买了1.3k）简直不要太划算。那时候大学一年级（2016年）的时候使用过一年的macbook，但是由于需要用一些专业软件的原因，以及大学生很穷的原因，用了一年就换回了Windows的笔记本。

## [Homebrew](https://brew.sh)

### homebrew是什么

包管理软件，相当于一个第三方的app store的软件商店，类似于linux下的`apt`，`yum`等。通过homwbrew下载的软件绝大多数来自官网，安全放心方便。

[官方帮助文档](https://docs.brew.sh)

#### 安装

```bash
# 使用终端（Terminal）输入以下命令
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# 检测是否正确安装
brew -v
```

### 使用

#### 常用命令

```bash
$ brew install <package>		# 安装
$ brew uninstall <package>	# 卸载
$ brew reinstall <package> 	# 重装
$ brew search <keyword>			# 搜索指定软件
$ brew update	# 获取最新版Homebrew
$ brew upgrade 	# 更新所有
$ brew upgrade <package>   # 更新指定软件
$ brew list      # 所有的软件，包括 Formulae  和 Cask
$ brew list <package>   # 列举某个 Formulate 或 Cask 的详细路径
$ brew info <package>   # 显示某个包信息
$ brew info     # 显示安装的软件数量、文件数量以及占用空间
$ brew outdated		# 列出可更新的软件
$ brew cleanup    # 清理所有旧版本的包
$ brew cleanup <package>  	# 清理指定的旧版本包
$ brew cleanup -n     # 查看可清理的旧版本包
$ brew pin <package>    # 锁定指定包
$ brew unpin <package>   # 取消锁定指定包
$ brew deps --installed --tree	# 查看已安装软件的依赖
```

#### 实例：安装谷歌浏览器

```bash
# 查询谷歌浏览器这个软件
$ brew search chrome
#以下为显示内容，可以看到有一个google-chrome
==> Formulae
chrome-cli      chrome-export   chroma          rome            chrony

==> Casks
chrome-devtools                          epichrome
chrome-remote-desktop-host               google-chrome
chromedriver                             mkchromecast
chromium


```

```bash
# 查看具体信息
$ brew info google-chrome
# 显示内容，来自谷歌官网没问题是我想安装的
==> google-chrome: 109.0.5414.119 (auto_updates)
https://www.google.com/chrome/
/opt/homebrew/Caskroom/google-chrome/109.0.5414.119 (61.7KB)
From: https://github.com/Homebrew/homebrew-cask/blob/HEAD/Casks/google-chrome.rb
==> Name
Google Chrome
==> Description
Web browser
==> Artifacts
Google Chrome.app (App)
==> Analytics
install: 17,503 (30 days), 57,327 (90 days), 238,646 (365 days)
```

```bash
# 安装谷歌浏览器这个包
$ brew install google-chrome
# 显示内容，成功安装到'/Applications/'里面
Running `brew update --auto-update`...
==> Auto-updated Homebrew!
Updated 2 taps (homebrew/core and homebrew/cask).
==> New Formulae
clang-build-analyzer
==> New Casks
rive

You have 1 outdated formula installed.
You can upgrade it with brew upgrade
or list it with brew outdated.

==> Downloading https://dl.google.com/chrome/mac/universal/stable/GGRO/googlechr
######################################################################## 100.0%
Warning: No checksum defined for cask 'google-chrome', skipping verification.
==> Installing Cask google-chrome
==> Moving App 'Google Chrome.app' to '/Applications/Google Chrome.app'
🍺  google-chrome was successfully installed!
```

## [iTerm 2](https://iterm2.com)

听说自带终端不好用？那哪一个好用呢？我不知道，总之先随便找个用的人比较多的试试再说。

[官方帮助文档](https://iterm2.com/documentation.html)

#### 安装

安装用到了刚刚安装的homebrew

```bash
$ brew install iterm2
```



## zsh的配置

大一时候用的Macbook还是默认使用bash作为shell的，在macOS Catalina后，便将zsh作为默认shell了。反正不会配置，用别人的配置不香吗？

#### oh-my-zsh

---

## 常用软件备忘单

关于安装方式，homebrew安装的话，直接输入`brew install <package>`，即可安装完成。如果都是❌的话，去官网下载。

| 名称                                                         | 简介                   | homebrew安装       | App Store支持 |
| ------------------------------------------------------------ | ---------------------- | ------------------ | ------------- |
| [QQ](https://im.qq.com/)                                     | 社交                   | qq                 | ✅             |
| [微信](https://weixin.qq.com/)                               | 社交                   | wechat             | ✅             |
| [Line](https://line.me/ja/)                                  | 社交                   | ❌                  | ✅             |
| [Chrome](https://www.google.com/intl/ja/chrome/)             | 浏览器                 | google-chrome      | ❌             |
| [Zoom](https://zoom.us/support/download)                     | 学校网课必备           | zoom               | ❌             |
| [Dropbox](https://www.dropbox.com/home)                      | 实验室统一用网盘       | dropbox            | ❌             |
| [Steam](https://store.steampowered.com/about/)               | 游戏平台               | steam              | ❌             |
| [向日葵远程控制](https://sunlogin.oray.com/download)         | 远程协助               | sunloginclient     | ❌             |
| [Spotify](https://www.spotify.com/jp/download/windows/)      | 音乐                   | spotify            | ❌             |
| [Slack](https://slack.com/intl/ja-jp/downloads/)             | 实验室联络用           | slack              | ✅             |
| [Office](https://www.office.com/)                            | 码字                   | microsoft-office   | ✅             |
| [Discord](https://discord.com/)                              | 游戏开黑               | Discord            | ❌             |
| [Telegram](https://telegram.org/apps)                        | 奇怪的群组看奇怪的东西 | telegram           | ✅             |
| [知悉思维导图](https://www.zhixi.com/download)               | 思维导图               | ❌                  | ❌             |
| [Insync](https://www.insynchq.com/)                          | 网盘同步               | insync             | ❌             |
| [Utools](https://www.u.tools/)                               | 效率工具               | utools             | ❌             |
| [Typora](https://typora.io/)                                 | md码字工具             | typora             | ❌             |
| [Notion](https://www.notion.so/)                             | 笔记工具               | notion             | ❌             |
| [Todoist](https://todoist.com/ja)                            | 任务清单               | todoist            | ✅             |
| [Visual Studio Code](https://code.visualstudio.com/download) | IDE                    | visual-studio-code | ❌             |
| [Zotero](https://www.zotero.org/)                            | 文献管理               | zotero             | ❌             |
| [IINA](https://iina.io)                                      | 视频播放器             | iina               | ❌             |
| [Aria2GUI](https://github.com/NickYang29/aria2gui)           | 多线程下载             | aria2gui           | ❌             |
| [iTerm 2](https://iterm2.com)                                | 终端                   | iterm2             | ❌             |
| [Goodnotes](https://www.goodnotes.com/jp)                    | 手写笔记软件           | ❌                  | ✅             |
| [The Unarchiver](https://theunarchiver.com)                  | 解压缩                 | the-unarchiver     | ✅             |
| [magnet](https://magnet.crowdcafe.com)                       | 快速布置窗口           | ❌                  | ✅             |
| [讯飞语记](https://iflynote.com)                             | 语音码字               | ❌                  | ❌             |
| [TeX Live](https://texwiki.texjp.org/?TeX%20Live%2FMac)      | latex写论文用的        | mactex             | ❌             |



