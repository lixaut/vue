## 收集表单数据

1. 若`<input type="text" />`，则`v-model`收集的是value值，用户输入的就是value值。

2. 若`<input type="radio" />`，则`v-model`收集的是value值，且要给标签配置value值。

3. 若`<input type="checkbox" />`

    * 没有配置input的value属性，那么收集的就是checked（勾选 or 不勾选，是布尔值）。

    * 配置input的value属性：

        * `v-model`的初始值是非数组，那么收集的就是checked（勾选 or 不勾选，是布尔值）。

        * `v-model`的初始值是数组，那么收集的就是value组成的数组。

4. `v-model`的三个修饰符：

   * `lazy`失去焦点再收集数据。

   * `number`输入字符串转为有效的数字。

   * `trim`输入收尾空格过滤。