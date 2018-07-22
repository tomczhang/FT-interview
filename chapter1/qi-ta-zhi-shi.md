### 1. 异步
* 异步的实现
* Promise

### 2. DOM
* 得到一个DOM节点的绝对位置

### 3. 闭包
突破作用域链

### 4. 请求方式
1. XHR/fetch/Axios
2. 手写ajax/jsonp

### 5. js的内存控制和泄漏/垃圾回收

### 6. 设计模式
单例/订阅者/观察者/工厂

### 7. 安全性
1. 同源/跨域/为什么危险
2. 

### 8. 模块化

### 9. ES6的新特性

Object.is()

### 10. arguments
arguments是一个类数组，除了length之外没有数组的其他方法。每个js函数都有这样一个参数，用来表征传给这个函数的参数列表。

严格模式下arguments和参数的值不会保持统一，混杂模式下则会保持统一。
ES6的参数默认赋值对于argumengts没有影响。

将arguments转为数组：
* Array.prototype.slice.call(arguments）
* Array.from(arguments)

### 11. apply/call

js中使用apply/call来改变函数运行时的上下文。

区别：使用时除了要传作用域以外，call还要传具体数量的参数，apply则可以使用arguments。









