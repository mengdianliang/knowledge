### 1. 移动设备上开发环境及工具
``` python
    (1) chrome移动端开发工具：
     1) 主流设备选择
     2) 通过设备选择下方的横条进行调整自定义尺寸(也可以手动输入)
     3) 界面缩放比例调整(最好在100%的情况下进行预览)
     
     注意事项：
     1) 当切换设备或切换状态时，一定要刷新；
     2) 当调试工具发现有问题时，先确认甄姬是否存在同一个问题，一切效果以真机为主。
```
### 2. 本地虚拟服务器(相当于不同设备间访问的桥梁)
``` python
    1) PC/移动端必须处于同一个网络
    2) 使用pc的ipv4网址代替127.0.0.1
    3) 电脑替换ip地址后测试是否可以访问
    4) 手机完整输入对应地址
    5) 如果还访问不了，检查第三步，尝试关闭PC防火墙
```
### 3. 移动设备
``` python
    <meta name="viewport" content=""/>
    width: 设备宽度 [pixel-value|device-wdith]
    user-scable是否允许缩放
    initial-scale初始比例
    minimum-scale 允许缩放的最小比例
    maximum-scale 允许缩放的最大比例
    
    var dpr = 1 / window.devicePixelRatio;
			
		console.log(dpr);
		
		document.write('<meta name="viewport" content="width=device-width,user-scalable=no,initial-scale='+ dpr +',minimum-scale='+ dpr +',maximum-scale='+ dpr +'" />')
```