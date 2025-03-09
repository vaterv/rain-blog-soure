第 8 章对象、类与面向对象编程

### 属性分两种：数据属性和访问器属性

1. 数据属性
   数据属性包含一个保存数据值的位置。值会从这个位置读取，也会写入到这个位置。
   有 4 个特性描述它们的行为
   -  [[Configurable]]：表示属性是否可以通过 delete 删除并重新定义，
   - [[Value]]：包含属性实际的值。这就是前面提到的那个读取和写入属性值的位置。这个特性的默认值 undefined。

## 原型链

每个构造函数都有一个原型对象，原型有
一个属性指回构造函数，而实例有一个内部指针指向原型。如果原型是另一个类型的实例呢？那就意味
着这个原型本身有一个内部指针指向另一个原型，相应地另一个原型也有一个指针指向另一个构造函
数。这样就在实例和原型之间构造了一条原型链。这就是原型链的基本构想。

### 类

```
// 类声明
class Person {}
```

类构造函数
constructor 关键字用于在类定义块内部创建类的构造函数。方法名 constructor 会告诉解释器在使用 new 操作符创建类的新实例时，应该调用这个函数。

```
class Animal {}
class Person {
 constructor() {
 console.log('person ctor');
 }
}
class Vegetable {
 constructor() {
 this.color = 'orange';
 }
}
let a = new Animal();
let p = new Person(); // person ctor
let v = new Vegetable();
console.log(v.color); // orange
```

### 继承

ES6 类支持单继承。使用 extends 关键字

```
class Vehicle {}
// 继承类
class Bus extends Vehicle {}
let b = new Bus();
console.log(b instanceof Bus); // true
console.log(b instanceof Vehicle); // true
```
