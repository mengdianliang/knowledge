### 1. css hack
``` python
   (1) \9 IE10及其以前的IE浏览器
   (2) * IE7以及以前的IE浏览器
   (3) - IE6以及以前的IE浏览器
```
### 2.兼容性
``` python
    由于代码写的不规范，或者不正确导致的问题，这叫做错误，不是兼容性；当我们写了一段正确的代码，但是不同浏览器下，残剩的一些不正确的解析，这叫做兼容性。
(1) 盒模型兼容性：
    IE6（5，6）以下在老版本IE下，不设置文档声明，页面就会陷入怪异盒模型解析：<!DOCTYPE html>
(2) 子级超过父级宽高：
    在IE6（5，6）以下，子元素宽高超出父级的宽高，可以把父级设置好的宽高撑开。
    解决方法：严格控制子级宽高，使其不超过父级宽高
(3) 最小高度：
    在IE6（5，6）以下，块属性元素的高度小于19px的时候，高度会按照19px来处理
    解决方法： overflow： hidden
(4) chrome 文字大小：
    在chrome下，文字大小小于12px的时候，会被当做12px来处理
    解决方法：用图片代替
(5) 1px虚线问题：(边框)
    在IE6(6)以下，1px的点线会显示成虚线 （仅限于1px）
    解决方法：用图片代替
(6) 边框transparent: (三角形、扇形)：
    在IE6（6）下给边框加transparent的时候，border-style最好设置成虚线（dashed）
    经过实际检测（虚线、点线）均可
    eg： .box {
        width: 0;
        height: 0;
        overflow: hidden;
        border: 50px solid(dotted/dashed) transparent;
        border-top: 50px solid red;
    }
(7) h5标签的兼容性：
    1) 自定义标签默认都是内联元素，每个浏览器都支持自定义标签
    2) 可以引入h5兼容文件： html5shiv.min.js
(8) inline-block问题：
    在IE6、7下，不支持给块标签加inline-block
    解决方案：
        在inline-block下，添加以下代码：
        *display: inline;
        *zoom: 1;
(9) 同级浮动问题：
    同级有浮动元素，最好所有同级元素都浮动
(10) 浮动双边距：
    IE6下，双边距bug
    在IE6下，块元素所有浮动有横向的margin,横向的margin值会被放大两倍
    浮动方向与margin方向一致时，该方向会出现双边距
    解决方法是：display:inline;
(11) 浮动下margin失效：
    在IE6（5，6，7）下，一行元素的宽度与父级宽度相差超过2px（最好不要超过2px）,最后后一行元素的下margin会失效
    解决方法：无
    可以在父级上加： padding-bottom: 5px；
(12) 文字溢出：
    在IE6（5，6）下，子级元素的宽度和父级宽度相差小于3px，并且两个浮动之后之间有注释或者内嵌元素，元素内容会被复制
    解决方法：可以用div可以把注释或内嵌元素包起来
(13) li之间的间隙：
    在IE5，6，7下，li本身没有加浮动，但是li的内容都浮动或有定位，li下边就会有4px的间隙
    解决方法： vertical-align: top;
               display: inline;
               zoom: 1;
(14) 绝对定位元素消失：
     在IE6下，当浮动元素和绝对定位元素是同级关系的话(并且浮动元素的站位宽度和父级小于3px)，绝对定位元素会消失掉 
    解决方法： 把绝对定位元素单独包起来
(15) 定位偏移量误差：
    在IE6下，定位父级元素宽度为奇数时，元素的right值和bottom值会有1px的偏差
    解决方法：父级元素宽度最好为偶数
(16) 父级无法包含相对定位子级（并且子级容器超出父级）：
    在IE6，7下，子元素有相对定位时，父级的overflow包不住他
    解决方法：给父级也加相对定位
(17) 固定定位(IE6不支持)：
    1) 页面滚动条默认出现在html标签上
    2) 任何一个元素，子级超出父级宽高。设置overflow:auto后，会出现滚动条
    eg:  html {
            height: 100%;
            overflow:hidden;
        }
        body {
            margin: 0;
            height: 100%;
            overflow:auto;
        }
        #box {
            position:abslute;
            right: 0;
            top: 100px;
            width: 1000px;
            height: 100px;
            background: red;
            font-size: 20px;
            color: #ffffff;
        }
        该代码在IE6下系统会崩，不要用
(18) 输入类型控件（5，6，7，8）：
     在IE6、7下，input上下各有1px的间隙
     解决方法：给input加浮动
     (text, password, textarea)
(18) 输入类型控件背景图问题：
    在IE6下，输入类型的表单控件，输入文字的时候，背景图会随文字一起移动。
    解决方法： 设置背景图固定定位 ？？？
    *background-position: fixed;
(19) 输入类型控件边框问题：
    在IE6下，输入类型表单控件border: none无效
    解决方法：
    1) border: 0;
    2) 重置input背景
    如果不要背景： background-color: rgba(0,0,0,0)
        该代码在IE6下系统会崩，不要用
(20) hover只有放在a标签下才好用，IE6下，不行的话用js解决：
     a标签上margin有时改为block,在IE6下不起作用，但改为inline反而起作用了    
```