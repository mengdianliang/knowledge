### 1. 页面注释
``` python
    条件注释只有IE浏览器支持，但是只在IE9及其以下有效
    if IE：从IE9及其以下全部认识
   
    <!--[if IE7]>
        <link rel="stylesheet" href="fixIE.css"/>
    <![endif]-->
    
    
    if IE： 从IE9及其以下全部识别
    if IE6: 指定IE版本
    if lte IE7：
    if gte IE7:
    if !IE7
```
### 2. 图片格式
``` python
    (1) jpg、jpeg
       高保真图片
       优点：清晰、样色丰富
       缺点：压缩会有损失、不清晰
    (2) gif
        gif动画
        优点：惠东、体积小
        缺点： 清晰度不高
    (3) png
        优点： 清晰、体积较小、压缩无损
        png-8：劣势：支持全透明、不支持半透明
        png-24: 优势： 支持全透明、半透明
        
        
    注：jpg: 完全不透
        gif: 全透明
        png-8: 全透明
        png-24: 全透明、半透明
    (4) IE6不支持png-24
        解决方法：
        1) js插件：
            DD-letatedPNG.fix('.fixImg');
            js/DD-letatedPNG_0.0.8a.js
            
            缺点： 不支持body背景图png24处理
        2) 滤镜：(全支持)
        ????????
```
### 3. 一些小问题
``` python
    (1) 消除某一方向的定位： right: initial
    (2) 图片背景一定要加文字
    (3) min-width（IE7不支持）
    (4) 导航后边的 ‘更多’也算导航内容
    (5) 有些图片IE6下显示不出来，有可能是改图片格式了
    (6) line-height不要与font-size相同，IE6有偏差
    (7) select用结构样式模拟
```