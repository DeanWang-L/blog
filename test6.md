### CSS的全称是什么?

Cascading Style Sheets，层叠样式表

### CSS有几种引入方式?`link`和`@import`有什么区别?

**内联样式**：直接在 HTML 标签 style 属性中添加 CSS ，只能改变当前样式，会增加代码的长度和维护成本，不推荐使用。
`<h1 style = "样式" >`
**内部样式**：包含于`<style>`标签中的css代码。
`<style>样式</style>`
**外部样式**：从 HTML 外部链接样式。
`link`：html的一个标签
`<link rel="stylesheet" type="text/css" href="style.css">`
`@import`：css的一个语法
```
@import url"style.css";
@import "style.css";
```
- `link`属于html，通过 `href` 属性来引入外部文件，可以放置于`<body>`标签中的任何位置（一般放在`<head>`中）；而`@import`属于css，需要写在样式表的开头，否则无法正确导入外部文件。
- `@import`是 css2.1 才有的概念，如果浏览器版本较低，将无法正确导入外部文件。
- 当html被加载后，`link`引用的文建会同时被加载，而 `@import` 则会等页面全部下载完毕再加载。
- 如果要引用多个 css 文件，可以使用 `link` 引用一个“目录” css 文件，再在这个 css 文件中使用
 `@import` 引入其他 css 文件。

 ### 以下这几种文件路径分别用在什么地方，代表什么意思?

 **相对路径**：相对与当前文件夹位置的路径
 `css/a.css`：当前文件夹中的css文件夹中的a.css文件
 `./css/a.css`：同上，`./`：当前文件夹
 `b.css`：当前文件夹中的 b.css 文件
 `../imgs/a.png`：上一文件夹中的 imgs 文件夹中的 a.png 文件，`../`：上一文件夹
 **绝对路径**：本地文件的绝对地址
 `/Users/hunger/project/css/a.css`：a.css 文件在本地的真实地址，只能在本地使用无法在服务器使用。
 **网站路径**：
 `/static/css/a.css：static`文件夹中css文件夹下的a.css文件。
 `http://cdn.jirengu.com/kejian1/8-1.png`：网络图片地址。

 ### 如果我想在js.jirengu.com上展示一个图片，需要怎么操作?

 将本地的图片上传到网络，生成一个网址进行引用。
 或者建立一个本地服务器，将图片上传到服务器后通过相对路径进行引用。

 ### 列出5条以上html和 css 的书写规范
 - 语法不分大小写，统一使用小写。
 - 不实用内联的 style 属性定义样式。
 - id 和 class 使用有意义的单词，分隔符建议使用`-`。
 - 尽量使用缩写。
 - 属性的值为0时省略单位。
 - 块的内容缩进。
 - 属性名的冒号后面加一个空格。

 ### 截图介绍 chrome 开发者工具的功能区
 - **Element**：元素面板，查找网页源代码 HTML 中的任一元素,手动修改任一元素的属性和样式且能实时在浏览器里面得到反馈。
 - **Console**： JS 控制台，记录开发者开发过程中的日志，可以作为与 JS 进行交互的命令行 Shell。
 - **Sources**：断点调试 JS。
 - **Network**：从发起网页页面请求Request后分析 HTTP 请求后得到的各个请求资源信息，可以根据这个进行网络性能优化。
 - **Performance**：在 Performance 面板可以查看页面加载过程中的详细信息，比如在什么时间开始做什么事情，耗时多久等等。
 - **Memory**：主要显示页面 JS 对象和相关联的 DOM 节点的内存分布情况。
 - **Application**：记录网站加载的所有资源信息，包括存储数据、缓存数据、字体、图片、脚本、样式表等。
 - **Security**：判断当前页面是否安全。
 - **Audits**：审计面板，对当前网页进行网络利用情况、网页性能方面的诊断，并给出优化建议。




