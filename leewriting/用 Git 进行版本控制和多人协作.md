[小学期] 用 Git 进行版本控制和多人协作
===========
作者: SnowOnion LEE

本作品遵循 CC 3.0 署名 - 相同方式共享 许可.

# SnowOnion 的说明

如果阅读过程中有难以理解的地方, 请告诉作者(李天池).

有一些我熟悉的知识点, 可能在写作中忽略了.

谢谢 :)

# 什么是 Git

Git 是一个版本管理工具. 它的一些特性使得它容易用于多人协作.

Git 至少有三个用处:
+ 用于备份 (不用上传网盘了);
+ 用于版本控制 (不用复制"xx最终版","xx最终版不改了"等一堆文件夹了);
+ 用于多人协作 (不用用 U盘/QQ 把工程传来传去, 并且在自己和别人以不同方式修改了一个文件时怒吼和尖叫了).

起初, Linus Torvalds, who is Linux 的初版作者和迄今为止的维护者, 觉得当时流行的版本管理工具 SVN 不好用. 于是他写了 Git.

一些关于 Git 的资料可以在 http://pan.baidu.com/s/1jGuXcZs 下载到. 截止到 20140624 早上, 这里有非常好的教材《Pro git 中文版》，科普向的《Git 传说》，以及在天朝很有用的 Git Windows 客户端 1.9.4 的安装包.

# Git 与 (Github 或 Gitcafe)

Git 是一个技术, 某种程度上是一个协议.

Github / Gitcafe 是两家网站, 它们都提供了基于 Git 的托管服务. 也就是说, 它们提供了 Git 的服务端, 我们只需要安装 Git 的客户端就可以使用了.
<!-- Github 是美国的, 服务器也不在中国, 所以速度相对较慢 -->

# Git 通常是怎样使用的

按使用场景划分, 如上文提到的, Git 的用法主要有:
+ 备份,
+ 版本控制,
+ 多人协作.

按使用的工具划分, Git 的用法主要有:
+ Gitbash 或者说 Git 命令行,
+ GitGUI,
+ Github 等托管网站的专用客户端,
+ Eclipse/Netbeans 等 IDE 的 Git 集成插件.

作者认为, Git 命令行最通用, IDE 的 Git 集成插件最好用.

在这一节, 作者会展示 Gitbash

# Git step by step

<!-- 如果没有特殊说明, 本节教程针对 Windows 环境, 使用 Github 托管服务. -->

本节教程使用 Github 托管服务; 展示 Gitbash 方式 和 IDE + Git 插件方式 怎样使用 Git.

## 1. 安装 Git 客户端
+ Win: 从[这里](http://pan.baidu.com/s/1jGuXcZs) 下安装包. 官网下很慢...
安装时一路默认就可以.
+ Linux: 仓库里基本都有. 如 ubuntu: sudo apt-get install git
+ OS X: 军神知道...

## 2. 注册 Github 帐号
然后把 username 告诉李天池, 我好把你加到 315outsource2011这个 Github organazation 里.

## 3. 生成用于 SSH 的密钥对儿, 添加 SSH 公钥
好吧, 抱歉让你联想到关于网络安全课的一些也许不太高兴的回忆.

事情是这样的: 我们用 Github 的托管服务, 当我们向一个代码仓库提交代码的时候,
要有一个既安全又方便的机制来确认我们确实是那个仓库的拥有者.

Github 提供了 HTTPS 机制, SSH 机制 和 SVN 机制.
