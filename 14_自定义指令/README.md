## 自定义指令总结

1. 定义语法

    * 局部指令

        * new Vue({ directives: { 指令名: 配置对象 } })

        * new Vue({ directives() {} })

    * 全局指令

        * Vue.directive(指令名, 配置对象)

        * Vue.directive(指令名, 回调函数)

2. 配置对象常用的3个回调

    * bind - 指令与元素成功绑定时调用。

    * inserted - 指令所在元素被插入页面时调用。

    * update - 指令所在模版被重新解析时调用。

3. 备注

    * 指令定义时不加 v- ，但使用时要加 v- 。

    * 指令名如果是多个单词，要使用kebab-case命名方式，不要用camelCase命名。