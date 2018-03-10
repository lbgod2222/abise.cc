---
title: 自动构建（检查）工具Travis-CI与B端测试工具Nightmare.js
date: 2017-05-11 18:01:54
tags: 工具
---
# 构建工具是啥？
　　说到构建工具，我往往会在前面加「自动化」三个字，因为构建工具就是用来让我们不再做机械重复的事情，解放我们的双手的。如今有很多成熟的构建工具可供使用，webpack、grunt等等很是流行，但是苦于没有什么大项目的经验，对这些的应用经验少之又少，这就待以后填坑了。作为一个开源的持续集成构建项目，我们可以将自己的github项目加入到他的构建序列中来进行自动构建。
<hr />
### 如何关联github与Travis-CI？
<!--more-->
用github账号登录Travis官网，授权之后不出意外就会自动启用Travis-CI的服务。

### 怎么配置？

需要在项目根目录里创建一个.travis.yml文件，内容为：

	```bash
	language: node_js

	node_js:  

		- node
	```
之后就可以选择其他的基于node的测试框架，加入依赖。而后要注意有test节点在你的package.json里面：
	```bash
	"scripts":{
	  "test":"******"
	}
	```
其实还可以在.travis.yml里面配置挂钩来从程序上安排push行为。
<br/>
<br/>
<br/>
# 接下来就是Nightmare.js
<br/>
	这是个很有意思的工具，能模拟人类操作对网页的操作，并设置期待来判断是否成功，我的理解就是个能替代人力来检验产品的工具，具体操作还有待探究（附上管网图，大爱）
	![Nightmare.js官网截图](http://i2.muimg.com/588926/eca4cd6abaf11913.png)