### 4. 严格模式
> 1. 严格模式的好处

在脚本或函数开头添加`'use strict'；`严格模式禁止了JS代码中一些不严谨的行为，提供了更加严格的标准。

ES6自动采用严格模式。

包括不限于：禁止使用未声明变量，定义了一些新的关键字，禁止this指向全局变量，不允许删除禁止删除的变量，不允许使用eval, with, arguments.caller/callee

**好处**：
    * 提升了代码安全
    * 提高了编译效率
    * 为未来的JS代码做好了铺垫

### 5. arguments
arguments是一个类数组，除了length之外没有数组的其他方法。每个js函数都有这样一个参数，用来表征传给这个函数的参数列表。

严格模式下arguments和参数的值不会保持统一，混杂模式下则会保持统一。
ES6的参数默认赋值对于argumengts没有影响。

将arguments转为数组：
* Array.prototype.slice.call(arguments）
* Array.from(arguments)

arguments.callee 我是谁   严格模式下不能使用
arguments.caller 谁调我




















