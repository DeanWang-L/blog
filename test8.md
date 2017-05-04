## 问答
### 1.块级元素和行内元素分别有哪些？动手测试并列出4条以上的特性区别
**块级元素（block-level）**：
```
<div>, <h1-6>, <p>, <hr>, <form>
<ul>, <dl>, <ol>, <pre>, <table>
<li>, <dd>, <dt>, <tr>, <td>, <th>
```
**行级元素**（inline-level）：

```
<em>, <strong>, <span>, <a>, <br>, <img>
<button>, <input>, <label>, <select>
<textarea>, <code>, <script>
```

**区别**：

1. 块级可以包含块级和行内，行内只能包含文本和行内。
2. 块级占据一整行空间，行内占据自身宽度空间。
3. 宽高设置:只对块级元素有效，对行内元素无效。
4. 内外边距的差异：块级元素可以设置上下左右内外边距，行内元素只能设置左右内外边距。

### 2.什么是 CSS 继承? 哪些属性能继承，哪些不能？

**css继承**：父元素设置的一些css样式会继承到其子元素及其后代上。
**能继承的元素**：
所有元素可继承：visibility、cursor
内联元素可继承：letter-spacing、word-spacing、white-space、line-height、color、font、 font-family、font-size、font-style、font-variant、font-weight、text- decoration、text-transform、direction
块状元素可继承：text-indent和text-align。
列表元素可继承：list-style、list-style-type、list-style-position、list-style-image
表格元素可继承：border-collapse

**不能继承的元素**：

```
display、margin、border、padding、background、height、min-height、max- height、width、min-width、max-width、overflow、position、left、right、top、 bottom、z-index、float、clear、table-layout、vertical-align、page-break-after、 page-bread-before、unicode-bidi
```

### 3.如何让块级元素水平居中？如何让行内元素水平居中?

**块级元素**`margin: 0, auto;`块级元素可以通过设置外边距属性居中
**行内元素**`text-align: center;`通过属性设置居中

### 4.用 CSS 实现一个三角形

创建一个`<div class = box>`的标签，使用如下样式：
```
.box{
width: 0;
height: 0;
border-top: 30px solid transparent;
border-right: 30px solid transparent;
border-bottom: 30px solid red;
border-left: 30px solid red;
}
```

### 5.单行文本溢出加 ...如何实现?

```
.card > h3{
white-space: nowrap; /*禁止换行*/
overflow: hidden; /*隐藏超出来的部分*/
text-overflow: ellipsis; /*将超出的部分用省略号代替*/
}
```

### 6.px, em, rem 有什么区别

px是像素单位，设置的是元素的固定尺寸。
em是是倍率，设置的是相对与父元素的尺寸大小。
rem也是倍率，设置的是相对于根元素的尺寸大小。

### 7.解释下面代码的作用?为什么要加引号? 字体里\5b8b\4f53代表什么?
```
body{
  font: 12px/1.5 tahoma,arial,'Hiragino Sans GB','\5b8b\4f53',sans-serif;
  }
```
设置`<body>`标签的字体属性，大小12px，行间距1.5，按照`tahoma,arial,'Hiragino Sans GB','\5b8b\4f53',sans-serif`的顺序依次测试能否加载字体到浏览器。
加引号的原因是 “`Hiragino Sans GB`” 中有空格如果不加引号浏览器会将其视为三种字体。
`\5b8b\4f53`：是“宋体”这两个字的unicode码，防止用户电脑不识别汉字名的字体。

## 代码
1-5

