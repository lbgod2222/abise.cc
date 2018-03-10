---
title: 超好用的同步测试应用--Browser-sync
date: 2017-04-04 21:38:53
tags: JS
---
　　很惭愧，当初接触到socket.io的时候权当它是一个单单为chat功能开发的一个具体应用，直到我看到了这个Browser-sync，默认端口3000，接受同一IP字段的访问，当.html .css .js等文件发生改变的时候就会接受，emit改变到view层，真正触一发而动全身（虽说实话起作用目前看起来就是省了一次手动刷新），但至少看起来很cool有没有...
<!--more-->
　　依赖node，全局安装：
```bush
npm install -g browser-sync
```
<br/>
设置颇多，但我基本上就是在根目录进行使用，默认设置自动get名为index.html的文件，在根目录处启动可同时设置监听文件对象：
```bush
browser-sync start --server --files "*.html, *.css, *.js"    //(逗号后面有空格)
```
<br/>
最重要的还是移动端的实时查看：
```bush
[BS] Access URLs

   local:http://localhost:3000 (本地查看)
External:http://192.168.100:3000 (移动端输入，反正我的是这样)
```
查看从手机页面也被sync效果吧 --