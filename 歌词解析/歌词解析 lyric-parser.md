### 安装与引入
```python
npm install -S lyric-parser
import Lyric from 'lyric-parser'
```
### 使用
```python
let lyric = new Lyric(lyricStr, handler)

 function hanlder({lineNum, txt}){
   // this hanlder called when lineNum change
 }
```
### 一些方法
```python
play()
play the lyric

stop()
stop play

seek(startTime)
seek to correspond starTime

togglePlay()
toggle play state
```
