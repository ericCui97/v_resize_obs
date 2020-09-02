
## 使用

* 在入口文件(比如：`main.js`)中引入并`use`
```
const VueResizeObserver = require("vue-resize-observer");
Vue.use(VueResizeObserver);
```

或者

```
import VueResizeObserver from "vue-resize-observer";
Vue.use(VueResizeObserver);
```

* 在组件元素中使用`v-resize`
```
<template>
  <div class="resize" v-resize="onResize">
    width: {{width}}, height: {{height}}
  </div>
</template>

<script>
export default {
  data() {
    return {
      width: 0,
      height: 0,
    }
  },
  mounted() {
    this.width = this.$el.offsetWidth;
    this.height = this.$el.offsetHeight;
  },
  methods: {
    onResize({ width, height }) {
      this.width = width;
      this.height = height;
    }
  }
}
</script>

<style>
.resize {
  background-color: orange;
  width: 300px;
  height: 300px;
  margin: 0 auto;
  resize: both;
  overflow: auto;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
```
## 预览 
``` bash
npm run dev
```