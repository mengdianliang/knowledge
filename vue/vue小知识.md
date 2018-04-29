### 1.$emit()
```python
（1）如果子组件$emit给了父组件，如果父组件什么都不做的话，可以不用接受这个事件，即也什么都不用做。
（2）可以通过子组件来触发父组件里的自定义事件。
```
### 2.created()
```python
经常会在获取数据时，调用这个函数
```
### 3.v-html和v-text
```python
v-html可以用来处理一些特殊的符号，v-text只用来渲染文本(如果有标签，也只渲染文本)
```
### 4.Vue.set( target, key, value )
```python
{Object | Array} target
{string | number} key
{any} value
设置对象的属性。如果对象是响应式的，确保属性被创建后也是响应式的，同时触发视图更新。这个方法主要用于避开 Vue 不能检测属性被添加的限制。
```
### 5.计算属性的 setter
```python
computed: {
  fullName: {
    // getter
    get: function () {
      return this.firstName + ' ' + this.lastName
    },
    // setter
    set: function (newValue) {
      var names = newValue.split(' ')
      this.firstName = names[0]
      this.lastName = names[names.length - 1]
    }
  }
}
```
### 6.:class
```python
（1）一种写法：
    :class="classStr"
    classStr: {
        red-bg: true,
        blue-color: true
    }
    这样的话，可以同时渲染两个属性
（2）    
    :class="[activeClass, errorClass]"
    data: {
      activeClass: 'active',
      errorClass: 'text-danger'
    }
（3） :class="[{ active: isActive }, errorClass]"   
```
### 7.v-model .lazy, .number, .trim
```python
（1）在默认情况下，v-model 在每次 input 事件触发后将输入框的值与数据进行同步 (除了上述输入法组合文字时)。你可以添加 lazy 修饰符，从而转变为使用 change 事件进行同步：
（2） 如果想自动将用户的输入值转为数值类型，可以给 v-model 添加 number 修饰符：
（3） 如果要自动过滤用户输入的首尾空白字符，可以给 v-model 添加 trim 修饰符：  
```
### 8.v-on
```python
修饰符：

.stop - 调用 event.stopPropagation()。
.prevent - 调用 event.preventDefault()。
.capture - 添加事件侦听器时使用 capture 模式。
.self - 只当事件是从侦听器绑定的元素本身触发时才触发回调。
.{keyCode | keyAlias} - 只当事件是从特定键触发时才触发回调。
.native - 监听组件根元素的原生事件。
.once - 只触发一次回调。
.left - (2.2.0) 只当点击鼠标左键时触发。
.right - (2.2.0) 只当点击鼠标右键时触发。
.middle - (2.2.0) 只当点击鼠标中键时触发。
.passive - (2.3.0) 以 { passive: true } 模式添加侦听器
```
### 9.父子组件通信的方式
```python
（1）动态属性 props 父-->子
（2）$emit() 子-->父
（3）<slot></slot> 传递模板
```
### 10.挂载元素的方式
```python
（1）el: ''
（2）new Vue().$mounted('')
})
```
### 11.挂载元素的方式
```python
（1）el: ''
（2）new Vue().$mounted('')
})
```