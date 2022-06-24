- [Vue中使用组件的三大步骤](#vue中使用组件的三大步骤)
- [如何定义一个组件？](#如何定义一个组件)
- [如何注册组件？](#如何注册组件)
- [编写组件标签](#编写组件标签)
- [几个注意的点](#几个注意的点)
- [关于VueComponent](#关于vuecomponent)

## Vue中使用组件的三大步骤

1. 定义组件（创建组件）

2. 注册组件

3. 使用组件（写组件标签

## 如何定义一个组件？

* 使用`Vue.extend(options)`创建，其中`options`和`new Vue(options)`时传入的那个`options`几乎一样，但也有点区别。

* 区别如下：

    1. el不用写，因为最终所有的组件都要经过一个vm的管理，由vm中的el决定服务哪个容器。

    2. data必须写成函数，因为为了避免组件被复用时，数据存在引用关系。

* 备注：使用template可以配置组件结构。

## 如何注册组件？

1. 局部注册：通过`new Vue`的时候传入components选项。

2. 全局注册：通过`Vue.component('组件名', 组件）`。

## 编写组件标签

`<组件名></组件名>` `<school></school>`

## 几个注意的点

1. 关于组件名

    * 一个单词组成：

        1. 第一种写法（首字母小写）：school

        2. 第二种写法（首字母大写）：School

    * 多个单词组成：

        1. 第一种写法（kebab-case命名）：my-school

        2. 第二种写法（CamelCase命名）：MySchool（需要Vue脚手架支持）

    * 备注：

        1. 组件名尽量回避HTML中已有的元素名称。

        2. 可以使用name配置项指定组件在开发者工具中呈现的名字。

2. 关于组件标签

    * 第一种写法：`<school></school>`

    * 第二种写法：`<school/>`

    * 备注：不使用脚手架时，`<school/>`会导致后续组件不能渲染。

3. 一个简写方式

`const school = Vue.extend(options)`可简写为`const school = options`

## 关于VueComponent

1. school组件本质是一个名为VueComponent的构造函数，且不是程序员定义的，是Vue.extend生成的。

2. 我们只需要写`<school/>`或`<school></school>`,Vue解析时会帮我们创建school组件的实例对象，即Vue帮我们执行：`new VueComponent(options)`。

3. 特别注意：每次调用Vue.extend，返回的都是一个全新的VueComponent！

4. 关于this的指向：

    * 在组件配置中：data函数、methods中的函数、watch中的函数、computed中的函数，它们的this均是【VueComponent实例对象】。

    * new Vue(options)配置中：data函数、methods中的函数、watch中的函数、computed中的函数，它们的this均是【Vue实例对象】。

5. VueComponent的实例对象，简称vc，也称为组件实例对象。Vue的实例对象，简称vm。

6. 一个重要的内置关系：`VueComponent.prototype.__proto__ === Vue.prototype`。

7. 为什么要有这个关系：让组件实例对象（vc）可以访问到Vue原型上的属性和方法。