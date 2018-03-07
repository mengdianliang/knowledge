### 1.html组成？
``` python
html (Hypertext Markup language) 结构
css(Cascading Style Sheets) 样式
js(javascript) 行为
```
### 2.标签分为单标签、双标签
``` python
编码设置： <meta charset="utf-8" />
网页标题: <title></title>
标签嵌套关系：父子关系、兄弟关系
```
### 3.样式分为：
``` python
(1)行间样式：style="" 作用范围：某一个标签
(2)内联样式：<style type="text/css"></style>
(3)外联样式： <link rel="" type="" href="" /><
            如果要设置页面图标：
            <link rel="icon" type="image/x-icon" href="img/fav.ico"/>
```
### 4.边框
``` python
border-top:
    border-top-width
    border-top-style
    border-top-color
border-left/border-right/border-bottom同上
border-width/border-style/border-color
```
### 5.三角和斜角问题？                  
```python
(1)三角的例子：
(2)边框斜角:
    可以通过父元素跟子元素创建边框
```
### 6.css编码风格
``` python
(1)选择器与其实花括号一行
(2)结束的花括号独占一行
(3)css代码整体tab缩进一格
(4)一条css命令独占一行
(5)一条独立且完整的css语法结束后添加分号
```
### 7.background
``` python
(1)background:bg-color bg-image position/bg-size bg-repeat bg-origin bg-clip bg-attachment initial|inherit;
(2)background-color:color/transparent(透明)/inherit(从父元素继承)
(3)background-position:
    1) left right center top center bottom
    2) x% y%
    3) px px
(4)background-size:
    1) length 第一个值代表宽度，第二个只代表高度；如果只有一个值，第二个值默认是auto
    2) percent (同上)
    3) cover 此时会保持图像的纵横比并将图像缩放成将完全覆盖背景定位区域的最小大小。
    4) contain 此时会保持图像的纵横比并将图像缩放成将适合背景定位区域的最大大小。
    
(5)background-repeat: repeat(默认)/repeat-x/repeat-y/no-repeat
(6)background-origin: padding-box|border-box|content-box;
(7)background-clip: border-box|padding-box|content-box;
(8)background-attachment设置背景图像是否固定或者随着页面的其余部分滚动。
    1)scroll 背景图片随页面的其余部分滚动。这是默认
    2)fixed	背景图像是固定的
    3)inherit	指定background-attachment的设置应该从父元素继承
(9)background-image: url(img_flwr.gif), url(paper.gif); 
```
### 8.颜色值
``` python
(1)英文关键字
(2)rgb(),rgba()
(3)十六进制颜色代码
```
