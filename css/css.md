# 9 、 CSS 技术 文档 :CSS 2. 0 .chm

# 9. 1 、 CSS 技术介绍

CSS是「层叠样式表单」。是用于(增强)控制网页样式并允许将样式信息与网页内容分离的一种标记性语言。

# 9. 2 、 CSS 语法规则：

![image-20210610113615450](https://gitee.com/zouyu0310/images/raw/master/img/20210617104046.png)

选择器：浏览器根据“选择器”决定受CSS样式影响的HTML元素（标签）。

属性 (property) 是你要改变的样式名，并且每个属性都有一个值。属性和值被冒号分开，并

由花括号包围，这样就组成了一个完整的样式声明（declaration），例如：p{color:blue}

多个声明：如果要定义不止一个声明，则需要用分号将每个声明分开。虽然最后一条声明的

最后可以不加分号(但尽量在每条声明的末尾都加上分号)

例如：

```html
p{

color:red;

font-size: 30 px;

}
```

注：一般每行只描述一个属性

CSS注释：/*注释内容*/



# 9. 3 、 CSS 和 HTML 的结合方式

## 9. 3. 1 、第一种：

在标签的style属性上设置”key:valuevalue;”，修改标签样式。

需求 1 ：分别定义两个 div 、 span 标签，分别修改每个 div 标签的样式为：边框 1 个像素，实线，红色。

```html
<div>div 标签 1</div>
<div>div 标签 2</div>
<span>span 标签 1</span>
<span>span 标签 2</span
```



```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Title</title>
</head>
<body>
<!--需求 1：分别定义两个 div、span 标签，分别修改每个 div 标签的样式为：边框 1 个像素，实线，红色。-->
<div style="border: 1px solid red;">div 标签 1</div>
<div style="border: 1px solid red;">div 标签 2</div>
<span style="border: 1px solid red;">span 标签 1</span>
<span style="border: 1px solid red;">span 标签 2</span>
</body>
</html>
```

问题：这种方式的缺点？

1 .如果标签多了。样式多了。代码量非常庞大。

2 .可读性非常差。

3 .Css代码没什么复用性可方言。


## 9. 3. 2 、第二种：

在head标签中，使用style标签来定义各种自己需要的css样式。

格式如下：

```css
xxx {

Key : value value;

}
```



需求 1 ：分别定义两个 div 、 span 标签，分别修改每个 div 标签的样式为：边框 1 个像素，实线，红色。

```html
<div>div 标签 1</div>
<div>div 标签 2</div>
<span>span 标签 1</span>
<span>span 标签 2</span
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Title</title>
<!--style 标签专门用来定义 css 样式代码-->
<style type="text/css">
/* 需求 1：分别定义两个 div、span 标签，分别修改每个 div 标签的样式为：边框 1 个像素，实线，红色。*/
div{
border: 1px solid red;
}
span{
border: 1px solid red;
}
</style>
</head>
<body>
<div>div 标签 1</div>
<div>div 标签 2</div>
<span>span 标签 1</span>
<span>span 标签 2</span>
</body>
</html>
```

![image-20210610165428314](https://gitee.com/zouyu0310/images/raw/master/img/20210617104154.png)





Css 注释 /* 这是css 的代码注释 */

问题：这种方式的缺点。

1 .只能在同一页面内复用代码，不能在多个页面中复用css代码。

2 .维护起来不方便，实际的项目中会有成千上万的页面，要到每个页面中去修改。工作量太大了。

## 9. 3. 3 、第三种：

把css样式写成一个单独的css文件，再通过link标签引入即可复用。

使用html 的 <linkrel= "stylesheet" type= "text/css" href= "./styles.css"/ > 标签 导入 css 样

式文件。

1 、css文件内容：

```
div{
border: 1 px solidyellow;
}
span{
border: 1 px solid red;
}
```

html文件代码：

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Title</title>
<!--link 标签专门用来引入 css 样式代码-->
<link rel="stylesheet" type="text/css" href="1.css"/>
</head>
<body>
<div>div 标签 1</div>
<div>div 标签 2</div>
<span>span 标签 1</span>
<span>span 标签 2</span>
</body>
</html>
```




# 9. 4 、 CSS 选择器

## 9. 4. 1 、标签名选择器

标签名选择器的格式是：
```css
标签名{

属性：值;

}
```
标签名选择器，可以决定哪些标签被动的使用这个样式。
```
<div>div标签 1 </div>

<div>div标签 2 </div>

<span>span标签 1 </span>

<span>span标签 2 </span>
```
需求 1 ：在所有div标签上修改字体颜色为蓝色，字体大小 30 个像素。边框为 1 像素黄色实线。

并且修改所有span 标签的字体颜色为黄色，字体大小 20 个像素。边框为 5 像素蓝色虚线。

示例代码：
```html
<!DOCTYPEhtml>
<html>

<head>
<meta charset="UTF- 8 ">
<title>CSS选择器</title>
<style type="text/css">
div{
border: 1 px solid yellow;
color:blue;
font-size: 30 px;
}
span{
border: 5 px dashed blue;
color:yellow;
font-size: 20 px;
}
</style>
</head>

<body>
    <!--
    需求 1 ：在所有div标签上修改字体颜色为蓝色，字体大小 30 个像素。边框为 1 像素黄色实线。并且修改所有span标签的字体颜色为黄色，字体大小 20 个像素。边框为 5 像素蓝色虚线。- ->

<div>div标签 1 </div>
<div>div标签 2 </div>

<span>span标签 1 </span>
<span>span标签 2 </span>
</body>
</html>
```
## 9. 4. 2 、 id 选择器

id 选择器的格式是：

```css
#id 属性值{
属性：值;
}
```


id 选择器，可以让我们通过 id 属性选择性的去使用这个样式

需求 1：分别定义两个 div 标签，
第一个 div 标签定义 id 为 id001 ，然后根据 id 属性定义 css 样式修改字体颜色为蓝色，
字体大小 30 个像素。边框为 1 像素黄色实线。
第二个 div 标签定义 id 为 id002 ，然后根据 id 属性定义 css 样式 修改的字体颜色为红色，字体大小 20 个像
素。边框为 5 像素蓝色点线。

```css
<div id="id001">div 标签 1</div>
<div id="id002">div 标签 2</div
```

示例代码

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>ID 选择器</title>
<style type="text/css">
#id001{
color: blue;
font-size: 30px;
border: 1px yellow solid;}
#id002{
color: red;
font-size: 20px;
border: 5px blue dotted ;
}
</style>
</head>
<body>
<!-- 需求 1：分别定义两个 div 标签，
第一个 div 标签定义 id 为 id001 ，然后根据 id 属性定义 css 样式修改字体颜色为蓝色，
字体大小 30 个像素。边框为 1 像素黄色实线。
第二个 div 标签定义 id 为 id002 ，然后根据 id 属性定义 css 样式 修改的字体颜色为红色，字体大小 20 个像素。
边框为 5 像素蓝色点线。
-->
<div id="id002">div 标签 1</div>
<div id="id001">div 标签 2</div>
</body>
</html>
```

## 9.4.3、class 选择器（类选择器）
class 类型选择器的格式是：

```css
.class 属性值{
属性：值;
}
```


class 类型选择器，可以通过 class 属性有效的选择性地去使用这个样式。



需求 1：修改 class 属性值为 class01 的 span 或 div 标签，字体颜色为蓝色，字体大小 30 个像素。边框为 1 像素黄色实线。
需求 2：修改 class 属性值为 class02 的 div 标签，字体颜色为灰色，字体大小 26 个像素。边框为 1 像素红色实线

```html
<div class="class01">div 标签 class01</div>
<div class="class02">div 标签</div>
<span class="class01">span 标签 class01</span>
<span>span 标签 2</span
```

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>class 类型选择器</title>
<style type="text/css">
.class01{
color: blue;
font-size: 30px;
border: 1px solid yellow;
}
.class02{
color: grey;
font-size: 26px;
border: 1px solid red;
}
</style>
</head>
<body>
<!--需求 1：修改 class 属性值为 class01 的 span 或 div 标签，字体颜色为蓝色，字体大小 30 个像素。边框为 1 像素黄色实线。
需求 2：修改 class 属性值为 class02 的 div 标签，字体颜色为灰色，字体大小 26 个像素。边框为 1 像素红色实线。
-->
<div class="class02">div 标签 class01</div>
<div class="class02">div 标签</div>
<span class="class02">span 标签 class01</span>
<span>span 标签 2</span>
</body>
</html>
```

## 9.4.4、组合选择器

组合选择器的格式是：

```
选择器 1，选择器 2，选择器 n{
属性：值;
}
```

组合选择器可以让多个选择器共用同一个 css 样式代码。

```
<div class="class01">div 标签 class01</div> <br />
<span id="id01">span 标签</span> <br />
<div>div 标签</div> <br />
<div>div 标签 id01</div> <br />
```



需求 1：修改 class="class01" 的 div 标签 和 id="id01" 所有的 span 标签，字体颜色为蓝色，字体大小 20 个像素。 边框为 1 像素黄色实线

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>class 类型选择器</title>
<style type="text/css">
.class01 , #id01{
color: blue;
font-size: 20px;
border: 1px yellow solid;
}
</style>
</head>
<body>
<!-- 需求 1：修改 class="class01" 的 div 标签 和 id="id01" 所有的 span 标签，
字体颜色为蓝色，字体大小 20 个像素。边框为 1 像素黄色实线。
-->
<div id="id01">div 标签 class01</div> <br />
<span >span 标签</span> <br />
<div>div 标签</div> <br />
<div>div 标签 id01</div> <br />
</body>
</html>
```

# 9.5、常用样式：

------

## 1、字体颜色
color：red；
颜色可以写颜色名如：black, blue, red, green 等
颜色也可以写 rgb 值和十六进制表示值：如 rgb(255,0,0)，#00F6DE，如果写十六进制值必
须加#

## 2、宽度
width:19px;
宽度可以写像素值：19px；
也可以写百分比值：20%；

## 3、高度

height:20px;
高度可以写像素值：19px；
也可以写百分比值：20%；

## 4、背景颜色

background-color:#0F2D4C
## 5、字体样式：
color：#FF0000；字体颜色红色
font-size：20px; 字体大小

## 6、红色 1 像素实线边框

border：1px solid red;

## 7、DIV 居中

margin-left: auto;
margin-right: auto;

## 8、文本居中：

text-align: center;

## 9、超连接去下划线
text-decoration: none;
## 10、表格细线
```css
table {
border: 1px solid black; /*设置边框*/
border-collapse: collapse; /*将边框合并*/
}
td,th {
border: 1px solid black; /*设置边框*/
}
```


## 11、列表去除修饰
```css
ul {
list-style: none;
}
```



## 代码

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>06-css 常用样式.html</title>
<style type="text/css">
div{
color: red;
border: 1px yellow solid;
width: 300px;
height: 300px;
background-color: green;
font-size: 30px;
margin-left: auto;
margin-right: auto;
text-align: center;
}
table{
border: 1px red solid;
border-collapse: collapse;
}
td{border: 1px red solid;
}
a{
text-decoration: none;
}
ul{
list-style: none;
}
</style>
</head>
<body>
<ul>
<li>11111111111</li>
<li>11111111111</li>
<li>11111111111</li>
<li>11111111111</li>
<li>11111111111</li>
</ul>
<table>
<tr>
<td>1.1</td>
<td>1.2</td>
</tr>
</table>
<a href="http://www.baidu.com">百度</a>
<div>我是 div 标签</div>
</body>
</html>
```

