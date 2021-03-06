# 分享


---

## Vue 的 所见所得


Note:
这几年ng，react，vue等mvvm框架的兴起，感觉前端圈也是异常的活跃，圈子里面时常都有各种撕逼大战，撕完语言撕框架。不过也挺好的，毕竟代表现在这个圈子很活跃。

---

### 学习途径

- [vue.js](https://cn.vuejs.org/v2/guide/join.html)
- [vue-router](https://router.vuejs.org/zh-cn/)
- [vuex](https://vuex.vuejs.org/zh-cn/getting-started.html)
- [新手向：Vue 2.0 的建议学习顺序](https://zhuanlan.zhihu.com/p/23134551)

Note:
因为尤大大，身份的缘故，我感觉也是一直在推上面几个文档的本地化，基本上保持中文文档和英文文档的同步。
本身文档就是很好的教程。

---

### MVC & MVP & MVVM

--

### MVC

![mvc](http://image.beekka.com/blog/2015/bg2015020105.png)

+ 视图（View）：用户界面。
+ 控制器（Controller）：业务逻辑
+ 模型（Model）：数据保存

Note:
View 传送指令到 Controller
Controller 完成业务逻辑后，要求 Model 改变状态
Model 将新的数据发送到 View，用户得到反馈

--

### MVP

![MVP](http://image.beekka.com/blog/2015/bg2015020109.png)

+ MVP 模式将 Controller 改名为 Presenter，同时改变了通信方向。

Note:
1. 各部分之间的通信，都是双向的。
2. View 与 Model 不发生联系，都通过 Presenter 传递。
3. View 非常薄，不部署任何业务逻辑，称为"被动视图"（Passive View），即没有任何主动性，而 Presenter非常厚，所有逻辑都部署在那里。

--

### MVVM

![MVVM](http://files.jb51.net/file_images/article/201703/201703231413069.png)

+ 双向绑定（data-binding），虚拟DOM


---
## vue 基本结构

![vue](http://ojr16of5n.bkt.clouddn.com/3E8006DD-724B-4351-A3EC-71AA3BFE75E7.png)

---

### 数据双向绑定

![data-binding](https://cn.vuejs.org/images/data.png)
state => DOM
+ getter、setter对属性进行劫持
+ 属性值改变是就会notify通知watch对象
+ 而watch对象则会notify到view上对应的位置进行更新
DOM => state
+ 输入数据时，也会触发订阅者watch
+ 更新最新的数据到data里面

Note:
Observer(),里面做了,劫持了vm.data所有属性的输入和输出(set和get),并为其每一个单独创建了一个data数据的通知者和data数据的订阅者列表
getter: 主要是添加订阅者,维护一个订阅者数组,return val
setter: view => model(输入而改变vm中的data数据), model => view(dep.notify()去遍历所有的订阅者,update数据,从而改变相关的文本节点数据)
遍历解析指定id的DOM树(documentFragment的使用, 虚拟DOM)
如果其中有v-model的元素节点, 就把vm上相应的data数据赋值给它,并且去除v-model(如果还是input输入框,就监听其keyup,并去触发vm.data的getter)
---

### 组件通讯
![组件通讯](https://ohc0m0ub0.qnssl.com/vue-event-bus-example.jpg)

+ 父组件 => 子组件
+ 子组件 => 父组件
+ 兄弟组件 => 兄弟组件

Note:
vue2.0之前父子组件通讯 $dispatch 和 $broadcast 
弃用之后采用props和，父组件绑定事件$on和$emit
新建一个中央事件总线（一个新的独自的只管理状态的Vue实例），$on, $emit
但是当项目规模变大之后，一个简单的中央事件总线就很难管理这么多状态了。

--

### Vuex

![vuex](https://vuex.vuejs.org/zh-cn/images/vuex.png)

集中式存储管理应用的所有组件的状态
相应的规则保证状态以一种可预测的方式发生变化

Note:
state: Vuex 使用 单一状态树 —— 是的，用一个对象就包含了全部的应用层级状态。至此它便作为一个『唯一数据源(SSOT)』而存在。这也意味着，每个应用将仅仅包含一个 store 实例。单一状态树让我们能够直接地定位任一特定的状态片段，在调试的过程中也能轻易地取得整个当前应用状态的快照。
mutation:更改 Vuex 的 store 中的状态的唯一方法是提交 mutation。
action:Action 类似于 mutation，不同在于：
Action 提交的是 mutation，而不是直接变更状态。
Action 可以包含任意异步操作。

---



## Vue ：更快更轻

1. 不用编译，可以直接导入
2. setter和getter数据响应更快
3. 它无法检测属性的添加和删除，需要借助改造原有js api
4. 模板，指令更加方便，易上手（模板容易出现难以注意到的运行时错误，同时也不易于测试，重构和分解）

Note:
vue的jsx并不好用

---

### ciaas 项目模板分析

- api
- component
- mock
- store
- view
- router.js

---

![book](http://www.ruanyifeng.com/images/hnp_cover_b.jpg)

如果自己就是潮水的一部分，怎么能看清潮流的方向呢？

Note:
讨论黑客成长、黑客对世界的贡献以及编程语言和黑客工作方法等所有对计算机时代感兴趣的人的一些话题。



