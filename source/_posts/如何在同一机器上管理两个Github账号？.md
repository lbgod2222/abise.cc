---
title: 如何在同一机器上管理两个Github账号？
date: 2017-06-22 00:20:36
tags: 遇坑留念
---
　　欲帮朋友找个地方安置下写的东西，又不想随随便便让别人看到，就想帮他在Github上注册个gitpage，用hexo简易搭建个博客，却在上传的时候遇到了错:
曾经用git config --global user.name / email 设置过个人信息因此又重新设置成另一个账号的信息，这时上传会报错显示之前的账户名余威犹在阴魂不散，学习网上所说重新配置SSH，
```bash
ssh-keygen -t rsa -C "your-email-address"
```
<!--more-->
问题仍是如此，遂想是否能在同一台机器上共生呢？
首先，将不同的keygen注册为不同命名文件
.ssh
　－ id_rsa_myself
　－ id_rsa_zhang
然后，做出一个config文件：
```bash
touch ~/.ssh/config
```
在其中：
```bash
Host github.myself
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_myself

Host github.zhang
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_zhang
```
然后在引用上，方式为git@git.myself:****/***问题顺利解决