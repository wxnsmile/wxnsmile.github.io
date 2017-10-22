---
title: es6知识点总结
date: 2017-03-26 18:34:52
categories: 编程
tags:
---

### 子类的__proto__属性，表示构造函数的继承，总是指向父类。
（1）子类的__proto__属性，表示构造函数的继承，总是指向父类。

（2）子类prototype属性的__proto__属性，表示方法的继承，总是指向父类的prototype属性。

```javascript
class A {
}

class B extends A {
}

B.__proto__ === A // true
B.prototype.__proto__ === A.prototype // true
```
这两条继承链，可以这样理解：作为一个对象，子类（B）的原型（__proto__属性）是父类（A）；作为一个构造函数，子类（B）的原型（prototype属性）是父类的实例。

### super关键字
* super作为函数调用时，代表父类的构造函数。但是返回的是子类的实例

```javascript
class A {
  constructor() {
    console.log(new.target.name);
  }
}
class B extends A {
  constructor() {
    super();
  }
}
new A() // A
new B() // B
```
* super作为对象时，指向父类的原型对象,所以定义在父类实例上的方法或属性，是无法通过super调用的。

```javascript
class A {
  p() {
    return 2;
  }
}

class B extends A {
  constructor() {
    super();
    console.log(super.p()); // 2
  }
}

let b = new B();
```
ES6规定，通过super调用父类的方法时，super会绑定子类的this。

###实例的__proto__属性

子类实例的__proto__属性的__proto__属性，指向父类实例的__proto__属性。也就是说，子类的原型的原型，是父类的原型。

```javascript
var p1 = new Point(2, 3);
var p2 = new ColorPoint(2, 3, 'red');

p2.__proto__ === p1.__proto__ // false
p2.__proto__.__proto__ === p1.__proto__ // true
```






