---
title: java crash course 2.4笔记
date: 2025-03-09 15:52:28
tags:
categories: java

---

>example
>├─ CheckBox.java
>├─ Main.java
>├─ Point.java
>├─ TextBox.java
>└─ UIControl.java

1. CheckBox.java
```
package org.example;

//public abstract class CheckBox extends UIControl{//因为extends了ui control 这个render方法 要不就要实现 要不就要也声明为abstract
////    @Override
////    public void render() {//这个render方法 要不就要实现 要不就要也声明为abstract
////        System.out.println("render checkbox");
////    }
//}
public final class CheckBox extends UIControl{//因为extends了ui control 这个render方法 要不就要实现 要不就要也声明为abstract
    @Override
    public void render() {//这个render方法 要不就要实现 要不就要也声明为abstract
        System.out.println("render checkbox");
    }


}

//public class MyCheckBox extends CheckBox{}
//public class MyCheckBox extends String{}//String class是不可继承的
```

2. Main.java
```

package org.example;
//package org.codewithme;

//import org.example.UIControl;

//TIP To <b>Run</b> code, press <shortcut actionId="Run"/> or
// click the <icon src="AllIcons.Actions.Execute"/> icon in the gutter.
public class Main {
    public static void main(String[] args) {
// var control = new TextBox();
// control.
//        control.disable();
//        System.out.println(control.isEnabled());
//        var obj = new Object();
//        obj.

//        var box1 = new TextBox();
//        var box2 =box1;
//        System.out.println(box1.hashCode());
//        System.out.println(box2.hashCode());//这个对象的地址的哈希值
//        System.out.println(box1.equals(box2));

//        var box1 = new TextBox();
//        var box2 =new TextBox();
//        System.out.println(box1.equals(box2));
//        System.out.println(box1.toString());

//        2.不想重复编码 使用inheritance

//      3.  访问修饰符
//        public成员可以在class外被访问 而private不能
//
        var textBox = new TextBox();
//        new UIControl(true).is
//        protected 修饰的变量在这个包里是公共的

//        4.方法重写 overriding 重写继承至父类的方法
//        方法重构 overloading ,同一个名字的方法 传参不一样
//        var textBox = new TextBox();
//        textBox.setText("hello world");
//        System.out.println(textBox);//不用显示调用textBox.toString()，因为printline方法自动会调用，任何传到这个括号里的对象 的toString()方法

//        System.out.println(textBox.toString());

//        5.upcasting和downcasting

//        var control = new UIControl(true);
//        var textBox = new TextBox();
//        show(textBox);//TextBox class中继承了uI ctrolclas

//        6.比较两个对象
//var point1 = new Point(1,2);
//var point2 = new Point(1,2);
//        System.out.println(point1==point2);//point1和point2都是引用类型，这俩东西储存的是point对象在内存中的地址，这是两个不同的对象 所以这两个变量中有不同的值
////        System.out.println(point1.equals(point2));
////        System.out.println(point1.equals(textBox));
////        System.out.println(point1.equals(point1));
//        System.out.println(point1.hashCode());
//        System.out.println(point2.hashCode());

//
//        7.面向编程的第四个特点 多态
//UIControl[] controls = {new TextBox(),new CheckBox()};
//for (var control : controls){//for (元素类型 变量名 : 集合或数组)
//    control.render();//多态的体现 每个类都有自己各自的render方法 而不是在主方法里写 fat if else语句
//}

//  8.抽象类和方法

//       a.
//        var uiControl = new UIControl();

//        b.final classes 当声明一个class为此类型时 不能再extends它了

//        9.多重继承 python c++类语言可以继承多个父级 但也因为带来了一些复杂性 所以java没有多重继承
    }
//    5.upcasting和downcasting的函数
//    public static void show(UIControl control){//调用这个方法时 TextBox被自动转换成UIControl类型，这就是upcasting
//        if (control instanceof TextBox){//control是否是TextBox class的实列
//            var textBox=(TextBox)control;//显示转换此对象为TextBox类型
//            textBox.setText("ddd");//这就是downcasting,使用时要确定传到这个函数里的对象它原本就是Textbox的实列，这样就可以安全地将其转换成TextBVox了
//        }
//        System.out.println(control);
//    }
}
```

3. Point.java
```
package org.example;

import java.util.Objects;

public class Point {

    private int x;
    private int y;

    public Point(int x, int y) {
        this.x = x;
        this.y = y;
    }




//    @Override
//    public boolean equals(Object obj) {
//        if(this == obj)
//            return true;
//
//        if (!(obj instanceof Point))
//            return false;
//        var other = (Point) obj;
//            return other.x == x && other.y == y;
////        if (obj instanceof Point) {
////            var other = (Point) obj;
////            return other.x == x && other.y == y;
////        }
////        return false;
//    }
//

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Point point = (Point) o;
        return x == point.x && y == point.y;
    }

    @Override
    public int hashCode() {
        return Objects.hash(x, y);
    }
//    @Override
//    public int hashCode() {
//       return Objects.hash(x,y);//哈希值理论上是 标志对象的唯一值
//    }
}
```
4. TextBox.java
```
package org.example;

public class TextBox extends UIControl {
//    textBox继承了uiconrol class中所有的特性
//
    private String text = "";

//    public TextBox() {
//        super(true);//显示调用父级 extends对象的构造函数
////        this.is//subclass不能访问 baseClass的private field methods
////        System.out.println("text box");
//    }

    public void setText(String text) {
        this.text = text;
    }

    public void clear() {
        text = "";
    }

    @Override//这种叫注释,这一句的目的是告诉java我们重写了toString这个方法
    public String  toString(){
        return text;
    }

    @Override
    public void render() {
        System.out.println("render textbox");
    }
}
```

5. UIControl.java
```
package org.example;

public abstract class UIControl {//声明这一类为abstract后 此class不能再被实列化了 ，只能继承extends 它
//    private boolean isEnabled = true;
protected boolean isEnabled = true;//protected is public in pacakage,即只要在package org.example;中isEnabled就是公共字段

//    public UIControl(boolean isEnabled) {
//        this.isEnabled =isEnabled;
//        System.out.println("ui conrol");
//    }

//    public void enable(){
//        isEnabled = true;
//    }
public final void enable(){//final 方法是不能override的
    isEnabled = true;
}

    public void disable(){
        isEnabled = false;
    }

    public boolean isEnabled(){
        return isEnabled;
    }

//    定义一个泛型方法
//    public void render(){
//
//    }

    public abstract void render();//声明此方法为abstract 删除{}编成方法的声明而不是实现
}
```


