---
title: java crash course-1语法笔记
date: 2025-03-09 15:32:28
tags:
categories: java
---
```
import java.awt.*;
import java.text.NumberFormat;
import java.util.Arrays;
import java.util.Date;
import java.util.Locale;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        System.out.println("Hello world");// system代表java中的system类;println ln是line的缩写,java中的string是用双引号的

//1.void 是java的保留关键字

//2.函数 function
/*
    函数是java中的最小块

    java函数的大括号和中括号在同一行

    函数始终属于一个类

    method的命名方式是camel 小驼峰 第一个开头字母小写
*/

//3.class
/*
    class就像一个超市，是相关功能的容器

    每一个java程序至少应该包含一个main()函数的类，这个类的名称叫做Main

    class Main {
    void main(){
        }
    }

    class的命名方式是Pascal 第一个字母大写

    在某些语言中，如果一个函数function被包含在了一个class里，那么这个函数被称作方法method
* */

//4.访问修饰符
/*
    类和方法都应该有一个访问修饰符

    访问修饰符是一个特殊关键字，它确定该程序的其他类和方法是否可以访问被标记的类和方法

    例如public、private,放在类和方法申明的前面

    public class Main {
        public void main(){
        }
    }

    这也是java程序的基本结构 有一个Main class 一个main()函数
* */

//5.$代表命令提示符

//6.变量
/*
int age = 30;
age=35;
System.out.println(age);
int myAge =30;
int herAge=myAge;
System.out.println(herAge);
* */

//7.java中的type
//    a.原始类型primitive 用于储存简单值
//    b.引用类型reference 用于储存复杂的对象

/*
原始类型(用来储存简单数据)

只能储存整数的：

byte    占用一个字节Byte     能储存[-128,127]的值
short   占用2个字节          能储存[-32k,32k]的值 k即千
int     占用4个字节          能储存[-2B,2B]的值 B即BILLION 十个亿
long    占用8个字节

用来储存小数的：

float    占用4个字节
double    占用8个字节

用来储存字符的
char     占用2个字节     比如说A,B,C

用来储存布尔值的：
boolean   占用1个字节    true/false

 */
//byte age =24

//int viewsCount =3_123_456_789
//long viewsCount =3_123_456_789L;//加上L作为后缀 报错，让编译器以为这个数字就是long类型、每三位数字=可以用一个下划线


//float price=10.99F;
//char letter ='A'//单引号 引用单个字符、双引号引用多个字符
//boolean isFilm = false;//橙色的就是 保留关键字，命名变量时不能用保留关键字

        /*8.引用类型
         * 用来储存 复杂的对象 如日期对象
         * java的引用类型 需要使用new运算符实例化得到变量
         * */
//
//Date now = new Date(); //一个对象 即是一个类的实例
////now.getTime(); //可以使用点方位对象里的方法
//System.out.println(now);


//byte x =1;
//byte y =1;
//x=2;
//System.out.println(y);

//引用类型是指命名变量时 即以为是 不同的两个变量A，b 其实是引用了同一个对象 同一个地址，即同一个对象
//引用类型的复制是 复制的引用值
//原始类型的复制是 复制的值 这两个值复制出来完全不一样
//        Point point1 = new Point(1,2)
//        Point point2 = point1;
//        point1.x=2;
//        System.out.println(point2);


//  初始化一个字符串变量的方式
//        a.使用new
//String message = new String('hey String')
//         b.直接字面意思赋值
//        String message = "hi String";
//        System.out.println(message);

//        c.对字符串的操作
//                1.用＋号拼接字符串
//        String message = "hi String" + "keys" + "!!";
//        System.out.println(message);
//                 2.使用点 可以看到 字符串类的所有方法和函数
//        System.out.println(message.startsWith("!!")); //endwidth length indexOf[某字符第一次出现的下标]
//        System.out.println(message.replace("!!",";;;")); //endwidth length indexOf[某字符第一次出现的下标]
//         trim ()去掉开头结尾多余的空格
//        3.如何在字符串中 写特殊字符 使用返斜杠\
//        String message = "hey \"rain\"";


//   反斜杠 像windows c \
//        String message = "c \\file\n sec";
//
//        System.out.println(message);

        /*9.jsva的数组的*/

//        int number =1;
//        int[] numbers = new int[5]; //数组数组int[] ；数组名numbers；数组是引用类型所以需要呢哇 new int[5]
//        numbers[0] =1;
////        System.out.println(numbers); //打印出内存地址
//
////                转换成字符串
//        System.out.println(Arrays.toString(numbers)); //打印出内存地址

//        a.另一种命名的方式
//        int [] numbers = {2,3,4,5,6}; //java中一旦创建了数组就不能删除 或者添加

//        b.创建多维数组
//        int [][] numbers = new int[2][3]; //代表2行3列
//        numbers[0][0] =1; //将第一行 第一列初始化为1
////        System.out.println(Arrays.toString(numbers));
////       //处理多重数组


//        c.用花括号赋值 多维数组 （字面量？
//        int [][] numbers = {{1,2,3},{4,5,6}};
//        System.out.println(Arrays.deepToString(numbers));

        /*10.java里的常变量 用全大写命名常常*/
//        float pi =3.14F;
//     final float PI =3.14F;
//        PI =1;

        /*11.算术表达式(加减乘除)*/
//        a.除法;

//        int result =10/3;
//        double result =(double) 10/(double) 3;
//        System.out.println(result); //java中 除法得到的是整数

//        b.增量运算 ++
//        int x=1;
//
////        int y = x++; //增量运算号放在后缀时，x会先赋值给y,再去加自加1
//        int y = ++x; //增量运算号放在前缀时，x会先增加1,再去赋值给y
//
//        System.out.println(x);
//        System.out.println(y);

//        c.增强复合运算符，如果想让自增的不是1而是2
//        int x=1;
////        x = x+2;
////        x += 2 ;//更简短了
////        x-=2;
//        x/=2;
//
//        System.out.println(x);

//        d.()总是优先级
//        int x = (10+3) *2;

        /*12.强制类型转换*/
//        a.隐式转换
//        short x =1;
//        int y = x+2; //两种类型的值 被转换成了同一种类型;  shiort类型的值被复制到了Integer的内存做加法，//隐式转换
//        byte > short > int > long byte可以被这样转化

//        double x =1.1;
//        double y = x+2;//小数有更精确的描述可以包括2，int 2会被转换成 double
//        byte > short > int > long >float >double

//        如果想要加的结果是int的
//        int y = (int)x+2;//显式转换 只能发生在能兼容的数据类型中数字类型
//        System.out.println(y);

//        b.把字符串类型转换成数字
//        String x ="1";
//        Integer.parseInt(x);//转换成数字
//        int y = Integer.parseInt(x) + 2;
//        System.out.println(y);

//        String x ="1.1";
//        double y = Double.parseDouble(x) + 2;
//        System.out.println(y);

//        13.数学类
//       int result = (int)Math.floor(1.1);
//        System.out.println(result);

        /*14.格式化数字*/
//        NumberFormat currency = new NumberFormat()//看报错，这个class是absracted 抽象的类不能使用new运算符
//        NumberFormat currency =  NumberFormat.getCurrencyInstance();//转换成钱的字符串
//       String result=  currency.format(123456.932);

//       a.链式方法
//      String result=  NumberFormat.getPercentInstance().format(0.1);//NumberFormat.getPercentInstance()返回了一个对象，直接点出来
//        System.out.println(result); //shift f6选择变量名快速改名

        /*15.读取java的输入*/
//        从终端窗口键入还是
//       Scanner scanner = new Scanner(System.in);//通过new获得一个scanner对象 终端窗口输入
////byte age = scanner.nextByte();//返回一个byte类型的值 读取
//        System.out.print("Name:");
////        String age = scanner.next();//如果输入空格的话 只能读取到空格前的
//        String age = scanner.nextLine().trim();//解决使用nextLine
////        读取一个String的值
//        System.out.println("you are"+ age);

        /*16.控制执行流程 control flow*/
//        a.比较运算符
//int x=1;
//int y=1;
//        System.out.println(x==y);//比较等于运算符== ,<=

//b.逻辑运算符
//        int temperature =22;
//        boolean isWarm = temperature >20&& temperature<30; //从左到有执行，只要第一个返回false就不会再去看第二个表达式
//        System.out.println(isWarm);

//        boolean hasHighIncome =true;
//        boolean hasG =true;
//        boolean isE = hasHighIncome ||  hasG; //从左到有执行，只要第一个返回TRUE就不会再去看第二个表达式,如果第一个是false，是会去看第二个式子的
//        System.out.println(isE);

//                boolean hasHighIncome =true;
//        boolean hasG =true;
//        boolean hasCrime = false;
//        boolean isE = (hasHighIncome ||  hasG)&& !hasCrime; //!取反
//        System.out.println(isE);

//c.if语句
//        int temp =32;
//        if (temp>30){
//            System.out.println("hott day");
//        }
//        else if (temp >20)
//            System.out.println("beautiful day");
//        else
//            System.out.println("cold day");

        int income = 120_000;
//boolean hasH ;

//        if (income>10_000){
//           hasH=true;//花括号表示一个作用阈；1.如果定义变量需要加花括号 2.如果在外面读取花括号里面的东西是读不到的
//        }
//        else
//            hasH=false;

//        boolean hasH = income>10_000;
//        System.out.println(hasH);


//        d.三元运算
//        String classNam;
////        if (income > 100_000) {
////            classNam = "First";
////        }
//
//        classNam =income >100_000 ? "First" :"E"//省去了if

//        e.switch语句
        String role = "admin";
//        if (role == "admin") {
//            System.out.println("you are an admin");
//        } else if (role == "moderator") {
//            System.out.println(" u r moderator");
//
//        }

//        switch (role) {
//            case "admin":
//                System.out.println("you are an admin");
//                break; //不使用break,它就会继续执行
//            case "moderator":
//                System.out.println(" u r moderator");
//                break;
//            default:
//                System.out.println(" u r gust");
//        }

//        f. for循环
//        for (int i =0;i <5 ;i++){
//            System.out.println("heyyy " +i);
//        }

//        ｇ．ｗｈｉｌｅ　循环

//        int i =5;
//        while (i>0){ //在不清楚会循环多少次时使用
//            System.out.println("hey while");
//            i --;
//        }

        String input = "";
//        while (input !="quit"){ //input是字符串

        Scanner scanner = new Scanner(System.in);     //  创建一个扫描对象
//        while (!input.equals("quit")){  //因为是2个不同的字符串 所以他们的地址不一样，可以用equal比较
////          Scanner scanner = new Scanner(System.in) ;     //  创建一个扫描对象 如果每次while都要创建一个 这会污染内存，所以把它放外面
//            input = scanner.next().toLowerCase();
//            System.out.println(input);
//        }

//        h.do while循环 至少会执行一次 即使条件为假
//do{
//    System.out.println("Input:");
//    input = scanner.next().toLowerCase();
//    System.out.println(input);
//
//}while (!input.equals("quit"));

//        i.break

//                while (!input.equals("quit")){  //因为是2个不同的字符串 所以他们的地址不一样，可以用equal比较
//                    System.out.println("Input:");
//            input = scanner.next().toLowerCase();
//            if (input.equals("pass"))
//                continue;// 遇到此关键字 java会把控制移到循环的开始
//            if (input.equals("quit"))
//                break;//当java看到break时它将终止循环 忽略其他所有内容
//            System.out.println(input);
//        }
//                当使用whiLe (true)语句时候 一定要保证花括号里有break语句否则它会一直循环下去

//        j.foreach循环
        String[] fruits = {"apple", "mango", "orange"};
//                for (int i =0;i<fruits.length,i++)
//        System.out.println(fruits[i]);

        for (String fruit : fruits) //不需要定义开始的数，不需要定义自增
            System.out.println(fruit);//此方法总是向前出发，上面的方法是可以自减的

//运行代码 shift f10
    }
}
```