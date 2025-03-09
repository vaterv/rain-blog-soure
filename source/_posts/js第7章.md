### 第 7 章

迭代的英文“iteration”源自拉丁文 itero，意思是“重复”或“再来”。一遍又一遍来

最简单的迭代

```for (let i = 1; i <= 10; ++i) {
 console.log(i);
}
```

set
设置, 集, 组, 设定, 集合, 一套
检查是否存在默认迭代器属性

````let str = 'abc'; // 这些类型都实现了迭代器工厂函数
console.log(str[Symbol.iterator]); // f values() { [native code] } ```
任何实现 Iterable接口的对象都有一个 Symbol.iterator 属性


// 数组解构
// 扩展操作符
let arr2 = [...arr];
console.log(arr2); // ['foo', 'bar', 'baz']

#### 生成器
生成器的形式是一个函数，函数名称前面加一个星号（*）表示它是一个生成器。只要是可以定义
函数的地方，就可以定义生成器。
````

// 生成器函数声明
function* generatorFn() {}
// 生成器函数表达式
let generatorFn = function* () {}

```
调用生成器函数会产生一个生成器对象。生成器对象一开始处于暂停执行（suspended）的状态。与
迭代器相似，生成器对象也实现了 Iterator 接口，因此具有 next()方法。调用这个方法会让生成器
开始或恢复执行
```

function\* generatorFn() {}
const g = generatorFn();
console.log(g); // generatorFn {<suspended>}
console.log(g.next); // f next() { [native code] }

```
#### 通过 yield 中断执行
yield 关键字可以让生成器停止和开始执行，生成器函数在遇到 yield
关键字之前会正常执行。遇到这个关键字后，执行会停止，函数作用域的状态会被保留。停止执行的生
成器函数只能通过在生成器对象上调用 next()方法来恢复执行：
```

function\* generatorFn() {
yield;
}
let generatorObject = generatorFn();
console.log(generatorObject.next()); // { done: false, value: undefined }
console.log(generatorObject.next()); // { done: true, value: undefined }

```

```
