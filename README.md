
# CSS-skill
## 1.使用CSS reset
#####   像normalize.css这样的CSS重置库非常受欢迎，它为您的站点样式提供了一个清爽的选择，能确保浏览器之间更好的一致性。而实际上并不是每个项目都需要这些库中包含的所有规则，我们可以通过一些简单的css规则就能规避浏览器之间的差异。请看下面的盒模型代码：
```css
* {
  box-sizing: border-box;    
  margin: 0;     
  padding: 0;   
}
```
## 2.继承box-sizing
##### 让 box-sizing 继承 html：
```css
html {     
    box-sizing: border-box;   
}     
*, *:before, *:after {     
    box-sizing: inherit;   
} 
```
##### *这样在插件或杠杆其他行为的其他组件中就能更容易地改变box-sizing了。
## ***使用Flexbox摆脱外边距的各种hack
##### *当需要用到列分隔符时，通过flexbox的 space-between 属性，你就可以摆脱nth-，first-，和 last-child 的hack了：
```css
.list { 
  display: flex; 
  justify-content: space-between; 
} 
 
.list .person { 
  flex-basis: 23%; 
} 
```
## 3.使用：not()定义菜单边框
##### 我们要定义菜单列表的边框，然后去掉最后一个菜单的边框，通常做法是：
```css
.nav li {     
    border-right: 1px solid #666;   
} 
.nav li:last-child {     
    border-right: none;   
} 
```
##### 而我们现在可以直接使用：not()伪类来应用元素，让代码更干净，易读，易于理解。
```css
.nav li:not(:last-child) {     
    border-right: 1px solid #666;   
} 
```
## 4.给 body 添加行高
##### 你不需要分别添加line-height 到每个p，h标记等。只要添加到body即可：
```css
body { 
  line-height: 1.5; 
} 
```
## 5.垂直居中
##### 要将所有元素垂直居中，使用以下代码：
```css
html, body {     
    height: 100%;     
    margin: 0;   
}     
body {     
    -webkit-align-items: center;     
    -ms-flex-align: center;     
    align-items: center;     
    display: -webkit-flex;     
    display: flex;   
}  
```
## 6.使用SVG作为图标
##### SVG可以适应不同的分辨率，并且在所有的浏览器中都支持，还有什么理由不用呢。
```css
.logo {     
    background: url("logo.svg");   
} 
```
## 7.等宽的表格单元格
##### 表格工作起来很麻烦，所以务必尽量使用 table-layout: fixed 来保持单元格的等宽：
```css
.calendar { 
  table-layout: fixed; 
} 
```
## 8.使用属性选择器用于空链接
##### 当a元素没有文本值，但 href 属性有链接的时候显示链接：
```css
a[href^="http"]:empty::before { 
  content: attr(href); 
} 
```
## 9.图片不存在的替代样式
##### 由于某种原因导致图片加载失败，这时我们使用css来友好的告诉用户图片除状况了。
```css
img {     
    display: block;     
    font-family: Helvetica, Arial, sans-serif;     
    font-weight: 300;     
    height: auto;     
    line-height: 2;     
    position: relative;     
    text-align: center;     
    width: 100%;   
} 
img:before {     
    content: "We're sorry, the image below is missing :(";     
    display: block;     
    margin-bottom: 10px;   
}     
img:after {     
    content: "(url: " attr(src) ")";    
    display: block;     
    font-size: 12px;   
} 
```
## 10.在表单元素上设置font-size
##### 为了避免移动浏览器（iOS Safari等）在点击<select>下拉菜单时放大HTML表单元素，请将font-size添加到输入样式中：
    ```html
	input[type="text"],   
	input[type="number"],   
	select, textarea {     
			font-size: 16px;   
	} 
```
