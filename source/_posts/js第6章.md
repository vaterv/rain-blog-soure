### 第 6 章

#### 创建 Object

显式地创建 Object 的实例有两种方式。

1. 使用 new 操作符， Object 构造函数

````let person = new Object();
person.name = "Nicholas";```
2. 对象字面量（object literal）[字面意思]
```let person = {
"name": "Nicholas",
"age": 29
};```

#### 创建数组
1. 使用 Array 构造函数，比如：let colors = new Array();
2. 数组字面量（array literal）表示法
let colors = ["red", "blue", "green"]; // 创建一个包含 3 个元素的数组
Array.from() 的第一个参数是一个类数组对象
```// 字符串会被拆分为单字符数组
console.log(Array.from("Matt")); // ["M", "a", "t", "t"]```
判断一个对象是不是数组。:
```if (value instanceof Array){
// 操作数组
}```

 Array.isArray() 方法
```if (Array.isArray(value)){
// 操作数组
}```

 fill() 方法可以向数组填充指定的值
 ```const zeroes = [0, 0, 0, 0, 0];
// 用 5 填充整个数组
zeroes.fill(5);
console.log(zeroes); // [5, 5, 5, 5, 5]
zeroes.fill(0); // 重置```

 toString() 方法，以得到最终的字符串
```let colors = ["red", "blue", "green"]; // 创建一个包含 3 个字符串的数组
alert(colors.toString()); // red,blue,green```

- ECMAScript 数组提供了 push() 和 pop() 方法，以实现类似栈的行为。
push() 方法接收任意数量的参数，并将它们添加到数组末尾，返回数组的最新长度。
 pop() 方法则
用于删除数组的最后一项，同时减少数组的 length 值，返回被删除的项。来看下面的例子：
```let colors = new Array(); // 创建一个数组
let count = colors.push("red", "green"); // 推入两项
alert(count); // 2
count = colors.push("black"); // 再推入一项
alert(count); // 3
let item = colors.pop(); // 取得最后一项
alert(item); // black```
- 队列方法
就像栈是以 LIFO 形式限制访问的数据结构一样，队列以先进先出（FIFO，First-In-First-Out）形式
限制访问。
shift() ，它会删除数
组的第一项并返回它，然后数组长度减 1。
````

let count = colors.push("red", "green"); // 推入两项
alert(count); // 2
count = colors.push("black"); // 再推入一项
alert(count); // 3
let item = colors.shift(); // 取得第一项
alert(item); // red

````
indexOf() 和 lastIndexOf() 都返回要查找的元素在数组中的位置，如果没找到则返回1。
```let numbers = [1, 2, 3, 4, 5, 4, 3, 2, 1];
alert(numbers.indexOf(4)); // 3
alert(numbers.lastIndexOf(4)); // 5
````

- 迭代方法

````let numbers = [1, 2, 3, 4, 5, 4, 3, 2, 1];
let filterResult = numbers.filter((item, index, array) => item > 2);
alert(filterResult); // 3,4,5,4,3```
 map方法非常适合创建一个与原
始数组元素一一对应的新数组。
```let numbers = [1, 2, 3, 4, 5, 4, 3, 2, 1];
let mapResult = numbers.map((item, index, array) => item * 2);
alert(mapResult); // 2,4,6,8,10,8,6,4,2
````

- 归并方法
  这两个方法都会迭代数
  组的所有项，并在此基础上构建一个最终返回值。

可以使用 reduce() 函数执行累加数组中所有数值的操作，比如：

```
let values = [1, 2, 3, 4, 5];
let sum = values.reduce((prev, cur, index, array) => prev + cur);
alert(sum); // 15
```

- webGl
  有了它，开发者就能够编写涉及复杂图形的应用程序

#### Map

与 Object 只能使用数值、字符串或符号作为键不同， Map 可以使用任何 JavaScript 数据类型作为
键。
使用 new 关键字和 Map 构造函数可以创建一个空映射：
const m = new Map();

```
/ 使用嵌套数组初始化映射
const m1 = new Map([
["key1", "val1"],
["key2", "val2"],
["key3", "val3"]
]);
alert(m1.size); // 3
```

初始化之后，可以使用 set() 方法再添加键/值对。

```
const m = new Map().set("key1", "val1");
m.set("key2", "val2")
.set("key3", "val3");
alert(m.size); // 3
```

```
const m = new Map();
const symbolKey = Symbol();

m.set(symbolKey, "symbolValue");
alert(m.get(symbolKey)); // symbolValue
```

从大型 Object 和 Map 中查找键/值对的性能差异极小，但如果只包含少量键/值对，
则 Object 有时候速度更快。

##### Set

ECMAScript 6 新增的 Set 是一种新集合类型，为这门语言带来集合数据结构
使用 new 关键字和 Set 构造函数可以创建一个空集合：
const m = new Set();

```
// 使用数组初始化集合
const s1 = new Set(["val1", "val2", "val3"]);
alert(s1.size); // 3
```

初始化之后，可以使用 add() 增加值，使用 has() 查询，通过 size 取得元素数量，以及使用 delete()
和 clear() 删除元素：

```
const s = new Set();
alert(s.has("Matt")); // false
alert(s.size); // 0
s.add("Matt")
.add("Frisbie");
```
