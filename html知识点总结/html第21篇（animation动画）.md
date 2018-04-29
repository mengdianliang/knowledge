### 1. keyframes
``` python
    @keyframes move {
        0% {
            transform: translateX(0px)
        }
        15% {
            transform: translateX(100px)
        }
        100% {
            transform: translateX(0px)
        }
    }
```
### 2. animation 
``` python
    (1) animation-name: 指定动画的名称
    (2) animation-duration：用来设置动画播放所需的时间
    (3) animation-timing-function：用来设置动画播放的速度曲线
    (4) animation-delay: 用来指定动画的延迟时间
    (5) animation-iteration-count: n/count 用来指定动画的播放次数
    (6) animation-direction: normal/alternate 用于指定动画的播放方向
    (7) animation-play-state:running（默认）/paused 用来控制动画的播放状态
    (8) animation-fill-mode: none/forwards/backforwards/both 用于设置动画的时间外属性
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
    trnasform-style 建立3d空间
    需要让哪个元素具备3d特性，那么就给谁添加；
    添加之后，当前元素以及子孙元素都具备3d特性
```