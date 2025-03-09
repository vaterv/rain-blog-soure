#### 要创建一个表示“2019 年 5 月 23 日”的日期对象，可以使用以下代码：

`let someDate = new Date(Date.parse("May 23, 2019"))`

#### 正则表达式 RegExp

`var patt = /runoob/i`
/runoob/i 是一个正则表达式。

runoob 是一个正则表达式主体 (用于检索)。

i ：不区分大小写，表示在查找匹配时忽略 pattern 和字符串的大小写。

正则表达式参数可用在以上方法中 (替代字符串参数)。
正则表达式使得搜索功能更加强大(如实例中不区分大小写)。

```
var str = document.getElementById("demo").innerHTML;
var txt = str.replace(/microsoft/i,"Runoob");
```

#### URL 编码方法

有效的 URI 不能包含某些字符，比如空格。使用 URI 编码方法来编码 URI 可以让浏览器能够理解它们

````let uri = "http://www.wrox.com/illegal value.js#start";
console.log(encodeURI(uri));
// "http://www.wrox.com/illegal%20value.js#start"```
使用 encodeURI() 编码后，空格被替换为 %20

#### eval() 方法
它接收一个参数，即一个要执行的 ECMAScript（JavaScript）字符串,会将参数解释为实际的 ECMAScript 语句，然后将其插入到该位置。
通过 eval() 执行的代码属于该调用所在上下文，被执行的代码与该上下文拥有相同的作用域链。


eval("console.log('hi')");
等价：
console.log("hi");


#### Math
 Math 对象提供了一些辅助计算的属性和方法。
Math.SQRT1_2 //1/2的平方根
- min() 和 max() 方法
  用于确定一组数值中的最小值和最大值。这两个方法都接收任意多个参数，如
下面的例子所示：
```let max = Math.max(3, 54, 32, 16);
console.log(max); // 54```

- 舍入方法
  Math.ceil() 方法始终向上舍入为最接近的整数
  Math.round() 方法执行四舍五入
   ```console.log(Math.ceil(25.1)); // 26
      console.log(Math.round(25.5)); // 26
      console.log(Math.round(25.1)); // 25
````

random() 方法
let num = Math.floor(Math.random() \* 10 + 1);
方法返回一个 0~1 范围内的随机数，其中包含 0 但不包含 1
