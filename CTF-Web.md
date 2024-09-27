# CTF-Web  

*编辑人：coffee	编辑日期：2024年9月19日*  

---

## 一、CTF-Web学习路线

### 注意事项

1. 学习的过程一定要记笔记，web安全技术又多又杂，累积起来的笔记不仅能帮助你在比赛中即使回忆起知识点还能带给你一定的成就感。
2. 任何语言的编程都一定要会调试代码，不然稍微复杂点的漏洞你就会看不明白，所有要从开始就，养成调试的习惯。
3. web安全是看重实践能力的，不要眼高手低，漏洞看懂了不等于会做，有一大堆看懂writeup但给你自己试就打不通的例子。

### 1.1 编程基础（前期）

- **html**：https://www.runoob.com/html/html5-intro.html
- **js**：https://www.runoob.com/js/js-tutorial.html
- **css**：https://www.runoob.com/css/css-tutorial.html
- **php**：https://www.runoob.com/php/php-tutorial.html
- **http**
- **mysql**：https://www.runoob.com/mysql/mysql-tutorial.html
- **python**：https://www.runoob.com/python3/python3-tutorial.html

### 1.2 基础漏洞

- **了解常见概念**：漏洞、OWASP TOP 10、抓包、暴力破解、payload、poc、exp、writeup、github、webshell、0day/1day/nday
- **信息收集**：前段代码泄漏、目录扫描（https://github.com/maurosoria/dirsearch）
- **SQL注入**
- **burpsuite**：https://www.bilibili.com/video/BV1aq4y1X7oE?p=1&Vd_source=fd08cbc395a0b7444beaebfda9515db2
- **文件上传**：https://github.com/c0ny1/upload-labs
- **命令执行**
- **文件包含**
- **XSS**
- **CSRF**
- **SSRF**
- **XXE**
- **反序列化**



## 二、编程基础

### 2.1 HTML

#### HTML简介

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>
 
<h1>我的第一个标题</h1>
 
<p>我的第一个段落。</p>
 
</body>
</html>

```

![02A7DD95-22B4-4FB9-B994-DDB5393F7F03](https://raw.githubusercontent.com/c0ffee-milk/photo/master/02A7DD95-22B4-4FB9-B994-DDB5393F7F03.jpg?token=BHYTHC2LEWQDBLQFP2KQ6NLG5Z4CU)

- **<!DOCTYPE html>** 声明为 HTML5 文档
- **<html>** 元素是 HTML 页面的根元素
- **<head>** 元素包含了文档的元（meta）数据，如 **<meta charset="utf-8">** 定义网页编码格式为 utf-8
- **<title>** 元素描述了文档的标题
- **<body>** 元素包含了可见的页面内容
- **<h1>** 元素定义一个大标题
- **<p>** 元素定义一个段落

**什么是HTML ？**

HTML是用来描述网页的一种语言。

**HTML 标签**

HTML 标记标签通常被称为 HTML 标签 (HTML tag)。

- HTML 标签是由尖括号包围的关键词，如`<html>`
- HTML 标签通常成对出现，如`<b>` 和` </b>`
- 标签对中的第一个标签是开始标签，第二个标签是结束标签
- 开始和结束标签也被称为开放标签和闭合标签

**HTML 元素**

严格来讲, 一个 HTML 元素包含了开始标签与结束标签，如`<p>这是一个段落。</p>`

**Web 浏览器**

Web浏览器（如谷歌浏览器，Internet Explorer，Firefox，Safari）是用于读取HTML文件，并将其作为网页显示。浏览器并不是直接显示的HTML标签，但可以使用标签来决定如何展现HTML页面的内容给用户：

**HTML 网页结构**

![截屏2024-09-21 15.52.49](https://raw.githubusercontent.com/c0ffee-milk/photo/master/%E6%88%AA%E5%B1%8F2024-09-21%2015.52.49.png?token=BHYTHCZH6YYG7Y25ILWLIC3G5Z5ZI)

只有 <body> 区域 (白色部分) 才会在浏览器中显示。

**<!DOCTYPE> 声明**

`<!DOCTYPE>`声明有助于浏览器中正确显示网页。

网络上有很多不同的文件，如果能够正确声明HTML的版本，浏览器就能正确显示网页内容。

doctype 声明是不区分大小写的。

**中文编码**

目前在大部分浏览器中，直接输出中文会出现中文乱码的情况，这时候我们就需要在头部将字符声明为 UTF-8 或 GBK。

#### HTML 基础

**HTML 标题**

HTML 标题（Heading）是通过<h1> - <h6> 标签来定义的。

```html
<h1>这是一个标题</h1>
<h2>这是一个标题</h2>
<h3>这是一个标题</h3>
```

**HTML 段落**

HTML 段落是通过标签 <p> 来定义的。

```html
<p>这是一个段落。</p>
<p>这是另外一个段落。</p>
```

**HTML 链接**

HTML 链接是通过标签 <a> 来定义的。

```html
<a href="https://www.runoob.com">这是一个链接</a>
```

在 href 属性中指定链接的地址。

**HTML 图像**

HTML 图像是通过标签 <img> 来定义的。

```html
<img src="/images/logo.png" width="258" height="39" />
```

图像的名称和尺寸是以属性的形式提供的。

#### HTML 元素

**HTML 元素语法**

- HTML 元素以开始标签起始，以结束标签终止。元素的内容是开始标签与结束标签之间的内容。
- 某些 HTML 元素具有空内容（empty content）
- 空元素在开始标签中进行关闭（以开始标签的结束而结束）
- 大多数 HTML 元素可拥有属性

**HTML 元素的嵌套**

大多数 HTML 元素可以嵌套（HTML 元素可以包含其他 HTML 元素）。

HTML 文档由相互嵌套的 HTML 元素构成。

**HTML 空元素**

没有内容的 HTML 元素被称为空元素。空元素是在开始标签中关闭的。

`<br>`就是没有关闭标签的空元素（代表换行）。

在 XHTML、XML 以及未来版本的 HTML 中，所有元素都必须被关闭。

在开始标签中添加斜杠，比如` <br />`，是关闭空元素的正确方法，HTML、XHTML 和 XML 都接受这种方式。

即使` <br>` 在所有浏览器中都是有效的，但使用` <br />` 其实是更长远的保障。

#### HTML 属性

属性是 HTML 元素提供的附加信息。

属性总是以 **name="value"** 的形式写在标签内，**name** 是属性的名称，**value** 是属性的值。

**HTML 属性**

- HTML 元素可以设置属性
- 属性可以在元素中添加附加信息
- 属性一般描述于开始标签
- 属性总是以名称/值对的形式出现，比如：name="value"

**`id`**: 给元素一个唯一的标识符，可以用于 CSS 选择器或 JavaScript 操作。

```html
<div id="header">This is a header</div>
```

**`class`**: 给元素指定一个或多个类名，方便通过 CSS 或 JavaScript 操作。

```html
<p class="text-muted">This is a paragraph.</p>
```

**`style`**: 直接为元素定义 CSS 样式。

```html
<span style="color: red;">This text is red.</span>
```

**`href`**: 用于 `<a>` 标签，指定链接目标。

```html
<a href="https://www.example.com">Visit Example</a>
```

**`src`**: 用于 `<img>` 和 `<script>` 标签，指定资源的路径。

**`alt`**: 用于 `<img>` 标签，提供图片的替代文本。

```html
<img src="image.jpg" alt="Description">
```

**`title`**: 提供关于元素的额外信息，通常在鼠标悬停时显示。

```html
<button title="Click me">Submit</button>
```

**`name`**: 在 `<input>`, `<form>`, `<select>` 等表单元素中使用，定义元素的名称。

```html
<input type="text" name="username">
```

**`value`**: 定义表单元素的值。

```html
<input type="text" value="Default text">
```

**`target`**: 用于 `<a>` 标签，指定链接的打开方式（如 `_blank` 在新窗口中打开）。

```html
<a href="https://www.example.com" target="_blank" rel="noopener">Open in new tab</a>
```

**`type`**: 指定表单元素的类型（如 `text`, `password`, `submit`）。

```html
<input type="password" name="password">
```

**`placeholder`**: 为 `<input>` 和 `<textarea>` 提供一个占位符文本。

```html
<input type="text" placeholder="Enter your name">
```

#### HTML 标题

标题（Heading）是通过 `<h1> - <h6>` 标签进行定义的。

下划线：`<hr>`

注释：`<!-- -->`

#### HTML 段落

段落：`<p>xxx</p>`

段中换行：`<p>xxx<br>xxx<br>xxx</p>`

#### HTML 文本格式化

![截屏2024-09-23 21.05.40](https://raw.githubusercontent.com/c0ffee-milk/photo/master/%E6%88%AA%E5%B1%8F2024-09-23%2021.05.40.png?token=BHYTHCYU7F37KJOPZC57JEDG6FT6K)

#### HTML 链接

HTML 使用超级链接与网络上的另一个文档相连。

HTML中的链接是一种用于在不同网页之间导航的元素。

链接通常用于将一个网页与另一个网页或资源（如文档、图像、音频文件等）相关联。

链接允许用户在浏览网页时单击文本或图像来跳转到其他位置，从而实现网页之间的互联。

**HTML 链接语法**

- `href`：指定链接目标的URL，这是链接的最重要属性。可以是另一个网页的URL、文件的URL或其他资源的URL。
- `target`（可选）：指定链接如何在浏览器中打开。常见的值包括 `_blank`（在新标签或窗口中打开链接）和 `_self`（在当前标签或窗口中打开链接）。
- `title`（可选）：提供链接的额外信息，通常在鼠标悬停在链接上时显示为工具提示。
- `rel`（可选）：指定与链接目标的关系，如 nofollow、noopener 等。

**图像链接：**您还可以使用图像作为链接。在这种情况下，<a> 元素包围着 <img> 元素。例如：

```html
<a href="https://www.example.com">
  <img src="example.jpg" alt="示例图片">
</a>
```

**锚点链接：**除了链接到其他网页外，您还可以在同一页面内创建内部链接，这称为锚点链接。要创建锚点链接，需要在目标位置使用 <a> 元素定义一个标记，并使用#符号引用该标记。例如：

```html
<a href="#section2">跳转到第二部分</a>
<!-- 在页面中的某个位置 -->
<a name="section2"></a>
```

**下载链接：**如果您希望链接用于下载文件而不是导航到另一个网页，可以使用 download 属性。例如：

```html
<a href="document.pdf" download>下载文档</a>
```

#### HTML `<head>`

<head> 元素包含了所有的头部标签元素。在 <head>元素中你可以插入脚本（scripts）, 样式文件（CSS），及各种meta信息。

可以添加在头部区域的元素标签为: <title>, <style>, <meta>, <link>, <script>, <noscript> 和 <base>。

**`title` 元素**

- 定义了浏览器工具栏的标题
- 当网页添加到收藏夹时，显示在收藏夹中的标题
- 显示在搜索引擎结果页面的标题

**`base` 元素**

`<base> `标签描述了基本的链接地址/链接目标，该标签作为HTML文档中所有的链接标签的默认链接:

```html
<head>
<base href="http://www.runoob.com/images/" target="_blank">
</head>
```

**`link` 元素**

<link> 标签定义了文档与外部资源之间的关系。

<link> 标签通常用于链接到样式表:

```html
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```

**`style`元素**

`<style> `标签定义了HTML文档的样式文件引用地址.

在`<style> `元素中你也可以直接添加样式来渲染 HTML 文档:

```html
<head>
<style type="text/css">
body {
    background-color:yellow;
}
p {
    color:blue
}
</style>
</head>
```

#### HTML 样式-CSS

CSS 可以通过以下方式添加到HTML中:

- 内联样式- 在HTML元素中使用"style" 属性
- 内部样式表 -在HTML文档头部 <head> 区域使用<style> 元素 来包含CSS
- 外部引用 - 使用外部 CSS 文件

#### HTML 图像

**HTML 图像- 图像标签（ <img>）和源属性（Src）**

<img> 是空标签，意思是说，它只包含属性，并且没有闭合标签。

要在页面上显示图像，你需要使用源属性（src）。src 指 "source"。源属性的值是图像的 URL 地址。语法：

```html
<img src="url" alt="some_text">
```

**HTML 图像- 设置图像的高度与宽度**

height（高度） 与 width（宽度）属性用于设置图像的高度与宽度。

属性值默认单位为像素:

 ```html
 <img src="pulpit.jpg" alt="Pulpit rock" width="304" height="228">
 ```

#### HTML 表格

HTML 表格由 **<table>** 标签来定义。

每个表格均有若干行（由 **<tr>** 标签定义），每行被分割为若干单元格（由 **<td>** 标签定义），表格可以包含标题行（**<th>**）用于定义列的标题。

```html
<table>
  <thead>
    <tr>
      <th>列标题1</th>
      <th>列标题2</th>
      <th>列标题3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>行1，列1</td>
      <td>行1，列2</td>
      <td>行1，列3</td>
    </tr>
    <tr>
      <td>行2，列1</td>
      <td>行2，列2</td>
      <td>行2，列3</td>
    </tr>
  </tbody>
</table>
```

#### HTML 列表

无序列表：`<ul>`标签

```html
<ul>
<li>Coffee</li>
<li>Milk</li>
</ul>
```

有序列表：`<ol>`标签

```html
<ol>
<li>Coffee</li>
<li>Milk</li>
</ol>
```

自定义列表：自定义列表以 <dl> 标签开始。每个自定义列表项以 <dt> 开始。每个自定义列表项的定义以 <dd> 开始。

```html
<dl>
<dt>Coffee</dt>
<dd>- black hot drink</dd>
<dt>Milk</dt>
<dd>- white cold drink</dd>
</dl>
```

#### HTML 布局

大多数网站会把内容安排到多个列中（就像杂志或报纸那样）。

大多数网站可以使用 <div> 或者 <table> 元素来创建多列。CSS 用于对元素进行定位，或者为页面创建背景以及色彩丰富的外观。

#### HTML 表单和输入

HTML 表单用于收集用户的输入信息。

HTML 表单表示文档中的一个区域，此区域包含交互控件，将用户收集到的信息发送到 Web 服务器。

HTML 表单通常包含各种输入字段、复选框、单选按钮、下拉列表等元素。

- `<form>` 元素用于创建表单，`action` 属性定义了表单数据提交的目标 URL，`method` 属性定义了提交数据的 HTTP 方法（这里使用的是 "post"）。
- `<label>` 元素用于为表单元素添加标签，提高可访问性。
- `<input>` 元素是最常用的表单元素之一，它可以创建文本输入框、密码框、单选按钮、复选框等。`type` 属性定义了输入框的类型，`id` 属性用于关联 `<label>` 元素，`name` 属性用于标识表单字段。
- `<select>` 元素用于创建下拉列表，而 `<option>` 元素用于定义下拉列表中的选项。

```html
<form action="/" method="post">
    <!-- 文本输入框 -->
    <label for="name">用户名:</label>
    <input type="text" id="name" name="name" required>

    <br>

    <!-- 密码输入框 -->
    <label for="password">密码:</label>
    <input type="password" id="password" name="password" required>

    <br>

    <!-- 单选按钮 -->
    <label>性别:</label>
    <input type="radio" id="male" name="gender" value="male" checked>
    <label for="male">男</label>
    <input type="radio" id="female" name="gender" value="female">
    <label for="female">女</label>

    <br>

    <!-- 复选框 -->
    <input type="checkbox" id="subscribe" name="subscribe" checked>
    <label for="subscribe">订阅推送信息</label>

    <br>

    <!-- 下拉列表 -->
    <label for="country">国家:</label>
    <select id="country" name="country">
        <option value="cn">CN</option>
        <option value="usa">USA</option>
        <option value="uk">UK</option>
    </select>

    <br>

    <!-- 提交按钮 -->
    <input type="submit" value="提交">
</form>
```

**HTML 表单**

表单是一个包含表单元素的区域。

表单元素是允许用户在表单中输入内容，比如：文本域（textarea）、下拉列表（select）、单选框（radio-buttons）、复选框（checkbox） 等等。

method 属性：

- **post**：指的是 HTTP POST 方法，表单数据会包含在表单体内然后发送给服务器，用于提交敏感数据，如用户名与密码等。
- **get**：默认值，指的是 HTTP GET 方法，表单数据会附加在 **action** 属性的 URL 中，并以 **?**作为分隔符，一般用于不敏感信息，如分页等。例如：https://www.runoob.com/?page=1，这里的 page=1 就是 get 方法提交的数据。

![Monica_2024-09-24_11-44-41](https://raw.githubusercontent.com/c0ffee-milk/photo/master/Monica_2024-09-24_11-44-41.png?token=BHYTHC555L6VVXSASYNDUXLG6I27C)

#### HTML 框架

通过使用框架，你可以在同一个浏览器窗口中显示不止一个页面。

**iframe语法:**

```html
<iframe src="URL"></iframe>
```

#### HTML 脚本

JavaScript 使 HTML 页面具有更强的动态和交互性。

**HTML `<script>` 标签**

`<script>`标签用于定义客户端脚本，比如 JavaScript。

`<script>` 元素既可包含脚本语句，也可通过 src 属性指向外部脚本文件。

JavaScript 最常用于图片操作、表单验证以及内容动态更新。

下面的脚本会向浏览器输出"Hello World!"：

```html
<script>
document.write("Hello World!");
</script>
```

**HTML `<noscript>` 标签**

`<noscript>` 标签提供无法使用脚本时的替代内容，比方在浏览器禁用脚本时，或浏览器不支持客户端脚本时。

`<noscript>`元素可包含普通 HTML 页面的 body 元素中能够找到的所有元素。


只有在浏览器不支持脚本或者禁用脚本时，才会显示 <noscript> 元素中的内容：

```html
<script>
document.write("Hello World!")
</script>
<noscript>抱歉，你的浏览器不支持 JavaScript!</noscript>
```

#### HTML 统一资源定位器（Uniform Resource Locators）

URL 是一个网页地址。

Web浏览器通过URL从Web服务器请求页面。

当您点击 HTML 页面中的某个链接时，对应的 <a> 标签指向万维网上的一个地址。

一个统一资源定位器(URL) 用于定位万维网上的文档。

一个网页地址实例: http://www.runoob.com/html/html-tutorial.html 语法规则:

```html
scheme://host.domain:port/path/filename
```

- scheme - 定义因特网服务的类型。最常见的类型是 http
- host - 定义域主机（http 的默认主机是 www）
- domain - 定义因特网域名，比如 runoob.com
- :port - 定义主机上的端口号（http 的默认端口号是 80）
- path - 定义服务器上的路径（如果省略，则文档必须位于网站的根目录中）。
- filename - 定义文档/资源的名称

#### HTML 速查列表

https://www.runoob.com/html/html-quicklist.html



### 2.2 CSS

#### CSS 简介

**什么是CSS？**

- CSS 指层叠样式表 (**C**ascading **S**tyle **S**heets)
- 样式定义**如何显示** HTML 元素
- 样式通常存储在**样式表**中
- 把样式添加到 HTML 4.0 中，是为了**解决内容与表现分离的问题**
- **外部样式表**可以极大提高工作效率
- 外部样式表通常存储在 **CSS 文件**中
- 多个样式定义可**层叠**为一个

#### CSS 语法

CSS 规则由两个主要的部分构成：选择器，以及一条或多条声明:

![632877C9-2462-41D6-BD0E-F7317E4C42AC](https://raw.githubusercontent.com/c0ffee-milk/photo/master/632877C9-2462-41D6-BD0E-F7317E4C42AC.jpg?token=BHYTHC53H7E7WB4AIAM6FB3G6ZMB6)

注释：/* */

#### CSS id 和 class

**id选择器**

id 选择器可以为标有特定 id 的 HTML 元素指定特定的样式。

HTML元素以id属性来设置id选择器,CSS 中 id 选择器以 "#" 来定义。

以下的样式规则应用于元素属性 id="para1":

```css
#para1
{
    text-align:center;
    color:red;
}
```

**class 选择器**

class 选择器用于描述一组元素的样式，class 选择器有别于id选择器，class可以在多个元素中使用。

class 选择器在 HTML 中以 class 属性表示, 在 CSS 中，类选择器以一个点 **.** 号显示：

在以下的例子中，所有拥有 center 类的 HTML 元素均为居中。

```css
.center {text-align:center;}
```

你也可以指定特定的 HTML 元素使用 class。

在以下实例中, 所有的 p 元素使用 class="center" 让该元素的文本居中:

```css
p.center {text-align:center;}
```

#### CSS 创建

当读到一个样式表时，浏览器会根据它来格式化 HTML 文档。

插入样式表的方法有三种:

- 外部样式表(External style sheet)
- 内部样式表(Internal style sheet)
- 内联样式(Inline style)

**外部样式表**

当样式需要应用于很多页面时，外部样式表将是理想的选择。在使用外部样式表的情况下，你可以通过改变一个文件来改变整个站点的外观。每个页面使用 <link> 标签链接到样式表。 <link> 标签在（文档的）头部：

```html
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```

浏览器会从文件 mystyle.css 中读到样式声明，并根据它来格式文档。

外部样式表可以在任何文本编辑器中进行编辑。文件不能包含任何的 html 标签。样式表应该以 .css 扩展名进行保存。下面是一个样式表文件的例子：

```css
hr {color:sienna;}
p {margin-left:20px;}
body {background-image:url("/images/back40.gif");}
```

**内部样式表**

当单个文档需要特殊的样式时，就应该使用内部样式表。你可以使用 <style> 标签在文档头部定义内部样式表，就像这样:

```html
<head>
<style>
hr {color:sienna;}
p {margin-left:20px;}
body {background-image:url("images/back40.gif");}
</style>
</head>
```

**内联样式**

要使用内联样式，你需要在相关的标签内使用样式（style）属性。Style 属性可以包含任何 CSS 属性。本例展示如何改变段落的颜色和左外边距：

```html
<p style="color:sienna;margin-left:20px">这是一个段落。</p>
```

**多重样式优先级**

一般情况下，优先级如下：

**（内联样式）Inline style > （内部样式）Internal style sheet >（外部样式）External style sheet > 浏览器默认样式**

#### CSS 背景

![截屏2024-09-27 15.17.37](https://raw.githubusercontent.com/c0ffee-milk/photo/master/%E6%88%AA%E5%B1%8F2024-09-27%2015.17.37.png?token=BHYTHCZ3UOEW7SCG47NZK33G6ZOFE)

#### CSS 文本

![截屏2024-09-27 15.23.01](https://raw.githubusercontent.com/c0ffee-milk/photo/master/%E6%88%AA%E5%B1%8F2024-09-27%2015.23.01.png?token=BHYTHC5XGYHZIL6OIUSRMMLG6ZOZO)

**字体系列**

font-family 属性设置文本的字体系列。

font-family 属性应该设置几个字体名称作为一种"后备"机制，如果浏览器不支持第一种字体，他将尝试下一种字体。

**注意**: 如果字体系列的名称超过一个字，它必须用引号，如Font Family："宋体"。

多个字体系列是用一个逗号分隔指明：

```css
p{font-family:"Times New Roman", Times, serif;}
```

**字体样式**

主要是用于指定斜体文字的字体样式属性。

这个属性有三个值：

- 正常 - 正常显示文本
- 斜体 - 以斜体字显示的文字
- 倾斜的文字 - 文字向一边倾斜（和斜体非常类似，但不太支持）

**字体大小**

px：像素大小，默认16px

em：1em和当前字体大小相等。在浏览器中默认的文字大小是16px。因此，1em的默认大小是16px。可以通过下面这个公式将像素转换为em：**px/16=em**

百分比与em组合：在所有浏览器的解决方案中，设置 <body>元素的默认字体大小的是百分比：

```css
body {font-size:100%;}
h1 {font-size:2.5em;}
h2 {font-size:1.875em;}
p {font-size:0.875em;}
```

![截屏2024-09-27 15.38.10](https://raw.githubusercontent.com/c0ffee-milk/photo/master/%E6%88%AA%E5%B1%8F2024-09-27%2015.38.10.png?token=BHYTHC7TE7MS3BUTSANOTULG6ZQSG)

#### CSS 链接

**链接样式**

链接的样式，可以用任何CSS属性（如颜色，字体，背景等）。

特别的链接，可以有不同的样式，这取决于他们是什么状态。

这四个链接状态是：

- a:link - 正常，未访问过的链接
- a:visited - 用户已访问过的链接
- a:hover - 当用户鼠标放在链接上时
- a:active - 链接被点击的那一刻

```css
a:link {color:#000000;}      /* 未访问链接*/
a:visited {color:#00FF00;}  /* 已访问链接 */
a:hover {color:#FF00FF;}  /* 鼠标移动到链接上 */
a:active {color:#0000FF;}  /* 鼠标点击时 */
```

