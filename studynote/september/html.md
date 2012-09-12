# HTML基础 #

##HTML概述

**什么是HTML？**

超文本标记语言（ HyperText Mark-up Language）

- 标签（element）
- 属性（attribute,property）
- 数据类型（data type）

**HTML的发展史**

- HTML 1.0
	- 在1993年6月作为互联网工程工作小组 (IETF)工作草案发布（并非标准）
- HTML 2.0
	- 1995年11月作为RFC 1866发布，在RFC 2854于2000年6月发布之后被宣布已经过时
- HTML 3.2
	- 1996年1月14日，W3C推荐标准
- HTML 4.0
	- 1999年12月24日，W3C推荐标准
- **HTML 4.01**
	- 1999年12月24日，W3C推荐标准.ISO/IEC 15445:2000（“ISO HTML”）——2000年5月15日发布，基于严格的HTML 4.01语法，是国际标准化组织和国际电工委员会的标准
- XHTML 1.0
	- 发布于2000年1月26日，是W3C推荐标准，后来经过修订于2002年8月1日重新发布。
- XHTML 1.1
	- 于2001年5月31日发布
- HTML 5.0
	- 201*,W3C工作草案

**Doctype与浏览器模式**

	页面文档类型统一使用html5声明类型：
>` <!DOCTYPE HTML>`

## HTML语义化

什么是HTML语义化？

语义化就是使用带有语义的标签。

语义化的目的：

- 使得页面结构清晰，网页标准化
- 结构好，有利于搜索引擎优化
- 可读性高，更利于开发人员的维护
- 有利于一些终端设备的读取（手机、盲人设备等）

HTML的核心结构：
	
	<!doctype html>
	<html>
		<head></head>
		<body></body>
	</html>
## HTML的常用标签

1、表格标签：

- `<table>` 表格
- `<caption>` 表格的标题
-` <thead>` 表格页面
- `<tbody>`表格主体
- `<tfoot>`表格页脚
- `<tr>`表格的行
- `<td>`表格的列
- `<th>`表格的表头

例如：

	<table border="1">
	  <thead>
	    <tr>
	      <th>年</th>
	      <th>月</th>
	    </tr>
	  </thead>
	  <tbody>
	    <tr>
	      <td>2012</td>
	      <td>12</td>
	    </tr>
	    <tr>
	      <td>2012</td>
	      <td>1</td>
	    </tr>
	  </tbody>
	  <tfoot>
	    <tr>
	      <td>2012</td>
	      <td>3</td>
	    </tr>
	  </tfoot>
	</table>

结果：
<table border="1">
	  <thead>
	    <tr>
	      <th>年</th>
	      <th>月</th>
	    </tr>
	  </thead>
	  <tbody>
	    <tr>
	      <td>2012</td>
	      <td>12</td>
	    </tr>
	    <tr>
	      <td>2012</td>
	      <td>1</td>
	    </tr>
	  </tbody>
	  <tfoot>
	    <tr>
	      <td>2012</td>
	      <td>3</td>
	    </tr>
	  </tfoot>
	</table>


2、列表元素

- `<ol>`	有序列表。
- `<ul>`	无序列表。
- `<li>`	列表项。
- `<dl>`	定义列表。
- `<dt>`	定义项目。
- `<dd>`	定义的描述。

3、标题 段落

- `h1~h6`标题
- `hr` 分隔符
- `p` 段落
- `</br>` 换行





## HTML代码规范 ##
## 1、基本规范 ##
- 使用符合语义的标签编写html文档。
- 元素的标签名和属性名必须小写，属性值必须加双引号。例如：
>  `<input type="submit"/>`
- 正确区分自闭合标签和非自闭合标签。非法闭合会导致页面嵌套错误问题。
- 通过给元素设置自定义属性来存放于javascript交互的数据，自定义的属性名命名规范：rel,data-xx.例如:data-lazyload-url 。
避免使用”data:“等其他的命名方法。

- 块级元素能嵌套所有内联元素，行内元素不能嵌套块级元素

## 2、文档声明DOCTYPE ##
	页面文档类型统一使用html5声明类型：
>` <!DOCTYPE HTML>`

## 3、编码 ##
	页面统一使用GBK编码，声明方法遵循HTML5规范，代码如下：
>` <meta charset="gbk"/>`

## 4、注释 ##
	html单行注释：
> `<!--  单行注释  --> `

	html多行注释：
> `<!--注释{{--`
> 
> 		`html注释区块`
> 
> `<!--  注释}}-->`

## 5、页面模版

	<!DOCTYPE HTML>
	<html lang="zh">
		<head>
			<meta charset="gbk"/>
			<title>标题</title>
			<meta content="IE=EmulateIE7" http-equiv="X-UA-Compatible">
			<meta content="说明文字" name="description">
			<link type="image/x-icon" href="http://img04.taobaocdn.com/favicon.ico" rel="shortcut icon">
			<!-- 样式，单独方便维护-->
	        <link rel="stylesheet" type="text/css" href="../reset.css">
			<!-- 脚本 -->
	        <script src="../main.js" type="text/javascript"></script>
			<!--[if lte IE 8]>
			<script src="http://a.tbcdn.cn/apps/lottery/public/js/html5.js"></script>
			<![endif]-->
		</head>
		<body>	
	        <section id="c-wrapper"<!—主体--</section>
			<section id="c-footmenu"<!—底部菜单--</section>
			<section id="c-partners"<!—合作伙伴--</section>
			<footer id="c-footer"<!—页脚--</footer>
			<script>
			//你的js代码 	
			</script>
		</body>
	</html>

##6、相关链接

<http://www.w3school.com.cn/>