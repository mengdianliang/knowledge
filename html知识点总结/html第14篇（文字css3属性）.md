### 1. 文字阴影
``` python
    text-shadow: x y blur color
    文字阴影如果加很多层，会很卡很卡...
```
### 2. 文字描边
``` python
    -webkit-text-stroke: 宽度 颜色
```
### 3. 文字溢出
``` python
    text-overflow: 
    clip 无省略号
    ellipsis 省略号   配合overflow：hidden 和white-space: nowrap;一起使用(只能处理单行)
    
    多行文字：
    方法一： 用after来做，不过文字不溢出，也会有省略号
    方法二： display: -webkit-box;
             -webkit-box-orient: vertical;
             -webkit-line-clamp: 2;
             overflow: hidden;
    方法三： 用js处理         
```
### 4. 多背景
``` python
    用逗号分开，先写先展示
    注意：如果使用多张背景图，并且还需要使用背景颜色时，需要将背景色放在最后一组中
    background-size: x y 
                    100% 100% 或者 100%
                    % px
                    cover放大
                    contain缩小
```
### 5. 背景显示位置
``` python
    background-origin: 
    border-box
    padding-box
    content-box
```
### 6. 背景剪切
``` python
    background-clip: 
    border-box
    padding-box
    content-box
    no-clip: 从border区域向外剪切背景
    
    
    （背景在文字上）
    -webkit-background-clip: text; 以文字进行剪切
    文字需要具备透明度属性
    
    eg: html:
            <section>妙味课堂</section>
        css:
            div{
                border: 20px solid rgba(0,0,0,0.5);
                padding: 20px;
                width: 400px;
                height: 400px;
                background:rgba(255,0,0,0.3) url(img/1.jpg);
                background-clip: -webkit-text;
            }
            section {
                font:bold 68px '黑体';
                background: url(img/3.jpg);
                color: rgba(0,0,0,0);
                -webkit-background-clip: text;
            }
```
### 7. 遮罩
``` python
    html:
        <div></div>
    css:
        div{
            height: 500px;
            background: url(img/1.jpg);
            -webkit-mask-position: 0 0;
            -webkit-mask-repeat: no-repeat;
            transition: 6s;
        }
        div:hover{
            -webkit-mask-position: 500px 500px;
        }
```