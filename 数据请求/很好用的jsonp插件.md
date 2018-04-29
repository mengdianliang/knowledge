### 1.引入
```python
npm i -S jsonp
import originJSONP from 'jsonp'
github网址：https://github.com/webmodules/jsonp
```
### 2.封装
```python
export default function jsonp(url, data, option) {
  url += (url.indexOf('?') < 0 ? '?' : '&') + param(data)
  return new Promise((resolve, reject) => {
    originJSONP(url, option, (err, data) => {
      if (!err) {
        resolve(data)
      } else {
        reject(err)
      }
    })
  })
}

function param(data) {
  let url = ''
  for (let k in data) {
    let value = data[k] !== undefined ? data[k] : ''
    url += `&${k}=${encodeURIComponent(value)}`
  }
  return url ? url.substring(1) : ''
}
```
### 3.使用
```python
import jsonp from 'common/js/jsonp'

export function getRecommend() {
  const url = 'https://shc.y.qq.com/musichall/fcgi-bin/fcg_yqqhomepagerecommend.fcg'
  const options = {
    param: 'jsonpCallback'
  }
  const data = {
    g_tk: 5381,
    inCharset: 'utf-8',
    outCharset: 'utf-8',
    notice: 0,
    format: 'jsonp',
    platform: 'h5',
    uin: 0,
    needNewCode: 1,
    _: 1515922621811
  }
  return jsonp(url, data, options)
}
```
