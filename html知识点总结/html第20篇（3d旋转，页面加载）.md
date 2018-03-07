### 1. 页面加载
``` python
    window.onload
    window.onreadystatechange
```
### 2. transform
``` python
    (1) translate(x,y)
        translate3d(x,y,z)
        translateX(x)
        translateY(y)
        translateZ(z)
    (2) scale(x[,y])
        scale3d(x,y,z)
        scaleX(x)
        scaleY(y)
        scaleZ(z)
    (3) rotate(angle)
        rotate3d(x,y,z,angle)
        rotateX(angle)
        rotateY(angle)
        rotateZ(angle)
    (4) skew(x-angle,y-angle)
        skewX(angle)
        skewY(angle)
```
### 3. 景深
``` python
    perspective 景深(近大远小)--父级
    perspective-origin: 景深基点
```
### 4. 3d空间
``` python
    trnasform-style 建立3d空间
    需要让哪个元素具备3d特性，那么就给谁添加；
    添加之后，当前元素以及子孙元素都具备3d特性
```
### 5. 3d筛子
``` python
    <style>
		@keyframes move{
			0%{
				transform: rotateX(0) rotateY(0) rotateZ(0);
			}
			20%{
				transform: rotateX(360deg) rotateY(0) rotateZ(0);
			}
			40%{
				transform: rotateX(360deg) rotateY(360deg) rotateZ(0);
			}
			60%{
				transform: rotateX(360deg) rotateY(360deg) rotateZ(360deg);
			}
			80%{
				transform: rotateX(720deg) rotateY(720deg) rotateZ(720deg);
			}
			100%{
				transform: rotateX(0) rotateY(0) rotateZ(0);
			}
		}
			.box{
				width: 200px;
				height: 200px;
				padding: 200px;
				border: 10px solid black;
				perspective:800px;
			}
			ul{
				margin: 0;
				padding: 0;
				list-style: none;
				position: relative;
				/*transition: 5s;*/
				width: 200px;
				height: 200px;
				transform-style: preserve-3d;
				transform-origin: center center -100px;
				animation: move 10s infinite;
			}
			li{
				position: absolute;
				width: 160px;
				height: 160px;
				text-align: center;
				color: #fff;
				font: 68px/200px "宋体";
				background-color: #EB3D00;
				padding: 20px;
			}
			ul li:nth-of-type(1) {
				left: 0;
				top: -200px;
				transform: rotateX(90deg);
				transform-origin: left bottom;
			}
			ul li:nth-of-type(2) {
				left: -200px;
				top: 0px;
				transform: rotateY(-90deg);
				transform-origin: right bottom;
			}
			ul li:nth-of-type(3) {
				left: 0px;
				top: 0px;
				transform: translateZ(-200px);
			}
			ul li:nth-of-type(4) {
				left: 200px;
				top: 0px;
				transform: rotateY(90deg);
				transform-origin: left bottom;
			}
			ul li:nth-of-type(5) {
				left: 0px;
				top: 200px;
				transform: rotateX(-90deg);
				transform-origin: left top;
			}
			ul li:nth-of-type(6){
				left: 0;
				top: 0;
			}
			/*.box:hover ul{
				transform: rotateY(720deg) rotateX(720deg);
			}*/
			.point_wrapper{
				background-color: #fff;
				width: 160px;
				height: 160px;
				border-radius: 10px;
				backface-visibility: hidden;  /*之所以加在这里，因为内容透过去了，li并没有透*/
			}
			.point{
				display: block;
				width: 40px;
				height: 40px;
				background-color: #EB3D00;
				border-radius: 25px;
				box-shadow: 1px 1px 3px #000000;
			}
			.point1{
				width: 50px;
				height: 50px;
				transform: translateX(55px) translateY(55px);
			}
			.point2:nth-child(1){
				transform: translateX(100px) translateY(20px);
			}
			.point2:nth-child(2){
				transform: translateX(20px) translateY(60px);
			}
			.point3:nth-child(1){
				transform: translateX(100px) translateY(20px);
			}
			.point3:nth-child(2){
				transform: translateX(60px) translateY(20px);
			}
			.point3:nth-child(3){
				transform: translateX(20px) translateY(20px);
			}
			.point4:nth-child(1){
				transform: translateX(20px) translateY(20px);
			}
			.point4:nth-child(2){
				transform: translateX(100px) translateY(-20px);
			}
			.point4:nth-child(3){
				transform: translateX(20px) translateY(20px);
			}
			.point4:nth-child(4){
				transform: translateX(100px) translateY(-20px);
			}
			.point5:nth-child(1){
				transform: translateX(15px) translateY(15px);
			}
			.point5:nth-child(2){
				transform: translateX(105px) translateY(-25px);
			}
			.point5:nth-child(3){
				transform: translateX(60px) translateY(-20px);
			}
			.point5:nth-child(4){
				transform: translateX(15px) translateY(-15px);
			}
			.point5:nth-child(5){
				transform: translateX(105px) translateY(-55px);
			}
			.point6:nth-child(1){
				transform: translateX(15px) translateY(15px);
			}
			.point6:nth-child(2){
				transform: translateX(105px) translateY(-25px);
			}
			.point6:nth-child(3){
				transform: translateX(15px) translateY(-20px);
			}
			.point6:nth-child(4){
				transform: translateX(105px) translateY(-60px);
			}
			.point6:nth-child(5){
				transform: translateX(15px) translateY(-55px);
			}
			.point6:nth-child(6){
				transform: translateX(105px) translateY(-95px);
			}
		</style>
	</head>
	<body>
		<div class="box">
			<ul>
				<li>
					<div class="point_wrapper">
						<span class="point point1"></span>
					</div>	
				</li>
				<li>
					<div class="point_wrapper">
						<span class="point point2"></span>
						<span class="point point2"></span>
					</div>
				</li>
				<li>
					<div class="point_wrapper">	
						<span class="point point3"></span>
						<span class="point point3"></span>
						<span class="point point3"></span>
					</div>
				</li>
				<li>
					<div class="point_wrapper">
						<span class="point point4"></span>
						<span class="point point4"></span>
						<span class="point point4"></span>
						<span class="point point4"></span>
					</div>	
				</li>
				<li>
					<div class="point_wrapper">
						<span class="point point5"></span>
						<span class="point point5"></span>
						<span class="point point5"></span>
						<span class="point point5"></span>
						<span class="point point5"></span>
					</div>	
				</li>
				<li>
				    <div class="point_wrapper">
						<span class="point point6"></span>
						<span class="point point6"></span>
						<span class="point point6"></span>
						<span class="point point6"></span>
						<span class="point point6"></span>
						<span class="point point6"></span>
					</div>	
				</li>
			</ul>
		</div>
	</body>
</html>

```