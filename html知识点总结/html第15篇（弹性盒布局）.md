### 1. 布局划分
``` python
    常规布局：
    1) 使用浮动让块元素在一行显示
    2) 父级宽度需要大于等于所有子级宽度
    弹性盒布局:
    父级设置弹性盒模型： display:flex; 需要让某个元素的子孙元素具备弹性盒模型的特征，那么就给该元素设置
```
### 2. 主轴
``` python
    flex-direction: 
        row (默认值)
        row-reverse
        column
        column-reverse
```
### 3. 主轴对齐方式
``` python
    justify-content:
        flex-start（默认）:  元素在开始位置，富余空间占据另一侧
        flex-end: 富余空间在开始位置，元素占据另一侧
        center: 元素居中，富余空间均分左右两侧
        space-between: 富余空间在元素之间平均分配
        space-around: 富余空间在元素两侧平均分配
```        
### 3. 侧轴对齐方式
``` python
    align-items:
        flex-start(默认): 元素在开始位置，富余空间占据另一侧
        flex-end/center
```
### 4. 设置是否换行
``` python
    flex-wrap:换行/nowrap(不换行)/wrap/wrap-reverse
```
### 5. 设置伸缩性
``` python
    flex：none | [ flex-grow ] || [ flex-shrink ] || [ flex-basis ]
    
    none：none关键字的计算值为: 0 0 auto
    [ flex-grow ]：定义弹性盒子元素的扩展比率。
    [ flex-shrink ]：定义弹性盒子元素的收缩比率。
    [ flex-basis ]：定义弹性盒子元素的默认基准值
    
    一般的，flex: 1
    flex: 0 0 200px;
```