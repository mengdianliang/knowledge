### 1.引入
``` python
npm install vue-infinite-scroll --save
import infiniteScroll from 'vue-infinite-scroll'
Vue.use(infiniteScroll)
github网址：https://github.com/ElemeFE/vue-infinite-scroll
```
### 2.使用
``` python
<div v-infinite-scroll="loadMore" infinite-scroll-disabled="busy" infinite-scroll-distance="10">
  ...
</div>

var count = 0;

new Vue({
  el: '#app',
  data: {
    data: [],
    busy: false
  },
  methods: {
    loadMore: function() {
      this.busy = true;

      setTimeout(() => {
        for (var i = 0, j = 10; i < j; i++) {
          this.data.push({ name: count++ });
        }
        this.busy = false;
      }, 1000);
    }
  }
});
```
