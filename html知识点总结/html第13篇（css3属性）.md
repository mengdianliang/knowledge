### 1. E = element 元素、节点
``` python
    attr = 属性
     写在标签上的都是属性：
     有些属性是标准定义好的，我们叫‘标准属性’: id、class、style
     还有些是不在标准定义中的，我们叫‘自定义属性’，开发者认为创建。习惯性的，使用自定义属性时，加上data-前缀
```
### 2. css3
``` python
    (1) E[attr] 指定属性名，但没有确定任何属性值；
    如果写了element，必须符合element的条件；
    如果没写，那么查找的是所有元素
    
    (2) E[attr=“value”] 
    指定属性名，并指定了该属性的属性值
    属性名，属性值都需要完全匹配
    
    (3) E[attr~=‘value’] 指定属性名，并具有属性值，此属性值是一个此列表，并且以空格隔开，其中词列表中包含了一个value词，且只能是一个value值，而且等号前面的‘~’不能不写。
    词列表： 由多个value组成，并且以空格隔开（类似于多个class）
    ~= 查找词列表中由空格隔开且完整的value值
    
    (4) E[attr^='value']指定了属性名，并且具有属性值，属性值以value开头； 
    从完整的属性值中(被引号包裹)，从左到右逐个匹配，并且每一位都能匹配上才符合条件
    
    (5) E[attr$=“value”] 
    指定属性名，并且有属性值，属性值以value结尾；
    从完整的属性值(被引号包裹)中，从右到左逐个匹配，并且每一个都能匹配上才符合条件
    
    (6) E[attr*=‘value’] 指定属性名，并且有属性值，而且属性值中包含了value,在整个属性值中有符合条件的值即可
    
    (7) E[attr|=“value”] 
    指定属性名，并且属性值是value或以‘value-’开头的值(匹配所有)：
    已匹配的value进行查找，找到以value-开头的属性值的元素
```
### 3. 伪类选择器：
``` python
    （IE9及其以上）一定会从查找元素的父级开始，往子级进行顺序查找 
    (1) E: nth-child(n):表示E的父元素中第n个E子节点
    (2) E: nth-last-child(n): 从后往前计算
            odd、even、2n+1、2n+2
    (3) E: nth-of-type(n): 表示E的父元素的第n个子节点，并且类型为E的第n个
    (4) E: nth-last-of-type(n):从后往前计算 表示E元素的第n个子节点，并且类型为E的第n个
    (5) E: first-child 表示E元素的第一个子节点
    (6) E: last-child 表示E元素的最后一个子节点
    (7) E：first-of-type:表示E元素的第一个子节点，且节点类型为E
        E：last-of-type:表示E元素的最后一个子节点，且节点类型为E
    (8) E: only-child 表示E父元素的只有一个子节点，且这个唯一的子节点的类型必须是E.
    注意：子节点不包含文本节点
    (9) E: empty 表示E元素没有子节点 
    注：子节点包含文本节点
```
### 4. E:target (锚点)
``` python
    表示当前的url片段的元素类型，这个元素必须是E；
    如果写了element，那么元素与url片段需要全部匹配
    eg: html：
        <a href="#div1">div1</a>
        <a href="#div2">div2</a>
        <a href="#div3">div3</a>
        <div id="div1">div1</div>
        <div id="div2">div2</div>
        <div id="div3">div3</div>
    css:
        div{
            display: none;
            height: 50px;
            border: 1px solid black; 
        }
        div:target{
            display: block;
            background-color: pink;
        }
    
    思考题： 在页面第一次加载时，默认显示#div1
    解答： 可以用绝对定位，通过z-index来显示相应的区域
    css: 
    div {
        position: absolute;
        top: 30px;
        left: 0;
        height: 50px;
        border: 1px solid black;
        background-color: pink;
    }
    div:target{
        z-index: 2;
    }
    #div1{
        z-index: 1;
    }
```
### 5. 一些属性：
``` python
    E: disabled 不可点击的表单控件
    E: enabled 可点击的表单控件
    E: checked 已选中的checkbox或radio
    E: first-line E元素的第一行
    E: first-lettr E元素的第一个字符
    E::selection E元素在用户选中文字时
       注：不能加在body上，必须用两个冒号
    
    在css中语法书写规则及HTML表现：
        伪类
            伪类标准写法加两个冒号，如果没用，就写一个
        伪元素::
        
        E::after、E::before 一定要配合content使用
    
    E:not(s)E元素不被匹配(选择器匹配非指定元素)    
```