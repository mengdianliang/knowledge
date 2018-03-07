### 1. 表格标签
``` python
   table
   thead
   tbody
   tr
   th
   td
   
   table,th,td可以设置border
   thead,tbody,tr无法设置border
```
### 2.表格样式重置：
``` python
(1) 单元格间隙合并：
    table{border-collapse: collapse;}
(2) 重置单元格： 
    th,td{padding: 0;}
(3) 表头文字默认居中，
    主题文字默认居左
(4) 例子：
    table,th,td{border: 1px solid red;}
    colspan,rowspan
```
### 3.表单
``` python
    form表单：
        action用于提交地址
        method用于提交类型
        1) get
        2) post
```
### 4. label
``` python
    为某个元素的标注，
    for某个表单元素的id
```
### 5.表单元素专属属性
``` python
    1) checked 在页面加载时，默认选定的input元素
    2) disabled 规定金庸的input元素，适用于所有类型的表单控件
    3) autofocus 加载页面时，自动获取焦点；
    适用于输入类型的控件
    
```
### 5.元素大小
``` python
    input： text/password = width/height + 边框(大小不包括边框)
    select 大小包括边框
    input: submit/reset/button 大小包括边框
```
