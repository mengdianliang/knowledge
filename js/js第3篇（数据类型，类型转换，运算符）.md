### 1. 数据类型
``` python
(1) 基本数据类型：
    字符串、数字、布尔
(2) 引用数据类型：
    对象(Array,function，Object)
(3) 特殊数据类型：
    null、undefined
```
### 2. 数据类型转换
``` python
注：转换过程中不会改变原值，而是产生新值
(1) 字符串类型： String
(2) 只要for执行不冲突。就可以用同一个循环变量
(3) 同时执行的for循环要区分循环变量，不是同时执行的就可以不用去分
eg: for(var i = 0;i < obj.length;i++){
    obj[i].onclick = function(){
        for(var i = 0;i < obj.length;i++) {
            obj[i].style.backgroundColor = '';
        }
    }
    this.style.backgroundColor='yellow';
}
```
### 3. 函数中的this
``` python
(1) this是指针；
(2) 每一个函数中this都指向调用这个函数的对象
注：
 1) this不能写在函数外；
 2) 凡是手动执行的函数，都是window调用
 3) 父元素和子元素添加相同的事件会出现冒泡
```
### 4. 获取索引值
``` python
获取点击事件的索引值
(1) for循环结束后的i是最终值
    i < dives.length(10) 当这个判断不成立的时候，i=10，最终值为10
(2) 所有for循环添加的事件里要做的事情，都是在for循环结束后才执行的
for(var i = 0;i < obj.length;i++){
    obj[i].index = i;
    obj[i].onclick = function() {
        console.log(this.index)
    }
}
```
### 5. 实例
``` python
eg: 选项卡：模拟单选框、模拟多选框
eg: 二级列表：手动执行的函数，定义的自定义属性，本身就可以理解成在最外层定义了；如果不是，我们定义相同的属性，也可以是公用的。
```
### 6. 执行效率
``` python
js中直接赋值比判断执行效率高，但判断可以提纯代码。
```
### 7. 星星评分
``` python
html: 
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title>评分</title>
    <!--重置样式-->
    <link rel="stylesheet" type="text/css" href="css/reset.css"/>
    <!--工具类样式-->
    <link rel="stylesheet" type="text/css" href="css/tools.css"/>
    <!--全局样式-->
    <link rel="stylesheet" type="text/css" href="css/global.css"/>
    <!--style页面样式-->
    <link rel="stylesheet" type="text/css" href="css/score.css"/>
    <!--style页面交互-->
    <!--<script type="text/javascript" src="exec/score.exec"></script>-->
    <script type="text/javascript" src="js/score2.js"></script>
</head>
<body>
    <section class="wrapper">
        <h3 class="tit">总体评价</h3>
        <div class="con clearfix">
            <ul class="star_list fl">

            </ul>
            <span class="score_val fl"></span>
        </div>
        <div class="info">小提示：点击星星就能打分</div>
    </section>
</body>
</html>

css：
body{
    background-color: #f1f1f1;
}
.wrapper{
    width: 300px;
    margin: 50px auto 0;
    background-color: #ffffff;
    border: 1px solid #ff0000;
}
.tit{
    height: 40px;
    line-height: 40px;
    text-align: center;
    font-size: 18px;
    font-weight: normal;
}
.con{
    padding: 20px 40px;
}
.star_list li{
    font-size: 20px;
    padding: 0 10px;
    width: 14px;
    color: #ffffff;
   text-shadow: 0 0 1px #333333;
    cursor: pointer;
}
.score_val{
    width: 50px;
    height: 26px;
    line-height: 26px;
    text-align: center;
    background-color: #ff0000;
    color: #ffffff;
   opacity: 0;
}
.info{
    height:50px;
    line-height: 50px;
    text-align: center;
    background-color: #ff0000;
    color: #ffffff;
    font-size: 14px;
}

js:
/**
 * Created by Administrator on 2017/7/16.
 */
/*
*  步骤：
*   1.获取节点；.pics img,.points li,.prev,.next
*   2.evlArr存储评价内容；
*   3.初始化页面；
*   4.添加鼠标移入移出事件；
*   5.添加鼠标点击事件；
*   6.完善鼠标移入移除事件；
*   7.优化代码(去重)；
* */
window.onload = function(){
    //获取节点
    var star_list = $('.star_list')[0];
    var score_val = $('.score_val')[0];
    var evlArr = ['极差','差评','一般','好评','极好'];
    var len = evlArr.length;
    var num = -1;
    init();
    //代码去重
    function commons(no){
        for(var j = 0; j < len;j++){
            if(j <= no){
                if(no <= 1){
                    $('li',star_list)[j].style.color = "#eeeeee";
                }else{
                    $('li',star_list)[j].style.color = "#ff0000";
                }
            }else{
                $('li',star_list)[j].style.color = "";
            }
        }
        score_val.innerHTML = evlArr[no];
    }
    //初始化页面
    function init(){
        addLi();
        mouseEvt();
    }
    /*添加li元素*/
    function addLi(){
        for(var i = 0;i < len;i++){
            star_list.innerHTML += '<li class="fl">★</li>';
        }
    }
    //元素获取方法的重写
    function $(element,obj){
        if(obj == null){
            return document.querySelectorAll(element);
        }else{
            return obj.querySelectorAll(element);
        }
    }
    function evt(index){
        $('li',star_list)[index].onmouseover = function(){
            commons(index);
            score_val.style.opacity = 1;
        };
        $('li',star_list)[index].onmouseout = function(){
            commons(num);
            if(num == -1){
                score_val.style.opacity = 0;
            }
        };
        $('li',star_list)[index].onclick = function(){
            if(num == -1 || num != index){  //这里可以做修改评价的效果
                num = index;
            }else{
                num = -1;
            }
        };
    }
    function mouseEvt(){
        for(var i = 0;i < len;i++){
            evt(i);
        }
    }
};
```
