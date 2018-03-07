### 1.文字
``` python
font-weight: bold/normal
font-style: static/normal
font-size:
(1)测量文字大小时，以正方形的方式测量
(2)字体大小最好是偶数
(3)提高测量文字效率的小技巧：
    1) 字体小于20像素时，可以直接量相对饱满度的文字高度
    2) 每一个文字图片都是正方形
    3) 绝大多数文字右侧都会预留1px空隙
    4) 文字字体越大，右侧空隙会相对越大
    5) 文字默认字体大小：
     16px  --window chrome
     浏览器限制，中文字体最小12px
font-family:
line-height:
    行高 = 文字大小 + 上下留白区域
    当上下留白为奇数时，上留白少1px
    
复合样式: font-weight font-style font-size/line-height font-family    
```
### 2.测量行高
``` python
方法一：
    1) 确定文字大小 
    2) 测量两行文字中间的空白区域
    3) 根据第二步得出的值/2
    4) 平均分配给文字上下区域
方法二:
    测量第一行文字顶部到第二行文字的顶部

注： (1) 当没有高度时，行高会撑开容器
     (2) 当行高与高度同时存在时，容器以高度的值为主
     (3)行高为偶数时，才会发生偏移
     (4)没有经过任何处理的情况下，文字默认就会有行高
```
### 3.超链接：
``` python
(1)相对路径：根据自身文件所处的位置进行路经查找；
(2)绝对路径： http:// https:// svn:// git://
    ftp:// file://；
(3)锚点：通过a标签的href属性中填写#id名称，当点击时会自动定位到该元素所在的位置；
(4)下载：a标签默认的下载行为是有要求的，只能是非文档的格式
target:_blank, _self(默认值)
```
### 4.文字
``` python
text-align: center/left/right
text-indent: px/em   1em = 当前字体的大小
text-decoration：underline/line-through/upperline/none
letter-spacing: 字母间距
word-spacing: 单词以空格隔开
white-space: nowrap/wrap(默认)
word-wrap: break-word
```
### 5.一个空格有多大？
```python
(1)在(宋体)的情况下，字体大小的一半
(2)单词间距 = 测量间距 - 默认以空格间距
(3)空格存在于兄弟元素之间，inline, line-block存在上或左右空格
```
### 6. 盒模型

``` python
padding内填充
margin外边距，不会改变容器的大小

问题：
(1)margin-top、margin-bottom传递给父级
    解决方案：
        1) 给父级添加border -- 重绘
        2) 给父级添加padding来达到同样的视觉效果
(2)同级元素margin叠压，以最大值为标准
    解决方案：
        1) 可以设置单一方向的margin
        2) 如果元素没有特殊特征，可以用padding代替
```
### 7.盒模型
``` python
(1)盒子组成：margin border padding width/height
(2)盒子大小 = border+padding+width/height
```
### 8.解决空格：
``` python
(1)font-size: 0; 但在有些浏览器中字体大小有限制
(2)body{
    font-size: 12px;
    font-family: '宋体';
    margin-right: -6px;
}（不常用）
(3)word-sapcing
```
