# CSS基础 #
## 一、CSS概述 ##
**1、CSS（Cascading Style Sheet）层叠样式表**

CSS设计的目的是让设计师指定文档元素中的字体、颜色、外边距、缩进、边框等属性来描述整个页面的布局设计，与HTML所负责的结构分开。

**2、CSS的发展史**

- CSS1在1996年12月成为标准（它定义了具体的颜色、字体、外边距、边距和其他的基本样式）
- CSS2在1998年5月被采纳成为推荐标准（在CSS1的基础上添加了一些高级特性，例如：绝对定位、浮动、选择器） 
- CSS2.1在2002年修订（现在的浏览器基本上都支持，但是低于IE8的还有一些遗漏问题）
- CSS3 目前还未正式发布
CSS3规范和工作草案：[http://www.w3.org/Style/CSS/current-work](httphttp://www.w3.org/Style/CSS/current-work:// "CSS3规范和工作草案")

**3、CSS的层叠概念**

层叠说明文档中的任何给定元素的样式是由各个**“来源”**的**“层叠“**效果：

- 浏览器默认样式

- 文档样式（作用于整个页面的样式：link的外联样式表 & 写在`<style>`中的样式）

- 每个独立的HTML元素的样式属性（`style=""`定义的内联样式）

## 二、CSS语法 ##
CSS的3个组成部分：

- 选择器  selector
- 属性    property
- 属性值  value

**基本结构**

`selector { property: value}`

只有一个属性对。 

> `color: #cccccc /*文本颜色设置*/`

多个属性对，使用分号隔开。

> `font-size:14px; /*字体大小14像数*/`

> `font-weight:bold;/*字体加粗*/`

**样式表中的注释**

为了后期文件的维护和交接工作方便，文件注释是必不可少的。

常见的注释有两种：

第一种，写在文件开头：
> /* --------------------------------------

>  `* @fileOverview文件描述 ` 

> ` * @author作者 `

>  `* 功能描述`

>  `* @version 版本号`

>  `*` ---------------------------------------

>  */

第二种，注释文本
> `/* 注释文本 */`

## 三、CSS和HTML的关联方式 ##

- 行内样式（内联样式）

> `<p  style="color:red">本段落的文字设置为红色</p>`

	只在行内生效

- 外部样式

> `<link rel="stylesheet" href="../../main.css">`

	样式在引入该文件的文档中生效，因为没有和内容相互分离，不建议使用

- 内部样式

>` <!doctype HTML>`

> `<html>`

> 	`<head>`

> 		<meta charset="gbk"/>

> 		<title>例子</title>

> 		<style type="text/css">

> 		.red { color:red ;}

> 		</style>

> 	</head>

> 	<body>

> 		<p class="red">本段落的文本颜色为红色</p>

> 	</body>

> `</html>`

	写在<style></style>标签里而后放在<head></head>中，在该文档中生效

- 导入样式

	@import url("/css/global.css");

**优先级：**
行内样式表 > 内部样式表 > 外部样式表

## 四、选择器  Selector	 ##
- 标签名选择器    h1
- 群组选择器	   h1,h2
- 类选择器  .classname
- id选择器  #id
- 通配符选择器 *
- 后代选择器 div p
- 伪类选择器 :hover
- CSS 属性选择器  input[type=“button”] ie6

其中三种基本选择器类型：

- 标签名选择器，如：p{}，即直接使用HTML标签作为选择器
- 类选择器，如 .container{}
- ID选择器，如 #container{}

扩展的选择器：

- 后代选择器

> `.container p a{ color: #808080;}`

- 群组选择器

> `section,article,aside,header,footer,nav,dialog,figure {display:block; padding:0; margin:0;}`

【注意点】：类选择器和ID选择器的一个重要区别：一个页面中相同的class可以多次使用，但是id只可以使用一次。再就是定义的id选择器经常是留给js使用的。

**选择器的优先级**

通常我们用1表示标签名选择器的优先级，用10表示类选择器的优先级，用100标示ID选择器的优先级。
> `div.test1 .span  优先级 1+10 +10` 

> `span#xxx .songs li 优先级1+100 + 10 + 1 `

> `#xxx li 优先级 100 +1 `

特别：标签内引入CSS的方式来写CSS：

> `<div style="color:red">文本颜色红色</div>` 

这种的优先级是最高的。我们给它的优先级是1000，这种写法不推荐使用

## 五、重要的CSS样式属性 ##
### position ###
CSS使用position属性来指定元素的定位类型：

- static 默认值
- relative 相对定位
- absolute 绝对定位
- fixed    可视区域定位/屏幕定位

**static**：指定元素按照常规的文档内容流（常规流）进行定位,也就是元素按从左往右、从上到下进行布局

**relative**：相对定位，元素按照常规的文档流进行布局，系统保留着元素在文档流中的空间

**absolute**：绝对定位，容器是相对于包裹它的容器来定位的，绝对定位的元素是独立的，脱离文档内容流的，一般来说，要么是相对于最近的定位（relative、absolute）祖先元素，要么是相对于文档本身。

**fixed**：元素相对于浏览器窗口进行定位，元素固定在那里，不会随着文档的的滚动而滚动。大多数浏览器都支持，但是IE6不支持

###left、top、right和bottom###

- left：元素的左边缘到容器左边缘的距离
- top：元素的上边缘到容器上边缘的距离
- right： 元素的右边缘到容器右边缘的距离
- bottom：元素的下边缘到容器下边缘的距离

例如：放置一个距离文档左、上边缘各100像素的元素：

> `<div style="position: absolute; left: 100px; top: 100px;">`

例如：让一个元素的右下角定位在文档的右下角（没有父元素是定位元素）

> `<div style="position: absolute; right: 0px; bottom: 0px;">`

例如：定位一个元素让其右、上边缘相对于窗口右、上边缘各10像素，并且不随文档的滚动而滚动

> `<div style="position: fixed; right: 10px; top: 10px;">`

position除了static外的定位，都可以和eft、top、right和bottom属性一起使用。

### float(浮动) ###

float：相对于常规流来讲，它漂浮在常规流的上方

特性值：
 
- none
- left  向左浮动
- right 向右浮动

### width 、height ###

width：设置块状元素的宽度

height：设置块状元素的宽度



### z-index ###

指定元素相对于其他重叠元素的“堆叠次序”，定义了元素定位的第三个维度

- 默认值为0
- z-index可以为正值：定位元素显示在常规文档流的上面
- z-index可以为负值：定位元素显示在常规文档流的下面

如果z-index的值一样的多个元素重叠在一起的话，会按照他们在文档中出现的顺序绘制，也即最后一个重叠元素显示在最上面。如果z-index的值不一样的话，它们会按照z-index从低到高的顺序绘制的，一就是z-index越大的越在上层。

【注意】：

- 这种堆叠的效果，只有设置z-index的元素是在同一个容器是才生效。当他们处于不同容器中的时候，你必须为他们各自的容器设置z-index才能达到效果。
- 此属性仅仅作用于 position 属性值为 relative 或 absolute 的元素


## 六、CSS Hack技术 ##

- CSS Hack的基本原理
- 常用的CSS Hack
- CSS Hack的使用原则

> #abc{

> border:2px solid #00f;   /* ff的属性 */ 

> border:2px solid #090\9; /* 所有（ie6+）都支持 */ 

> border:2px solid #F90\0; /* IE8 、IE9*/ 

> border:2px solid #090\9\0;/* IE9 */

> *border:2px solid #F90; /* IE6 IE7*/

> _border:2px solid #f00; /* IE6 */

> }

## 七、CSS Sprites ##

- 什么是CSS Sprites 

	CSS Sprites就是合并你的背景图片，然后通过background-image和background-position来显示背景图片；

- CSS Sprites的优缺点

	* 优点

		- 减少HTTP请求,降低服务器负担
		- 文件体积更小  1+1 < 2

	* 缺点
		- 开发/维护成本高
		- 扩展性差

   * 如何解决维护成本高的问题:
		- 按模块 or 组件合成图片
		- 按布局样式合成图片

- 图片

	使用CSS Sprites 优化图片

	使用工具：Photoshop

	图片格式：GIF JPG PNG

	图片规范：		
		
	 - 所有页面元素类图片都放在images文件夹中
	 - 图片格式仅限于 gif | png | jpg；在保证视觉效果的情况下选择最小的图片合适和图片质量，以减少加载时间
	 - 尽量避免使用半透明的PNG图片(有锯齿、png-24 IE6不支持)
	 - 运用CSS Sprite技术集中背景图和小图标



## 八、CSS代码规范 ##

- 名称一律小写，多个单词用连字符（-）连接。名称中只能出现英文字母，数字，连字符。例如：main-nav
- 名称尽量使用英文单词命名。找不到，在考虑适用中文拼音。对于中国以及淘宝特色词汇，可以使用拼音。例如：wangwang（旺旺） daigou（代沟） xiaobao。除了产品名称和特色词汇，严禁使用拼音。
- 在不影响语义的情况下，id和class中可以适当的适用英文单词缩写。例如col、hd。切务自造缩写。
- id和class名称中的第一个词必须是单词全拼或语义非常清晰的单词缩写，比如present, col（栏目）。
- 能以背景形式呈现的图片，尽量写入到CSS样式中
- 公用CSS文件reset.css、global.css，每个页面必须都要引入。且不可以随意修改里面的代码。
- class和id的使用：id是唯一的，class是可以重复的，所以在大的的模块中使用id，重复使用频率高的使用class。
- 在JavaScript中当作（钩子）hook用的id和class, 命名规则为J-UpperCamelCase（请注意，J-后的首字母也大写！）, 其中字母J代表JavaScript, 也是钩子（hook）的象形。命名规范：J-产品代号-命名。注意：如果在JavaScript和CSS中都需要用到，则不用遵守本约定。
- 为了避免和全部样式和淘宝现有产品产生混淆以及冲突，class命名规范：c-产品代号-模块名（c来源于cubee的首字母）
- 必须为大区块样式添加注释，小区块适量注释。
- 建议CSS属性的编写顺序：布局定位→自身→文本→其他：
	- 布局定位属性：margin\padding\float\position(right,left,top,bottom)\overflow……
	- 自身属性：width\height\border\background……
	- 文本属性：font\text-align\color……
	- 其他属性：zoom\cursor……



相关链接：

- [http://www.w3help.org/zh-cn/](http://www.w3help.org/zh-cn/ "W3Chelp")















