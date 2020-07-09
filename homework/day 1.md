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

1.   执行用户设置的prepatch钩子函数

2.   判断新老节点是否相同，相同则直接返还，不相同则继续执行

3.   vnode如果定义了data，执行模块和用户设置的钩子函数

4.   对比新旧节点

    -  如果vnode.text未定义

		1. 如果新老子节点都有定义，对比新老子节点，不相同则更新子节点

		2. 如果新子节点有定义而老子节点未定义

            - 老节点有text，清空dom内容

            - 批量添加子节点

		3. 如果老子节点有定义，而新子节点未定义，批量移除子节点

		4. 如果老节点有text属性，清空dom内容

	- 如果定义了vnode.text且oldVnode.text不等于它

		1. 如果老节点有children，移除children，

		2. 设置textCOntent为vnode.text

5. 执行用户设置的postpatch钩子函数

