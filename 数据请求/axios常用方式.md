### 1.引入
```python
npm i -S axios
import originJSONP from 'jsonp'
```
### 2.使用
```python
export function getGoodList (...args) {
  const url = '/api/goods/list'
  const data = args[0]
  return axios.get(url, {
    params: data
  }).then((res) => {
    // console.log(res)
    return Promise.resolve(res.data)
  }).catch(function (err) {
    console.log(err)
  })
}

export function addCartById (productId) {
  const url = '/api/goods/addCart'

  return axios.post(url, {
    productId: productId
  }).then((res) => {
    // console.log(res)
    return Promise.resolve(res.data)
  }).catch(function (err) {
    console.log(err)
  })
}
```