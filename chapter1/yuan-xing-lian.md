### 5. 原型链


**定义：**
* 原型：每个**函数对象**都有一个prototype属性，这个属性本身是一个对象，用来包含所有实例共享的属性和方法，被成为原型对象/原型。每个原型会有一个constructor对象，指向原型所在的函数。
* 原型链：每个**对象**都有一个[[Prototype]]属性，Chrome中可以使用`__proto__`访问，指向的是这个**对象的构造函数的原型**。当对象需要引用一个属性的时候，js引擎会首先在自身的属性表中查找，没有找到的话则在`__proto__`属性引用的对象属性表中继续查找，如此往复，直到找到或者`__proto__`指向null。这个引用链，就是原型链。

**作用：**
* 用来继承

**经典图：**
![](/assets/原型链.jpeg)
* 所有对象都继承自Object.prototype。
* Function继承Function本身，Function.prototype继承Object.prototype。
* Function.prototype和Function.`__proto__`都指向Function.prototype
* Object.prototype.__proto__ === null ，说明原型链到Object.prototype终止。* 

注意：重写原型对象会切断构造函数和最初原型链之间的联系，导致构造函数指向新的原型，而实例还指向老的原型。