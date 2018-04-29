### 安装与引入
``` python
npm install good-storage
import storage from 'good-storage'
github网址：https://github.com/ustbhuangyi/storage
```

### 使用
``` python
set(key, val)
set storage with key and val

get(key, def)
get storage with key, return def if not find

remove(key)
remove storage with key

has(key)
determine storage has the key

clear()
clear all storages

getAll()
get all the storages

forEach(callback)
forEach the storages and call the callback function with each storage
```