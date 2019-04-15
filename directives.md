# 自定义指令

## 注册自定义指令

```bash
// 注册一个全局自定义指令 `v-focus`
Vue.directive('focus', {
  // 当被绑定的元素插入到 DOM 中时……
  inserted: function (el) {
    // 聚焦元素
    el.focus()
  }
})

// 局部注册
directives: {
  focus: {
    // 指令的定义
    inserted: function (el) {
      el.focus()
    }
  }
}
```

## 钩子函数

* bind

* inserted

* update

* componentUpdated

* unbind

## 钩子函数参数

* el (只有它是可修改的，其他都是只读的)
* binding
  - name 
  - value
  - oldValue
  - expression
  - arg 
  - modifiers
* vnode
* oldVnode

## 函数间简写

```bash
Vue.directive('color-swatch', function (el, binding) {
  el.style.backgroundColor = binding.value
})
```
## 对象字面量

```bash
<div v-demo="{ color: 'white', text: 'hello!' }"></div>

Vue.directive('demo', function (el, binding) {
  console.log(binding.value.color) // => "white"
  console.log(binding.value.text)  // => "hello!"
})
```



