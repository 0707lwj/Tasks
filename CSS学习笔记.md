# CSS学习笔记

一、CSS的作用

- 样式定义：CSS（层叠样式表）用于控制HTML元素的外观和布局。它可以让网页从单调的纯文本形式转变为具有丰富视觉效果的页面，比如设置文字的颜色、字体、大小，元素的背景颜色、边框样式，以及页面的整体布局等。
- 分离样式与内容：使得HTML文件专注于内容结构的搭建，而将样式相关的设置放在独立的CSS文件（或在HTML文件的特定区域）中，这样便于维护和修改样式，当需要更改整个网站的风格时，只需修改CSS文件而不用在每个HTML标签里逐一调整。

二、CSS选择器

1. 通用选择器（*）

- 作用：选择页面上的所有元素。
- 示例：

```css
*{
    margin: 0;
    padding: 0;
    }
```

这会将页面上所有元素的外边距和内边距都设置为0。

2. 元素选择器

- 作用：根据元素的标签名来选择元素。
- 示例：
```css
p {
    color: red;
    font-size: 16px;
}
```

上述代码会将所有 `<p>`段落元素的颜色设置为红色，字体大小设置为`16px`。

3. 类选择器（.classname）

- 作用：通过在HTML元素中定义的类名来选择元素。可以将相同的类名赋予多个不同元素，以便对这些元素应用相同的样式。
- 示例：
在HTML中：
```css
<div class="highlight">这是一个有特殊样式的div</div>
<p class="highlight">这是一段有特殊样式的段落</p>
```

在CSS中：
```css
.highlight {
    background-color: yellow;
    font-weight: bold;
}
```

这样，带有 highlight 类名的 `<div>` 和` <p> `元素都会有黄色背景和加粗字体的样式。

4. ID选择器（#idname）

- 作用：依据HTML元素的唯一ID来选择元素。每个ID在页面中应该是独一无二的，主要用于对特定的单个元素进行精准样式设置。
- 示例：
在HTML中：
```css
<div id="main-content">这是主要内容区域</div>
```

在CSS中：
```css
#main-content {
    width: 800px;
    margin: 0 auto;
}
```

这里就对ID为 main-content 的 `<div>` 元素设置了宽度为800px，并使其在页面中水平居中。

三、设置元素基础样式

- 大小：可以通过 width 和 height 属性来设置元素的宽度和高度。例如：
```css
div {
    width: 200px;
    height: 100px;
}
```

- 颜色：使用 color 属性设置文字颜色， background-color 属性设置背景颜色。如：
```css
p {
    color: blue;
    background-color: lightgray;
}
```

- 文字字体：通过 font-family 属性指定字体， font-size 属性设置字体大小， font-weight 属性调整字体粗细等。例如：
```css
h1 {
    font-family: Arial, sans-serif;
    font-size: 32px;
    font-weight: bold;
}
```

四、CSS盒模型

- 组成：
- 内容区（Content）：是元素实际包含的内容，比如文本、图像等。
- 内边距（Padding）：位于内容区和边框之间的空白区域，可以通过 padding 属性设置。
- 边框（Border）：围绕在内边距外面的线条，可以通过 border 属性设置边框的样式、宽度和颜色。
- 外边距（Margin）：位于边框外面的空白区域，用于控制元素与周围元素的间隔，通过 margin 属性设置。
- 示例：
```css
div {
    width: 200px;
    height: 100px;
    padding: 10px;
    border: 1px solid black;
    margin: 15px;
}
```

这个 div 元素的内容区大小是200px×100px，内边距为10px，边框是1px宽的黑色实线，外边距是15px。

五、CSS的5种position定位

1. static（默认）

- 特点：元素按照正常的文档流顺序排列，不受 top 、 bottom 、 left 、 right 等定位属性的影响。

2. relative（相对定位）

- 特点：元素相对于其自身在正常文档流中的原始位置进行定位。可以通过 top 、 bottom 、 left 、 right 等属性来调整其位置，但它原来占据的空间仍然保留。
- 示例：
```css
div {
    position: relative;
    left: 20px;
    top: 10px;
}
```

这个 div 元素会相对于它原来的位置向左移动20px，向上移动10px，但原来的空间依然被占用。

3. absolute（绝对定位）

- 特点：元素脱离正常的文档流，相对于其最近的已定位祖先元素（即具有除 static 以外的定位方式的祖先元素）进行定位。如果没有已定位的祖先元素，则相对于文档的根元素（ `<html> `）进行定位。它原来占据的空间不再保留。
- 示例：
```css
.parent {
    position: relative;
}
.child {
    position: absolute;
    left: 10px;
    top: 10px;
}
```

这里先将父元素设置为相对定位，然后子元素设置为绝对定位，子元素就会相对于父元素的左上角向左移动`10px`，向上移动`10px`，并且子元素原来在文档流中的空间不再保留。

4. fixed（固定定位）

- 特点：元素脱离正常的文档流，相对于浏览器窗口进行定位。无论页面如何滚动，该元素的位置始终不变。
- 示例：
```css
div {
    position: fixed;
    top: 10px;
    right: 10px;
}
```

这个` div `元素会固定在浏览器窗口的右上角，距离顶部`10px`，距离右侧`10px`，即使页面滚动也不会改变位置。

5. sticky（粘性定位）

- 特点：元素在正常文档流中开始，当页面滚动到一定位置时，它会根据设置的条件（如距离顶部的距离等）开始脱离正常文档流并进行定位，既具有相对定位的某些特点，又具有绝对定位的某些特点。
- 示例：
```css
div {
    position: sticky;
    top: 0;
}
```

这个` div` 元素在页面滚动前按照正常文档流排列，当页面滚动到` div `元素距离顶部为0时，它就会固定在页面顶部，不再随着页面滚动而移动，直到页面再次滚动到使它不再满足粘性定位的条件。

六、CSS常用布局方式

1. 浮动布局（Float）

- 原理：通过设置元素的 float 属性（如 float: left 或 float: right ），使元素脱离正常的文档流并向左或向右浮动，其他元素会围绕着浮动元素排列。常用于实现多列布局等。
- 示例：
```css
.left-column {
    float: left;
    width: 300px;
}
.right-column {
    float: right;
    width: 500px;
}
```

这里将两个` div `元素分别设置为向左和向右浮动，实现了两列布局。

2. 弹性布局（Flex）

- 原理：使用 display: flex 或 display: flexbox 将父元素设置为弹性布局容器，然后通过一系列的子元素属性（如 flex-grow 、 flex-shrink 、 flex-basis 等）来控制子元素在容器中的排列、拉伸、收缩等行为，实现灵活的布局效果。
- 示例：
```css
.container {
    display: flex;
    justify-content: space-between;
    alignItems: center;
}
```

这里将 container 父元素设置为弹性布局，通过 justify-content 属性使子元素在水平方向上均匀分布，通过  alignItems 属性使子元素在垂直方向上居中。

3. 网格布局（Grid）

- 原理：使用 display: grid 将父元素设置为网格布局容器，然后通过定义网格的行和列（如 grid-template-columns 、 grid-template-rows 等）以及子元素在网格中的位置（如 grid-column-start 、 grid-column-end 、 grid-row-start 、 grid-row-end 等）来实现复杂的布局效果，适合于制作规整的多列、多行布局。
- 示例：
```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr;
}
```

这里将 container 父元素设置为网格布局，设置了3列2行的网格结构，子元素可以根据需要放置在不同的网格位置上。

七、CSS伪类

- 定义：伪类是添加到选择器的关键字，指定要选择的元素的特定状态或条件。
- 示例：
```css
:hover
```
- 作用：当鼠标悬停在元素上时应用相应的样式。
- 示例：
```css
a:hover {
    color: red;
}
```

当鼠标悬停在 `<a> `链接上时，链接的颜色会变成红色。
```css
:active
```
- 作用：当元素被按下（如鼠标点击时）时应用相应的样式。
- 示例：
```css
button:active {
    background-color: gray;
}
```

当鼠标点击` <button>` 按钮时，按钮的背景颜色会变成灰色。
```css
:first-child
```
- 作用：选择父元素的第一个子元素。
- 示例：
```css
ul li:first-child {
    font-weight: bold;
}
```

在` <ul> `列表中，第一个 `<li> `子元素会有加粗字体的样式。
