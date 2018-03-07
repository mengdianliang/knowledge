### 1. border-radius
``` python
   (1) border-radius: 40px;
   (2) border-radius: 10px 40px;
       border-radius: 10px 20px 30px;
       border-radius: 10px 20px 30px 40px;
       左上、右上、右下、左下
   (3) x(水平、宽)/y(垂直、高)
        圆角最大值：宽高两个值中最小值的一半
```
### 2.盒模型阴影
``` python
(1) box-shadow：[inset] x y blur [spread] color;
(2) 三向有阴影，头部没有阴影怎么做？
    box-shadow: 0 1px 3px #999999;
(3) 只有底部有阴影： box-shadow: 0 3px 0 #999999;
```
### 2.雪碧图
``` python
(1) 好处？
    1) 减少图片请求数量
    2) 服务端加快图片显示
    3) 节省服务器资源
(2) 局限性、规则？
    1) 不经常更换的小图片
    2) 装饰性的小图片
(3) 建议：
    1) 存一个PSD文件作为备用修改文件
    2) png24作为css引入文件
    3) 一个页面一张雪碧图
```