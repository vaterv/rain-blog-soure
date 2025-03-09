---
title: java crash course 2.2笔记
date: 2025-03-09 15:46:15
tags:
categories: java

---
```
package org.example;

//TIP To <b>Run</b> code, press <shortcut actionId="Run"/> or
// click the <icon src="AllIcons.Actions.Execute"/> icon in the gutter.
public class Main {
    public static void main(String[] args) { //main方法是静态的是 因为直接使用此方法 而不用再去创建新对象见最后一点
//            TextBox textBox1 = new TextBox();
//        var textBox1 = new TextBox(); //var关键字 java编译器会根据等号右边的类型自动给变量赋上适合的类型，这种变量是静态的，一旦赋值不可修改，和js中的var是两个不同的东西
//        textBox1.setText("Box 1");
//        System.out.println(textBox1.text.toUpperCase());
//
//        var textBox2= new TextBox(); //var关键字 java编译器会根据等号右边的类型自动给变量赋上适合的类型，这种变量是静态的，一旦赋值不可修改，和js中的var是两个不同的东西
//        textBox2.setText("Box 2");
//        System.out.println(textBox2.text);


        /*2.内存分配

heap
stack
当运行完一个method java会自动删除储存在stack上的变量
同时java也会自己看 在heap上没有用的对象 没用就删除 这叫做gabage collection
* */

//        var textBox1 = new TextBox();//变量textBox1 正在引用在heap上的值，所以这些变量被称为引用类型，因为这些变量并不存储实际的值；而如果申明一个原始 类型int的变量，这个int是储存在stack中的，而此变量的值将会被储存在那个储存地址
//        var textBox2 = textBox1;//textBox2\textBox1都在引用同一个在heap上的对象，所以没有两个不同的对象，在heap上只有一个对象；而在stack上有两个对象是引用这个对象，正如式子所见，赋值只是把值给赋值到了textBox2；实际我们得到的是对象在heap上的地址
//        textBox2.setText("Hello world");//所以改变其中一个变量另外的变量也能看到这个改变
//        System.out.println(textBox1.text);


        /*
         *3.
         * */
//        如果功能变多 main method会变得很臃肿,这叫做程序性编程 -mosh
//        int baseSalary = 50_000;
//        int extraHours = 10;
//        int hourlyRate = 20;
//
//        int wage = calculateWage(baseSalary, extraHours, hourlyRate);
//        System.out.println(wage);
//    }
//
//    public static int calculateWage(int baseSalary, int extraHours, int hourlyRate) {
//        return baseSalary + (extraHours * hourlyRate);


        /*
         *  4.面向对象编程的规则
         *   (1).封装 encapsulation
         *
         * */
//        var employee =new Employee();
//        employee.baseSalary = 50_000;
//        employee.hourlyRate = 20;
//        int wage =employee.calculateWage(10);

//        var employee = new Employee();
//        employee.setBaseSalary(-1);
//        employee.setHourlyRate(20);
//        int wage = employee.calculateWage(10);


        //    使用intellij快速创建getter和setter
//    (2).抽象
//    a.coupling耦合
//        ex.1
//    var employee = new Employee();
//        employee.setBaseSalary(-1);
//        employee.setHourlyRate(20);
//    int wage = employee.calculateWage(10);// 以上四句话都和ｅｍｐｌｏｙｅｅ　ｃｌａｓｓ耦合了,一个class提供的方法越多，越有可能被其他类耦合
//employee.尽量减少暴露在class外的东西

//        ex.2
//        var browser = new Browser();
//        browser.navigate();

//        ex.3
//        var employee = new Employee(50_000);//构造函数用于构造或创建一个新的对象
//        employee.calculateWage(10);
//        int wage = employee.calculateWage();

//        b.重载构造函数
//        ctrl b 快速跳到函数
//        ctrl p 查看这个函数有哪些传参

//        c.静态字段和方法 static
//
//        Employee.
        var employee = new Employee(50_000);
            Employee.printNumberOfEmployees();
    }


}
```