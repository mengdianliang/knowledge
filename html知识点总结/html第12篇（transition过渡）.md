### 1. transition（只支持样式值能解析成数字的都支持）
``` python
    (1) 多个参数用空格隔开，多组参数用逗号隔开：
    transition-property: 要运动的样式（all（默认）/ [attr] || none）
    transiiton-delay:延迟时间
    transition-timing-function: 运动形式
        ease 逐渐变慢 （默认值）
        linear (匀速)
        ease-in (加速)
        ease-out(减速)
        ease-in-out（先加速后减速）
        cubic-bezier贝塞尔曲线（x1,y1,x2,y2）
    transition-duration: 执行效果所需时间    
```
### 2. transition的问题
``` python
    当在过度过程中且没有到达目标点前，中途离开并再次触发时，那么还将所设置的时间再次进行过渡    
```
### 3. 过渡加给谁？
``` python
    谁要变加给谁 
```
### 4. img问题？
``` python
    img不设置display: block是不会居中的（margin： 0 auto； 无效）？
    元素也可以居中，但IE6下不行 
```