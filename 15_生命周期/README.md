## 常用生命周期钩子

1. mounted：发送ajax请求、启动定时器、绑定自定义事件、订阅消息等【初始化工作】

2. beforeDestroy：消除定时器、解绑自定义事件、取消订阅消息等【收尾工作】

## 关于销毁Vue实例

1. 销毁后借助Vue开发者工具看不到任何信息。

2. 销毁后自定义事件会失效，但原生DOM事件依然有效。

3. 一般不会在beforeDestroy操作数据，因为即便操作数据，也不会再出发更新流程。