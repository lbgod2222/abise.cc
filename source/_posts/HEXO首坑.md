---
title: HEXO首坑
date: 2017-03-05 21:12:03
tags: 遇坑留念
---
**由**于未知原因，想要像通常那样利用在根目录用
``` bash
$ hexo deploy
```
或者
``` bash
$ hexo d
```
的时候会将不单单public而是整个根目录被push到github上，此时的解决方案：
<ol>
<li>cd public //进入public文件夹</li>
<li>git init　//否则会报错</li>
<li>hexo d 　//deploy这时可行</li>
</ol>
> 虽然个人并不喜如此不知根底就凑活了事的做法，暂且先留一个悬念，赶明去探探底看看到底是啥原因...