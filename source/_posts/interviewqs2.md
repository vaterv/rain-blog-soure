---
title: JS题目
date: 2022-11-18 19:32:56
updated: 2022-11-18 19:32:56
categories: 面试
---

## 判断一个 js 变量 x 是不是数组的方法？

- 1.打印 变量 x.prototype.toString()
  如果打印为[object Array]，则 x 是数组
- 2.打印 变量 x.constructor==Array，如果打印为 true 则 x 是数组
- 3.打印 变量 x instanceof array 判断，如果打印为 true 则 x 是数组

## 请回答下列代码执行结果，并标出 console.log 的执行顺序。

```
(function a() {
  let i = 1;
  setTimeout(() => {
    i++;
    console.log(i);
  }, 0);
  new Promise((resolve) => {
    console.log(1);
    resolve(2);
  }).then(function (res) {
    setTimeout(() => {
      console.log(i + ~~!!i);
    }, 10);
    i = 3;
    console.log(res);
    console.log(i);
  });
})();//打印结果1，2，3，4，5
```

- 打印顺序

  - 1 console.log(1);
  - 2 console.log(res);
  - 3 console.log(i);
  - 4 console.log(i + ~~!!i);
  - 5 console.log(i);

### !!是转换成布尔值的意思，~~是取整的意思

一整个函数先执行 promise 异步运算.传 resolve 的情况， 那么 promise 下一步执行 then 方法 ,resolve 刚刚传了一个参数 2

3. jQuery 的美元符号$有什么作用？
    $只是”jQuery”的别名，它是 jQuery 的选择器
   也可以用 jQuery 来代替$，如下代码：
   jQuery(document).ready(function(){
   });

4. 请使用 jQuery 将页面上的所有元素边框设置为 2px 宽的虚线？

```
	<script language="javascript" type="text/javascript">

	$("*").css("border", "2px dotted red");

	</script>

```

5. body 中的 onload()函数和 jQuery 中的 document.ready()有什么区别？
   我们可以在页面中使用多个 document.ready()，但只能使用一次 onload()。

6. 选择器的 change 事件
   `$(".check").cahnge(function())`

7. 用 jquey 查看输入框是否被选中
   `$(".check").prop("checked",true)`

8. 实现一个全选中，其他也全选中

- props 可以改变输入框选择的属性
  `$(".check").prop("checked",$("this").prop("checked"))`
