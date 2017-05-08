### 1.text-align: center的作用是什么，作用在什么元素上？能让什么元素水平居中

使块级元素中的文本居中，作用于块级元素中的内容，可以让元素中的文本和块级元素中的行内元素或display为inline-block的元素居中。

### 2.IE 盒模型和W3C盒模型有什么区别?

W3C标准中`padding`、`border`所占的空间不在width，height范围内，IE的盒模型width包括content尺寸 + padding + border

### 3.`*{ box-sizing: border-box;}`的作用是什么？

将当前页面盒模型类型改为“IE盒模型”

### 4.`line-height: 2`和`line-height: 200%`有什么区别?

`line-height: 2`是其本身文字高度的两倍
`line-height: 200%`使其父元素文字高度的两倍

### 5.inline-block有什么特性？如何去除缝隙？高度不一样的inline-block元素如何顶端对齐?

**特性：**
- 既呈现inline特性（不占据一整行，宽度由内容宽度决定）
- 又呈现block特性（可设置宽高，内外边距）
**去除缝隙的方法：**
- 删掉元素间的空白字符
- 将空白字符的font-size设为0
**inline-block顶端对齐：**
- 可以通过设置vertical-align属性来调节inline-block元素的对齐方式(top/bottom/middle)。

### 6.CSS sprite 是什么?

- 指将不同的图片/图标合并在一张图上。
- 只显示图片的一部分来显示图标，但鼠标点击时，平移背景图片，表现出变色或图标改变的效果。
- 使用CSS Sprite 可以减少网络请求，提高网页加载性能。

### 7.让一个元素"看不见"有几种方式？有什么区别?

- `opacity: 0;`将不透明度设为0，作用于整体
- `visibility: hidden;`隐藏元素和`opacity: 0`;类似
- `display: none;`使元素消失，不占位置
- `background-color: rgba(0,0,0,0.2)`只针对背景色
