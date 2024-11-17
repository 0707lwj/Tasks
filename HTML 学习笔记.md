## HTML 学习笔记

一、常用 HTML 标签

1.div标签

- 功能：是一个块级元素，常用于将页面划分成不同的区域，方便对页面布局进行设计和样式控制。它没有特定的语义，可以包含各种其他标签。
- 示例：

<div>
    <h1>这是一个标题</h1>
    <p>这是一段内容</p>
</div>
 

2.p标签

- 功能：表示段落，是块级元素。会在段落前后自动添加一些空白间距，使文本更易读。
- 示例：

<p>这是第一段内容。</p>
<p>这是第二段内容。</p>

3.a标签

- 功能：用于创建超链接，可以链接到其他网页、同一网页的其他位置、文件等。通过 href 属性指定目标地址。
- 示例：

<a href="#">这是一个链接</a>


还可以创建页面内的锚点链接，比如：

<a href="#section1">跳转到第一部分</a>

<div id="section1">这是第一部分内容</div>

4.button标签

- 功能：创建一个可点击的按钮，常用于表单提交、触发 JavaScript 函数等操作。可以在按钮内添加文本或其他 HTML 元素。
- 示例：

<button type="submit">提交表单</button>

5.img标签

* 示例：

``` HTML
<img src="./">
```

* 功能：上传图片，常用于美化网站。

6.audio标签

* 示例：

```HTML
<audio src="" controls loop autoplay></audio>
```

* 功能：添加音频，常用于添加背景音乐。

7.video标签

* 示例：

```HTML
<video src="" controls loop muted autoplay></video>
<!-- 要自动播放autopiay必需要自动静音muted -->
```

* 功能：添加视频元素，常用于添加网站视频。


二、块级元素与内联元素

1. 块级元素

- 特点：
- 在页面中独占一行，从新的一行开始，并且占据父元素的整个宽度。
- 可以设置宽度、高度、外边距和内边距等属性。常见的块级元素有 ` <div> `、 `<p>` 、` <h1>-<h6>` 、 `无序列表<ul>` 、 `有序列表 <ol>` 、`包裹内容 <li>` 等。
- 示例：

<h2>块级元素示例</h2>
<div style="background-color: lightgray; width: 300px; height: 200px;">这是一个块级元素<div>
```HTML
<ul>
    <li>666</li>
    <li>666</li>
</ul>
<ol>
    <li>666</li>
    <li>666</li>
</ol>    
```



2. 内联元素

- 特点：
- 不会独占一行，它们在一行内依次排列，直到一行排不下才会换行。
- 宽度和高度属性通常不起作用，其大小由内容决定。内边距和外边距在水平方向有效，但在垂直方向上，外边距和内边距可能不会按预期显示。常见的内联元素有 `<a> `、` <span>` 、` <strong>` 、` <em>` 、`表单<input>`等。
- 示例：

`<span style="background-color: yellow;">`这是一个内联元素`</span>`
`<a href="#">`这是一个链接（内联元素）`</a>`


三、HTML 标签的样式

1. 内联样式

- 方式：在 HTML 标签内使用 style 属性来设置样式。
- 示例：

`<p style="color: red; font-size: 20px;">`这段文字是红色的，字号为 20px。</p>

2. 外部样式表

- 步骤：
- 创建一个 .css 文件，比如 styles.css ，在其中定义样式规则。
- 在 HTML 文件的 `<head> `部分使用` <link>` 标签将 CSS 文件链接到 HTML 文件，例如：

```html
<head>
    <link rel="stylesheet" type="text/css" href="styles.css">
</head>```

- 示例（styles.css）：

```html
p {
    color: blue;
    font-family: Arial, sans-serif;
}```

3. 内部样式表
- 方式：在 HTML 文件的` <head> `部分使用` <style> `标签来定义样式规则。
- 示例：

```html
<head>
    <style>
        h1 {
            color: green;
        }
    </style>
</head>```
