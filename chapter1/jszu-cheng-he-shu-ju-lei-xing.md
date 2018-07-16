### 1. JS的组成

> 1. JS由什么组成

**组成：**
    * ECMAScript
    
ECMAScript是脚本语言的标准，提供核心语言功能。它规定了语言的语法，类型，语句，关键字，保留字，操作符和对象。JS是ECMAScript的一个实例。ES5诞生自2009年，ES6诞生自2015年。由于之后每一年都有新的ES标准诞生（ES2016, ES2017），所以官方开始以年份而不是序号命名。

需要注意的是，ECMA和浏览器并没有依赖关系，它不包含输入和输出定义。同时，ECMA是1997年为了规范和标准化JS，基于JS诞生的，但是JS又依赖于ECMA提供的标准。

    * 文档对象模型（DOM）

DOM提供了访问和操作网页内容的方法和接口。DOM把整个页面映射为一个多层节点结构。W3C制定DOM是为了防止微软和Netscape因为支持不同格式的DHTML导致的浏览器不兼容问题。所以我们可以看到IE之所以有那么多不兼容问题，实际上就是出于对话语权的不断渴求。

    * 浏览器对象模型（BOM）

BOM提供了与浏览器交互的方法和接口。尽管BOM只处理浏览器的接口与对象，但是人们习惯上也把针对浏览器的JS扩展作为BOM的一部分，诸如navigator对象，location对象、cookie对象和XHR。

### 2. JS的数据类型
> 1. JS的数据类型有哪些
2. 为什么要设定这些数据类型
3. 判断数据类型的方法
4. undefined和null的区别

* 基本数据类型：Undefined、Null、Boolean、Number、String、Symbol
* 引用数据类型：Object

![](/assets/2503287553-54202f79a6215_articlex.jpeg)

**基本数据类型与引用数据类型的区别**：
基本数据类型会保存在栈内存中，引用数据类型会保存在堆类型中，而引用类型的引用地址是存放在栈内存中的。栈内存与堆内存的区分与垃圾回收机制相关，这样可以使得程序运行时占用的内存最小。具体看内存相关章节。

基本数据类型的创建使用了一种特殊的引用类型——基本包装类型，例如`let str = 'Hello World';`用伪代码表示为`let str = new String('Hello World');`这也是为什么能对字符串调用方法的原因。基本包装类型与普通引用类型的主要区别是生命周期不同，它会在创建完字符串后立刻被销毁。

**数据类型的作用**：
    * 方便变量在计算机内存中的空间管理，提升运行效率
    * 提供了保护式的封装，可以在编译期查找缺陷，提高了程序的正确性
    * 可以帮助构建抽象数据类型和模块化，提供了软件开发工程化的基础
    * 方便人们理解并构建语言的语义模型

**如何判断数据类型**：
    * typeof：检测基本数据类型很棒，但是检测引用类型时只能区分object，undefined和function
    * instanceof：判断同一个全局作用域下，一个对象是否是某种对象的实例。会一直递归的查询到它的最终原型。不过因为基本数据类型没有父类型，全部会返回false。
    * Object.prototype.toString.call(value) == '[object Array]': 任何值上调用Object原生的toString方法，都会返回一个[object NativeConstructorName]格式的字符串。而这个构造函数名由每个类内部的[[Class]]属性指定。这样做没有全局作用域的问题。
    
**各数据类型知识点：**

* Number
![](/assets/849589-20171013113026887-1981568120.png)

JS使用的是64位双精度浮点数。因为指数为11位，所以数值范围为[2^1024-2^-1023]，对应`Number.MAX_VALUE-Number.MIN_VALUE`，但是因为数据精度的问题，精确的整数范围在（-2^53~2^53），对应着`Number.MAX_SAFE_INTEGER-Number.MIN_SAFE_INTEGER`。

因为二进制和十进制相互换算时可能会出现无限循环，所以JS存在精度丢失，例如`0.1 + 0.2 != 0.3`

**四舍五入方法：**
ceil，floor，round，toFixed，toPrecision

**数值转换：**
Number(value)，parseInt，parseFloat

* String

    * 字符操作：charAt，charCodeAt，fromCharCode
    * 字符串提取：substr，substring，slice
    * 位置索引：indexOf，lastIndexOf
    * 大小写转换：toLowerCase，toUpperCase
    * 模式匹配：match，search，replace，split
    * 其他操作：concat，trim，localeCompare

* Boolean
在JS中，所有类型的值都可以被转换为true或false。其中，空字符串，null，undefined，0和NaN是false。

* Undefined
Undefined表示一个变量最原始的状态，没有赋值的变量都是undefined。

* Null
Null表示一个对象被人为重置为空对象。所以`typeof null = 'object'`但是它本身并不是以Object为原型建立的，所以`null instanceof Object`是false。


* Symbol
表示独一无二的值，可以接收一个参数，用于区分 `let s = Symbol('test')`。Symbol作为属性名，只会被`Object.getOwnPropertySymnbols`方法返回，不会被`for...of`或`for...in`返回。

* Object
引用类型除了Object本身，还有Array，RegExp，Date，Function。

**对象拷贝：**
浅拷贝/一级拷贝：`Object.assign`，`[].concat`
深拷贝：Json序列化与反序列化，但是会忽略掉值为undefined的属性和函数表达式

**属性类型：**
属性类型包括数据属性和访问器属性两种，都需要通过`Object.defineProperty`来设置。这些内部特性都是用来实现JS引擎的，因此不能直接访问。

    * 数据属性
        * configurable：是否能删除属性或者修改为访问器属性
        * enumerable：能否通过for...in返回
        * writable：是否能修改
        * value
    
    * 访问器属性
        * configurable：是否能删除属性或者修改为数据属性
        * enumerable：能否通过for...in返回
        * Get：读取属性时调用的函数
        * Set：写入属性时调用的函数

















