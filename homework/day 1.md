# Day 1

### 1、下面关于虚拟 DOM 的说法正确的是：

- A. 使用虚拟 DOM 不需要手动操作 DOM，可以极大的提高程序的性能。
- B. 使用虚拟 DOM 不需要手动操作 DOM，可以极大的提高开发效率。
- C. 虚拟 DOM 可以维护程序的状态，通过对比两次状态的差异更新真实 DOM。
- D. 虚拟 DOM 本质上是 JavaScript 对象，可以跨平台，例如服务器渲染、Weex 开发等。



## 回答： D

### 2、下面关于 Snabbdom 库的描述错误的是：

- A. Snabbdom 库是一个高效的虚拟 DOM 库，Vue.js 的虚拟 DOM 借鉴了 Snabbdom 库。
- B. 使用 h() 函数创建 VNode 对象，描述真实 DOM 结构。
- C. Snabbdom 库本身可以处理 DOM 的属性、事件、样式等操作。
- D. 使用 patch(oldVnode, null) 可以清空页面元素



## 回答：D



## 简答题

### 1、请简述 patchVnode 函数的执行过程。

#### 答：

1.	执行用户设置的prepatch钩子函数

2.	查看是否是同一个节点、是否是注释节点、是否是异步函数组件、是否是静态节点，是否是 once 的节点，是的话，不执行，不相同则继续执行

3.	是否存在子节点，然后新老节点的子节点是否相同，否就执行 updateChildren 函数深入对比

4.	否则就查看新老节点是否存在，新节点存在但是老节点不存在，增加，新节点不存在但是老节点存在，删除

5.	检查 新老节点的 text 属性是否一致，否的话，就更新
