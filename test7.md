### 1.class 和 id 的使用场景?

id 定义到页面唯一的一个元素，class 定义到页面的一类元素，一个id只能定义一个元素。
class 是一个样式先定义好，然后可以套给多个结构/内容，便于复用。
id 是一个标签，用于区分不同的结构和内容，先找到结构/样式，再给它定义样式。
id 选择器的权重要高于 class。

### 2.CSS选择器常见的有几种?

1. **基础选择器**：全局选择器，id 选择器，类选择器，标签选择器等。
2. **组合选择器**：
`E,F`:多元素选择器，给多个元素赋予同样的样式。
`E F`:后代选择器，匹配 E 元素所有子元素 F。（包括其子元素的子元素）
`E>F`:子元素选择器，匹配 E 元素所有的直接子元素 F。
`E+F`:直接相邻选择器，匹配 E 元素之后的相邻的同级元素 F。
`E~F`:普通相邻选择器（弟弟选择器），匹配 E 元素之后的同级元素 F（无论直接相邻与否）
`.class1.class2`: id 和 class 选择器和选择器连写的时候中间没有分隔符，`.` 和 `#` 本身充当分隔符的元素。
3. **属性选择器**：通过匹配某种属性来配置样式的选择器。
4. **伪类选择器**：
匹配某种状态的标签的选择器。
`E:link, E:visited, E:active, E:hover, E:focus`
从标签结构的排列方式进行匹配的选择器。
`E:first-child, E:nth-child(n), E;nth-of-type(n)`等
匹配标签元素状态的选择器。
`E:checked, E:enabled, E:disabled`
5. **伪元素选择器**：
伪元素的效果需要通过添加一个实际的元素才能达到。
`:first-line, :first-letter, :before, :after`

### 3.选择器的优先级是怎样的?对于复杂场景如何计算优先级？

`css样式的简单权重级别由高到低排列：
1. 在属性后面使用`!important`会覆盖页面内任何位置定义的元素样式。
2. 作为style属性写在元素标签上的内联样式
3.id 选择器
4.类选择器
5.伪类选择器
6.属性选择器
7.标签选择器
8.通配符选择器
9.浏览器自定义

**复杂场景**下通过将选择器分为四个级别通过各级别的出现次数决定。
四个级别分别为：行内选择符、ID选择符、类别选择符、元素选择符。
优先级的算法：
- 每个规则对应一个初始"四位数"：0、0、0、0
- 若是 行内选择符，则加1、0、0、0
- 若是 ID选择符，则加0、1、0、0
- 若是 类选择符/属性选择符/伪类选择符，则分别加0、0、1、0
- 若是 元素选择符/伪元素选择符，则分别加0、0、0、1

算法：将每条规则中，选择符对应的数相加后得到的“四位数”，从左到右进行比较，大的优先级更高。

优先级相同时，采用就近原则，即最后出现的样式。

### 4.a:link, a:hover, a:active, a:visited 的顺序是怎样的？ 为什么？

正确顺序：`a:link, a:visited, a:hover, a:active`
`<a>`标签的样式是由下至上逐级进行条件验证的，所以最具一般性的条件要放在最上面，当标签处于多种状

态并存的情况下，要将希望表现的样式放在最下面。
- 当一个`<a>`标签处于未被点击过状态时，只具有`link`状态的样式，所以将`a:link`放在最上面。
- 当光标经过`<a>`标签上时，具有`link, hover`或` visited，hover`状态的样式，所以`a:hover`要放在

`a:visited`和`link`的后面。
- 当`<a>`标签被光标点击的时候，具有`visited, hover, active`的状态样式，所以`a:active`放在`a:hover`后面。

### 5.以下选择器分别是什么意思?
```
#header{
}/* 匹配id为header的元素 */
.header{
}/* 匹配所有class为header的元素 */
.header .logo{
}/* 匹配class为header的元素下的子元素及其所有后代元素中，class为logo的元素 */
.header.mobile{
}/* 匹配class为header和mobile的元素 */
.header p, .header h3{
}/* 匹配class为header的元素下的 p 标签和class为header的元素下的 h3 标签 */
#header .nav>li{
}/* 匹配id为header的元素和class为nav的元素下的直接子元素 li 标签 */
#header a:hover{
}/* 匹配id为header的元素下的所有值为 a:hover 的伪类选择器的元素 */
#header .logo~p{
}/* 匹配id为header的元素下的class为logo的元素后的所有同级 p 标签 */
#header input[type="text"]{
}/* 匹配id为header的元素之下的所有type属性为 text 的input标签 */
```
### 6.列出你知道的伪类选择器

>伪类选择器
E:link 匹配所有未被点击的链接
E:visited 匹配所有已被点击的链接
E:active 匹配已经被鼠标点击还没释放的E元素
E:hover 匹配鼠标悬停其上的E元素
E:focus 匹配获得当前焦点的E元素
E:lang(c) 匹配 lang 属性等于 c 的E元素
E:enabled 匹配表单中的可用元素
E:disabled 匹配表单中禁用的元素
E:checked 匹配表单中被选中的radio或checkbox元素
E::selection 匹配用户当前选中的元素
E:root 匹配文档的根元素，对于html文档，就是html元素
E:nth-child(n) 匹配其父元素的第n个子元素，第一个编号为1
E:nth-last-child(n)  匹配其父元素的倒数第n个子元素，第一个编号为1
E:nth-of-type(n) 与nth-child(n)类似但只匹配使用同种标签的元素
E:nth-last-of-type(n) 与nth-last-child(n)类似但只匹配使用同种标签的元素
E:first-child 匹配作为长子的元素E
E:last-child 匹配父元素的最后一个子元素，等同于:nth-last-child(1)
E:first-of-type 匹配父元素下使用同种标签的第一个子元素，等同于:nth-of-type(1)
E:last-of-type 匹配父元素下使用同种标签的最后一个元素，等同于:nth-last-of-type(1)

注意：`E:nth-child(n)`中的（）里的字母，只能使用字母 n 。

### 7. `div:first-child`、`div:first-of-type`、`div :first-child` 和 `div :first-of-type` 的作用和区别 （注意空格的作用）

`div:first-child` 选择div父元素下的第一个div子元素
`div :first-child` 选择div元素下的第一个子元素
`div:first-of-type` 选择div父元素下首个div子元素
`div :first-of-type` 选择div元素下所有的同类型的第一个元素

### 8.运行如下代码，解析下输出样式的原因。
```
<style>
.item1:first-child{
  color: red;
}
.item1:first-of-type{
  background: blue;
}
</style>
    <div class="ct">
      <p class="item1">aa</p>
      <h3 class="item1">bb</h3>
      <h3 class="item1">ccc</h3>
    </div>
```

<img src="/uploads/default/original/2X/2/280d97034743e0ac0018a5bbd27d178cd91ac964.png" width="645" height="119">

`.item1:first-child {color: red;}`：class为 item1 的元素的父元素下的第一个元素的颜色为红色，即 `aa` 显示为红色。
`.item1:first-of-type {background: blue;}`：class为 item2 的元素的父元素下所有拥有同标签的第一个子元素的背景颜色为蓝色，所以`<p>`和第一个`<h3>`元素的背景色变成了蓝色。
