---
title: JS做VersionCompare
date: 2017-03-15 11:28:32
tags: JS
---
<h3>　　陆陆续续投了许多前端简历，姿态低下有些愧对这些年学的英语=_=，有几个邀请面试也是胆战心惊，北京水深，防备万般都难免要被坑个几回合，唉，来京慎重啊。话说这日来了个消息让我用JS弄个VersionCompare出来，用以外部程序比较版本。一时间云里雾里，特地搜索名词，有个PHP关键字的结果传入三个参数，可以返回三个结果，那好吧，就用JS还原吧...</h3>
<p>下面上代码</p>
<!--more-->
***
```bash
  <script language="javascript">
  function cmpVersions (a, b) {
 //数点测试
    var part1 = a, part2 = b;
	var regpoint = new RegExp("[\.]");
	if (regpoint.test(a) && regpoint.test(b))
	{
		hasPoint = true;
	}
	else if(regpoint.test(a) || regpoint.test(b))
	{
		alert("请确认是否为同一产品，否则这TM太刁钻任性了");
	}
	else
	{
		hasPoint = false;
	}
//版本字符测试
	var regChar = new RegExp("[A-Za-z]");
	if (regChar.test(a) || regChar.test(b))
	{
		hasChar = true;
	}
	else
	{
		hasChar = false;
	}
//转化传参
	if (hasPoint)
	{
		part1 = part1.split(".").join("");
		part2 = part2.split(".").join("");
		if (hasChar)
		{
			part1.charAt(part1.length).charCodeAt();
			part2.charAt(part2.length).charCodeAt();
		}
		part1 = part1.split("");
		part2 = part2.split("");
	}
	else
	{
		if (hasChar)
		{
			part1.charAt(part1.length).charCodeAt();
			part2.charAt(part2.length).charCodeAt();
		}
		part1 = part1.split("");
		part2 = part2.split("");
	}
//同位比较
	for (var i = 0; i < part1.length ;  ++i)
	{
		if (part2.length == i)
		{
			return 1; //a > b
		}
		if (part1[i] == part2[i])
		{
			continue; //进行下一位运算
		}
		if (part1[i] > part2[i])
		{
			return 1; //a > b
		}
		else
		{
			return -1; //a < b
		}
	}
	if (part1.length != part2.length)
	{
		return -1 // a<b
	}
	else{
		return 0;
	}
   }
	var result = cmpVersions("1.1.1","1.1.1");
	var result2 = cmpVersions("1.1.1a","1.1.1");
	var result3 = cmpVersions("1.1.1a","1.1.1b");
	var result4 = cmpVersions("1111","1110");
	var result5 = cmpVersions("111","111");
	document.write(result,result2,result3,result4,result5);
  </script>
```