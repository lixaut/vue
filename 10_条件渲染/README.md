## 用法

使用`v-show`做条件渲染。

```
<h1 v-show="false">hello world</h1>
<h1 v-show="1 === 1">hello world</h1>
```

使用`v-if`做条件渲染。

```
<h1 v-if="false">hello world</h1>
<h1 v-if="1 === 1">hello world</h1>
```

使用`v-else`和`v-else-if`。

```
<div v-if="n === 1">Angular</div>
<div v-else-if="n === 2">React</div>
<div v-else-if="n === 3">Vue</div>
<div v-else>hello world</div>
```

`v-if`与`template`的配合使用。

```
<template v-if="n === 1">
    <h1>hello</h1>
    <h1>world</h1>
    <h1>hi</h1>
</template>
```
## 总结

### 1. v-if

写法：

* `v-if="表达式"`
* `v-else-if="表达式"`
* `v-else="表达式"`

适用于：切换频率较低的场景。
特点：不展示的 DOM 元素直接被删除。
注意：`v-if`可以和`v-else-if`、`v-else`一起使用，但要求结构不能被“打断”。

### 2. v-show

写法：

* `v-show="表达式"`

适用于：切换频率较高的场景。
特点：不展示的 DOM 元素未被移除，仅仅是使用样式隐藏掉。

### 3. 备注

使用`v-if`的时候，元素可能无法获取到，而使用`v-show`一定可以获取到。
