# Java

[TOC]



## 1.Java概述

- Java历史 

  > Java是由<span style='color:orange'>Sun Microsystems公司</span>于1995年5月推出的Java面向对象程序设计语言和Java平台的总称。由<span style='color:orange'>James Gosling</span>和同事们共同研发，并在<span style='color:orange'>1995年</span>正式推出。
  >
  > 注：什么是程序，计算机执行某些操作或解决某个问题而编写的一系列<span style='color:orange'>有序指令的集合</span>

- Java特点

  > Java是一种广泛使用的计算机编程语言，拥有<span style="color:orange">跨平台、面向对象、泛型编程</span>的特性，广泛应用于企业级Web应用开发和移动应用开发。
  >
  > Java编程语言是个简单、面向对象、分布式、解释性、健壮、安全与系统无关、可移植、高性能、多线程和动态的语言
  >
  > Java不同于一般的编译语言或解释型语言。它首先将<span style="color:orange">源代码</span>编译成<span style="color:orange">字节码</span>，再依赖各种<span style="color:orange">不同平台上的虚拟机</span>来解释执行字节码，从而具有“<span style="color:orange">一次编写，到处运行</span>”的<span style="color:orange">跨平台特性</span>。

- Java技术体系平台

  > <span style="color:RED">Java SE</span> (Java Standard Edition)<span style="color:RED">标准版</span> J2SE 
  >
  > 支持面向桌面级应用（如Windows下的应用程序）的Java平台，提供了完整的Java核心API
  >
  > <span style="color:RED">Java EE</span>(Java Enterprise Edition)<span style="color:RED">企业版</span> J2EE
  >
  > 是为开发企业环境下的应用程序提供的一套解决方案。该技术体系中包含的技术如：Servlet、JSP等，主要针对于web应用程序开发
  >
  > <span style="color:RED">Java ME</span>(Java Micro Edition)<span style="color:RED">小型版</span> J2ME
  >
  > 支持Java程序运行在移动终端，对Java API 有所精并加入了针对移动终端的支持

- Java运行机制及运行过程

  ![image-20220708115628346](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062242956.png)

  什么是<span style="color:RED">编译</span>：

  例如：javac Hello.java

  答：有了java<span style='color:red'>源文件</span>，通过编译器将其编译成<span style='color:red'>JVM</span>可以识别的<span style='color:red'>字节码文件</span>。在该源文件目录下，通过javac编译工具对Hello.java文件进行编译。如果程序无误，无任何提示，但在当前目录下会出现一个Hello.class文件，该文件为字节码文件，也是可以执行的java程序。

  什么是<span style='color:red'>运行</span>：

  答：有了可执行的java程序（Hello.class字节码文件），通过运行工具java.exe对字节码文件进行执行，本质就是.class文件装载到JVM执行

- Java开发环境搭建

  JDK1.8下载及安装  环境变量path配置  

  ![image-20220708115715642](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062243894.png)

  ![image-20220708115806451](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062243717.png)

  ![image-20220708115837236](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062243440.png)

- DOS常用指令

- Java开发注意事项与细节

  1. Java源文件以.java为扩展名。源文件的基本组成部分是<span style='color:red'>类class</span>。

  2. Java应用程序的执行入口是main()方法。有固定的书写格式：

     <span style='color:red'>public static void main(String[] args){...}</span>

  3. Java语言严格<span style='color:red'>区分大小写</span>。

  4. Java方法由一条条语句构成，每个语句以“<span style='color:red'>;</span>”结束。

  5. 大括号都是成对出现的，缺一不可。习惯先写{}再写代码。

  6. 一个源文件中最多只能有<span style='color:red'>一个</span>public类。其他类的个数不限。

  7. 如果源文件包含一个public类，这文件名必须按该类命名。

  8. 可以将main方法写在非public类中，然后指定运行非public类，这样入口方法就是非public的main方法。



### 2.java常识

#### 	1.转义字符

​		java常用转义字符：

​		<span style="color:RED"> \t </span>  一个制表位，实现对齐的功能

​		<span style="color:RED"> \n </span>  换行符

​		<span style="color:RED"> \\\ </span> 一个\

​		<span style="color:RED">\\''</span>  一个''

​		<span style="color:RED">\\'</span>  一个'

​		<span style="color:RED">\r</span>  一个回车 System.out.println("今朝有酒\r今朝醉");



#### 	2.易犯错误

​		找不到文件![image-20220708154255799](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062243632.png)

​		解决方法：源文件名不存在或者写错，或者当前路径错误



​		主类名和文件名不一致![image-20220708154320380](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062243007.png)

​		解决方法：声明为public的主类应与文件名一致，否者编译失败



​		缺少分号![image-20220708154334672](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062243121.png)

​		解决方法：编译失败，注意错误出现的行数，再到源代码中指定位置改错。

​		以及更加复杂的<span style="color:red">业务错误及环境错误</span>。



#### 3.注释介绍 <span style="color:red">comment</span>

​	用于注解说明解释程序的文字就是注释，注释提高了代码的阅读性（可读性）；注释是一个程序员必须要具有的良好编程习惯。将自己思想通过注释先整理出 	来，再用代码去实现。



​	Java中的注释类型

​	<span style="color:red">单行注释</span>

​	基本格式：//注释文字

​	<span style="color:red">多行注释</span>

​	基本格式：/* 注释文字*/

​	<span style="color:red">文档注释</span>

​	注释内容可以被JDK提供的工具javadoc所解析，生成一套以网页形式体现的该程序的说明文档，一般写在类

![image-20220708163642493](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062244539.png)

​	javadoc -d 文件夹名 -xx -yy Comment02.java![image-20220708163754521](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062244125.png)



​	Javadoc 可以识别的标签 如下表所示：

| 标签          | 描述                                                        | 在 JDK/SDK 中引入 |
| ------------- | ----------------------------------------------------------- | ----------------- |
| @author       | 名称文本，仅限类和接口                                      | 1.0               |
| @version      | 指定版本，仅限类和接口                                      | 1.0               |
| {@code}       | 显示文本，而不会将文本解释为 HTML 标记或嵌套的 javadoc 标签 | 1.5               |
| {@docRoot}    | 指明当前文档根目录的路径                                    | 1.3               |
| @deprecated   | 弃用文本，指名一个过期的类或成员，表明该类或方法不建议使用  | 1.0               |
| @exception    | 可能抛出异常的说明，一般用于方法注释                        | 1.0               |
| {@inheritDoc} | 从直接父类继承的注释                                        | 1.4               |
| {@link}       | 插入一个到另一个主题的链接                                  | 1.2               |
| {@linkplain}  | 插入一个到另一个主题的链接，但是该链接显示纯文本字体        | 1.4               |

​	细节：

​	<span style="color:red">被注释的文字，不会被JVM（Java虚拟机）解释执行</span>

​	<span style="color:red">多行注释里不允许有多行注释嵌套</span>



#### 4.代码规范

​	类、方法的注释，要以javadoc的方式来写。

​	非javadoc的注释，往往是给代码的维护者看的，着重说明代码逻辑和注意事项。

​	使用tab操作，实现缩进，默认整体向右移动，shift+tab则是整体向左移动。

​	运算符 = 两边习惯性各加一个空格。比如 2 + 4 * 6 - 3 

​	<span style="color:red">源文件使用utf-8编码</span>

​	行宽度不要超过80字符

​	代码编写<span style="color:red">次行风格</span>与<span style="color:red">行尾风格</span>

![image-20220708171133662](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062245332.png)



#### 5.DOS原理

​	**<span style="color:red">DOS命令不区分大小写</span>**

​	1.常用DOS命令：

| **序号** | 操作                                              | **说明**                                  | **示例**                                                     | 结果                                                  |
| -------- | ------------------------------------------------- | ----------------------------------------- | ------------------------------------------------------------ | ----------------------------------------------------- |
| 1        | <span style="color:red">盘符名称:</span>          | 盘符切换。                                | C:\Users\DELL><span style="color:red">D:</span>              | <span style="color:red">D:\\></span>                  |
|          | <span style="color:red">D:</span>                 | 切换到D盘                                 |                                                              |                                                       |
| 2        | <span style="color:red">cd 目录</span>            | 进入单级目录。名字为Program Files的文件夹 | D:><span style="color:red">cd Program Files</span>(D盘必须存在此文件夹) | <span style="color:red">D:\Program Files></span>      |
|          |                                                   | 从C盘到D盘中的Program Files               | C:\Users\DELL><span style="color:red">cd D:\Program Files</span>C:><span style="color:red">d:</span> | <span style="color:red">D:\Program Files></span>      |
| 3        | <span style="color:red">cd 目录1\\目录2...</span> | 进入多级目录。                            | D:><span style="color:red">cd Program Files\Java</span>      | <span style="color:red">D:\Program Files\Java></span> |
|          |                                                   |                                           |                                                              |                                                       |



| 操作          | 说明                                          |
| ------------- | --------------------------------------------- |
| cd.           | （change directory）当前目录                  |
| cd..          | （change directory）可以返回上一级目录        |
| cd\           | 返回到当前盘符根目录                          |
| dir           | （directory）查看当前路径下的文件夹和文件内容 |
| date          | 日期设置命令（Ctrl+z）                        |
| time          | 时间设置命令（Ctrl+z）                        |
| cls           | （clear screen）清屏。                        |
| exit          | 退出命令提示符窗口                            |
| F7            | 查看历史命令，选中之后执行用过的命令          |
| cd /?`或`cd/? | （`/`表示命令的功能开关）查看cd命令的具体用法 |
| md /?`或`md/? | 查看md命令的具体用法                          |

![image-20220708174215696](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062245065.png)



​	2.创建文件夹（<span style="color:red">md \[盘符:][路径名] 文件夹名称</span>）make directory



​	3.删除文件夹（<span style="color:red">rd \[盘符:][路径名] 文件夹名称</span>）remove directory



​	4.创建文件（<span style="color:red">copy con 文件名称.后缀名</span>）（可以创建，但输入内容的问题还没有解决）



​	5.查看文件（<span style="color:red">type 文件名称.后缀名</span>）

![image-20220708175605395](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062245251.png)



​	6.删除文件（<span style="color:red">del 文件名称.后缀名</span>）delete



​	7.拷贝（复制）文件（<span style="color:red">copy [源目录或文件] [目的目录或文件]</span>）

​	举例1：`copy C:*.txt D:`表示将C盘根目录下所有扩展名为txt的文件拷贝到D盘根目录中。
​	举例2：`copy C:autoexec.bat C:autoexec.bak`表示将autoexec.bat复制成为拓展名为bak的文件。输入dir命令，可以发现变化。



​	8.修改文件名（<span style="color:red">ren [源文件名称.后缀名] [新文件名称.后缀名]</span>）

![image-20220708175347939](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062245955.png)

#### 6.路径详解

​	**基本概念**

　　文件路径就是文件在电脑中的位置，表示文件路径的方式有两种，相对路径和绝对路径。在[网页设计](https://so.csdn.net/so/search?q=网页设计&spm=1001.2101.3001.7020)中通过路径可以表示链接，插入图像、Flash、CSS文件的		位置。

​		<span style='color:red'>**相对路径(Relative Path)**</span>

​		相对路径就是以当前文件为基准进行一级级目录指向被引用的资源文件。

​		<span style="color:red">**绝对路径(Absolute Path)**</span>

​		绝对路径就是文件的真正存在的路径，是指从硬盘的根目录(盘符)开始，进行一级级目录指向文件。

​		![image-20220708202312426](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062246092.png)



#### 7.总结作业

​	1.编写hello world 程序

```java
public class Homework01 {
	public static void main(String[] args) {
		System.out.println("helloworld");
		//System.out.println(helloworld);
	}
}
```



​	2.将个人的基本信息（姓名、性别、籍贯、住址）打印到控制台输出。各条信息分别占一行。

```java
public class Homework02 {
	public static void main(String[] args) {
		System.out.println("姓名\t性别\t籍贯\t住址\nmomo\t男\t湖南\t长沙");
	}
}
```



​	3.JDK、JRE、JVM的关系

​		<span style="color:red">JDK=JRE+Java开发工具</span>

​		<span style="color:red">JRE=JVM+核心类库</span>



​	4.环境变量path配置及其作用

```java
1.作用：为了在dos任意目录可以使用java和javac命令
2.先配置JAVA_HOME = 指向jdk安装主目录
3.编辑path环境变量，增加%JAVA_HOME%\bin
```



​	5.Java编写步骤

 ```java
 1.编写java源码
 2.javac编译，得到对应的.class字节码文件
 3.java运行，本质就是把,class文件加载到JVM运行
 ```



​	6.Java编写7个规范

```java
1.类、方法的注释，使用javadoc的方式，即文档注释
2.非javadoc注释，往往是对代码的说明（程序的维护者），说明如何修改及注意事项
3.使用tab使整体代码向右移，使用shift+tab使代码整体左移
4.运算符和 = 两边给空格，代码清晰 例如 int n = 1 + 1；
5.源码文件使用utf-8编码
6.行宽字符不超过80
7.代码编程风格有两种 次行风格与行尾风格
```



​	7.初学者Java易犯错误

```java
1.编译或者运行时，找不到文件 javac Hello,java,把文件或者目录找对
2.主类名与文件名不一致
3.缺少;
4.拼写错误
```

## 2.Java基础

### 1.Java基础—变量

#### 	1.变量原理

​		<span style="color:red">变量是程序的基本组成单位</span>

​		无论是使用哪种高级程序语言编写程序，变量都是其程序的基本组成单位

​		变量有三个基本要素（<span style="color:red">类型 + 名称 + 值</span>）

```java
class Test{
    public static void mian(String[] args){
        int a = 1;//定义了一个变量，类型为int整型，名称为a，值为1
        int b = 3;//定义了一个变量，类型为int整型，名称为b，值为3
        b = 83;//把83值赋给b变量
        System.out.println(a);//输出a变量的值
        System.out.println(b);//输出b变量的值
    }
}
```

​		

#### 	2.变量概念

​		变量相当于内存中一个数据存储空间的表示，可以看作一个房间的门牌号，通过门牌号可以找到房间，而通过变量名可以访问到变量值。

​		变量使用的基本步骤

​		1）声明变量 

```java
int a;
```

​		2）赋值

```java
a = 60;//把60赋值给a
```

​		3）输出使用

```java
System.out.println(a);
```

​		通常一步到位 <span style="color:red">int a = 60;

#### 	3.变量入门

​	变量入门案例：

```java
//记录一个人的信息
int age = 18;
double score = 88.9;
char gender = '男';
String name = "汤姆";
```



#### 	4.变量细节

​	1)变量表示内存中的一个存储区域，不同的变量，类型不同，占用的空间大小不同

​	2）该区域有自己的变量名和数据类型

​	3）变量必须先声明，后使用，即有顺序

​	4）该区域的数据可以在<span style="color:red">同一类型</span>范围内不断变化

​	5)变量在同一个作用域内不能重名

​	6）变量 = 变量名 + 值 + 数据类型，变量三要素

```JAVA
//变量必须先声明，后使用，即有顺序
int a = 50;
a = 60;//对
//a = "jack";// 值可以在同一类型范围内不断变化
System.out.println(a);

//变量在同一个作用域内不能重名
//int a = 100;//x
```



#### 	5.加号使用

​	1）当左右两边都是数值型时，则做加法运算

​	2）当左右两边有一方为字符串，则做拼接运算

​	3）运算顺序，从左到右

```java
System.out.println(100 + 90);              //190
System.out.println("100" + 98);            //10098
System.out.println(100 + 3 + "helloworld");//103helloworld
System.out.println("helloworld" + 100 + 3);//helloworld1003
```



#### 	6.数据类型

![image-20220709120717965](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062246569.png)

​	

#### 	7.整型使用

​	1.Java的整数类型就是用于存放整数值的，比如12、30、3456等。

![image-20220709122645039](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062246328.png)



#### 8.整型细节

​	1）Java各整数类型有固定的范围和字段长度，不受具体OS操作系统的影响，以保证Java程序的可移植性

​	2）Java程序中变量常声明为int型，除非不足以表示太大的数，才使用long

​	3）Java的整型常量（具体值）默认为int型，声明long型常量需加'i'或'L'

​	4）<span style="color:red"> bit：计算机最小存储单位。byte：计算机基本存储单位。1byte = 8bit。</span>如下示例byte3与short3

![image-20220709124034483](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062246377.png)

#### 9.浮点数使用

![image-20220709125235745](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062246158.png)

​	说明：

​	<span style="color:red">浮点数 = 符号位 + 指数位 + 尾数位</span>

​	尾数部分可能丢失，造成精度损失（小数都是近似值）。

#### 10.浮点数细节

​	1）与整数类型相似，Java浮点类型也有固定的范围和字段长度，不受具体OS的影响。

​	2）Java的浮点型常量（具体值）默认为double型，声明为float常量，需加'f'或'F'

​	3）浮点型常量有两种表示形式

​		十进制数形式：5.12       5.12f      .12（0可以省略，小数点必须保留）

​		科学计数法形式：5.12e2【5.12*10的二次方】  5.12E-2【5.12/10的二次方】

​	4）通常情况下，应该使用double型，因为它比float型更精确，如下

```JAVA
//Java的浮点型常量（具体值）默认为double型，声明Float型常量，徐后加'f'或'F'
//float num1 = 1.1;//这是错误的
float num2 = 1.1f;//这是正确的
double num3 = 1.1;//正确
double num4 = 1.1F;//正确

//十进制数形式：如 5.12   512.0F   .512(小数点保留)
double num5 = .123;//等价与0.123
System.out.println(num5);

//科学计数法形式：如 5.12e2 【5.12 * 10的二次方】  5.12E-2 【5.12 / 10的二次方】
System.out.println(5.12e2);//512.0
System.out.println(5.12E-2);//0.0512

//通常情况下，应该使用double型，因为它比float型更准确
//例如 double num9 = 2.123456789；float num10 = 2.123456789；
double num9 = 2.123456789;
float nun10 = 2.123456789f;
System.out.println(num9);//2.123456789;
System.out.println(num10);//2.1234567;
```

<span style="color:red">**浮点数陷阱**</span>：

```java
//浮点数使用陷阱：2.7 和 8.1 / 3 比较
double num1 = 2.7;
double num2 = 8.1 / 3;
System.out.println(num1);//2.7
System.out.println(num2);//2.6999999999999997 不等于2.7

//重点：对运算结果是小数进行判断时，要注意小心
//错误写法
if (num1 == num2) {
    System.out.println("相等");
}

//正确写法：以两个数的差值的绝对值，在某个精度范围内判断
if (Math.abs(num1 - num2) < 0.00000001) {
    System.out.println("差值非常小，到达规定精度，所以认为相等");
}
```



#### 11.Java文档

![image-20220709141747756](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062247785.png)

​															https://www.matools.com/api/java8

​	1）API（Application Programming Interface，应用程序编程接口）是Java提供的基本编程接口。

​	2）Java语言提供了大量的基础类，因此Oracle公司也为这些基础类提供了相应的API文档，用于告诉开发者如何使用，以及这些类里包含的方法。

​	3）Java类的组织形式

![image-20220709141805061](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062247847.png)

#### 12.字符型使用

​	字符类型可以表示单个字符，字符类型是char，char是两个字节（可以存放汉字），多个字符永字符串String

```java
char c1 = 'a';
char c2 = '\t';
char c3 = '是';
char c4 = 97;//说明：字符类型可以直接存放一个数字

System.out.println(c1);
System.out.println(c2);
System.out.println(c3);
System.out.println(c4);
```



#### 13.字符型细节

​	1）字符常量是用单引号（''）括起来的单个字符。例如： char c1 = 'a'; char c2 = '中'; char c3 = 9;

​	2）Java中还允许使用转义字符'\'\来将后来的字符转变为特殊字符常量。

​	3）在Java中，<span style="color:red">char的本质是一个整数</span>，在输出时，是按照对应的unicode字符输出

​	4）可以直接给char赋值一个整数，然后输出时，会按照对应unicode字符输出

​	5）<span style="color:red">char类型是可以进行运算的</span>，相当于一个整数

```java
char c1 = 'a';//输出'a'对应的数字
System.out.println((int)c1);

char c2 = '胡';
System.out.println((int)c2);

char c3 = 38889;
System.out.println(c3);

//char类型是可以进行运算的，相当于一个整数

System.out.println('a' + 10);//107

char c5 = 'b' + 1；//98 + 1 = 99
    System.out.println((int)c5);
System.out.println(c5);
```



#### 14.常用编码

![v2-76b9928eef936eda85b873bf0c0f6766_1440w](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062247671.jpg)

​	1）字符型存储到计算机中，需要将字符对应的码值（整数）找出来，比如'a'

​		存储：'a' ==> 码值97 ==> 二进制（1100001）==> 存储

​		读取：二进制（1100001） ==> 97 ==> 'a' 显示

​	2）字符和码值的对应关系是通过字符编码表决定的

​	3）介绍一下字符编码表

​		**ASCII码** —ASCII编码表由一个字节表示，128个字符，实际上一个字节可以表示256个字符，但是老外的英文只有那么24个字母，用不了那么多的字符。但是随着计算机的普及，全球都在使用计算机，原本的编码不能够满足全球各国语言，所以出现了[Unicode](https://so.csdn.net/so/search?q=Unicode&spm=1001.2101.3001.7020)。

​		**Unicode**—Unicode编码表是固定大小的编码，使用两个字节来表示字符，字母和汉字统一都是占用两个字节，容易造成空间浪费。

​		**utf-8**—大小可变的编码，字母使用一个字节，汉字使用3个字节。

​		**gbk**—gbk编码可以表示汉字，而且范围广，字母使用一个字节，汉字2个字节。

​		**gb2312**—可以表示汉字，gb2312<gbk

​	<span style="color:red">注意！！！</span>

- WHY? 经常出现的乱码的原因就是因为同一段代码采用的编码和解码的编码格式不同导致乱码的情况。
- 比如Notepad++中的默认编码格式为utf-8,而cmd中的编码格式为gbk，两者默认编码语言不同，无法进行正常编码，所以会出现乱码的现象，就像你听不懂外文是一回事。

#### 15.布尔类型

​	1）布尔类型也叫boolean类型，只允许取值true和false，无null

​	2）boolean类型占一个字节

​	3）boolean适用于逻辑运算，一般用于流程控制

```java
//演示判断成绩是否通过的案例
//定义一个布尔变量
boolean isPass = true;
if (isPass = true) {
    System.out.println("考试通过了，恭喜");
} else {
    System.out.println("考试没有通过，下次努力");
}
```

注：不可以0或者非0的整数替代false和true，这点和c语言不同

#### 16.自动类型转换

​	当Java程序在进行赋值或者运算时，精度小的类型自动转换为精度大的数据类型，这就是自动类型转换

​	<span style="color:red">**数据类型按精度（容量）大小排序为 ，重点！！！！**</span>

![image-20220709171318215](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062247160.png)

```java
//演示自动类型转换
int num = 'a';//ok  char -》 int
double num2 = 80;//ok  int -》 double
System.out.println(num);//98
System.out.println(num2);//80.0
```



 1）有多种类型的数据混合运算时，系统首先自动将所有数据转换成容量最大的那种数据类型，然后再计算。

 2）当我们把精度（容量）大的数据类型赋值给精度（容量）小的数据类型时就会报错，反之则进行自动类型转换

 3）（byte、short）和char之间不会相互自动转换

```java
//有多种类型的数据混合运算时
//细节1：系统首先自动将所有数据转换成容量最大的数据类型，然后进行计算
int n1 = 10;//ok
//float n2 = n1 + 1.1;//错误 n1 + 1.1 =》 结果类型是double
//double n3 = n1 + 1.1;//正确 n1 + 1.1 =》 结果类型是double
float n4 = n1 + 1.1f;//正确 n1 + 1.1 =》 结果类型是float

//细节2：当我们把精度（容量）大的数据类型赋值给精度（容量）小的数据类型时
//就会报错。反之则进行自动类型转换

//int n5 = 1.1;//错误

//细节3：（byte、short）和char之间不会相互自动转换
//当把具体数赋给byte时，应该先判断是否在byte范围内，如果是就可以
byte b1 = 10;//正确的，原因：如果10在-127至128之间

int i1 = 1;
byte i2 = i1;//错误，如果是变量赋值，则首先判断类型

char c1 = b1;//错误，原因byte不能自动转换成char
```

 4）byte、short、char他们三者可以计算，在计算时首先转成int类型

 5）boolean不参与转换

 6）自动提升原则：表达式结果的类型自动提示为操作数中最大的类型

其他见<span style="color:red">**常量优化机制!!!!**</span>

#### 17.强制类型转换

​	自动类型转换的逆过程，将容量大是数据类型转换为容量小的数据类型。使用时要加上强制转换符（），但可能造成<span style='color:red'>精度降低或溢出</span>，需注意。

```java
//演示强制类型转换
int a1 = (int)1.9;
System.out.println(a1);//1 造成精度损失

int a2 = 2000;
byte b1 = (byte)a2;
System.out.println(b1);//-48 造成数据溢出
```

​	1）当进行数据的大小从大=》小，就需要使用到强制转换

​	2）强转符号只针对最近的操作数有效，往往会使用小括号提升优先级

​	3）char类型可以保存int的常量值，但不能保存int的变量值，需要强转

​	4）byte、short、char类型在进行运算时，当作int类型处理。

```java
//演示强制类型转换
//强制符号只针对最近的操作数有效，往往会使用小括号提升优先级
//int x = (int)10 * 3.5 + 6 * 1.5;//编译错误 double => int
int a = (int)(10 * 3.5 + 6 * 1.5);//(int)44.0 -> 44
System.out.println(a);

char c1 = 100;//ok
int m = 100;//ok
//char c2 = m;//错误
char c3 = (char)m;
System.out.println(c3);
```



#### 18.String与基本类型转换

​	在程序开发中，我们经常需要将基本数据类型转成String类型。或者将String类型转成基本数据类型。

​	1）基本数据类型转String类型 

​		语法：基本数据类型的值 + ""

​	2）String类型转基本数据类型

​		语法：通过基本数据类型的包装类调用parseXXX方法即可

```java
//基本数据类型 --》 String
int a = 100;
float b = 1.1f;
double c = 2.2;
boolean d = true;

String a1 = a + "";
String b1 = b + "";
String c1 = c + "";
String d1 = d + "";
System.out.println(a1 + "" + b1 + "" + c1 + "" + d1 + "");

//String => 对应的基本数据类型
String s = "123";

int z1 = Integer.parseInt(s);
float z2 = Float.parseFloat(s);
double z3 = Double.parseDouble(s);
long z4 = Long.parseLong(s);
byte z5 = Byte.parseByte(s);
boolean z6 = Boolean.parseBoolean("true");
short z7 = Short.parseShort(s);

System.out.println(z1 + 1);
System.out.println(z2 + 2);
System.out.println(z3 + 3);
System.out.println(z4 + 4);
System.out.println(z5 + 5);
System.out.println(z6 + "FALSE" );
System.out.println(z7 + 6);
```

​	细节：

​		1）在将String类型转成基本数据类型时，要确保String类型能够转成有效的数据，比如我们可以把"123"转成一个整数，但是不能把"hello"转成一个整数

​		2）如果格式不正确，就会<span style="color:red">抛出异常</span>，程序就会终止

![image-20220709214010098](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062247035.png)

#### 19.作业总结

```java
//使用char类型，分别保存\n \t \r \\ 1 2 3 等字符，并打印输出
char a = '\n';
char b = '\t';
char c = '\r';
char d = '\\';
char e = '1';
char f = '2';
char g = '3';
System.out.println(a + b + c + d + e + f + g );

//编程，保存两本书名，用+号拼接
String book01 = "夏有乔木";
String book02 = "雅望天堂";
System.out.println(book01 + book02);//夏有乔木雅望天堂

//保存两个性别，用+好拼接
char m = '男';
char w = '女';
System.out.println(m + w);//52906

//保存两本书的价格，用+号拼接
double p1 = 100.12;
double p2 = 120.22;
System.out.println(p1 + p2);//220.34

/*
		姓名 年龄 成绩 性别 爱好
		xx   xx  xx   xx   xx

		要求：
		1）用变量名将姓名、年龄、成绩、性别、爱好存储
		2）使用+
		3）添加适当的注释
		4）添加转义字符，使用一条语句输出 
		*/

//姓名定义
String name = "张三";
//年龄定义
int age = 18;
//成绩定义
double score = 98.0;
//性别定义
char gender = '男';
//爱好定义
String hobby = "游泳";

System.out.println("姓名\t年龄\t成绩\t性别\t爱好" + "\n" + name +
                   "\t" + age + "\t" + score + "\t" + gender + "\t" + hobby);
```

### 2.Java基础—运算符

​	<span style="color:red">运算符是一种特殊的符号，用以表示数据的运算、赋值和比较等。</span>

#### 	1.算数运算符		![image-20220710114942672](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062247609.png)

​		算数运算符是对数值类型的变量进行运算的，在Java程序中使用非常多。

```java
//算数运算符的使用
// /（除号） 的使用
System.out.println(10 / 4);//从数学角度来看是2.5 java中是2
System.out.println(10.0 / 4);//java是2.5

// 注释快捷键ctrl + / ，再次输入ctrl + /，取消注释
double d = 10 / 4;//java中10 / 4 = 2，2=》2.0
System.out.println(d);//2.0

//% 取模（余）
//% 的本质是一个公式： a % b = a - a / b * b
// -10 % 3 => (-10) - (-10) / 3 * 3 =-10 + 9 = -1
// 10 % -3 => 10 - 10 / (-3) * (-3) = 1
// -10 % -3 => (-10) - (-10) / (-3) * (-3) = -1

System.out.println(10 % 3);//1
System.out.println(-10 % 3);
System.out.println(10 % -3);
System.out.println(-10 % -3);

//++的使用
int i = 10;
i++;//自增 等价于i = i + 1；
System.out.println(i);//11

++i；//自增 等价于i = i + 1；
    System.out.println(i);//12

/*
		作为表达式使用
		前++：++i 先自增后赋值
		后++：i++ 先赋值后自增
		*/

int a = 8;
// int b = ++a;
// System.out.println("a=" + a + "b=" + b);//a=9,b=9

int c = a++;
System.out.println("a=" + a + "c=" + c );//a=9,c=8
```

细节1：

```java
// 经典面试题1
int i = 1;
i = i++;//规则使用临时变量temp 
//(1)temp = i;
//(2)i = i + 1;
//(3)i = templ
System.out.println(i);//1

//经典面试题2
//(1)a = a + 1;
//(2)temp = a;
//(3)a = temp;
int a = 1;
a = ++a;
System.out.println(a);//2
```

细节2：

```java
//算数运算符测试
int a = 10;
int b = 20;
int c = a++;
System.out.println(c);//10
System.out.println(b);//20

// c = --b;
// System.out.println(c);//19
// System.out.println(b);//19
c = b--;
System.out.println(c);//20
System.out.println(b);//19
```

细节3：

```java
//练习：假如还有59天放假，问：合几个星期零几天
//定义剩余天数
int days = 59;
//定义星期为七天
int weeks = 7;
int a = days/weeks;
int b = days%weeks;
System.out.println("合" + a + "个星期零" + b + "天");

//定义一个变量保存华氏温度，华氏温度转换摄氏温度的公式为：
// 5/9*（华氏温度-100），请求出华氏温度对应的摄氏温度。【234.5】
//思路：
//定义一个变量保存华氏温度
//定义一个摄氏温度变量接收华氏温度转换后结果
double fahrenheit = 234.5;
double centigrade = 5.0 / 9 * (fahrenheit - 100);
System.out.println(fahrenheit + "华氏温度对应的摄氏温度为" + centigrade);
```



#### 	2.关系运算符

![image-20220710141852083](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062247475.png)

细节1：

​		1）关系运算符的结果都是boolean类型，也就是要么是true、要么是false

​		2）关系运算符组成的表达式，我们称之为关系表达式。例如 a > b

​		3）比较运算符"=="不能误写成”=“

```java
//比较运算符（关系运算符）
int a = 9;//开发中不可用a、b之类代替，要有实际意义
int b = 8;
System.out.println(a > b);//true
System.out.println(a >= b);//true
System.out.println(a <= b);//false
System.out.println(a < b);//false
System.out.println(a == b);//fasle
System.out.println(a != b);//true
boolean flag = a > b;//true
System.out.println(flag);
```



#### 	3.逻辑运算符

![image-20220710143956054](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062248798.png)

![image-20220710144052500](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062248876.png)



​		&& 和 &基本规则

| 名称      | 语法           | 特点                                      |
| --------- | -------------- | ----------------------------------------- |
| 短语与 && | 条件1 && 条件2 | 两个条件都为true，结果为true，否则为false |
| 逻辑与 &  | 条件1 & 条件2  | 两个条件都为true，结果为true，否则为false |

​		&& 和 & 使用区别

​		1）&&短路与：如果第一个条件为false，则第二个条件不再判断执行，结果为false，效率高

​		2）& 逻辑与：不管第一个条件是否为false，第二个条件都会执行判断，效率低

​		3）开发中，基本使用短路与&&，效率高

```java
//短路与&& 逻辑与&演示
int a = 4;
int b = 9;

//对于短路与而言，如果第一个条件为false，后面的语句不再执行判断
if (a < 1 && ++b <50) {
    System.out.println("ok123");
}

System.out.println(a);//4
System.out.println(b);//9

//对于逻辑与而言，如果第一个条件为false，后面的语句继续执行判断
if (a < 1 & ++b <50) {
    System.out.println("ok123");
}

System.out.println(a);//4
System.out.println(b);//10
```

​		|| 和 | 基本规则

| 名称        | 语法             | 特点                                              |
| ----------- | ---------------- | ------------------------------------------------- |
| 短路或 \|\| | 条件1 \|\| 条件2 | 两个条件中只要有一个成立，结果为true，否则为false |
| 逻辑或 \|   | 条件1 \| 条件2   | 两个条件中只要有一个成立，结果为true，否则为false |

​		|| 和 | 使用区别

​		1）短路或 ||：如果第一个条件为true，则第二个条件不再判断

​		2）逻辑或 |：不管第一个条件是否为true，第二个条件都要判断

​		3）开发中，基本使用 ||



​		！取反与 ^ 逻辑异或

```java
// ! 操作是取反 
System.out.println(60 > 20);
System.out.println(!(60 > 20));

//a^b:逻辑异或，当a和b不同时，则结果为true，否则为false
boolean b = (10 > 1) ^ (3 > 5);
System.out.println(b);//true
```

​		练习：

```java
//逻辑运算符练习
int x = 5;
int y = 5;
if (x++ == 6 & ++y == 6) {
    x = 11;
}
System.out.println(x,y);//6,6

int x = 5,y = 5;
if (x++ == 6 && ++y == 6) {
    x = 11;
}
System.out.println(x,y);//6,5

int x = 5,y = 5;
if (x++ = 5 | ++y = 5) {
    x = 11;
}
System.out.println(x,y);//11,6

int x = 5,y = 5;
if (x++ = 5 || ++y = 5) {
    x = 11;
}
System.out.println(x,y);//11,5
```

​		练习2：

```java
boolean x = true;
boolean y = false;
short z = 46;
if ((z++ == 46 && (y = true))) {//!!!注意 == 与 = 配合使用时相区分 
    z++	
}
if ((x = false) || (++z == 49)) {
    z++
}
System.out.println(z);//50
```



#### 	4.赋值运算符

​		赋值运算符就是将某个运算后的值，赋给指定的变量。

​		赋值运算符的分类：

​		<span style="color:red">基本赋值运算符</span>：=

​		<span style="color:red">复合赋值运算符</span>：+= 、-=、*=、/=、%=等，a += b => a = a +b;

```java
//
int n1 = 10;
n1 += 4;//n1 = n1 + 4;
System.out.println(n1);//14
n1 /= 3;//n1 = n1 / 3;
System.out.println(n1);//4

//复合赋值运算符
//会进行类型转换
byte b = 2;
b += 2;//等价于 b = (byte)(b + 2)
```



#### 	5.三元运算符

​		<span style="color:red">条件表达式 ？ 表达式1 ： 表达式2</span>

​		1.如果条件表达式为true，运算后结果是表达式1

​		2.如果条件表达式为false，运算后结果是表达式2

```java
//演示三元运算符
int a = 10;
int b = 99;
//解读：
//1.a < b返回true
//2.返回a++，先返回a的值，然后再a+1

int result = a < b ? a++ : b--;
System.out.println("result=" + result);//10
System.out.println("a=" + a);//11
System.out.println("b=" + b);//99
```

细节1：

```java
//三元运算符可以转换成一个if..esle..语句
//表达式1和表达式2要为可以赋给接收变量的类型
//也可以自动转换/或者强制转换
int a = 3;
int b = 8;
int c = a > b ? (int)1.1 : (int)3.4;//ok
double d = a > b ? a : b + 3;//ok,满足int =》 double
```

例题：

```java
//案例：实现三个数的最大值
int a = 1;
int b = 55;
int c =66;

//思路：
//先得到a和b中的最大数，保存到max1
//然后再求出max和c中的最大数,保存到max
int max1 = a > b ? a : b;
int max = max1 > c ? max1 : c;
System.out.println("最大数=" + max);//以后可以有更好的选择，例如冒泡排序
```



#### 	6.运算符优先级

![image-20220710185420220](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062248313.png)

#### 	7.标识符相关

​		标识符：Java对各种变量、方法和类等命名时使用的字符序列称为标识符。

​			凡是可以自己起名的地方都叫标识符 int num1 = 1;

​		<span style="color:red">标识符命名规则（必须遵守）</span>：

​			**1.由26个英文字母大小写、0-9、_或$组成**

​			**2.不可以由数字开头**

​			**3.不可以使用关键字和保留字**

​			**4.Java中严格区分大小写，长度无限制**

​			**5.标识符不能包含空格**

​		<span style="color:red">标识符命名规范（建议遵守）</span>：

​			1.包名：多单词组成时所有字母小写。例aaa.bbb.ccc

​			2.类名、接口名：多单词组成时，所有单词首字母大写。例AaaBbbCcc[大驼峰命名]

​			3.变量名、方法名：多单词组成时，第一个单词首字母小写，第二个单词开始每个单词首字母大写。例xxxYyyZzz[小驼峰命名]

​			4.常量名：所有字母都大写。多单词时用下划线连接：XXX_YYY_ZZZ

​			5.其他见文档

#### 	8.关键字保留字

​		关键字：被Java语言赋予了特俗含义，用做专门用途的字符串。

​		注：<span style="color:red">关键字所有字母皆为小写</span>。

![image-20220710194121650](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062248303.png)

![image-20220710194209874](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062248869.png)

​		保留字：现有Java版本尚未使用，但以后版本可能作为关键字使用。自己命名时要避免使用这些保留字。

```java
byValue、cast、future、 generic、 inner、 operator、 outer、 rest、 var 、 goto 、const
```



#### 	9.键盘输入

```java
//创建一个Scanner类的对象
Scanner myScanner = new Scanner(System.in);

//提醒控制台输入姓名
System.out.println("请输入用户姓名：");
String name = myScanner.next();

//提醒控制台输入年龄
System.out.println("请输入用户年龄：");
int age = myScanner.nextInt();

//提醒控制台输入薪水
System.out.println("请输入用户薪水：");
double salary =  myScanner.nextDouble();

System.out.println("该员工信息如下：");
System.out.println("姓名：" + name + "\n" + "年龄：" + age +
                   "\n" + "薪水：" + salary);
```

![image-20220710202140879](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062248928.png)

#### 	10.进制介绍

​		对于整数，有四种表示方式：

​		1.二进制：0、1，满2进1，以0b或者0B开头

​		2.十进制：0—9，满10进1

​		3.八进制：0—7，满8进1，以数字0开头

​		4.十六进制：0—9及A（10）—F（15），满16进1，以0x或0X开头表示。A—F不区分大小写。

```java
//二进制
int a = 0b1010;
//十进制
int b = 1010;
//八进制
int c = 01010;
//十六进制
int d = 0x10101;
System.out.println(a);//10
System.out.println(b);//1010
System.out.println(c);//520
System.out.println(d);//65793
```

​		图示：

![image-20220710212605088](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062248821.png)

![image-20220710212636462](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062248623.png)



​	<span style="color:red">**进制转换（基本功）**</span>

​		1.二进制——>十进制

​		规则：从最低位（右边）开始，将每个位上的数提取出来，<span style="color:red">乘以2的（位数-1）次方，最后求和</span>

​		例如：将0b1011转换成十进制

​		0b1011 = 1 * 2的（1-1）次方 + 1 * 2的（2-1）次方 + 0 * 2的（3-1）次方 + 1 * 2的（4-1）次方

​					   =1 + 2 + 0 + 8  = 11

​		2.八进制——>十进制

​		规则：从最低位（右边）开始，将每个位上的数提取出来，<span style="color:red">乘以8的（位数-1）次方，最后求和</span>

​		例如：将0234装换成十进制的数

​		0234 = 4 * 8的（1 - 1）次方 + 3 * 8的（2 - 1）次方 + 2 * 8的（3-1）次方 + 0 * 8的（4-1）次方

​				  =4 * 8^0 + 3 * 8^1 + 2  * 8^2 + 0 * 8^3   

​				  =4 + 24 + 128 + 0 = 156

​		3.十六进制——>十进制

​		规则：从最低位（右边）开始，将每个位上的数提取出来，<span style="color:red">乘以16的（位数-1）次方，最后求和</span>

​		例如：将0x23A转换成十进制

​		0x23A = 10 * 16^0 + 3 * 16^1 + 2 * 16^2

​					=10 + 48 + 512

​					= 570

​		4.十进制——>二进制

​		规则：<span style="color:red">将该数不断除以2，直到商为0为止，然后将每步得到的余数倒过来</span>，就是对应的二进制

​		案例：将156转换成二进制

![image-20220710220227271](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062249032.png)

​		5.十进制——>八进制

​		规则：<span style="color:red">将该数不断除以8，直到商为0为止，然后将每步得到的余数倒过来</span>，就是对应的八进制
​		6.十进制——>十六进制

​		规则：<span style="color:red">将该数不断除以16，直到商为0为止，然后将每步得到的余数倒过来</span>，就是对应的十六进制

​		7.二进制——>八进制

​		规则：<span style="color:red">从低位开始，将二进制数每三位一组，转换成对应的八进制数即可</span>

​		8.二进制——>十六进制

​		规则：<span style="color:red">从低位开始，将二进制数每四位一组，转换成对应的十六进制数即可</span>

​		9.八进制——>二进制

​		规则：<span style="color:red">将八进制数每一位，转换成对应的一个3位的二进制数即可。</span>

​		10.十六进制——>二进制

​		规则：<span style="color:red">将十六进制数每一位，转换成对应的一个4位的二进制数即可。</span>

#### 	11.<span style="color:red">源码、反码、补码</span>

​		1）二进制的最高位是符号位：0表示正数，1表示负数

```java
00000000 00000000 00000000 00000001  => 1
10000000 00000000 00000000 00000001  => -1
```

​		2）<span style="color:red">正数的源码、反码、补码都一样（三码合一）</span>

​		3）<span style="color:red">负数的反码 = 负数的原码符号位不变，其他位取反</span>

​		4）<span style="color:red">负数的补码 = 负数的反码 + 1，负数的反码 = 负数的补码 - 1</span>

​		5）0的反码、补码都是0

​		6）java中没有无符号数，换言之，java中的数都是有符号的

​		7）<span style="color:red">计算机以补码的方式来运行的</span>

​		8）<span style="color:red">查看运行结果时，要看他的原码</span>

#### 12.位运算详解

​	Java中共有7个位运算符（&、|、^、~、>>、<<及>>>）



​		& 按位与： 两位全为1，结果为1，否则为0

​		|按位或 ：两位有一个为1，结果为1，否则为0

​		^按位异或：两位一个为0，一个为0，结果为0，否则为0

​		~按位取反：0=>1，1=>0



​		>> 、 << 和 >>> 运算规则

​		1.算数右移>>：低位溢出，符号位不变，并用符号位补溢出的高位

​		2.算数左移<<：符号位不变，低位补0

​		3.逻辑右移（无符号右移）>>>：低位溢出、高位补0

例如：

```java
int a = 1 >> 2;//1 => 00000001 => 00000000 本质是 1 / 2 / 2 = 0
int b = 1 << 2;//1 => 00000001 => 00000100 本质 1 * 2 * 2 = 4
```



​		例题：

```java
//位运算详解 + 原码、反码、补码：
2 & 3 = ？
    //1.先得到2的补码，因为是正数，三码合一，原码=补码
    //2.先得到2 的原码：00000000 00000000 00000000 00000010
    //3.所以2的补码也是：00000000 00000000 00000000 00000010
    //4.同理，3的补码=原码：00000000 00000000 00000000 00000011
    //5.按位&
    //  00000000 00000000 00000000 00000010
    //  00000000 00000000 00000000 00000011
    //——————————————————————————————————————————
    //  00000000 00000000 00000000 00000010
    //因为开头是0，是正数，所以三码合一，结果原码=运算后补码
    //2 & 3 =00000000 00000000 00000000 00000010 = 2
    //结果为2
    System.out.println(2&3);//2

~ -2 = ?
    //1.先得到-2的原码 10000000 00000000 00000000 00000010
    //2. 负数的反码 = 负数的原码符号位不变，其他位取反，所以
    //3.得到-2的反码：11111111 11111111 11111111 11111101
    //4.负数的补码 = 负数的反码 + 1，所以
    //5.得到-2的补码：11111111 11111111 11111111 11111110
    //6.符号~进行取反操作，得到：00000000 00000000 00000000 00000001
    //7.运算后第一个符号位为0，是正数，所以三码合一，即：
    //8.运算结果原码：00000000 00000000 00000000 00000001，即1
    System.out.println(~-2);//1

~2 = ?
    //1.先得到2的原码：00000000 00000000 00000000 00000010
    //2.正数三码合一，即2的补码：00000000 00000000 00000000 00000010
    //3.进行~取反操作：11111111 11111111 11111111 11111111 11111101
    //4.负数的反码 = 负数的补码 - 1，所以
    //5.反码即：11111111 11111111 11111111 11111100
    //6.负数的反码 = 负数的原码符号位不变，其他位取反，所以
    //7.结果原码为：10000000 00000000 00000000 00000011，即-3
```

#### 13.总结作业

```java
-10.5 % 3 = ?
//当a % b中a是小数时，套用公式：a % b = a - (int)a / b * b
-10.5 % 3 = (-10.5) - (-10)/3 * 3 = -10.5 + 9 = -1.5,所得结果是近似值
```



### 3.Java基础—流程控制

​	在程序中，程序运行的流程控制决定程序是如何执行的，是我们必须掌握的，主要有三大流程控制语句。

​		1）顺序控制 ：程序从上到下逐行执行，中间无任何判断和跳转。

​		2）分支控制

​		3）循环控制

#### 1.单分支

![image-20220711132358036](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062249045.png)

​	基本语法：

​		if（条件表达式）{

​				执行代码块;

}

说明：当条件表达式为true时，就会执行{}的代码。如果为fasle，就不执行。如果{}中只有一条语句，可以不用{}

```java
//new一个Scanner类的对象
Scanner myScanner = new Scanner(System.in);

//提醒用户输入
System.out.println("请输入对应年龄：");

//接收控制台输入数据
int age = myScanner.nextInt();

//判断该数据是否大于18岁，输出对应提醒
if (age > 18) {
    System.out.println("你的年龄大于18，要对自己的行为负责");
}
```



#### 2.双分支

![image-20220711134144551](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062249672.png)

​		if（条件表达式）{

​				执行代码块1;

  		}else{

​				执行代码块2;

​		}

```java
//判断该数据是否大于18岁，输出对应提醒
if (age > 18) {
    System.out.println("你的年龄大于18，要对自己的行为负责");
}else{
    System.out.println("你的年龄不大，这次就放过你了");
}
```

例题1：

```java
//编写程序，声明两个double类型变量并赋值。判断第一个数大于10.0，
//且第二个数小于20.0，打印两数之和。
double a = 17.8;
double b = 13.5;
if (a > 10.0 & b < 20.0) {
    double c = a + b;
    System.out.println("两数之和为："+ c);
}
```

例题2：

```java
//定义两个变量int，判断二者的和是否能被3又能被5整除，打印提示信息。
int a = 7;
int b = 8;

int c = a + b;
if (c % 3 == 0 && c % 5 == 0) {
    System.out.println("两个变量的和能被3又能被5整除");
}else{
    System.out.println("不能");
}
```

例题3：

```java
//判断一个年份是否是闰年，闰年的条件是符合下面二者之一：
//1）年份能被4整除，但不能被100整除
//2）能被400整除

//new一个Scanner类的对象
Scanner myScanner = new Scanner(System.in);

//提示输入
System.out.println("请输入年份：");

//定义一个变量接收控制台输入年份
int years = myScanner.nextInt();

//判断是否是闰年
if (years % 4 == 0 && years % 100 != 0) {
    System.out.println(years + "年是闰年");
}else{
    if (years % 400 == 0) {
        System.out.println(years + "年是闰年");
    }else{
        System.out.println(years + "年不是闰年");
    }
}
```



#### 3.多分支

![image-20220711143913200](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062249324.png)

​	说明：

​	1）当条件表达式1成立时，即执行代码块1。

​	2）如果条件表达式1不成立，才去判断条件表达式2是否成立，以此类推。

​	3）如果所有条件表达式都不成立，则执行else代码块。只能有一个执行入口。

```java
/*
		输入马保国同志的芝麻信用分
		如果：
		信用分为100分时，输出 信用极好；
		信用分为（80，90】时，输出 信用优秀
		信用分为【60，80】时，输出 信用一般
		其他情况，输入 信用不及格
		请从键盘输入保国的芝麻信用分，并加以判断
		*/

//new一个Sacnner类的对象
Scanner myScanner = new Scanner(System.in);

//提醒用户输入
System.out.println("请输入马保国同志的芝麻信用分(1-100)：");

//接收用户输入数据
int grade = myScanner.nextInt();

//判断
if (grade >=0 && grade <= 100) {

    if (grade == 100) {
        System.out.println("信用极好");
    }else if (grade > 80 && grade <= 99) {
        System.out.println("信用优秀");
    }else if (grade >= 60 && grade <= 80) {
        System.out.println("信用一般");
    }else{
        System.out.println("信用不及格");
    }
}else{
    System.out.println("请输入正确是数据：");
}
```



#### 4.嵌套分支

例题：

```java
import java.util.Scanner;

public class If05{
    public static void main(String[] args) {
        //出票系统：根据淡旺季的月份和年龄，打印票价。
        //4—10 旺季：成人（18-60）：60
        //   		儿童:(<18) :半价
        //          老人（>60）：1/3

        //淡季：成人：40
        //     其他：20

        //先分离淡旺季
        //在旺季内区分三种票价
        //在淡季内区分两种票价

        //定义旺季成人票价
        int price = 60;

        //定义淡季成人票价
        int price1 = 40;


        //创建一个Scanner类的对象
        Scanner myScanner = new Scanner(System.in);

        //提示输入月份
        System.out.println("请输入对应月份：");
        //接收月份数据
        int months = myScanner.nextInt();
        if (months > 4 && months < 10) {
            //接收客户年龄
            System.out.println("现为旺季。请输入客户年龄：");
            int age = myScanner.nextInt();
            if (age >= 18 && age < 60) {
                System.out.println("该客户年龄为：" + age + ",票价为：" + price);				
            }else if (age < 18 && age >= 0) {
                int price2 = price / 2;
                System.out.println("该客户年龄为：" + age + ",票价为：" + price2);
            }else if(age >= 60 && age <= 200){
                int price3 = price / 3;
                System.out.println("该客户年龄为：" + age + ",票价为：" + price3);
            }else{
                System.out.println("请输入正确的年龄！");
            }
        }else if((months >= 1 && months <4)||(months >= 11 && months <= 12)  ){
            System.out.println("现为淡季。请输入客户年龄：");
            int age = myScanner.nextInt();
            if (age >= 18 && age < 60) {
                System.out.println("该客户年龄为：" + age + ",票价为：" + price1);
            }else if((age >= 0 && age <18) || (age >= 60 && age <= 200)){
                int price5 = price1 / 2;
                System.out.println("该客户年龄为：" + age + ",票价为：" + price5);
            }else{
                System.out.println("请输入正确的年龄！");
            }
        }else{
            System.out.println("请输入正确的月份！");
        }
    }
}
```



#### 5.switch循环

```java
基本语法：

    switch(表达式){
        case 常量1:
            语句块1;
            break;
            ....
        default:
        default语句块;
            break;
    }
```





![image-20220711181447139](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062249442.png)



![image-20220711181908680](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062249636.png)

细节：

​	1）表达式数据类型，应与case后的常量类型一致，或者是可以自动转成可以相互比较的类型。

​	2）<span style="color:red">switch（表达式）中表达式的返回值必须是：（byte、short、int、char、enum、String）</span>

```JAVA
double c = 1.1;
switch(c){
    case 1.1://错误
        System.out.println("ok1");
        break;
}
```

​	3）case子句中的值必须是常量，而不能说变量

​	4）default子句是可选的

​	5）break语句用来在执行完一个case分支后使程序跳出switch语句块。

例题1：

```java
//使用switch把小写类型的char型转换成大写（键盘输入）。
//只转换a、b、c、d、e，其他输出other

//创建Scanner对象
Scanner myScanner = new Scanner(System.in);

//提示用户输入
System.out.println("请输入小写char型（a、b、c、d、e）：");

//接收用户输入
char char1 = myScanner.next().charAt(0);

//switch控制输出
switch (char1) {
    case 'a':
        System.out.println(char1 + "的大写是A");
        break;

    case 'b':
        System.out.println(char1 + "的大写是B");
        break;

    case 'C':
        System.out.println(char1 + "的大写是C");
        break;

    case 'd':
        System.out.println(char1 + "的大写是D");
        break;

    case 'e':
        System.out.println(char1 + "的大写是E");
        break;

    default:
        System.out.println("other");
        break;
}
```

例题2：

```java
//对学生成绩大于60分的，输出“合格”。低于60分的，输出“不合格”。
//输入的成绩不能大于100。

//创建Scanner类的对象
Scanner myScanner = new Scanner(System.in);
//提示用户输入
System.out.println("请输入学生成绩：");
//接收用户输入
int gader = myScanner.nextInt();

//switch判断
if (gader >= 0 && gader <=100) {
    switch (gader / 60) {
        case 1:
            System.out.println("合格");
            break;

        case 0:
            System.out.println("不合格");
            break;
    }
}else{
    System.out.println("请输入正确是成绩！");
}
```

例题3：

```java
//根据用于指定月份，打印该月份所属的季节。
//3、4、5是春季，4、5、6是夏季，9、10、11是秋季，12、1、2是冬季
//提示使用穿透

//创建Scanner类的对象
Scanner myScanner = new Scanner(System.in);
//提示用户输入
System.out.println("请输入一个月份：");
//接收用户输入
int months = myScanner.nextInt();

switch (months) {
    case 12:
    case 1:
    case 2:
        System.out.println(months + "月是冬季");
        break;

    case 3:
    case 4:
    case 5:
        System.out.println(months + "月是春季");
        break;

    case 6:
    case 7:
    case 8:
        System.out.println(months + "月是夏季");
        break;

    case 9:
    case 10:
    case 11:
        System.out.println(months + "月是秋季");
        break;

    default:
        System.out.println("请输入正确的月份：");
```



<span style="color:red">注意！！！if 与switch使用建议</span>

1）如果判断的具体数值不多，而且符合byte、short、int、char、enum、String这六种类型，建议switch

2）其他对区间判断、对结果为boolean类型判断，使用if



#### 6.for循环

​	基本语法：

```java
for(循环变量初始化;循环条件;循环变量迭代){
    循环操作（可以多条语句）;
}
```

说明：1）for关键字，表示循环控制

​			2）for有四要素：循环变量初始化;循环条件;循环变量迭代；循环操作

​			3）循环操作可以有多条语句

​			4）循环操作语句只有一条语句时，{}可以省略，但建议不要省略

```java
//一个简单的for循环
for (int i = 1;i <= 10 ;i++ ) {
    System.out.println("循环输出" + i);
}
```

细节：

​	1）循环条件是返回一个布尔值的表达式

​	2）for循环中的初始化和变量迭代可以写到其他地方，但是两边的分号不能省略。

​	3）循环初始化值可以有多条初始化语句，但要求类型一样，并且中间用逗号隔开。

​		  循环变量迭代也可以有多条变量迭代语句，中间用逗号隔开。

```java
int count = 3;
for(int i = 0,j = 0;i < count;i++,j += 2){
    System.out.println("i=" + i + "j=" + j);
}
```



<span style="color:red">**for编程思想**</span>

1）化繁为简：即将复杂的需求，拆解成简单的需求，逐步完成

2）先死后活：先考虑固定的值，然后转成可以灵活变化的值

例题：

```java
//打印1~100之间所有是9的倍数的整数，统计个数及总和。
int count = 0;
int sum = 0;
int start = 1;
int end = 100;
int times = 9;

for (int i = start;i <= end ;i++ ) {
    switch (i % times) {
        case 0:
            count++;
            sum += i;
            break;
    }
}
System.out.println("个数为:" + a + "总和为：" + sum);//11 594 
```



#### 7.while循环

![image-20220712115327137](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062249784.png)

```java
基本语法：

    循环变量初始化;
    while(循环条件){
    	循环体语句;
    	循环变量迭代;
}
```

1）while循环也有四要素

2）只是四要素放的位置不一样

```java
//演示while循环

int a = 1;//循环变量初始化-1
while (a <= 10) {//循环条件-2
    System.out.println(a);//执行语句-3
    a++;//循环变量迭代-4
}
```

例题：

```java
//打印1——100之间所有能被3整除的数，使用while循环

int i = 1;
while (i <= 100) {
    switch (i % 3) {
        case 0:
            System.out.println(i);
    }
    i++;
}

System.out.println("------------------------");

//打印40——200之间所有的偶数，使用while循环

int a = 40;
while (a <= 200) {
    switch (a % 2) {
        case 0:
            System.out.println(a);
    }
    a++;
}
```



#### 8.do while循环

![image-20220712122221157](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062249448.png)

```java
基本语法：
    do{
        循环体语句;
        循环变量迭代;
    }while(循环条件);
```

```java
//演示do while循环

int i = 1;//循环变量初始化
do{
    System.out.println(i);//循环语句
    i++;//循环变量初始化
}while(i <= 10);//循环条件
```

说明：

1）do while是关键字

2）也有循环四要素，位置不同于其他循环

3）先执行、再判断。至少执行一次

4）最后有一个分号;

5）while与do while区别，举例：要帐

例题：

```java
//如果李三不还钱，则老韩一直释出五连鞭，直到说还钱为止。
//System.out.println("老韩问：还钱吗？y/n");

//创建Scanner对象
Scanner myScanner = new Scanner(System.in);

int i = 1;
char ans = '';
do{
    //提醒用户输入
    System.out.println("老韩问：还钱吗？y/n");
    //接收用户输入
    ans = myScanner.next().charAt(0);
    i++;
}while(ans != 'y');
System.out.println("还钱了");
```



#### 9.<span style="color:red">多重循环</span>

​	将一个循环放在另一个循环体内，就形成了嵌套循环。其中，for、while、do while都可以作为外层循环或内层循环。【建议最多3层嵌套，否则代码可读性太差】

​	实际上，嵌套循环就是把内层循环当成外层循环的循环体。当只有内层循环的循环条件为false时，才会完全跳出内层循环，才可结束外层的当次循环，开始下一次循环。例题如下：

```JAVA
//演示嵌套循环
for (int i = 1;i <= 2;i++ ) {
    for (int j = 1;j <= 3;j++ ) {
        System.out.println("i=" + i + "j=" + j);
    }
}
```

<span style="color:red">**重点例题！！！**</span>

```java
//统计3个班成绩情况，每个班有5名学生，求出各个班的平均分和所有班级的平均分。
//学生成绩从键盘输入
//统计三个班及格人数

//3个班，一个班5个人，从一个班开始,求一个5人班的班级平均分
Scanner myScanner = new Scanner(System.in);

//定义所有班级总分
double sum = 0.0;
//定义及格人数
int pass = 0;
//定义班级个数
int classConent = 3;
//定义每个班班级人数
int classNum = 5;


for (int a = 1;a <= classConent;a++ ) {
    //定义变量统计一个班的总分
    double sumone = 0.0;

    for (int i = 1;i <= classNum;i++ ) {
        //提醒用户输入
        System.out.println("请输入第" + a +"个班的第" + i + "个人的分数");
        //接收数据
        double grade = myScanner.nextDouble();
        if (grade >= 60.0) {
            pass++;
        }
        //计算一个班总分
        sumone += grade;
    }
    //计算所有班级总分
    sum += sumone;
    System.out.println("第" + a + "个班的班级总分为：" + sumone +
                       ",平均分为：" + (sumone / classNum) + "\n");
}
System.out.println("所有班级总分为：" + sum + ",平均分为：" +
                   sum / (classNum * classConent) + "及格人数为：" + pass);
```

经典九九乘法表：

```java
//九九乘法表
for (int i = 1;i <= 9;i++ ) {
    for (int j = 1;j <= i;j++ ) {
        System.out.print(j + "*" + i + "=" + i*j + " ");
    }
    System.out.println();
}
```

![image-20220712162752648](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062249269.png)

关注print与printlln的区别！

**<span style="color:red">重要例题</span>：**

```java
/*打印一个空心金字塔，如下
		     *
	        * *
	       *   *
	      *     *
	     *********

		思路分析：化繁为简
		1.先打印一个矩形
		*****
		*****
		*****
		*****
		*****
		2.再打印半个金字塔
		*					第一层 1个*
		**					第二层 2个*
		***					第三层 3个*
		****				第四层 4个*
		*****				第五层 5个*
		3.打印整个金字塔
		     *              第一层 1个*		2 * 1 - 1 
	        ***        		第二层 3个*		2 * 2 - 1	
	       *****			第三层 5个*		2 * 3 - 1
	      *******			第四层 7个*		2 * 4 - 1
	     *********			第五层 9个*		2 * 5 - 1
		4.打印空心金字塔
		     *              第一层 1个*      当前行第一个位置是*，最后一个位置也是*
	        * *				第二层 2个*		当前行第一个位置是*，最后一个位置也是*
	       *   *			第三层 2个*		当前行第一个位置是*，最后一个位置也是*
	      *     *			第四层 2个*		当前行第一个位置是*，最后一个位置也是*
	     *********			第五层 9个*		全部输出*
		5.先死后活
		*/

//定义层数
int num = 10;

for (int i = 1;i <= num;i++ ) {

    for (int k = 1;k <= num - i ;k++ ) {
        System.out.print(" ");
    }

    for (int j = 1;j <= 2 * i - 1;j++ ) {
        if ((j == 1 || j == 2 * i - 1) || i == num) {
            System.out.print("*");
        }else{
            System.out.print(" ");
        }

    }
    System.out.println("");
}
```

![image-20220712194452011](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062250881.png)

#### 10.break

![image-20220712201100767](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062250312.png)

​	基本介绍：

​	break语句用于终止某个语句块的执行，一般使用在switch或者其他循环中。break;  如上所示：

​	break语句出现在多层嵌套的语句块中时，可以通过标签指明要终止的是哪一层语句块。

```java
//标签的使用
	label1 :{  ...
        label2:{  ...
            label3:{ ...
                break label1;
            }
        }
    }
```

​	细节：

​	1）break语句可以指定退出哪层

​	2）label是标签，名字由程序员指定

​	3）break后指定到哪个label就退出哪里

​	4）<span style="color:red">在实际开发中，尽量不要使用标签</span>

​	5）如果没有指定break，默认推出最近的循环体。

例题：

```java
//1-100以内的数求和，求出当和第一次大于20的当前数【for+break】
//化繁为简 ，求和，和大于20

//定义变量sum求和
int sum = 0;

for (int i = 1;i <= 100;i++ ) {
    sum += i;
    if (sum > 20) {
        System.out.println("当和第一次大于20的当前数是：" + i);
        break;
    }
}
// System.out.println(sum);
```

```JAVA
//实现登录验证，有3次机会，如果用户名为"丁真"，密码为666提示登录成功。
//否则提示还有几次机会，请使用for+break完成。

//创建Scanner对象
Scanner myScanner = new Scanner(System.in);

//定义用户名
String str = "";
//定义密码
String pwd = ""; 
//定义可用次数
int sum = 3;

//提示输入
for (int i = 1;i <= sum ;i++ ) {
    //提醒用户输入用户名
    System.out.println("请输入用户名：");
    //接收用户名
    str = myScanner.next();	
    // System.out.println(str);		

    //提醒用户输入密码
    System.out.println("请输入密码：");
    //接收密码
    pwd = myScanner.next();
    // System.out.println(pwd);

    if ("丁真".equals(str) && "666".equals(pwd)) {
        System.out.println("您已登录成功！");
        break;
    }else{
        System.out.println("你还有" + (sum - i) + "次机会！");
    }

}
```



#### 11.continue

基本介绍：

1）continue语句用于结束本次循环，继续执行下一轮循环。

2）continue语句出现在多层嵌套的循环语句中时，可以通过标签指明要跳的是哪层循环，与break标签一致。

```java
基本语法：
{   ...
    continue;
}   ...
```

```java
//continue演示：
lablel1:
for (int j = 0;j < 2 ;j++ ) {
    lablel2:
    for (int i = 0;i < 10 ;i++ ) {
        if (i == 2) {
            continue lablel1;
        }
        System.out.println(i);//[0,1][0,1]
    }
}
```



#### 12.return

return使用在方法。表示跳出所在的方法，在讲解方法的时候，会详细介绍

注意：如果return写在mian方法，会退出程序

#### 13.重点例题

```java
//某人有100000元，每经过一次路口，需要缴费，规则如下：
//当现金>50000时，每次缴5%
//当现金<=50000时，每次缴1000
//编程计算该人可以经过多少次路口，要求使用while break完成

//三种情况：if语句
//目的：次数
//条件：现金

//定义现金
double money = 100000;

//定义次数
int sum = 0;

while (true) {
    if (money > 50000) {
        // money = money - money * 0.05;
        money *= 0.95;
        sum++;
    }else if (money >= 1000) {
        money -= 1000;
        sum++;
    }else{
        break;
    }
}
System.out.println(sum);
```

```java
//实现判断一个整数，属于哪个范围：大于0；小于0；等于0；
Scanner myScanner = new Scanner(System.in);
System.out.println("请输入一个整数：");
int integ = myScanner.nextInt();
if (integ > 0 ) {
    System.out.println("大于0");
}else if(integ < 0){
    System.out.println("小于0");
}else{
    System.out.println("等于0");
}
```

```java
//判断一个整数是否是水仙花数，所谓水仙花数是指一个3位数，
//其各个位上的数字立方和等于其本身。例如：153 = 1*1*1+5*5*5+3*3*3
int integ = 153;

//定义百位
int a = integ / 100;
//定义十位
int b = integ % 100 /10;
//定义十位
int c = integ % 10;

if (integ == a*a*a + b*b*b + c*c*c) {
    System.out.println(integ + "是水仙花数");
}else{
    System.out.println(integ + "不是水仙花数");
}
```

```java
//输出1-100之间的不能被5整除的数，每五个一行

int count = 0;
for (int i = 1;i <= 100 ;i++ ) {

    if (i % 5 != 0) {
        System.out.print(i + " ");
        count++;

        if (count % 5 == 0) {
            System.out.println("\n");
        }
    }
}
```

```java
//输出小写的a-z以及大写的Z-A
//思路：
//小写a-z 化为字符对应的数字 ？-？
//大写z-A 化为字符对应的数字 ？-？

int startSmall = 'a';//97
int endSmall = 'z';//122
int startBig = 'Z';//90
int endBig = 'A';//65

// System.out.println("小写a对应数字为：" + endSmall);
// System.out.println("小写z对应数字为：" + startSmall);
// System.out.println("大写Z对应数字为：" + startBig);
// System.out.println("大写A对应数字为：" + endBig);

System.out.println("小写的a-z:");
for (int i = startSmall; i <= endSmall ;i++ ) {
    System.out.print((char)i + " ");
}

System.out.println("\n" + "大写的Z-A:");
for (int j = startBig;j >= endBig ;j-- ) {
    System.out.print((char)j + " ");
}
```

```java
//求出1-1/2+1/3-1/4...1/100的和
//+1/1 -1/2 +1/3...
//1/1 + 1/3 + ... -1/2-1/4

//拆解公式
double con1 = 1.0;
double zhenshu = 0;
double fushu = 0;

for (int i = 1;i <= 100;i++ ) {
    if (i % 2 == 0) {
        fushu += (con1 / i);
    }else{
        zhenshu += (con1 /i);
    }
}
double sum = zhenshu + (fushu * (-1));
System.out.println("1-1/2+1/3-1/4...1/100的和" + sum);
```

```java
//求1 + (1+2) + (1+2+3)+ ...+(1+2+3+..+100)的和
//
//for

int sum = 0;
int con = 0;

for (int i = 1;i <= 100 ;i++ ) {
    for (int j = 1;j <= i ;j++ ) {
        sum += j;
    }
}
System.out.println(sum);
```



### 4.Java基础—数组

#### 1.数组必要性

​	一个农场有六只鸡，他们的体重分别是3kg、5kg、1kg、3.4kg、2kg、50kg。

​	请问这六只鸡的总体重是多少？平均体重是？

```java
double a = 3;
double b = 5;
double c = 1;
double d = 3.4;
double e = 2;
double f = 50;
```

​	传统思路：定义六个变量，先加起来后平均。

​	现在引出——数组！

数组实现上述问题：

```java
//数组实现
double[] chicken = {3,5,1,3.4,2,50};

//总体重
double con = 0;

for (int i = 0;i < chicken.length ;i++ ) {
    con += chicken[i];
}
System.out.println("总体重是：" + con + "平均体重是：" +
                   con / chicken.length );
```

#### 2.数组使用

方式1——<span style="color:red">动态初始化</span>

1）数组的定义

数据类型 数组名[] = new 数据类型[大小]

```java
int array[] = new int[5];//创建了一个数组，名字为array，存放5个int
```

2）数组的引用

数组名[下标/索引/index]

```java
array[2]；//数组的第三个数，从0开始
```

3）案例：

循环输入5个成绩，保存到double数组并输出。

```java
//循环输入5个成绩，保存到double数组，并输出

//拆解：数组接收
//循环输出
Scanner myScanner = new Scanner(System.in);

//定义数组
double array01[] = new double[5];

for (int i = 0;i < array01.length ;i++ ) {
    //提示输入
    System.out.println("请输入第" + (i + 1) + "个数：");
    //放入数组
    array01[i] =  myScanner.nextDouble();
}

for (int j = 0;j < array01.length ;j++ ) {
    System.out.println("第" + (j + 1) + "个数为：" + array01[j]);
}
```

方式2——<span style="color:red">动态初始化</span>

1）声明数组

数据类型 数组名[]; 或 数据类型[]  数组名;

```java
int array[];//或者int[] array; 
```

2）创建数组（分配内存空间）

数组名 = new 数据类型[大小]；

```java
array = new int[3];
```

方式3——<span style="color:red">静态初始化</span>

1）初始化数组

数据类型 数组名[] = {元素值,元素值...}

```java
double[] chicken = {3,5,1,3.4,2,50};
```



#### 3.注意事项

​	1）数组是多个相同类型数据的组合，实现对这些数据的统一管理

```java
double[] chicken = {3,5,1,3.4,2,50};
String str[] = {"sdas","asda","dasdas"}; 
```

​	2）数据中的元素可以是任何数据类型，包括基本类型和引用类型，但是不能混用

```java
String str[] = {"sdas","asda","dasdas",'c'}; //报错
```

![image-20220713171433671](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062250324.png)

​	3）<span style="color:red">数组创建后，如果没有赋值，有默认值：int 0、short 0、byte 0、long 0、float 0.0、double 0.0、char \u0000、boolean false、String null</span>

​	4）使用数组的步骤：1.声明数组并且开辟空间 2.给数组各个元素赋值 3.使用

​	5）数组下标从0开始

​	6）数组下标必须在指定范围内使用，否则报：下标越界异常。

```java
int array[] = {1,2,3,3};
System.out.println(array[4]); 
```

![image-20220713172138052](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062250704.png)

​	7）数组属于引用类型，数组型数据是对象object

#### 4.例题：

```java
//创建一个char类型的26个元素的数组，分别放置'A'-'Z'.
//使用for循环访问所有元素并打印出来。提示：char类型数据运算'A'+1 --> 'B'

//化繁为简 放置'A'
//定义开始的数
int start = 'A';

//定义数组
char array[] = new char[26];

//放入数据
for (int i = 0 ;i < array.length;i++ ) {
    array[i] = (char)(start + i);
    System.out.println("第" + (i+1) + "个元素为：" + array[i]);
}
```

```java
//请求出一个数组int[]的最大值{4,-1,9,10,23},并得到对应的下标

//定义数组
int ary[] = {4,-1,9,10,23,888,21,666,23};

int max = ary[0];
int maxIndex = 0;

for (int i = i;i < ary.length ;i++ ) {
    if (max < ary[i]) {
        max = ary[i];
        maxIndex = i;
    }
}
System.out.println("最大值为：" + max + "下标为：" + maxIndex);
```



#### 5.数值赋值

​	1）基本数据类型赋值，这个值就是具体的数据，而且相互不影响。

​	2）数组在默认情况下是引用传递，赋的值是地址。

```java
//基本数据类型赋值，赋值方式为值拷贝
//n2的变化不会影响到n1的值
int n1 = 12;
int n2 = n1;

n2 = 14;
System.out.println("n1:" + n1);//12
System.out.println("n2:" + n2);//14

//数组在默认情况下是引用传递，赋的值是地址，赋值方式为引用赋值
int ary1[] = {1,2,3};
int ary2[] = ary1;

ary2[1] = 4;
System.out.println("ary1:" + ary1[1]);//4
```

![image-20220714105425775](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062250214.png)

#### 6.数组拷贝

```java
//实现数组拷贝
int ary1[] = {10,20,30};

int ary2[] = new int[ary1.length];

for (int i = 1;i < ary1.length ;i++ ) {
    ary2[i] = ary1[i];
}
```



#### 7.数组反转

```java
//数组反转
int ary1[] = {1,2,3,4,5,6};

//第一种方式：
int temp = 0;
for (int i = 0;i < ary1.length / 2  ;i++ ) {
    temp = ary1[ary1.length - 1 - i];
    ary1[ary1.length - 1 - i] = ary1[i];
    ary1[i] = temp;
}
for (int i = 0;i <ary1.length ;i++ ) {
    System.out.println(ary1[i]);
}

//第二种方式
int ary2[] = new int[ary1.length];

//逆序遍历
for (int i = ary1.length - 1,j = 0;i >= 0 ;i--,j++ ) {
    ary2[j] = ary1[i];
} 
ary1 = ary2;
```



#### 8.数值扩容与缩减

```java
//数值扩容
//实现动态的给数组添加元素的效果，实现对数组的扩容
//1）原始使用静态分配int arr[] = {123}
//2）添加元素4，直接放在数组的最后arr = {1,2,3,4}
//3）用户可以通过如下方法来决定是否继续添加，添加成功，是否继续?y/n

Scanner myScanner = new Scanner(System.in);

//定义添加元素
int add1 = 0;

//定义数组
int arr[] = {1,2,3};

//是否继续
char yn = ' ';

do{
    int ary1[] = new int[arr.length + 1];

    for (int i = 0;i < arr.length ;i++ ) {
        ary1[i] = arr[i];
    }

    System.out.println("请输入添加元素：");
    //接收
    add1 = myScanner.nextInt();
    ary1[ary1.length - 1] = add1;
    arr = ary1;

    //显示数组
    for (int i = 0;i < arr.length ;i++ ) {
        System.out.print(arr[i]);
    }

    System.out.println("添加成功，是否继续？y/n");
    yn = myScanner.next().charAt(0);
    if (yn == 'y' || yn == 'n') {
        if (yn == 'n') {
            break;
        }
    }else{
        System.out.println("请输入正确的选择！");
        break;
    }
}while(true);
```

```java
//数组缩减
//有一个数组{1,2,3,4,5},可以将该数组进行缩减，
//提示用户是否继续缩减，每次缩减最后一个元素。
//当只剩下最后一个元素，提示，不能再缩减。

//定义数组
int ary1[] = {1,2,3,4,5};

//创建Scanner对象
Scanner myScanner = new Scanner(System.in);

//缩减，造一个新数组，长度等于原数组长度-1，复制粘贴
do{
    int ary2[] = new int[ary1.length - 1 ];

    //copy
    for (int i = 0;i < ary2.length ;i++ ) {
        ary2[i] = ary1[i];
    }

    ary1 = ary2;

    //输出现在数组的数量
    System.out.print("数组现在如下所示：");
    for (int i = 0;i < ary1.length ;i++ ) {
        System.out.print(ary1[i]);
    }

    //询问需否继续删减
    System.out.println("是否继续删减？y/n");
    char whe = myScanner.next().charAt(0);

    if (whe == 'n') {
        break;
    }

}while(ary1.length >= 2);

System.out.println("不能再缩减");
```

![image-20220714155959470](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062250747.png)



![image-20220714160123102](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062250850.png)

#### 9.排序

排序是将多个数据，依指定的顺序进行排列的过程。

1）内部排序

指将需要处理的所有数据都加载到内存存储器中进行排序。包括（交换式排序法、选择式排序法、插入式排序法）

2）外部排序法

数据量过大（例如大数据），无法全部加载到内存中，需要借助外部存储进行排序。包括（合并排序法和直接合并排序法）

​	冒泡排序

通过对待排序序列从后向前（从下标较大的元素开始），依次比较相邻元素的值，若发现逆序则交换，使值较大的元素逐渐从前移向后部，就像水底下的气泡一样逐渐向上向前冒出。

#### 10.冒泡排序

![image-20220714163218323](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062250482.png)

```java
//演示冒泡排序
//将五个无序整数使用冒泡排序24,69,80,57,13 从小到大排序

int ary[] = {24,69,80,57,13};

int temp = 0;

for (int j = 0;j < ary.length - 1 ;j++ ) {
    for (int i = 0;i < ary.length - 1 - j ;i++ ) {
        if (ary[i] > ary[i+1]) {
            temp = ary[i+1];
            ary[i+1] = ary[i];
            ary[i] = temp;
        }
    }
}
for (int i = 0;i < ary.length ;i++ ) {
    System.out.print(ary[i] + " ");
}
```

#### 11.查找

​	在Java中，我们常用的查找有两种：

1）顺序查找

2）二分查找（二分法）

```java
//演示顺序查找
//有一个数列：白眉鹰王、金毛狮王、紫衫龙王、青翼蝠王
//从键盘中任意输入一个名称，判断数列中是否包含此名称【顺序查找】
//要求：如果找到了，就提示找到，并给出下标值。
//化繁为简：
//定义数列
String str[] = {"白眉鹰王","金毛狮王","紫衫龙王","青翼蝠王"};

//创建Scanner对象
Scanner myScanner = new Scanner(System.in);

//判断用
boolean jud = false;

//提示用户输入
System.out.println("请输入：（白眉鹰王、金毛狮王、紫衫龙王、青翼蝠王）");
//接收
String ans = myScanner.next();

for (int i = 0;i < str.length ;i++ ) {
    if (ans.equals(str[i])) {
        System.out.println("找到了" + "下标值为：" + i);
        jud = true;
    }
}
if (jud == false) {
    System.out.println("没有找到");
}
```



#### 12.二维数组

1）从定义上来看 int【】【】

2）可以这么理解，原来的一维数组的每个元素是一对数组，就构成二维数组

```JAVA
//二维数组
//开发一个五子棋游戏，棋盘需要二维数组来表示。
/*
		0 0 0 0 1 0
		1 0 0 0 0 0
		0 0 0 0 0 1
		0 1 0 0 1 0
		*/

//定义一个二维数组
int wuziqi[][] = {{0,0,0,0,1,0},
                  {1,0,0,0,0,0},
                  {0,0,0,0,0,1},
                  {0,1,0,0,1,0}};
for (int i = 0;i < wuziqi.length ;i++ ) {
    for (int j = 0;j < wuziqi[i].length ;j++ ) {
        System.out.print(wuziqi[i][j] + " ");
    }
    System.out.println();
}
//1）二维数组的每个元素是一维数组，所以如果需要得到每个一维数组的值，还需要每次遍历
//2）如果需要访问第（i+1）个一维数组的第（j+1）个值 arr[i][j]
System.out.println("第3个一维数组的第4个值=" + arr[2][3]);
```



​	**使用方式1：动态初始化**

1）语法：类型[ ] [ ] 数组名 = new 类型[大小] [大小]

2）比如：int a[ ] [ ] =new int[2] [3]

![image-20220714214031890](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062358686.png)

**使用方式2：动态初始化**

1）先声明：类型 数组名【】【】；

2）在定义（开辟空间）数组名 = new 类型【大小】【大小】

3）赋值，有默认值，比如int 类型的就是0

4）使用演示

```java
//二维数组———动态初始化
int ary[][] = new int[4][4];-------第一种方式

    int ary[][];-----------------------第二种方式
    ary = new int[4][4];

ary[2][2] = 8;

for (int i = 0;i < ary.length ;i++ ) {
    for (int j = 0;j < ary[i].length ;j++ ) {
        System.out.print(ary[i][j]);
    }
    System.out.println(" ");
}


```

```java
//二维数组第三种使用方式
//需求：动态创建下面二维数组，并输出
/*
		1  
		2 2
		3 3 3
		*/
int ary[][] = new int[3][];//---------------使用方式3—动态初始化-列数不确定

for (int i = 0;i < ary.length ;i++ ) {
    //给二维数组下面的一维数组开空间,遍历开空间
    ary[i] = new int[i+1];
    //遍历赋值
    for (int j = 0;j < ary[i].length ;j++ ) {
        ary[i][j] = i + 1;
    }
}

for (int i = 0;i < ary.length ;i++ ) {
    for (int j = 0;j < ary[i].length ;j++ ) {
        System.out.print(ary[i][j]);
    }
    System.out.println(" ");
}
```

![image-20220714221929425](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062250179.png)

使用方式3—动态初始化-列数不确定，如图上

使用方式4—静态初始化

1）定义 ：类型 数组名【】【】 = {{值1}，{值2}，{值3}，...}

例如：

```java
int [][] arr = {{1,2,3},{2,4,5},{100}}
```

解读：

1）定义了一个二维数组

2）arr有三个元素（每个元素都是一维数组）

3）第一个一维数组有3个元素，第二个一维数组有3个元素，第三个一维数组有1个元素

```java
//使用二维数组打印一个10行杨辉三角
/*
		1
		1  1
		1  2  1
		1  3  3  1
		1  4  6  4  1
		1  5  10 10 5  1
		...

		*/
//提示：
//1.第一行有一个元素，第n行有n个元素
//2.每一行的第一个元素和最后一个元素都是1
//2.从第三行开始，对于非第一个元素和最后一个元素的值。
//arr[i][j] = arr[i-1][j] + arr[i-1][j-1];


int arr[][] = new int[10][];

for (int i = 0;i < arr.length ;i++ ) {
    arr[i] = new int[i+1];//第n行有n个元素


    for (int j = 0;j < arr[i].length ;j++ ) {
        if (j ==0 || j ==arr[i].length - 1) {
            arr[i][j] = 1;
        } 
        if (i >= 2 && (j != 0 && j != arr[i].length - 1)) {

            arr[i][j] = arr[i-1][j] + arr[i-1][j-1];
        }
    }
}

for (int i = 0;i < arr.length ;i++ ) {
    for (int j = 0;j < arr[i].length ;j++ ) {
        System.out.print(arr[i][j] + "\t");
    }
    System.out.println(" ");
}
```

细节：

![image-20220714233235959](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062250804.png)

![image-20220714233635514](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062250031.png)

#### 13.总结作业

```java
//已知有个升序的数组，要求插入一个元素，该数组顺序依然是升序，比如：
//[10,12,45,90],添加23后，数组为[10,12,23,45,90]

//思路：先放入最后一个数，再重新排序
//放数:新建一个数组，copy一遍原始数组，数组长度加一
//然后排序
Scanner myScanner = new Scanner(System.in);

//新数组引用赋给旧数组
int ary1[] = {10,12,45,90};

int ary2[] = new int[ary1.length + 1];

for (int i = 0;i < ary1.length ;i++ ) {
    ary2[i] = ary1[i];
}

System.out.println("请输入新增数据：");
int addData = myScanner.nextInt();
ary2[ary2.length - 1] = addData;

ary1 = ary2;

//排序
for (int i = 0;i < ary1.length - 1 ;i++ ) {
    for (int j = 0;j < ary1.length - 1 - i ;j++ ) {
        if (ary1[j] > ary1[j + 1]) {
            int temp = ary1[j + 1];
            ary1[j + 1] = ary1[j];
            ary1[j] = temp;
        }
    }
}
for (int i = 0;i < ary1.length ;i++ ) {
    System.out.print(ary1[i] + "\t");
}
```

```java
//上面一题第二种解法
//已知有个升序的数组，要求插入一个元素，该数组顺序依然是升序，比如：
//[10,12,45,90],添加23后，数组为[10,12,23,45,90]

//思路：先得到插入数据的下标，再扩容、赋值

//定义原数组
int ary1[] = {10,12,45,90};
//定义插入数据
int ins = 230;
//定义插入数据下标
int insIndex =  0;

//得到插入数据的下标
for (int i = 0;i < ary1.length ;i++ ) {
    if (ary1[i] > ins) {
        insIndex = i;
        break;
    }
}

if (insIndex == 0) {
    insIndex = ary1.length;
}

// System.out.println(insIndex);

//扩容
//定义新数组
int arrNew[] = new int[ary1.length + 1];

//遍历插入数据
for (int i = 0,j = 0;i < arrNew.length ;i++ ) {
    if (i != insIndex) {
        arrNew[i] = ary1[j];
        j++;
    }else{
        arrNew[i] = ins;
    }
}

ary1 = arrNew;

for (int i = 0;i < ary1.length ;i++ ) {
    System.out.println(ary1[i] + "\t");
}
```

![image-20220715104957265](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062251883.png)



```java
//随机生成10个整数（1-100范围）保存到数组，并倒序打印以及求平均值、
//求最大值和最大值的下标，并查找里面是否有8

//需求拆解
//1.随机生成10个整数（1-100范围）
//2.保存到数组
//3.倒序打印
//4.求平均值、求最大值和最大值的下标
//5.查找里面是否有8

int int01;

//计算总数
int con = 0;

//冒泡排序临时变量
int temp = 0;

//是否有8
int sum = 0;

// System.out.println(int01);
int arr[] = new int[10];

for (int i = 0;i < 10 ;i++ ) {
    int01 =  (int)(Math.random() * 100 + 1);
    arr[i] = int01;
}

System.out.println("以下为倒叙打印：");
for (int i = arr.length - 1;i >= 0;i-- ) {
    System.out.print(arr[i] + "\t");
    con += arr[i];
}

//平均值
System.out.println("平均值为：" + con / arr.length);

//最大值与最大值下标
for (int i = 0;i < arr.length - 1 ;i++ ) {
    for (int j = 0;j < arr.length - 1 - i ;j++ ) {
        if (arr[j] > arr[j+1]) {
            temp = arr[i+1];
            arr[j+1] = arr[j];
            arr[j] = temp;
        }
    }
}

System.out.println("排序后：");
for (int i = 0;i < arr.length;i++ ) {
    System.out.print(arr[i] + "\t");
    if (arr[i] == 8) {
        sum++;
        System.out.println("有8");
    }
}

System.out.println("有" + sum + "个8"+",最大值为" +
                   arr[arr.length-1] + ",最大值下标为："  + (arr.length-1));
```

## 3.oop—初级

#### 1.概述入门

看一个问题：

张老太养了两只猫：一只叫做小白，3岁，白色。一只叫做小花，4岁，花色。

编写程序：当用户输入小猫姓名时，显示该猫姓名、年龄、颜色。输入错误，则提示没有这只猫。

以现有技术解决：1）单独的定义变量解决 2）使用数组解决

缺点：不利于数据的管理、效率低-----------------------引出新的内容<span style="color:red">**（类与对象）（oop）**</span>

![image-20220715144153765](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062251533.png)

```JAVA
public class ClassEntry{
    public static void main(String[] args) {
        //类与对象入门
        //实例化对象
        Cat myCat1 = new Cat();
        myCat1.name = "小白";
        myCat1.age = 3;
        myCat1.color = "白色";

        Cat myCat2 = new Cat();	
        myCat2.name = "小花";
        myCat2.age = 5;
        myCat2.color = "花色";

        System.out.println("第一只猫的名字是：" + myCat1.name +
                           ",年龄是：" + myCat1.age + ",颜色是：" + myCat1.color);

    }
}

class Cat{
    String name;
    int age;
    String color;
}
```

![image-20220715151124019](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062251417.png)

#### 2.属性

从概念或语法上看：<span style="color:red">**成员变量 = 属性 = field（字段）**</span>

属性是类的一个组成部分，一般是基本数据类型，也可以是引用数据类型（对象、数组）

1）属性的定义语法同变量，实例：访问修饰符  属性类型  属性名;

​	访问修饰符：public、protected、默认、private

2）属性的定义类型可以为任意类型，包含基本数据类型和引用数据类型

3）<span style="color:red">**属性如果不赋值，有默认值，同数组规则一致：int 0、short 0、byte 0、long 0、float 0.0、double 0.0、char \u0000、boolean false、String null**</span>

4）

```java
Person p1 = new Person();
//p1是对象名（对象引用），new Person()创建的对象空间（数据）才是真正的对象
```



#### 3.对象

如何创建对象：

1）先声明，再创建

```java
Cat cat;//声明对象
cat = new Cat();//创建
```

2）直接创建

```java
Cat cat = new Cat();
```

如何访问属性：

对象名.属性名;

```java
cat.name;
```

对象分配机制：

![image-20220715155600955](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062251420.png)

类与对象的内存分配机制：

​	Java内存结构分析：

1）栈：一般存放基本数据类型（局部变量）

2）堆：存放对象（Cat cat，数组等）

3）方法区：常量池（常量，比如字符串）、类加载信息

​	Java创建对象流程简单分析

```java
Person p = new Person();
p.name = "jack";
p.age = 10;
```

1.先加载Person类信息（属性和方法信息，只会加载一次）

2.在堆中分配空间，进行默认初始化

3.把地址赋给p。p指向对象

4.进行指定初始化

#### 4.方法

​	在某些情况下，我们需要定义成员方法。比如人类：除了有一些属性外（年龄、姓名。。。），我们人类还有一些行为，比如：可以说话、跑步。。。。通过成员方法完成。

```JAVA
public class Method01{
    public static void main(String[] args) {
        //方法（成员方法快速入门）
        Person p = new Person();
        p.Speak();
        p.Cal01();
        p.Cal02(10);
        int con = p.getSum(11,22);
        System.out.println(con);

    }
}

class Person{
    //属性
    String name;
    int age;
    String gender;

    //方法
    public void Speak(){
        System.out.println("输出了");
    }

    //添加cal01成员方法，计算1+...+1000的结果
    public void Cal01(){
        int con = 0;
        for (int i = 1;i <= 1000 ;i++ ) {
            con += i;
        }
        System.out.println("1+...+100的结果是：" + con);
    }

    //添加cal02成员方法，该方法可以接收一个数n，计算从1+...+n的结果
    public void Cal02(int n){
        int con = 0;
        for (int i = 1;i <= n ;i++ ) {
            con += i;
        }
        System.out.println("1+...+" + n + "的结果是：" + con);
    }
    //添加getSum成员方法，可以计算两个数的和。
    public int getSum(int num1,int num2){
        int con = num1 + num2;
        return con;
    }

}
```

#### 5.方法调用机制

![image-20220715172953053](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062251090.png)

使用成员方法的好处：

提高代码复用性

可以将实现的细节封装起来，然后供其他用户调用即可。

```java
public class Method02{
    public static void main(String[] args) {
        //±éÀúÒ»¸öÊý×é£¬Êä³öÊý×éµÄ¸÷¸öÔªËØÖµ
        //int[][] map = {{0,0,1},{1,1,1},{1,1,3}};

        int map[][] = {{0,0,1},{1,1,1},{1,1,3}};

        Ary ary = new Ary();
        ary.Tra(map);
        ary.Tra(map);
        ary.Tra(map);
    }
}

class Ary{
    public void Tra(int map[][]){
        for (int i = 0;i < map.length ;i++ ) {
            for (int j = 0;j < map[i].length ;j++ ) {
                System.out.print(map[i][j]);
            }
            System.out.println();
        }
    }
}
```

成员方法定义：

```java
public 返回数据类型 方法名（形参列表...）{
    语句;
    return 返回值;
}
```

1）形参列表：表示成员方法输入例如：cal（int n）、getSum（int num1,int num2）

2）返回数据类型：表示成员方法输出，void表示没有返回值

3）方法主体：表示为了实现某一功能代码块

3）return语句不是必须的



​	成员方法注意事项：

1.访问修饰符（作用是控制方法使用的范围）

2.一个方法最多有一个返回值，可以返回数组来实现返回多个结果

3.返回类型可以为任意类型，包含基本类型或引用类型（数组、对象）

4.如果方法要求有返回数据类型，则方法体中最后的执行语句必须为return 值;而且要求返回值类型必须与return的值类型一致或兼容。

5.如果方法是void，则方法体中可以没有return语句，或则只写return;

6.方法名 遵循驼峰命名法，最好见名知义。

7.一个方法可以有0个参数，也可以有多个参数，中间用逗号隔开

8.参数类型可以为任意类型，包含基本类型和引用类型。

9.调用带参数的方法时，一定对应着参数列表传入相同类型或兼容类型的参数

10.方法定义时的参数为形式参数，简称形参；方法调用时传入的参数称为实际参数，简称实参。新参和实参的类型要一致或兼容、个数、顺序必须一致。

11.方法体里面写完成功能的具体的语句，可以为输入、输出、变量、运算、分支、循环、方法调用，但里面不能再定义方法！即方法不能嵌套定义！

12.同一个类中的方法调用：直接调用即可。

13.跨类中的方法调用：需要通过对象名调用。

14.特别说明：跨类的方法调用和方法的访问修饰符相关。

```java
public class MethodExercise01{
	public static void main(String[] args) {
		//编写类AA，有一个方法：判断一个数是奇数odd还是偶数，返回boolean。
		AA p = new AA();
		// boolean b = p.judeg(20);
		// System.out.println(b);
		if (p.judeg(5)) {
			System.out.println("偶数");
		}else{
			System.out.println("奇数");
		}
	}
}

class AA{
	public boolean judeg(int a){
		// if (a % 2 == 0) {
		// 	System.out.println(a + "是偶数");
		// 	return true;
		// }else{
		// 	System.out.println(a + "是奇数");
		// 	return false;
		// }

		// return a % 2 == 0 ? true : false;

		return a % 2 == 0;
	}
}
```

```JAVA
public class MethodExercise02{
	public static void main(String[] args) {
		//根据行、列、字符打印对应行数和列数的字符，比如：行：4，列：4，字符 #
		//则打印相应的效果

		Squ s = new Squ();
		s.HangLie(4,4,'#');

	}
}

class Squ{
	public void HangLie(int a,int b,char c){
		for (int i = 0;i < a ;i++ ) {
			for (int j = 0;j < b ;j++ ) {
				System.out.print(c);
			}
			System.out.println();
		}
	}
}
```



#### 6.方法传参

1）基本数据类型，传递的是值（值拷贝），形参的任何改变不影响实参

```java
public void swap(int a,int b){
    int temp = a;
    a = b;
    b = temp;
    System.out.println("a=" +a +"b=" + b);
}
```

![image-20220715214127337](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062251907.png)



2）引用类型传递的是地址，可以通过形参改变实参

![image-20220715215410926](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062251509.png)



克隆对象：

```java
public class MethodExercise03{
	public static void main(String[] args) {
		//编写一个方法copyPerson，可以复制一个Person对象，返回复制的对象
		//注意要求得到的新对象和原来的对象是两个独立的对象，只是他们属性不同。

		Person p = new Person();
		p.name = "milan";
		p.age = 25;

		MyTools m = new MyTools();
		Person p2 = m.copyPerson(p);

		//到此p和p2是Person对象，但是是两个独立的对象
		// System.out.println(p.age);
		// System.out.println(p2.age);

		System.out.println(p.hashCode());
		System.out.println(p2.hashCode());
	}
}

class Person{
	String name;
	int age;
}

class MyTools{
	public Person copyPerson(Person p){
		Person p2 = new Person();
		p2.name = p.name;
		p2.age = p.age;
		return p2;
	}
}
```



#### 7.递归

​	递归，就是在运行的过程中不断地调用自己。递归有两个过程，简单地说一个是递的过程，一个是归的过程。简单用代码来理解：

```java
public void fun(参数) {
    if (终止条件) {
        return;
    }
    fun(参数);
    (其他判断条件或语句);
}
```

​	在上边代码中，当第一次进入函数时，先判断是否符合终止条件，符合则直接结束函数，不符合入下一语句，调用自己重新进入下一层自身函数，(注意这是最外一层将不向下继续执行语句，外层卡在fun（参数处）)，这个调用自己进入自身函数的操作过程即为“递”的过程。假设进入下一层后符合终止条件，返回结果，此时之前进入自身函数执行完成返回最外一层函数，最外一层函数递归调用处得到结果，(即内层函数执行完成得到结果返回值)，这个过程即为“归”的过程。这时最外一层函数才能继续执行下一语句，直至函数运行完成。

​	判断递归使用的场景

1.大问题可以拆分为多个子问题。

2.原问题和拆分后的子问题除了数据规模不同，解决思路完全相同。

3.存在递归终止条件。

递归在线性数据结构中使用不太明显，迭代基本可以很容易地解决问题。

递归在非线性结构中非常重要，比如二叉树，回溯，典型的树形问题-九宫格字母组合

​	递归代码的写法，(一定要注意方法的语义)

递归必须具备两个条件，

- <span style="color:red">一是有边界，即终止条件。</span>
- <span style="color:red">二是需要调用自己。</span>

这两个条件缺一不可，并且其中终止条件语句必须在递归调用语句之前。如果顺序颠倒则递归函数会进入死循环，永远退不出来，会出现堆栈溢出异常(StackOverflowError)。

在递归函数中，终止条件可以不止一个，递归调用也可以通过一些逻辑语句分成好几个。

```java
public class Recursion{
	public static void main(String[] args) {
		//演示递归调用
		Recursions r = new Recursions();
		r.rec(4);
	}
}

class Recursions{
	public void rec(int n){
		if (n > 2) {
			rec(n-1);
		}
		System.out.println(n);//2 3 4
	}
}
```

![image-20220716100539278](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062251882.png)

递归实现斐波那契数：

```java
public class Fibonacci{
	public static void main(String[] args) {
		//递归实现斐波那契
		//需求：使用递归的方式求出斐波那契数1,1,2,3,5,8,13...
		//给你一个整数，求出它对应的斐波那契数是多少

		//思路：从第三个数开始，该数等于前面两个数的和

		//两种情况：前两个数等于1，后面的数等于前面两数之和

		//代码实现：
		T t = new T();
		int sum = t.getFibonacci(6);
		System.out.println(sum);
	}
}

class T{
	public int getFibonacci(int n){
		if (n <= 0) {
			return 0;
		}else if (n == 1 || n ==2) {
			return 1;
		}else{
			return getFibonacci(n-1) + getFibonacci(n-2);
		}
	}
}
```

```java
public class RecursionExercise01{
	public static void main(String[] args) {
		//猴子吃桃的问题
		//有一堆桃子，猴子第一天吃了其中的一半，并再多吃了一个
		//以后每天猴子都吃一半，然后再多吃一个。第10天时，再想吃时发现只有一个桃子。
		//问题：最初有多少个桃子？

		//思路：
		//要素提取：10天 一个
		//
		//这些桃子有一个总数，con
		//

		Peach p = new Peach();
		int con = p.getPeach(1);
		System.out.println(con);

	}
}

class Peach{

	public int getPeach(int days){
		if (days == 10) {
			return 1;
		}else if (days >= 1 && days < 10) {
			return (getPeach(days + 1) + 1) * 2;
		}else{
			return -1;
		}
	}
}
```



#### 8.实例

![image-20220716161305316](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062251142.png)

```java
public class Lab{
	public static void main(String[] args) {
		//迷宫游戏，老鼠找路
		//定义二维数组，模拟迷宫
		int lab[][] =new int[8][7];

		for (int i = 0;i < lab[i].length ;i++ ) {
			lab[0][i] = 1;
			lab[7][i] = 1;
		}

		for (int i = 0;i < lab.length ;i++ ) {
			lab[i][0] = 1;
			lab[i][6] = 1;
		}

		lab[3][1] = 1;
		lab[3][2] = 1;
        //测试回溯
		lab[2][2] = 1;

		//输出
		for (int i = 0;i < lab.length ;i++ ) {
			for (int j = 0;j < lab[i].length ;j++ ) {
				System.out.print(lab[i][j] + " ");
			}
			System.out.println();
		}

		Mouse m = new Mouse();
		m.mouseRun(lab,1,1);

		System.out.println("run---------");
		for (int i = 0;i < lab.length ;i++ ) {
			for (int j = 0;j < lab[i].length ;j++ ) {
				System.out.print(lab[i][j] + " ");
			}
			System.out.println();
		}
	}
}

class Mouse{

	//思路：
	//起点lab[1][1],终点lab[6][5]
	//定义状况：0——可以走，1——障碍物，2——已走过，可走，3——已走过，不可走
	//行走策略：下右上左

	public boolean mouseRun(int[][] lab,int row,int col){
		//已经走到终点
		if (lab[6][5] == 2) {                
			return true;
		}else{                            //尚未走到终点，进行下一步
			if (lab[row][col] == 0) {     //当前位置可以走
				//假定可以走通
				lab[row][col] = 2;

				//按照行走策略来走
				if (mouseRun(lab,row + 1,col)) {        //下
					return true;
				}else if (mouseRun(lab,row,col + 1)) {  //右
					return true;
				}else if (mouseRun(lab,row - 1,col)) {  //上
					return true;
				}else if (mouseRun(lab,row,col - 1)) {  //左
					return true;
				}else{
					lab[row][col] = 3;
					return false;
				}
			}else{            
				return false;
			}
		}
	}
}
```

![image-20220716161656366](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062251241.png)

![image-20220716163513255](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062251717.png)

上图汉诺塔实现：

```java
public class Hannuota{
	public static void main(String[] args) {
		//演示汉诺塔
		Tower t = new Tower();
		t.move(1,'A','B','C');
	}
}

class Tower{

	//num表示要移动的个数，a,b,c分别表示A塔、B塔、C塔
	public void move(int num,char a,char b,char c){
		//如果只有一个盘 num = 1
		if (num == 1) {
			System.out.println(a + "->" + c);
		}else{
			//如果有多个盘，可以看成两个，最下面的和上面的所有盘（num - 1）
			//先移动上面所有的盘到b，借助c
			move(num - 1,a,c,b);
			//把最下面的这个盘，移动到c
			System.out.println(a + "->" + c);
			//再把b塔是所有盘，移动到c，借助a
			move(num - 1,b,a,c);
		}
	}

}
```

![image-20220716165739252](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062251740.png)



#### 9.重载

​	Java中允许同一个类中，多个同名方法的存在，但要求形参列表不一致。

```java
public class OverLoad02{
	public static void main(String[] args) {
		//
		OverLoad ol = new OverLoad();

		int a = ol.getSum(1,2);
		System.out.println(a);
		double b = ol.getSum(1.1,2);
		System.out.println(b);
		int c = ol.getSum(1,2,3);
		System.out.println(c);

	}
}

class OverLoad{
	//
	public int getSum(int a,int b){
		return a + b;
	}
	public double getSum(double a,int b){
		return a + b;
	}
	public int getSum(int a,int b,int c){
		return a + b + c;
	}
}
```

重载(overload) 是在一个类里面，方法名字相同，而参数不同。返回类型可以相同也可以不同。

每个重载的方法（或者构造函数）都必须有一个独一无二的参数类型列表。

最常用的地方就是构造器的重载。

**重载规则:**

- 被重载的方法必须改变参数列表(参数个数或类型不一样)；
- 被重载的方法可以改变返回类型；
- 被重载的方法可以改变访问修饰符；
- 被重载的方法可以声明新的或更广的检查异常；
- 方法能够在同一个类中或者在一个子类中被重载。
- 无法以返回值类型作为重载函数的区分标准。

```JAVA
public class OverloadExercise01{
	public static void main(String[] args) {
		//演示方法重载
		//编写程序：类Methods中定义三个重载方法并调用。方法名为m。三个方法分别接收
		//一个int参数、两个int参数、一个字符串参数。分别执行平方运算并输出结果、相乘
		//并输出结果、输出字符串信息。在主类的main（）方法中分别调用参数区分三个方法。

		Methods m = new Methods();
		System.out.println(m.m(4));
		System.out.println(m.m(1,2));
		System.out.println(m.m("张三"));
	}
}

class Methods{
	public int m(int a){
		return a * a;
	}

	public int m(int a,int b){
		return a * b;
	}

	public String m(String str){
		return str;
	}
}
```

```java
public class OverloadExercise02{
	public static void main(String[] args) {
		//在Methods类，定义三个重载方法max（），
		//第一个方法：返回两个int值中的最大值，
		//第二个方法，返回两个double值中的最大值
		//第三个方法，返回三个double值中的最大值，并分别调用三个方法

		Methods m = new Methods();
		System.out.println(m.Max(1,2));
		System.out.println(m.Max(5.1,2.2));
		System.out.println(m.Max(7.1,2.2,3.3));

	}
}

class Methods{
	public int Max(int a,int b){
		if (a > b) {
			return a;
		}else{
			return b;
		}
	}

	public double Max(double a,double b){
		if (a > b) {
			return a;
		}else{
			return b;
		}
	}

	public double Max(double a,double b,double c){
		/*
        if (a > b) {
			if (a > c) {
				return a;
			}else{
				return c;
			}
		}else{
			if (b > c) {
				return b;
			}else{
				return c;
			}
		}*/
        double max1 = a > b ? a : b;
        return max1 > c ? max1 : c;
	}
}
```



#### 10.可变参数

可变参数
1.概念
可变参数(variable argument)允许你指定可以采用多个同类型参数的方法，而不需要事先确定参数的数目。
2.语法格式
可变参数语法：

```java
访问修饰符 返回类型 方法名(数据类型...形参名){
}
```

3.调用可变参数的方法时, 编译器将自动创建一个数组保存传递给方法的可变参数，因此，程序员可以在方法体中以数组的形式访问可变参数

4.在一个方法参数中只能使用一个省略号；且省略号必须出现在方法中参数列表的最后一个位置。

5.可变参数可以和基本类型的参数一起放在参数列表，但是必须保证可变参数在最后。

<span style="color:red">**注意：可变参数其实就是把多个参数放入数组当中，我们在方法中获取参数就需要遍历数组来获取参数的值。**</span>



```java
public class VarParament{
	public static void main(String[] args) {
		//演示可变参数,int求和
		VarPara vp = new VarPara();
		int con = vp.varParameter(1,2,3,88);
		System.out.println(con);
	}
}

class VarPara{
	public int varParameter(int...nums){
		int con = 0;
		for (int i = 0;i < nums.length ;i++ ) {
			con += nums[i];
		}
		return con;
	}
}
```

```java
public class VarParameterExercise{
	public static void main(String[] args) {
		//有三个方法，分别实现返回姓名和两门课成绩（总分），
		//返回姓名和三门课成绩（总分），返回姓名和五门课成绩（总分）。
		//封装成一个可变参数的方法

		VarParameter vp = new VarParameter();
		System.out.println(vp.varPara("张三",55,66,77));
	}
}

class VarParameter{
	public String varPara(String name,int...grades){
		int con = 0;
		for (int i = 0;i < grades.length ;i++ ) {
			con += grades[i];
		}
		return "姓名：" + name + " "+ grades.length +  "门课总分：" + con;
	}
}
```



#### 11.作用域(重要)

​	面向对象中，变量作用域是非常重要的知识点。

1）在Java编程中，主要的变量就是属性（成员方法）和局部变量。

2）局部变量一般指在成员方法中定义的变量。

3）全局变量：也就是属性，作用域为整个类体。

​	  局部变量：就是除了属性之外的其他变量，作用域为定义它的代码块中。

4）全局变量（属性）可以不赋值，直接使用，因为有默认值，局部变量必须赋值后才能使用，因为没有默认值。

```java
class Cat{

	//全局变量（属性）
	int age;//有默认值：0

	public void run(){
		//局部变量，无默认值
		int age = 0;
	}
}
```

细节：

1）属性和局部变量可以重名，访问时遵循就近原则

2）在同一个作用域中，比如在同一个成员方法中，两个局部变量，不能重名。

3）属性生命周期较长，伴随着对象的创建而创建，伴随着对象的销毁而销毁。

​	  局部变量，声明周期短，伴随这它的代码块执行而创建，伴随着代码块的结束而销毁。

4）全局变量可以被本类使用，或其他类使用

​	  局部变量只能在对应的方法中使用

5）修饰符不同 全局变量（属性）可以加修饰符，局部变量不可以加修饰符

```java
public class VarScope{
	public static void main(String[] args) {
		//演示全局变量（属性）跨类访问
		Dog d = new Dog();
		d.Cry();//第一种跨类访问对象属性方式

		Cat c = new Cat();
		d.Run(c);//第二种跨类访问对象属性方式

	}
}

class Cat{
	String name = "小白";
	int age = 12;
}

class Dog{

	public void Cry(){
		Cat c = new Cat();
		System.out.println(c.name);
	}

	public void Run(Cat c){
		System.out.println(c.age);
	}
}
```



#### 12.构造器

来看一个需求

我们来看一个需求：前面我们在创建人类的对象时，是先把一个对象创建好后，再给他的年龄和姓名赋值，如果现在我们要求，在创建人类对象时，就直接指定这个对象的年龄和姓名，该怎么做？使用构造器。

​	构造器又叫构造方法（constructor），是类的一种特殊的方法，它的主要作用是完成对新对象的初始。

基本语法：

```java
修饰符 方法名(形参列表){
    方法体;
}
```

1）构造器的修饰符可以默认，也可以是public、protected、private

2）构造器没有返回值

3）方法名和类名必须一样

4）参数列表和成员方法一样的规则

5）构造器的使用，由系统完成

6）如果程序员没有定义构造器，系统就会自动给类生成一个默认无参构造器（也叫默认构造器），比如Dog(){},使用javap指令反编译看看

7）一旦定义了自己的构造器，默认的构造器就覆盖了，就不能再使用默认的无参构造器，除非显式的定义一下，即：Dog(){}

```java
public class Constructor01{
	public static void main(String[] args) {
		//演示构造器
		Dog d = new Dog("小白",12);
		System.out.println(d.name);
		System.out.println(d.age);

	}
}

class Dog{

	String name;
	int age;

	//构造器
	public Dog(String Dname,int Dage){
		System.out.println("构造器被调用！");
		name = Dname;
		age = Dage;
	}
}
```

```java
public class Constructor02{
	public static void main(String[] args) {
		//利用构造器设置所有人age属性初始值都为18
		Person p1 =new Person(18);
		System.out.println(p1.age + p1.name);

		//第二个带pName和pAge两个参数的构造器：使得每次创建Person对象
		//的同时初始化对象的age属性值和name属性值。
		Person p2 = new Person("小白",15);
		System.out.println(p2.age + p2.name);
	}
}

class Person{
	String name;
	int age;

	public Person(int Page){
		age = Page;
	}

	public Person(String pName,int pAge){
		name = pName;
		age = pAge;
	}
}
```

对象创建流程分析：

1）加载类信息，只会加载一次

2）在堆中分配空间（地址）

3）完成对象初始化（1.默认初始化 2.显式初始化 3.构造器初始化）

4）对象在堆中的地址返回给对象名

#### 13.this

​	this的类型：哪个对象调用就是哪个对象的引用类型

​	用法总结

1、this：表示自身对象，也就是本对象自己

2、this.属性名：表示本对象自己的属性

3、this.方法名：表示本对象自己的方法

4、this(参数)表示本对象自身的构造方法(注：”构造方法”这个概念是相对于”类”而言的，但具体到this(参数)这种用法时，表示”我这个对象自己的构造方法”)，必须放在第一条语句

5、外部类名.this.属性：表示在内部类中调用的是外部类的某个属性(调用外部类方法亦同)

​	细节：

1）this关键字可以用来访问本类的属性、方法、构造器

2）this用于区分当前类的属性和局部变量

3）this不能在类定义的外部使用，只能在类定义的方法中使用

```java
public class TestPerson{
	public static void main(String[] args) {
		//演示this关键字
		//定义Person类，里面有name、age属性，并提供compareTo比较方法，用于判断是否
		//和另一个人相等，名字和年龄完全一样，就返回
		//true。否则返回false
		Person p1 = new Person("王二",23);
		Person p2 = new Person("王二",23);
		System.out.println(p1.comparaTo(p2));

	}
}

class Person{
	//成员变量（属性）
	String name;
	int age;

	//构造器（构造方法）
	public Person(String name,int age){
		this.name = name;
		this.age = age;
	}

	//比较方法
	public boolean comparaTo(Person p){
		// if (this.name.equals(p.name) && this.age == p.age) {
		// 	return true;
		// }else{
		// 	return false;
		// }

		//简化代码
		return this.name.equals(p.name) && this.age == p.age;
	}
}


```



#### 14.作业

```java
public class Homework01{
	public static void main(String[] args) {
		//编写类A01，定义方法max，实现求某个double数组的最大值，并返回

		//定义一个double数组
		double ary[] = {};
 
		//创建对象
		A01 a = new A01();
		Double dou = a.max(ary);
		if (dou != null) {
			System.out.println("该数组最大值为：" + dou);
		}else{
			System.out.println("请输入至少一个数或不能为null");
		}
	}
}

class A01{

	public Double max(double ary[]){
		//数组求最大值，开始思路

		//判断数组长度大于0
		if (ary != null && ary.length > 0) {
			//假定数组第一个数是最大值
			double max = ary[0];
			//如果数组第二个数比第一个数大，则交换，依此类推
			for (int i = 1;i < ary.length ;i++ ) {
				if (ary[i] > max) {
					max = ary[i];
				}
			}
			return max;
		}else{
			return null;
		}
	}
}
```

```java
public class Homework02{
	public static void main(String[] args) {
		//编写类A02,定义方法find，实现查找某字符串数组中的元素查找，
		//并返回索引，如果找不到，返回-1

		//思路：
		//类A02
		//查找方法find
		//功能：字符串 数组 元素查找
		//返回：索引=数组下标+1
		//如果没有对应数据，返回-1
		//实现代码健壮性

		//定义数组
		String ary[] = {"张三","李四","王五","卡特"};
		A02 a = new A02();
		int ans = a.find(ary,"卡特");
		if (ans != -1) {
			System.out.println("数据索引为：" + ans);
		}else{
			System.out.println("请输入正确格式的数据");
		}
	}
}

class A02{

	public int find(String ary[],String str){

		//实现代码健壮性
		if (ary != null && ary.length > 0) {

			for (int i = 0;i < ary.length ;i++ ) {
				if (ary[i].equals(str)) {
				return i + 1;
				}
			}
			return -1;
		}else{
			return -1;
		}
	}
}
```

```java
public class Homework03{
	public static void main(String[] args) {
		//编写类Book，定义方法updatePrice，实现更改某本书的价格，具体：如果价格>150
		//则更改为150.如果价格>100，更改为100，否则不变。

		//思路：
		//类Book
		//更改价格的方法：updatePrice
		//参数：价格
		//逻辑：大于150 改为150
		//大于100 改为100
		//其他不变

		Book book = new Book(135);
		double priceNow = book.updatePrice();

			System.out.println(priceNow);

	}
}

class Book{
	//成员变量（属性）
	double price;

	public Book(double price){
		this.price = price;
	}

	public double updatePrice(){

		//-----第一种
		//实现代码健壮性
		// if (price >= 0) {
		// 	//逻辑判断
		// 	if (price > 150) {
		// 		return 150;
		// 	}else if (price > 100 && price <= 150) {
		// 		return 100;
		// 	}else{
		// 		return price;
		// 	}
		// }else{
		// 	return -1;
		// }

		//this实现-----第二种
		if (price > 150) {
			price = 150;
		}else if (price > 100 && price <= 150) {
			price = 100;
		}else{
			price = price;
		}
		return price;
	}
}
```

```java
public class Homework04{
	public static void main(String[] args) {
		//±àÐ´ÀàA03,ÊµÏÖÊý×éµÄ¸´ÖÆ¹¦ÄÜcopyArr£¬ÊäÈë¾ÉÊý×é£¬
		//·µ»ØÒ»¸öÐÂÊý×é£¬ÔªËØºÍ¾ÉÊý×éÒ»Ñù

		//Ë¼Â·£º
		//Àà£ºA03
		//¹¦ÄÜ£ºÊý×é¸´ÖÆ
		//·½·¨Ãû£ºcopyArr
		//·µ»ØÖµ£ºÊý×é

		int arrOld[] = {1,5,9,6,33};
		

		A03 a03 = new A03();
		int arrNew[] = a03.copyArr(arrOld);
		for (int i = 0;i < arrNew.length ;i++ ) {
			System.out.print(arrNew[i] + " ");
		}

		System.out.println(arrOld.hashCode());
		System.out.println(arrNew.hashCode());
	}
}

class A03{
	
	public int[] copyArr(int arrOld[]){
		int arrNew[] = new int[arrOld.length];
		for (int i = 0;i < arrOld.length ;i++ ) {
			arrNew[i] = arrOld[i];
		}
		return arrNew;
	}
}
```

```java
public class Homework05{
	public static void main(String[] args) {
		//定义一个圆类Circle，定义属性：半径，提供显示圆周长功能的方法，
		//提示显示圆面积的方法

		//思路：
		//类名：Circle
		//属性：半径
		//两个方法

		Circle c = new Circle();
		//周长+面积
		System.out.println("半径为5时，周长=" + c.perimeter(5) +
							 ",面积=" + c.area(5));

	}
}

class Circle{
	//定义半径
	double redius;

	// public Circle(double redius){
	// 	this.redius = redius;
	// }

	// //定义周长
	// double per;

	//定义π
	double pai = 3.14;

	// //定义面积
	// double are;

	//求圆周长的方法
	//圆周长= 圆周率×半径×2
	public double perimeter(int redius){
		return 2 * Math.PI * redius;
	}

	//求圆面积的方法
	//S=πr的平方（其中r为半径）
	public double area(int redius){
		return Math.PI * redius * redius;
	}
}
```

```java
public class Homework06{
	public static void main(String[] args) {
		//编程创建一个Cale计算类，在其中定义2个变量表示两个操作数，定义四个方法实现
		//求和、差、乘、商（要求除数为0时提示）并创建两个对象，分别测试

		Cale c1 = new Cale(5,6);
		int sum = c1.getRide();
		System.out.println(sum);

		Cale c2 =new Cale(300,0);
		int quo = c2.getQuo();
		if (quo != -1) {
			System.out.println(quo);
		}else{
			System.out.println("除数不能为0");
		}
		
	}
}

class Cale{
	//操作数
	int a;
	int b;

	//构造参数
	public Cale(int a,int b){
		this.a = a;
		this.b = b;
	}

	//求和
	public int getSum(){
		return a + b;
	}

	//差
	public int getDif(){
		return a - b;
	}

	//乘
	public int getRide(){
		return a * b;
	}

	//商
	public int getQuo(){
		if (b == 0) {
			return -1;
		}
		return a / b;
	}
}
```



```java
public class Homework07{
    public static void main(String[] args) {
        //设计一个Dog类，有名字、颜色和年龄属性，定义输出方法show（）显示其信息。
        //并创建对象，进行测试。【提示this.属性】

        Dog dog = new Dog("小白","绿色",25);
        dog.show();

        // String[] str = d.show();
        // for (int i = 0;i < str.length ;i++ ) {
        // 	System.out.println(str[i]);
        // }
    }
}

class Dog{
    String name;
    String color; 
    int age;

    public Dog(String name,String color,int age){
        this.name = name;
        this.color = color;
        this.age = age;
    }

    // public String[] show(){
    // 	String str[] = {name,color,age+""};
    // 	return str;
    // }

    public void show(){
        System.out.println(name);
        System.out.println(color);
        System.out.println(age);
    }
}
```

```java
public class Homework08{
	public static void main(String[] args) {
		//看程序，查输出(输出结果10，9，10)
		new Test().count1();//匿名对象，使用一次后销毁//10

		Test t1 = new Test();
		t1.count2();//9
		t1.count2();//10
	}
}

public class Test{
	int count = 9;

	public void count1(){
		count = 10;
		System.out.println("count1=" + count);
	}

	public void count2(){
		System.out.println("count1=" + count++);
	}

}
```

```java
public class Homework09{
	public static void main(String[] args) {
		//定义Music类，里面有很多音乐名name、音乐时长times属性、
		//并有播放play功能和返回本身属性信息的功能方法getInfo
		Music m = new Music("张三",25);
		if (m.play(false) == true) {
			System.out.println("开启播放");
		}
		String str[] = m.getInfo();
		for (int i = 0;i < str.length ;i++ ) {
			System.out.println(str[i]);
		}

	}
}

class Music{
	String name;
	int times;

	public Music(String name,int times){
		this.name = name;
		this.times = times;
	}

	public boolean play(boolean b){
		return !b;
	}

	public String[] getInfo(){
		String str[] = {name,times + ""};
		return str;
	}
}
```

```java
public class Homework10{
	public static void main(String[] args) {
		//请写出以下代码的运行结果：(101,100,101,101)
		Demo d1 = new Demo();
		Demo d2 = d1;
		d2.m();
		System.out.println(d1.i);
		System.out.println(d2.i);
	}
}

class Demo{
	int i = 100;
	public void m(){
		int j = i++;
		System.out.println("i=" + i);
		System.out.println("j=" + j);
	}
}
```

```java
public class Homework11{
	public static void main(String[] args) {
		//在测试方法中，调用methods方法，代码如下，编译正确，
		//试写出method方法的定义形式
		//调用语句为
		System.out.println(method(method(10.0,20.0),100));

	}
}
	public double methods(double a,double b){}

```

```java
public class Homework12{
	public static void main(String[] args) {
		//创建一个Employee类，属性有（名字、性别、年龄、职位、薪水），
		//提供3个构造方法，可以初始化
		//1）名字、性别、年龄、职位、薪水
		//2）名字、性别、年龄
		//3）职位、薪水
		//要求充分复用构造器

	}
}

class Employee{
	String name;
	char gender;
	int age;
	String post;
	double salary;

	public Employee(String post,double salary){
		this.post = post;
		this.salary = salary;
	}

	public Employee(String name,char gender,int age){
		this.name = name;
		this.gender = gender;
		this.age = age;
	}

	public Employee(String name,char gender,int age,String post,double salary){
		// this.name = name;
		// this.gender = gender;
		// this.age = age;
		this(name,gender,age);
		this.post = post;
		this.salary = salary;
	}
}
```

```java
public class Homework13{
	public static void main(String[] args) {
		//将对象作为参数传递给方法
		//1）定义一个Circle类，包含一个double型的redius属性代表圆的半径，
		//findArea（）方法返回圆的面积
		//2）定义一个类PassObject，在类中定义一个方法printAreas（），
		//该方法的定义如下：
		//public void printAreas(Circle c,int times)
		//3）在printAreas方法中打印输出1到times之间的每个整数半径值，
		//以及对应的面积。例如：times为5，则输出半径1，2，3，4，5以及对应的圆面积
		//4）在main方法中调用printAreas（）方法，调用完毕后输出当前半径值。
		Circle c = new Circle();

		PassObject p = new PassObject();
		p.printAreas(c,5);
	}
}

class Circle{
	//半径
	double redius;

	// public Circle(double redius){
	// 		this.redius = redius;
	// }
 
	//计算圆面积
	public double findArea(){
		return Math.PI * redius * redius;
	}

	public void setRadius(double redius){
		this.redius = redius;
	}
}

class PassObject{

	public void printAreas(Circle c,int times){
		System.out.println("Redius\tArea");
		for (int i = 1;i <= times ; i++) {
			c.setRadius(i);
			System.out.println((double)i + "\t" + c.findArea());
		}
	}	
}
```

```java
import java.util.Scanner;

public class Homework14{
	public static void main(String[] args) {
		//有个人Tom设计他的成员变量，成员方法，可以和电脑猜拳
		//电脑每次都会随机生成0，1，2
		//0表示石头 1表示剪刀 2表示布 
		//Math.random() 返回一个double值为正号，大于等于0.0 ，小于1.0 。 
		//返回的值是从该范围（大约）均匀分布而伪随机选择的。
		//并且可以显示Tom的输赢次数

		//思路：
		//键盘输入 -》 和电脑生成数比较 -》得出结果 
		//累计输赢

		//随机生成0、1、2  
		//(int)(Math.random() * 10) % 3

		//?怎么判赢？不能用大小判断
		//把电脑随机数与用户输入数放一起用人为逻辑判断

		Computer con = new Computer();
		con.finger();

	}
}

class Computer{

	Scanner myScanner = new Scanner(System.in);

	//定义猜拳次数
	int con = 0;

	//定义变量累计赢的次数
	int winCon = 0;

	//猜拳
	public void finger(){

		while (con < 5) {
			//提醒用户输入
			System.out.println("请输入:(0->石头，1->剪刀，2->布)");
			//接收，玩家出拳
			int userInput = myScanner.nextInt();

			//电脑出拳
			int comInput = (int)(Math.random() * 10) % 3;

			if ((userInput == 0 && comInput == 1) || (userInput == 1 && comInput == 2) || (userInput == 2 && comInput == 0)) {
				con++;
				winCon++;
				System.out.println("恭喜您赢了！");
			}else if ((userInput == 0 && comInput == 2) || (userInput == 1 && comInput == 0) || (userInput == 2 && comInput == 1)) {
				con++;
				System.out.println("抱歉您输了！");
			}else if ((userInput == 0 && comInput == 0) || (userInput == 1 && comInput == 1) || (userInput == 2 && comInput == 2)) {
				con++;
				System.out.println("打成平手！");
			}
		}
		System.out.println("游戏结束！您赢了" + winCon + "次");	
	}
}

```

## 3.oop—中级

#### 1.IDE

​	IDE————集成开发环境

1）IDEA全程IntelliJ IDEA	

2）在业界被认为是最好的Java开发工具

3）IDEA是JetBrains公司的产品，总部位于捷克的首都布拉格

4）除了支持Java开发，还支持HTML、CSS、PHP、Mysql、Python等

​	eclipse介绍

1）Eclipse是一个开放源代码的、基于Java的可扩展开发平台

2）最初是IBM公司耗资3000万美元开发的下一代IDE开发环境

3）2001年11月贡献给开源社区

4）Eclipse是目前最优秀的Java开发IDE之一



#### 2.IDEA常用快捷键总结

1.根据psvm或者main快速生成主函数

我们可以在类中输入psvm 或者main
然后IDEA会自动提示main(),敲击回车即可自动生成~

![在这里插入图片描述](https://img-blog.csdnimg.cn/e144348e22cf4c1db3e029a5c7dc1e47.png)



![在这里插入图片描述](https://img-blog.csdnimg.cn/e9e4f7b64ef4493ba58694e344d46d3c.png)



2. 根据sout快速生成打印语句

我们可以在方法中输入sout
然后IDEA会自动提示打印语句,敲击回车即可自动生成~

![在这里插入图片描述](https://img-blog.csdnimg.cn/ee4c19de44264f199dbab5513ecd613a.png)

3. 查找的快捷键

按Ctrl + F表示在当前页面中查找

4. **<span style="color:red">万能键Alt+Enter</span>**

Alt+Enter是一个特别常用且好用的“万能键”
比如我们可以在类中导入需要导的包
再比如我们可以在类中快速生成方法的返回值类型与变量名
如果代码中需要处理异常，我们还可以快速选择是抛出还是捕获

​	5.Ctrl系列

<span style="color:red">**Ctrl + Y 删除光标所在行的所有内容，Ctrl+X也可以**</span>
<span style="color:red">**Ctrl + D 快速向下复制当前行的内容**</span>
Ctrl + W 递进式选中代码
可以先选中光标所在的一部分代码，连续按这个快捷键会在原来的基础上继续扩展被选中的内容
Ctrl + E 显示最近打开的文件记录列表
Ctrl + G 在当前文件跳转到指定位置处
Ctrl + Q 光标所在的变量 / 类名 / 方法名等上面（也可以在提示补充的时候按），显示文档内容
Ctrl + U 前往当前光标所在的方法的父类的方法 / 接口定义
Ctrl + B 进入光标所在的方法/变量的接口或是定义处，等效于 Ctrl + 左键单击（必备）
Ctrl + O 选择可重写的方法
Ctrl + I 选择可继承的方法
<span style="color:red">**Ctrl + / 注释光标所在行代码，会根据当前不同文件类型使用不同的注释符号 （必备）**</span>
Ctrl + F1 在光标所在的错误代码处显示错误信息
Ctrl + F3 调转到所选中的词的下一个引用位置
Ctrl + F4 关闭当前编辑文件
Ctrl + ­- 折叠代码
Ctrl + + 展开代码
Ctrl + Tab 编辑窗口切换，如果在切换的过程又加按上delete，则是关闭对应选中的窗口
Ctrl + Enter 智能分隔行
Ctrl + Delete 删除光标后面的单词或是中文句
Ctrl + BackSpace 删除光标前面的单词或是中文句
Ctrl + End 跳到文件尾
Ctrl + Home 跳到文件头
Ctrl + [ 移动光标到当前所在代码的花括号开始位置
Ctrl + ] 移动光标到当前所在代码的花括号结束位置
Ctrl + 左方向键 光标跳转到当前单词 / 中文句的左侧开头位置
Ctrl + 右方向键 光标跳转到当前单词 / 中文句的右侧开头位置
Ctrl + 前方向键 等效于鼠标滚轮向前效果
Ctrl + 后方向键 等效于鼠标滚轮向后效果

​	6.Alt系列

Alt+Shift+向上 向上移动选中的代码
Alt + Insert 代码自动生成，如生成对象的 set / get 方法，构造函数，toString() 等
Alt + 左方向键 按左方向切换当前已打开的文件视图
Alt + 右方向键 按右方向切换当前已打开的文件视图
Alt + 前方向键 当前光标跳转到当前文件的前一个方法名位置
Alt + 后方向键 当前光标跳转到当前文件的后一个方法名位置

​	7.Shift系列

Alt+Shift+向上 向上移动选中的代码
Alt + Insert 代码自动生成，如生成对象的 set / get 方法，构造函数，toString() 等
Alt + 左方向键 按左方向切换当前已打开的文件视图
Alt + 右方向键 按右方向切换当前已打开的文件视图
Alt + 前方向键 当前光标跳转到当前文件的前一个方法名位置
Alt + 后方向键 当前光标跳转到当前文件的后一个方法名位置

​	8.Ctrl+Shift系列

Ctrl + Shift + Alt + V 无格式黏贴
Ctrl + Shift + Alt + N 前往指定的变量 / 方法
Ctrl + Shift + Alt + S 打开当前项目设置
Ctrl + Shift + ­ - 折叠所有代码
Ctrl + Shift + ­ + 展开所有代码
Ctrl + Shift + F12 编辑器最大化

​	9.Ctrl+Alt系列

Ctrl + Alt + S 打开设置
<span style="color:red">**trl + Alt + L 格式化代码，可以对当前文件和整个包目录使用**</span>
Ctrl + Alt + O 优化导入的类，可以对当前文件和整个包目录使用
Ctrl + Alt + I 光标所在行 或 选中部分进行自动代码缩进，有点类似格式化

````java
import java.util.Scanner;

public class ArrayTest {
    public static void main(String[] args) {
        //创建一个类MyTools,编写一个方法，可以完成对int数组冒泡排序的功能
        //定义int数组
        int ary[] = {1, 5, 66, 12, 34, -1};

        //快捷键自动分配变量名 .var
        Scanner myScanner = new Scanner(System.in);
        Scanner scanner = new Scanner(System.in);
        Scanner scanner1 = new Scanner(System.in);

        Mytools mt = new Mytools();
        //定位方法 ctrl + b
        mt.sort(ary);
        System.out.println("排序后：");
        for (int i = 0; i < ary.length; i++) {
            System.out.print(ary[i] + " ");
        }
        //在idea中，当我们run时，会先编译，后运行
    }
}

class Mytools {
    public void sort(int ary[]) {
        for (int i = 0; i < ary.length - 1; i++) {
            for (int j = 0; j < ary.length - 1 - i; j++) {
                if (ary[j] > ary[j + 1]) {
                    int temp = ary[j + 1];
                    ary[j + 1] = ary[j];
                    ary[j] = temp;
                }
            }
        }
    }
}

//查看类的继承关系 ctrl + h
class Person{
    String name;
    int age;
    //构造器快捷键 ale + insert
    public Person() {
    }

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}

````



#### 3.包

本质就是创建不同的文件夹/目录来保存类文件

1）区分相同名字的类

2）当类很多时，可以很好的管理类

3）控制访问范围

​	基本语法

```java
package com.baoname;
```

1）package 关键字，表示打包

2）com.baoname表示包名

```java
package Test;

import com.momo.Dog;

public class Test {
    public static void main(String[] args) {
        Dog dog = new Dog();
        System.out.println(dog);

        com.xiaobai.Dog dog1 = new com.xiaobai.Dog();
        System.out.println(dog1);
    }
}
```

​	包命名规则：

只能包含数字、字母、下划线、小圆点，但不能用数字开头，不能是关键字或保留字

包命名规范：

一般是小写字母+小圆点

com.公司名.项目名.业务模块名

例如：com.sina.crm.user

​	常用包：

java.lang.* //lang包是基本包，默认引入，不需要再引入

java.util.* //util包，系统提供的工具包、工具类，例如使用Scanner

java.net.* //网络包,网络开发

java.awt.* //Java界面开发，GUI

细节：

1）package的作用是声明当前类所在的包，需要放在类的最上面，一个类中最多一个包package

2）import指令 位置放在package的下面，在类定义前面，可以有多句且没有顺序要求。



#### 4.访问修饰符

![image-20220718163922013](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062252190.png)

**private** : 在同一类内可见。使用对象：变量、方法。 注意：不能修饰类（外部类）
**default (即缺省，什么也不写，不使用任何关键字**）: 在同一包内可见，不使用任何修饰符。使用对象：类、接口、变量、方法。
**protected** : 对同一包内的类和所有子类可见。使用对象：变量、方法。 注意：不能修饰类（外部类）。
**public** : 对所有类可见。使用对象：类、接口、变量、方法

简单理解：

- public：哪里都可以使用.
- default: 只能在同一个包中使用.
- private：只能在自己的类中使用.

注意事项：

1）修饰符可以用来修饰类中的属性、成员方法以及类

2）只有默认的和public才能修饰类！并且遵循上述访问权限的特点。

3）成员方法的访问规则和属性完全一样。

![在这里插入图片描述](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062252946.png)

#### 5.封装

​	<span style="color:red">**封装：将数据和操作数据的方法进行有机结合，隐藏对象的属性和实现细节，仅对外公开接口来和对象进行交互.**</span>

- 面向对象程序三大特性：**封装,继承,多态**.
- 通俗来说,封装就是**套壳**屏蔽细节.比如:一个电脑真正工作的是CPU,显卡等硬件,而用户只是通过鼠标和键盘等设备来和计算机进行*交互*.

![在这里插入图片描述](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062252405.png)



​	封装实现步骤：

1）属性私有化（private）

2）提供一个公共的(public)set 方法，用于对属性判断并赋值

```java
public void serXXX(数据类型 参数名){//xxx表示某个属性
    //数据验证的业务逻辑
    属性 = 参数名;
}
```

3）提供一个公共的（public）get方法，用于获取属性的值

```java
public 数据类型 getXXX(){//权限判断，XXX某个属性
    return xx;
}
```

```java
package com.hspedu.encap;

public class Encapsulation01 {
    //写一个程序，不能随便查看人的年龄、工资等隐私，
    // 并对设置的年龄进行合理的验证。年龄合理就设置，
    // 否则给默认年龄，必须在1-120之间，
    // 工资不能直接查看，name的长度在2-6字符之之间
    public static void main(String[] args) {
        Person person = new Person();
        person.setName("jack");
        person.setAge(30);
        person.setSalary(20000);
        person.setJob("程序员");
        //输出信息
        System.out.println(person.info());
        System.out.println(person.getSalary());
    }

}

class Person {
    public Person() {
    }

    public Person(String name, int age, double salary, String job) {
//        this.name = name;
//        this.age = age;
//        this.salary = salary;
//        this.job = job;

        setName(name);
        setAge(age);
        setSalary(salary);
        setJob(job);
    }

    public String name;
    private int age;
    private double salary;
    private String job;

    //get/set 快捷键 alt + insert
    public String getName() {
        return name;
    }

    public void setName(String name) {
        //加入对数据的校验
        if (name.length() >= 2 && name.length() <= 6) {
            this.name = name;
        } else {
            System.out.println("名字长度不对，需要（2-6）个");
            this.name = "暂无";
        }
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        if (age >= 1 && age <= 120) {
            this.age = age;
        } else {
            System.out.println("年龄有误");
            this.age = 18;
        }
        this.age = age;
    }

    public double getSalary() {
        //增加权限判断
        return salary;
    }

    public void setSalary(double salary) {
        this.salary = salary;
    }

    public String getJob() {
        return job;
    }

    public void setJob(String job) {
        this.job = job;
    }

    //返回属性信息
    public String info() {
        return "信息如下：name=" + name + " ，age=" + age + " ，salary=" +
                salary + " ，job=" + job;
    }
}

```

```java
package com.hspedu.encap;
//创建程序，在其中定义两个类：Account和AccountTest类。
//1）Account类要求具有属性：姓名(长度为2位或3为或4位)、余额（必须>20）、
//密码（必须六位数），如果不满足，提示信息并给默认值
//2）通过setXXX的方法给Account的属性赋值
//3）在AccountTest中测试
//提示：String name = "";
//int len = name.length;

public class Account {
    private String name;
    private double balance;
    private String pwd;

    //构造器
    public Account() {
    }

    public Account(String name, double balance, String pwd) {
//        this.name = name;
//        this.balance = balance;
//        this.pwd = pwd;
        this.setName(name);
        this.setBalance(balance);
        this.setPwd(pwd);
    }

    public String getName() {
        return name;
    }

    //长度为2位或3为或4位
    public void setName(String name) {
        if (name != null) {
            if (name.length() == 2 || name.length() == 3 || name.length() == 4) {
                this.name = name;
            } else {
                System.out.println("姓名长度为2位或3为或4位，给默认值");
                this.name = "暂无";
            }
        } else {
            System.out.println("字符位空，请输入值");
            this.name = "暂无";
        }
    }

    public double getBalance() {
        return balance;
    }

    //余额（必须>20）
    public void setBalance(double balance) {
        if (balance > 20) {
            this.balance = balance;
        } else {
            System.out.println("余额小于或等于20，给默认值");
            this.balance = 0;
        }
    }

    public String getPwd() {
        return pwd;
    }

    //必须六位数
    public void setPwd(String pwd) {
        if (pwd != null) {
            if (pwd.length() == 6) {
                this.pwd = pwd;
            } else {
                System.out.println("密码不为6位，给默认值");
                this.pwd = "666666";
            }
        } else {
            System.out.println("密码为空，请输入值");
            this.pwd = "0";
        }
    }

    //显示信息方法
    public String info() {
        //可增加权限校验
        return "name=" + name + ",balance=" + balance + ",pwd=" + pwd;
    }
}

```



#### 6.继承

![image-20220719054643098](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062252144.png)

​	定义：

class 子类 extends 父类 {}

通常也称子类为派生类、父类为超类。

​	功能： 

继承的主要目的是使子类可以重用父类的结构，也可以根据子类功能的需要进行覆写或结构扩充，因此子类往往比父类描述的范围更小。

​	要求：

在Java中子类只能继承一个父类。

不允许**多重继承**但允许**多层继承**。

```java
//情景1：
public class A extends B {}    //只继承一个父类，正确

//情景2：
public class A extends B,C {}  //多重继承，错误

//情景3：
public class A {}
public class B extends A {}
public class C extends B {}    //多层继承，正确   
```

细节：

1）子类继承了父类所有的属性和方法，但是私有属性和方法不能在子类中直接访问，要通过公共的方法访问

2）子类必须调用父类的构造器，完成父类的初始化

3）当创建子类对象时，不管使用子类的哪个构造器。默认情况下总会去调用父类的无参构造器，如果父类中没有提供无参构造器，则必须在子类的构造器中用super去指定使用父类的哪个构造器完成对父类的初始化工作，否则编译不通过。

4）如果希望指定去调用父类的某个构造器，则显式的调用一下：super（参数列表）

5）super在使用时，必须放在构造器第一行（super只能在构造器中使用）

6）super（）和this（）都只能放在构造器第一行，因此这两个方法不能共存在一个构造器

7）java所有类都是Object类的子类，Object是所有类的基类。

![image-20220719072624506](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062252507.png)

8）父类构造器的调用不限于直接父类i！将一直往上追溯直到Object类（顶级父类）

9）子类最多继承一个父类（直接继承），单继承机制

10）不能滥用继承，子类和父类之间必须满足is-a的逻辑关系

![image-20220719080200149](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062252171.png)



  练习

```java
package com.hspedu.extend_.exercise;

public class ExtendsExercise01 {
    public static void main(String[] args) {
        B b = new B();//输出a 、b name、b
    }
}
class A{
    A(){
        System.out.println("a");
    }

    A(String name){
        System.out.println("a name");
    }
}
class B extends A{
    B(){
        this("abc");
        System.out.println("b");
    }
    B(String name){
        super();//默认调用父类无参构造器
        System.out.println("b name");
    }
}

```

```java
package com.hspedu.extend_.exercise;

public class ExtendsExercise02 {
    public static void main(String[] args) {
        C1 c1 = new C1();
    }
}
class A1{
    public A1(){
        System.out.println("我是A1类");//1
    }
}
class B1 extends A1{
    public B1(){
        System.out.println("我是B1类的无参构造");
    }
    public B1(String name){
        super();
        System.out.println("我是B1类的有参构造");//2
    }
}
class C1 extends B1{
    public C1(){
        this("hello");//this(参数)：去执行带一个本类的String类型的构造器
        System.out.println("我是C1类的无参构造");//4
    }
    public C1(String name){
        super("haha123");
        System.out.println("我是C1类的有参构造");//3
    }
}

```

```java
package com.hspedu.extend_.exercise;
//编写Computer类，包含CPU、内存、硬盘等属性，getDetails方法用于返回
//Computer的详细信息
//编写PC子类，继承Computer类，添加特有属性【品牌brand】
//编写NotePad子类，继承Computer类，添加特有属性【颜色color】
//编写Test类，在main方法中创建PC和NoteOPad对象，
//分别给对象中特有的属性赋值，以及从Computer类继承的属性赋值，并
//使用方法并打印输出信息
public class ExtendsExercise03 {
}
class Computer{
    //定义cpu
    private String CPU;
    //定义内存
    private String RAM;
    //定义硬盘
    private String HDD;

    public Computer(String CPU, String RAM, String HDD) {
        this.CPU = CPU;
        this.RAM = RAM;
        this.HDD = HDD;
    }

    public String getCPU() {
        return CPU;
    }

    public void setCPU(String CPU) {
        this.CPU = CPU;
    }

    public String getRAM() {
        return RAM;
    }

    public void setRAM(String RAM) {
        this.RAM = RAM;
    }

    public String getHDD() {
        return HDD;
    }

    public void setHDD(String HDD) {
        this.HDD = HDD;
    }

    public String getDetails(){
        return "CPU:" + CPU + " 内存" + RAM + " 硬盘" + HDD;
    }
}
class PC extends Computer{
    //子类特有属性
    private String brand;

    //继承设计基本思想：父类构造器完成父类初始化、子类构造器完成子类初始化
    public PC(String CPU, String RAM, String HDD, String brand) {
        super(CPU, RAM, HDD);
        this.brand = brand;
    }

    public void setBrand(String brand) {
        this.brand = brand;
    }

    public String getBrand() {
        return brand;
    }

    public void showInfo(){
        System.out.println("PC信息如下：");
        //调用父类的方法显示信息
        System.out.println(getDetails() + "品牌：" + getBrand());
    }
}
class NotePad extends Computer{
    private String color;

    public void setColor(String color) {
        this.color = color;
    }

    public NotePad(String CPU, String RAM, String HDD, String color) {
        super(CPU, RAM, HDD);
        this.color = color;
    }
}

```



#### 7.super

​	super代表父类的引用，用于访问父类的属性、方法、构造器

1）super.属性名;

访问父类的属性，但不能访问父类的private属性

2）super.方法名（参数列表）;

访问父类的方法，但不能访问父类的private方法

3）super（参数列表）;

访问父类的构造器，只能放在构造器的第一句，只能出现一句。

细节：

1）调用父类的构造器的好处（分工明确，父类属性由父类初始化，子类的属性由子类初始化）

2）当子类中有和父类中的成员（属性或方法）重名时，为了访问父类的成员必须通过super

如果没有重名，使用super、this、直接访问效果一样。

3）super的访问不限于直接父类，如果爷爷类和本类中有同名的成员，也可以使用super去访问爷爷类的成员；如果多个基类（上级类）中都有同名成员，使用super访问遵循就近原则。



​	**this和super区别**

![image-20220719122742973](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062252704.png)



#### 8.重写

重写是子类对父类的允许访问的方法的实现过程进行重新编写, 返回值和形参都不能改变。**即外壳不变，核心重写！**

重写的好处在于子类可以根据需要，定义特定于自己的行为。 也就是说子类能够根据需要实现父类的方法。

注意：重写方法不能抛出新的检查异常或者比被重写方法申明更加宽泛的异常。例如： 父类的一个方法申明了一个检查异常 IOException，但是在重写这个方法的时候不能抛出 Exception 异常，因为 Exception 是 IOException 的父类，抛出 IOException 异常或者 IOException 的子类异常。

在面向对象原则里，重写意味着可以重写任何现有方法。实例如下：

```java
package com.hspedu.override;

public class Override01 {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.cry();
    }
}
class Animal{
    public void cry(){
        System.out.println("动物叫唤");
    }
}
class Dog extends Animal{
    public void cry(){
        System.out.println("小狗汪汪汪");
    }
}
```

细节：

1）子类方法的形参列表、方法名称，要和父类方法的形参列表、方法名称保持一致。

2）子类方法发返回类型和父类方法发返回类型一样，或者是父类方法返回类型的子类。Object->String

3）子类方法不能缩小父类方法的访问权限。



**重写与重载的区别**

![image-20220719130523850](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062252143.png)



```java
package com.hspedu.override;
//编写一个Person类，包括属性private（name、age），构造器，方法say
//（返回自我介绍的字符串）
//编写一个Student类，继承Person类，增加id、score属性（private），
//以及构造器，定义say方法（返回自我介绍的信息）
//在main中，分别创建Person和Student对象，调用say方法输出自我介绍
public class OverrideExercise {
    public static void main(String[] args) {
        Person person = new Person("张三",12);
        System.out.println(person.say());;
        System.out.println("+++++++++++++++");
        Student student = new Student("李四",25,001,66);
        System.out.println(student.say());;
    }
}
class Person{
    //属性
    private String name;
    private int age;

    //构造器
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    //自我介绍
    public String say(){
        return "姓名：" + name + " 年龄：" + age;
    }
}

class Student extends Person{
    private int id;
    private int score;

    public Student(String name, int age, int id, int score) {
        super(name, age);
        this.id = id;
        this.score = score;
    }

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public int getScore() {
        return score;
    }

    public void setScore(int score) {
        this.score = score;
    }

    //自我介绍
    public String say(){
//        return "姓名：" + super.getName() + " 年龄：" + super.getAge() + " id：" + id + " 成绩：" + score;
        return super.say() + " id：" + id + " 成绩：" + score;
    }
}

```



#### 9.多态

通俗来说，就是多种形态，那么在Java中，就是**去完成某个行为，当不同的对象去完成时会产生不同的状态和表现**。
举两个简单的例子

![image-20220719142409693](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062252296.png)

总的来说：同一件事，发生在不同对象身上，就会产生不同的结果



在Java中要实现多态，那么必须要满足以下几个条件，缺一不可：

1. **必须在继承体系下**
2. **子类必须要对父类中的方法进行重写**
3. **通过父类的引用调用重写的方法**

对象的多态

1）一个对象的运行类型和编译类型可以不一致

2）编译类型在定义对象时，就确定了，不能改变

3）运行类型是可以变化的

4）编译类型看定义时 = 号的左边，运行类型看 = 号的右边

```Java
package com.hspedu.poly_.objectpoly_;

public class PloyObject {
    public static void main(String[] args) {
        //对象多态
        //animal编译类型是Animal，运行类型是Dog
        Animal animal = new Dog();
        //因为运行时，执行到该行时，animal运行按类型是Dog，所以cry就是Dog的cry
        animal.cry();

        //animal编译类型Animal，运行类型就是Cat
        animal = new Cat();
        animal.cry();
    }
}
```



##### 1.**向上转型**

<span style="color:red">**本质：父类的引用指向子类的对象**</span>

语法：

```java
父类类型 引用名（对象名） = new 子类类型();
```

特点：

1）编译类型看 = 左边，运行类型看右边。

2）可以调用父类中所有成员（须遵守访问权限）。

3）不能调用子类中特有成员

4）最终运行效果看子类具体实现

##### **2.向下转型**

1）语法：

```java
子类类型 引用名（对象名） = （子类类型）父类引用;
```

2）只能强转父类的引用，不能强转父类的对象

3）要求父类的引用必须指向的是当前目标类型的对象

4）当向下转型后，可以调用子类类型中所有的成员

细节：

属性没有重写之说！属性的值看编译类型

<span style="color:red">instanceOf比较操作符，用于判断对象的运行类型是否为xx类型或xx类型的子类型</span>

```java
package com.hspedu.poly_;

public class PloyExercise {
    public static void main(String[] args) {
        Sub sub = new Sub();
        System.out.println(sub.count);//20
        sub.display();//20
        Base base = sub;
        System.out.println(base == sub);//true
        System.out.println(base.count);//10
        base.display();//20
    }
}
class Base{
    int count = 10;
    public void display(){
        System.out.println(this.count);
    }
}
class Sub extends Base{
    int count = 20;

    @Override
    public void display() {
        System.out.println(this.count);
    }
}

```

#### 10.动态绑定机制

```java
public class DynamicBinding {

    public static void main(String[] args) {
        A a = new B();
        System.out.println(a.sum());	//40
        System.out.println(a.sum1());	//30
    }
}
class A {
    public int i = 10;
    public int sum(){
        return getl() + 10;
    }
    public int sum1(){
        return i + 10;
    }
    public int getl(){
        return i;
    }
}

class B extends A{
    public int i = 20;
    public int sum(){
        return i + 20;
    }
    public int getl(){
        return i;
    }
    public int sum1(){
        return i + 10;
    }
}

```

**A a = new B();是向上转型，调用方法看运行类型**
**a.sum()和a.sum1()分别输出40和30，这一点毫无疑问**



**动态绑定机制-调用对象方法**

**如果把上述子类中的sum()注释掉，结果会有什么不同？**

```java
public class DynamicBinding {

    public static void main(String[] args) {
        A a = new B();
        System.out.println(a.sum());
        System.out.println(a.sum1());
    }
}
class A {
    public int i = 10;
    public int sum(){
        return getl() + 10;
    }
    public int sum1(){
        return i + 10;
    }
    public int getl(){
        return i;
    }
}

class B extends A{
    public int i = 20;
//    public int sum(){
//        return i + 20;
//    }
    public int getl(){
        return i;
    }
    public int sum1(){
        return i + 10;
    }
}
```

**这个时候a.sum()访问子类，发现子类中没有sum方法，再去访问父类，父类中有sum方法，调用的过程中getl()出现了分歧，父类和子类中都有getl()，该调用哪一个？**
**这里就体现出java的动态绑定机制**

**java的动态绑定机制**
<span style="color:red">**1.当调用对象方法的时候，该方法会和该对象的内存地址/运行类型绑定**</span>
<span style="color:red">**2.当调用对象属性时，没有动态绑定机制，哪里声明，哪里使用**</span>

**所以该案例中的a.sum()和a.sum1()分别输出30和30**



**接着把子类中的sum1()注销**

```java
public class DynamicBinding {

    public static void main(String[] args) {
        A a = new B();
        System.out.println(a.sum());
        System.out.println(a.sum1());
    }
}
class A {
    public int i = 10;
    public int sum(){
        return getl() + 10;
    }
    public int sum1(){
        return i + 10;
    }
    public int getl(){
        return i;
    }
}

class B extends A{
    public int i = 20;
//    public int sum(){
//        return i + 20;
//    }
    public int getl(){
        return i;
    }
//    public int sum1(){
//        return i + 10;
//    }
}

```

**根据案例2中对动态绑定机制的描述，很容易分析出
a.sum()和a.sum1()分别输出30和20**



#### 11.多态数组

<span style="color:red">多态数组的定义类型为父亲类型，里面保存的实际元素类型为子类类型</span>

```java
package com.hspedu.poly_.polyarr;
//演示多态数组
//现有一个继承结构如下，要求创建1个Person对象，2个Student对象和2个
//Teacher对象，同一放在数组中，并调用每个对象say方法。
public class PloyArray {
    public static void main(String[] args) {
        Person[] peoples = new Person[5];
        peoples[0] = new Person("jack",20);
        peoples[1] = new Student("tom",25,33);
        peoples[2] = new Student("smith",20,66);
        peoples[3] = new Teacher("momo",35,2000);
        peoples[4] = new Teacher("milan",29,5000);
        
        //循环遍历多态数组，调用say方法
        for (int i = 0; i < peoples.length; i++) {
            //person[i]的编译类型是person，运行类型根据实际情况
            System.out.println(peoples[i].say());//动态绑定机制
            //判断person[i]的运行类型是不是Student
            if (peoples[i] instanceof Student){
                Student student = (Student)peoples[i];
                student.study();
                //判断person[i]的运行类型是不是Teacher
            } else if (peoples[i] instanceof Teacher) {
                Teacher teacher = (Teacher) peoples[i];
                teacher.teach();
            }
        }
    }
}

```

多态参数

方法定义的形参类型为父类类型，其实参类型允许为子类类型

```java
package com.hspedu.poly_.ployparameter_;
//定义员工类Employee，包含姓名和月工资【private】，以及计算年工资
//getAnnual的方法。普通员工和经理继承了员工，经理类多了奖金bonus属性
//和管理manage方法，普通员工类多了work方法，普通员工和经理类要求分别重写
//getAnnual方法。测试类中添加一个方法showEmpAnna（Employee e），实现
//获取任何员工对象的年工资，并在main方法中调用该方法【e.getAnnual】
//测试类中添加一个方法，testWork，如果是普通员工，则调用work方法
//如果是经理，则调用manage方法
public class PloyParameter {
    public static void main(String[] args) {
        Test test = new Test();
//        Manager manager = new Manager("经理1", 2000, 500);
        Employee employee1 = new Manager("经理01",5000,500);
        System.out.println(test.showEmpAnna(employee1));
        test.testWork(employee1);

        Employee employee2 = new Worker("员工01",3000);
        System.out.println(test.showEmpAnna(employee2));
        test.testWork(employee2);

    }
}
class Test{
    public String showEmpAnna(Employee employee){
        return employee.getName() + "---" + employee.getAnnual();
    }

    //如何区分是员工还是经理？
    public void testWork(Employee employee){
//        if (employee.getSalary() * 12 == employee.getAnnual() ){
////            Worker worker = (Worker) employee;
//            ((Worker) employee).work();
//        } else if (employee.getSalary() * 12 != employee.getAnnual()) {
//            ((Manager)employee).manage();
//        }
        if (employee instanceof Worker){
            ((Worker) employee).work();
        } else if (employee instanceof Manager) {
            ((Manager) employee).manage();
        }
    }
}

```



#### 12.Object



```
public class Object
```

Class `Object`是类`Object`结构的根。 每个类都有`Object`作为超类。 所有对象（包括数组）都实现了这个类的方法。

| Modifier and Type  | Method and Description                                       |
| :----------------- | :----------------------------------------------------------- |
| `protected Object` | `clone()`创建并返回此对象的副本。                            |
| `boolean`          | `equals(Object obj)`指示一些其他对象是否等于此。             |
| `protected void`   | `finalize()`当垃圾收集确定不再有对该对象的引用时，垃圾收集器在对象上调用该对象。 |
| `类<?>`            | `getClass()`返回此 `Object`的运行时类。                      |
| `int`              | `hashCode()`返回对象的哈希码值。                             |
| `void`             | `notify()`唤醒正在等待对象监视器的单个线程。                 |
| `void`             | `notifyAll()`唤醒正在等待对象监视器的所有线程。              |
| `String`           | `toString()`返回对象的字符串表示形式。                       |
| `void`             | `wait()`导致当前线程等待，直到另一个线程调用该对象的 [`notify()`](https://www.matools.com/file/manual/jdk_api_1.8_google/java/lang/Object.html#notify--)方法或 [`notifyAll()`](https://www.matools.com/file/manual/jdk_api_1.8_google/java/lang/Object.html#notifyAll--)方法。 |
| `void`             | `wait(long timeout)`导致当前线程等待，直到另一个线程调用 [`notify()`](https://www.matools.com/file/manual/jdk_api_1.8_google/java/lang/Object.html#notify--)方法或该对象的 [`notifyAll()`](https://www.matools.com/file/manual/jdk_api_1.8_google/java/lang/Object.html#notifyAll--)方法，或者指定的时间已过。 |
| `void`             | `wait(long timeout, int nanos)`导致当前线程等待，直到另一个线程调用该对象的 [`notify()`](https://www.matools.com/file/manual/jdk_api_1.8_google/java/lang/Object.html#notify--)方法或 [`notifyAll()`](https://www.matools.com/file/manual/jdk_api_1.8_google/java/lang/Object.html#notifyAll--)方法，或者某些其他线程中断当前线程，或一定量的实时时间。 |



#### 13.== 与 equals

想必你在面试题中多多少少碰见过让你对比equals和==的区别的，我们大体上的区别相比一定能说出来，但是未必能说得好，而且也总有些细节你是没注意到的，因此这里来详细总结下。

首先，我们分别来看下equals和==

- **==**

1. 对于基本数据类型的变量，如：Byte（字节型）、short（短整型）、char（字符型） 、int（整型）、float（单精度型/浮点型）、long（长整型）、double（双精度型） 和boolean(布尔类型）， **==**是直接对其值进行比较。
2. 对于引用数据类型的变量，则是对其内存地址的比较

因此，不管怎样，==是对数值上的一种比较。

- **equals**

我们知道任何类都继承Object类，这里我们先看下object类里的equals方法：

![img](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062252045.jpeg)

我们可以从这段源码看出，在没有重写equals方法之前，equals方法里是直接调用==，因此实质上与==没有差别。但是要注意：equals方法不能作用于基本数据类型的变量，这是因为基本数据类型非对象的缘故，没有方法。

然而，**在一些类库当中这个方法被重写了，**比如String 、Date、ArrayList等类，这样就不在是去比较在堆内存中的存放地址了。这里我们可以看下String类里equals方法的重写：

![img](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062252301.jpeg)

我们可以看到在String类里，equals是逐一对比两者的内容，内容相同才返回true.



- 代码示例：

```java
package com.zzq.test;

public class Testequals {
	public static void main(String[] args) {
        String a = new String("ab"); // a 为一个引用
        String b = new String("ab"); // b为另一个引用,对象的内容一样
        String aa = "ab"; // 放在常量池中
        String bb = "ab"; // 从常量池中查找
        String c=b.intern();
        
            System.out.println(aa==bb);

            System.out.println(a==b);  // false，非同一对象
       
            System.out.println(a.equals(b));
 
            System.out.println(a==c); //每new一次，都会重新开辟堆内存空间
            
            System.out.println(aa==c);
    }
```

> *这里用到了intern()，延展文章放一下:[https://blog.csdn.net/guoxiaolongonly/article/details/80425548](https://link.zhihu.com/?target=https%3A//blog.csdn.net/guoxiaolongonly/article/details/80425548)*

运行结果为：

![img](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062253670.png)

对于第一个输出：以String aa="ab"; 形式赋值在java中叫直接量,它是在常量池中而不是像new一样放在压缩堆中。这种形式的字符串，在JVM内部发生字符串拘留，即当声明这样的一个字符串后，JVM会在常量池中先查找有有没有一个值为"abcd"的对象,如果有,就会把它赋给当前引用.即原来那个引用和现在这个引用指点向了同一对象，如果没有将开辟新内存地址存放。在这里将“ab”赋予bb时是给了bb以aa相同的内存地址，故为true;

1. 对于第二个输出：虽然a和b内容相同，但是都是new出来的，内存地址不同，故为false;
2. 对于第三个输出：equals在这里为比较内容是否相同，明显一样，输出为true；
3. 对于第四个输出：仍然因为其存放地址不同，导致输出为false;
4. 对于第五个输出：这里就要介绍下intern（）了。

调用intern()方法之后把字符串对象加入常量池中，常量池我们都知道他是存在于方法区的，他是方法区的一部分，而方法区是线程共享的，所以常量池也就是线程共享的，但是他并不是线程不安全的，他其实是线程安全的，他仅仅是让有相同值的引用指向同一个位置而已，如果引用值变化了，但是常量池中没有新的值，那么就会新开辟一个常量结果来交给新的引用，而并非像线程不同步那样，针对同一个对象，new出来的字符串和直接赋值给变量的字符串存放的位置是不一样的，前者是在堆里面，而后者在常量池里面。

因此，对于输出5，c已经被加入常量池中，常量池中已有同值存在，故给c以aa相同存放地址，故返回为true。因此，因为b还是在堆内存，存放地址肯定不同，c==b肯定返回为false,这个也可以去测试下。

另外，在做字符串拼接操作，也就是字符串相"+"的时候，得出的结果是存在在常量池或者堆里面，这个是根据情况不同不一定的.

这里来一段代码测试下

```text
String str1 = "aaa";
        String str2 = "bbb";
        String str3 = "aaabbb";
        String str4 = str1 + str2;
        String str5 = "aaa" + "bbb";
        System.out.println(str3 == str4); // false
        System.out.println(str3 == str4.intern()); // true
        System.out.println(str3 == str5);// true
```



因此，

1）对于==，一般比较的是值是否相等

- 如果作用于基本数据类型的变量，则直接比较其存储的 “值”是否相等；
- 如果作用于引用类型的变量，则比较的是所指向的对象的地址

2）对于equals方法，一般为比较内容是否相同（只能判断引用类型）

- 如果没有对equals方法进行重写，则比较的是引用类型的变量所指向的对象的地址；

- 诸如String、Date等类对equals方法进行了重写的话，比较的是所指向的对象的内容。

  

**关于equals重写**

Object

```java
public boolean equals(Object obj) {
        return (this == obj);
    }
```

String

```java
public boolean equals(Object anObject) {
        if (this == anObject) {
            return true;
        }
        if (anObject instanceof String) {
            String anotherString = (String)anObject;
            int n = value.length;
            if (n == anotherString.value.length) {
                char v1[] = value;
                char v2[] = anotherString.value;
                int i = 0;
                while (n-- != 0) {
                    if (v1[i] != v2[i])
                        return false;
                    i++;
                }
                return true;
            }
        }
        return false;
    }
```

Integer

```java
public boolean equals(Object obj) {
        if (obj instanceof Integer) {
            return value == ((Integer)obj).intValue();
        }
        return false;
    }
```

date

```java
public boolean equals(Object obj) {
        return obj instanceof Date && getTime() == ((Date) obj).getTime();
    }
```



例题：

```java
package com.hspedu.object_;

//判断两个Person对象的内容是否相等，如果两个Person对象的各个属性值都
//一样，则返回true，反之false。
public class EqualsExercise01 {
    public static void main(String[] args) {
        Person person = new Person("tom", 22, '男');
        Person person1 = new Person("tom", 22, '男');
//        Person person1 = new Person("milan", 23, '女');
        System.out.println(person.equals(person1));
//        if (person.getName() == person1.getName()){
//            System.out.println(true);
//        }


    }
}

class Person {
    private String name;
    private int age;
    private char gender;

    //重写Object类的equals方法
    public boolean equals(Object obj){
        //判断如果比较的两个对象是同一个对象，则直接返回true
        if (this == obj){
            return true;
        }

        //类型判断
        if (obj instanceof Person){//是Person，才去比较
            //向下转型，需要得到obj的各个属性
            Person person = (Person) obj;
            return this.name.equals(person.name) && this.age == person.age && this.gender == person.gender;
        }
        return false;
    }

    public Person(String name, int age, char gender) {
        this.name = name;
        this.age = age;
        this.gender = gender;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public char getGender() {
        return gender;
    }

    public void setGender(char gender) {
        this.gender = gender;
    }
}

```



#### 14.hashCode

`hashCode()`返回对象的哈希码值。

1）目的：提高具有哈希结构的容器的效率

2）两个引用，如果指向的是同一个对象，则哈希值肯定是一样的

3）两个引用，如果指向的是不同的对象，则哈希值是不一样的

4）哈希值主要是根据地址号来的！不能完全将哈希值等价于地址。

```java
        A a = new A();
        A a1 = new A();
        System.out.println(a.hashCode());//460141958
        System.out.println(a1.hashCode());//1163157884
        A a3 = a;
        System.out.println(a3.hashCode());//460141958
```



#### 15.toString

返回对象的字符串表示形式。

源码：

```java
public String toString() {
        return getClass().getName() + "@" + Integer.toHexString(hashCode());
    }

//getClass().getName() 类的全类名（包名+类名）
//Integer.toHexString(hashCode())将对象的hashCode值转成16进制字符串
```

默认返回：全类名 + @ + 哈希值的十六进制

1）子类往往重写toString方法，用于返回对象的属性信息

2）重写toString方法，打印对象或拼接对象时，都会自动调用该方法

3）当直接输出一个对象时，toString方法会默认被调用

```java
package com.hspedu.object_;

public class ToString_01 {
    public static void main(String[] args) {
        aa aa = new aa("123", 12);
        System.out.println(aa.toString());//aa{name='123', age=12}
        System.out.println(aa);//com.hspedu.object_.aa@1b6d3586
    }
}
class aa{
    private String name;
    private int age;

    public aa(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

//    @Override
//    public String toString() {
//        return super.toString();
//    }


    @Override
    public String toString() {
        return "aa{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}

```



#### 16.finalize

当垃圾收集确定不再有对该对象的引用时，垃圾收集器在对象上调用该对象。

1）当对象被回收时，系统自动调用该对象的finalize方法。子类可以重写该方法，做一些释放资源的操作。

2）什么时候被回收：当某个对象没有任何引用时，则jvm就认为这个对象是一个垃圾对象，就会使用垃圾回收机制来销毁该对象，在销毁对象前，会先调用finalize方法。

3）垃圾回收机制的调用，是由系统决定的（即有自己的GC算法），也可以通过System.gc()主动触发垃圾回收机制。

4）实际开发中，几乎不会运用finalize，更多是应对面试。



#### 17.断点调试

实际需求：

1）在开发中，新手程序员在查找错误时，这时老程序员就会温馨提示可以用断点调试，一步一步的看源码执行的过程，从而发现错误所在。

2）重要提示：在断点调试过程中，是运行状态，是以对象的运行类型来执行的。



介绍：

1）断点调试是在程序的某一行设置一个断点，调试时，程序运行到这一行时就会停住，然后你可以一步一步往下调试，调试过程中可以看各个变量当前的值，出错的话，调试到出错的代码行即可显示错误，停下，进而分析找到这个bug。

2）断点调试是程序员必须掌握的技能

3）断点调试可能帮助我们查看java底层源代码的执行过程，提高程序员的Java水平。



F7——跳入方法内

F8——逐行执行代码

shift+F8——跳出方法

F9——执行到下一个断点

![image-20220720132934578](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062253630.png)

![image-20220720141047669](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062253490.png)



4）断点可以在debug过程中，动态的下断点



![image-20220720142145869](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062253964.png)





1.加载类信息

![image-20220720143059481](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062253718.png)

2.构造器初始化

![image-20220720143244338](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062253999.png)

![image-20220720143409236](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302070000459.png)

![image-20220720143629708](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062253559.png)

![image-20220720143710211](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062253202.png)

![image-20220720143809183](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062253378.png)

3.返回对象地址



#### 18.项目

项目需求说明：

使用Java开发零钱通项目，可以完成收益入账、消费、查看明细、退出系统等功能

![image-20220720162112090](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062253408.png)

实现思路：

实现步骤：1）实现零钱通菜单

​					2）实现零钱通明细

​                     3）收益入账

​                      4）消费

​                      5）退出



面向过程实现：

```java
package com.hspedu.smallchange;

import java.text.SimpleDateFormat;
import java.util.Date;
import java.util.Scanner;

public class SmallChangeSys {
    public static void main(String[] args) {
        //化繁为简
        //1.先完成显示菜单，并可以选择菜单，给出对应提示
        //定义退出循环变量
        boolean button = true;


        //定义总金额
        double sum = 0;
        //定义入账金额
        double addMoney = 0;
        //定义消费地点
        String address = "";
        //定义消费金额
        double redMoney = 0;
        //日期处理
        SimpleDateFormat simpleDateFormat = new SimpleDateFormat("yyyy-MM-dd HH:mm");//日期格式化 2022-07-20 17:01


        Scanner scanner = new Scanner(System.in);
        String key = "";

        //字符串拼接实现明细添加
        String details = "---------------\t\t零钱通明细\t\t---------------";

        do {
            System.out.println("\n---------------\t\t零钱通菜单\t\t---------------");
            System.out.println("              \t\t1 零钱通明细\t\t              ");
            System.out.println("              \t\t2 收益入账\t\t                ");
            System.out.println("              \t\t3 消费\t\t                   ");
            System.out.println("              \t\t4 退   出\t\t                ");
            System.out.println("请选择(1-4)：");
            //接收输入信息
            key = scanner.next();
            switch (key) {
                case "1":
                    System.out.println(details);
                    break;
                case "2":
                    System.out.println("请输入收益入账金额：");
                    addMoney = scanner.nextDouble();
                    //校验
                    if (addMoney <= 0){
                        System.out.println("请输入正确的金额！");
                        break;
                    }
                    sum += addMoney;
                    Date date1 = new Date();
                    details += "\n收益入账\t+" + addMoney + "\t" + simpleDateFormat.format(date1) + "\t余额：" + sum;
                    System.out.println("入账成功！");
                    break;
                case "3":
                    //校验
                    if (sum <= 0){
                        System.out.println("没钱消费！！！");
                        break;
                    }
                    System.out.println("请确认消费地点：");
                    address = scanner.next();
                        System.out.println("请输入消费金额：");
                        redMoney = scanner.nextDouble();
                        if (redMoney <= 0){
                            System.out.println("消费不能为0元及以下");
                            break;
                        }
                        if (redMoney >= sum ){
                            System.out.println("余额不足~有" + sum);
                            break;
                        }
                    sum -= redMoney;
                    Date date2 = new Date();
                    details += "\n" + address + "\t-" + redMoney + "\t" + simpleDateFormat.format(date2) + "\t余额：" + sum;
                    System.out.println("消费完成！");
                    break;
                case "4":
                    //确定退出接收
                    String exitButton = "";

                    while (true) {
                        System.out.println("你确定要退出吗？y/n");
                        exitButton = scanner.next();
                        if ("y".equals(exitButton) || "n".equals(exitButton)) {
                            break;
                        }
                        System.out.println("请输入正确的格式！");
                    }

                    if ("y".equals(exitButton)) {
                        button = false;
                        System.out.println("已退出");
                    }
                    break;

                default:
                    System.out.println("请输入正确的选项！（1 零钱通明细 2 收益入账3 消费4 退   出）");
            }
        } while (button);
    }
}

```

面向对象实现：

```java
package com.hspedu.smallchange.oop;

import java.text.SimpleDateFormat;
import java.util.Date;
import java.util.Scanner;

/*
该类是完成零钱通的各个功能的类
使用OOP（面向对象编程）
 */
public class SmallChangeSysOOP {
    boolean button = true;

    //总金额
    private double sum;

    //入账金额
    private double addMoney;

    //定义消费地点
    private String address;

    //定义消费金额
    private double redMoney;

    //日期处理
    SimpleDateFormat simpleDateFormat = new SimpleDateFormat("yyyy-MM-dd HH:mm");

    Scanner scanner = new Scanner(System.in);
    String key = "";
    //字符串拼接实现明细添加
    String details = "---------------\t\t零钱通明细\t\t---------------";

    public void menu(){
        do {
            System.out.println("\n---------------\t\t零钱通菜单oop\t\t---------------");
            System.out.println("              \t\t1 零钱通明细\t\t              ");
            System.out.println("              \t\t2 收益入账\t\t                ");
            System.out.println("              \t\t3 消费\t\t                   ");
            System.out.println("              \t\t4 退   出\t\t                ");
            System.out.println("请选择(1-4)：");
            //接收输入信息
            key = scanner.next();
            switch (key) {
                case "1":
                    this.details();
                    break;
                case "2":
                    this.recorded();
                    break;
                case "3":
                    this.pay();
                    break;
                case "4":
                    this.exit();
                    break;

                default:
                    System.out.println("请输入正确的选项！（1 零钱通明细 2 收益入账3 消费4 退   出）");
            }
        } while (button);
    }

    public void details(){
        //明细
        System.out.println(details);
    }

    public void recorded(){
        //入账
        System.out.println("请输入收益入账金额：");
        addMoney = scanner.nextDouble();
        //校验
        if (addMoney <= 0){
            System.out.println("请输入正确的金额！");
            return;
        }
        sum += addMoney;
        Date date1 = new Date();
        details += "\n收益入账\t+" + addMoney + "\t" + simpleDateFormat.format(date1) + "\t余额：" + sum;
        System.out.println("入账成功！");
    }

    public void pay(){
        //消费
        //校验
        if (sum <= 0){
            System.out.println("没钱消费！！！");
            return;
        }
        System.out.println("请确认消费地点：");
        address = scanner.next();
        System.out.println("请输入消费金额：");
        redMoney = scanner.nextDouble();
        if (redMoney <= 0){
            System.out.println("消费不能为0元及以下");
            return;
        }
        if (redMoney >= sum ){
            System.out.println("余额不足~有" + sum);
            return;
        }
        sum -= redMoney;
        Date date2 = new Date();
        details += "\n" + address + "\t-" + redMoney + "\t" + simpleDateFormat.format(date2) + "\t余额：" + sum;
        System.out.println("消费完成！");
    }

    public void exit(){
        //确定退出接收
        String exitButton = "";

        while (true) {
            System.out.println("你确定要退出吗？y/n");
            exitButton = scanner.next();
            if ("y".equals(exitButton) || "n".equals(exitButton)) {
                break;
            }
            System.out.println("请输入正确的格式！");
        }

        if ("y".equals(exitButton)) {
            button = false;
            System.out.println("已退出");
        }
    }

}

```



#### 19.总结作业

太多不复制。放在idea

#### 20.综合项目

房屋出租系统

需求：实现基于文本界面的《房屋出租软件》。

​			能够实现对房屋信息的添加、修改和删除（用数组实现），并能够打印房屋明细表。

![image-20220722063946220](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062253908.png)



![image-20220722064026293](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062253848.png)



![image-20220722064039434](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062253329.png)

![image-20220722064107784](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062253485.png)

![image-20220722064138048](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062253736.png)

![image-20220722064300885](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062253782.png)

![image-20220722064319177](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062253024.png)



开发模式：分层模式 

![image-20220722064402624](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062253593.png)

实现代码

HouseRentApp

```java
package com.hspedu.house;

import com.hspedu.house.view.HouseView;

public class HouseRentApp {
    public static void main(String[] args) {
        new HouseView().mainMenu();
        System.out.println("您已退出！");
    }
}

```

HouseService

```java
package com.hspedu.house.server;

import com.hspedu.house.domin.House;

//业务层，完成crud
public class HouseService {
    //记录当前房屋信息
    private int houseNums = 1;

    //记录当前id自增长
    private int idCon = 1;

    private House[] houses;

    public HouseService(int size) {
        houses = new House[size];
        houses[0] = new House(1,"milan","125223565","zhangjiapo",2000,"未出租");
    }

    //房屋数据
    public House[] houseList(){
        return houses;
    }

    //新增房屋数据
    public boolean addHouses(House house){
        //判断是否还可以继续添加（暂时不考虑扩容问题）
//        if (houseNums == houses.length){
//            System.out.println("不能在添加");
//            return  false;
//        }

        //判断是否需要扩容
        if (houseNums == houses.length){
            //数组扩容实现
            House house1[] = new House[houses.length + 1];
            for (int i = 0; i < houses.length; i++) {
                house1[i] = houses[i];
            }
            //把新对象加入到数组
            house1[houseNums++] = house;//数组扩容实现方式

            //完成扩容
            houses = house1;
            //保证数组扩容后编号继续自增
            house.setId(++idCon);
            return  true;
        }else {
            //固定数组长度的实现方式（数组扩容前）
            houses[houseNums++] = house;
            //编号自增长
            house.setId(++idCon);
            return true;
        }
    }

    //删除房屋数据
    public boolean delHouse(int house_id){
        System.out.println(house_id);
        int index = -1;
        for (int i = 0; i < houseNums; i++) {
            if (house_id == houses[i].getId()){
                index = i;
            }
        }

        if (index == -1){
            System.out.println("没有对应元素！" + house_id);
            return false;
        }

        for (int i = index; i < houseNums - 1; i++) {
            houses[i] = houses[i+1];
        }
        houses[--houseNums] = null;
        return true;
    }

    //查找房屋
    public House selHouse(int id){
//        if (id <= houses.length && id > -1){
//            return houses[id - 1].getId() +
//                    "\t" + houses[id-1].getName() +
//                    "\t" + houses[id-1].getPhone() +
//                    "\t" + houses[id-1].getAddress() +
//                    "\t" + houses[id-1].getRent() +
//                    "\t" + houses[id-1].getState()
//                    ;
//        }
        for (int i = 0; i < houseNums; i++) {
            if (id == houses[i].getId()){
                return houses[i];
            }
        }
        return null;
    }

    //修改房屋
    public House changeHouse(int id,House house){
        for (int i = 0; i < houseNums; i++) {
            if (id == houses[i].getId()){
                return houses[i];
            }
        }
        return null;
    }

}

```

House

```java
package com.hspedu.house.domin;
//一个House对象表示一个房屋信息

public class House {
    //编号  房主  电话  地址  月租  状态（未出租/已出租）
    private int id;
    private String name;
    private String phone;
    private String address;
    private int rent;
    private String state;

    public House(int id, String name, String phone, String address, int rent, String state) {
        this.id = id;
        this.name = name;
        this.phone = phone;
        this.address = address;
        this.rent = rent;
        this.state = state;
    }

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getPhone() {
        return phone;
    }

    public void setPhone(String phone) {
        this.phone = phone;
    }

    public String getAddress() {
        return address;
    }

    public void setAddress(String address) {
        this.address = address;
    }

    public int getRent() {
        return rent;
    }

    public void setRent(int rent) {
        this.rent = rent;
    }

    public String getState() {
        return state;
    }

    public void setState(String state) {
        this.state = state;
    }

    @Override
    public String toString() {
        return  id +
                "\t" + name +
                "\t" + phone +
                "\t" + address +
                "\t" + rent +
                "\t" + state
                ;
    }
}

```

HouseView

```java
package com.hspedu.house.view;

import com.hspedu.house.domin.House;
import com.hspedu.house.server.HouseService;
import com.hspedu.house.util.Utility;

import java.util.Scanner;

//1)显示界面
//2）接受用户输入
//3）调用HouseService完成对房屋信息的各种操作
public class HouseView {
    //循环显示菜单控制
    private boolean loop = true;
    //接收用户输入
    private char input = ' ';
//    //已有工具类
//    Scanner scanner = new Scanner(System.in);
    //创建HouseService对象，拿到房屋对象数组数据
    private HouseService houseService =new HouseService(10);

    //实现1 新增房屋
    private void addHouse(){
        System.out.println("----------------------添加房屋----------------------");
        System.out.println("姓名：");
        String addName = Utility.readString(5, "暂无");
        System.out.println("电话：");
        String addPhone = Utility.readString(11, "00000000000");
        System.out.println("地址：");
        String addAdress = Utility.readString(10, "暂无");
        System.out.println("月租：");
        int addMoney = Utility.readInt();
        System.out.println("状态(未出租/已出租)：");
        String addState = Utility.readString(3, "未出租");
        House house = new House(0,addName,addPhone,addAdress,addMoney,addState);
        if (houseService.addHouses(house)){
            System.out.println("--------------------添加房屋成功--------------------\n");
        }else {
            System.out.println("--------------------添加房屋失败--------------------\n");
        }
    }

    //实现2 查找房屋
    public void selHouse(){
        System.out.println("----------------------查找房屋----------------------");
        System.out.println("请输入你要查找的id：");
        int id = Utility.readInt();
        House house = houseService.selHouse(id);
        if (house != null){
            System.out.println(house);
        } else {
            System.out.println("----------------------查无此屋----------------------");
        }
    }


    //实现3 删除房屋
    public void delHouse(){
        boolean delOn = true;
        System.out.println("----------------------删除房屋----------------------");
        System.out.println("请选择待删除房屋编号(-1退出):");
        int house_id = Utility.readInt();
        if (house_id == -1){
            System.out.println("----------------------放弃删除----------------------");
            return;
        }

        char choice = Utility.readConfirmSelection();
        if (choice == 'Y'){
            if (houseService.delHouse(house_id)){
                System.out.println("----------------------删除完成----------------------");
            } else {
                System.out.println("----------------------删除失败----------------------");
            }
        } else {
            System.out.println("----------------------放弃删除----------------------");
        }
    }

    //实现4 修改客户
    public void changeHouse(){
        System.out.println("----------------------修改客户----------------------");
        System.out.println("请选择待修改房屋编号（-1退出）：");
        int id = Utility.readInt();
        if (id == -1){
            System.out.println("----------------------放弃修改----------------------");
            return;
        }
        House updateHouse = houseService.selHouse(id);
        if (houseService.selHouse(id) == null){
            System.out.println("----------------------无此数据----------------------");
            return;
        }
        System.out.print("姓名(" + updateHouse.getName() + "):");
        String changeName = Utility.readString(5, "");
        if (!"".equals(changeName)){
            updateHouse.setName(changeName);
        }

        System.out.print("电话(" + updateHouse.getPhone() + "):");
        String changePhone =  Utility.readString(10,"");
        if (!"".equals(changeName)){
            updateHouse.setPhone(changePhone);
        }


        System.out.print("地址(" + updateHouse.getAddress() + "):");
        String changeAddress =  Utility.readString(10,"");
        if (!"".equals(changeAddress)){
            updateHouse.setAddress(changeAddress);
        }

        System.out.print("租金(" + updateHouse.getRent() + "):");
        int changeRent  = Utility.readInt(-1);
        if (changeRent != -1){
            updateHouse.setRent(changeRent);
        }
        updateHouse.setRent(Utility.readInt());

        System.out.print("状态(" + updateHouse.getState() + "):");
        String changeState =  Utility.readString(10,"");
        if (!"".equals(changeState)){
            updateHouse.setState(changeState);
        }

        System.out.println("----------------------修改完成----------------------");
    }




    //实现5 房屋列表
    private void houseList(){
        System.out.println("----------------------房屋列开始----------------------");
        System.out.println("编号\t房主\t\t电话\t\t\t地址\t\t\t月租\t\t状态(未出租/已出租)");
        House house[] = houseService.houseList();
        for (int i = 0; i < house.length; i++) {
            if (house[i] == null){
                break;
            }
            System.out.println(house[i]);
        }
        System.out.println("--------------------房屋列表结束--------------------\n");
    }

    //6 完善退出功能
    public void exitHouse(){
//        for (; ; ) {
//            System.out.println("确认是否退出？（y/n）");
//            char exitAgain = Utility.readChar();
//            if (exitAgain == 'y'){
//                loop = false;
//                System.out.println("已退出！");
//                break;
//            } else if (exitAgain == 'n') {
//                break;
//            }
//        }
        char exits = Utility.readConfirmSelection();
        if (exits == 'Y'){
            loop = false;
            System.out.println("----------------------房屋退出----------------------\n");
        }
    }

    public void mainMenu(){
        do {
            System.out.println("--------------------房屋出租系统--------------------");
            System.out.println("\t\t\t1 新 增 房 源");
            System.out.println("\t\t\t2 查 找 房 屋");
            System.out.println("\t\t\t3 删 除 房 屋");
            System.out.println("\t\t\t4 修 改 房 屋 信 息");
            System.out.println("\t\t\t5 房 屋 列 表");
            System.out.println("\t\t\t6 退 出");
            System.out.println("请输入（1-6）：");
            input = Utility.readChar();
            switch (input){
                case '1':
                    addHouse();
                    break;
                case '2':
                    selHouse();
                    break;
                case '3':
                    delHouse();
                    break;
                case '4':
                    changeHouse();
                    break;
                case '5':
                    houseList();
                    break;
                case '6':
                    exitHouse();
                    break;
                default:
                    System.out.println("请输入正确的选项！");
                    break;
            }
        }while (loop);
    }
}

```

第一阶段完成。





## 4.oop—高级

#### 1.类变量和类方法

提出问题：

有一群小孩在玩堆雪人，不时有新的小孩加入进来，请问如何知道现在共有多少人在玩？编写程序解决。

![image-20220722182755728](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062254582.png)



思路：

1）在main方法中定义一个变量count

2）当一个小孩加入后count++，最后个count就记录多少个

代码：

```java
package com.hspedu.static_;

public class BoysTest {
    public static void main(String[] args) {
        int num = 0;

        Boy boy01 = new Boy("小攻");
        boy01.play();
        num++;
        Boy boy02 = new Boy("小红");
        boy02.play();
        num++;
        Boy boy03 = new Boy("大白");
        boy03.play();
        num++;

        System.out.println("一共有" + num + "个人在堆雪人");

    }
}
class Boy{
    private String name;

    public Boy(String name) {
        this.name = name;
    }

    public void play(){
        System.out.println(name + "在玩堆雪人");
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}

```

问题所在：

1）count独立于对象

2）以后我们访问count很麻烦，没有使用到oop

3）因此，我们引出 类变量/静态变量

```java
//定义一个类变量/静态变量
public static int count = 0;
```



解决思路：

设计一个所有对象共享的变量！（类变量）

1）类变量/静态变量被同一个类所有对象实例共享，格式：类名.类变量名（推荐）

2）static类变量在类加载时已经生成



**细节**：

1）什么时候需要用类变量

当我们需要让某个类的所有对象都共享一个变量时，就可以考虑使用类变量（静态变量）。

比如：定义学生类，统计所有学生共交多少钱。

2）类变量（静态变量）与实例变量（普通属性）的区别

**<span style="color:red">类变量是该类所有对象共享的，而实例变量是每个对象独享的</span>**

3）加上static称为类变量或静态变量，否则称为实例变量/普通变量

4）类变量可以通过  **类名.类变量名** 或 **对象名.类变量名** 来访问，但推荐使用<span style="color:red">**类名.类变量名**</span>方式访问

5）类变量在类加载时就初始化了，也就是说，即使没有创建对象，只要类加载了，就可以使用类变量了。

6）类变量的生命周期 ：<span style="color:red">随着类的加载开始而完成，随着类的消亡而消亡。</span>



**类方法（静态方法）**

```java
访问修饰符 static 数据返回类型 方法名（）{}
```

使用方式：

```java
类名.类变量名()//需满足访问修饰符访问范围和权限
```

应用场景：

当方法中不涉及到任何和对象相关的成员，则可以将方法设计成静态方法，提高开发效率。

比如工具类中的方法 utils、Math类、Array类、Collections集合类

小结：

实际开发中，往往会将一些通用的方法设计成静态方法，比如打印一维数组、冒泡排序，完成某个计算任务等。

<span style="color:red">**静态方法只能访问静态成员。**</span>

<span style="color:red">**非静态方法（普通方法）既可以访问非静态成员，也可以访问静态成员。**</span>



------



#### 2.理解main方法语法

1、main方法的调用者是java虚拟机。
2、因为调用者是java虚拟机，java虚拟机不在该类中也不在该类所在的包中更不是该类的子类，所以main函数的权限只能设置为最大的public，便于java虚拟机的调用。
3、java虚拟机在执行main方法时不必创建对象，所以方法必须是static，也就是在类加载进内存时该方法就可以使用。
4、该方法接收String类型的数组参数，该数据中保存执行java命令时传递给所运行的类的参数。

细节：

1）在main方法中，我们可以直接调用main方法所在类的静态方法或静态属性。

2）但是，不能直接访问该类中非静态成员，必须创建该类的一个实例对象后，才能通过这个对象去访问类中的非静态成员。



------



#### 3.代码块

​		代码块又称为初始化块，属于类中的成员，即是类的一部分，类似于方法，将逻辑语句封装在方法中，通过{}包围起来。

​		和方法不同，没有方法名，没有返回，没有参数，只有方法体，而且不同通过对象或类显式调用，而是在加载类时，或创建对象时显式调用。

基本语法

```java
[修饰符]{
    代码
}; 
```

1）修饰符可选，要写只能写static

2）代码块分为两类，使用static修饰的叫做静态代码块，否则为非静态代码块

3）逻辑语句可以为任何逻辑语句（输入、输出、方法调用、循环、判断等）

4）；可以写上，也可以省略



理解：

1）相当于另外一种形式的构造器（对构造器的补充机制），可以做初始化的操作

2）场景：如果多个构造器中都有重复语句，可以抽取到初始化块中，提高代码的重用



```java
package com.hspedu.codeblock;

public class CodeBlock {
    public static void main(String[] args) {
        Block name = new Block("米兰");

    }
}
class Block{
    private String name;
    private int age;
    private String hobby;
    
    //代码块
    {
        System.out.println("这个代码块无修饰符、无分号");
    }
    //静态代码块，优于普通代码块执行,且只执行一次
    static {
        System.out.println("电影开场");
    };

    public Block(String name) {
        System.out.println("播放广告");
        this.name = name;
    }

    public Block(String name, int age) {
        System.out.println("开始播放");
        this.name = name;
        this.age = age;
    }

    public Block(String name, int age, String hobby) {
        System.out.println("播放中");
        this.name = name;
        this.age = age;
        this.hobby = hobby;
    }
}

```



普通代码块与静态（static）代码块

1）static代码块也叫静态代码块，作用就是对类进行初始化，随着类的加载而执行，并且只会执行一次。

如果是普通代码块，每创建一个对象，就执行。



**2）<span style="color:red">类什么时候被加载（重点！！！）</span>**

> **A.创建对象实例时（new）**
>
> **B.创建子类对象实例时，父类也会被加载**
>
> **C.使用类的静态成员时（静态属性、静态方法）**



3）普通的代码块，在创建对象实例时，会被隐式的调用。创建一次，调用一次。

小结：

<span style="color:red">A.static代码块是类加载时执行，且只会执行一次</span>

<span style="color:red">B.普通代码块是创建对象时调用的，创建一次，调用一次</span>



4）创建一个对象时，在一个类调用顺序是：（**重点！难点！**）

A.调用静态代码块和静态属性初始化

静态代码块与静态属性初始化调用的优先级一样，如果有多个，按照定义顺序调用

B.调用普通代码块和普通属性初始化

普通代码块与普通属性初始化调用的优先级一样，如果有多个，按照定义顺序调用

C.调用构造方法



5）构造器的最前面不仅隐含了super（），还有调用普通代码块。静态相关的代码块，属性初始化，在类加载时，就执行完毕，因此优先于构造器和普通代码块执行。



**6.总顺序**

> **A.父类的静态代码块和静态属性初始化（优先级一样，按定义顺序执行）**
>
> **B.子类的静态代码块和静态属性初始化（优先级一样，按定义顺序执行）**
>
> **C.父类的普通代码块和普通属性初始化（优先级一样，按定义顺序执行）**
>
> **D.父类的构造方法**
>
> **E.子类的普通代码块和普通属性初始化（优先级一样，按定义顺序执行）**
>
> **F.子类的构造方法**



7.静态代码块只能直接调用静态成员（静态属性和静态方法），普通代码块可以调用任意成员。



------



#### 4.单例设计模式

**1、普通饿汉式**

该模式在类被加载时就会实例化一个对象。

```java
package com.hspedu.singletionPattern;
//单例设计模式之饿汉式
public class hungryModel {
    public static void main(String[] args) {
        Hungry.getInstance();
    }
}
class Hungry{
    //步骤：
    //1.将构造器私有化
    //2.在类的内部直接创建对象
    //3.提供一个公共的static静态方法返回该对象
    
    private String name;

    private Hungry(String name) {
        this.name = name;
    }

    //为了能够在静态方法中，返回hungry对象，需要将其修饰为static
    private static Hungry hungry = new Hungry("小猫");

    public static Hungry getInstance(){
        return hungry;
    }
}

```

该模式在类被加载时就会实例化一个对象。

该模式能简单快速的创建一个单例对象，而且是线程安全的(只在类加载时才会初始化，以后都不会)。但它有一个缺点，就是不管你要不要都会直接创建一个对象，会消耗一定的性能(当然很小很小，几乎可以忽略不计，所以这种模式在很多场合十分常用而且十分简单)

优点 

> 1.线程安全 
>
> 2.在类加载的同时已经创建好一个静态对象，调用时反应速度快 

缺点 

> 资源效率不高，可能getInstance()永远不会执行到，但执行该类的其他静态方法或者加载了该类（class.forName)，那么这个实例仍然初始化 



**2、普通懒汉式**

类加载时不初始化，该模式只在你需要对象时才会生成单例对象(比如调用getInstance方法)

```JAVA
package com.hspedu.singletionPattern;
//单例设计模式之懒汉式
public class LazyModel {
    public static void main(String[] args) {
        Lazy.getInstance();
    }
}
class Lazy{
    private static Lazy lazy;

    public static Lazy getInstance(){
        if (lazy == null){
            lazy = new Lazy();
        }
        return lazy;
    }
}
```

优点： 

> 避免了饿汉式的那种在没有用到的情况下创建事例，资源利用率高，不执行getInstance()就不会被实例，可以执行该类的其他静态方法。 



缺点： 

> 懒汉式在单个线程中没有问题，但多个线程同时访问的时候就可能同时创建多个实例，而且这多个实例不是同一个对象，虽然后面创建的实例会覆盖先创建的实例，但是还是会存在拿到不同对象的情况。 假设当前有N个线程同时调用getInstance（）方法，由于当前还没有对象生成，所以一部分同时都进入step 2,那么就会由多个线程创建多个多个user对象。
>
> 解决这个问题的办法就是加锁synchronized，第一次加载时不够快，多线程使用不必要的同步开销大。





#### 5.final关键字

１）final修饰的属性又叫常量，一般用XX_XX_XX来命名

２）final修饰的属性在定义时，必须赋初值，并且以后不能再修改，赋值可以在如下位置之一选择：

- 定义时
- 构造器中
- 代码块中

３）如果final修饰的属性是static静态的，则初始化的位置不能在构造器中赋值，只能是

- 定义时
- 静态代码块中

４）final类不能被继承，但是可以实例化对象

５）final修饰的方法不能被重写，可以被继承。

 6）一般来说，如果一个类已经是final类了，就没有必要再将方法修饰成final方法了。

7）final不能修饰构造方法

8）final和static往往搭配使用，效率更高，不会导致类加载，底层做了优化处理

9）包装类（Integer、Double、Float、Boolean等都是final修饰的），String也是final类。



#### 6.抽象类

**一、抽象类**

在Java中被abstract关键字修饰的类称为抽象类，被abstract关键字修饰的方法称为抽象方法，抽象方法只有方法的声明，没有方法体。抽象类是用来捕捉子类的通用特性的 。它不能被实例化，只能被用作子类的超类。抽象类是被用来创建继承层级里子类的模板。

**抽象类的特点：**

1、抽象类不能被实例化，即不能使用new关键字来实例化对象，只能被继承；

2、包含抽象方法的一定是抽象类，但是抽象类不一定含有抽象方法；

3、抽象类中的抽象方法的修饰符只能为public或者protected，默认为public；

4、抽象类中的抽象方法只有方法体，没有具体实现；

5、如果一个子类实现了父类（抽象类）的所有抽象方法，那么该子类可以不必是抽象类，否则就是抽象类；

6、抽象类可以包含属性、方法、构造方法，但是构造方法不能用于实例化，主要用途是被子类调用。

7、抽象方法不能使用private、final和static来修饰，因为这些关键字都是和重写相违背的。

**抽象类和普通类的主要有三点区别：**

1、抽象方法必须为public或者protected（因为如果为private，则不能被子类继承，子类便无法实现该方法），缺省情况下默认为public。

2、抽象类不能用来创建对象；

3、如果一个类继承于一个抽象类，则子类必须实现父类的抽象方法。如果子类没有实现父类的抽象方法，则必须将子类也定义为为abstract类。

在其他方面，抽象类和普通的类并没有区别。



抽象类最佳实践：模板设计模式

```java
package com.hspedu.abstract_;

//抽象类最佳实践  模板设计模式
//有多个类，完成不同的任务job
//要求统计得到各自完成任务的时间
public class TemplateModel {
    public static void main(String[] args) {
        AA aa = new AA();
        aa.calTimes();

        BB bb = new BB();
        bb.calTimes();


    }
}

class AA extends FatherTimes {

    public void job() {
        long num = 0;
        for (int i = 0; i < 10000000; i++) {
            num += i;
        }
    }
}

class BB extends FatherTimes {

    public void job() {
        long num = 0;
        for (int i = 0; i < 10000000; i++) {
            num += i;
        }
    }
}

abstract class FatherTimes {
    public void calTimes() {
        //得到从1970年1月1日午夜（UTC）开始到当前时间的毫秒值.

        long startTimes = System.currentTimeMillis();
        job();
        long endTimes = System.currentTimeMillis();
        System.out.println("bb" + (endTimes - startTimes));
    }

    abstract public void job();//动态绑定
}

```



#### 7.接口

一、为什么需要接口

因为我们在继承的时候，extends后面只能跟一个类，也就是所谓的单继承，想实现多继承就需要用到接口。

二、测试用例

1.首先生成一个接口
接口中不能定义方法体中的内容

```java
package com.hspedu.interface_;

public interface UsbInterFace {
    //规定接口相关文档
    public void start();
    public void end();
}

```

2.通过类来实现接口
implements + 接口名
实现了类的接口，就必须重写接口中的方法
利用接口实现多继承

```java
public class Camera implements UsbInterFace{
    @Override
    public void start() {
        System.out.println("相机开始工作");
    }

    @Override
    public void end() {
        System.out.println("相机结束工作");
    }
}
```

三、接口的作用

1. 对书写代码具有一定的约束。
2. 定义一些方法，让不同的人根据自己的情况来实现。
3. 接口中定义的方法体默认是public abstract，变量是public abstract final。
4. 接口不能被实例化，即不能new接口，因为接口中没有构造方法。
5. implements可以继承多个接口。
6. 继承接口的类必须要重写接口中的方法。

> 1. 对书写代码具有一定的约束。
> 2. 定义一些方法，让不同的人根据自己的情况来实现。
> 3. 接口中定义的方法体默认是public abstract，变量是public static final。
> 4. 接口不能被实例化，即不能new接口，因为接口中没有构造方法。
> 5. implements可以继承多个接口。
> 6. 继承接口的类必须要重写接口中的方法。



基本介绍：

接口就是给出没有实现的方法，封装到一起，到某个类使用的时候，再根据具体情况把这些方法写出来。

语法：

```java
//接口
interface 接口名{
    //属性
    //方法（1.抽象方法 2.默认实现方法 3.静态方法）
}

//实现
class 类名 implements 接口{
    自己的属性;
    自己的方法;
    以及必须实现的接口的抽象方法
}
```

小结：

1）在jdk7.0以前，接口里所有的方法都没有方法体，即都是抽象方法

2）jdk8.0后接口可以有静态方法，默认方法，也就是说接口中可以有方法的具体实现



细节：

1）接口不能被实例化

2）接口中所有的方法是public方法，接口中抽象方法可以不用写abstract修饰

![image-20220723201300219](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062254677.png)

3）抽象类实现接口，可以不用实现接口的方法。

4）一个普通类实现接口，就必须将该接口的所有方法都实现。

5）一个类同时可以实现多个接口（补充继承的单继承机制，实现多继承）

6）接口中的属性，是public static final修饰的

```java
int n1 = 1;//public static final int = 0;
```

7）接口中属性的访问形式：接口名.属性名

8）接口不能继承其他的类，但是可以继承多个别的接口

```java
interface A extends B,C{};
```

9）接口的修饰符只能是public和默认，这点和类的修饰符是一样的。



继承与接口

1.当子类继承了父类，就自动获得了父类的功能

2.如果子类需要扩展功能，可以通过接口实现

3.可以理解 实现接口是java对单继承机制的一种补充

```java
public class SmallMonkey extends Monkey implements FishAble,BirdAble{

    public SmallMonkey(String name, int age) {
        super(name, age);
    }

    @Override
    public void play() {
        super.play();//System.out.println("猴子会爬树");
    }

    @Override
    public void swimming() {
        System.out.println("猴子学会了游泳");
    }
    @Override
    public void flying() {
        System.out.println("猴子学会了飞翔");
    }
}
```





解决的问题不同：

继承的价值在于：解决代码的复用性和可规范性

接口的价值主要在于：设计，设计好各种规范（方法），让其他类去实现这些方法



接口比继承更加灵活：

继承是is-a的关系，接口是like-a的关系



接口在一定程度上实现了代码解耦（接口规范性和动态绑定）



#### 8.内部类

基本介绍：

一个类的内部又完整嵌套了另一个类结构。

被嵌套的类称为内部类（inner class），嵌套其他类的类称为外部类（outer class）。是类的五大成员之一（属性、方法、构造器、代码块、内部类）。内部类最大的特点就是可以直接访问私有属性，并且可以体现类与类之间的包含关系。

基本语法：

```java
class Outer{//外部类
    class Inner{//内部类
        
    }
}
class Other{//外部其他类
    
}
```



内部类分类：

定义在外部类局部位置上（比如方法内）：

> 1）局部内部类（有类名）
>
> 2）匿名内部类（没有类名，重点！！！！）



定义在外部类的成员位置上：

> 1）成员内部类（没用static修饰）
>
> 2）静态内部类（使用static修饰）



**局部内部类：**

局部内部类定义在外部类的局部位置，比如方法中，并且有类名。

1）可以直接访问外部类的所有成员，包含私有的

2）不能添加访问修饰符，因为他的地位就是一个局部变量。局部变量是不能使用修饰符的。但是可以使用final修饰，因为局部变量也可以使用final修饰。

3）作用域：仅仅在定义他的方法或代码块中。

4）局部内部类——访问——外部类成员【访问方式：直接访问】

5）外部类——访问——局部内部类的成员【访问方式：创建对象访问】

6）局部内部类本质仍是一个类，类该有的东西他都有。

7）外部其他类——不能访问——局部内部类（因为局部内部类的地位是一个局部变量）

8） 如果外部类与局部内部类成员重名，默认就近原则，如果想访问外部类的成员，则可以使用

```java
外部类名.this.成员名
```

```java
package com.hspedu.innerClass;
//演示局部内部类
public class PartInnerClass {
    public static void main(String[] args) {
        OuterPart outerPart = new OuterPart();
        outerPart.show();
    }
}
//外部类
class OuterPart{
    private String nameOuter = "milan";

    private String name = "外部类重名成员";

    private void methodOuter(){
        System.out.println("外部类方法");
    }
    public void show(){
        //局部内部类定义在外部类的局部位置，比如方法中，并且有类名。
        final class Inner{//不能添加访问修饰符，可以使用final修饰
            private int innerAge = 10;
            //与外部类重名的局部内部类成员属性
            private String name;
            //局部内部类可以直接访问外部类的所有成员，包含私有的
            public void partInner(){
                System.out.println("局部内部类方法");
                methodOuter();
                System.out.println("外部类属性：" + nameOuter);
                System.out.println("与局部内部类成员重名的外部内成员：" + OuterPart.this.name);
            }
        }
        //外部类——访问——局部内部类的成员【访问方式：创建对象访问】
        Inner inner = new Inner();
        inner.partInner();
        System.out.println("局部内部类属性：" + inner.innerAge);
    }

    {//局部内部类作用域：仅仅在定义他的方法或代码块中。
        class Inner02{}
    }
}
```

<span style="color:red">

<span style="color:red">**匿名内部类     （重要!!!!!!!!!!!!!）：**</span>

说明：

匿名内部类定义在外部类的局部位置，比如方法中，并且<span style="color:red">没有类名</span>

基本语法：

```java
new 类或接口(参数列表){
    类体
};
```

```java
package com.hspedu.innerClass;
//演示匿名内部类
public class AnonymousInnerClass {
    public static void main(String[] args) {
        OuterClass outerClass = new OuterClass();
        outerClass.methods();
    }
}
//外部类
class OuterClass{
    //外部类属性
    private String name = "这是外部类属性";

    //外部类方法
    private void OuterMethod(){
        System.out.println("这是外部类方法");
    }


    public void methods(){
        /*
            class OuterClass$1 implements IA() {
            @Override
            public void say() {
                System.out.println("匿名内部类实现");
            }
        }
       */
        IA ia = new IA() {
        //匿名内部类只使用一次 底层分配类名OuterClass$1
        //创建后立即实例化
        //基于接口的匿名内部类
        //简化开发
            @Override
            public void say() {
                System.out.println("匿名内部类实现");
            }
        }.say();
//        System.out.println("ia的运行类型：" + ia.getClass());//OuterClass$1
//        ia.say();

        //基于类的匿名内部类
        //简化开发
        /*



         */
//        Father father = new Father("JACK"){
        new Father("JACK"){
            @Override
            public void thank() {
                System.out.println("匿名内部类重写方法");
            }
        }.thank();
//        System.out.println("father:" + father.getClass());//OuterClass$2
    }

}

//接口
interface IA{
    public void say();
}

//外部其他类
class Father{

    public Father() {
    }

    public Father(String str) {
    }

    public void thank(){}
}
```

```java
package com.hspedu.innerClass;

import javax.jws.soap.SOAPBinding;

//匿名内部类
public class AnonymousInnerClass02 {
    public static void main(String[] args) {
        new Outer02().run();
    }
}

//外部类
class Outer02 {
    //外部类的属性
    private String name = "外部类name属性";
    private int age = 10;

    //外部类的方法
    public void play() {
        System.out.println("这是外部类的方法");
    }

    public void run() {
        //匿名内部类
        new Father02() {
            //匿名内部类属性，与外部类属性同名
            private String name = "内部类name属性";

            private void show() {
                System.out.println("这是内部类同名属性：" + name);
                System.out.println("这是外部类同名属性：" + Outer02.this.name);
            }

            @Override
            public void speak() {
                System.out.println("这是匿名内部类重写的speak（）方法 查看该匿名内部类运行类型" + getClass());
            }

            @Override
            public void hobby(String str) {
                super.hobby(str);//这里会回到父类方法
            }
//        }.speak();
//        }.hobby("小明");
        }.show();
    }

}

class Father02 {
    public void speak() {
        System.out.println("我是父亲");
    }

    public void hobby(String str) {
        System.out.println(str + "是一个父亲");
    }
}

```

2.匿名内部类语法比较奇特，因为它既是一个类的定义，同时它本身也是一个对象，因此从语法上看，它既有定义类的特征，也有创建对象的特征，对前面代码可以看出这个特点，因此可以调用匿名内部类方法。、

```java
IA ia = new IA() {
    @Override
    public void say() {
        System.out.println("匿名内部类实现");
    }
};
ia.say();
```

```java
new IA() {
    @Override
    public void say() {
        System.out.println("匿名内部类实现");
    }
}.say();
```

3）可以直接访问外部类的所有成员，包含私有的。

4）不能添加访问修饰符，因为他的地位就是一个局部变量。

5）作用域：仅仅在定义它的方法或代码块中

6）匿名内部类——访问——外部类成员【直接访问】

7）外部其他类——不能访问——匿名内部类（因为匿名内部类地位就是一个局部变量）

8）如果外部类和匿名内部类成员重名，匿名内部类访问的话，默认就近原则。如果想访问外部类的成员，则可以使用（外部类名.this.成员名）去访问.

```java
package com.hspedu.innerClass;
//有一个铃声接口Bell，里面有个ring方法。
//有一个手机类Cellphone，具有闹钟功能alarMclock，参数是Bell类型
//测试手机类的闹钟功能，通过匿名内部类（对象）作为参数，打印：懒猪起床了
//再传入另一个匿名内部类（对象），打印：小伙伴上课了
public class Homework01 {
    public static void main(String[] args) {
        CellPhone cellPhone = new CellPhone();
        cellPhone.alarMcLock(new Bell() {
            @Override
            public void ring() {
                System.out.println("懒猪起床了");
            }
        });
        cellPhone.alarMcLock(new Bell() {
            @Override
            public void ring() {
                System.out.println("小伙伴上课了");
            }
        });
    }
}
interface Bell{
    void ring();
}
class CellPhone{
    public void alarMcLock(Bell bell){
        bell.ring();
    }
}
```



**成员内部类**

说明：

成员内部类定义在外部类的成员位置，并且没有static修饰。

1）可以直接访问外部类的所有成员，包含私有的。

2）可以添加任意访问修饰符（public、protected、默认、private），因为它的地位就是一个成员。

3）作用域：和外部类的其他成员一样，为整个类体。在外部类的成员中创造成员内部类对象，再调用方法。

4）成员内部类——访问——外部类【直接访问】

5）外部类——访问——成员内部类【创建对象、再访问】

6）外部其他类——访问——成员内部类

7）如果外部类和成员内部类成员重名，成员内部类访问的话，默认就近原则。如果想访问外部类的成员，则可以使用（外部类名.this.成员名）去访问.



```java
package com.hspedu.innerClass;
//演示成员内部类
public class memberInnerClass {
    public static void main(String[] args) {
        MemberInnerClass01 memberInnerClass01 = new MemberInnerClass01();
        memberInnerClass01.OuterMember();

        //外部其他类调用成员内部类
        //第一种方式：
        MemberInnerClass01.InnerClass innerClass = memberInnerClass01.new InnerClass();

        //第二种方式
//        public innerClass getInnerClass(){
//            return new innerClass();
//        }
        memberInnerClass01.getInnerClass();
    }
}
class MemberInnerClass01{//外部类
    private String name;
    private int age;

    public void OuterMember(){
        System.out.println("我是外部类");
    }

    //成员内部类
    class InnerClass{
        private String name;
        private int age;

        public void show(){
            System.out.println("我是成员内部类");
        }
    }

    //调用成员内部类
    public void run(){
        InnerClass innerClass = new InnerClass();
        innerClass.show();
    }

    //返回成员内部类
    public innerClass getInnerClass(){
        return new innerClass();
    }
}

```



**静态内部类**

说明：

静态内部类定义在外部类的成员位置，并且有static修饰。

1）可以直接访问外部类的所有静态成员，包含私有的，但不能直接访问非静态成员。

2）可以添加任意访问修饰符，因为他的地位就是类的一个成员。

3）作用域：同其他成员一样，是整个类体。

4）静态内部类——访问——外部类【直接访问所有静态成员】

5）外部类——访问——静态内部类【创建对象，再访问】

6）外部其他类——访问——静态内部类

7）如果外部类和静态内部类成员重名，静态内部类访问的话，默认就近原则。如果想访问外部类的成员，则可以使用（外部类名.成员名）去访问.

```java
package com.hspedu.innerClass;
//演示静态内部类
public class staticInnerClass {
    public static void main(String[] args) {
        OuterClass05 outerClass05 = new OuterClass05();
        outerClass05.run();

        //外部其他类——访问——静态内部类
        //方式1
        OuterClass05.InnerClass05 innerClass05 = new OuterClass05.InnerClass05();
        innerClass05.innerMethod();
        //方式2
        //编写一个方法，可以返回静态内部类实例
        OuterClass05.InnerClass05 inner = outerClass05.getInner();
        inner.innerMethod();

        //方式3
        OuterClass05.InnerClass05 inner02 = OuterClass05.getInner02();
        inner02.innerMethod();
    }
}
//外部类
class OuterClass05{
    private String name;
    private static int age;

    public void outerMethod(){
        System.out.println("外部方法");
    }

    //静态内部类
    static class InnerClass05{
        private int age;
        private String name;

        //静态内部类访问外部类【直接访问所有静态成员】
        public void innerMethod(){
            System.out.println(age);//访问静态内部类成员
            System.out.println(OuterClass05.age);//访问外部类静态成员，不用this
        }
    }

    //外部类——访问——静态内部类【创建对象，再访问】
    public void run(){
        InnerClass05 innerClass05 = new InnerClass05();
        System.out.println(innerClass05.name);
    }

    public InnerClass05 getInner(){
        return new InnerClass05();
    }

    public static InnerClass05 getInner02(){
        return new InnerClass05();
    }
}
```



## 5.枚举注解

### 枚举

（enumeration，简写 enum）

枚举是一组常量的集合。可以这样理解：枚举属于一种特殊的类，里面只包含一组有限的特定的对象。



**自定义枚举：**

1）不需要提供setXXX方法，因为枚举对象值通常为只读。

2）对枚举对象/属性使用final+static共同修饰，实现底层优化

3）枚举对象名通常使用全部大写，常量的命名规范

4）枚举对象根据需要，也可以有多个属性。



自定义枚举过程：

1）构造器私有化

2）本类内部创建对象

3）对外暴露对象（public final static）

4）可以提供getXXX方法，但不能提供setXXX方法

实例如下：

```java
package com.momo.enum_;

/**
 * @author momo~
 * @version 1.0
 */
public class Enumeration02 {
    public static void main(String[] args) {
        System.out.println(SeasonEnum.AUTUMN);
        System.out.println(SeasonEnum.SPRING);
        System.out.println(SeasonEnum.SUMMER);
        System.out.println(SeasonEnum.WINTER);
    }
}
class SeasonEnum{
    private String name;
    private String desc;

    //自定义枚举第三步：直接在类内部完成数据创建，final修饰完成只读
    public final static SeasonEnum SPRING = new SeasonEnum("春天","温暖");
    public final static SeasonEnum SUMMER = new SeasonEnum("夏天","炎热");
    public final static SeasonEnum AUTUMN = new SeasonEnum("秋天","凉爽");
    public final static SeasonEnum WINTER = new SeasonEnum("冬天","寒冷");


    //自定义枚举第一步：构造器私有化，防止new
    private SeasonEnum(String name, String desc) {
        this.name = name;
        this.desc = desc;
    }

    public String getName() {
        return name;
    }

    //自定义枚举第二步：删除setXXX方法，防止修改
//    public void setName(String name) {
//        this.name = name;
//    }

    public String getDesc() {
        return desc;
    }

//    public void setDesc(String desc) {
//        this.desc = desc;
//    }


    @Override
    public String toString() {
        return "SeasonEnum{" +
                "name='" + name + '\'' +
                ", desc='" + desc + '\'' +
                '}';
    }
}
```



使用enum关键字完成：

1）使用enum替代class

2）常量名（实参列表）

3）如果有多个常量对象，使用 , 分隔

4）将常量对象写在最前面

```java
package com.momo.enum_;

/**
 * @author momo~
 * @version 1.0
 */
public class Enumeration03 {
    public static void main(String[] args) {
        System.out.println(SeasonEnumeration.AUTUMN);
        System.out.println(SeasonEnumeration.SPRING);
        System.out.println(SeasonEnumeration.SUMMER);
        System.out.println(SeasonEnumeration.WINTER);
    }
}
enum SeasonEnumeration{
    SPRING("春天","温暖"),SUMMER("夏天","炎热"),AUTUMN("秋天","凉爽"),WINTER("冬天","寒冷");
    private String name;
    private String desc;

    private SeasonEnumeration(String name, String desc) {
        this.name = name;
        this.desc = desc;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getDesc() {
        return desc;
    }

    public void setDesc(String desc) {
        this.desc = desc;
    }

    @Override
    public String toString() {
        return "SeasonEnumeration{" +
                "name='" + name + '\'' +
                ", desc='" + desc + '\'' +
                '}';
    }
}
```



**enum关键字实现枚举注意事项**

1）当我们使用enum关键字开发一个枚举类时，默认会继承Enum类，而且是一个final类

2）传统实现方式里public final static SeasonEnum SPRING = new SeasonEnum("春天","温暖");

​	使用enum关键字后简化成SPRING("春天","温暖");这里调用的是两个实参为字符串的构造器

3）如果使用无参构造器创建对象，则实参列表和小括号都可以省略

4）当有多个枚举对象时，使用 , 间隔，最后有一个分号

5）枚举对象必须放在枚举类的行首



**enum常用方法**

1）ordinal()方法: 返回枚举值在枚举类种的顺序（这个顺序是枚举值声明的顺序）

2） compareto()方法: Enum实现了java.lang.Comparable接口，因此可以比较象与指定对象的顺序。Enum中的compareTo返回的是两个枚举值的顺序之差。当然，前提是两个枚举值必须属于同一个枚举类，否则会抛出ClassCastException()异常。(具体可见源代码)

3）values()方法： 静态方法，返回一个包含全部枚举值的数组。

4）toString()方法： 返回枚举常量的名称。

5）valueOf()方法： 这个方法和toString方法是相对应的，返回带指定名称的指定枚举类型的枚举常量。

6）equals()方法： 比较两个枚举类对象的引用

![image-20220724184502972](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062254932.png)

```java
    public static void main(String[] args) {
        System.out.println(SeasonEnumeration.AUTUMN);
        System.out.println(SeasonEnumeration.SPRING);
        System.out.println(SeasonEnumeration.SUMMER);
        System.out.println(SeasonEnumeration.WINTER);

        SeasonEnumeration season = SeasonEnumeration.WINTER;
        //name() 返回枚举常量的名称，建议优先使用toString()方法
        System.out.println(season.name());//WINTER
        //toString()方法： 返回枚举常量的名称。
        System.out.println("返回枚举常量的名称:"+season.toString());//WINTER
        //ordinal()方法:返回枚举值在枚举类种的顺序（这个顺序是枚举值声明的顺序）
        System.out.println(season.ordinal());//3
        //values()方法： 静态方法，返回一个包含全部枚举值的数组。
        SeasonEnumeration[] values = SeasonEnumeration.values();
        for(SeasonEnumeration i : values){//增强for循环
            System.out.println(i);
        }
        //valueOf()方法： 这个方法和toString方法是相对应的，返回带指定名称的指定枚举类型的枚举常量。
        System.out.println("valueOf():"+SeasonEnumeration.valueOf("SPRING"));
        //Enum实现了java.lang.Comparable接口，因此可以比较象与指定对象的顺序。
        // Enum中的compareTo返回的是两个枚举值的顺序之差 SPRING编号—AUTUMN编号 = 0 - 2 = -2
        System.out.println("compareTo():" + SeasonEnumeration.SPRING.compareTo(SeasonEnumeration.AUTUMN));
    }
```



注意：

1）使用enum关键字后，就不能再继承其他类了，因为enum会隐式继承Enum，Java是单继承机制。

2）枚举类和普通类一样，可以实现接口。



### **注解**

1）注解（Annotation）也被称为元数据（Metadata），用于修饰解释包、类、方法、属性、构造器、局部变量等信息，

2）和注释一样，注解不影响程序逻辑，但注解可以被编译或运行，相当于嵌入在代码中的补充信息

3）在JavaSE中，注解的使用目的比较简单，例如标记过时的功能，忽略警告等。在JavaEE中，注解占据了更重要的角色，例如用来配置应用程序的任何切面，代替java旧版中所遗留的繁冗代码和XML配置等。



**@Override**

1）表示指定重写父类的方法（从编译层面验证），如果父类没有fly方法，则会报警

2）@Override只修饰方法，不能修饰其他类、包、属性等，源码如下

@Target(ElementType.METHOD)



```java
@Override 源代码如下：

@Target(ElementType.METHOD)//修饰注解的注解，称为元注解，说明@Override只能修饰方法
@Retention(RetentionPolicy.SOURCE)
public @interface Override {
}
//@interface 不是接口interface，是注解类 jdk1.5之后加入
```



**@Deprecated**

1）用于表示某个程序元素已过时，不是不能用，是不推荐用，作版本兼容与过度

2）可以修饰类、方法、字段、包、参数等，源码如下

@Target(value={CONSTRUCTOR, FIELD, LOCAL_VARIABLE, METHOD, PACKAGE, PARAMETER, TYPE})

```JAVA
@Documented
@Retention(RetentionPolicy.RUNTIME)
@Target(value={CONSTRUCTOR, FIELD, LOCAL_VARIABLE, METHOD, PACKAGE, PARAMETER, TYPE})
public @interface Deprecated {
}
```



**@SuppressWarnings**

1）unchecked ：忽略没有检查的警告

2）rawtypes：忽略没有指定泛型的警告

3）unused：忽略没有使用某个变量的警告

4）生成@SuppressWarnings时，不用背，直接点击左侧黄色提示就可以选择

```java
@Target({TYPE, FIELD, METHOD, PARAMETER, CONSTRUCTOR, LOCAL_VARIABLE})
@Retention(RetentionPolicy.SOURCE)
public @interface SuppressWarnings {
        String[] value();
}
```



**元注解**

JDK的元注解用于修饰其他的注解

元注解本身作用并不大，主要是看懂源码

元注解种类：

1）Retention   //指定注解的作用范围，三种source、class、runtime

2）Target //指定注解可以在哪些地方使用

3）Documented //指定该注解是否会在javadoc体现

4）Inherited //子类会被继承父类注解

详情见https://blog.csdn.net/weixin_48554146/article/details/123848098



### 总结作业：

```java
package com.momo.homework;
/*
    1）在Frock类中声明私有的静态属性currentNum【int类型】，初始值为100000，作为衣服出厂
       的序列号起始值
    2）声明公有的静态方法getNextNum，作为生成上衣唯一序列号的方法。每调用一次，将currentNum
      增加100，并作为返回值。
    3）在TestFrock类的main方法中，分两次调用getNextNum方法，获取序列号并打印输出。
    4）在Frock类中声明seriaINumber（序列号）属性，并提供对应的get方法。
    5）在Frock类的构造器中，通过调用getNextNum方法为Forck对象获取唯一序列号，赋给seriaINumber属性
    6）在TestFrock类的main方法中，分别创建三个Frock对象，并打印三个对象的序列号，验证是否为100递增。

 */
/**
 * @author momo~
 * @version 1.0
 */
public class Homework01 {
}
class Frock{
    //序列号起始值
    private static int currentNum = 100000;

    private int seriaINumber;

    public Frock() {
        this.seriaINumber = getNextNum();
    }

    public int getSeriaINumber() {
        return seriaINumber;
    }

    public static int getNextNum(){
        return currentNum += 100;
    }
}
class TestFrock{
    public static void main(String[] args) {
        System.out.println("第一次调用序列号：" + Frock.getNextNum());;
        System.out.println("第一次调用序列号：" + Frock.getNextNum());;

        Frock frock1 = new Frock();
        System.out.println("seriaINumber:" + frock1.getSeriaINumber());
        Frock frock2 = new Frock();
        System.out.println("seriaINumber:" + frock2.getSeriaINumber());
        Frock frock3 = new Frock();
        System.out.println("seriaINumber:" + frock3.getSeriaINumber());
    }
}
```

```java
package com.momo.homework;
/*
    1)动物类Animal包含了抽象方法shout();
    2)Cat类继承Animal，并实现了方法shout，打印“猫会喵喵叫”
    3)Dog类继承了Animal，并实现了方法shout，打印“狗会汪汪叫”
    4）在测试类中实例化对象Animal cat = new Cat(),并调用cat的shout方法
    5）在测试类中实例化对象Animal dog = new Dog(),并调用dog的shout方法
 */
/**
 * @author momo~
 * @version 1.0
 */
public class Homework02 {
    public static void main(String[] args) {
        Animal cat = new Cat();
        cat.shout();
        Animal dog = new Dog();
        dog.shout();
    }
}
abstract class Animal{
    public abstract void shout();
}
class Cat extends Animal{

    @Override
    public void shout() {
        System.out.println("猫会喵喵叫");
    }
}
class Dog extends Animal{

    @Override
    public void shout() {
        System.out.println("狗会汪汪叫");
    }
}

```

```java
package com.momo.homework;
/*
    1)计算器接口具有work方法，功能是运算，有一个手机类Cellphone，定义方法testWork
      测试计算功能，调用计算接口的work方法
    2）要求调用CellPhone对象的testWork方法，使用上匿名内部类
 */
/**
 * @author momo~
 * @version 1.0
 */
public class Homework03 {
    public static void main(String[] args) {
        CellPhone cellPhone = new CellPhone();
        cellPhone.testWork(new Calculator() {
            @Override
            public double work(double d1, double d2) {
                return d1 + d2;
            }
        },5.6,3.1);
    }
}
interface Calculator{
    //接口中所有的方法是public方法，
    //接口中抽象方法可以不用写abstract修饰
    double work(double d1,double d2);
}
class CellPhone{
    public void testWork(Calculator calculator,double d1,double d2){
        double res = calculator.work(5.3, 2.3);
        System.out.println(res);
    }
}
```

```java
package com.momo.homework;
/*
    1)编一个类A,在类中定义局部内部类B，B中有一个私有常量name，有一个方法shoW（）
      打印常量name。进行测试
    2）进阶：A中也定义一个私有变量name。在show方法中打印测试
 */
/**
 * @author momo~
 * @version 1.0
 */
public class Homework04 {
    public static void main(String[] args) {
        A a = new A();

    }
}

class A{
    private String name = "outer";

    {
        class B{
            private String name = "momo";
            public void show(){
                System.out.println("内部类变量：" + name);
                System.out.println("外部类变量：" + A.this.name);
            }
        }
        B b = new B();
        b.show();
    }


}
```

重点案例！

```java
package com.momo.homework;
/*
    1)有一个交通工具接口类Vehicles，有work接口
    2）有Horse类和Boat类分别实现Vehicles
    3）创建交通工具工厂类，有两个方法分别获得交通工具Horse和Boat
    4）有Person类，有name和Vehicles属性，在构造器中为两个属性赋值
    5）实例化Person对象“唐僧”，要求一般情况下用Horse作为交通工具，遇到大河时用
      Boat作为交通工具
 */
/**
 * @author momo~
 * @version 1.0
 */
public class Homework06 {
    public static void main(String[] args) {
        Person  person = new Person("唐僧",new Horse());
        person.ridHorse();
        person.byBoat();
        person.walk();
    }
}
//交通工具接口类Vehicles
interface Vehicles {
    void work();
}
//马类
class Horse implements Vehicles{
    @Override
    public void work() {
        System.out.println("一般情况下骑马");
    }
}
//船类
class Boat implements Vehicles{
    @Override
    public void work() {
        System.out.println("遇到大河时坐船");
    }
}

class Cloud implements Vehicles{
    @Override
    public void work() {
        System.out.println("过火焰山用筋斗云");
    }
}

package com.momo.homework;

/**
 * @author momo~
 * @version 1.0
 */
public class VehiclesPlant {
    private static Horse horse = new Horse();

    private static Cloud cloud = new Cloud();

    //马只需要一匹，用单例设计模式之饿汉模式
    public static Horse getHorse(){
        return horse;
    }

    public static Boat getBoat(){;
        return new Boat();
    }

    public static Cloud getCloud(){
        return cloud;
    }

}
class Person{
    private String name;
    private Vehicles vehicles;

    public Person(String name, Vehicles vehicles) {
        this.name = name;
        this.vehicles = vehicles;
    }

    //骑马
    public void ridHorse(){
//        Horse horse = VehiclesPlant.getHorse();
//        horse.work();
        if (!(vehicles instanceof Horse)){
            vehicles = VehiclesPlant.getHorse();
        }
        vehicles.work();
    }

    //坐船
    public void byBoat() {
//        Boat boat = VehiclesPlant.getBoat();
//        boat.work();
//    }
        if (!(vehicles instanceof Boat)) {
            vehicles = VehiclesPlant.getBoat();
        }
        vehicles.work();
    }

    public void walk(){
        if (!(vehicles instanceof Cloud)){
            vehicles = VehiclesPlant.getCloud();
        }
        vehicles.work();
    }
}

```

```java
package com.momo.homework;
/*
    1)有一个Car类，有属性temperature（温度），车内有Air（空调）类，有吹风的功能
      flow，Air会监视车内的温度，如果温度超过40度则吹冷风，如果温度低于0都则吹暖风
      如果在这之间则关掉空调，实例化具有不同温度的Car对象，调用空调的flow方法，测试
      空调吹的是否正确。
 */
/**
 * @author momo~
 * @version 1.0
 */
public class Homework07 {
    public static void main(String[] args) {
        Car car1 = new Car(45);
        Car car2 = new Car(25);
        Car car3 = new Car(-13);
        car1.run();
        car2.run();
        car3.run();
    }
}
class Car{
    //温度
    private double temperature;

    public Car(double temperature) {
        this.temperature = temperature;
    }

    class Aie{
        private void flow(){
            if (temperature > 40){
                System.out.println("吹冷风");
            } else if (temperature < 0) {
                System.out.println("吹暖风");
            } else {
                System.out.println("关掉空调");
            }
        }
    }

    public void run(){
        Aie aie = new Aie();
        aie.flow();
    }
}
```

```JAVA
package com.momo.homework;
/*
    1)创建一个Color枚举类
    2）有RED、BLUE、BLACK、YELLOW、GREEN这五个枚举值/对象。
    3）Color有三个属性redValue、greenValue、blueValue
    4）创建构造器，参数包括这三个属性
    5）每个枚举值都要给这三个属性赋值，三个属性分别对应的值是
    6）red：255、0、0 blue：0、0、255 black：0、0、0
       yellow：255、255、0 green：0、255、0
    7）定义接口，里面有方法show、要求Color实现该接口
    8）show方法中显示三属性的值
    9）将枚举对象在switch语句中匹配使用

 */

/**
 * @author momo~
 * @version 1.0
 */
public class Homework08 {
    public static void main(String[] args) {
        Color red = Color.YELLOW;
        red.show();
        switch (red) {
            case RED:
                System.out.println("红色");
            case BLUE:
                System.out.println("蓝色");
            case BLACK:
                System.out.println("黑色");
            case GREEN:
                System.out.println("绿色");
            case YELLOW:
                System.out.println("黄色");
            default:
                System.out.println("无匹配");
        }
    }
}

interface Inter {
    void show();
}

enum Color implements Inter {
    RED(255, 0, 0), BLUE(0, 0, 255),
    BLACK(0, 0, 0), YELLOW(255, 255, 0), GREEN(0, 255, 0);
    private int redValue;
    private int greenValue;
    private int blueValue;

    Color(int redValue, int greenValue, int blueValue) {
        this.redValue = redValue;
        this.greenValue = greenValue;
        this.blueValue = blueValue;
    }

    @Override
    public void show() {
        System.out.println(redValue + "   " + greenValue + "   " + blueValue);
    }

    public int getRedValue() {
        return redValue;
    }

    public int getGreenValue() {
        return greenValue;
    }

    public int getBlueValue() {
        return blueValue;
    }
}

```



## 6.异常

**异常概念**

Java语言中，将程序执行中发生的不正常情况称为”异常“。

**两大类：**

1）**error错误**：Java虚拟机无法解决的严重问题，如：JVM系统内部错误，资源耗尽等严重情况。比如StackOverFlowError【栈溢出】和OOM（out of memory），Error是严重错误，程序会崩溃

2）**Exception**：其他因编译错误或偶然的外在因素导致的一般性问题，可以使用针对性的代码进行处理。

例如空指针异常，试图读取不存在的文件，网络链接中断等等。Exception分为两大类：运行时异常【程序运行时，发生的异常】和编译时异常【编程时，编译器检查出的异常】



![image-20220725143045220](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062255317.png)



1）异常分为两大类，运行时异常和编译时异常

2）运行时异常，编译器检查不出来。一般是指编程时的逻辑错误，是程序员应该避免的异常。java.lang.

RuntimeException类及其子类都是运行时异常

3）对于运行时异常，可以不做处理

4）编译时异常，是编译器必须要求处理的异常



**五大运行时异常**

1）NullPointerException  空指针异常

当应用程序试图在需要对象的地方使用null时，抛出该异常。

![image-20220725144403137](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062255909.png)



2）ArithmeticException  数学运算异常

抛出异常算术条件时抛出。 例如，“除以零”的整数会抛出此类的一个实例。



3）ArrayIndexOutOfBoundsException    数组下标越界异常

抛出以表示使用非法索引访问数组。 索引为负数或大于或等于数组的大小。



4）ClassCastException   类型转换异常

抛出表示代码尝试将对象转换为不属于实例的子类。 例如，以下代码生成一个`ClassCastException` ：

> ```java
> Object x = new Integer(0);
> System.out.println((String)x);
> ```



5）NumberFormatException   数字格式不正确异常 

抛出以表示应用程序已尝试将字符串转换为其中一个数字类型，但该字符串不具有相应的格式。



编译异常

是指编译期间，就必须处理掉的异常，否则代码不能通过编译

常见的编译时异常

SQLException    //操作数据库时，查询表可能发生的异常

IOException    //操作文件时发生的异常

FileNotFoundException    //当操作一个不存在的文件时发生的异常

ClassNotFoundException    //加载类，而该类不存在，发生异常

EOFException    //操作文件，到文件末尾发生异常

IllegaIArguementException    //参数异常



异常处理机制：

当异常发生时，对异常处理的方式。

1）try—catch—finally

程序员在代码中捕获发生的异常，自行处理

2）throws

将发生的异常抛出，交给调用者（方法）来处理，最顶级的处理者就是JVM

(发生异常后如果不处理，默认用throws抛出至jvm打印错误信息，停止程序)



![image-20220725151643732](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062255097.png)



![image-20220725153249346](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062255912.png)



try—catch

1）Java提供try和catch块来处理异常。try块用于处理可能出错的代码。catch块用于处理try块中的异常。

2）基本语法

```JAVA
try{
    //可疑代码
    //将异常生成对应的异常对象，传递给catch块
}catch（异常）{
    //对异常的处理
}//如果没有finally，语法可以通过
```

处理：

1）如果异常发生了，则异常后面的代码不会执行，直接进入到catch块

2）如果异常没有发生，则顺序执行try的代码块，不会进入到catch

3）如果希望不管有没有发生异常都执行某段代码（比如关闭连接、释放资源等），则使用finally

4）可以有多个catch语句，捕获不同的异常（进行不同的业务处理），要求父类异常在后，子类异常在前，

比如EException在后，NullPointerException在前，如果发生异常，就只会匹配一个catch

```javca
try{
}catch(NullPointerException){
}catch(Exceptino e){
}finally{
}
```

5）可以try—finally配合使用，这种用法相当于没有捕获异常，因此程序会直接崩掉

```java
try{
  //代码
}finally{
  //总是执行
}
```

案例：

```java
package com.momo.exception;

/**
 * @author momo~
 * @version 1.0
 */
public class Exception01 {
    public static void main(String[] args) {
        int a = 1;
        int b = 0;

        try {
            int c = a / b;
            System.out.println("我咋了");
        }finally {
            System.out.println("finally");
        }
//        } catch (ArithmeticException e) {
//            System.out.println("ArithmeticException");;
//        }catch (Exception e){
//            System.out.println("Exception");
//        }


        System.out.println("程序继续执行，。。。");
        //Exception in thread "main" java.lang.ArithmeticException: / by zero
        //	at com.momo.exception.Exception01.main(Exception01.java:11)
    }
}

```

```java
package com.momo.exception;
/*
    1)如果用户输入的不是一个整数，就提示它反复输入，直到输入一个整数为止
    try—catch实现
 */

import java.util.Scanner;

/**
 * @author momo~
 * @version 1.0
 */
public class Homework01 {
    public static void main(String[] args) {
        Run run = new Run();
        run.nextInt();

    }
}

class Run {
    Scanner scanner = new Scanner(System.in);

    public void nextInt() {
        while (true) {
            try {
                System.out.println("请输入一个整数：");
                int i = Integer.parseInt(scanner.next());
                break;
            } catch (NumberFormatException e) {
                System.out.println("请输入一个整数：");;
            }

        }
    }
}
```



throws异常处理

1）如果一个方法（中的语句执行时）可能生成某种异常，但是并不能确定如何处理这种异常，则此方法应当显式的声明抛出异常，表明该方法将不对这些异常进行处理，而是由该方法发的调用者负责处理。

2）在方法声明中用throws语句可以声明抛出异常的列表，throws后面的异常类型可以是方法中产生的异常类型，也可以是他的父类。



细节：

1）对于编译异常，程序中必须处理

2）对于运行时异常，程序中如果没有处理，默认就是throws的方式处理。

3）子类重写父类的方法时，对抛出异常的规定：子类重写的方法所抛出的异常，要么于父类抛出的异常一致，要么是父类抛出异常类型的子类型。

4）在throws过程中，如果有方法try—catch，就相当于处理异常，就可以不必throws



自定义异常

1）定义类：自定义异常类名（自己写），继承Exception或RuntimeException

2）如果继承Exception，属于编译异常

3）如果继承RuntimeException，属于运行时异常，一般来说，继承运行时异常



**throw与throws**

![image-20220725173554028](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062255892.png)



```java
package com.momo.exception;
/*
    1）编写应用程序EcmDef.java 接收命令行的两个参数（整数），计算两数相除
    2）计算两个数相除，要求使用方法cal（int n1，int n2）
    3）对数据格式不正确、缺少命令行参数、除0进行异常处理
 */

import java.util.Scanner;

/**
 * @author momo~
 * @version 1.0
 */
public class Homework02 {
    public static void main(String[] args) {

        try {
            if (args.length != 2) {
                throw new ArrayIndexOutOfBoundsException("参数个数不正确");
            }

            int n1 = Integer.parseInt(args[0]);
            int n2 = Integer.parseInt(args[1]);

            double res = cal(n1, n2);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println(e.getMessage());
        } catch (NumberFormatException e) {
            System.out.println("参数格式不正确");
        } catch (ArithmeticException e){
            System.out.println("出现了除0的异常");
        }

    }

    public static double cal(int n1, int n2) {
        return n1 / n2;
    }
}
```



## 7.常用类

### 1.包装类

针对八种基本数据类型相应的引用类型，有了类的特点，可以调用类中的方法

![image-20220726114758472](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062255273.png)

![image-20220726115753258](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062255992.png)



**装箱与拆箱**

1）JDK5之前的手动装箱和拆箱方式：

```java
//手动装箱
int a = 1;
Integer integer1 = new Integer(a);
Integer integer = Integer.valueOf(a);
//手动拆箱
Integer integer2 = new Integer(99);
int i = integer2.intValue();
```

2）JDK5以后（含JDK5）的自动装箱和自动拆箱方式

```java
//自动装箱
int n1 = 12;
Integer n2 = n1;
//自动拆箱
Integer integer3 = new Integer(98);
int n3 = integer3;
```

3）自动装箱底层调用的是valueOf（）方法，与手动装箱一致，自动拆箱同理调用的是intValue（）方法



**包装类与String相互转换**

```JAVA
//包装类型——》String类型
Integer num1 = 100;//自动装箱
//方式1
String st1 = num1 + "";
//方式2
String str2 = num1.toString();
//方式3
String str3 = String.valueOf(num1);

//String类型——》包装类型
String str4 = "123";
//方式1
Integer int1 = Integer.parseInt(str4);
//方式2
Integer int2 = Integer.valueOf(str4);
```



**包装类常用方法**

```java
System.out.println(Integer.MIN_VALUE);//返回最小值
System.out.println(Integer.MAX_VALUE);//返回最大值
System.out.println(Character.isDigit('1'));//判断是不是数字
System.out.println(Character.isLetter('A'));//判断是不是字母
System.out.println(Character.isUpperCase('a'));//判断是不是大写
System.out.println(Character.isLowerCase('A'));//判断是不是小写
System.out.println(Character.isWhitespace('A'));//判断是不是空格
System.out.println(Character.toUpperCase('a'));//转成大写
System.out.println(Character.toLowerCase('A'));//转成小写
```



Integer.valueOf()

```java
public static Integer valueOf(int i) {
    if (i >= IntegerCache.low && i <= IntegerCache.high)
        return IntegerCache.cache[i + (-IntegerCache.low)];
    return new Integer(i);
}
```

IntegerCache.calss

```java
Cache to support the object identity semantics of autoboxing for values between -128 and 127 (inclusive) as required by JLS.
根据JLS的要求，缓存支持自动装箱-128到127(包括)之间的值的对象标识语义。
```

所以

```java
public void method1(){
    Integer i = new Integer(1);
    Integer j = new Integer(j);
    System.out.println(i == j);//false
    
    Integer m = 1;
    Integer n = 1;
    System.out.println(m == n);//true
    
    Integer x = 128;
    Integer y = 128;
    System.out.println(x == y);//false
}
```



### 2.String类

![image-20220726133201656](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062255147.png)



1）String对象用于保存字符串，也就是一组字符序列。

2）字符串常量对象是用双引号括起来的字符序列。例如："hello"、"123"、"你好"

3）字符串的字符使用Unicode字符编码，一个字符（不区分大小写）占两个字节。

4）String类较常用构造

```java
String s1 = new String();
String s1 = new String(String original);
String s1 = new String(char[] a);
String s1 = new String(char[],int startIndex,int count);
```

![image-20220726135311278](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062255973.png)

```java
The value is used for character storage.
该值用于字符存储。
```

String值真正存储在字符数组里。且由final修饰。



![image-20220726141111336](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062255745.png)

![image-20220726141148290](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062255466.png)



1）String是一个final类，代表不可变的字符序列。

2）字符串是不可变的。一个字符串对象一旦被分配，其内容是不可变的。

![image-20220726154938590](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062255864.png)



String类的常见方法

String类是保存字符串常量的。每次更新都需要重新开辟空间，效率较低，因此java设计者还提供了StringBuilder和StringBuffer来增强Striing的功能，并提高效率。

```java
public class StringDemo {
	
	
	public static void main(String[] args) { 
	
	//字符串是一个类 字符串变量是引用数据类型
	//""引起来的内容就是字符串  只要是字符串就能调用字符串中的方法
	System.out.println("zhangsan".equals("ddd"));
	//字符串里面的常用方法如下
	String strA = "zhangsan";
	String strB =  "LISI";
	String strC =   " 王五";
	
	//长度 返回字符串长度 length() 注意 此时的length是方法 不是变量后面的.length
	System.out.println("返回字符串的长度："+strA.length());
	
	//字符串拼接 concat或者+
	System.out.println("字符串拼接:"+strA.concat("王五"));
	System.out.println("字符串拼接:"+strB.concat("李四"));
	
	//字符串判断 
	//相等判断 
	System.out.println("比较两个字符串的内容 相等返回true 否则返回false："+strA.equals("zhangsana"));
	//是否为空判断
	System.out.println("判断字符串是否为空为空返回true 否则返回salse："+strA.isEmpty());
	//相等判断忽略大小写
	System.out.println("比较两个字符串的内容忽略大小写 相等返回true 否则返回false："+strA.equalsIgnoreCase("ZHANGSAN"));
	//按字典顺序比较 返回的整数 0代表相同 排在之前为负数 否则为正数 
	System.out.println("按字典顺序比较 返回的整数 0代表相同 排在之前为负数 否则为正数: "+strA.compareTo(strB));
	//按字典顺序进行比较 忽略大小写
	System.out.println("按字典顺序进行比较 忽略大小写："+strA.compareToIgnoreCase("ZHANGSAN"));
	//判断是否以特定字符开头 是返回true 否则返回false
	System.out.println("判断是否以特定字符串开头:"+strA.startsWith("zh"));
	//判断是否以特定字符串结尾
	System.out.println("判断是否以特定字符串结尾: "+strA.endsWith("a"));
	
	System.out.println("");	
	System.out.println("");
	//字符串转换
	//把字符串全部转换成大写
	System.out.println("把字符串全部转换成大写:"+strA.toUpperCase());
	//把字符串全部转换成小写
	System.out.println("把字符串全部转换成小写:"+strB.toLowerCase());
	//将字符串转换成字节数组
	System.out.println("将字符串转换成字节数组:"+strA.getBytes());
	//将基本数据类型转换成字符串
	System.out.println("将基本数据类型转换成字符串:"+strA.valueOf(123));
	//去掉前后空白
	System.out.println("去掉前空白:"+strC.trim());
	
	
	System.out.println("");	
	System.out.println("");
	//返回字符串的索引（下标）
	System.out.println("根据索引返回字符串该索引的内容："+strA.charAt(3));
	System.out.println("根据字符串返回它的索引值："+strA.indexOf("s"));
	
	
	System.out.println("");	
	System.out.println("");
	//字符串截取 
	System.out.println("由索引值开始截取到结尾："+strA.substring(2));
	System.out.println("由索引值开始到索引值结束 左闭右开"+strA.substring(2, 4));
	
	//字符串串分割 以特定字符作为依据分割字符串 以字符数组接收
	String strD =  "绿叶阴浓，遍池亭水阁，偏趁凉多";
	String[] strE = new  String[3]; 
	
	strE= strD.split("，");
	
	for(String str:strE) {
		System.out.println(str);
	}
	}
}


```



![image-20220726173829383](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062358891.png)



![image-20220726173858402](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062256210.png)



.

### 3.StringBuffer

```java
 public final class StringBuffer
    extends AbstractStringBuilder
    implements Serializable, CharSequence
{
```

当对字符串进行修改的时候，需要使用 StringBuffer 和 StringBuilder 类。

和 String 类不同的是，StringBuffer 和 StringBuilder 类的对象能够被多次的修改，并且不产生新的未使用对象。



![image-20220726195309000](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062256593.png)





在使用 StringBuffer 类时，每次都会对 StringBuffer 对象本身进行操作，而不是生成新的对象，所以如果需要对字符串进行修改推荐使用 StringBuffer。

StringBuilder 类在 Java 5 中被提出，它和 StringBuffer 之间的最大不同在于 StringBuilder 的方法不是线程安全的（不能同步访问）。

由于 StringBuilder 相较于 StringBuffer 有速度优势，所以多数情况下建议使用 StringBuilder 类。

```java
public class RunoobTest{
    public static void main(String args[]){
        StringBuilder sb = new StringBuilder(10);
        sb.append("Runoob..");
        System.out.println(sb);  
        
        sb.append("!");
        System.out.println(sb); 
        
        sb.insert(8, "Java");
        System.out.println(sb); 
        
        sb.delete(5,8);
        System.out.println(sb);  
        
        sb.replace(5,7,"取代");
        System.out.println(sb);
        
        //查找指定字符串在字符序列第一次出现的位置，找不到返回-1
        //lastindexOf——》查找最后一次出现的位置
        int indexOf = sb.indexOf("取代");
        System.out.println(indexOf);

        //在索引为4的地方插入kpk，原来数据自动后移
        sb.insert(4,"kpk");
        System.out.println(sb);
    }
}

//以上实例编译运行结果如下：
Runoob..
Runoob..!
Runoob..Java!
RunooJava!
Runoo取代va!
5
Runokpko取代va!
```

![image-20220726195427409](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062256350.png)



然而在应用程序要求线程安全的情况下，则必须使用 StringBuffer 类。

| 序号 | 方法描述                                                     |
| :--- | :----------------------------------------------------------- |
| 1    | append（String s） 将指定的字符串<span style="color:red">追加到此字符序列</span> |
| 2    | reverse（）将此字符序列用其<span style="color:red">反转</span>形式取代 |
| 3    | delete （int start, int end） <span style="color:red">移除</span>此序列的子字符串中的字符 |
| 4    | insert （int offset, int i） 将 `int` 参数的字符串表示形式插入此序列中 |
| 5    | insert （int offset, String str）将 `str` 参数的字符串<span style="color:red">插入</span>此序列中 |
| 6    | replace （int start, int end, String str）使用给定 `String` 中的字符<span style="color:red">替换</span>此序列的子字符串中的字符 |
| 7    | int capacity（）  返回当前<span style="color:red">容量</span> |
| 8    | nt indexOf（String str, int fromIndex）<br/>从指定的索引处开始，返回<span style="color:red">第一次出现</span>的指定子字符串在该字符串中的索引。 |
| 9    | int lastIndexOf（String str）<br/>返回<span style="color:red">最后一次出现</span>的指定子字符串在此字符串中的索引。 |



StringBuffer与String互转

```java
//String ———》StringBuffer
String str = "hello world";
//方式1 使用构造器
//返回的才是StringBuffer对象，对str本身没有影响
StringBuffer stringBuffer = new StringBuffer(str);
//方式2 使用append（）方法
StringBuffer stringBuffer1 = new StringBuffer();
StringBuffer strBuffer1 = stringBuffer1.append(str);

//StringBuffer ————》String
StringBuffer stringBuffer2 = new StringBuffer("helloWorld");
//方式1 使用toString方法
String str2 = stringBuffer2.toString();
//方式2 使用构造器
String str3 = new String(stringBuffer2);

```

案例：

```java
package com.momo.stringbuffer_;
/*
    输入商品名称和商品价格，要求打印效果示例
    手机 1,165,341,523,564.23
 */
import java.util.Scanner;

/**
 * @author momo~
 * @version 1.0
 */
public class Test02 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("请输入商品名称：");
        String prdName = scanner.next();

        System.out.println("请输入商品价格：");
        String price = scanner.next();
        StringBuffer stringBuffer = new StringBuffer(price);

//        int indexOf = price.lastIndexOf('.');
//        stringBuffer.insert(indexOf - 3,',');
        
        for (int i = stringBuffer.lastIndexOf(".") - 3; i > 0 ; i -= 3) {
            stringBuffer = stringBuffer.insert(i,',');
        }

        System.out.println(prdName + "\t" + stringBuffer);
    }
}

```



### 4.StringBuilder

![image-20220726213959297](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062256480.png)



**StringBuilder和StringBuffer均代表<span style="color:red">可变的字符序列</span>，方法是一样的，所以使用和StringBuffer一样。**



**String、StringBuffer、StringBuilder**

![image-20220726215207058](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062256045.png)



![image-20220726215245275](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062256986.png)



### 5.Math类

Java 的 Math 包含了用于执行基本数学运算的属性和方法，如初等指数、对数、平方根和三角函数。

Math 的方法都被定义为 static 形式，通过 Math 类可以在主函数中直接调用。

```java
public class Test {  
    public static void main (String []args)  
    {  
        System.out.println("90 度的正弦值：" + Math.sin(Math.PI/2));  
        System.out.println("0度的余弦值：" + Math.cos(0));  
        System.out.println("60度的正切值：" + Math.tan(Math.PI/3));  
        System.out.println("1的反正切值： " + Math.atan(1));  
        System.out.println("π/2的角度值：" + Math.toDegrees(Math.PI/2));  
        System.out.println(Math.PI);  
    }  
}
```

以上实例编译运行结果如下：

```java
90 度的正弦值：1.0
0度的余弦值：1.0
60度的正切值：1.7320508075688767
1的反正切值： 0.7853981633974483
π/2的角度值：90.0
3.141592653589793
```





Number & Math类方法

| 序号 | 方法与描述                                                   |
| :--- | :----------------------------------------------------------- |
| 1    | [xxxValue()](https://www.runoob.com/java/number-xxxvalue.html) 将 Number 对象转换为xxx数据类型的值并返回。 |
| 2    | [compareTo()](https://www.runoob.com/java/number-compareto.html) 将number对象与参数比较。 |
| 3    | [equals()](https://www.runoob.com/java/number-equals.html) 判断number对象是否与参数相等。 |
| 4    | [valueOf()](https://www.runoob.com/java/number-valueof.html) 返回一个 Number 对象指定的内置数据类型 |
| 5    | [toString()](https://www.runoob.com/java/number-tostring.html) 以字符串形式返回值。 |
| 6    | [parseInt()](https://www.runoob.com/java/number-parseInt.html) 将字符串解析为int类型。 |
| 7    | [abs()](https://www.runoob.com/java/number-abs.html) 返回参数的绝对值。 |
| 8    | [ceil()](https://www.runoob.com/java/number-ceil.html) 返回大于等于( >= )给定参数的的最小整数，类型为双精度浮点型。 |
| 9    | [floor()](https://www.runoob.com/java/number-floor.html) 返回小于等于（<=）给定参数的最大整数 。 |
| 10   | [rint()](https://www.runoob.com/java/number-rint.html) 返回与参数最接近的整数。返回类型为double。 |
| 11   | [round()](https://www.runoob.com/java/number-round.html) 它表示**四舍五入**，算法为 **Math.floor(x+0.5)**，即将原来的数字加上 0.5 后再向下取整，所以，Math.round(11.5) 的结果为12，Math.round(-11.5) 的结果为-11。 |
| 12   | [min()](https://www.runoob.com/java/number-min.html) 返回两个参数中的最小值。 |
| 13   | [max()](https://www.runoob.com/java/number-max.html) 返回两个参数中的最大值。 |
| 14   | [exp()](https://www.runoob.com/java/number-exp.html) 返回自然数底数e的参数次方。 |
| 15   | [log()](https://www.runoob.com/java/number-log.html) 返回参数的自然数底数的对数值。 |
| 16   | [pow()](https://www.runoob.com/java/number-pow.html) 返回第一个参数的第二个参数次方。 |
| 17   | [sqrt()](https://www.runoob.com/java/number-sqrt.html) 求参数的算术平方根。 |
| 18   | [sin()](https://www.runoob.com/java/number-sin.html) 求指定double类型参数的正弦值。 |
| 19   | [cos()](https://www.runoob.com/java/number-cos.html) 求指定double类型参数的余弦值。 |
| 20   | [tan()](https://www.runoob.com/java/number-tan.html) 求指定double类型参数的正切值。 |
| 21   | [asin()](https://www.runoob.com/java/number-asin.html) 求指定double类型参数的反正弦值。 |
| 22   | [acos()](https://www.runoob.com/java/number-acos.html) 求指定double类型参数的反余弦值。 |
| 23   | [atan()](https://www.runoob.com/java/number-atan.html) 求指定double类型参数的反正切值。 |
| 24   | [atan2()](https://www.runoob.com/java/number-atan2.html) 将笛卡尔坐标转换为极坐标，并返回极坐标的角度值。 |
| 25   | [toDegrees()](https://www.runoob.com/java/number-todegrees.html) 将参数转化为角度。 |
| 26   | [toRadians()](https://www.runoob.com/java/number-toradians.html) 将角度转换为弧度。 |
| 27   | [random()](https://www.runoob.com/java/number-random.html) 返回一个随机数。 |



例题：

<span style="color:red">求a-b之间随机整数</span>

```JAVA
int num = (int)(a + Math.random() * (b - a + 1))
```



### 6.Arrays类

java.util.Arrays类能方便地操作数组，它提供的所有方法都是静态的。具有以下功能：

-  给数组赋值：通过fill方法。
-  对数组排序：通过sort方法,按升序。
-  比较数组：通过equals方法比较数组中元素值是否相等。
-  查找数组元素：通过binarySearch方法能对排序好的数组进行二分查找法操作。

```java
import java.util.Arrays;

public class TestArrays {
    public static void output(int[] array) {
        if (array != null) {
            for (int i = 0; i < array.length; i++) {
                System.out.print(array[i] + " ");
            }
        }
        System.out.println();
    }

    public static void main(String[] args) {
        int[] array = new int[5];
        // 填充数组
        Arrays.fill(array, 5);
        System.out.println("填充数组：Arrays.fill(array, 5)：");
        TestArrays.output(array);
        // 将数组的第2和第3个元素赋值为8
        Arrays.fill(array, 2, 4, 8);
        System.out.println("将数组的第2和第3个元素赋值为8：Arrays.fill(array, 2, 4, 8)：");
        TestArrays.output(array);
        int[] array1 = { 7, 8, 3, 2, 12, 6, 3, 5, 4 };
        // 对数组的第2个到第6个进行排序进行排序
        Arrays.sort(array1, 2, 7);
        System.out.println("对数组的第2个到第6个元素进行排序进行排序：Arrays.sort(array,2,7)：");
        TestArrays.output(array1);
        // 对整个数组进行排序
        Arrays.sort(array1);
        System.out.println("对整个数组进行排序：Arrays.sort(array1)：");
        TestArrays.output(array1);
        // 比较数组元素是否相等
        System.out.println("比较数组元素是否相等:Arrays.equals(array, array1):" + "\n" + Arrays.equals(array, array1));
        int[] array2 = array1.clone();
        System.out.println("克隆后数组元素是否相等:Arrays.equals(array1, array2):" + "\n" + Arrays.equals(array1, array2));
        // 使用二分搜索算法查找指定元素所在的下标（必须是排序好的，否则结果不正确）
        Arrays.sort(array1);
        System.out.println("元素3在array1中的位置：Arrays.binarySearch(array1, 3)：" + "\n" + Arrays.binarySearch(array1, 3));
        // 如果不存在就返回负数
        System.out.println("元素9在array1中的位置：Arrays.binarySearch(array1, 9)：" + "\n" + Arrays.binarySearch(array1, 9));
    }
}
```

输出结果：

```java
填充数组：Arrays.fill(array, 5)：
5 5 5 5 5 
将数组的第2和第3个元素赋值为8：Arrays.fill(array, 2, 4, 8)：
5 5 8 8 5 
对数组的第2个到第6个元素进行排序进行排序：Arrays.sort(array,2,7)：
7 8 2 3 3 6 12 5 4 
对整个数组进行排序：Arrays.sort(array1)：
2 3 3 4 5 6 7 8 12 
比较数组元素是否相等:Arrays.equals(array, array1):
false
克隆后数组元素是否相等:Arrays.equals(array1, array2):
true
元素3在array1中的位置：Arrays.binarySearch(array1, 3)：
1
元素9在array1中的位置：Arrays.binarySearch(array1, 9)：
-9
```



**Arrays排序实现**

1）可以直接使用冒泡排序，也可以直接使用Arrays提供的sort方法排序

2）因为数组是引用类型，所以通过sort排序后，会直接影响到实参

3）sort方法是可以重载的，也可以通过传入一个Comparator接口实现定制排序

4）调用定制排序时，传入两个参数：（1）需要排序的数组（2）实现了Comparator接口的匿名内部类，实现compare方法，体现了接口编程方式

5）最终到TimSort类的binarySort方法，根据动态绑定机制执行传入的comapre方法

6）compare方法返回的值直接影响排序结果

```java
package com.momo.arrays_;

import java.util.Arrays;
import java.util.Comparator;

/**
 * @author momo~
 * @version 1.0
 */
public class Arrays01 {
    public static void main(String[] args) {
        Integer integer[] = {1,-5,63,23,7};

        //方式1 使用冒泡排序
        for (int i = 0; i < integer.length - 1; i++) {
            for (int j = 0; j < integer.length - 1 - i; j++) {
                if (integer[j] > integer[j + 1]){
                    int temp = integer[j];
                    integer[j] = integer[j + 1];
                    integer[j + 1] = temp;
                }
            }
        }
        
        //方式2 使用Arrays提供的sort方法排序
        Arrays.sort(integer);
        
        //方式3 使用Arrays提供的sort方法定制排序
        //通过传入一个Comparator接口实现定制排序
        //调用定制排序时，传入两个参数：（1）需要排序的数组（2）实现了Comparator接口的匿名内部类
        // 实现compare方法
        Arrays.sort(integer, new Comparator<Integer>() {
            @Override
            public int compare(Integer o1, Integer o2) {
                return o2 - o1;
            }
        });
        System.out.println(Arrays.toString(integer));
    }
}
```

![image-20220727123031632](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062256468.png)



Arrays模拟排序

```JAVA
package com.momo.arrays_;

import java.util.Arrays;
import java.util.Comparator;

/**
 * @author momo~
 * @version 1.0
 */
public class Arrays02 {
    public static void main(String[] args) {
        Integer integer[] = {1,-5,63,23,7};
//        bubble(integer);
        bubble(integer, new Comparator() {
            @Override
            public int compare(Object o1, Object o2) {
                int i1 = (Integer) o1;
                int i2 = (Integer) o2;
                return i2 - i1;
            }
        });

        System.out.println(Arrays.toString(integer));
    }

//    public static void bubble(Integer integer[]){
//        for (int i = 0; i < integer.length - 1; i++) {
//            for (int j = 0; j < integer.length - 1 - i; j++) {
//                if (integer[j] > integer[j + 1]){
//                    int temp = integer[j];
//                    integer[j] = integer[j + 1];
//                    integer[j + 1] = temp;
//                }
//            }
//        }


//    }

    //冒泡+定制
    public static void bubble(Integer integer[], Comparator c){
        for (int i = 0; i < integer.length - 1; i++) {
            for (int j = 0; j < integer.length - 1 - i; j++) {
                if (c.compare(integer[j] ,integer[j + 1]) > 0){
                    int temp = integer[j];
                    integer[j] = integer[j + 1];
                    integer[j + 1] = temp;
                }
            }
        }
    }
}
```



Arrays其他方法

```java
package com.momo.arrays_;

import java.util.Arrays;
import java.util.List;

/**
 * @author momo~
 * @version 1.0
 */
public class Arrays03 {
    public static void main(String[] args) {
        Integer integer[] = {1,-6,54,554,78};
        //copyOf数组元素的拷贝
        //从integer数组中，拷贝integer.length个元素到integer1数组中
        //如果拷贝长度 > integer.length,则在新数组的后面增加null
        //如果拷贝长度 < 0,则抛出异常NegativeArraySizeException
        //底层使用System.arraycopy()
        Integer integer1[] = Arrays.copyOf(integer,3);
        System.out.println(Arrays.toString(integer1));

        //asList 将数组转换成List
        //asList方法，会将数组数据转换成List集合
        //返回的asList编译类型List（接口）
        //asList运行类型 class java.util.Arrays$ArrayList
        //即是Arrays类的static静态内部类
        List asList = Arrays.asList(1,5,6,46,46,52);
        System.out.println(asList);
        System.out.println(asList.getClass());

    }
}

```

```java
package com.momo.arrays_;
/*
    自定义Book类，里面包含name、price，按price排序。要求使用两种排序方式，有一个
    Book[] books = 4 本书对象
    使用前面学习过的传递 实现Comparator接口匿名内部类，也称为定制排序。
    1）从大到小 2）从小到大 3）按照书名长度从大到小

 */

import java.util.Arrays;
import java.util.Comparator;

/**
 * @author momo~
 * @version 1.0
 */
public class ArraysExercise01 {
    public static void main(String[] args) {
        Book books[] = new Book[4];
        books[0] = new Book("红楼梦", 100);
        books[1] = new Book("新金瓶梅", 90);
        books[2] = new Book("青年文摘2022", 5);
        books[3] = new Book("Java从入门到入土", 300);


        //方式1 冒泡排序
        Book temp = null;
//        for (int i = 0; i < books.length - 1; i++) {
//            for (int j = 0; j < books.length - 1 - i; j++) {
//                if (books[j].getPrice() < books[j + 1].getPrice()) {
//                    temp = books[j];
//                    books[j] = books[j + 1];
//                    books[j + 1] = temp;
//                }
//            }
//        }

        for (int i = 0; i < books.length - 1; i++) {
            for (int j = 0; j < books.length - 1 - i; j++) {
                if (books[j].getName().length() > books[j + 1].getName().length()) {
                    temp = books[j];
                    books[j] = books[j + 1];
                    books[j + 1] = temp;
                }
            }
        }

        //方式2 sort定制排序
//        Arrays.sort(books, new Comparator<Book>() {
//            @Override
//            public int compare(Book o1, Book o2) {
//                double d =   o1.getPrice() -  o2.getPrice();
//                if (d > 0){
//                    return 1;
//                } else if (d < 0) {
//                    return -1;
//                } else {
//                    return 0;
//                }
//            }
//        });

//        Arrays.sort(books, new Comparator<Book>() {
//            @Override
//            public int compare(Book o1, Book o2) {
//                return  o1.getName().length() -  o2.getName().length();
//            }
//        });

        for (int i = 0; i < books.length; i++) {
            System.out.println(books[i].toString());
        }
    }
}

class Book {

}
```



### 7.System类

System系统类，主要用于获取系统的属性数据和其他操作，因其构造方法是私有的并且类中的成员方法都是静态的，所以在使用的时候不需要创建对象，可直接调用。

**arraycopy(…)**

概述
arraycopy(…)方法将指定原数组中的数据从指定位置复制到目标数组的指定位置。

语法
```java
static void arraycopy(Object src,  int srcPos, Object dest, int destPos, int length)
```

src – 原数组。

srcPos – 在原数组中开始复制的位置。

dest – 目标数组。

destPos – 在目标数组中开始粘贴的位置。

length – 复制的长度。

```java
package com.ibelifly.commonclass.system;

public class Test1 {
    public static void main(String[] args) {
        int[] arr={23,45,20,67,57,34,98,95};
        int[] dest=new int[8];
        System.arraycopy(arr,4,dest,4,4);
        for (int x:dest) {
            System.out.print(x+" ");
        }
    }
}
```



**currentTimeMillis()**

currentTimeMillis()方法返回当前时间（以毫秒为单位）。

语法：

```java
static long currentTimeMillis()
```

```java
package com.ibelifly.commonclass.system;

public class Test2 {
    public static void main(String[] args) {
        System.out.println(System.currentTimeMillis()); //打印现在的时间
        long start=System.currentTimeMillis(); //该方法可用来计时
        for (int i = -99999999; i < 99999999; i++) {
            for (int j = -99999999; j < 99999999; j++) {
                int result=i+j;
            }
        }
        long end=System.currentTimeMillis();
        System.out.println("用时："+(end-start));
    }
}

```



**gc()**

gc()方法用来运行垃圾回收器。（至于是否回收垃圾，有可能执行，有可能不执行，是否执行取决于JVM）

语法：

```java
static void gc();
```

举例：

```java
package com.ibelifly.commonclass.system;

public class Student {
    private String name;
    private int age;

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    @Override
    protected void finalize() throws Throwable {
        System.out.println("回收了"+name+" "+age);
    }
}
```

```java
package com.ibelifly.commonclass.system;

public class Test3 {
    public static void main(String[] args) {
        new Student("小明",20);
        new Student("小红",28);
        new Student("小刚",22);
        System.gc();
    }
}
```

**exit(int status)**

exit(int status)方法用于终止当前运行的Java虚拟机。如果参数是0，表示正常退出JVM；如果参数非0，表示异常退出JVM。

语法：

```java
static void exit(int status);
```

举例：

```java
package com.ibelifly.commonclass.system;

public class Test4 {
    public static void main(String[] args) {
        System.out.println("程序开始了");
        System.exit(0); //因为此处已经终止当前运行的Java虚拟机，故不会执行之后的代码
        System.out.println("程序结束了");
    }
}
```





### 8.大数处理方案

如果基本的整数和[浮点](https://so.csdn.net/so/search?q=浮点&spm=1001.2101.3001.7020)数精度不能够满足需求，那么可以使用java.math包中两个很有用的类：BigInteger和BigDecimal。这两个类可以处理包含任意长度数字序列的数值。BigInteger类实现任意精度的整数运算，BigDecimal实现任意精度的浮点数运算。

使用静态的valueOf方法可以将普通的数值转换为大数：

```java
BigInteger a = BigInteger.valueOf(100);
```

对于更大的数，可以使用一个带[字符串](https://so.csdn.net/so/search?q=字符串&spm=1001.2101.3001.7020)参数的构造器：

```java
BigInteger reallyBig = new BigInteger("999999999999999999999999999999999999999999");
```

另外还有一些常量：[BigInteger](https://so.csdn.net/so/search?q=BigInteger&spm=1001.2101.3001.7020).ZERO、BigInteger.ONE和BigInteger.TEN，Java 9之后还增加了BigInteger.TWO。

遗憾的是，不能使用人们熟悉的算术运算符处理大数，而需要使用大数类中的add和multiply方法。

```java
BigInteger c = a.add(b); // c = a + b
BigInteger d = c.multiply(b.add(BigInteger.valueOf(2))); // d = c * (b + 2)
```

**API**

java.math.BigInteger

```JAVA
BigInteger add(BigInteger other) //加
BigInteger subtract(BigInteger other) //减
BigInteger multiply(BigInteger other) //乘
BigInteger divide(BigInteger other) //除
BigInteger mod(BigInteger other) //求余
int compareTo(BigInteger other) //比较
static BigInteger valueOf(long x) //返回值等于x的大整数
```

java.math.BigDecimal

```JAVA
BigDecimal add(BigDecimal other) //加
BigDecimal subtract(BigDecimal other) //减
BigDecimal multiply(BigDecimal other) //乘
BigDecimal divide(BigDecimal other) //除
BigDecimal divide(BigDecimal other, RoundingMode mode) //除
int compareTo(BigDecimal other) //比较
static BigDecimal valueOf(long x) //返回值等于x的大实数
static BigDecimal valueOf(long x, int scale) 
```



### **9.Date类**

![image-20220727162328564](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062257728.png)

![image-20220727172716380](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062257427.png)

#### **一、Date类（第一代日期类）**

```java
package com.momo.date_;


import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

/**
 * @author momo~
 * @version 1.0
 */
public class Date01 {
    public static void main(String[] args) throws ParseException {
        //默认输出格式为国外的格式，因此通常需要对格式进行转换
        Date date = new Date();//获取当前系统时间
        System.out.println("当前时间为：" + date);
        Date date1 = new Date(949846464);//通过指定毫秒数得到时间

        SimpleDateFormat sim = new SimpleDateFormat("yyyyMMdd HH:mm:ss E");
        System.out.println("当前时间为：" + sim.format(date));;
//        System.out.println(sim.format(date1));

        //字符串转成时间
        //注意跟上面格式SimpleDateFormat保持一致，否则会抛出转换异常
        String str = "19990101 14:20:30 星期三";
        Date parse = sim.parse(str);
        System.out.println(sim.format(parse));
    }
}
```



#### **二、Calendar类（第二代日期类）**![image-20220727173434235](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062257032.png)

1、Calendar类简介
Calendar类的功能要比Date类强大很多，可以方便的进行日期的计算,获取日期中的信息时考虑了时区等问题。而且在实现方式上也比Date类要复杂一些。

Calendar类是一个抽象类，由于Calendar类是抽象类，且Calendar类的构造方法是protected的，所以无法使用Calendar类的构造方法来创建对象，API中提供了getInstance方法用来创建对象。
2、创建一个代表系统当前日期的Calendar对象

```java
Calendar calendar = Calendar.getInstance();//默认是当前日期
```

3、创建一个指定日期的Calendar对象

```java
public static void main(String[] args) {
    Calendar calendar = Calendar.getInstance();
    calendar.set(2021, 5, 9);
    System.out.println(calendar.getTime());//Wed Jun 09 18:36:09 CST 2021
}
```

实例

```java
package com.momo.date_;

import java.util.Calendar;

/**
 * @author momo~
 * @version 1.0
 */
public class Calendar01 {
    public static void main(String[] args) {
        //Cal是一个抽象类，并且构造器是private
        //可以通过getInstance来获取实例
        //提供了大量的方法和字段提供给程序员
        //没有提供对应的格式化类，需要程序员自己组合输出
        //如果需要按照24小时进制获取时间，
        Calendar instance = Calendar.getInstance();//创建日历类对象
        System.out.println(instance);
        //获取日历对象的某个日历字段Calendar.HOUR ——>Calendar.HOUR.OF.DAY
        System.out.println("年：" + instance.get(Calendar.YEAR));
        //月份需要+1.原因与数组下标一样，是由0开始
        System.out.println("月：" + (instance.get(Calendar.MONTH) + 1));
        System.out.println("日：" + instance.get(Calendar.DAY_OF_MONTH));
        System.out.println("时：" + instance.get(Calendar.HOUR));
        System.out.println("分：" + instance.get(Calendar.MINUTE));
        System.out.println("秒：" + instance.get(Calendar.SECOND));
        //Calendar没有专门的格式化方法，所以需要程序员自己组合显示
        System.out.println("年：" + instance.get(Calendar.YEAR) +
                "\t月：" + (instance.get(Calendar.MONTH) + 1) +
                "\t日：" + instance.get(Calendar.DAY_OF_MONTH) +
                "\t时：" + instance.get(Calendar.HOUR) +
                "\t分："+instance.get(Calendar.MINUTE) +
                "\t秒：" + instance.get(Calendar.SECOND));

    }
}
```



**4、set设置**

（1）set设置

```java
public final void set(int year,int month,int date)
```

（2）利用字段类型设置

```java
public static void main(String[] args) {
    Calendar calendar = Calendar.getInstance();
    calendar.set(Calendar.YEAR,2021);
    calendar.set(Calendar.MONTH,11);
    calendar.set(Calendar.DAY_OF_MONTH,6);
    System.out.println(calendar.getTime());//Mon Dec 06 18:39:22 CST 2021
}
```

Calendar类中用一下这些常量表示不同的意义，jdk内的很多类其实都是采用的这种思想

Calendar.YEAR——年份

Calendar.MONTH——月份

Calendar.DATE——日期

Calendar.DAY_OF_MONTH——日期，和上面的字段意义相同

Calendar.HOUR——12小时制的小时

Calendar.HOUR_OF_DAY——24小时制的小时

Calendar.MINUTE——分钟

Calendar.SECOND——秒

Calendar.DAY_OF_WEEK——星期几

**5、add**

```java
public static void main(String[] args) {
    Calendar calendar = Calendar.getInstance();
    calendar.set(Calendar.YEAR,2021);
    calendar.set(Calendar.MONTH,11);
    calendar.set(Calendar.DAY_OF_MONTH,6);
    calendar.add(Calendar.DAY_OF_MONTH,2);
    System.out.println(calendar.getTime());//Wed Dec 08 18:42:25 CST 2021
}
```

**6、使用get获取时间**

```java
public static void main(String[] args) {
    Calendar calendar = Calendar.getInstance();
    calendar.set(Calendar.YEAR,2021);
    calendar.set(Calendar.MONTH,11);
    calendar.set(Calendar.DAY_OF_MONTH,6);
    calendar.add(Calendar.DAY_OF_MONTH,2);
    System.out.println(calendar.get(Calendar.YEAR));//2021
    System.out.println(calendar.get(Calendar.MONTH));//11
    System.out.println(calendar.get(Calendar.DAY_OF_MONTH));//8
}
```

**三、日期互转**

1、Date与long

```java
public static void main(String[] args) {
    Date date = new Date();
    long time = date.getTime();
}
```

2、Calendar与long

```java
public static void main(String[] args) {
    Calendar calendar = Calendar.getInstance();
    calendar.set(Calendar.YEAR,2021);
    calendar.set(Calendar.MONTH,11);
    calendar.set(Calendar.DAY_OF_MONTH,6);
    calendar.add(Calendar.DAY_OF_MONTH,2);
    long timeInMillis = calendar.getTimeInMillis();
}
```

3、Date与Calendar互转

（1）Date转Calendar

```java
public static void main(String[] args) {
    Date date = new Date();
    Calendar calendar = Calendar.getInstance();
    calendar.setTime(date);
}
```

（1）Calendar转Date

```java
public static void main(String[] args) {
    Calendar calendar = Calendar.getInstance();
    calendar.set(Calendar.YEAR,2021);
    calendar.set(Calendar.MONTH,11);
    calendar.set(Calendar.DAY_OF_MONTH,6);
    calendar.add(Calendar.DAY_OF_MONTH,2);
    Date time = calendar.getTime();
}
```

4、String与Date互转

（1）Date转String

```java
public static void main(String[] args) {
    SimpleDateFormat sdf= new SimpleDateFormat("yyyy-MM-dd");
    String dateStr=sdf.format(new Date());
}
```

（2）String转Date

```java
public static void main(String[] args) throws ParseException {
    String str="20211106";
    SimpleDateFormat sdf= new SimpleDateFormat("yyyy-MM-dd");
    Date date = sdf.parse(str);
    System.out.println(date);
}
```

![image-20220727163655348](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062257775.png)



5、String与Calendar互转

（1）Calendar 转化 String

```java
public static void main(String[] args) throws ParseException {
    Calendar calendar = Calendar.getInstance();
    SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd");
    String str = sdf.format(calendar.getTime());
}
```

（2）String 转化Calendar

```java
public static void main(String[] args) throws ParseException {
    String str="2021-11-6";
    SimpleDateFormat sdf= new SimpleDateFormat("yyyy-MM-dd");
    Date date =sdf.parse(str);
    Calendar calendar = Calendar.getInstance();
    calendar.setTime(date);
    System.out.println(calendar.getTime());//Sat Nov 06 00:00:00 CST 2021
}
```



#### 三、第三代日期类

![image-20220727180639838](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062258394.png)



第三代日期常用方法

JDK8加入

**LocalDate（年月日）**

```java
LocalDate now1 = LocalDate.now();//获取年月日
```

**LocalTime（时分秒）**

```java
LocalTime now2 = LocalTime.now();//获取时分秒
```

**LocalDateTim（年月日时分秒）**

```java
LocalDateTime now = LocalDateTime.now();
```

**DateTimeFormatter格式日期类**，类似于SimpleDateFormat，语法：

```java
DateTimeFormatter dt = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss");
String format = dt.format(now);
```

**Instant 时间戳**

```java
Instant now3 = Instant.now();
```

**plusDays**  增加天数

```java
//查看856天后，是什么时候，年月日时分秒
LocalDateTime plus = now.plusDays(856);
```

**minusMinutes**  减少分钟

```java
//查看1025分钟前，是什么时候，年月日时分秒
LocalDateTime min = now.minusMinutes(1025);
```

更多第三代日期类方法请查看JDK8以后文档

```java
package com.momo.date_;

import java.time.Instant;
import java.time.LocalDate;
import java.time.LocalDateTime;
import java.time.LocalTime;
import java.time.format.DateTimeFormatter;
import java.util.Date;

/**
 * @author momo~
 * @version 1.0
 */
public class Three {
    public static void main(String[] args) {
        //第三代日期
        //1)使用now（）返回当前日期时间的对象
        LocalDateTime now = LocalDateTime.now();
        System.out.println(now);

        //使用DateTimeFormatter格式化日期
        DateTimeFormatter dt = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss");
        String format = dt.format(now);
        System.out.println("格式化后：" + format);//输出格式化后时间日期


        System.out.println("年：" + now.getYear());
        System.out.println("(英文)月：" + now.getMonth());//英文三月
        System.out.println("(数字)月：" + now.getMonthValue());//英文三月
        System.out.println("日：" + now.getDayOfMonth());
        System.out.println("时：" + now.getHour());
        System.out.println("分：" + now.getMinute());
        System.out.println("秒：" + now.getSecond());

        LocalDate now1 = LocalDate.now();//获取年月日
        LocalTime now2 = LocalTime.now();//获取时分秒

        //通过静态方法new()获取表示当前时间戳的对象
        Instant now3 = Instant.now();
        System.out.println(now3);
        //通过from可以把Instant转成Date
        Date date = Date.from(now3);
        Instant instant = date.toInstant();

        //提供了大量的plus方法可以对当前时间进行加或者减
        //查看856天后，是什么时候，年月日时分秒
        LocalDateTime plus = now.plusDays(856);
        System.out.println("856天后:" + dt.format(plus));
        //查看1025分钟前，是什么时候，年月日时分秒
        LocalDateTime min = now.minusMinutes(1025);
        System.out.println("1025分钟前" + dt.format(min));
    }
}
```



### 10.数组翻转

```java
package com.momo.stringclass;

/**
 * @author momo~
 * @version 1.0
 */
public class StringExercise01 {
    public static void main(String[] args) {

        String str = "abcdef";

        try {
            str = Reverse_.reverse(str, 1, 4);
        } catch (Exception e) {
            System.out.println(e.getMessage());
            return;
        }
        System.out.println(str);

    }
}
class Reverse_{

    //将字符串中指定部分进行反转。
    //编写方法public static String reverse(String str,int start,int end)搞定
    public static String reverse(String str,int start,int end){

        //自己思路：
//        StringBuffer stringBuffer = new StringBuffer(str);
//        StringBuffer str2 = stringBuffer.replace(start, end, "edcb");
//        String str3 = str2.toString();
//        return str3;

        //老师答案：

        if (!(str != null && start >= 0 && end > start && end < str.length())){
            throw new RuntimeException("参数不正确");
        }
        char[] chars = str.toCharArray();

        for (int i = start,j = end; i < j; i++, j --) {
            char temp = chars[i];
            chars[i] = chars[j];
            chars[j] = temp;
        }

        String strNew = chars.toString();//错误写法
//        return strNew;
        return new String(chars);
    }
}
```



### 11.注册处理题

```JAVA
package com.momo.stringclass;
/*
    输入用户名、密码、邮箱，如果信息录入正确，则提示注册成功，否则生成异常对象
    要求：1）用户名长度为2或3或4
         2）密码长度为6，要求全是数字 isDigital
         3）邮箱中包含@和.并且@在.的前面
 */

import java.util.Scanner;

/**
 * @author momo~
 * @version 1.0
 */
public class Homework02 {
    public static void main(String[] args) {

        String name = "123";
        String pwd = "123456";
        String Email = "E@12312.3";

        try {
            Register.register(name, pwd, Email);
        } catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}

class Register {
//    private String name;
//    private String pwd;
//    private String Email;

    public static void register(String name, String pwd, String Email) {

        //1）用户名长度为2或3或4
        int nameLen = name.length();
        int pwdLen = pwd.length();
        if (!(nameLen >= 2 && nameLen <= 4)) {
            throw new RuntimeException("用户名长度为2或3或4");
        }

        //2）密码长度为6，要求全是数字 isDigital
        if (!(pwdLen == 6 && isDigital(pwd))) {
            throw new RuntimeException("密码长度不为6");
        }

        //3）邮箱中包含@和.并且@在.的前面
        int i = Email.indexOf("@");
        int j = Email.indexOf(".");
        if (!(i > 0 && j > i)) {
            throw new RuntimeException("邮箱格式需要包含@与.且@需要在.的前面");
        }

        System.out.println("注册成功");

    }

    //判断字符串是否全是数字，返回布尔值
    public static boolean isDigital(String str) {
        char[] chars = str.toCharArray();
        for (int i = 0; i < chars.length; i++) {
            if (chars[i] > '9' && chars[i] < '0') {
                return false;
            }
        }
        return true;
    }
}
```



### 12.字符串案例

```java
package com.momo.stringclass;
/*
    1）编写Java程序，输出形式为：Han Shun Ping的人名，以Ping,Han.S的形式打印出来。
       其中.S是中间单词的首字母
    2）例如输出"Willian Jefferson Clinton",输出形式为：Clinton,Willian.J
 */
/**
 * @author momo~
 * @version 1.0
 */
public class Homework03 {
    public static void main(String[] args) {
        String name = "Willian Jefferson Clinton";
        printName(name);
    }
    public static void printName(String str){
        if (str == null){
            System.out.println("字符串不能为空");
            return;
        }
        String[] strNew = str.split(" ");
        if (strNew.length != 3){
            System.out.println("格式不正确");
        }
        String format = String.format("%s,%s.%c",strNew[2],strNew[0],strNew[1].toUpperCase().charAt(0));
        System.out.println(format);
    }
}

```

```JAVA
package com.momo.stringclass;
/*
    1)输入字符串，判断里面有多少个大写字母，多少个小写字母，多少个数字
 */
/**
 * @author momo~
 * @version 1.0
 */
public class Homework {
    public static void main(String[] args) {
        String str = "12356sfdAD4D..";
        judge(str);
    }
    public static void judge(String str){
        if (str == null){
            System.out.println("字符串为空");
            return;
        }
        int numCount = 0;
        int lowerCount = 0;
        int upperCount = 0;
        int otherCount = 0;
        for (int i = 0; i < str.length(); i++) {
            if (str.charAt(i) >= '0' && str.charAt(i) <= '9'){
                numCount++;
            } else if (str.charAt(i) >= 'a' && str.charAt(i) <= 'z') {
                lowerCount++;
            } else if (str.charAt(i) >= 'A' && str.charAt(i) <= 'Z') {
                upperCount++;
            } else {
                otherCount++;
            }
        }
        System.out.println("数字有" + numCount + "个");
        System.out.println("大写字母有" + upperCount + "个");
        System.out.println("小写字母有" + lowerCount + "个");
        System.out.println("其他有" + otherCount + "个");
    }
}


```



## 8.集合

![image-20220728095945368](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062258178.png)

![image-20220728100146189](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062258405.png)



### 1.集合体系图

**collection—单列集合**（单个对象）

![image-20220729125839505](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062258693.png)



**map—双列集合**（键值对）

![image-20220728101200554](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062258434.png)



<span style="color:red">**集合选型**</span>

![image-20220730142730119](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062258572.png)





### 2.Collection

**collection接口和常用方法**

![image-20220728102041618](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062258930.png)





![image-20220728102211297](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062258922.png)



```java
package com.momo.collection_;

import java.util.ArrayList;

/**
 * @author momo~
 * @version 1.0
 */
public class Collection01 {
    public static void main(String[] args) {
        ArrayList strings = new ArrayList();
        //add：添加单个元素,添加后不再是基本数据类型
        strings.add("123");
        strings.add(123);
        strings.add(true);
        System.out.println("list：" + strings);//list：[123, 123, true]
        //remove：删除指定元素
        strings.remove(0);//依下标删除
        System.out.println(strings);
        strings.remove(true);//指定删除某个元素
        System.out.println(strings);
        //contains：查找元素是否存在
        System.out.println(strings.contains(123));
        //size：获取元素个数
        System.out.println(strings.size());
        //isEmpty：判断是否为空
        System.out.println(strings.isEmpty());
        //clear：清空
//        strings.clear();
        System.out.println(strings);
        //addAll：添加多个元素
        ArrayList<Object> objects = new ArrayList<>();
        objects.add("红楼梦");
        objects.add("三国演义");
        strings.addAll(objects);
        System.out.println(strings);
        //containsAll：查找多个元素是否都存在
        System.out.println(strings.containsAll(objects));
        //removeAll：删除多个元素
        strings.removeAll(objects);
        System.out.println(strings);
    }
}
```



**3.iterator迭代器**![image-20220728115435002](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062359513.png)

![image-20220728115158654](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062258395.png)

![image-20220728120018678](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062258623.png)

![image-20220728120127508](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062258939.png)



```java
package com.momo.collection_;
/*
    演示collection接口实现的方法iterator迭代器
 */

import java.util.ArrayList;
import java.util.Collection;
import java.util.Iterator;

/**
 * @author momo~
 * @version 1.0
 */
public class Iterator_ {
    public static void main(String[] args) {
        ArrayList<Book> books = new ArrayList<>();
        books.add(new Book("三国演义","罗贯中",150));
        books.add(new Book("水浒传","施耐庵",200));
        books.add(new Book("红楼梦","曹雪芹",120));
        System.out.println(books);
        //遍历集合
        //1.得到对应集合的迭代器
        Iterator<Book> iterator = books.iterator();
        //2.使用while循环遍历
        while (iterator.hasNext()){
            Book book = iterator.next();
            System.out.println(book);
        }
        //while循环+iterator  快捷键 itit
//        while (iterator.hasNext()) {
//            Book next =  iterator.next();
//
//        }
        //当退出while循环后，iterator指向最后的元素
//        iterator.next();//NoSuchElementException
        //如果需要再次遍历，需要重置迭代器
        Iterator<Book> iterator2 = books.iterator();//再次遍历
        

    }
}
```



**4.增强for循环**

![image-20220728121836981](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062259473.png)

```JAVA
public class ForPlus {
    public static void main(String[] args) {
        ArrayList<Book2> books = new ArrayList<>();
        books.add(new Book2("三国演义","罗贯中",150));
        books.add(new Book2("水浒传","施耐庵",200));
        books.add(new Book2("红楼梦","曹雪芹",120));
//        System.out.println(books);
        //增强for循环遍历集合
        //增强for底层依然是迭代器
        for (Book2 book2 : books){
            System.out.println(book2);
        }
        //增强for循环遍历数组 快捷键 I
        int num[] = {1,5,6,3,12};
        for (int i : num){
            System.out.print(" "+i);
        }
    }
}
```

![image-20220728123030897](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062259674.png)

代码实现：

```java
package com.momo.collection_;

import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

/**
 * @author momo~
 * @version 1.0
 */
public class Exercise01 {
    public static void main(String[] args) {
        List<Dog> dogs = new ArrayList<>();
        dogs.add(new Dog("小花",12));
        dogs.add(new Dog("小白",14));
        dogs.add(new Dog("小黑",16));

        //迭代器遍历
        Iterator<Dog> iterator = dogs.iterator();
        while (iterator.hasNext()) {
            Dog next =  iterator.next();
            System.out.println(next);
        }
        System.out.println("===============");
        //增强for遍历,需要确保集合内类型一致为Dog
        for (Dog dog : dogs) {
            System.out.println(dog);
        }

    }
}
class Dog{
    private String name;
    private int age;

    public Dog(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public String toString() {
        return "Dog{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}
```



#### **1.list接口**

![image-20220728124245218](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062259668.png)

```java
public class List01 {
    public static void main(String[] args) {
        //1.List集合中元素有序且可以重复
        ArrayList arrayList = new ArrayList();
        arrayList.add("milan");
        arrayList.add("momo");
        arrayList.add("tom");
        arrayList.add("ace");
        arrayList.add("ace");
        System.out.println(arrayList);
        //2.List集合中每个元素都有其对应的顺序索引，即支持索引
        System.out.println(arrayList.get(1));
        //3.API
        
    }
}
```



![image-20220728125028945](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062259064.png)

```java
package com.momo.list_;

import java.util.ArrayList;
import java.util.List;

/**
 * @author momo~
 * @version 1.0
 */
public class ListMethod {
    public static void main(String[] args) {
        List list = new ArrayList();
        list.add("三国演义");
        list.add("红楼梦");

        //add(int index,Object ele):在index位置插入ele元素
        list.add(1,"水浒传");
        list.add("青年文摘");
//        System.out.println(list);
        //addAll(int index,Collection eles)在index位置开始插入所有元素
        List list2 = new ArrayList();
        list2.add("123");
        list2.add("456");
        list.addAll(1,list2);
        System.out.println(list);
        //Object get(int index):获取指定index位置的元素
        System.out.println(list.get(3));
        //int indexOf(Object obj):返回obj在集合中首次出现的位置
        System.out.println(list.indexOf("青年文摘"));
        //int indexOf(Object obj):返回obj在集合中末次出现的位置
        System.out.println(list.lastIndexOf("456"));
        //Object remove(int index):移除指定index位置的元素，并返回元素
        System.out.println(list.remove(2));
        System.out.println(list);
        //Object set(int index,Object ele):设置指定位置元素为ele,相当于替换
        list.set(1,"家有儿女123");
        System.out.println(list);
        //List subList(int fromIndex,int toIndex);返回从fromIndex位置到toIndex位置的子集合
        List list1 = list.subList(1, 3);//前闭后开，包前不包后
        System.out.println(list1);
    }
}
```

Exercise:

![image-20220728131439634](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062259262.png)

```java
package com.momo.list_;

import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

/**
 * @author momo~
 * @version 1.0
 */
public class Exercise01 {
    public static void main(String[] args) {
        List list = new ArrayList();

        for (int i = 0; i < 10; i++) {
            list.add("动脉" + i);
        }

        list.add(1,"hsplu");
        System.out.println("第五个元素为：" + list.get(4));;
        list.remove(5);
        list.set(6,"修改01");

        //迭代器遍历
        Iterator iterator = list.iterator();
        while (iterator.hasNext()) {
            Object next = iterator.next();
            System.out.println(next);
        }
    }
}
```



##### 6.List三种遍历方式

![image-20220728133052874](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062259057.png)

```java
package com.momo.list_;

import java.util.*;

/**
 * @author momo~
 * @version 1.0
 */
public class ListFor {
    public static void main(String[] args) {
//        List list = new ArrayList();
//        List list = new LinkedList();
        List list = new Vector();
        list.add("攒首付");
        list.add("koko");
        list.add("朱炯大");

        //迭代器遍历
        Iterator iterator = list.iterator();
        while (iterator.hasNext()) {
            Object str = iterator.next();
            System.out.println(str);
        }
        System.out.println("============");
        //增强for遍历
        for (Object o : list) {
            System.out.println(o);
        }
        System.out.println("===========");
        //普通for遍历
        for (int i = 0; i < list.size(); i++) {
            System.out.println(list.get(i));
        }
    }
}
```



7.List排序

![image-20220728134216783](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062259434.png)

```java
package com.momo.list_;

import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

/**
 * @author momo~
 * @version 1.0
 */
public class Exercise02 {
    public static void main(String[] args) {
        ArrayList<Book> books = new ArrayList<>();
        books.add(new Book("红楼梦","曹雪芹",99));
        books.add(new Book("西游记","吴承恩",15));
        books.add(new Book("水浒传","施耐庵",9));
        books.add(new Book("三国演","罗贯中",80));
        books.add(new Book("西游记","吴承恩",10));


//        System.out.println(books);
        sort(books);

        Iterator<Book> iterator = books.iterator();
        while (iterator.hasNext()) {
            Book book = iterator.next();
            System.out.print("名称：" + book.getName() + "\t\t" +
                    "价格：" + book.getPrice() + "\t\t" +
                    "作家：" + book.getAuthor() + "\n");
        }
    }
    public static void sort(ArrayList books){
        //冒泡
        Book temp = null;
        for (int i = 0; i < books.size() - 1; i++) {
            for (int j = 0; j < books.size() - 1 - i; j++) {
                Book book1 = (Book)books.get(j);
                Book book2 = (Book)books.get(j+1);
                if (book1.getPrice() > book2.getPrice()){
                    books.set(j,book2);
                    books.set(j+1,book1);
                }
            }
        }
    }
}

```



**ArrayList注意事项**

![image-20220728142400641](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062259366.png)



##### **7.ArratList底层源码**

![image-20220728143255259](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062259316.png)





![image-20220728145317462](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062259672.png)

![image-20220728145358204](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062259769.png)



![image-20220728145418113](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062259985.png)



##### 8.Vector

![image-20220728164245002](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062300407.png)



**Vector与ArrayList区别**

![image-20220728164534034](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062300796.png)



##### 9.LinkedList

![image-20220728171438224](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062300070.png)

这里不详细了解，大致即可

![image-20220728173349162](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062300120.png)



#### 2.Set接口 

![image-20220728173640802](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062300108.png)



![image-20220728173738114](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062300131.png)



```java
package com.momo.collection_.set_;

import java.util.HashSet;
import java.util.Iterator;

/**
 * @author momo~
 * @version 1.0
 */
public class Set01 {
    public static void main(String[] args) {
        //以Set接口的实现类HashSet来讲解Set接口的方法
        //set接口的实现子类的对象，不能存放重复元素，
        // 可以为null，且为无序，添加顺序与取出顺序不一致
        //取出顺序虽然无序但是固定
        HashSet hashSet = new HashSet();
        hashSet.add("123");
        hashSet.add("米兰");
        hashSet.add("milan");
        hashSet.add(null);//可以为null
        hashSet.add("momo");//不能存放重复元素
        hashSet.add("momo");
        System.out.println(hashSet);

        hashSet.remove(null);
        System.out.println(hashSet);

        //遍历方式1 迭代器
        Iterator iterator = hashSet.iterator();
        while (iterator.hasNext()) {
            Object next = iterator.next();
            System.out.println(next);
        }

        System.out.println("--------");
        //增强for循环（底层是迭代器）
        for (Object o : hashSet) {
            System.out.println(o);
        }

        //无法使用普通for循环
    }
}
```

##### 1.HashSet

![image-20220728175534300](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062300231.png)



![image-20220728183946847](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062300727.png)



```java
package com.momo.collection_.set_;

import java.util.HashSet;

/**
 * @author momo~
 * @version 1.0
 */
public class HashSet03 {
    public static void main(String[] args) {
        HashSet hashSet = new HashSet();
        System.out.println(hashSet.add("milan"));//true
        System.out.println(hashSet.add("luck"));//true
        System.out.println(hashSet.add("milan"));//false
        System.out.println(hashSet.add("jack"));//true
        System.out.println(hashSet.add("Rose"));//true

        hashSet.remove("jack");
        System.out.println(hashSet);//[luck, Rose, milan]

        hashSet = new HashSet();//重置清空
        System.out.println(hashSet);

        //HashSet不能添加相同的元素
        hashSet.add("TOM");
        hashSet.add("Tom");
        hashSet.add("Tom");
        hashSet.add(new Dog("LUCK"));
        hashSet.add(new Dog("LUCK"));

        System.out.println(hashSet);
        //取出顺序固定
        //[TOM, Tom, Dog{name='LUCK'}, Dog{name='LUCK'}]

        //经典面试题
        hashSet.add(new String("sgs"));
        hashSet.add(new String("sgs"));
        //[TOM, Tom, Dog{name='LUCK'}, Dog{name='LUCK'}, sgs]
        System.out.println(hashSet);

    }
}
class Dog{
    private String name;

    public Dog(String name) {
        this.name = name;
    }

    @Override
    public String toString() {
        return "Dog{" +
                "name='" + name + '\'' +
                '}';
    }
}
```



![image-20220728205051521](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062300682.png)



案例：

![image-20220728211217130](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062300253.png)

```java
package com.momo.collection_.set_;

import java.util.HashSet;
import java.util.Objects;

/**
 * @author momo~
 * @version 1.0
 */
public class Exercise05 {
    public static void main(String[] args) {
        HashSet<Employee> employees = new HashSet<>();
        employees.add(new Employee("小猫",18));
        employees.add(new Employee("徐爱",18));
        employees.add(new Employee("小猫",18));

        System.out.println(new Employee("小猫",18));

        System.out.println(employees);

    }
}
class Employee{
    private String name;
    private int age = 0;

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Employee employee = (Employee) o;
        return age == employee.age && Objects.equals(name, employee.name);
    }

    @Override
    public int hashCode() {
        return Objects.hash(name, age);
    }

    //    @Override
//    public int hashCode() {
//        return 100;
//    }


    public Employee(String name, int age) {
        this.name = name;
        this.age = age;
    }

//    @Override
//    public boolean equals(Object obj) {
//        if (this == obj){
//            return true;
//        }
//        if (obj instanceof Employee){
//            Employee employee = (Employee)obj;
//            return this.name.equals(employee.name) && this.age == employee.age;
//        }
//        return false;
//    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    @Override
    public String toString() {
        return "Employee{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}
```



![image-20220728215531781](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062300316.png)

```java
package com.momo.collection_.set_;
/*
    定义一个Employee类，该类包括：private成员属性name、sal、birthday（MyDate类型）
    其中birthday为MyDate类型（属性包括：year、month、day）

    1.创建3个Employee放入HashSet中
    2.当name和birthday的值相同时，认为是相同员工，不能添加到HashSet集合中
 */

import java.util.HashSet;
import java.util.Objects;

/**
 * @author momo~
 * @version 1.0
 */
public class Exercise06 {
    public static void main(String[] args) {
        HashSet<Employee2> employees2 = new HashSet<>();
        employees2.add(new Employee2("小嘿",2500,new MyDate("1997","01","12")));
        employees2.add(new Employee2("小白",2500,new MyDate("1996","07","25")));
        employees2.add(new Employee2("小嘿",2500,new MyDate("1997","01","12")));

        System.out.print(employees2);
        //[Employee2{name='小嘿', sal=2500.0, myDate=MyDate{year=1997, month=01, day=12}}, Employee2{name='小白', sal=2500.0, myDate=MyDate{year=1996, month=07, day=25}}]


    }
}
class Employee2{

    private String name;
    private double sal;
    private MyDate myDate;

    public Employee2(String name, double sal, MyDate myDate) {
        this.name = name;
        this.sal = sal;
        this.myDate = myDate;
    }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Employee2 employee2 = (Employee2) o;
        return Double.compare(employee2.sal, sal) == 0 && Objects.equals(name, employee2.name) && Objects.equals(myDate, employee2.myDate);
    }

    @Override
    public int hashCode() {
        return Objects.hash(name, sal, myDate);
    }



    @Override
    public String toString() {
        return "Employee2{" +
                "name='" + name + '\'' +
                ", sal=" + sal +
                ", myDate=" + myDate +
                '}';
    }
}
class MyDate{
    private String year;
    private String month;
    private String day;

    public MyDate(String year, String month, String day) {
        this.year = year;
        this.month = month;
        this.day = day;
    }
    
   this.day = day;
    }

    @Override
    public String toString() {
        return "MyDate{" +
                "year=" + year +
                ", month=" + month +
                ", day=" + day +
                '}';
    }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        MyDate myDate = (MyDate) o;
        return Objects.equals(year, myDate.year) && Objects.equals(month, myDate.month) && Objects.equals(day, myDate.day);
    }

    @Override
    public int hashCode() {
        return Objects.hash(year, month, day);
    }
}
```



##### 2.LinkedHashSet

![image-20220729125540062](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062301004.png)



![image-20220729130651481](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062301992.png)



##### 3.TreeSet

TreeSet是一个可以对元素进行排序的容器。HashSet不支持对元素进行排序处理。底层实际是用TreeMap实现的，内部维持了一个简化版的TreeMap，通过Key来存储Set的元素。TreeSet内部需要对存储的元素进行排序。因此，需要给定排序规则。

排序规则实现方式：

通过元素自身实现比较规则

通过比较器指定比较规则

```java
import java.util.*;
public class TreeSetTest {
	public static void main(String[] args) {
		//实例化TreeSet
		Set<String> set = new TreeSet<>();
		//添加元素
		set.add("c");
		set.add("a");
		set.add("b");
		set.add("a");
		//获取元素,在这里String规则自身实现了排序规则
		for(String str:set) {
			System.out.println(str);
		}
	}
}	
//重复元素不能出现，做了排序处理
/*
a
b
c
*/
```



**通过元素自身实现比较规则**

在元素自身实现比较规则时，需要实现Comparable接口中的compareTo方法，该方法中用来定义比较规则。TreeSet通过调用该方法来完成对元素的排序处理。

**如果没有定义自身的比较接口，也没有给定外部的比较器，直接使用TreeSet会报错。**

通过比较器定义比较规则时，需要单独创建一个比较器，比较器需要实现Comparator接口中的compare方法来定义比较规则。在实例化TreeSet时将比较器对象交给TreeSet来完成元素的排序处理。此时元素自身就不需要实现比较规则了。

```java
package com.momo.collection_.set_;

import java.util.Comparator;
import java.util.TreeSet;

/**
 * @author momo~
 * @version 1.0
 */
public class TreeSet01 {
    public static void main(String[] args) {
        TreeSet treeSet = new TreeSet();

        //使用无参构造器创建，按照key自然排序
        treeSet.add("jack");
        treeSet.add("0");
        treeSet.add("milan");
        treeSet.add("aoMo");
        treeSet.add("c1235");

        System.out.println(treeSet);

        //按照字符串大小排序
        TreeSet treeSet1 = new TreeSet(new Comparator() {
            @Override
            public int compare(Object o1, Object o2) {
                //调用String的compareTo方法进行字符串大小比较
                return ((String) o2).compareTo((String) o1);
            }
        });

        treeSet1.add("jack");
        treeSet1.add("0");
        treeSet1.add("milan");
        treeSet1.add("aoMo");
        treeSet1.add("c1235");

        System.out.println(treeSet1);
    }
}
```



### 3.Map [K,V]

![image-20220729141808021](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062301146.png)



![image-20220729145602306](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062301722.png)



```JAVA
package com.momo.map_;

import java.util.HashMap;
import java.util.Map;
import java.util.Set;

/**
 * @author momo~
 * @version 1.0
 */
public class Map01 {
    public static void main(String[] args) {
        //map接口实现类的特点
        Map hashMap = new HashMap();
        hashMap.put("no1", "milan");
        hashMap.put(2, "momo");
        hashMap.put(new Object(), "tom");
        hashMap.put("no4", "张十三");
        hashMap.put("no5", null);
        hashMap.put("no6", "abc");

//        System.out.println(hashMap);
        //通过get方法，传入key，返回对应的value
//        System.out.println(hashMap.get(2));;

        //HashMap对象存放到entrySet$Node对象存放到entrySet主要是为了方便遍历
        //因为Map.entry提供了重要的方法getKey（）、getValue（）
        Set set = hashMap.entrySet();
        for (Object o : set) {
            Map.Entry entry = (Map.Entry) o;
            System.out.println(entry.getKey() + "=" + entry.getValue());
        }
    }
}
```



#### 1.Map接口常用方法

![image-20220730103412621](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062301042.png)



![image-20220730103438957](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062301767.png)



```java
package com.momo.map_;
/*
    演示Map接口常用方法
 */

import java.util.HashMap;

/**
 * @author momo~
 * @version 1.0
 */
public class MapMethods {
    public static void main(String[] args) {
        HashMap hashMap = new HashMap();
        hashMap.put("milan", "momo");
        hashMap.put("邓超", "孙俪");
        hashMap.put("王宝强", "马蓉");
        hashMap.put("宋姐", "马蓉");
        hashMap.put("kkk", "mmm");
        hashMap.put("kkk", "vvv");
        hashMap.put(null, "vvv");

        System.out.println(hashMap);

        //remove:根据键删除映射关系
        hashMap.remove(null);
        System.out.println(hashMap);
        //get:根据键获取值
        System.out.println(hashMap.get("kkk"));
        //size():获取元素隔宿
        System.out.println(hashMap.size());
        //isEmpty:判空
        System.out.println(hashMap.isEmpty());
        //clear:清空
//        hashMap.clear();
//        System.out.println(hashMap);
        //containsKey:查找键是否存在
        System.out.println(hashMap.containsKey("123"));
        System.out.println(hashMap.containsKey("邓超"));
    }
}
```



**Map六大遍历方式**

![image-20220730105155430](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062301666.png)



![image-20220730105208020](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062301821.png)



```java
package com.momo.map_;
/*
    演示Map接口实现类六大遍历方式
 */

import java.util.*;

/**
 * @author momo~
 * @version 1.0
 */
@SuppressWarnings("all")
public class traverse {
    public static void main(String[] args) {
        HashMap hashMap = new HashMap();
        hashMap.put("milan", "momo");
        hashMap.put("邓超", "孙俪");
        hashMap.put("王宝强", "马蓉");
        hashMap.put("宋姐", "马蓉");
        hashMap.put("kkk", "mmm");
        hashMap.put("kkk", "vvv");
        hashMap.put(null, "vvv");

        //第一组：取出所有key，通过key取出value
        Set set = hashMap.keySet();
        //方式1 增强for
        System.out.println("第一种方式：");
        for (Object key : set) {
            System.out.println(key + "=" + hashMap.get(key));
        }

        //方式二 迭代器
        System.out.println("第二种方式：");
        Iterator iterator = set.iterator();
        while (iterator.hasNext()) {
            Object key = iterator.next();
            System.out.println(key + "=" + hashMap.get(key));
        }

        //第二组：取出所有value
        Collection values = hashMap.values();
        //这里可使用所有Cellentions使用的遍历方式
        //方式1 增强for
        System.out.println("取出所有value");
        for (Object v : values) {
            System.out.println(v);
        }

        //方式二 迭代器
        Iterator iterator = values.iterator();
        while (iterator.hasNext()) {
            Object value = iterator.next();
            System.out.println(value);
        }

        //第三组 通过EntrySet获取k-v
        Set set1 = hashMap.entrySet();
        //方式1 增强for
        for (Object o : set1) {
            Map.Entry entry = (Map.Entry) o;
            System.out.println(entry.getKey() + "--" + entry.getValue());
        }

        //方式2 迭代器
        Iterator iterator2 = set1.iterator();
        while (iterator2.hasNext()) {
            Object next = iterator.next();
            Map.Entry entry = (Map.Entry) next;
            System.out.println(entry.getKey() + "-" + entry.getValue());
        }
    }
}
```

![image-20220730112058777](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062302922.png)

代码实现：

```java
package com.momo.map_;

import javax.jws.soap.SOAPBinding;
import java.util.*;

/**
 * @author momo~
 * @version 1.0
 */
public class Exercise01 {
    public static void main(String[] args) {
        HashMap hashMap = new HashMap();
        Employee employee1 = new Employee("小红", 5600, 1);
        Employee employee2 = new Employee("小蓝", 52000, 2);
        Employee employee3 = new Employee("小白", 3600, 3);
        hashMap.put(1,employee1);
        hashMap.put(2,employee2);
        hashMap.put(3,employee3);

        //hashMap.keySet()方式
        Set set = hashMap.keySet();
        for (Object key : set) {
            Employee employee = (Employee) hashMap.get(key);
            if (employee.getSal() > 18000){
                System.out.println(employee );
            }
        }
        
        //hashMap.values()方式
        Collection values = hashMap.values();
        for (Object o : values) {
            Employee employee = (Employee) o;
            if (employee.getSal() > 18000){
                System.out.println(employee);
            }
        }

        //hashMap.entrySet()方式
        Set set1 = hashMap.entrySet();
        Iterator iterator = set1.iterator();
        while (iterator.hasNext()) {
            Object next = iterator.next();
            Map.Entry entry = (Map.Entry) next;
            Employee employee = (Employee) entry.getValue();
            if (employee.getSal() > 18000){
                System.out.println(employee);
            }
        }
    }
}
class Employee{
	//省略
}
```

#### 2.HashMap

![image-20220730121933230](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062302073.png)



HashMap底层机制

![image-20220730122424685](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062302511.png)



![image-20220730123106469](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062302892.png)



#### 3.HashTable

![image-20220730134535400](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062302193.png)



![image-20220730140336563](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062302756.png)



HashTable与HashMap对比

![image-20220730140512229](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062302459.png)



#### 4.Properties![image-20220730140754757](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062359332.png)

![image-20220730141912060](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062302722.png)



#### 5.TreeMap

Map在Java里面分为两种：HashMap和TreeMap

区别就是TreeMap有序，HashMap无序。如果只需要存映射，那么HashMap就够了，但是如果需要存有顺序的key那么就用TreeMap。

写程序需要知道怎么构建comparator去自定义排序，还要知道floorKey 和floorEntry

TreeMap构建

```java
TreeMap<Integer, String> treemap = new TreeMap<>();
// populating tree map
treemap.put(2, "two");
treemap.put(1, "one");
treemap.put(3, "three");
treemap.put(4, "six");
treemap.put(5, "five");
```

他会自动根据key进行排序

```java
System.out.println("Value is: "+ treemap.floorKey(4));//输出小于等于4对最大对key
System.out.println("Value is: "+ treemap.floorEntry(2));//输出小于等于2对最大key=value
System.out.println("Value is: "+ treemap.firstEntry());//输出最小对key=value

Value is: 4

Value is: 2=two

Value is: 1=one
```



那么如果我们想自己去定义排序呢。

建立对时候可以定义

```java
TreeMap<Integer, String> treemap = new TreeMap<>(new Comparator<Integer>() {
    @Override
    public int compare(Integer o1, Integer o2) {
        return o1.compareTo(o2);
    }
});
```

看源码

```java
public int compareTo(Integer anotherInteger) {
    return compare(this.value, anotherInteger.value);
}

public static int compare(int x, int y) {
    return (x < y) ? -1 : ((x == y) ? 0 : 1);
}
```

返回

1：往前插入： o1>o2 由于默认升序，所以o2会放在o1前面。

0： 相同

-1 ： 往后插入： o1<o2 由于默认升序所以o2会在o1后面。

全部手写：定义其他规则也一样，如果我们希望满足什么规则往前插入，则让他返回1。

```java
TreeMap<Integer, String> treemap = new TreeMap<>(new Comparator<Integer>() { @Override
    public int compare(Integer o1, Integer o2) {
        if(o1>o2)
            return 1;
        else if(o1<o2)
            return -1;
        return 0; } });
```



所以我们自己定义优先级的时候要知道怎么去定义优先级，然后重写compare函数就好。

当然如果只想和默认顺序相反那么将返回的时候o1和o2换位置就好了。



### 4.Collections工具类

![image-20220730155130816](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062302364.png)



![image-20220730164338922](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062302840.png)



**案例总结：**

![image-20220730171531621](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062302864.png)

```java
package com.momo;

import java.util.ArrayList;
import java.util.Collections;
import java.util.Iterator;

/**
 * @author momo~
 * @version 1.0
 */
public class Homework01 {
    public static void main(String[] args) {
        News new1 = new News("新冠确诊病例超千万，数百万印度教徒赴恒河\"圣浴\"引民众担忧");
        News new2 = new News("男子突然想起2个月前钓的鱼还在网兜里，捞起一遍赶紧放生");

        ArrayList<News> news = new ArrayList<>();
        news.add(new1);
        news.add(new2);


        for (int i = news.size() - 1; i >= 0; i--) {
            String title = news.get(i).getTitle();
            System.out.println(minus(title));
        }

//        for (Object o : news) {
//            News n = (News)o;
//            String str = n.getTitle();
//            System.out.println(minus(str));
//        }

    }
    public static String minus(String str){
        //记得判空
        if (str == null){
            return "";
        }
        if (str.length() > 15){
            String substring = str.substring(0, 16);
            return substring + "...";
        } else {
            return str;
        }
    }
}
```



![image-20220730203813248](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062302151.png)

```java
package com.momo;

import java.util.ArrayList;
import java.util.Iterator;

/**
 * @author momo~
 * @version 1.0
 */
public class Homework02 {
    public static void main(String[] args) {
        ArrayList<Car> cars = new ArrayList<>();
        Car car = new Car("小黑", 555);
        cars.add(new Car("小明",12.65));
        cars.add(new Car("小红",26));
        cars.add(new Car("小蓝",653));
        cars.add(new Car("小白",1.6));
        cars.add(car);

        System.out.println(cars);

        cars.remove(2);
        System.out.println(cars);

        System.out.println(cars.contains(car));

        System.out.println(cars.size());

        System.out.println(cars.isEmpty());

        cars.clear();
        System.out.println(cars);

        ArrayList<Car> cars1 = new ArrayList<>();
        cars1.add(new Car("小猫",125));
        cars.addAll(cars1);
        System.out.println(cars);

        cars.removeAll(cars1);
        System.out.println(cars);

        cars.add(new Car("小明",12.65));
        cars.add(new Car("小红",26));
        cars.add(new Car("小蓝",653));
        cars.add(new Car("小白",1.6));

//        for (Object o : cars) {
//            System.out.println(o);
//        }

        Iterator<Car> iterator = cars.iterator();
        while (iterator.hasNext()) {
            Car next = iterator.next();
            System.out.println(next);
        }

    }
}
```



![image-20220730205737643](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062302286.png)

```java
package com.momo;

import java.util.HashMap;

/**
 * @author momo~
 * @version 1.0
 */
public class Homework03 {
    public static void main(String[] args) {

        HashMap hashMap = new HashMap();
        hashMap.put("jack",650);
        hashMap.put("tom",1200);
        hashMap.put("smith",2900);

        System.out.println(hashMap);
        hashMap.replace("jack",2600);

        System.out.println(hashMap);

        for (Object key : hashMap.keySet()) {
            hashMap.put(key,(Integer)hashMap.get(key) + 100);
        }
        
        for (Object key : hashMap.keySet()) {
            System.out.println(key);
        }

        for (Object value : hashMap.values()) {
            System.out.println(value);
        }
    }
}
```



![image-20220730214816954](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062303464.png)

```java
package com.momo;

import java.util.TreeSet;

/**
 * @author momo~
 * @version 1.0
 */
public class Homework04 {
    public static void main(String[] args) {
        TreeSet treeSet = new TreeSet();
        treeSet.add(new Person());
        treeSet.add(new Person());
        treeSet.add(new Person());
        System.out.println(treeSet);
    }
}
class Person implements Comparable{

    @Override
    public int compareTo(Object o) {
        return 0;
    }
}
```



![image-20220730215938360](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062303355.png)



![image-20220730220500346](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062303771.png)



## 9.泛型

  ![image-20220731122918766](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062303060.png)

```java
package com.momo.genericity_;

import java.util.ArrayList;

/**
 * @author momo~
 * @version 1.0
 */
public class Generic01 {
    public static void main(String[] args) {
        ArrayList arrayList = new ArrayList();
        arrayList.add(new Dog("小白",15));
        arrayList.add(new Dog("小黑",12));
        arrayList.add(new Dog("小蓝",6));

        //添加一只猫
//        arrayList.add(new Cat("小猫",13));
        //抛出异常ClassCastException

        for (Object o : arrayList) {
            Dog dog = (Dog) o;
            System.out.println(dog.getName() + "=" + dog.getAge());
        }
    }
}
class Dog{
}
class Cat{
}
```



![image-20220731124017553](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062303990.png)



![image-20220731125047701](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062303300.png)

```java
public class Generic02 {
    public static void main(String[] args) {
        //<Dog2>表示存放到集合中元素为Dog2类型，编译器进行检测
        ArrayList<Dog2> arrayList = new ArrayList<Dog2>();
        arrayList.add(new Dog2("小白",15));
        arrayList.add(new Dog2("小黑",12));
        arrayList.add(new Dog2("小蓝",6));

//        arrayList.add(new Cat("小猫",13));

//        for (Object o : arrayList) {
//            Dog dog = (Dog) o;
//            System.out.println(dog.getAge() + "=" + dog.getName());
//        }

        for (Dog2 dog2 : arrayList) {
            System.out.println(dog2.getAge() + "=" + dog2.getName());
        }
    }
}
```





![image-20220731125736088](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062303858.png)



```java
package com.momo.genericity_;

/**
 * @author momo~
 * @version 1.0
 */
public class Generic03 {
    public static void main(String[] args) {
        Person<String> stringPerson = new Person<>("123");
        stringPerson.show();//class java.lang.String
        Person<Integer> integerPerson = new Person<>(123);
        //E具体数据类型在定义Person对象时指定，即在编译期间就确定E是什么类型
        integerPerson.show();//class java.lang.Integer
    }
}
//E表示s的数据类型，定义时指定
class Person<E>{
    E s;

    public Person(E s) {
        this.s = s;
    }

    public E f(){
        return s;
    }

    public void show(){
        System.out.println(s.getClass());
    }
}
```



**泛型应用实例**

![image-20220731131234269](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062303922.png)



![image-20220731131452574](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062303233.png)

```java
public class Generic04 {
    public static void main(String[] args) {
        Student stu01 = new Student("小白", 15);
        Student stu02 = new Student("小黑", 25);
        Student stu03 = new Student("小蓝", 13);

        HashSet<Student> students = new HashSet<>();
        students.add(stu01);
        students.add(stu02);
        students.add(stu03);
        
//        for (Student student : students) {
//            System.out.println(student);
//        }

//        Iterator<Student> iterator = students.iterator();
//        while (iterator.hasNext()) {
//            Student next = iterator.next();
//            System.out.println(next);
//        }
        
        HashMap<String, Student> strMap = new HashMap<>();
        strMap.put(stu01.getName(),stu01);
        strMap.put(stu02.getName(),stu02);
        strMap.put(stu03.getName(),stu03);

        for (Map.Entry<String, Student> strEntry : strMap.entrySet()) {
            System.out.println(strEntry.getKey() + "==" + strEntry.getValue());
        }
    }
}
```



**注意事项1：**

![image-20220731134638253](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062304039.png)

```java
package com.momo.genericity_;

import java.util.ArrayList;
import java.util.List;

/**
 * @author momo~
 * @version 1.0
 */
public class Generic05 {
    public static void main(String[] args) {
        //1.泛型不能用基本数据类型
        ArrayList<Integer> integers = new ArrayList<>();
//        ArrayList<int> ints = new ArrayList<int>();
        //Type argument cannot be of primitive type
        //类型参数不能是原始类型

        //2.泛型指定后，可以传入该类型或该类型的子类型
        Dog3<A> aDog3 = new Dog3<>(new A());
        Dog3<A> aDog31 = new Dog3<>(new B());

        //3.泛型使用形式  //实际开发中，简写如下
        ArrayList<Integer> integers1 = new ArrayList<>();
        List<Integer> integers2 = new ArrayList<>();
    }
}
class A{
}
class B extends A{
}
class Dog3<E> {
    E e;

    public Dog3(E e) {
        this.e = e;
    }
}
```



![image-20220731140911246](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062306936.png)

```java
package com.momo.genericity_;

import java.util.ArrayList;
import java.util.Comparator;
import java.util.Date;

/**
 * @author momo~
 * @version 1.0
 */
public class GenericExercise01 {
    public static void main(String[] args) {
        ArrayList<Employee> employees = new ArrayList<>();
        employees.add(new Employee("tom",5600,new MyDate(2,26,1995)));
        employees.add(new Employee("milan",8600,new MyDate(6,3,1535)));
        employees.add(new Employee("como",3200,new MyDate(9,8,2095)));

        employees.sort(new Comparator<Employee>() {
            @Override
            public int compare(Employee o1, Employee o2) {
                if (!(o1 instanceof Employee && o2 instanceof Employee)){
                    System.out.println("类型错误");
                    return 0;
                }
                //比较name
                int nameCom = o1.getName().compareTo(o2.getName());
                if (nameCom != 0){
                    return nameCom;
                }

                return o1.getBirthday().compareTo(o2.getBirthday());
            }
        });

        for (Employee employee : employees) {
            System.out.println(employee);
        }
    }
}
class Employee{
    private String name;
    private double sal;
    private MyDate birthday;

    public Employee(String name, double sal, MyDate birthday) {
        this.name = name;
        this.sal = sal;
        this.birthday = birthday;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public double getSal() {
        return sal;
    }

    public void setSal(double sal) {
        this.sal = sal;
    }

    public MyDate getBirthday() {
        return birthday;
    }

    public void setBirthday(MyDate birthday) {
        this.birthday = birthday;
    }

    @Override
    public String toString() {
        return "Employee{" +
                "name='" + name + '\'' +
                ", sal=" + sal +
                ", birthday=" + birthday +
                '}';
    }
}
class MyDate implements Comparable<MyDate>{
    private int month;
    private int day;
    private int year;

    public MyDate(int month, int day, int year) {
        this.month = month;
        this.day = day;
        this.year = year;
    }

    public int getMonth() {
        return month;
    }

    public void setMonth(int month) {
        this.month = month;
    }

    public int getDay() {
        return day;
    }

    public void setDay(int day) {
        this.day = day;
    }

    public int getYear() {
        return year;
    }

    public void setYear(int year) {
        this.year = year;
    }

    @Override
    public String toString() {
        return "MyDate{" +
                "month=" + month +
                ", day=" + day +
                ", year=" + year +
                '}';
    }

    @Override
    public int compareTo(MyDate o) {
        //比较年
        int yearCom = this.year - o.getYear();
        if (yearCom != 0){
            return yearCom;
        }

        //比较月
        int monthCom = this.month - o.getMonth();
        if (monthCom != 0){
            return monthCom;
        }
        //比较日
        return  this.day - o.getDay();
    }
}
```



**自定义泛型**

![image-20220731161020981](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062307971.png)



```java
package com.momo.genericity_.customgeneric;

/**
 * @author momo~
 * @version 1.0
 */
public class CustomGeneric01 {
    public static void main(String[] args) {

    }
}
//自定义泛型类 T,R,M泛型标识符
//<>可有多个

class Tiger<T,R,M>{
    //属性使用泛型
    String name;
    T r;
    M m;
    T t;
    //Type parameter 'T' cannot be instantiated directly
    //不能直接实例化类型参数“T”
    //因为不能确定类型，所以无法在内存开辟空间
//    T[] ts =  new T[8];

    //因为静态是和类相关的，在类加载时，对象还没创建
//    public static void m1(M m){
//    }

    //构造器使用泛型
    public Tiger(String name, T r, M m, T t) {
        this.name = name;
        this.r = r;
        this.m = m;
        this.t = t;
    }

    //方法使用泛型
    public T getR() {
        return r;
    }
}
```



**自定义泛型接口**

![image-20220731163241772](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062307318.png)



**自定义泛型方法**

![image-20220731170739336](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062307346.png)



**泛型的继承和通配符**

![image-20220731171845048](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062307638.png)



**JUnit**

![image-20220731172150655](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062307224.png)



![image-20220731172338766](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062307738.png)



![image-20220731173047553](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062307450.png)

```JAVA
    @Test
    public void m1(){
        System.out.println("m1()");
    }

    @Test
    public void  m2(){
        System.out.println("m2()");
    }
}
```



案例总结：

![image-20220731173144983](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062308664.png)

```java
package com.momo.genericity_;

import org.junit.jupiter.api.Test;

import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

/**
 * @author momo~
 * @version 1.0
 */
public class Homework {
    public static void main(String[] args) {

    }
    @Test
    public void test(){
        DAO<User> userDAO = new DAO<>();
        userDAO.save("001",new User(1,10,"jack"));
        userDAO.save("002",new User(2,16,"milan"));
        userDAO.save("003",new User(3,19,"momo"));


        userDAO.update("003",new User(5,22,"sims"));
        System.out.println();

        List<User> list = userDAO.list();
        System.out.println(list);

        
    }
}
class DAO<T>{
    private Map<String,T> map = new HashMap<>();

    @Test
    public void save(String id,T entity){
        map.put(id, entity);
    }

    public T get(String id){
        return map.get(id);
    }

    public void update(String id,T entity){
        map.put(id,entity);
    }

    public void delete(String id){
        map.remove(id);
    }

    @Test
    public List<T> list(){
        ArrayList<T> ts = new ArrayList<>();
        for (T value : map.values()) {
            ts.add(value);
        }
        return ts;
    }

    @Override
    public String toString() {
        return "DAO{" +
                "map=" + map +
                '}';
    }
}
class User{
    private int id;
    private int age;
    private String name;

    public User(int id, int age, String name) {
        this.id = id;
        this.age = age;
        this.name = name;
    }

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Override
    public String toString() {
        return "\nUser{" +
                "id=" + id +
                ", age=" + age +
                ", name='" + name + '\'' +
                '}';
    }
}
```



## 10.坦克大战verson1.0

![image-20220802080136427](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062308205.png)

![image-20220802075826534](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062308463.png)



### 1.Java绘图坐标体系

![image-20220802080642870](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062308292.png)



![image-20220802081009876](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062308406.png)



#### 1.画圆

`Graphics`类是所有图形上下文的抽象基类，允许应用程序绘制在各种设备上实现的组件，以及屏幕上的图像。

```
drawOval(int x, int y, int width, int height)
```

绘制椭圆形轮廓。

```
public abstract void drawOval(int x,
                              int y,
                              int width,
                              int height)
```

绘制椭圆形轮廓。 其结果是由指定的矩形内配合在一个圆或椭圆`x` ， `y` ， `width`和`height`参数。

椭圆形覆盖了`width + 1`像素宽和`height + 1`像素高的区域。

- **参数**

  `x` - 要绘制的椭圆的左上角的 *x*坐标。

  `y` - 要绘制的椭圆的左上角的 *y*坐标。

  `width` - 要绘制的椭圆的宽度。

  `height` - 要绘制的椭圆的高度。



![image-20220802083143690](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062308874.png)

效果：

![image-20220802083220380](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062308619.png)



```java
package com.momo.draw;
/*
    演示绘图
 */

import javax.swing.*;
import java.awt.*;

/**
 * @author momo~
 * @version 1.0
 */
public class DrawCircle extends JFrame{//画框
    //定义一个面板
    private MyPanel mp = null;

    public static void main(String[] args) {
        new DrawCircle();
    }

    public DrawCircle(){
        //初始化面板
        mp = new MyPanel();
        //把面板放入画框
        this.add(mp);
        //设置窗口（画框）的大小
        this.setSize(400,300);
        //点击窗口X,即可退出程序
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        this.setVisible(true);//设置可以显示
    }
}
//1.先定义一个面板MyPanel，继承JPanel类
class MyPanel extends JPanel{

    //绘图方法
    //1.MyPanel ——》画板
    //2.Graphics ——》画笔
    //3.Graphics提供了很多绘图的方法
    @Override
    public void paint(Graphics g) {
        super.paint(g);//调用父类的方法完成初始化
        //画圆 drawOval
        //public abstract void drawOval(int x,
        //                              int y,
        //                              int width,
        //                              int height)
        //绘制椭圆形轮廓。 其结果是由指定的矩形内配合在一个圆或椭圆x ， y ， width和height参数。
        //椭圆形覆盖了width + 1像素宽和height + 1像素高的区域。
        //
        //参数
        //x - 要绘制的椭圆的左上角的 x坐标。
        //y - 要绘制的椭圆的左上角的 y坐标。
        //width - 要绘制的椭圆的宽度。
        //height - 要绘制的椭圆的高度。

        g.drawOval(10,10,100,100);
    }
}

```



#### 2.Graphics类常用方法

![image-20220802083927098](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062308316.png)



```java
drawLine(int x1, int y1, int x2, int y2)
```

在该图形上下文的坐标系中的点 `(x1, y1)`和 `(x2, y2)`之间绘制一行，使用当前颜色。



```java
drawRect(int x, int y, int width, int height)
```

绘制指定矩形的轮廓



```java
fillRect(int x, int y, int width, int height)
```

填写指定的矩形。



```java
fillOval(int x, int y, int width, int height)
```

用当前颜色填充由指定矩形界定的椭圆。



```java
        //演示绘制不同图形
        //drawLine(int x1, int y1, int x2, int y2)
        //在该图形上下文的坐标系中的点 (x1, y1)和 (x2, y2)之间绘制一行，使用当前颜色。
        g.drawLine(10,10,100,100);

        //drawRect(int x, int y, int width, int height)
        //绘制指定矩形的轮廓
        g.drawRect(10,10,100,100);

        //fillRect(int x, int y, int width, int height)
        //填写指定的矩形。
        //设置颜色
        g.setColor(Color.blue);
        g.fillRect(10,10,100,100);

        //fillOval(int x, int y, int width, int height)
        //用当前颜色填充由指定矩形界定的椭圆。
        g.setColor(Color.blue);
        g.fillOval(10,10,50,100);

        //画图片
        //1.获取图片资源 /001.jpg根目录下寻找
        Image image = Toolkit.getDefaultToolkit().getImage(Paint.class.getResource("/001.jpg"));
        g.drawImage(image,10,10,200,200,this);

        //画字符串
        //drawString(String str, int x, int y)
        //使用该图形上下文的当前字体和颜色绘制由指定字符串给出的文本。
        //给画笔设置颜色和字体
        g.setColor(Color.blue);
        g.setFont(new Font("隶书",Font.BOLD,50));
        g.drawString("北京你好",100,100);
        //设置画笔的字体 setFont
        //设置画笔的颜色 setColor
```



#### 3.Java事件处理机制

![image-20220802114230814](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062308473.png)



![image-20220802114542143](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062308760.png)



![image-20220802114553471](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062308359.png)



![image-20220802114944350](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062309916.png)



![image-20220802115004016](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062309839.png)



```java
package com.momo.event_;

import javax.swing.*;
import java.awt.*;
import java.awt.event.KeyEvent;
import java.awt.event.KeyListener;

/**
 * @author momo~
 * @version 1.0
 * 演示小球通过键盘控制上下左右的移动
 */
public class BallMove extends JFrame  {
    MyPanel mp = null;
    public static void main(String[] args) {
        BallMove ballMove = new BallMove();
    }

    public BallMove(){
        mp = new MyPanel();
        this.add(mp);
        this.setSize(400,300);
        //窗口JFrame对象监听键盘事件
        this.addKeyListener(mp);
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        this.setVisible(true);
    }
}

class MyPanel extends JPanel implements KeyListener {
    //为了让小球移动,把他的左上角的坐标(x,y)设置成变量
    int x = 10;
    int y = 10;

    @Override
    public void paint(Graphics g) {
        super.paint(g);
        g.fillOval(x, y, 20, 20);//默认黑色
    }

    //有字符输出时,该方法就会触发
    @Override
    public void keyTyped(KeyEvent e) {

    }

    //当某个键按下.该方法触发
    @Override
    public void keyPressed(KeyEvent e) {
//        System.out.println((char) e.getKeyCode() + "被按下");
        //根据用户按下不同方向键处理移动
        //在java中,会给每一个键,分配一个值
        if (e.getKeyCode() == KeyEvent.VK_DOWN){//KeyEvent.VK_DOWN 键盘向下对应code
            y++;
        } else if (e.getKeyCode() == KeyEvent.VK_UP){
            y--;
        } else if (e.getKeyCode() == KeyEvent.VK_RIGHT) {
            x++;
        } else if (e.getKeyCode() == KeyEvent.VK_LEFT) {
            x--;
        }

        //重绘
        this.repaint();
    }

    //当某个键松开,该方法触发
    @Override
    public void keyReleased(KeyEvent e) {
    }
}
```

![image-20220802115218514](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062309662.png)





## 11.线程进程

![image-20220802132324093](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062309961.png)



![image-20220802132534259](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062309504.png)



![image-20220802132731873](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062309129.png)



![image-20220802134316845](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062309469.png)



### 1.创建线程方式

![image-20220802134552023](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062309716.png)



![image-20220802142558979](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062309246.png)



![image-20220802142516916](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062309972.png)



#### **1.继承Thread类**

```java
package com.momo.thread_;

/**
 * @author momo~
 * @version 1.0
 * 演示通过thread类创建线程
 */
public class Thread01 {
    public static void main(String[] args) {
        //创建一个cat对象,当作线程使用
        Cat cat = new Cat();
        //当main线程启动一个子线程Thread-0,主线程不会阻塞,会继续执行

        //private native void start0();
        cat.start();//启动线程


//        cat.run();//这里的run()方法就是一个普通的方法,没有真正的启动一个线程

        System.out.println("主线程名:" + Thread.currentThread().getName());

        for (int i = 0; i < 60; i++) {
            System.out.println("主线程 i=" + i);
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
        }
    }
}
//1.当一个类继承了Thread类,该类就可以当作线程使用
//2.run Thread类实现了Runnable 接口 的run方法
class Cat extends Thread {

    private int times = 0;

    @Override
    public void run() {
//        super.run();//重写run方法,实现自己的业务逻辑
        while (true){
            System.out.println("喵喵" + (++times));
            try {
                sleep(1000);
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
            if (times == 80){
                break;
            }
        }
    }
}

```



#### 2.实现Runable接口

```java
package com.momo.thread_;

/**
 * @author momo~
 * @version 1.0
 */
public class Runnable01 {
    public static void main(String[] args) {
        Dog dog = new Dog();
        Thread thread = new Thread(dog);
        thread.start();
    }
}
//通过实现Runnable接口,开发线程
class Dog implements Runnable{

    int count = 0;
    @Override
    public void run() {
        while (true){
            System.out.println("汪汪叫" + (++count) + Thread.currentThread().getName());

            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }

            if (count == 10){
                break;
            }
        }
    }
}
```



#### 3.静态代理

1、静态代理在使用时，需要定义接口或者父类，被代理对象（即目标对象）与代理对象一起实现相同的接口或者是继承相同父类。

1、具体要求

　（1）定义一个接口：ITeacherDAO

　（2）目标对象 TeacherDAO 实现接口 ITeacherDAO

　（3）使用静态代理方式，就需要在代理对象 TeacherDAOProxy 中也实现 ITeacherDAO

　（4）调用的时候通过调用代理对象的方法来调用目标对象

　   (5）特别提示：代理对象与目标对象要实现相同的接口，然后通过调用相同的方法来调用目标对象的方法；



![image-20220802151140127](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062309767.png)

接口:

```java
/**
2  * 接口
3  */
4 public interface ITeacher {
5 
6     void teach();
7 }
```

被代理类:

```java
 /**
2  * 被代理对象
3  */
4 public class TeacherDao implements ITeacher{
5     @Override
6     public void teach() {
7         System.out.println("老师授课中。。。。");
8     }
9 }
```

代理类:

```java
 /**
 2  * 代理对象，静态代理
 3  */
 4 public class TeacherDaoProxy implements ITeacher{
 5 
 6     /**
 7      *  目标对象，通过接口来聚合
 8      */
 9     private ITeacher target;
10 
11     /**
12      * 构造器
13      * @param target
14      */
15     public TeacherDaoProxy(ITeacher target) {
16         this.target = target;
17     }
18 
19     @Override
20     public void teach() {
21         System.out.println("开始代理，完成某些操作....");
22         target.teach();
23         System.out.println("提交");
24     }
25 }
```

执行:

```java
 public class Client {
 2     public static void main(String[] args) {
 3         //创建目标对象，被代理对象
 4         TeacherDao teacherDao = new TeacherDao();
 5 
 6         //创建代理对象，同时把被代理对象传递给代理对象
 7         TeacherDaoProxy teacherDaoProxy = new TeacherDaoProxy(teacherDao);
 8 
 9         //通过代理对象，调用到被代理对象的方法
10         //即：执行的是代理对象的方法，代理对象再去调用目标对象的方法
11         teacherDaoProxy.teach();
12     }
13 }
```



**小结:**

　　1、优点：在不修改目标对象的功能前提下，能通过代理对象对目标功能扩展；

　　2、缺点：因为代理对象需要与目标对象实现一样的接口，所以会有很多代理类；

　　3、一旦接口增加方法，目标对象与代理对象都要维护





#### 4.为什么是start

```java
cat.start();//启动线程

private native void start0();
```

![image-20220802143356420](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062310742.png)



![image-20220802155756156](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062310065.png)



![image-20220802155815974](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062310670.png)

```java
package com.momo.thread_;

/**
 * @author momo~
 * @version 1.0
 */
public class Multithreading01 {
    public static void main(String[] args) {
        Person person = new Person();
        Person2 person2 = new Person2();
        Thread thread = new Thread(person);
        thread.start();
        Thread thread1 = new Thread(person2);
        thread1.start();
    }
}

class Person implements Runnable {

    int count = 0;
    @Override
    public void run() {
        while (true) {
            System.out.println("hello world" + (++count));
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
            if (count == 10) {
                break;
            }
        }
    }
}

class Person2 implements Runnable {

    int count = 0;
    @Override
    public void run() {
        while (true){
            System.out.println("Hi" + (++count));
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
            if (count == 5){
                break;
            }
        }
    }
}
```



#### 5.多线程售票问题

![image-20220802162906061](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062310398.png)

```JAVA
package com.momo.thread_;

/**
 * @author momo~
 * @version 1.0
 * 使用多线程,模拟三个窗口同时售票
 */
public class SaleThread01 {
    public static void main(String[] args) {
        Sale sale1 = new Sale();
        Sale sale2 = new Sale();
        Sale sale3 = new Sale();
        new Thread(sale1).start();
        new Thread(sale2).start();
        new Thread(sale3).start();
//        sale1.start();
//        sale2.start();
//        sale3.start();

    }
}
class Sale implements Runnable{

    private static int count = 100;

    @Override
    public void run() {
        while (true){
            if (count <= 0){
                System.out.println("票已售完");
                break;
            }
            try {
                Thread.sleep(50);
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
            System.out.println("窗口" + Thread.currentThread().getName()
                    + "剩余票数:" + (--count));
        }
    }
}
```



![image-20220802162816798](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062310608.png)



#### 6.线程终止退出

![image-20220802164247826](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062310497.png)

```java
package com.momo.thread_;

/**
 * @author momo~
 * @version 1.0
 */
public class ThreadExit01 {
    public static void main(String[] args) throws InterruptedException {
        Dog3 dog3 = new Dog3();
        dog3.start();

        //希望main线程去控制子线程的终止
        Thread.sleep(1000 * 10);
        dog3.setLoop(false);//通知方式
    }
}
class Dog3 extends Thread{
    private int count = 0;

    private boolean loop = true;

    @Override
    public void run() {
        while (loop){
            try {
                Thread.sleep(50);
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
            System.out.println("运行中..." + (++count));
        }
    }

    public boolean isLoop() {
        return loop;
    }

    public void setLoop(boolean loop) {
        this.loop = loop;
    }
}
```



#### 7.线程常用方法

![image-20220802164344567](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062310509.png)



![image-20220802164733815](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062311610.png)

```java
package com.momo.thread_;

/**
 * @author momo~
 * @version 1.0
 */
public class ThreadMethods {
    public static void main(String[] args) throws InterruptedException {
        T t = new T();
        t.setName("momo");
        t.setPriority(Thread.MIN_PRIORITY);//设置线程优先级
        t.start();

        for (int i = 0; i < 5; i++) {
            Thread.sleep(1000);
            System.out.println("hi" + i);
        }

        t.interrupt();
    }
}
class T extends Thread{

    @Override
    public void run() {
        while (true){
            for (int i = 0; i < 100; i++) {
                //Thread.currentThread().getName() 获取当前线程名称
                System.out.println(Thread.currentThread().getName() + "吃包子" + i);
            }
            try {
                System.out.println(Thread.currentThread().getName() + "休眠中");
                Thread.sleep(20000);
            } catch (InterruptedException e) {
                System.out.println(Thread.currentThread().getName() + "被interrupted了");
            }
        }
    }
}
```



**yield与join**

![image-20220802171250453](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062311604.png)



```java
package com.momo.thread_;

/**
 * @author momo~
 * @version 1.0
 */
public class ThreadMethod02 {
    public static void main(String[] args) throws InterruptedException {
        Jo jo = new Jo();
        jo.start();

        for (int i = 0; i < 20; i++) {
            System.out.println("Hi" + Thread.currentThread().getName() + i);
            Thread.sleep(1000);
            //线程插队
//            if (i == 5){
//                jo.join();
//            }
            Thread.yield();//礼让,不一定成功
        }
    }
}
class Jo extends Thread{
    public int count = 0;

    @Override
    public void run() {
        while (true){
            if (count == 20){
                break;
            }
            System.out.println("hello" + Thread.currentThread().getName() + (++count));
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
        }
    }
}

```



![image-20220802174026571](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062359982.png)

```JAVA
package com.momo.thread_;

import java.awt.*;

/**
 * @author momo~
 * @version 1.0
 */
public class ThreadJoinExercise {
    public static void main(String[] args) throws InterruptedException {
        T2 t2 = new T2();
        Thread thread = new Thread(t2);
        for (int i = 0; i < 10; i++) {
            if (i == 5) {
                thread.start();//启动子线程
                thread.join();//让子线程插队,先执行完毕
            }
            Thread.sleep(1000);
            System.out.println("Hi" + i);
        }
    }
}
class T2 implements Runnable{

    private int count = 0;

    @Override
    public void run() {
        while (true){
            if (count == 10){
                break;
            }
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
            System.out.println(Thread.currentThread().getName() + "hello0" + (++count));
        }
    }
}
```



#### 8.守护线程

![image-20220802195233454](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062311954.png)

```java
package com.momo.thread_;

/**
 * @author momo~
 * @version 1.0
 */
public class GuardThread01 {
    public static void main(String[] args) throws InterruptedException {
        MyDaemonThread myDaemonThread = new MyDaemonThread();
        
        //如果希望当主线程结束后子线程自动退出
        //只需要将子线程设为守护线程
        myDaemonThread.setDaemon(true);

        myDaemonThread.start();//开启子线程

        for (int i = 0; i <= 10; i++) {
            System.out.println(Thread.currentThread().getName() + "主线程");
            Thread.sleep(1000);
        }
    }
}
class MyDaemonThread extends Thread{

    @Override
    public void run() {
        for (; ; ) {
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
            System.out.println(Thread.currentThread().getName() + "结束了");
        }
    }
}
```



#### 9.线程生命周期

![image-20220802200554319](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062311236.png)

![image-20220802204424771](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062311860.png)

```java
package com.momo.thread_;

import javax.jws.soap.SOAPBinding;

/**
 * @author momo~
 * @version 1.0
 * 演示线程生命周期
 */
public class ThreadState {
    public static void main(String[] args) throws InterruptedException {
        H h = new H();
        System.out.println(h.getName() + "状态:" + h.getState());
        h.start();

        while (Thread.State.TERMINATED != h.getState()){
            System.out.println(h.getName() + "状态:" +h.getState());
            Thread.sleep(1000);
        }

        System.out.println(h.getName() + "状态:" +h.getState());

    }
}
class H extends Thread{
    @Override
    public void run() {
        while (true){
            for (int i = 0; i < 10; i++) {
                System.out.println("Hi" + i);
                try {
                    Thread.sleep(1000);
                } catch (InterruptedException e) {
                    throw new RuntimeException(e);
                }
            }
            break;
        }
    }
}
```







在java中，任何对象都要有生命周期，线程也不例外，它也有自己的生命周期。当Thread对象创建完成时，线程的生命周期便开始了，当run()方法中代码正常执行完毕或者线程抛出一个未捕获的异常(Exception)或者错误(Error)时，线程的生命周期便会结束。线程的整个生命周期可以分为5个阶段，分别是新建状态(New)、就绪状态(Runnable)、运行状态(Running)、阻塞状态(Blocked)和死亡状态(Terminated)，线程的不同状态表名了线程当前正在进行的活动。在程序中，通过一些操作可以使线程在不同状态之间转换，如下图：

![image-20220802202022333](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062313319.png)

上图中展示了线程各种状态的转换关系，箭头表示可转换的方向，其中，单箭头表示状态只能单向的转换，例如，线程只能从新建状态转换到就绪状态，反之则不能;双箭头表示两种状态可以互相转换，例如，就绪状态和运行状态可以互相转换。通过一张图还不能完全描述清楚线程各状态之间的区别，接下来针对线程生命周期中的五种状态分别进行详细讲解，具体如下



**1. 新建状态(New)**

创建一个线程对象后，该线程对象就处于新建状态，此时它不能运行，与其他Java对象一样，仅仅由Java虚拟机为其分配了内存，没有表现出任何线程的动态特征。

**2. 就绪状态(Runnable)**

当线程对象调用了start()方法后，该线程就进入就绪状态。处于就绪状态的线程位于线程队列中，此时它只是具备了运行的条件，能否获得CPU的使用权并开始运行，还需要等待系统的调度。

**3. 运行状态(Running)**

如果处于就绪状态的线程获得了CPU的使用权，并开始执行run()方法中的线程执行体，则该线程处于运行状态。一个线程启动后，它可能不会一直处于运行状态，当运行状态的线程使用完系统分配的时间后，系统就会剥夺该线程占用的CPU资源，让其他线程获得执行的机会。需要注意的是，只有处于就绪状态的线程才可能转换到运行状态。

**4.阻塞状态(Blocked)**

一个正在执行的线程在某些特殊情况下，如被人为挂起或执行耗时的输入/输出操作时，会让出CPU的使用权并暂时中止自己的执行，进人阻塞状态。线程进人阻塞状态后，就不能进入排队队列。只有当引起阻塞的原因被消除后，线程才可以转入就绪状态。

下面就列举一下线程由运行状态转换成阻塞状态的原因，以及如何从阻塞状态转换成就绪状态。

·当线程试图获取某个对象的同步锁时，如里该销被其他线程所持有，则当前线程会进入阻塞状态，如果想从阻塞状态进入就绪状态就必须获取到其他线程所持有的锁。

·当线程调用了一个阻塞式的I/O方法时，该线程就会进入阻寒状态，如果想进入就绪状态就必须要等到这个阻塞的I/O方法返回。

·当线程调用了某个对象的wait()方法时，也会使线程进入阻塞状态，如果想进入就绪状态就需要使用notify()方法唤醒该线程。

·当线程调用了Thread的sleep(long millis)方法时，也会使线程进入阻塞状态，在这种情况下，只需等到线程睡眠的时间到了后，线程就会自动进入就绪状态。

·当在一个线程中调用了另一个线程的join()方法时，会使当前线程进入阻塞状态，在这种情况下，需要等到新加入的线程运行结束后才会结束阻塞状态，进入就绪状态。

需要注意的是，线程从阻塞状态只能进入就绪状态，而不能直接进人运行状态，也就是说，结束阻塞的线程需要重新进入可运行池中，等待系统的调度。

**5.死亡状态(Terminated)**

如果线程调用stop()方法或nun()方法正常执行完毕，或者线程抛出一个未捕获的异常(Exception)错误(Error)，线程就进入死亡状态。一旦进入死亡状态，线程将不再拥有运行的资格，也不能再转换到其他状态。



#### 10.synchronized

![image-20220802205028112](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062313719.png)



![image-20220802205406368](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062313346.png)



```java
package com.momo.thread_.synchronized_;

/**
 * @author momo~
 * @version 1.0
 * 使用多线程,模拟三个窗口同时售票
 */
public class SaleThread01 {
    public static void main(String[] args) {
        Sale sale1 = new Sale();
        new Thread(sale1).start();
        new Thread(sale1).start();
        new Thread(sale1).start();
//        sale1.start();
//        sale2.start();
//        sale3.start();

    }
}
class Sale implements Runnable{
    private boolean loop = true;

    private static int count = 1000;

    //同一时刻,只能有一个线程操作
    public synchronized void syn(){
        if (count <= 0){
            System.out.println("票已售完");
            loop = false;
            return;
        }
        try {
            Thread.sleep(50);
        } catch (InterruptedException e) {
            throw new RuntimeException(e);
        }
        System.out.println("窗口" + Thread.currentThread().getName()
                + "剩余票数:" + (--count));
    }

    @Override
    public void run() {
        while (loop){
            syn();
        }
    }
}
```





#### 11.互斥锁

![image-20220802211855439](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062314641.png)



![image-20220802212314815](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062314081.png)



![image-20220802215756356](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062314941.png)



```java
package com.momo.thread_.synchronized_;

/**
 * @author momo~
 * @version 1.0
 * 使用多线程,模拟三个窗口同时售票
 */
public class SaleThread01 {
    public static void main(String[] args) {
        Sale sale1 = new Sale();
        new Thread(sale1).start();
        new Thread(sale1).start();
        new Thread(sale1).start();
//        sale1.start();
//        sale2.start();
//        sale3.start();

    }
}
class Sale implements Runnable{
    private boolean loop = true;

    private static int count = 100;

    //同一时刻,只能有一个线程操作

    //如果在静态方法中,实现一个同步代码块
    //synchronized 的锁加在
    public void syn(){
        synchronized (this) {
        //如果在静态方法中,实现一个同步代码块
        //synchronized 的锁加在类本身
//        synchronized (Sale.class){
            if (count <= 0) {
                System.out.println("票已售完");
                loop = false;
                return;
            }
            try {
                Thread.sleep(50);
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
            System.out.println("窗口" + Thread.currentThread().getName()
                    + "剩余票数:" + (--count));

        }
    }

    @Override
    public void run() {
        while (loop){
            syn();
        }
    }
}
```



#### 12.线程死锁

![image-20220803095140008](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062314715.png)



```java
package com.momo.thread_.synchronized_;

/**
 * @author momo~
 * @version 1.0
 */
public class DieThread {
    public static void main(String[] args) {
        //模拟死锁现象
        T3 A = new T3(true);
        T3 B = new T3(false);
        A.setName("A线程");
        B.setName("B线程");
        A.start();
        B.start();
    }
}
class T3 extends Thread{

    static Object o1 = new Object();
    static Object o2 = new Object();
    boolean flag;

    public T3(boolean flag){
        this.flag = flag;
    }

    @Override
    public void run() {
        //1.如果flag为T,线程A就会先得到/持有o1对象锁，然后尝试获取o2对象锁
        //2.如果线程A得不到o2对象锁，就会blocked
        //3.如果flag为F，线程B就会先得到/持有O2对象锁，然后尝试去获取o1对象锁
        //4.如果线程B得不到o1对象锁，就会blocked
        if (flag){
            synchronized (o1){
                System.out.println(Thread.currentThread().getName() + "进入1");
                synchronized (o2){
                    System.out.println(Thread.currentThread().getName() + "进入2");
                }
            }
        } else {
            synchronized (o2){
                System.out.println(Thread.currentThread().getName() + "进入3");
                synchronized (o1){
                    System.out.println(Thread.currentThread().getName() + "进入4");
                }
            }
        }
    }
}
```



#### 13.释放锁

![image-20220803102440874](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062314354.png)



![image-20220803103436769](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062314377.png)



**1.sleep()方法**

在指定时间内让当前正在执行的线程暂停执行，但不会释放“锁标志”。不推荐使用。

sleep()使当前线程进入阻塞状态，在指定时间内不会执行。

**2.wait()方法**

在其他线程调用对象的notify或notifyAll方法前，导致当前线程等待。线程会释放掉它所占有的“锁标志”，从而使别的线程有机会抢占该锁。

当前线程必须拥有当前对象锁。如果当前线程不是此锁的拥有者，会抛出IllegalMonitorStateException异常。

唤醒当前对象锁的等待线程使用notify或notifyAll方法，也必须拥有相同的对象锁，否则也会抛出IllegalMonitorStateException异常。

waite()和notify()必须在synchronized函数或synchronized　block中进行调用。如果在non-synchronized函数或non-synchronized　block中进行调用，虽然能编译通过，但在运行时会发生IllegalMonitorStateException的异常。

**3.yield方法**

暂停当前正在执行的线程对象。

yield()只是使当前线程重新回到可执行状态，所以执行yield()的线程有可能在进入到可执行状态后马上又被执行。

yield()只能使同优先级或更高优先级的线程有执行的机会。

**4.join方法**

等待该线程终止。

等待调用join方法的线程结束，再继续执行。如：t.join();//主要用于等待t线程运行结束，若无此句，main则会执行完毕，导致结果不可预测。

> join()底层就是调用wait()方法的，wait()释放锁资源，故join也释放锁资源
> 1.sleep会使当前线程睡眠指定时间，不释放锁
> 2.yield会使当前线程重回到可执行状态，等待cpu的调度，不释放锁
> 3.wait会使当前线程回到线程池中等待，释放锁，当被其他线程使用notify，notifyAll唤醒时进入可执行状态
> 4.当前线程调用 某线程.join（）时会使当前线程等待某线程执行完毕再结束，底层调用了wait，释放锁



#### 14.案例总结

![image-20220803103525742](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062314044.png)



```java
package com.momo.thread_;

import java.awt.event.KeyEvent;
import java.awt.event.KeyListener;
import java.util.Locale;
import java.util.Scanner;

/**
 * @author momo~
 * @version 1.0
 */
public class Homework01 {
    public static void main(String[] args) {
        A1 a1 = new A1();
        B1 b1 = new B1(a1);
        Thread thread1 = new Thread(a1);
        Thread thread2 = new Thread(b1);
        thread1.start();
        thread2.start();
    }
}
class A1 implements Runnable{

    boolean flag = true;

    @Override
    public void run() {
        while (flag){
            System.out.println((int)(Math.random() * 100 + 1));
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
        }
    }
    public void setFlag(boolean flag) {
        this.flag = flag;
    }
}
class B1 implements Runnable{

    private A1 a1;
    private Scanner scanner = new Scanner(System.in);

    public B1(A1 a1) {
        this.a1 = a1;
    }
    
    @Override
    public void run() {
        while (true){
            System.out.println("请输入q：");
            char c = scanner.next().toUpperCase().charAt(0);
            if (c == 'Q'){
                a1.setFlag(false);
                System.out.println("b1线程退出");
                break;
            }
        }
    }
}
```



![image-20220803111455236](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062314342.png)

```java
package com.momo.thread_;

import javax.jws.soap.SOAPBinding;

/**
 * @author momo~
 * @version 1.0
 */
public class Homework02 {
    public static void main(String[] args) {
        A3 a3 = new A3();
        Thread thread1 = new Thread(a3);
        thread1.start();
        Thread thread2 = new Thread(a3);
        thread2.start();
    }
}

class A3 implements Runnable {
    static int money = 10000;

    @Override
    public void run() {
        while (true) {
            synchronized (this) {
                if (money < 1000) {
                    System.out.println("A3余额不足");
                    break;
                }
                money -= 1000;
                System.out.println(Thread.currentThread().getName() + "取钱1000,剩余：" + money);
                try {
                    Thread.sleep(1000);
                } catch (InterruptedException e) {
                    throw new RuntimeException(e);
                }
            }
        }
    }
}
```

**涉及多个线程共享资源，优先使用Runnable接口创建线程。**



## 12.坦克大战0.3

![image-20220803124518441](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062315255.png)



## 13.坦克大战0.4

![image-20220803134632385](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062316232.png)





![image-20220803152713389](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062316511.png)



![image-20220803161005534](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062316011.png)





## 14.io流

### 1. 文件

![image-20220805174218448](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062359452.png)



![image-20220805174727174](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062316108.png)



**创建文件**

![image-20220805174917401](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062316044.png)



```java
package com.momo.file;

import org.junit.jupiter.api.Test;

import java.io.File;
import java.io.IOException;

/**
 * @author momo~
 * @version 1.0
 * 演示创建文件
 */
public class FileCreate {
    public static void main(String[] args) {
    }
    //方式1 根据路劲创建一个file对象
    @Test
    public void createFile01() throws IOException {
        String filePath = "D:\\news1.txt";
        File file = new File(filePath);

        file.createNewFile();
        System.out.println("创建成功");
    }

    //方式2 根据父目录文件 + 子路径构建
    @Test
    public void createFile02() throws IOException {
        File file = new File("D:\\");
        String fileName = "news2.txt";
        File file2 = new File(file, fileName);
        file2.createNewFile();
        System.out.println("创建成功");
    }

    //方式3 根据父目录 + 子路径构建
    @Test
    public void createFile03() throws IOException {
        String parentPath = "D:\\";
        String fileName = "news3.txt";
        File file = new File(parentPath, fileName);
        file.createNewFile();
        System.out.println("创建成功");
    }
}

```



**获取文件信息**

![image-20220805181827126](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062316283.png)

```java
package com.momo.file;

import org.junit.jupiter.api.Test;

import java.io.File;

/**
 * @author momo~
 * @version 1.0
 */
public class FileInformation {
    public static void main(String[] args) {

    }

    //获取文件信息
    @Test
    public void info(){
        //创建文件对象
        File file = new File("D:\\news1.txt");

        //调用相应方法得到相应信息
        System.out.println("文件名：" + file.getName());

        System.out.println("文件绝对路径：" + file.getAbsoluteFile());

        System.out.println("文件父目录：" + file.getParent());

        System.out.println("文件大小：" + file.length());

        System.out.println("文件是否存在：" + file.exists());

        System.out.println("是否是一个文件：" + file.isFile());

        System.out.println("是否是一个目录：" + file.isDirectory());
    }
}

```



### 2.目录

![image-20220805181946875](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062316286.png)



![image-20220805183553039](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062316041.png)



```java
package com.momo.directory;

import org.junit.jupiter.api.Test;

import java.io.File;
import java.io.IOException;

/**
 * @author momo~
 * @version 1.0
 */
public class Directory_ {
    public static void main(String[] args) {
    }
    @Test
    public void m1(){
        //判断文件是否存在，如果存在就删除
        String filePath = "D:\\news1.txt";
        File file = new File(filePath);
        if (file.exists()){
            if (file.delete()){
                System.out.println("删除成功");
            } else {
                System.out.println("删除失败");
            }
        } else {
            System.out.println("该文件不纯在");
        }
    }

    @Test
    public void m2(){
        //判断目录是否存在，如果存在就删除
        String directoryPath = "D:\\news2";
        File file = new File(directoryPath);
        if (file.exists()){
            if (file.delete()){
                System.out.println("删除成功");
            } else {
                System.out.println("删除失败");
            }
        } else {
            System.out.println("该目录不纯在");
        }
    }

    @Test
    public void m3() throws IOException {
        //判断目录是否存在，如果不存在就创建
        String directoryPath = "D:\\news2";
        File file = new File(directoryPath);
        if (file.exists()){  //创建一级目录，使用mkdir（），创建多级目录使用mkdirs（）
            System.out.println("该目录已经存在");
        } else {
            if (file.mkdirs()){
                System.out.println("创建成功");
            } else {
                System.out.println("创建失败");
            }
        }
    }
}

```



### 3.IO流

![image-20220805183840232](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062317125.png)



![image-20220805184012701](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062317869.png)



![image-20220805184325515](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062317565.png)





![image-20220806083041098](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062317559.png)



![image-20220806083252344](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062317067.png)



#### **1.FileInputStream**

| `int`            | `available()`返回从此输入流中可以读取（或跳过）的剩余字节数的估计值，而不会被下一次调用此输入流的方法阻塞。 |
| ---------------- | ------------------------------------------------------------ |
| `void`           | `close()`关闭此文件输入流并释放与流相关联的任何系统资源。    |
| `protected void` | `finalize()`确保当这个文件输入流的 `close`方法没有更多的引用时被调用。 |
| `FileChannel`    | `getChannel()`返回与此文件输入流相关联的唯一的[`FileChannel`](https://www.matools.com/file/manual/jdk_api_1.8_google/java/nio/channels/FileChannel.html)对象。 |
| `FileDescriptor` | `getFD()`返回表示与此 `FileInputStream`正在使用的文件系统中实际文件的连接的 `FileDescriptor`对象。 |
| `int`            | `read()`从该输入流读取一个字节的数据。                       |
| `int`            | `read(byte[] b)`从该输入流读取最多 `b.length`个字节的数据为字节数组。 |
| `int`            | `read(byte[] b, int off, int len)`从该输入流读取最多 `len`字节的数据为字节数组。 |
| `long`           | `skip(long n)`跳过并从输入流中丢弃 `n`字节的数据。           |

```java
package com.momo.inputstream;

import org.junit.jupiter.api.Test;

import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;

/**
 * @author momo~
 * @version 1.0
 * 演示FileInputStream的使用（字节输入流 文件——》程序（内存））
 */
public class FileInputStream_ {
    public static void main(String[] args) {

    }
    /**
      演示读取文件
      单个字节读取，效率较低
      ——》使用read(byte[] b)
     */
    @Test
    public void readFile01() throws IOException {
        String filePath = "D:\\hello.txt";
        int readData = 0;
        //创建FileInputStream对象，用于读取文件
        FileInputStream fileInputStream = new FileInputStream(filePath);

        //读取一个字节数据
        while ((readData = fileInputStream.read()) != -1){
            System.out.print((char) readData);
        }
        //关闭文件流，释放资源
        fileInputStream.close();
    }

    /**
     * 使用read(byte[] b)读取文件
     * @throws IOException
     */
    @Test
    public void readFile02() throws IOException {
        String filePath = "D:\\hello.txt";
        int readData = 0;
        //字节数组
        byte[] bytes = new byte[8];//一次读取八个字节

        //创建FileInputStream对象，用于读取文件
        FileInputStream fileInputStream = new FileInputStream(filePath);

        //读取一个字节数据
        while ((readData = fileInputStream.read(bytes)) != -1){
            System.out.print(new String(bytes,0,readData));
        }
        //关闭文件流，释放资源
        fileInputStream.close();
    }
}

```



#### **2.FileOutputStream**

![image-20220806090858263](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062317795.png)



| `void`           | `close()`关闭此文件输出流并释放与此流相关联的任何系统资源。  |
| ---------------- | ------------------------------------------------------------ |
| `protected void` | `finalize()`清理与文件的连接，并确保当没有更多的引用此流时，将调用此文件输出流的 `close`方法。 |
| `FileChannel`    | `getChannel()`返回与此文件输出流相关联的唯一的[`FileChannel`](https://www.matools.com/file/manual/jdk_api_1.8_google/java/nio/channels/FileChannel.html)对象。 |
| `FileDescriptor` | `getFD()`返回与此流相关联的文件描述符。                      |
| `void`           | `write(byte[] b)`将 `b.length`个字节从指定的字节数组写入此文件输出流。 |
| `void`           | `write(byte[] b, int off, int len)`将 `len`字节从位于偏移量 `off`的指定字节数组写入此文件输出流。 |
| `void`           | `write(int b)`将指定的字节写入此文件输出流。                 |



![image-20220806090954534](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062317065.png)



```java
package com.momo.outputstream;

import org.junit.jupiter.api.Test;

import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;

/**
 * @author momo~
 * @version 1.0
 */
public class FileOutPutStream_ {
    public static void main(String[] args) {

    }

    /**
     * 演示使用FileOutPutStream 将数据写入到文件中
     * 如果该文件不存在，则创建
     */
    @Test
    public void writeFile() throws IOException {
        String filePath = "D:\\a.txt";
        FileOutputStream fileOutputStream1 = null;
        try {
            //new FileOutputStream(filePath) 会覆盖原有数据
            //创建文件输出流以写入由指定的File对象表示的文件。
            // 如果第二个参数是true ，则字节将被写入文件的末尾而不是开头。
            fileOutputStream1 = new FileOutputStream(filePath,true);
            //写入一个字节
            fileOutputStream1.write('a');
            //写入一个字符串
            //str.getBytes() 将字符串转成字节数组
            String str = "hello,world";
            fileOutputStream1.write(str.getBytes());

            //写入一个字符串规定长度
            String str2 = "Hello,world";
            fileOutputStream1.write(str2.getBytes(),0,3);

        } catch (FileNotFoundException e) {
            throw new RuntimeException(e);
        } finally {
            try {
                fileOutputStream1.close();
            } catch (IOException e) {
                throw new RuntimeException(e);
            }
        }
    }
}
```



**文件拷贝**

```java
package com.momo.outputstream;

import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;

/**
 * @author momo~
 * @version 1.0
 */
public class FileCopy {
    public static void main(String[] args) throws IOException {
        //完成文件拷贝，将D:\\a.txt 拷贝至E盘
        //1.创建文件输入流，读取文件
        //2.创建文件输出流，写入文件
        String srcPath = "D:\\a.txt";
        String destPath = "E:\\a.txt";

        FileInputStream fileInputStream = null;
        FileOutputStream fileOutputStream = null;

        fileInputStream = new FileInputStream(srcPath);
        fileOutputStream = new FileOutputStream(destPath);

        //定义一个字节数组，提高读取效率
        byte[] bytes = new byte[8];
        int readLen = 0;
        while ((readLen = fileInputStream.read(bytes)) != -1){
            //读取后写入
            fileOutputStream.write(bytes,0, readLen);
        }
        System.out.println("拷贝成功");

        //关闭输入流和输出流
        if (fileInputStream != null){
            fileInputStream.close();
        }
        if (fileOutputStream != null){
            fileOutputStream.close();
        }

    }
}

```



#### 4.FileReader

![image-20220806095954490](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062317668.png)



![image-20220806095905334](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062317050.png)



```java
package com.momo.reader;

import org.junit.jupiter.api.Test;

import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;

/**
 * @author momo~
 * @version 1.0
 */
public class FileReader_ {
    public static void main(String[] args) throws IOException {

    }
    /**
     * 单个字符读取文件
     */
    @Test
    public void readFile01() throws IOException {
        String filePath = "D:\\story.txt";
        FileReader fileReader = null;
        int data = 0;
        //1.创建FileReader对象
        fileReader = new FileReader(filePath);
        //循环读取 单个字符读取
        while ((data = fileReader.read()) != -1){
            System.out.print((char) data);
        }
        if (fileReader != null){
            fileReader.close();
        }
    }

    /**
     * 字符数组读取文件
     * @throws IOException
     */
    @Test
    public void readFile02() throws IOException {
        String filePath = "D:\\story.txt";
        FileReader fileReader = null;
        int readLen = 0;
        char[] buf = new char[8];
        //1.创建FileReader对象
        fileReader = new FileReader(filePath);
        //循环读取 使用read(buf),返回的是实际读取的字符数
        //如果返回-1，说明到文件结束
        while ((readLen = fileReader.read(buf)) != -1){
            System.out.print(new String(buf,0,readLen));
        }
        if (fileReader != null){
            fileReader.close();
        }
    }
}
```



















#### 5.FileWriter

![image-20220806100150995](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062318017.png)



![image-20220806100451164](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062318249.png)



```java
package com.momo.writer_;

import java.io.FileWriter;
import java.io.IOException;

/**
 * @author momo~
 * @version 1.0
 */
public class FileWriter_ {
    public static void main(String[] args) throws IOException {
        //文件路径
        String filePath = "D:\\news.txt";
        //创建FileWriter对象
        FileWriter fileWriter = null;
        char[] chars = {'a','b','v'};
        fileWriter = new FileWriter(filePath);

        //write(int):写入单个字符
        fileWriter.write('H');
        //write(char[]):写入指定数组
        fileWriter.write(chars);
        //write(char[],off,len):写入指定数组的指定部分
        fileWriter.write("今天是星期几".toCharArray(),0,3);
        //write(string):写入整个字符串
        fileWriter.write(" 你好，北京");
        //write(string,off,len):写入字符串的指定部分
        fileWriter.write("上海天津",0,2);
        //在数据量大的情况下，可以循环操作
        //对于FileWriter，一定要关闭流close()或者刷新流flush()，才能写入内容
        fileWriter.close();
        System.out.println("程序结束");
    }
}
```



#### 6.节点流和处理流

![image-20220811073624674](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062318044.png)



![image-20220811073802019](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062318148.png)



![image-20220811074913621](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062318433.png)



![image-20220811082142588](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062318204.png)



#### **7.装饰器模式**

上班族大多都有睡懒觉的习惯，每天早上上班时间都很紧张，于是很多人为了多睡一会，就会用方便的方式解决早餐问题。有些人早餐可能会吃煎饼，煎饼中可以加鸡蛋，也可以加香肠，但是不管怎么“加码”，都还是一个煎饼。在现实生活中，常常需要对现有产品增加新的功能或美化其外观，如房子装修、相片加相框等，都是装饰器模式。

在软件开发过程中，有时想用一些现存的组件。这些组件可能只是完成了一些核心功能。但在不改变其结构的情况下，可以动态地扩展其功能。所有这些都可以釆用装饰器模式来实现。



**装饰器模式的定义与特点**
装饰器（Decorator）模式的定义：指在不改变现有对象结构的情况下，动态地给该对象增加一些职责（即增加其额外功能）的模式，它属于对象结构型模式。

装饰器是继承的有力补充，比继承灵活，在不改变原有对象的情况下，动态的给一个对象扩展功能，即插即用

通过使用不用装饰类及这些装饰类的排列组合，可以实现不同效果

装饰器模式完全遵守开闭原则

其主要缺点是：装饰器模式会增加许多子类，过度使用会增加程序得复杂性

 装饰器模式的结构与实现
通常情况下，扩展一个类的功能会使用继承方式来实现。但继承具有静态特征，耦合度高，并且随着扩展功能的增多，子类会很膨胀。如果使用组合关系来创建一个包装对象（即装饰对象）来包裹真实对象，并在保持真实对象的类结构不变的前提下，为其提供额外的功能，这就是装饰器模式的目标。下面来分析其基本结构和实现方法。

模式的结构
装饰器模式主要包含以下角色。

抽象构件（Component）角色：定义一个抽象接口以规范准备接收附加责任的对象。

具体构件（ConcreteComponent）角色：实现抽象构件，通过装饰角色为其添加一些职责。

抽象装饰（Decorator）角色：继承抽象构件，并包含具体构件的实例，可以通过其子类扩展具体构件的功能。

具体装饰（ConcreteDecorator）角色：实现抽象装饰的相关方法，并给具体构件对象添加附加的责任。



```java
public class DecoratorPattern {
    public static void main(String[] args) {
        Component p = new ConcreteComponent();
        p.operation();
        System.out.println("---------------------------------");
        Component d = new ConcreteDecorator(p);
        d.operation();
    }
}
//抽象构件角色
interface Component {
    public void operation();
}
//具体构件角色
class ConcreteComponent implements Component {
    public ConcreteComponent() {
        System.out.println("创建具体构件角色");
    }
    public void operation() {
        System.out.println("调用具体构件角色的方法operation()");
    }
}
//抽象装饰角色
class Decorator implements Component {
    private Component component;
    public Decorator(Component component) {
        this.component = component;
    }
    public void operation() {
        component.operation();
    }
}
//具体装饰角色
class ConcreteDecorator extends Decorator {
    public ConcreteDecorator(Component component) {
        super(component);
    }
    public void operation() {
        super.operation();
        addedFunction();
    }
    public void addedFunction() {
        System.out.println("为具体构件角色增加额外的功能addedFunction()");
    }
}
 
/*
程序运行结果如下：
创建具体构件角色
调用具体构件角色的方法operation()
---------------------------------
调用具体构件角色的方法operation()
为具体构件角色增加额外的功能addedFunction()*/
```



#### 8.处理流

##### **1. BufferedReader**

![image-20220811083301270](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062318388.png)



![image-20220811083547947](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062319816.png)



```java
package com.momo.reader;

import java.io.BufferedReader;
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;

/**
 * @author momo~
 * @version 1.0
 * 演示BufferedReader
 */
public class BufferedReader_ {
    public static void main(String[] args) throws IOException {
        String filePath = "D:\\story.txt";

        //创建bufferedReader
        BufferedReader bufferedReader = new BufferedReader(new FileReader(filePath));
        //读取
        String len;//按行读取，效率高
        //说明：
        //1.bufferedReader.readLine() 是按行读取文件
        //2.当返回null时，表示文件读取完毕
        while ((len = bufferedReader.readLine()) != null){
            System.out.println(len);
        }
        //关闭流，这里注意，只需要关闭BufferedReader，因为底层会自动关闭FileReader
        bufferedReader.close();
    }
}
```





##### **2. BufferedWriter**

```java
package com.momo.writer_;

import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

/**
 * @author momo~
 * @version 1.0
 * 演示BufferedWriter
 */
public class BufferedWriter_ {
    public static void main(String[] args) throws IOException {
        String filePath = "D:\\news.txt";
        //创建BufferedWriter
        BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(filePath,true));
        bufferedWriter.write("今天是星期几");
        bufferedWriter.newLine();//插入一个和系统相关的换行
        bufferedWriter.write("今天是星期几");
        bufferedWriter.write("今天是星期几");
        //关闭外层流即可
        bufferedWriter.close();
    }
}

```



**buffered拷贝**

![image-20220811090124218](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062319796.png)



```java
package com.momo.writer_;

import java.io.*;

/**
 * @author momo~
 * @version 1.0
 */
public class BufferedCopy {
    public static void main(String[] args) throws IOException {
        //1.BufferedReader 和 BufferedWriter 字符处理流
        //2.不要去操作二进制文件(音视频等)，可能造成文件损坏
        String srcFilePath = "D:\\news.txt";
        String desFilePath = "E:\\news.txt";

        String line;

        BufferedReader bufferedReader = new BufferedReader(new FileReader(srcFilePath));
        BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(desFilePath));

        while ((line = bufferedReader.readLine()) != null){
            bufferedWriter.write(line);
            bufferedWriter.newLine();//readLine()读取一行内容，但没有换行
        }

        bufferedReader.close();
        bufferedWriter.close();
    }
}
```



##### **3. 字节处理流**

![image-20220811092203687](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062319024.png)



![image-20220811092019640](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062319146.png)



![image-20220811092842196](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062319011.png)



**字节处理流拷贝文件**

```java
package com.momo.outputstream;

import java.io.*;

/**
 * @author momo~
 * @version 1.0
 * 演示使用BufferedOutputStream 和 BufferedInputStream 使用
 */
public class BufferedCopy02 {
    public static void main(String[] args) throws IOException {
        String srcFilePath = "D:\\001.png";
        String desFilePath = "E:\\001.png";

        byte[] buff = new byte[1024];
        int readLen = 0;

        BufferedInputStream bufferedInputStream = new BufferedInputStream(new FileInputStream(srcFilePath));
        BufferedOutputStream bufferedOutputStream = new BufferedOutputStream(new FileOutputStream(desFilePath));

        while ((readLen = bufferedInputStream.read(buff)) != -1){
            bufferedOutputStream.write(buff,0,readLen);
        }

        if (bufferedInputStream != null){
            bufferedInputStream.close();
        }

        if (bufferedOutputStream != null){
            bufferedOutputStream.close();
        }

    }
}
```



#### 9. 对象处理流

![image-20220811095730130](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062319721.png)



![image-20220811100152809](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062319029.png)



![image-20220811100553683](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062319005.png)



![image-20220811100358156](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062320828.png)



![image-20220811100515898](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062320971.png)



**序列化保存**

```java
package com.momo.outputstream;

import java.io.*;

/**
 * @author momo~
 * @version 1.0
 * 演示ObjectOutputStream的使用，完成数据的序列化
 */
public class ObjectOutputStream_ {
    public static void main(String[] args) throws IOException {
        String filePath = "D:\\a.txt";

        ObjectOutputStream objectOutputStream = new ObjectOutputStream(new FileOutputStream(filePath));
        objectOutputStream.writeInt(100);//int -> Integer 自动装箱，实现了Serializable序列化接口
        objectOutputStream.writeBoolean(true);//boolean -> Boolean 自动装箱，实现了Serializable序列化接口
        objectOutputStream.writeChar('a');//char -> Character 自动装箱，实现了Serializable序列化接口
        objectOutputStream.writeDouble(9.3);//double -> Double 自动装箱，实现了Serializable序列化接口
        objectOutputStream.writeUTF("今天是星期几");
        //保存一个dog对象
        objectOutputStream.writeObject(new Dog("小白",12));

        objectOutputStream.close();

        System.out.println("数据保存完毕（序列化形式）");

    }
}
class Dog implements Serializable{
    private String name;
    private int age;

    public Dog(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```



**反序列化读取**

```java
package com.momo.outputstream;

import javax.jws.soap.SOAPBinding;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.io.ObjectInputStream;

/**
 * @author momo~
 * @version 1.0
 * 演示ObjectInputStream的使用，完成数据的反序列化
 */
public class ObjectInputStream_ {
    public static void main(String[] args) throws IOException, ClassNotFoundException {
        String filePath = "D:\\a.txt";

        ObjectInputStream objectInputStream = new ObjectInputStream(new FileInputStream(filePath));

        System.out.println(objectInputStream.readInt());
        System.out.println(objectInputStream.readBoolean());
        System.out.println(objectInputStream.readChar());
        System.out.println(objectInputStream.readDouble());
        System.out.println(objectInputStream.readUTF());
        Object o = objectInputStream.readObject();
        System.out.println("运行类型：" + o.getClass());
        System.out.println(o);

        objectInputStream.close();
    }
}
```



![image-20220811121737885](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062320279.png)



#### 10. 标准输入输出流

![image-20220811122936954](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062320854.png)



```java
package com.momo.standard_;

import java.util.Scanner;

/**
 * @author momo~
 * @version 1.0
 */
public class InputAndOutput {
    public static void main(String[] args) {
        //public final static InputStream in = null;
        //System.in 编译类型 InputStream
        //System.in 运行类型 BufferedInputStream
        //表示标准输入 键盘
        System.out.println(System.in.getClass());

        //public final static PrintStream out = null;
        //System.out 编译类型 PrintStream
        //System.out 运行类型 PrintStream
        System.out.println(System.out.getClass());

        System.out.println("System.out 标准输出流");
        //System.in 标准输入流
        Scanner scanner = new Scanner(System.in);
    }
}
```





#### 11. 转换流

**InputStreamReader**

![image-20220811124323825](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062320718.png)



![image-20220811124732651](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062320276.png)



![image-20220811125954560](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062320434.png)



```JAVA
package com.momo.inputstream;

import sun.nio.cs.ext.GBK;

import java.io.*;
import java.nio.charset.StandardCharsets;

/**
 * @author momo~
 * @version 1.0
 * 演示使用InputStreamReader 转化流解决中文乱码问题
 */
public class InputStreamReader_ {
    public static void main(String[] args) throws IOException {
        String filePath = "D:\\a.txt";

        BufferedReader bufferedReader = new BufferedReader(
                new InputStreamReader(new FileInputStream(filePath), "UTF-8"));

        String s = bufferedReader.readLine();
        System.out.println(s);

        bufferedReader.close();

    }
}
```







**OutputStreamWriter**

![image-20220811124629938](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062320839.png)



![image-20220811131504686](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062320294.png)



```java
package com.momo.outputstream;

import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStreamWriter;

/**
 * @author momo~
 * @version 1.0
 * 演示OutputStreamWriter 使用
 * 把FileOutputStream 字节流抓换成 字符流 OutputStreamWriter
 * 指定处理的编码 gbk/utf-8
 */
public class OutputStreamWriter_ {
    public static void main(String[] args) throws IOException {
        String filePath = "D:\\b.txt";
        String charSet = "UTF-8";

        OutputStreamWriter outputStreamWriter = new OutputStreamWriter(new FileOutputStream(filePath),charSet);
        outputStreamWriter.write("hello world123");

        outputStreamWriter.close();
    }
}

```



#### 12. 打印流

![image-20220811133524720](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062320826.png)



##### 1. PrintStream

![image-20220811132416672](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062321663.png)



```java
package com.momo.Print_;

import java.io.IOException;
import java.io.PrintStream;

/**
 * @author momo~
 * @version 1.0
 * 演示字节打印流
 */
public class PrintStream_ {
    public static void main(String[] args) throws IOException {
        PrintStream out = System.out;
        //在默认情况下，PrintStream输出数据的位置是标准输出，即显示器
        out.print("john,hello");
        //因为底层使用的是write，所以我们可以直接调用write进行打印输出
        out.write("momo".getBytes());
        out.close();

        //修改打印流输出位置
        System.setOut(new PrintStream("D:\\c.txt"));
        System.out.println("hello world");
    }
}
```





##### 2. PrintWriter

![image-20220811132615162](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062325516.png)



```java
package com.momo.Print_;

import java.io.FileWriter;
import java.io.IOException;
import java.io.PrintWriter;

/**
 * @author momo~
 * @version 1.0
 * 演示PrintWriter使用方式
 */
public class PrintWriter_ {
    public static void main(String[] args) throws IOException {
        //PrintWriter printWriter = new PrintWriter(System.out);
        PrintWriter printWriter = new PrintWriter(new FileWriter("D:\\d.txt"));
        printWriter.print("hello world");
        printWriter.close();
    }
}
```



#### 13. properties

![image-20220811140616797](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062325417.png)



![image-20220811140855833](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062325498.png)



![image-20220811142638166](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062325812.png)



```java
package com.momo.properties_;

import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;
import java.util.Properties;

/**
 * @author momo~
 * @version 1.0
 */
public class Properties02 {
    public static void main(String[] args) throws IOException {
        //使用Properties类来读取mysql.properties文件

        //1.创建Properties对象
        Properties properties = new Properties();
        //2.加载指定配置文件
        properties.load(new FileReader("src\\mysql.properties"));
        //3.把k-v显示控制台
        properties.list(System.out);
        //4.根据键获取对应的值
        String user = properties.getProperty("user");
        String pwd = properties.getProperty("pwd");
        System.out.println("用户名=" + user);
        System.out.println("密码=" + pwd);
    }
}
```



```java
package com.momo.properties_;

import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;
import java.util.Properties;

/**
 * @author momo~
 * @version 1.0
 */
public class Properties03 {
    public static void main(String[] args) throws IOException {
        //使用properties类来创建配置文件，修改配置文件内容
        Properties properties = new Properties();

        //如果该文件没有对应key，就是创建
        //如果该文件有对应key，就是修改
        properties.setProperty("charSet","UTF-8");
        properties.setProperty("user","汤姆");
        properties.setProperty("pwd","888888");

        //将k-v存储到文件中
        properties.store(new FileOutputStream("src\\mysql2.properties"),null);
    }
}
```



#### 14.案例总结

![image-20220811143309351](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062325889.png)

```java
package com.momo;

import java.io.BufferedWriter;
import java.io.File;
import java.io.FileWriter;
import java.io.IOException;

/**
 * @author momo~
 * @version 1.0
 */
public class Homework01 {
    public static void main(String[] args) throws IOException {
        String directPath = "e:\\myTemp";
        String filePath = directPath + "\\hello.txt";

        File file1 = new File(directPath);
        if (file1.exists()){
            System.out.println("已经存在该文件夹");
        } else {
            if (file1.mkdirs()){
                System.out.println("文件夹创建成功");
            } else {
                System.out.println("文件夹创建失败");
            }
        }

        File file2 = new File(filePath);
        if (file2.exists()){
            System.out.println("已经存在该文件");
        } else {
            if (file2.createNewFile()){
                System.out.println("文件创建成功");
                BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(file2));
                bufferedWriter.write("今天是星期几");
                bufferedWriter.close();
            } else {
                System.out.println("文件创建失败");
            }
        }
        
    }
}
```



![image-20220811145125872](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062325984.png)

```java
package com.momo;

import java.io.*;

/**
 * @author momo~
 * @version 1.0
 */
public class Homework02 {
    public static void main(String[] args) throws IOException {
        String filePath = "D:\\story.txt";
        String line;
        int lineNum = 0;

        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(new FileInputStream(filePath),"UTF-8"));

        while ((line = bufferedReader.readLine()) != null){
            System.out.println(++lineNum + line);
        }

        if (bufferedReader != null){
            bufferedReader.close();
        }
    }
}
```



![image-20220811145749666](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062325517.png)

```java
package com.momo;

import org.junit.jupiter.api.Test;

import java.awt.*;
import java.io.*;
import java.util.Properties;

/**
 * @author momo~
 * @version 1.0
 */
public class Homework03 {
    public static void main(String[] args) throws IOException {
//        Properties properties = new Properties();
//        properties.setProperty("name","tom");
//        properties.setProperty("age","5");
//        properties.setProperty("color","red");
//
//        properties.store(new FileOutputStream("src\\dog.properties"),null);

        Properties properties = new Properties();
        properties.load(new FileReader("src\\dog.properties"));

        String name = properties.getProperty("name");
        int age = Integer.parseInt(properties.getProperty("age"));
        String color = properties.getProperty("color");

        Dog dog = new Dog(name, age, color);
        System.out.println(dog);

        //序列化
        String serFilePath = "D:\\f.txt";
        ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream(serFilePath));
        oos.writeObject(dog);

        oos.close();
        System.out.println("序列化完成");
    }

    //反序列化
    @Test
    public void  Serializable1() throws IOException, ClassNotFoundException {
        String serFilePath = "D:\\f.txt";
        ObjectInputStream ois = new ObjectInputStream(new FileInputStream(serFilePath));
        Dog dog = (Dog) ois.readObject();
        System.out.println(dog);
        ois.close();
    }
}
class Dog implements Serializable{
    private String name;
    private int age;
    private String color;

    public Dog(String name, int age, String color) {
        this.name = name;
        this.age = age;
        this.color = color;
    }
    
    @Override
    public String toString() {
        return "Dog{" +
                "name='" + name + '\'' +
                ", age=" + age +
                ", color='" + color + '\'' +
                '}';
    }
}
```



## 15. 坦克大战0.5

![image-20220811155450445](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062325914.png)



![image-20220811161417967](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062325106.png)



![image-20220811191452792](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062325992.png)



代码如下：

Bomb类：

```java
package com.momo.tankgame5;

/**
 * @author momo~
 * @version 1.0
 */
public class Bomb {
    int x, y; //炸弹
    int life = 9; //炸弹的生命周期
    boolean isLive = true;

    public Bomb(int x, int y) {
        this.x = x;
        this.y = y;
    }

    //减少生命值
    public void lifeDown(){
        if (life > 0){
            life--;
        } else {
            isLive = false;
        }
    }
}

```



EnemyTabk类：

```java
package com.momo.tankgame5;

import java.awt.*;
import java.util.Vector;

/**
 * @author momo~
 * @version 3.0
 * 敌人的坦克
 */
public class EnemyTank extends Tank implements Runnable {
    //敌人坦克使用Vector保存，为了线程安全
    Vector<Shot> shots = new Vector<Shot>();

    //增加成员，EnemyTank可以得到敌人坦克的Vector
    Vector<EnemyTank> enemyTanks = new Vector<>();

    boolean isLive = true;

    public EnemyTank(int x, int y) {
        super(x, y);
    }

    //提供一个方法，可以将MyPanel的成员Vector<EnemyTank> enemyTanks = new Vector<>()
    //设置到EnemyTank的成员enemyTanks
    public void setEnemyTanks(Vector<EnemyTank> enemyTanks) {
        this.enemyTanks = enemyTanks;
    }

    //编写方法，判断当前这个敌人坦克是否和其他坦克发生碰撞
    public boolean isTouchEnemy() {
        //判断当前敌人坦克
        switch (this.getDirect()) { //上右下左
            case 0:
                //让当前敌人坦克和其他所有其他坦克比较
                for (int i = 0; i < enemyTanks.size(); i++) {
                    //从vector中取出一个敌人坦克
                    EnemyTank enemyTank = enemyTanks.get(i);
                    //不和自己比较
                    if (enemyTank != this) {
                        //如果敌人坦克是上下
                        //1.如果敌人坦克是上下，x的范围[enemyTank.getX(),enemyTank.getX()+40]
                        //                  y的范围[enemyTank.getY(),enemyTank.getY()+60]
                        if (enemyTank.getDirect() == 0 || enemyTank.getDirect() == 2) {
                            //2.当前坦克左上角的坐标[this.getX(),this.getY()]
                            if (this.getX() >= enemyTank.getX() && this.getX() <= enemyTank.getX() + 40
                                    && this.getY() >= enemyTank.getY() && this.getY() <= enemyTank.getY() + 60) {
                                return true;
                            }
                            //3.当前坦克左上角的坐标[this.getX() + 40,this.getY()]
                            if (this.getX() + 40 >= enemyTank.getX() && this.getX() + 40 <= enemyTank.getX() + 40
                                    && this.getY() >= enemyTank.getY() && this.getY() <= enemyTank.getY() + 60) {
                                return true;
                            }
                        }
                        //如果敌人坦克是左右
                        //1.如果敌人坦克是左右，x的范围[enemyTank.getX(),enemyTank.getX() + 60]
                        //                  y的范围[enemyTank.getY(),enemyTank.getY() + 40]
                        if (enemyTank.getDirect() == 1 || enemyTank.getDirect() == 3) {
                            //2.当前坦克左上角的坐标[this.getX(),this.getY()]
                            if (this.getX() >= enemyTank.getX() && this.getX() <= enemyTank.getX() + 60
                                    && this.getY() >= enemyTank.getY() && this.getY() <= enemyTank.getY() + 40) {
                                return true;
                            }
                            //3.当前坦克左上角的坐标[this.getX() + 40,this.getY()]
                            if (this.getX() + 40 >= enemyTank.getX() && this.getX() + 40 <= enemyTank.getX() + 60
                                    && this.getY() >= enemyTank.getY() && this.getY() <= enemyTank.getY() + 40) {
                                return true;
                            }
                        }
                    }
                }
                break;
            case 1:
                //让当前敌人坦克和其他所有其他坦克比较
                for (int i = 0; i < enemyTanks.size(); i++) {
                    //从vector中取出一个敌人坦克
                    EnemyTank enemyTank = enemyTanks.get(i);
                    //不和自己比较
                    if (enemyTank != this) {
                        //如果敌人坦克是上下
                        //1.如果敌人坦克是上下，x的范围[enemyTank.getX(),enemyTank.getX()+40]
                        //                  y的范围[enemyTank.getY(),enemyTank.getY()+60]
                        if (enemyTank.getDirect() == 0 || enemyTank.getDirect() == 2) {
                            //2.当前坦克右上角的坐标[this.getX() + 60,this.getY()]
                            if (this.getX() + 60 >= enemyTank.getX() && this.getX() + 60 <= enemyTank.getX() + 40
                                    && this.getY() >= enemyTank.getY() && this.getY() <= enemyTank.getY() + 60) {
                                return true;
                            }
                            //3.当前坦克右下角的坐标[this.getX() + 60,this.getY() + 40]
                            if (this.getX() + 60 >= enemyTank.getX() && this.getX() + 60 <= enemyTank.getX() + 40
                                    && this.getY() + 40 >= enemyTank.getY() && this.getY() + 40 <= enemyTank.getY() + 60) {
                                return true;
                            }
                        }
                        //如果敌人坦克是左右
                        //1.如果敌人坦克是左右，x的范围[enemyTank.getX(),enemyTank.getX() + 60]
                        //                  y的范围[enemyTank.getY(),enemyTank.getY() + 40]
                        if (enemyTank.getDirect() == 1 || enemyTank.getDirect() == 3) {
                            //2.当前坦克右上角的坐标[this.getX() + 60,this.getY()]
                            if (this.getX() + 60 >= enemyTank.getX() && this.getX() + 60 <= enemyTank.getX() + 60
                                    && this.getY() >= enemyTank.getY() && this.getY() <= enemyTank.getY() + 40) {
                                return true;
                            }
                            //3.当前坦克右下角的坐标[this.getX() + 60,this.getY() + 40]
                            if (this.getX() + 60 >= enemyTank.getX() && this.getX() + 60 <= enemyTank.getX() + 60
                                    && this.getY() + 40 >= enemyTank.getY() && this.getY() + 40 <= enemyTank.getY() + 40) {
                                return true;
                            }
                        }
                    }
                }
                break;
            case 2:
                //让当前敌人坦克和其他所有其他坦克比较
                for (int i = 0; i < enemyTanks.size(); i++) {
                    //从vector中取出一个敌人坦克
                    EnemyTank enemyTank = enemyTanks.get(i);
                    //不和自己比较
                    if (enemyTank != this) {
                        //如果敌人坦克是上下
                        //1.如果敌人坦克是上下，x的范围[enemyTank.getX(),enemyTank.getX()+40]
                        //                  y的范围[enemyTank.getY(),enemyTank.getY()+60]
                        if (enemyTank.getDirect() == 0 || enemyTank.getDirect() == 2) {
                            //2.当前坦克左下角的坐标[this.getX(),this.getY() + 60]
                            if (this.getX() >= enemyTank.getX() && this.getX() <= enemyTank.getX() + 40
                                    && this.getY() + 60 >= enemyTank.getY() && this.getY() + 60 <= enemyTank.getY() + 60) {
                                return true;
                            }
                            //3.当前坦克右下角的坐标[this.getX() + 40,this.getY() + 60]
                            if (this.getX() + 40 >= enemyTank.getX() && this.getX() + 40 <= enemyTank.getX() + 40
                                    && this.getY() + 60 >= enemyTank.getY() && this.getY() + 60 <= enemyTank.getY() + 60) {
                                return true;
                            }
                        }
                        //如果敌人坦克是左右
                        //1.如果敌人坦克是左右，x的范围[enemyTank.getX(),enemyTank.getX() + 60]
                        //                  y的范围[enemyTank.getY(),enemyTank.getY() + 40]
                        if (enemyTank.getDirect() == 1 || enemyTank.getDirect() == 3) {
                            //2.当前坦克左下角的坐标[this.getX(),this.getY() + 60]
                            if (this.getX() >= enemyTank.getX() && this.getX() <= enemyTank.getX() + 60
                                    && this.getY() + 60 >= enemyTank.getY() && this.getY() + 60 <= enemyTank.getY() + 40) {
                                return true;
                            }
                            //3.当前坦克右下角的坐标[this.getX() + 40,this.getY() + 60]
                            if (this.getX() + 40 >= enemyTank.getX() && this.getX() + 40 <= enemyTank.getX() + 60
                                    && this.getY() + 60 >= enemyTank.getY() && this.getY() + 60 <= enemyTank.getY() + 40) {
                                return true;
                            }
                        }
                    }
                }
                break;
            case 3:
                //让当前敌人坦克和其他所有其他坦克比较
                for (int i = 0; i < enemyTanks.size(); i++) {
                    //从vector中取出一个敌人坦克
                    EnemyTank enemyTank = enemyTanks.get(i);
                    //不和自己比较
                    if (enemyTank != this) {
                        //如果敌人坦克是上下
                        //1.如果敌人坦克是上下，x的范围[enemyTank.getX(),enemyTank.getX()+40]
                        //                  y的范围[enemyTank.getY(),enemyTank.getY()+60]
                        if (enemyTank.getDirect() == 0 || enemyTank.getDirect() == 2) {
                            //2.当前坦克左上角的坐标[this.getX(),this.getY()]
                            if (this.getX() >= enemyTank.getX() && this.getX() <= enemyTank.getX() + 40
                                    && this.getY() >= enemyTank.getY() && this.getY() <= enemyTank.getY() + 60) {
                                return true;
                            }
                            //3.当前坦克左下角的坐标[this.getX(),this.getY() + 40]
                            if (this.getX() >= enemyTank.getX() && this.getX() <= enemyTank.getX() + 40
                                    && this.getY() + 40 >= enemyTank.getY() && this.getY() + 40 <= enemyTank.getY() + 60) {
                                return true;
                            }
                        }
                        //如果敌人坦克是左右
                        //1.如果敌人坦克是左右，x的范围[enemyTank.getX(),enemyTank.getX() + 60]
                        //                  y的范围[enemyTank.getY(),enemyTank.getY() + 40]
                        if (enemyTank.getDirect() == 1 || enemyTank.getDirect() == 3) {
                            //2.当前坦克左上角的坐标[this.getX(),this.getY()]
                            if (this.getX() >= enemyTank.getX() && this.getX() <= enemyTank.getX() + 60
                                    && this.getY() >= enemyTank.getY() && this.getY() <= enemyTank.getY() + 40) {
                                return true;
                            }
                            //3.当前坦克左下角的坐标[this.getX(),this.getY() + 40]
                            if (this.getX() >= enemyTank.getX() && this.getX() <= enemyTank.getX() + 60
                                    && this.getY() + 40 >= enemyTank.getY() && this.getY() + 40 <= enemyTank.getY() + 40) {
                                return true;
                            }
                        }
                    }
                }
                break;
        }
        return false;
    }
    @Override
    public void run() {
        while (true) {

            //我们判断如果shots size（）= 0
            if (isLive && shots.size() == 0) {
                //判断坦克方向，创建对应子弹
                Shot s = null;
                switch (getDirect()) {
                    case 0:
                        s = new Shot(getX() + 20, getY(), 0);
                        break;
                    case 1:
                        s = new Shot(getX() + 60, getY() + 20, 1);
                        break;
                    case 2:
                        s = new Shot(getX() + 20, getY() + 60, 2);
                        break;
                    case 3:
                        s = new Shot(getX(), getY() + 20, 3);
                        break;
                }
                shots.add(s);
                new Thread(s).start();
            }

            //根据坦克方向继续移动
            switch (getDirect()) {
                case 0:
                    //让坦克保持一个方向走30步
                    for (int i = 0; i < 30; i++) {
                        if (getY() > 0 && !isTouchEnemy()) {
                            moveUp();
                        }
                        //休眠50ms
                        try {
                            Thread.sleep(50);
                        } catch (InterruptedException e) {
                            throw new RuntimeException(e);
                        }
                    }
                    break;
                case 1:
                    //让坦克保持一个方向走30步
                    for (int i = 0; i < 30; i++) {
                        if (getX() + 60 < 1000 && !isTouchEnemy()) {
                            moveRight();
                        }
                        //休眠50ms
                        try {
                            Thread.sleep(50);
                        } catch (InterruptedException e) {
                            throw new RuntimeException(e);
                        }
                    }
                    break;
                case 2:
                    //让坦克保持一个方向走30步
                    for (int i = 0; i < 30; i++) {
                        if (getY() + 60 < 750 && !isTouchEnemy()) {
                            moveDown();
                        }
                        //休眠50ms
                        try {
                            Thread.sleep(50);
                        } catch (InterruptedException e) {
                            throw new RuntimeException(e);
                        }
                    }
                    break;
                case 3:
                    //让坦克保持一个方向走30步
                    for (int i = 0; i < 30; i++) {
                        if (getX() > 0 && !isTouchEnemy()) {
                            moveLeft();
                        }
                        //休眠50ms
                        try {
                            Thread.sleep(50);
                        } catch (InterruptedException e) {
                            throw new RuntimeException(e);
                        }
                    }
                    break;
            }
            //随机改变坦克方向
            setDirect((int) (Math.random() * 4));
            //多线程并发一定要考虑什么时候结束
            if (!isLive) {
                break;
            }
        }
    }
}

```



Hero类：

```java
package com.momo.tankgame5;

import java.util.Vector;

/**
 * @author momo~
 * @version 3.0
 *
 */
public class Hero extends Tank {
    //定义一个Shot对象,表示一个射击（线程）
    Shot shot = null;
    //可以发射多颗子弹
    Vector<Shot> shots = new Vector<>();

    public Hero(int x, int y) {
        super(x, y);
    }

    //射击
    public void shotEnemyTank(){
        //控制最多5颗子弹
        if (shots.size() == 5){
            return;
        }

        //创建Shot对象，根据当前Hero对象的位置创建Shot对象
        switch (getDirect()){//得到Hero对象的方向
            case 0: //上
                shot = new Shot(getX() + 20,getY(),0);
                break;
            case 1: //右
                shot = new Shot(getX() + 60,getY() + 20,1);
                break;
            case 2: //下
                shot = new Shot(getX() + 20,getY() + 60,2);
                break;
            case 3: //左
                shot = new Shot(getX(),getY() + 20,3);
                break;
        }
        //把新创建的shot放入shots
        shots.add(shot);
        //启动射击线程
        new Thread(shot).start();
    }
}

```



HspTankGame05类：

```java
package com.momo.tankgame5;

import javax.swing.*;
import java.awt.event.WindowAdapter;
import java.awt.event.WindowEvent;
import java.io.IOException;
import java.util.Scanner;

/**
 * @author momo~
 * @version 3.0
 */
public class HspTankGame05 extends JFrame {
    //定义MyPanel
    MyPanel mp = null;
    static Scanner scanner = new Scanner(System.in);


    public static void main(String[] args) {

        new HspTankGame05();
    }

    public HspTankGame05(){
        System.out.println("请输入选择 1：新游戏 2：继续");
        String next = scanner.next();
        mp = new MyPanel(next);
        //将mp放入Thread，启动
        Thread thread = new Thread(mp);
        thread.start();
        this.add(mp);
        this.setSize(1300,950);
        this.addKeyListener(mp);//监听
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        this.setVisible(true);

        //在JFrame中增加响应关闭窗口的处理
        this.addWindowListener(new WindowAdapter() {
            @Override
            public void windowClosing(WindowEvent e) {
//                System.out.println("监听到关闭窗口");
                try {
                    Recorder.keepRecord();
                } catch (IOException ex) {
                    throw new RuntimeException(ex);
                }
                System.exit(0);
            }
        });
    }
}

```



MyPanel类：

```java
package com.momo.tankgame5;

import javax.swing.*;
import java.awt.*;
import java.awt.event.KeyEvent;
import java.awt.event.KeyListener;
import java.io.IOException;
import java.util.Vector;

/**
 * @author momo~
 * @version 1.0
 * 坦克大战绘图区域
 */
//为了监听键盘事件,实现KeyListener
//为了让Panel不停的重绘子弹，需要将MyPanel实现Runnable，当作一个线程使用
public class MyPanel extends JPanel implements KeyListener, Runnable {
    //定义我的坦克
    Hero hero = null;
    //定义敌人的坦克,放入Vector
    Vector<EnemyTank> enemyTanks = new Vector<>();

    //定义一个存放Node对象的Vector，用于恢复敌人坦克的数据
    Vector<Node> nodes = new Vector<>();

    //定义一个Vector,用于存放炸弹
    //说明，当子弹击中坦克时，放入一个Bomb对象到bombs
    Vector<Bomb> bombs = new Vector<>();
    int enemyTankSize = 3;

    //定义三张图片。用于显示爆炸效果
    Image image1 = null;
    Image image2 = null;
    Image image3 = null;

    public MyPanel(String key) {
        try {
            nodes = Recorder.getNodesAndAllEnemyTankNum();
        } catch (IOException e) {
            throw new RuntimeException(e);
        }
        //将MyPanel对象的enemyTank设置给Recorder的enemyTanks
        Recorder.setEnemyTanks(enemyTanks);
        //初始化自己坦克
        hero = new Hero(500, 100);
        hero.setSpeed(5);

        switch (key){
            case "1":
                //初始化敌人坦克
                for (int i = 0; i < enemyTankSize; i++) {
                    EnemyTank enemyTank = new EnemyTank((100 * (i + 1)), 0);
                    enemyTank.setDirect(2);

                    //将enemyTanks设置给enemyTank
                    enemyTank.setEnemyTanks(enemyTanks);

                    //启动敌人坦克线程，让他动起来
                    new Thread(enemyTank).start();

                    //给该enemyTank 加入一颗子弹
                    Shot shot = new Shot(enemyTank.getX() + 20, enemyTank.getY() + 60, enemyTank.getDirect());
                    //加入到enemyTank的Vector集合
                    enemyTank.shots.add(shot);
                    //启动线程 shot
                    new Thread(shot).start();
                    enemyTanks.add(enemyTank);
                }
                break;
            case "2": //继续游戏
                //初始化敌人坦克
                for (int i = 0; i < nodes.size(); i++) {
                    Node node = nodes.get(i);

                    EnemyTank enemyTank = new EnemyTank(node.getX(), node.getY());
                    enemyTank.setDirect(node.getDirect());

                    //将enemyTanks设置给enemyTank
                    enemyTank.setEnemyTanks(enemyTanks);

                    //启动敌人坦克线程，让他动起来
                    new Thread(enemyTank).start();

                    //给该enemyTank 加入一颗子弹
                    Shot shot = new Shot(enemyTank.getX() + 20, enemyTank.getY() + 60, enemyTank.getDirect());
                    //加入到enemyTank的Vector集合
                    enemyTank.shots.add(shot);
                    //启动线程 shot
                    new Thread(shot).start();
                    enemyTanks.add(enemyTank);
                }
                break;
            default:
                System.out.println("输入有误");
        }


        //初始化图片对象
        image1 = Toolkit.getDefaultToolkit().getImage(Panel.class.getResource("/img_1.png"));
        image2 = Toolkit.getDefaultToolkit().getImage(Panel.class.getResource("/img_2.png"));
        image3 = Toolkit.getDefaultToolkit().getImage(Panel.class.getResource("/img_3.png"));

        //这里播放音乐
        new PlayAudio("src\\music.mp3").start();
    }

    //编写方法显示我方击毁敌方坦克信息
    public void showInfo(Graphics g){

        //画出玩家的总成绩
        g.setColor(Color.BLACK);
        Font font = new Font("宋体",Font.BOLD,25);
        g.setFont(font);

        g.drawString("您累计击毁敌方坦克",1020,30);
        drawTank(1020,60,g,0,0);//敌方坦克
        g.setColor(Color.BLACK);
        g.drawString(Recorder.getAllEnemyTankNum() + "",1080,100);

    }

    @Override
    public void paint(Graphics g) {
        super.paint(g);
        g.fillRect(0, 0, 1000, 750);//填充矩形,默认黑色

        showInfo(g);

        //画出自己坦克
        if (hero != null && hero.isLive){
            drawTank(hero.getX(), hero.getY(), g, hero.getDirect(), 0);
        }
        //画出子弹
//        if (hero.shot != null && hero.shot.isLive == true){
//            g.draw3DRect(hero.shot.x,hero.shot.y,2,2,false);
//        }

        //将hero子弹集合shots遍历取回
        for (int i = 0; i < hero.shots.size(); i++) {
            Shot shot = hero.shots.get(i);
            if (shot != null && shot.isLive == true) {
                g.draw3DRect(shot.x, shot.y, 2, 2, false);
            } else {
                //如果该shot对象已经无效，就从shots集合中拿掉
                hero.shots.remove(shot);
            }
        }

        //如果集合中有炸弹
        for (int i = 0; i < bombs.size(); i++) {
            //取出炸弹
            Bomb bomb = bombs.get(i);
            //根据当前bomb对象的life值画出对应图片
            if (bomb.life > 6) {
                g.drawImage(image1, bomb.x, bomb.y, 60, 60, this);
            } else if (bomb.life > 3) {
                g.drawImage(image2, bomb.x, bomb.y, 60, 60, this);
            } else {
                g.drawImage(image3, bomb.x, bomb.y, 60, 60, this);
            }
            //让炸弹生命值减少
            bomb.lifeDown();
            //如果bomb life为0，就从bombs集合中删除
            if (bomb.life == 0) {
                bombs.remove(bomb);
            }
        }

        //画出敌人的坦克
        for (int i = 0; i < enemyTanks.size(); i++) {
            EnemyTank enemyTank = enemyTanks.get(i);
            //判断当前坦克是否存活
            if (enemyTank.isLive) {//当敌人坦克存活才绘画
                drawTank(enemyTank.getX(), enemyTank.getY(), g, enemyTank.getDirect(), 1);
                //画出所有子弹
                for (int j = 0; j < enemyTank.shots.size(); j++) {
                    //取出子弹
                    Shot shot = enemyTank.shots.get(j);
                    //绘制
                    if (shot.isLive) {//isLive == true
                        g.draw3DRect(shot.x, shot.y, 1, 1, false);
                    } else {
                        enemyTank.shots.remove(shot);
                    }
                }
            }
        }
    }
    //编写坦克

    /**
     * @param x      坦克左上角x坐标
     * @param y      坦克左上角y坐标
     * @param g      画笔
     * @param direct 坦克方向
     * @param type   坦克类型
     */
    public void drawTank(int x, int y, Graphics g, int direct, int type) {
        //根据不同的坦克设置不同的颜色
        switch (type) {
            case 0: //我们的坦克
                g.setColor(Color.CYAN);
                break;
            case 1: //敌人的坦克
                g.setColor(Color.YELLOW);
                break;
        }
        //根据坦克方向,绘制不同坦克
        //direct表示方向(0 1 2 3)(上右下)
        switch (direct) {
            case 0: //表示向上
                g.fill3DRect(x, y, 10, 60, false);//坦克左边轮子
                g.fill3DRect(x + 30, y, 10, 60, false);//坦克右边轮子
                g.fill3DRect(x + 10, y + 10, 20, 40, false);//坦克中间盖子
                g.fillOval(x + 10, y + 20, 20, 20);//坦克中间圆形 盖子
                g.drawLine(x + 20, y + 30, x + 20, y);
                break;
            case 1://表示向右
                g.fill3DRect(x, y, 60, 10, false);//坦克上边轮子
                g.fill3DRect(x, y + 30, 60, 10, false);//坦克下边轮子
                g.fill3DRect(x + 10, y + 10, 40, 20, false);//坦克中间盖子
                g.fillOval(x + 20, y + 10, 20, 20);//坦克中间圆形 盖子
                g.drawLine(x + 30, y + 20, x + 60, y + 20);
                break;
            case 2: //表示向下
                g.fill3DRect(x, y, 10, 60, false);//坦克左边轮子
                g.fill3DRect(x + 30, y, 10, 60, false);//坦克右边轮子
                g.fill3DRect(x + 10, y + 10, 20, 40, false);//坦克中间盖子
                g.fillOval(x + 10, y + 20, 20, 20);//坦克中间圆形 盖子
                g.drawLine(x + 20, y + 30, x + 20, y + 60);
                break;
            case 3://表示向左
                g.fill3DRect(x, y, 60, 10, false);//坦克上边轮子
                g.fill3DRect(x, y + 30, 60, 10, false);//坦克下边轮子
                g.fill3DRect(x + 10, y + 10, 40, 20, false);//坦克中间盖子
                g.fillOval(x + 20, y + 10, 20, 20);//坦克中间圆形 盖子
                g.drawLine(x + 30, y + 20, x, y + 20);
                break;
        }
    }

    //如果我们的可以发射多颗子弹
    //在判断我方子弹是否击中敌人坦克时，就需要把我们的子弹集合
    //中所有的子弹，都取出和敌人的所有坦克进行判断

    public void hitEnemyTank() {
        //遍历我们的子弹
        for (int j = 0; j < hero.shots.size(); j++) {
            Shot shot = hero.shots.get(j);

            //判断子弹是否击中敌人坦克
            if (shot != null && shot.isLive) {//子弹存活
                //遍历敌人所有坦克
                for (int i = 0; i < enemyTanks.size(); i++) {
                    EnemyTank enemyTank = enemyTanks.get(i);
                    hitTank(shot, enemyTank);
                }
            }
        }
    }

    //编写方法，判断敌人坦克是否击中我方坦克
    public void hitHero(){
        //遍历所有的敌人坦克
        for (int i = 0; i < enemyTanks.size(); i++) {
            //取出敌人坦克
            EnemyTank enemyTank = enemyTanks.get(i);
            //遍历enemyTank对象所有子弹
            for (int j = 0; j < enemyTank.shots.size(); j++) {
                //取出子弹
                Shot shot = enemyTank.shots.get(j);
                //判断shot是否击中我方坦克
                if (hero.isLive && shot.isLive){
                    hitTank(shot,hero);
                }
            }
        }
    }




    //编写方法，判断我方坦克子弹是否击中敌人坦克
    public void hitTank(Shot shot, Tank enemyTank) {
        //判断s击中e
        switch (enemyTank.getDirect()) {
            case 0: //上
            case 2: //下
                if (shot.x > enemyTank.getX() && shot.x < enemyTank.getX() + 40
                        && shot.y > enemyTank.getY() && shot.y < enemyTank.getY() + 60) {
                    shot.isLive = false;
                    enemyTank.isLive = false;
                    //当我的子弹击中敌人坦克后，将enemyTank从集合中拿掉
                    enemyTanks.remove(enemyTank);
                    //当我方击毁一个敌人坦克时，就对数据allEnemyTankNum++
                    if (enemyTank instanceof EnemyTank){
                        Recorder.addAllEnemyTankNum();
                    }
                    //创建Bomb对象，加入bombs集合
                    Bomb bomb = new Bomb(enemyTank.getX(), enemyTank.getY());
                    bombs.add(bomb);
                }
                break;
            case 1: //右
            case 3: //左
                if (shot.x > enemyTank.getX() && shot.x < enemyTank.getX() + 60
                        && shot.y > enemyTank.getY() && shot.y < enemyTank.getY() + 40) {
                    shot.isLive = false;
                    enemyTank.isLive = false;
                    //当我的子弹击中敌人坦克后，将enemyTank从集合中拿掉
                    enemyTanks.remove(enemyTank);
                    //当我方击毁一个敌人坦克时，就对数据allEnemyTankNum++
                    if (enemyTank instanceof EnemyTank){
                        Recorder.addAllEnemyTankNum();
                    }
                    //创建Bomb对象，加入bombs集合
                    Bomb bomb = new Bomb(enemyTank.getX(), enemyTank.getY());
                    bombs.add(bomb);
                }
                break;
        }
    }

    @Override
    public void keyTyped(KeyEvent e) {

    }

    //处理wasd按下的情况
    @Override
    public void keyPressed(KeyEvent e) {
        if (e.getKeyCode() == KeyEvent.VK_W) {
            //改变坦克方向
            hero.setDirect(0);
            //修改坐标
            if (hero.getY() > 0) {
                hero.moveUp();
            }
        } else if (e.getKeyCode() == KeyEvent.VK_D) {
            hero.setDirect(1);
            if (hero.getX() + 60 < 1000) {
                hero.moveRight();
            }
        } else if (e.getKeyCode() == KeyEvent.VK_S) {
            hero.setDirect(2);
            if (hero.getY() + 60 < 750) {
                hero.moveDown();
            }
        } else if (e.getKeyCode() == KeyEvent.VK_A) {
            hero.setDirect(3);
            if (hero.getX() > 0) {
                hero.moveLeft();
            }
        }


        //用户按下J键发射子弹
        if (e.getKeyCode() == KeyEvent.VK_J) {
            //判断hero的子弹是否销毁
//            if (hero.shot == null || !hero.shot.isLive){
//                hero.shotEnemyTank();
//            }
            //发射多颗子弹
            hero.shotEnemyTank();

        }
        //重绘
        this.repaint();
    }

    @Override
    public void keyReleased(KeyEvent e) {

    }

    @Override
    public void run() {//每隔一百毫秒，重绘区域
        while (true) {
            try {
                Thread.sleep(100);
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
            hitEnemyTank();
            //判断敌人坦克是否击中我
            hitHero();
            this.repaint();
        }
    }
}

```



Node类：

```java
package com.momo.tankgame5;

/**
 * @author momo~
 * @version 1.0
 * 一个Node对象表示一个敌人坦克的信息
 */
public class Node {
    private int x;
    private int y;
    private int direct;

    public Node(int x,int y,int direct){
        this.x = x;
        this.y = y;
        this.direct = direct;
    }

    public int getX() {
        return x;
    }

    public void setX(int x) {
        this.x = x;
    }

    public int getY() {
        return y;
    }

    public void setY(int y) {
        this.y = y;
    }

    public int getDirect() {
        return direct;
    }

    public void setDirect(int direct) {
        this.direct = direct;
    }
}

```



PlayAudio类：

```java
package com.momo.tankgame5;

import javax.sound.sampled.*;
import java.io.*;

/**
 * @author ajun
 * Date 2021/7/16
 * @version 1.0
 * 播放音乐
 */
public class PlayAudio extends Thread {

    private String filename;

    public PlayAudio(String wavfile) {
        String path = System.getProperty("user.dir");
        filename = path+"\\"+wavfile;
    }

    @Override
    public void run() {
        // 从项目资源目录下加载背景音乐
        AudioInputStream audioInputStream = null;
        try {
            audioInputStream = AudioSystem.getAudioInputStream(new BufferedInputStream(new FileInputStream(filename)));
        } catch (Exception e1) {
            e1.printStackTrace();
            return;
        }

        AudioFormat format = audioInputStream.getFormat();
        SourceDataLine auline = null;
        DataLine.Info info = new DataLine.Info(SourceDataLine.class, format);

        try {
            auline = (SourceDataLine) AudioSystem.getLine(info);
            auline.open(format);
        } catch (Exception e) {
            e.printStackTrace();
            return;
        }

        auline.start();
        int nBytesRead = 0;
        //缓存
        byte[] abData = new byte[512];

        try {
            while (nBytesRead != -1) {
                nBytesRead = audioInputStream.read(abData, 0, abData.length);
                if (nBytesRead >= 0)
                    auline.write(abData, 0, nBytesRead);
            }
        } catch (IOException e) {
            e.printStackTrace();
            return;
        } finally {
            auline.drain();
            auline.close();
        }
    }
}

```



Recordar类：

```java
package com.momo.tankgame5;

import java.awt.*;
import java.io.*;
import java.util.Vector;

/**
 * @author momo~
 * @version 1.0
 */
public class Recorder {

    //定义变量，记录我方击毁敌人坦克数
    private static int allEnemyTankNum = 0;
    //定义IO对象
    private static String recordFile = "src\\myRecord.txt";
    private static Vector<EnemyTank> enemyTanks = null;
    private static BufferedReader br = null;
    //定义一个Node的Vector，用于保存敌人的信息
    private static Vector<Node> nodes = new Vector<>();

    public static void setEnemyTanks(Vector<EnemyTank> enemyTanks) {
        Recorder.enemyTanks = enemyTanks;
    }

    //用于读取文件,恢复相关信息
    public static Vector<Node> getNodesAndAllEnemyTankNum() throws IOException {
        br = new BufferedReader(new FileReader(recordFile));
        allEnemyTankNum = Integer.parseInt(br.readLine());
        //循环读取文件，生成集合
        String line= "";
        while ((line = br.readLine()) != null){
            String[] s = line.split(" ");
            Node node = new Node(Integer.parseInt(s[0]), Integer.parseInt(s[1]), Integer.parseInt(s[2]));
            nodes.add(node);//放入nodes Vector
        }

        if (br != null){
            br.close();
        }

        return nodes;
    }


    //当游戏退出时，就将allEnemyTankNum保存到recordFile
    //功能扩展，保存敌人坦克坐标方向
    public static void keepRecord() throws IOException {
        BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(recordFile));
        bufferedWriter.write(allEnemyTankNum + "\r\n");
//        bufferedWriter.newLine();//这里导致乱码

        //遍历敌人坦克的Vector，然后根据情况保存即可
        //定义一个属性，通过set方法得到敌人坦克的Vector
        for (int i = 0; i < enemyTanks.size(); i++) {
            //取出敌人坦克
            EnemyTank enemyTank = enemyTanks.get(i);
            if (enemyTank.isLive){
                //保存该enemyTank信息
                String record = enemyTank.getX() + " " + enemyTank.getY() + " " + enemyTank.getDirect();
                //写入到文件
                bufferedWriter.write(record + "\r\n");
            }
        }

        if (bufferedWriter != null){
            bufferedWriter.close();
        }
    }

    public static int getAllEnemyTankNum() {
        return allEnemyTankNum;
    }

    public static void setAllEnemyTankNum(int allEnemyTankNum) {
        Recorder.allEnemyTankNum = allEnemyTankNum;
    }

    //当我方坦克击毁敌方一辆坦克
    public static void addAllEnemyTankNum(){
        Recorder.allEnemyTankNum++;
    }
}

```



Shot类：

```java
package com.momo.tankgame5;

/**
 * @author momo~
 * @version 1.0
 */
public class Shot implements Runnable{
    int x;//子弹x坐标
    int y;//子弹y坐标
    int direct = 0;//子弹方向
    int speed = 2;//子弹速度
    boolean isLive = true;//子弹是否还存在

    public Shot(int x, int y, int direct) {
        this.x = x;
        this.y = y;
        this.direct = direct;
    }

    @Override
    public void run() {//射击
        while (true){

            //休眠50ms
            try {
                Thread.sleep(50);
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
            //根据方向改变坐标
            switch (direct){//0 1 2 3 (上右下左)
                case 0:
                    y -= speed;
                    break;
                case 1:
                    x += speed;
                    break;
                case 2:
                    y += speed;
                    break;
                case 3:
                    x -= speed;
                    break;
            }
            //测试输出x、y坐标
            System.out.println("x=" + x + "y=" + y);
            //子弹到边界应该销毁
            //当子弹碰到敌人坦克也应该结束线程
            if (!(x >= 0 && x <= 1000 && y >= 0 && y <= 750 && isLive)){
                isLive = false;
                break;
            }
        }
    }
}

```



Tank类：

```java
package com.momo.tankgame5;

/**
 * @author momo~
 * @version 3.0
 * 坦克父类
 */
public class Tank {
    private int x;
    private int y;
    private int direct;//方向0123 上右下左
    private int speed = 1;//坦克速度

    boolean isLive = true;

    public int getSpeed() {
        return speed;
    }

    public void setSpeed(int speed) {
        this.speed = speed;
    }

    //移动
    public void moveUp(){
        y -= speed;
    }
    public void moveRight(){
        x += speed;
    }
    public void moveDown(){
        y += speed;
    }
    public void moveLeft(){
        x -= speed;
    }




    public int getDirect() {
        return direct;
    }

    public void setDirect(int direct) {
        this.direct = direct;
    }


    public Tank(int x, int y) {
        this.x = x;
        this.y = y;
    }

    public int getX() {
        return x;
    }

    public void setX(int x) {
        this.x = x;
    }

    public int getY() {
        return y;
    }

    public void setY(int y) {
        this.y = y;
    }
}

```



## 16. 网络编程

### 1. 网络相关概念

![image-20220813072852545](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062325825.png)



![image-20220813073156556](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062325092.png)



### 2. IP地址

![image-20220813074133718](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062325259.png)



![image-20220813074316049](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062325393.png)



![image-20220813074905939](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326484.png)



![image-20220813075115903](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326516.png)



### 3. 域名和端口号

![image-20220813080729545](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326569.png)



![image-20220813080753107](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326817.png)





**<span style="color:red">浏览器访问服务器的过程</span>**

1、在浏览器地址栏中输入网址

![img](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326012.png)

 2、浏览器通过用户在地址栏中输入的URL构造HTTP请求报文（请求报文一般没有请求体）

![img](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326219.png)

 3、浏览器发起 DNS 解析请求，将域名转换为 IP 地址

![img](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326166.png)

 4、浏览器将请求报文发送给服务器

5、服务器接收请求报文，并解析

6、服务器处理用户请求，并将处理结果封装成 HTTP 响应报文（响应报文大部分都有实体主体）

![img](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326768.png)

![img](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326044.png)

![img](https://img-blog.csdnimg.cn/9cd6b68dec124f33be0fbd00b3670b40.png)

7、服务器将 HTTP 响应报文发送给浏览器

8、浏览器接收服务器相应的 HTTP 报文，并解析

9、浏览器解析 HTML 页面并展示，在解析 HTML 页面时遇到新的资源需要再次发起请求

10、最终浏览器展示出页面



### 4. 网络协议

![image-20220813082519978](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326109.png)



![image-20220813082538846](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326224.png)





**FTP:**文件传输协议（FileTransferProtocol）FTP的任务是从一台计算机将文件传送到另一台计算机。

**TCP：**传输控制协议（Transmission Control Protocol）是一种面向连接的、可靠的、基于[字节流](https://so.csdn.net/so/search?q=字节流&spm=1001.2101.3001.7020)的传输层通信协议当应用层向TCP层发送用于网间传输的、用8位字节表示的数据流，TCP则把数据流分割成适当长度的报文段，最大传输段大小（MSS）通常受该计算机连接的网络的数据链路层的最大传送单元（MTU）限制。之后TCP把数据包传给IP层，由它来通过网络将包传送给接收端实体的TCP层。

 **TCP三次握手建立连接过程如下：**

1. 客户端发送带有SYN的报文
2. 服务端发送回带有SYN和ACK的报文
3. 客户端发送标有ACK的报文，进入Established状态。

- ![img](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326648.png)

 **TCP四次挥手终止连接过程如下：**

1. 客户端发送一个 FIN 报文（请求连接终止：FIN = 1），报文中会指定一个序列号 seq = u。并停止再发送数据，主动关闭 TCP 连接。此时客户端处于 FIN_WAIT1 状态，等待服务端的确认。
2. 服务端收到 FIN 之后，会发送 ACK 报文，且把客户端的序号值 +1 作为 ACK 报文的序列号值，表明已经收到客户端的报文了，此时服务端处于 CLOSE_WAIT状态。
3. 服务端收到 FIN 之后，会发送 ACK 报文，且把客户端的序号值 +1 作为 ACK 报文的序列号值，表明已经收到客户端的报文了，此时服务端处于 CLOSE_WAIT状态。
4. 客户端收到 FIN 之后，发送一个 ACK 报文作为应答，且把服务端的序列值 +1 作为自己 ACK 报文的序号值，此时客户端处于 TIME_WAIT（时间等待）状态。

**注意 ：这个时候由服务端到客户端的 TCP 连接并未释放掉，****需要经过时间等待计时器设置的时间 2MSL（一个报文的来回时间） 后才会进入 CLOSED状态****（这样做的目的是确保服务端收到自己的 ACK 报文。如果服务端在规定时间内没有收到客户端发来的 ACK 报文的话，服务端会重新发送 FIN 报文给客户端，客户端再次收到 FIN 报文之后，就知道之前的 ACK 报文丢失了，然后再次发送 ACK 报文给服务端）。服务端收到 ACK 报文之后，就关闭连接了，处于 CLOSED 状态。**

​    

![img](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326965.png)



**为什么要四次挥手：**

由于 TCP 的**半关闭**（half-close）特性，TCP 提供了连接的一端在结束它的发送后还能接收来自另一端数据的能力。

任何一方都可以在数据传送结束后发出连接释放的通知，待对方确认后进入**半关闭状态**。当另一方也没有数据再发送的时候，则发出连接释放通知，对方确认后就**完全关闭**了TCP连接。   

**IP：**网际互连协议（Internet Protocol）IP协议的作用是把各种数据包传送给对方。而要保证确实传送到对方那里，则需要满足各类条件。其中两个重要的条件是IP地址和MAC地址（Media Access Control Address）。IP地址指明了节点被分配到的地址，MAC地址是指网卡所属的固定地址。IP地址可以和MAC地址进行配对。IP地址可变换，但MAC地址基本上不会更改。

**DNS：**域名系统（Domain Name System）服务是和HTTP协议一样位于应用层的协议。它提供域名到IP地址之间的解析服务。

**SMTP：**简单邮件传输协议（Simple Mail Transfer Protocol）SMTP是一种提供可靠且有效的电子邮件传输的协议。SMTP是建立在FTP文件传输服务上的一种邮件服务，主要用于系统之间的邮件信息传递，并提供有关来信的通知。

**HTTP：**超文本传输协议（Hyper Text Transfer Protocol，HTTP）是一个简单的请求-响应协议，它通常运行在TCP之上。

**UDP：**该协议称为用户数据报协议（UDP，User Datagram Protocol）。UDP 为应用程序提供了一种无需建立连接就可以发送封装的 IP 数据包的方法。

**ARP：**地址解析协议，（Address Resolution Protocol）是根据IP地址获取物理地址的一个TCP/IP协议。主机发送信息时将包含目标IP地址的ARP请求广播到局域网络上的所有主机，并接收返回消息，以此确定目标的物理地址；收到返回消息后将该IP地址和物理地址存入本机ARP缓存中并保留一定时间，下次请求时直接查询ARP缓存以节约资源。

**TCP/IP协议族里重要的一点就是分层。TCP/IP协议族按层次分别分为以下5层：应用层、传输层、网络层和数据链路层，物理层。**

**应用层**：应用层决定了向用户提供应用服务时通信的活动。TCP/IP协议族内预存了各类通用的应用服务。

**传输层：**传输层对上层应用层，提供处于网络连接中的两台计算机之间的数据传输。

**网络层：**网络层用来处理在网络上流动的数据包。数据包是网络传输的最小数据单位。

**数据链路层、物理层：**[数据链路层](https://so.csdn.net/so/search?q=数据链路层&spm=1001.2101.3001.7020)在物理层提供的服务的基础上向网络层提供服务，其最基本的服务是将源自网络层来的数据可靠地传输到相邻节点的目标机网络层。

![img](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326614.png)





TCP/IP通信传输流：

![img](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326622.png)

发送端在层与层之间传输数据时，每经过一层时必定会被打上一个该层所属的首部信息。反之，接收端在层与层传输数据时，每经过一层时会把对应的首部消去。



![img](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326787.png)



### 5. TCP与UDP

![image-20220813084002949](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326449.png)



### 6. InetAddress类

![image-20220813084058444](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326458.png)



![image-20220813085838110](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326417.png)



```java
package com.momo.api;

import java.net.InetAddress;
import java.net.UnknownHostException;

/**
 * @author momo~
 * @version 1.0
 * 演示InetAddress类的使用
 */
public class API_ {
    public static void main(String[] args) throws UnknownHostException {
        //获取本机的InetAddress对象
        InetAddress localHost = InetAddress.getLocalHost();
        System.out.println(localHost);//DESKTOP-OKN8RBH/192.168.1.16

        //根据指定主机名获取对象
        InetAddress byName1 = InetAddress.getByName("DESKTOP-OKN8RBH");
        System.out.println(byName1);//DESKTOP-OKN8RBH/192.168.1.16

        //根据域名返回InetAddress对象，比如www.baidu.com
        InetAddress byName2 = InetAddress.getByName("www.baidu.com");
        System.out.println(byName2);//www.baidu.com/180.101.49.11

        //通过InetAddress对象，获取对应地址
        String hostAddress = byName2.getHostAddress();
        System.out.println(hostAddress);//180.101.49.11

        //通过InetAddress对象,获取对应的主机名或者域名
        String hostName = byName2.getHostName();
        System.out.println(hostName);//www.baidu.com
    }
}
```



### 7. socket

![image-20220813090725547](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326393.png)



![image-20220813091030530](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326307.png)



![image-20220813091004094](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326320.png)



### 8. TCP字节流编程

![image-20220813094907975](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326363.png)



![image-20220813094700569](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326338.png)



```java
package com.momo.socket_;

import java.io.IOException;
import java.io.InputStream;
import java.net.ServerSocket;
import java.net.Socket;

/**
 * @author momo~
 * @version 1.0
 */
public class SocketServer01 {//服务端
    public static void main(String[] args) throws IOException {
        //思路：
        //在本机9999端口监听，等待连接
        //细节：要求在本机没有其他服务在监听9999
        //细节：这个ServerSocket可以通过accept()返回多个Socket【多个客户端连接服务器的并发】
        ServerSocket serverSocket = new ServerSocket(9999);
        System.out.println("服务器端socket等待连接中。。。");
        Socket socket = serverSocket.accept();
        //如果没有客户端连接9999端口，程序会阻塞
        //当有客户端连接，则会返回Socket对象，程序继续
        //通过socket.getInputStream()读取
        InputStream inputStream = socket.getInputStream();
        byte data[] = new byte[1024];
        int readLen = 0;
        while ((readLen = inputStream.read(data)) != -1){
            System.out.println(new String(data,0,readLen));
        }
//        System.out.println("服务器端Socket：" + socket.getClass());

        //关闭流
        inputStream.close();
        socket.close();
        System.out.println("服务器端退出");
    }
}

```

![image-20220813095057500](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326849.png)

```java
package com.momo.socket_;

import java.io.IOException;
import java.io.OutputStream;
import java.net.InetAddress;
import java.net.Socket;
import java.net.UnknownHostException;

/**
 * @author momo~
 * @version 1.0
 */
public class SocketClient01 {//客户端
    public static void main(String[] args) throws IOException {
        Socket socket = new Socket(InetAddress.getLocalHost(), 9999);
        System.out.println("客户端socket返回=" + socket.getClass());

        //连接上后，生成Socket，通过socket.getOutPutStream()输出流写入数据到数据通道
        OutputStream outputStream = socket.getOutputStream();
        outputStream.write("hello,server".getBytes());
        //关闭流
        outputStream.close();
        socket.close();
        System.out.println("客户端退出");
    }
}

```



![image-20220813095132907](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062326917.png)



![image-20220813124148617](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327819.png)



```java
package com.momo.socket_;

import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;
import java.net.ServerSocket;
import java.net.Socket;

/**
 * @author momo~
 * @version 1.0
 */
public class SocketServer02 {
    public static void main(String[] args) throws IOException {
        ServerSocket serverSocket = new ServerSocket(9999);
        System.out.println("等待客户端连接。。。");
        Socket socket = serverSocket.accept();

        InputStream inputStream = socket.getInputStream();
        byte buf[] = new byte[1024];
        int readLen = 0;
        while ((readLen = inputStream.read(buf)) != -1){
            System.out.println(new String(buf,0,readLen));
        }

        OutputStream outputStream = socket.getOutputStream();
        outputStream.write("hello,client".getBytes());
        socket.shutdownOutput();

        outputStream.close();
        inputStream.close();
        socket.close();
        System.out.println("服务端退出");

    }
}
```



```java
package com.momo.socket_;

import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;
import java.net.InetAddress;
import java.net.Socket;
import java.net.UnknownHostException;

/**
 * @author momo~
 * @version 1.0
 */
public class SocketClient02 {
    public static void main(String[] args) throws IOException {
        Socket socket = new Socket(InetAddress.getLocalHost(), 9999);

        OutputStream outputStream = socket.getOutputStream();

        outputStream.write("hello,server".getBytes());
        socket.shutdownOutput();

        InputStream inputStream = socket.getInputStream();
        byte buf[] = new byte[1024];
        int readLen = 0;

        while ((readLen = inputStream.read(buf)) != -1){
            System.out.println(new String(buf,0,readLen));
        }


        inputStream.close();
        outputStream.close();
        socket.close();
        System.out.println("客户端退出");
    }
}
```



![image-20220813102010647](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327702.png)



```java
package com.momo.socket_;

import java.io.*;
import java.net.ServerSocket;
import java.net.Socket;

/**
 * @author momo~
 * @version 1.0
 */
public class SocketServer03 {
    public static void main(String[] args) throws IOException {
        ServerSocket serverSocket = new ServerSocket(9999);
        System.out.println("等待客户端发送。。");
        Socket socket = serverSocket.accept();

        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(socket.getInputStream()));
        String s = bufferedReader.readLine();
        System.out.println(s);

        BufferedWriter bufferedWriter = new BufferedWriter(new OutputStreamWriter(socket.getOutputStream()));
        bufferedWriter.write("hello,client");
        bufferedWriter.newLine();
        bufferedWriter.flush();

        bufferedWriter.close();
        bufferedReader.close();
        socket.close();
        System.out.println("服务端退出");
    }
}

```



```java
package com.momo.socket_;

import java.io.*;
import java.net.InetAddress;
import java.net.Socket;
import java.net.UnknownHostException;

/**
 * @author momo~
 * @version 1.0
 */
public class SocketClient03 {
    public static void main(String[] args) throws IOException {
        Socket socket = new Socket(InetAddress.getLocalHost(), 9999);
        BufferedWriter bufferedWriter = new BufferedWriter(new OutputStreamWriter(socket.getOutputStream()));
        bufferedWriter.write("hello,server");
        bufferedWriter.newLine();//换行符，表示写入内容结束，同时要求对方使用readLine()
        bufferedWriter.flush();//如果使用的字符流，需要手动刷新，否者数据进不去

        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(socket.getInputStream()));
        String s = bufferedReader.readLine();
        System.out.println(s);

        bufferedReader.close();
        bufferedWriter.close();
        socket.close();
        System.out.println("客户端退出");
    }
}

```



### 9. 网络上传文件

![image-20220813105558077](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327896.png)



![image-20220813135132581](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327875.png)



```java
package com.momo.socket_;

import java.io.*;
import java.net.ServerSocket;
import java.net.Socket;

/**
 * @author momo~
 * @version 1.0
 * 文件上传服务端
 */
public class TCPFileUploadServer {
    public static void main(String[] args) throws Exception {

        ServerSocket serverSocket = new ServerSocket(8888);
        System.out.println("服务端等待中。。。");
        Socket socket = serverSocket.accept();

        //读取客户端发送数据
        //通过socket得到输入流
        BufferedInputStream bis = new BufferedInputStream(socket.getInputStream());
        byte[] bytes = StreamUtils.streamToByteArray(bis);

        String filePath = "src\\001.jpg";
        BufferedOutputStream bos = new BufferedOutputStream(new FileOutputStream(filePath));
        bos.write(bytes);

        //向客户端回复
        BufferedOutputStream bufferedOutputStream = new BufferedOutputStream(socket.getOutputStream());
        bufferedOutputStream.write("服务端已经接收到".getBytes());
        bufferedOutputStream.flush();
        socket.shutdownOutput();

        //关闭其他流
        bos.close();
        bis.close();
        bufferedOutputStream.close();
        serverSocket.close();
        socket.close();
    }
}

```



```java
package com.momo.socket_;

import java.io.BufferedReader;
import java.io.ByteArrayOutputStream;
import java.io.InputStream;
import java.io.InputStreamReader;

/**
 * @author momo~
 * @version 1.0
 */
public class StreamUtils {
    /**
     * 功能：将输入流转换成byte[]， 即可以把文件的内容读入到byte[]
     * @param is
     * @return
     * @throws Exception
     */
    public static byte[] streamToByteArray(InputStream is) throws Exception{
        ByteArrayOutputStream bos = new ByteArrayOutputStream();//创建输出流对象
        byte[] b = new byte[1024];//字节数组
        int len;
        while((len=is.read(b))!=-1){//循环读取
            bos.write(b, 0, len);//把读取到的数据，写入bos
        }
        byte[] array = bos.toByteArray();//然后将bos 转成字节数组
        bos.close();
        return array;
    }
    /**
     * 功能：将InputStream转换成String
     * @param is
     * @return
     * @throws Exception
     */

    public static String streamToString(InputStream is) throws Exception{
        BufferedReader reader = new BufferedReader(new InputStreamReader(is));
        StringBuilder builder= new StringBuilder();
        String line;
        while((line=reader.readLine())!=null){
            builder.append(line+"\r\n");
        }
        return builder.toString();

    }
}

```



```java
package com.momo.socket_;

import java.io.BufferedInputStream;
import java.io.BufferedOutputStream;
import java.io.FileInputStream;
import java.io.IOException;
import java.net.InetAddress;
import java.net.Socket;
import java.net.UnknownHostException;

/**
 * @author momo~
 * @version 1.0
 * 文件上传客户端
 */
public class TCPFileUploadClient {
    public static void main(String[] args) throws Exception {
        //客户端连接服务器，得到socket对象
        Socket socket = new Socket(InetAddress.getLocalHost(), 8888);

        //创建读取磁盘文件的输入流
        String filePath = "D:\\001.jpg";
        BufferedInputStream bis = new BufferedInputStream(new FileInputStream(filePath));

        //bytes就是filePath对应的字节数组
        byte[] bytes = StreamUtils.streamToByteArray(bis);

        //通过socket获取输出流，将bytes数据发送给服务端
        BufferedOutputStream bos = new BufferedOutputStream(socket.getOutputStream());
        bos.write(bytes);
        socket.shutdownOutput();

        BufferedInputStream bufferedInputStream = new BufferedInputStream(socket.getInputStream());
        byte buf[] = new byte[1024];
        int readLen = 0;
        while ((readLen = bufferedInputStream.read(buf)) != -1){
            System.out.println(new String(buf,0,readLen));
        }

        //关闭其他流
        bufferedInputStream.close();
        bos.close();
        bis.close();
        socket.close();

    }
}

```



### 10. netstat

![image-20220813140029759](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327804.png)



### 11.TCP连接端口

![image-20220813140925583](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327735.png)



### 12. UDP编程

![image-20220813142101749](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327884.png)



![image-20220813142042187](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327985.png)



![image-20220813141922835](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327162.png)



![image-20220813142222969](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327054.png)



```JAVA
package com.momo.udp_;

import java.io.IOException;
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.InetAddress;
import java.net.SocketException;

/**
 * @author momo~
 * @version 1.0
 */
public class UDPReceive {
    public static void main(String[] args) throws IOException {
        //
        DatagramSocket datagramSocket = new DatagramSocket(9999);

        //UDP协议，数据包最大64k
        byte buf[] = new byte[1024];

        DatagramPacket datagramPacket = new DatagramPacket(buf, buf.length);

        System.out.println("接收端A等待数据");
        datagramSocket.receive(datagramPacket);

        int length = datagramPacket.getLength();
        byte[] data = datagramPacket.getData();

        String s = new String(data, 0, length);
        System.out.println(s);

        //回复
        //将准备发送的数据封装到DatagramPacket对象
        data = "了解收到".getBytes();
        datagramPacket = new DatagramPacket(data, data.length, InetAddress.getByName("192.168.1.16"), 9998);

        datagramSocket.send(datagramPacket);

        datagramSocket.close();
        System.out.println("接收端A退出");
    }
}

```



```JAVA
package com.momo.udp_;

import java.io.IOException;
import java.net.*;

/**
 * @author momo~
 * @version 1.0
 */
public class UDPSend {
    public static void main(String[] args) throws IOException {
        //创建DatagramSocket对象，准备在9998端口接收数据
        DatagramSocket datagramSocket = new DatagramSocket(9998);

        //将准备发送的数据封装到DatagramPacket对象
        byte data[] = "hello,明天吃火锅".getBytes();
        DatagramPacket datagramPacket = new DatagramPacket(data, data.length, InetAddress.getByName("192.168.1.16"), 9999);

        datagramSocket.send(datagramPacket);

        //接收
        //UDP协议，数据包最大64k
        byte buf[] = new byte[1024];

        datagramPacket = new DatagramPacket(buf, buf.length);

        System.out.println("接收端B等待数据");
        datagramSocket.receive(datagramPacket);

        int length = datagramPacket.getLength();
        data = datagramPacket.getData();

        String s = new String(data, 0, length);
        System.out.println(s);

        //关闭资源
        datagramSocket.close();
        System.out.println("发送端B退出");
    }
}

```



### 13. 总结作业

![image-20220813152119622](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327940.png)

```java
package com.momo;

import java.io.*;
import java.net.ServerSocket;
import java.net.Socket;

/**
 * @author momo~
 * @version 1.0
 */
public class Homework01Server {
    public static void main(String[] args) throws IOException {
        ServerSocket serverSocket = new ServerSocket(9999);
        System.out.println("等待客户端发送。。");
        Socket socket = serverSocket.accept();

        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(socket.getInputStream()));
        String answer = "";
        String s = bufferedReader.readLine();
        if ("name".equals(s)){
            answer = "我是momo";
        } else if ("bobby".equals(s)) {
            answer = "读书";
        } else {
            answer = "你在说什么";
        }


        BufferedWriter bufferedWriter = new BufferedWriter(new OutputStreamWriter(socket.getOutputStream()));
        bufferedWriter.write(answer);
        bufferedWriter.newLine();
        bufferedWriter.flush();

        bufferedWriter.close();
        bufferedReader.close();
        socket.close();
        System.out.println("服务端退出");
    }
}

```



```java
package com.momo;

import java.io.*;
import java.net.InetAddress;
import java.net.Socket;
import java.net.UnknownHostException;
import java.util.Scanner;

/**
 * @author momo~
 * @version 1.0
 */
public class Homework01Client {
    public static void main(String[] args) throws IOException {
        Socket socket = new Socket(InetAddress.getLocalHost(), 9999);
        BufferedWriter bufferedWriter = new BufferedWriter(new OutputStreamWriter(socket.getOutputStream()));

        //从键盘读取用户输入
        Scanner scanner = new Scanner(System.in);
        System.out.println("请输入你的问题：");
        String question = scanner.next();

        bufferedWriter.write(question);
        bufferedWriter.newLine();//换行符，表示写入内容结束，同时要求对方使用readLine()
        bufferedWriter.flush();//如果使用的字符流，需要手动刷新，否者数据进不去

        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(socket.getInputStream()));
        String s = bufferedReader.readLine();
        System.out.println(s);

        bufferedReader.close();
        bufferedWriter.close();
        socket.close();
        System.out.println("客户端退出");
    }
}

```



![image-20220813152202069](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327812.png)

```java
package com.momo;

import java.io.IOException;
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.InetAddress;

/**
 * @author momo~
 * @version 1.0
 */
public class HomeworkUDPReceive {
    public static void main(String[] args) throws IOException {
        //
        DatagramSocket datagramSocket = new DatagramSocket(8888);

        //UDP协议，数据包最大64k
        byte buf[] = new byte[1024];

        DatagramPacket datagramPacket = new DatagramPacket(buf, buf.length);

        System.out.println("接收端A等待数据");
        datagramSocket.receive(datagramPacket);


        int length = datagramPacket.getLength();
        byte[] data = datagramPacket.getData();

        String s = new String(data, 0, length);
        System.out.println(s);

        //回复
        //将准备发送的数据封装到DatagramPacket对象
        String answer = "";
        if ("四大名著是那些".equals(s)){
            answer = "四大名著是《1》《2》《3》《4》";
        } else {
            answer = "what?";
        }
        data = answer.getBytes();

        datagramPacket = new DatagramPacket(data, data.length, InetAddress.getByName("192.168.1.16"), 9998);

        datagramSocket.send(datagramPacket);

        datagramSocket.close();
        System.out.println("接收端A退出");
    }
}

```



```java
package com.momo;

import java.io.IOException;
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.InetAddress;
import java.util.Scanner;

/**
 * @author momo~
 * @version 1.0
 */
public class HomeworkUDPSend {
    public static void main(String[] args) throws IOException {
        //创建DatagramSocket对象，准备在9998端口接收数据
        DatagramSocket datagramSocket = new DatagramSocket(9998);

        //将准备发送的数据封装到DatagramPacket对象
        Scanner scanner = new Scanner(System.in);
        String question = scanner.next();
        byte data[] = question.getBytes();
        DatagramPacket datagramPacket = new DatagramPacket(data, data.length, InetAddress.getByName("192.168.1.16"), 8888);

        datagramSocket.send(datagramPacket);

        //接收
        //UDP协议，数据包最大64k
        byte buf[] = new byte[1024];

        datagramPacket = new DatagramPacket(buf, buf.length);

        System.out.println("接收端B等待数据");
        datagramSocket.receive(datagramPacket);

        int length = datagramPacket.getLength();
        data = datagramPacket.getData();

        String s = new String(data, 0, length);
        System.out.println(s);

        //关闭资源
        datagramSocket.close();
        System.out.println("发送端B退出");
    }
}

```



![image-20220813154054386](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327045.png)

```java
```





## 17. 多用户通信系统

### 1.项目开发流程

![image-20220822075721432](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327056.png)

 

### 2.需求分析

![image-20220822080023954](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327313.png)



![image-20220822080108381](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327422.png)



![image-20220822080121342](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327342.png)



![image-20220822080203696](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327364.png)



![image-20220822080236983](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327381.png)



![image-20220822080350233](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327471.png)



![image-20220822080438018](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327568.png)





![image-20220822082045540](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327546.png)



### 3.qq用户登录

![image-20220822084511459](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327463.png)



![image-20220822084245399](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062327263.png)



```java
package com.momo.qqcommon;

import java.io.Serializable;

/**
 * @author momo~
 * @version 1.0
 * 表示一个用户/客户信息
 */
public class User implements Serializable {
    private String userId;//用户名/用户id
    private String name;//用户密码

    public User(String userId, String name) {
        this.userId = userId;
        this.name = name;
    }

    public String getUserId() {
        return userId;
    }

    public void setUserId(String userId) {
        this.userId = userId;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}

```



```java
package com.momo.qqcommon;

/**
 * @author momo~
 * @version 1.0
 */
public interface MessageType {
    //1.在接口中定义了一些常量
    //2.不同的常量的值表示不同的消息类型
    String MESSAGE_LOGIN_SUCCEED = "1";//表示登录成功
    String MESSAGE_LOGIN_FAIL = "2";//表示登录失败
}

```



```java
package com.momo.qqcommon;

import java.io.Serializable;

/**
 * @author momo~
 * @version 1.0
 * 表示客户端和服务器端通信时的消息对象
 */
public class Message implements Serializable {
    private static final long serialVersionUID = 1L;
    private String sender;//发送方
    private String getter;//接收方
    private String content;//消息内容
    private String sendTime;//发送时间
    private String mesType;//消息类型【可以在接口中定义】

    public String getSender() {
        return sender;
    }

    public void setSender(String sender) {
        this.sender = sender;
    }

    public String getGetter() {
        return getter;
    }

    public void setGetter(String getter) {
        this.getter = getter;
    }

    public String getContent() {
        return content;
    }

    public void setContent(String content) {
        this.content = content;
    }

    public String getSendTime() {
        return sendTime;
    }

    public void setSendTime(String sendTime) {
        this.sendTime = sendTime;
    }

    public String getMesType() {
        return mesType;
    }

    public void setMesType(String mesType) {
        this.mesType = mesType;
    }
}

```



初版客户端界面：

```java
package com.momo.qqclient_view;

import com.momo.qqclient_utils.Utility;

import javax.jws.soap.SOAPBinding;

/**
 * @author momo~
 * @version 1.0
 * 客户端菜单界面
 */
public class QQView {
    private boolean loop = true;//控制是否显示菜单
    private String key = "";//接收用户输入

    public static void main(String[] args) {
        new QQView().mainMenu();
        System.out.println("退出系统。。。");
    }


    //显示主菜单
    private void mainMenu(){
        while (loop){
            System.out.println("==========欢迎登录网络通信系统==========");
            System.out.println("\t\t1 登录系统");
            System.out.println("\t\t9 退出系统");
            System.out.println("请输入你的选择：");
            key = Utility.readString(1);

            //根据用户输入，来处理不同的逻辑
            switch (key){
                case "1":
                    System.out.println("请输入用户号：");
                    String userId = Utility.readString(50);
                    System.out.println("请输入密码：");
                    String pwd = Utility.readString(50);
                    //到服务器验证该用户是否合法
                    if (true){
                        System.out.println("==========欢迎（"+ userId+"）==========");
                        while (loop){
                            System.out.println("==========网络通信系统二级菜单（"+ userId+"）==========");
                            System.out.println("\t\t1 显示在线用户列表");
                            System.out.println("\t\t2 群发消息");
                            System.out.println("\t\t3 私聊消息");
                            System.out.println("\t\t4 发送文件");
                            System.out.println("\t\t9 退出系统");
                            System.out.println("请输入你的选择：");
                            key = Utility.readString(1);
                            switch (key){
                                case "1":
                                    System.out.println("当前在线用户列表");
                                    break;
                                case "2":
                                    System.out.println("群发消息");
                                    break;
                                case "3":
                                    System.out.println("私聊消息");
                                    break;
                                case "4":
                                    System.out.println("发送文件");
                                    break;
                                case "9":
                                    loop = false;
                                    break;

                            }
                        }
                    } else {//登录服务器失败
                        System.out.println("登录失败");
                    }
                    break;
                case "9":
                    loop = false;
                    break;
            }
        }
    }
}

```



![image-20220822092255894](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062328288.png)



![image-20220822092316930](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062328790.png)









无异常退出系统

![image-20220822150835552](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062328118.png)



私聊功能

![image-20220822153357728](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062328221.png)



发送文件

![image-20220822165241293](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062328321.png)





服务端推送

![image-20220822183611620](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062328621.png)



客户端代码：

```java
package com.momo.qqclient.service;

import com.momo.qqcommon.Message;
import com.momo.qqcommon.MessageType;

import javax.jws.soap.SOAPBinding;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.ObjectInputStream;
import java.net.Socket;

/**
 * @author momo~
 * @version 1.0
 */
public class ClientConnectServerThread extends Thread{
    //该线程需要持有Socket
    private Socket socket;

    //构造器可以接收一个Socket对象
    public ClientConnectServerThread(Socket socket){
        this.socket = socket;
    }

    @Override
    public void run() {
        //因为Thread需要在后台和服务器通讯，因此使用while循环
        while (true){
            System.out.println("客户端线程等待读取服务器数据");
            try {
                ObjectInputStream ois = new ObjectInputStream(socket.getInputStream());
                Message message = (Message) ois.readObject();
                //如果服务器没有发送message对象，线程阻塞

                //注意，后面需要我们去使用message
                //判断这个message类型，然后做相应业务处理
                //如果读到的是服务端返回在线用户列表
                if (message.getMesType().equals(MessageType.MESSAGE_RET_ONLINE_FRIEND)){
                    //取出在线用户列表信息，并显示
                    String[] onlineUsers = message.getContent().split(" ");
                    System.out.println("\n==========当前在线用户列表==========");
                    for (int i = 0; i < onlineUsers.length; i++) {
                        System.out.println("用户：" + onlineUsers[i]);
                    }
                } else if (message.getMesType().equals(MessageType.MESSAGE_COMM_MES)) {
                    //从服务端转发的消息显示到控制台
                    System.out.println("\n" + message.getSender() + "对" + message.getGetter() + "说" + message.getContent());
                } else if (message.getMesType().equals(MessageType.MESSAGE_TO_ALL_MES)) {
                    //显示在客户端的控制台
                    System.out.println("\n" + message.getSender() + "对大家说" + message.getContent());
                } else if (message.getMesType().equals(MessageType.MESSAGE_FILE_ALL_MES)) {
                    System.out.println("\n" + message.getSender() + "给" + message.getGetter() + "发送文件：" + message.getSrc() + "到" + message.getDest());

                    //取出文件字节数组，通过文件输出流写入到磁盘
                    FileOutputStream fileOutputStream = new FileOutputStream(message.getDest());
                    fileOutputStream.write(message.getFileByte());
                    fileOutputStream.close();
                    System.out.println("\n保存文件成功");
                } else {
                    System.out.println("其他类型，暂时不做处理");
                }
            } catch (IOException | ClassNotFoundException e) {
                throw new RuntimeException(e);
            }
        }
    }

    //为了方便得到Socket
    public Socket getSocket() {
        return socket;
    }
}

```



```java
package com.momo.qqclient.service;

import com.momo.qqcommon.Message;
import com.momo.qqcommon.MessageType;

import java.io.*;

/**
 * @author momo~
 * @version 1.0
 * 该类完成文件传输服务
 */
public class FileClientServer {

    /**
     *
     * @param src 源文件路径
     * @param dest 目标文件路径
     * @param sendId 发送id
     * @param getterId 接收用户id
     */

    public void sendFileToOne(String src,String dest,String sendId,String getterId){

        //读取src文件  -》 message
        Message message = new Message();
        message.setMesType(MessageType.MESSAGE_FILE_ALL_MES);
        message.setSender(sendId);
        message.setGetter(getterId);
        message.setSrc(src);
        message.setDest(dest);

        //将文件读取
        FileInputStream fileInputStream = null;
        byte[] fileBytes = new byte[(int) new File(src).length()];
        try {
            fileInputStream = new FileInputStream(src);
            fileInputStream.read(fileBytes);
            //将文件对应的字节数组设置到message对象
            message.setFileByte(fileBytes);
        } catch (Exception e) {
            throw new RuntimeException(e);
        }
        System.out.println("\n" + message.getSender() + "给" + message.getGetter() + "发送文件" + src + "到对方的电脑上的" +  dest);
        try {
            ObjectOutputStream oos = new ObjectOutputStream(ManageClientConnectServerThread.getClientConnectServerThread(sendId).getSocket().getOutputStream());
            oos.writeObject(message);
        } catch (IOException e) {
            throw new RuntimeException(e);
        }
    }
}

```



```java
package com.momo.qqclient.service;

import java.util.HashMap;

/**
 * @author momo~
 * @version 1.0
 * 管理客户端连接到服务端线程的类
 */
public class ManageClientConnectServerThread {
    //把多个线程放入HashMap集合中，key就是用户id，value就是线程
    private static HashMap<String,ClientConnectServerThread> hm = new HashMap<>();

    //将某个线程加入集合中
    public static void addClientConnectServerThread(String userId,ClientConnectServerThread clientConnectServerThread){
        hm.put(userId,clientConnectServerThread);
    }

    //通过userId可以得到对应线程
    public static ClientConnectServerThread getClientConnectServerThread(String userId){
        return hm.get(userId);
    }
}

```



```java
package com.momo.qqclient.service;

import com.momo.qqcommon.Message;
import com.momo.qqcommon.MessageType;

import java.io.IOException;
import java.io.ObjectOutputStream;
import java.util.Date;

/**
 * @author momo~
 * @version 1.0
 * 该类提供和消息相关服务方法
 */
public class MessageClientServer {

    /**
     *
     * @param content
     * @param senderId
     */
    public void sendMessageToAll(String content,String senderId){
        //构建message
        Message message = new Message();
        message.setMesType(MessageType.MESSAGE_TO_ALL_MES);
        message.setSender(senderId);
        message.setContent(content);
        message.setSendTime(new Date().toString());//发送时间设置到message对象
        System.out.println(senderId + "对大家说" + content);

        //发送给服务端
        try {
            ObjectOutputStream oos = new ObjectOutputStream(ManageClientConnectServerThread.getClientConnectServerThread(senderId).getSocket().getOutputStream());
            oos.writeObject(message);
        } catch (IOException e) {
            throw new RuntimeException(e);
        }
    }


    /**
     *
     * @param content 内容
     * @param senderId 发送用户id
     * @param getterId 接收用户id
     */
    public void sendMessageToOne(String content,String senderId,String getterId){
        //构建message
        Message message = new Message();
        message.setMesType(MessageType.MESSAGE_COMM_MES);
        message.setSender(senderId);
        message.setGetter(getterId);
        message.setContent(content);
        message.setSendTime(new Date().toString());//发送时间设置到message对象
        System.out.println(senderId + "对" + getterId + "说" + content);

        //发送给服务端
        try {
            ObjectOutputStream oos = new ObjectOutputStream(ManageClientConnectServerThread.getClientConnectServerThread(senderId).getSocket().getOutputStream());
            oos.writeObject(message);
        } catch (IOException e) {
            throw new RuntimeException(e);
        }
    }
}

```



```java
package com.momo.qqclient.service;

import com.momo.qqcommon.Message;
import com.momo.qqcommon.MessageType;
import com.momo.qqcommon.User;

import java.io.IOException;
import java.io.ObjectInputStream;
import java.io.ObjectOutputStream;
import java.net.InetAddress;
import java.net.Socket;
import java.net.UnknownHostException;

/**
 * @author momo~
 * @version 1.0
 * 该类完成用户登录验证和用户注册等功能
 */
public class UserClientService {
    private User u = new User();//其他地方可能使用user,做成成员属性
    private Socket socket;//其他地方可能使用,做成成员属性

    //根据userId和pwd到服务器验证该用户是否合法
    public boolean checkUser(String userId,String pwd) throws IOException, ClassNotFoundException {
        boolean b = false;

        //创建User对象
        u.setUserId(userId);
        u.setPasswd(pwd);
        //连接到服务器，发送u对象
        socket = new Socket(InetAddress.getByName("127.0.0.1"), 9999);
        //得到ObjectOutputStream对象
        ObjectOutputStream oos = new ObjectOutputStream(socket.getOutputStream());
        oos.writeObject(u);//发送user对象

        //读取从服务端回复的Message对象
        ObjectInputStream ois = new ObjectInputStream(socket.getInputStream());
        Message ms = (Message) ois.readObject();
        if (ms.getMesType().equals(MessageType.MESSAGE_LOGIN_SUCCEED)){//登录成功
            //创建一个和服务器端保持通讯的线程 -》创建类ClientConnectServerThread

            ClientConnectServerThread clientConnectServerThread = new ClientConnectServerThread(socket);
            //启动线程
            clientConnectServerThread.start();
            //为了客户端扩展，将线程放入集合中
            ManageClientConnectServerThread.addClientConnectServerThread(userId,clientConnectServerThread);
            b = true;
        } else { //登录失败
            //不能启动和服务器的线程，关闭socket
            socket.close();
        }

        return b;
    }

    //向服务器端请求在线用户列表
    public void onlineFriendList(){

        //发送一个Message，类型MESSAGE_GET_ONLINE_FRIEND
        Message message = new Message();
        message.setMesType(MessageType.MESSAGE_GET_ONLINE_FRIEND);
        message.setSender(u.getUserId());
        //发送给服务器
        try {
            //得到当前线程的Socket对应的ObjectOutputStream对象
            ObjectOutputStream oos = new ObjectOutputStream
                    (ManageClientConnectServerThread.getClientConnectServerThread(u.getUserId()).getSocket().getOutputStream());
            oos.writeObject(message);//发送一个Message对象，向服务端请求在线用户列表
        } catch (IOException e) {
            throw new RuntimeException(e);
        }
    }

    //编写方法退出客户端，并给服务端发送一个退出系统的message对象
    public void logout(){
        Message message = new Message();
        message.setMesType(MessageType.MESSAGE_CLIENT_EXIT);
        message.setSender(u.getUserId());//当前是哪个客户端

        //发送message
        try {
            ObjectOutputStream oos = new ObjectOutputStream(socket.getOutputStream());
            oos.writeObject(message);
            System.out.println(u.getUserId() + "退出系统");
            System.exit(0);
        } catch (IOException e) {
            throw new RuntimeException(e);
        }
    }
}

```



```java
package com.momo.qqclient.utils;

/**
 工具类的作用:
 处理各种情况的用户输入，并且能够按照程序员的需求，得到用户的控制台输入。
 */

import java.util.*;
/**

 */
public class Utility {
    //静态属性。。。
    private static Scanner scanner = new Scanner(System.in);


    /**
     * 功能：读取键盘输入的一个菜单选项，值：1——5的范围
     * @return 1——5
     */
    public static char readMenuSelection() {
        char c;
        for (; ; ) {
            String str = readKeyBoard(1, false);//包含一个字符的字符串
            c = str.charAt(0);//将字符串转换成字符char类型
            if (c != '1' && c != '2' &&
                    c != '3' && c != '4' && c != '5') {
                System.out.print("选择错误，请重新输入：");
            } else break;
        }
        return c;
    }

    /**
     * 功能：读取键盘输入的一个字符
     * @return 一个字符
     */
    public static char readChar() {
        String str = readKeyBoard(1, false);//就是一个字符
        return str.charAt(0);
    }
    /**
     * 功能：读取键盘输入的一个字符，如果直接按回车，则返回指定的默认值；否则返回输入的那个字符
     * @param defaultValue 指定的默认值
     * @return 默认值或输入的字符
     */

    public static char readChar(char defaultValue) {
        String str = readKeyBoard(1, true);//要么是空字符串，要么是一个字符
        return (str.length() == 0) ? defaultValue : str.charAt(0);
    }

    /**
     * 功能：读取键盘输入的整型，长度小于2位
     * @return 整数
     */
    public static int readInt() {
        int n;
        for (; ; ) {
            String str = readKeyBoard(10, false);//一个整数，长度<=10位
            try {
                n = Integer.parseInt(str);//将字符串转换成整数
                break;
            } catch (NumberFormatException e) {
                System.out.print("数字输入错误，请重新输入：");
            }
        }
        return n;
    }
    /**
     * 功能：读取键盘输入的 整数或默认值，如果直接回车，则返回默认值，否则返回输入的整数
     * @param defaultValue 指定的默认值
     * @return 整数或默认值
     */
    public static int readInt(int defaultValue) {
        int n;
        for (; ; ) {
            String str = readKeyBoard(10, true);
            if (str.equals("")) {
                return defaultValue;
            }

            //异常处理...
            try {
                n = Integer.parseInt(str);
                break;
            } catch (NumberFormatException e) {
                System.out.print("数字输入错误，请重新输入：");
            }
        }
        return n;
    }

    /**
     * 功能：读取键盘输入的指定长度的字符串
     * @param limit 限制的长度
     * @return 指定长度的字符串
     */

    public static String readString(int limit) {
        return readKeyBoard(limit, false);
    }

    /**
     * 功能：读取键盘输入的指定长度的字符串或默认值，如果直接回车，返回默认值，否则返回字符串
     * @param limit 限制的长度
     * @param defaultValue 指定的默认值
     * @return 指定长度的字符串
     */

    public static String readString(int limit, String defaultValue) {
        String str = readKeyBoard(limit, true);
        return str.equals("")? defaultValue : str;
    }


    /**
     * 功能：读取键盘输入的确认选项，Y或N
     * 将小的功能，封装到一个方法中.
     * @return Y或N
     */
    public static char readConfirmSelection() {
        System.out.println("请输入你的选择(Y/N): 请小心选择");
        char c;
        for (; ; ) {//无限循环
            //在这里，将接受到字符，转成了大写字母
            //y => Y n=>N
            String str = readKeyBoard(1, false).toUpperCase();
            c = str.charAt(0);
            if (c == 'Y' || c == 'N') {
                break;
            } else {
                System.out.print("选择错误，请重新输入：");
            }
        }
        return c;
    }

    /**
     * 功能： 读取一个字符串
     * @param limit 读取的长度
     * @param blankReturn 如果为true ,表示 可以读空字符串。
     * 					  如果为false表示 不能读空字符串。
     *
     *	如果输入为空，或者输入大于limit的长度，就会提示重新输入。
     * @return
     */
    private static String readKeyBoard(int limit, boolean blankReturn) {

        //定义了字符串
        String line = "";

        //scanner.hasNextLine() 判断有没有下一行
        while (scanner.hasNextLine()) {
            line = scanner.nextLine();//读取这一行

            //如果line.length=0, 即用户没有输入任何内容，直接回车
            if (line.length() == 0) {
                if (blankReturn) return line;//如果blankReturn=true,可以返回空串
                else continue; //如果blankReturn=false,不接受空串，必须输入内容
            }

            //如果用户输入的内容大于了 limit，就提示重写输入
            //如果用户如的内容 >0 <= limit ,我就接受
            if (line.length() < 1 || line.length() > limit) {
                System.out.print("输入长度（不能大于" + limit + "）错误，请重新输入：");
                continue;
            }
            break;
        }

        return line;
    }
}


```



```java
package com.momo.qqclient.view;

import com.momo.qqclient.service.FileClientServer;
import com.momo.qqclient.service.MessageClientServer;
import com.momo.qqclient.service.UserClientService;
import com.momo.qqclient.utils.Utility;

import java.io.IOException;

/**
 * @author momo~
 * @version 1.0
 * 客户端菜单界面
 */
public class QQView {
    private boolean loop = true;//控制是否显示菜单
    private String key = "";//接收用户输入
    private UserClientService userClientService = new UserClientService();//用于登录服务器或注册
    private MessageClientServer messageClientServer = new MessageClientServer();//用于私聊或群聊
    private FileClientServer fileClientServer = new FileClientServer();//传输文件

    public static void main(String[] args) throws IOException, ClassNotFoundException {
        new QQView().mainMenu();
        System.out.println("退出系统。。。");
    }


    //显示主菜单
    private void mainMenu() throws IOException, ClassNotFoundException {
        while (loop){
            System.out.println("==========欢迎登录网络通信系统==========");
            System.out.println("\t\t1 登录系统");
            System.out.println("\t\t9 退出系统");
            System.out.println("请输入你的选择：");
            key = Utility.readString(1);

            //根据用户输入，来处理不同的逻辑
            switch (key){
                case "1":
                    System.out.println("请输入用户号：");
                    String userId = Utility.readString(50);
                    System.out.println("请输入密码：");
                    String pwd = Utility.readString(50);
                    //到服务器验证该用户是否合法
                    //编写类 UserClientService 用户登录注册
                    if (userClientService.checkUser(userId, pwd)){
                        System.out.println("==========欢迎（"+ userId+"）登录成功==========");
                        while (loop){
                            System.out.println("==========网络通信系统二级菜单（"+ userId+"）==========");
                            System.out.println("\t\t1 显示在线用户列表");
                            System.out.println("\t\t2 群发消息");
                            System.out.println("\t\t3 私聊消息");
                            System.out.println("\t\t4 发送文件");
                            System.out.println("\t\t9 退出系统");
                            System.out.println("请输入你的选择：");
                            key = Utility.readString(1);
                            switch (key){
                                case "1":
                                    //写一个方法获取在线用户列表
                                    userClientService.onlineFriendList();
                                    break;
                                case "2":
                                    System.out.println("请输入想对大家说的话：");
                                    String contentAll = Utility.readString(100);
                                    //调用一个方法，将消息封装成message对象，发送给服务端
                                    messageClientServer.sendMessageToAll(contentAll,userId);
                                    break;
                                case "3":
                                    System.out.println("请输入想聊天的用户号（在线）：");
                                    String getterId = Utility.readString(50);
                                    System.out.println("请输入想说的话：");
                                    String content = Utility.readString(100);
                                    //编写方法，将消息发送给服务端
                                    messageClientServer.sendMessageToOne(content,userId,getterId);
                                    System.out.println("私聊消息");
                                    break;
                                case "4":
                                    System.out.println("请输入你想发送文件的用户：");
                                    getterId = Utility.readString(50);
                                    System.out.println("请输入发送文件完整路径：");
                                    String src = Utility.readString(100);
                                    System.out.println("请输入对方文件完整路径：");
                                    String dest = Utility.readString(100);
                                    fileClientServer.sendFileToOne(src,dest,userId,getterId);
                                    break;
                                case "9":
                                    //调用方法，给服务器端发送一个退出系统的message
                                    userClientService.logout();
                                    loop = false;
                                    break;

                            }
                        }
                    } else {//登录服务器失败
                        System.out.println("登录失败");
                    }
                    break;
                case "9":
                    loop = false;
                    break;
            }
        }
    }
}

```





```java
package com.momo.qqcommon;

import java.io.Serializable;

/**
 * @author momo~
 * @version 1.0
 * 表示客户端和服务器端通信时的消息对象
 */
public class Message implements Serializable {
    private static final long serialVersionUID = 1L;
    private String sender;//发送方
    private String getter;//接收方
    private String content;//消息内容
    private String sendTime;//发送时间
    private String mesType;//消息类型【可以在接口中定义】

    //进行文件相关字段扩展
    private byte[] fileByte;
    private int fileLen = 0;
    private String dest;//目标文件路径
    private String src;//源文件路径

    public byte[] getFileByte() {
        return fileByte;
    }

    public void setFileByte(byte[] fileByte) {
        this.fileByte = fileByte;
    }

    public int getFileLen() {
        return fileLen;
    }

    public void setFileLen(int fileLen) {
        this.fileLen = fileLen;
    }

    public String getDest() {
        return dest;
    }

    public void setDest(String dest) {
        this.dest = dest;
    }

    public String getSrc() {
        return src;
    }

    public void setSrc(String src) {
        this.src = src;
    }

    public String getSender() {
        return sender;
    }

    public void setSender(String sender) {
        this.sender = sender;
    }

    public String getGetter() {
        return getter;
    }

    public void setGetter(String getter) {
        this.getter = getter;
    }

    public String getContent() {
        return content;
    }

    public void setContent(String content) {
        this.content = content;
    }

    public String getSendTime() {
        return sendTime;
    }

    public void setSendTime(String sendTime) {
        this.sendTime = sendTime;
    }

    public String getMesType() {
        return mesType;
    }

    public void setMesType(String mesType) {
        this.mesType = mesType;
    }
}

```



```java
package com.momo.qqcommon;

/**
 * @author momo~
 * @version 1.0
 */
public interface MessageType {
    //1.在接口中定义了一些常量
    //2.不同的常量的值表示不同的消息类型
    String MESSAGE_LOGIN_SUCCEED = "1";//表示登录成功
    String MESSAGE_LOGIN_FAIL = "2";//表示登录失败
    String MESSAGE_COMM_MES = "3";//普通信息包
    String MESSAGE_GET_ONLINE_FRIEND = "4";//要求返回在线用户列表
    String MESSAGE_RET_ONLINE_FRIEND = "5";//返回在线用户列表
    String MESSAGE_CLIENT_EXIT = "6";//客户端请求退出
    String MESSAGE_TO_ALL_MES = "7";//群发消息
    String MESSAGE_FILE_ALL_MES = "8";//发送文件
}

```



```java
package com.momo.qqcommon;

import java.io.Serializable;

/**
 * @author momo~
 * @version 1.0
 * 表示一个用户/客户信息
 */
public class User implements Serializable {
    private static final long serialVersionUID = 1L;
    private String userId;//用户名/用户id
    private String passwd;//用户密码

    public User() {
        this.userId = userId;
        this.passwd = passwd;
    }

    public String getUserId() {
        return userId;
    }

    public void setUserId(String userId) {
        this.userId = userId;
    }

    public String getPasswd() {
        return passwd;
    }

    public void setPasswd(String passwd) {
        this.passwd = passwd;
    }
}

```



服务端代码：

```java
package com.momo.qqcommon;

import java.io.Serializable;

/**
 * @author momo~
 * @version 1.0
 * 表示客户端和服务器端通信时的消息对象
 */
public class Message implements Serializable {
    private static final long serialVersionUID = 1L;
    private String sender;//发送方
    private String getter;//接收方
    private String content;//消息内容
    private String sendTime;//发送时间
    private String mesType;//消息类型【可以在接口中定义】

    //进行文件相关字段扩展
    private byte[] fileByte;
    private int fileLen = 0;
    private String dest;//目标文件路径
    private String src;//源文件路径

    public byte[] getFileByte() {
        return fileByte;
    }

    public void setFileByte(byte[] fileByte) {
        this.fileByte = fileByte;
    }

    public int getFileLen() {
        return fileLen;
    }

    public void setFileLen(int fileLen) {
        this.fileLen = fileLen;
    }

    public String getDest() {
        return dest;
    }

    public void setDest(String dest) {
        this.dest = dest;
    }

    public String getSrc() {
        return src;
    }

    public void setSrc(String src) {
        this.src = src;
    }

    public String getSender() {
        return sender;
    }

    public void setSender(String sender) {
        this.sender = sender;
    }

    public String getGetter() {
        return getter;
    }

    public void setGetter(String getter) {
        this.getter = getter;
    }

    public String getContent() {
        return content;
    }

    public void setContent(String content) {
        this.content = content;
    }

    public String getSendTime() {
        return sendTime;
    }

    public void setSendTime(String sendTime) {
        this.sendTime = sendTime;
    }

    public String getMesType() {
        return mesType;
    }

    public void setMesType(String mesType) {
        this.mesType = mesType;
    }
}

```



```java
package com.momo.qqcommon;

/**
 * @author momo~
 * @version 1.0
 */
public interface MessageType {
    //1.在接口中定义了一些常量
    //2.不同的常量的值表示不同的消息类型
    String MESSAGE_LOGIN_SUCCEED = "1";//表示登录成功
    String MESSAGE_LOGIN_FAIL = "2";//表示登录失败
    String MESSAGE_COMM_MES = "3";//普通信息包
    String MESSAGE_GET_ONLINE_FRIEND = "4";//要求返回在线用户列表
    String MESSAGE_RET_ONLINE_FRIEND = "5";//返回在线用户列表
    String MESSAGE_CLIENT_EXIT = "6";//客户端请求退出
    String MESSAGE_TO_ALL_MES = "7";//群发消息
    String MESSAGE_FILE_ALL_MES = "8";//发送文件

}

```



```java
package com.momo.qqcommon;

import java.io.Serializable;

/**
 * @author momo~
 * @version 1.0
 * 表示一个用户/客户信息
 */
public class User implements Serializable {
    private static final long serialVersionUID = 1L;
    private String userId;//用户名/用户id
    private String passwd;//用户密码

    public User(String userId, String passwd) {
        this.userId = userId;
        this.passwd = passwd;
    }

    public String getUserId() {
        return userId;
    }

    public void setUserId(String userId) {
        this.userId = userId;
    }

    public String getPasswd() {
        return passwd;
    }

    public void setPasswd(String passwd) {
        this.passwd = passwd;
    }
}

```





```java
package com.momo.QQDFrame;

import com.momo.qqserver.server.QQServer;

import java.io.IOException;

/**
 * @author momo~
 * @version 1.0\
 * 该类创建QQServer对象，启动后台的服务
 */
public class QQFrame {
    public static void main(String[] args) throws IOException, ClassNotFoundException {
        new QQServer();
    }
}

```





```java
package com.momo.qqserver.server;

import java.util.HashMap;
import java.util.Iterator;

/**
 * @author momo~
 * @version 1.0
 * 该类用于管理和客户端通讯的线程
 */
public class ManageClientThreads {
    private static HashMap<String,ServerConnectClientThread> hm = new HashMap<>();

    //返回hm
    public static HashMap<String, ServerConnectClientThread> getHm() {
        return hm;
    }

    //添加线程对象到集合中
    public static void addClientThread(String userId,ServerConnectClientThread serverConnectClientThread){
        hm.put(userId, serverConnectClientThread);
    }

    //根据userId返回serverConnectClientThread线程
    public static ServerConnectClientThread getServerConnectClientThread(String userId){
        return hm.get(userId);
    }

    //编写方法返回在线用户列表
    public static String getOnlineUser(){
        //集合遍历
        //取出所有key，通过key取出value
        Iterator<String> iterator = hm.keySet().iterator();
        String onlineUserList = "";
        while (iterator.hasNext()){
            onlineUserList += iterator.next().toString() + " ";
        }
        return onlineUserList;
    }

    //从集合中删除
    public static void removeServerConnectClientThread(String userId){
        hm.remove(userId);
    }


}

```





```java
package com.momo.qqserver.server;

import com.momo.qqcommon.Message;
import com.momo.qqcommon.MessageType;
import com.momo.qqcommon.User;

import java.io.IOException;
import java.io.ObjectInputStream;
import java.io.ObjectOutputStream;
import java.net.ServerSocket;
import java.net.Socket;
import java.util.HashMap;

/**
 * @author momo~
 * @version 1.0
 * 这里是服务器，在监听9999端口，等待客户端连接，并且保持通讯
 */
public class QQServer {
    private ServerSocket ss = null;

    //创建一个集合，存放多个用户，如果是这些用户登录，就认为合法
    private static HashMap<String,User> validUser = new HashMap<>();

    static {//静态代码块，初始化validUsers
        validUser.put("100",new User("100","123456"));
        validUser.put("200",new User("200","123456"));
        validUser.put("300",new User("300","123456"));
        validUser.put("至尊宝",new User("至尊宝","123456"));
        validUser.put("紫霞仙子",new User("紫霞仙子","123456"));
    }

    //验证用户是否有效的方法
    private boolean checkUsers(String userId,String passwd){
        User user = validUser.get(userId);
        //用户不存在
        if (user == null){
            return false;
        }
        if (!user.getPasswd().equals(passwd)){
            return false;
        }
        return true;
    }

    public QQServer() throws IOException, ClassNotFoundException {
        System.out.println("服务端在9999端口监听");
        //启动推送新闻的线程
        new Thread(new SendNewsToAllService()).start();
        ss = new ServerSocket(9999);

        while (true){ //当和某个客户端连接后会继续监听
            Socket socket = ss.accept();
            //得到socket管理的对象输入流
            ObjectInputStream ois = new ObjectInputStream(socket.getInputStream());
            User u = (User) ois.readObject();//读取客户端发送的user对象

            //得到socket关联的对象输出流
            ObjectOutputStream oos = new ObjectOutputStream(socket.getOutputStream());

            //创建一个Message对象，准备回复客户端
            Message message = new Message();

            //验证
            if (checkUsers(u.getUserId(),u.getPasswd())){
                message.setMesType(MessageType.MESSAGE_LOGIN_SUCCEED);
                //将Message对象回复给客户端
                oos.writeObject(message);
                //创建一个线程，和客户端保持通讯，该线程需要持有socket对象
                ServerConnectClientThread serverConnectClientThread = new ServerConnectClientThread(socket, u.getUserId());
                //启动线程
                serverConnectClientThread.start();
                //把线程对象放入集合中管理
                ManageClientThreads.addClientThread(u.getUserId(), serverConnectClientThread);
            } else { //登录失败
                System.out.println("用户id="+ u.getUserId() + "pwd=" + u.getPasswd() + "登录失败");
                message.setMesType(MessageType.MESSAGE_LOGIN_FAIL);
                oos.writeObject(message);
                //管理socket
//                socket.close();
            }
//            ss.close();
        }
    }
}

```



```java
package com.momo.qqserver.server;

import com.momo.qqcommon.Message;
import com.momo.qqcommon.MessageType;
import com.momo.utils.Utility;

import java.io.IOException;
import java.io.ObjectOutputStream;
import java.util.Date;
import java.util.HashMap;
import java.util.Iterator;
import java.util.Scanner;

/**
 * @author momo~
 * @version 1.0
 */
public class SendNewsToAllService implements Runnable{

    @Override
    public void run() {

        //为了可以推送多次新闻
        while (true) {
            System.out.println("请输入服务器要推送的新闻/消息[exit退出推送]");
            String news = Utility.readString(100);
            if ("exit".equals(news)){
                break;
            }
            //构建一个消息
            Message message = new Message();
            message.setMesType(MessageType.MESSAGE_TO_ALL_MES);
            message.setSender("服务器");
            message.setContent(news);
            message.setSendTime(new Date().toString());
            System.out.println("服务器推送消息：" + news);

            //需要遍历 管理线程的集合。把所有线程的socket都得到
            HashMap<String, ServerConnectClientThread> hm = ManageClientThreads.getHm();
            Iterator iterator = hm.keySet().iterator();
            while (iterator.hasNext()) {
                //取出在线用户id
                String onlineUserId = iterator.next().toString();
                ObjectOutputStream oos = null;
                try {
                    oos = new ObjectOutputStream(hm.get(onlineUserId).getSocket().getOutputStream());
                    oos.writeObject(message);
                } catch (IOException e) {
                    throw new RuntimeException(e);
                }
            }
        }
    }
}

```





```java
package com.momo.qqserver.server;

import com.momo.qqcommon.Message;
import com.momo.qqcommon.MessageType;

import java.io.IOException;
import java.io.ObjectInputStream;
import java.io.ObjectOutputStream;
import java.io.Serializable;
import java.net.Socket;
import java.util.HashMap;
import java.util.Iterator;

/**
 * @author momo~
 * @version 1.0
 * 该类的某个对象和某个客户端保持通讯
 */
public class ServerConnectClientThread extends Thread{
    private Socket socket;
    private String userId;//连接到客户端的用户id

    public ServerConnectClientThread(Socket socket, String userId) {
        this.socket = socket;
        this.userId = userId;
    }

    public Socket getSocket() {
        return socket;
    }

    @Override
    public void run() {//发送接收消息
        while (true){
            System.out.println("服务端和客户端"+userId+"保持通讯，读取数据");
            try {
                ObjectInputStream ois = new ObjectInputStream(socket.getInputStream());
                Message message = (Message) ois.readObject();

                //根据message类型做相应业务处理
                if (message.getMesType().equals(MessageType.MESSAGE_GET_ONLINE_FRIEND)){
                    //客户端请求在线用户列表
                    System.out.println(message.getSender() + "请求在线用户列表");
                    String onlineUser = ManageClientThreads.getOnlineUser();
                    //返回message
                    //构建一个Message对象返回客户端
                    Message message2 = new Message();
                    message2.setMesType(MessageType.MESSAGE_RET_ONLINE_FRIEND);
                    message2.setContent(onlineUser);
                    message2.setGetter(message.getSender());

                    //返回客户端
                    ObjectOutputStream oos = new ObjectOutputStream(socket.getOutputStream());
                    oos.writeObject(message2);

                } else if (message.getMesType().equals(MessageType.MESSAGE_CLIENT_EXIT)) {
                    System.out.println(message.getSender() + "退出系统");
                    //将客户端对应的线程从集合中删除
                    ManageClientThreads.removeServerConnectClientThread(message.getSender());
                    socket.close();
                    //退出线程
                    break;
                } else if (message.getMesType().equals(MessageType.MESSAGE_COMM_MES)) {
                    //根据message获取getterid，然后得到对应线程
                    ServerConnectClientThread serverConnectClientThread = ManageClientThreads.getServerConnectClientThread(message.getGetter());
                    //得到对应socket对象对应对象输出流，将message对象转发给指定客户端
                    ObjectOutputStream oos = new ObjectOutputStream(serverConnectClientThread.getSocket().getOutputStream());
                    oos.writeObject(message);//转发，如果客户不在线，保存到数据库
                } else if (message.getMesType().equals(MessageType.MESSAGE_TO_ALL_MES)) {
                    //需要遍历 管理线程的集合。把所有线程的socket都得到
                    HashMap<String, ServerConnectClientThread> hm = ManageClientThreads.getHm();
                    Iterator iterator = hm.keySet().iterator();
                    while (iterator.hasNext()) {
                        //取出在线用户id
                        String onlineUserId =  iterator.next().toString();
                        if (!onlineUserId.equals(message.getSender())){
                            ObjectOutputStream oos = new ObjectOutputStream(hm.get(onlineUserId).getSocket().getOutputStream());
                            oos.writeObject(message);
                        }
                    }

                } else if (message.getMesType().equals(MessageType.MESSAGE_FILE_ALL_MES)) {
                    //根据getterid 获取对应的线程，将message对象转发
                    ServerConnectClientThread serverConnectClientThread = ManageClientThreads.getServerConnectClientThread(message.getGetter());
                    ObjectOutputStream oos = new ObjectOutputStream(serverConnectClientThread.getSocket().getOutputStream());
                    oos.writeObject(message);
                } else {
                    System.out.println("其他类型，暂时不处理");
                }
            } catch (IOException e) {
                throw new RuntimeException(e);
            } catch (ClassNotFoundException e) {
                throw new RuntimeException(e);
            }
        }
    }
}

```





```java
package com.momo.utils;

/**
 工具类的作用:
 处理各种情况的用户输入，并且能够按照程序员的需求，得到用户的控制台输入。
 */

import java.util.Scanner;

/**

 */
public class Utility {
    //静态属性。。。
    private static Scanner scanner = new Scanner(System.in);


    /**
     * 功能：读取键盘输入的一个菜单选项，值：1——5的范围
     * @return 1——5
     */
    public static char readMenuSelection() {
        char c;
        for (; ; ) {
            String str = readKeyBoard(1, false);//包含一个字符的字符串
            c = str.charAt(0);//将字符串转换成字符char类型
            if (c != '1' && c != '2' &&
                    c != '3' && c != '4' && c != '5') {
                System.out.print("选择错误，请重新输入：");
            } else break;
        }
        return c;
    }

    /**
     * 功能：读取键盘输入的一个字符
     * @return 一个字符
     */
    public static char readChar() {
        String str = readKeyBoard(1, false);//就是一个字符
        return str.charAt(0);
    }
    /**
     * 功能：读取键盘输入的一个字符，如果直接按回车，则返回指定的默认值；否则返回输入的那个字符
     * @param defaultValue 指定的默认值
     * @return 默认值或输入的字符
     */

    public static char readChar(char defaultValue) {
        String str = readKeyBoard(1, true);//要么是空字符串，要么是一个字符
        return (str.length() == 0) ? defaultValue : str.charAt(0);
    }

    /**
     * 功能：读取键盘输入的整型，长度小于2位
     * @return 整数
     */
    public static int readInt() {
        int n;
        for (; ; ) {
            String str = readKeyBoard(10, false);//一个整数，长度<=10位
            try {
                n = Integer.parseInt(str);//将字符串转换成整数
                break;
            } catch (NumberFormatException e) {
                System.out.print("数字输入错误，请重新输入：");
            }
        }
        return n;
    }
    /**
     * 功能：读取键盘输入的 整数或默认值，如果直接回车，则返回默认值，否则返回输入的整数
     * @param defaultValue 指定的默认值
     * @return 整数或默认值
     */
    public static int readInt(int defaultValue) {
        int n;
        for (; ; ) {
            String str = readKeyBoard(10, true);
            if (str.equals("")) {
                return defaultValue;
            }

            //异常处理...
            try {
                n = Integer.parseInt(str);
                break;
            } catch (NumberFormatException e) {
                System.out.print("数字输入错误，请重新输入：");
            }
        }
        return n;
    }

    /**
     * 功能：读取键盘输入的指定长度的字符串
     * @param limit 限制的长度
     * @return 指定长度的字符串
     */

    public static String readString(int limit) {
        return readKeyBoard(limit, false);
    }

    /**
     * 功能：读取键盘输入的指定长度的字符串或默认值，如果直接回车，返回默认值，否则返回字符串
     * @param limit 限制的长度
     * @param defaultValue 指定的默认值
     * @return 指定长度的字符串
     */

    public static String readString(int limit, String defaultValue) {
        String str = readKeyBoard(limit, true);
        return str.equals("")? defaultValue : str;
    }


    /**
     * 功能：读取键盘输入的确认选项，Y或N
     * 将小的功能，封装到一个方法中.
     * @return Y或N
     */
    public static char readConfirmSelection() {
        System.out.println("请输入你的选择(Y/N): 请小心选择");
        char c;
        for (; ; ) {//无限循环
            //在这里，将接受到字符，转成了大写字母
            //y => Y n=>N
            String str = readKeyBoard(1, false).toUpperCase();
            c = str.charAt(0);
            if (c == 'Y' || c == 'N') {
                break;
            } else {
                System.out.print("选择错误，请重新输入：");
            }
        }
        return c;
    }

    /**
     * 功能： 读取一个字符串
     * @param limit 读取的长度
     * @param blankReturn 如果为true ,表示 可以读空字符串。
     * 					  如果为false表示 不能读空字符串。
     *
     *	如果输入为空，或者输入大于limit的长度，就会提示重新输入。
     * @return
     */
    private static String readKeyBoard(int limit, boolean blankReturn) {

        //定义了字符串
        String line = "";

        //scanner.hasNextLine() 判断有没有下一行
        while (scanner.hasNextLine()) {
            line = scanner.nextLine();//读取这一行

            //如果line.length=0, 即用户没有输入任何内容，直接回车
            if (line.length() == 0) {
                if (blankReturn) return line;//如果blankReturn=true,可以返回空串
                else continue; //如果blankReturn=false,不接受空串，必须输入内容
            }

            //如果用户输入的内容大于了 limit，就提示重写输入
            //如果用户如的内容 >0 <= limit ,我就接受
            if (line.length() < 1 || line.length() > limit) {
                System.out.print("输入长度（不能大于" + limit + "）错误，请重新输入：");
                continue;
            }
            break;
        }

        return line;
    }
}


```





## 18. 反射

![image-20220829165253250](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062328009.png)



```java
package com.momo.reflection.question;

import com.momo.Cat;

import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.lang.reflect.InvocationTargetException;
import java.lang.reflect.Method;
import java.util.Properties;

/**
 * @author momo~
 * @version 1.0
 * 反射问题引入
 */
public class ReflectionQuestion {
    public static void main(String[] args) throws IOException, ClassNotFoundException, InstantiationException, IllegalAccessException, InvocationTargetException, NoSuchMethodException {
        //根据配置文件re.properties指定信息，创建cat对象并调用方法hi

        //传统的方法，new对象-》调用方法
//        Cat cat = new Cat();
//        cat.hi();

        //反射
        //1.使用Properties类，可以读写配置文件
        Properties properties = new Properties();
        properties.load(new FileInputStream("src\\re.properties"));
        String classfullpath = properties.get("classfullpath").toString();
        String method = properties.get("method").toString();
        System.out.println("classfullpath=" + classfullpath);
        System.out.println("method=" + method);

        //2.创建对象，传统的方法不可行，需要使用反射
        //加载类，返回class类型的对象
        Class<?> aClass = Class.forName(classfullpath);
        //通过aClass得到加载的类com.momo.Cat的对象实例
        Object o = aClass.newInstance();
        //通过aClass得到加载的类com.momo.Cat的method的方法对象
        //在反射中，可以将方法视为对象（万物皆对象）
        Method method1 = aClass.getMethod(method);
        //通过method1调用方法：即通过方法对象来实现调用方法
        System.out.println("====================");
        method1.invoke(0);//传统方法 对象.方法（） ，反射机制 反射.invoke（对象）
    }
}

```



### **1.反射原理**

![image-20220829173609599](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062328827.png)



![image-20220901093238684](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062328353.png)



### **2.反射相关类**

![image-20220901093346842](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062328803.png)



![image-20220901093733939](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062328534.png)



```java
        //java.lang.reflect.Filed:代表类的成员变量
        //得到name字段
        //getField不能得到私有属性
        Field age = aClass.getField("age");
        System.out.println(age.get(0));//传统写法 对象.成员变量  反射：成员变量对象.get(对象)

        //java.lang.reflect.Constructor:代表类的构造方法，Constructor表示构造器
        Constructor<?> constructor = aClass.getConstructor();
        System.out.println(constructor);//无参构造器 Cat()

        Constructor<?> constructor1 = aClass.getConstructor(String.class);
        System.out.println(constructor1);//有参构造器 Cat(String name)
```



### **3.反射调用优化 **  setAccessible(true)![image-20220901101915151](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062359163.png)

![image-20220901095729117](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062328336.png)



![image-20220901100555837](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062328003.png)



```java
package com.momo.reflection.question;

import com.momo.Cat;

import java.lang.reflect.Method;

/**
 * @author momo~
 * @version 1.0
 * 测试反射调用的性能和优化方案
 */
public class ReflectionPlus {
    public static void main(String[] args) throws Exception {
        m1();
        m2();
        m3();
    }

    //传统方法调用hi
    public static void m1(){
        Cat cat = new Cat();
        long start = System.currentTimeMillis();
        for (int i = 0; i < 90000000; i++) {
            cat.hi();
        }
        long end = System.currentTimeMillis();
        System.out.println("m1时间：" + (end - start));
    }

    //反射机制调用方法hi
    public static void m2() throws Exception {
        Class<?> aClass = Class.forName("com.momo.Cat");
        Object o = aClass.newInstance();
        Method hi = aClass.getMethod("hi");
        long start = System.currentTimeMillis();
        for (int i = 0; i < 90000000; i++) {
            hi.invoke(o);
        }
        long end = System.currentTimeMillis();
        System.out.println("m2时间：" + (end - start));
    }

    //反射调用优化，关闭访问检查
    public static void m3() throws Exception {
        Class<?> aClass = Class.forName("com.momo.Cat");
        Object o = aClass.newInstance();
        Method hi = aClass.getMethod("hi");
        hi.setAccessible(true);
        long start = System.currentTimeMillis();
        for (int i = 0; i < 90000000; i++) {
            hi.invoke(o);
        }
        long end = System.currentTimeMillis();
        System.out.println("m2时间：" + (end - start));
    }
}

```



### **4.Class类分析**

![image-20220901102302719](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062328417.png)





![image-20220901103902226](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062328691.png)





![image-20220901103933890](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062328905.png)



![image-20220901103839999](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062328420.png)



### **5.class常用方法**

```java
package com.momo.reflection.class_;

import com.momo.Car;

import javax.jws.soap.SOAPBinding;
import java.lang.reflect.Field;

/**
 * @author momo~
 * @version 1.0
 * 演示class类的常用方法
 */
public class Class01 {
    public static void main(String[] args) throws ClassNotFoundException, InstantiationException, IllegalAccessException, NoSuchFieldException {
        String classAllPath = "com.momo.Car";
        //获取Car类对应的Class对象
        //<?> 表示不确定的java类型
        Class<?> aClass = Class.forName(classAllPath);
        //输出 class com.momo.Car
        System.out.println(aClass);//显示是哪个类的Class对象 即：
        //class java.lang.Class
        System.out.println(aClass.getClass());//显示运行类型
        //得到包名 com.momo
        System.out.println(aClass.getPackage().getName());
        //得到全类名 com.momo.Car
        System.out.println(aClass.getName());
        //创建对象实例
        Car car = (Car) aClass.newInstance();
        System.out.println(car);//car.toString()
        //通过反射获取属性
        Field brand = aClass.getField("brand");
        System.out.println(brand.get(car));//宝马，如果是私有属性则报错
        //通过反射给属性复赋值
        brand.set(car,"奔驰");
        System.out.println(brand.get(car));
        //遍历得到所有的属性
        for (Field field : aClass.getFields()) {
            System.out.println(field.getName());
        }
    }
}
```



### **6.获取Class对象的六种方式**

![image-20220903170127854](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062329159.png)



![image-20220903170205935](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062329011.png)



```java
package com.momo.reflection.class_;

import com.momo.Car;

/**
 * @author momo~
 * @version 1.0
 * 演示得到Class对象的各种方式（6）
 */
public class GetClass_ {
    public static void main(String[] args) throws ClassNotFoundException {
        //1.Class.getName
        //通过配置文件读取
        String classAllPath = "com.momo.Car";
        Class<?> aClass1 = Class.forName(classAllPath);

        //2.类名.class 应用场景：用于参数传递
        Class<Car> aClass2 = Car.class;

        //3.对象.getClass() 应用场景，有对象实例
        Car car = new Car();
        Class<? extends Car> aClass3 = car.getClass();

        //4.通过类加载器【4种】来获取到类的Class对象
        //得到类加载器
        ClassLoader classLoader = car.getClass().getClassLoader();
        //通过类加载器得到Class对象
        Class<?> aClass4 = classLoader.loadClass(classAllPath);

        //aClass1、aClass2、aClass3、aClass4其实是同一个对象
        System.out.println(aClass1.hashCode());
        System.out.println(aClass2.hashCode());
        System.out.println(aClass3.hashCode());
        System.out.println(aClass4.hashCode());

        //5.基本数据类型(byte,short,int,long,float,double,char,boolean)得到Class类对象
        Class<Integer> integerClass = int.class;
        Class<Character> characterClass = char.class;
        Class<Boolean> booleanClass = boolean.class;
        System.out.println(integerClass);

        //6.基本数据类型对应的包装类，可以通过.TYPE得到Class类对象
        Class<Integer> type = Integer.TYPE;
        Class<Character> type1 = Character.TYPE;
        System.out.println(type);
    }
}

```



![image-20220903172942189](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062329084.png)



```java
package com.momo.reflection.class_;

import java.io.Serializable;

/**
 * @author momo~
 * @version 1.0
 * 演示哪些类型有Class对象
 */
public class AllTypeClass {
    public static void main(String[] args) {

        Class<String> aClass01 = String.class;//外部类
        Class<Serializable> aClass02 = Serializable.class;//接口
        Class<Integer> aClass03 = Integer.class;//包装类
        Class<float[][]> aClass04 = float[][].class;//二维数组
        Class<Deprecated> aClass05 = Deprecated.class;//注解
        Class<Thread.State> aClass06 = Thread.State.class;//枚举
        Class<Long> aClass07 = long.class;//基本数据类型
        Class<Void> aClass08 = void.class;//void数据类型
        Class<Class> aClass09 = Class.class;

        System.out.println(aClass01);
        System.out.println(aClass02);
        System.out.println(aClass03);
        System.out.println(aClass04);
        System.out.println(aClass05);
        System.out.println(aClass06);
        System.out.println(aClass07);
        System.out.println(aClass08);
        System.out.println(aClass09);
    }
}

```



### **7.动态和静态加载**



![image-20220903180414142](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062329390.png)



```java
package com.momo.reflection.class_;

import java.lang.reflect.Method;
import java.util.Scanner;

/**
 * @author momo~
 * @version 1.0
 * 静态加载与动态加载
 */
public class RunStateLoader {
    public static void main(String[] args) throws Exception {
        Scanner scanner = new Scanner(System.in);
        System.out.println("请输入key：");
        String key = scanner.next();
        switch (key){
            case "1":
                //静态加载，必须编写Dog类且无报错
                //Dog dog = new Dog();
                //dog.cry();
                break;
            case "2":
                //动态加载，不执行则不报错
                Class<?> cls = Class.forName("Person");
                Object o = cls.newInstance();
                Method m = cls.getMethod("hi");
                m.invoke(0);
                System.out.println("ok");
                break;
            default:
                System.out.println("do nothing...");
        }
    }
}

```



### **8.类加载流程**

![image-20220903181017651](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062329190.png)



![image-20220903181504140](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062329385.png)



![image-20220909062536421](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062329438.png)



![image-20220909062913323](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062329093.png)



```java
package com.momo.reflection.classload_;

/**
 * @author momo~
 * @version 1.0
 */
public class ClassLoad01 {
    public static void main(String[] args) {

    }
}

class A{
    //属性/成员变量/字段
    //分析加载的连接阶段-准备
    //n1是实例属性，不是静态变量，因此在准备阶段不会分配内存
    //n2是静态变量，分配内存，n2默认初始化为0
    //n3是static final修饰，为常量，和静态变量不同，一旦赋值不再改变，n3=30
    public int n1 = 10;
    public static int n2 = 20;
    public static final int n3 = 30;
}

```





![image-20220909063818156](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062329681.png)



![image-20220909063830448](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062329688.png)



### 9.获取类结构信息



![image-20220909070046684](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062329226.png)



```java
package com.momo.reflection.question;

import org.junit.jupiter.api.Test;

import javax.jws.soap.SOAPBinding;
import java.lang.annotation.Annotation;
import java.lang.reflect.Constructor;
import java.lang.reflect.Field;
import java.lang.reflect.Method;

/**
 * @author momo~
 * @version 1.0
 * 演示如何通过反射获取类结构信息
 */
public class ReflectionUtils {
    public static void main(String[] args) {

    }

    //API
    @Test
    public void api_01() throws Exception {
        //获取Class对象
        Class<?> aClass = Class.forName("com.momo.reflection.question.Person");
        //获取全类名
        System.out.println(aClass.getName());//com.momo.reflection.question.Person
        //获取简单类名
        System.out.println(aClass.getSimpleName());//Person
        //获取所有public修饰的属性，包含本类及父类
        for (Field field : aClass.getFields()) {
            System.out.println("本类及父类的属性：" + field.getName());
        }
        //获取本类中所有属性
        for (Field declaredField : aClass.getDeclaredFields()) {
            System.out.println("本类的所有属性：" + declaredField.getName());
        }
        //获取所有public修饰的方法，包含本类以及父类的
        for (Method method : aClass.getMethods()) {
            System.out.println("本类及父类的方法：" + method.getName());
        }
        //获取本类中所有的方法
        for (Method declaredMethod : aClass.getDeclaredMethods()) {
            System.out.println("本类的所有方法：" + declaredMethod.getName());
        }
        //获取所有public修饰的构造器
        for (Constructor<?> constructor : aClass.getConstructors()) {
            System.out.println("本类的构造器：" + constructor.getName());
        }
        //获取本类中所有构造器
        for (Constructor<?> declaredConstructor : aClass.getDeclaredConstructors()) {
            System.out.println("本类所有构造器：" + declaredConstructor.getName());
        }
        //以Package形式返回包信息
        System.out.println(aClass.getPackage());//com.momo.reflection.question
        //以Class形式返回父类信息
        System.out.println(aClass.getSuperclass());//com.momo.reflection.question.A
        //以Class[]形式返回接口信息
        for (Class<?> anInterface : aClass.getInterfaces()) {
            System.out.println("接口信息：" + anInterface);
        }
        //以Annotation[]形式返回注解信息
        for (Annotation annotation : aClass.getAnnotations()) {
            System.out.println("注解信息：" + annotation);
        }
    }
}

class A{
    public String hobby;
    public void hi(){};
}

interface IA{
}

interface IB{
}

@Deprecated
class Person extends A implements IA,IB{
    //属性
    public String name;
    protected int age;
    String job;
    private double sal;

    public Person(){}
    public Person(String name){}

    //方法
    public void m1(){

    }

    protected void m2(){

    }

    void m3(){

    }

    private void m4(){

    }
}

```



com.momo.reflection.question.Person
Person
本类及父类的属性：name
本类及父类的属性：hobby
本类的所有属性：name
本类的所有属性：age
本类的所有属性：job
本类的所有属性：sal
本类及父类的方法：m1
本类及父类的方法：hi
本类及父类的方法：wait
本类及父类的方法：wait
本类及父类的方法：wait
本类及父类的方法：equals
本类及父类的方法：toString
本类及父类的方法：hashCode
本类及父类的方法：getClass
本类及父类的方法：notify
本类及父类的方法：notifyAll
本类的所有方法：m1
本类的所有方法：m2
本类的所有方法：m4
本类的所有方法：m3
本类的构造器：com.momo.reflection.question.Person
本类的构造器：com.momo.reflection.question.Person
本类所有构造器：com.momo.reflection.question.Person
本类所有构造器：com.momo.reflection.question.Person
package com.momo.reflection.question
class com.momo.reflection.question.A
接口信息：interface com.momo.reflection.question.IA
接口信息：interface com.momo.reflection.question.IB
注解信息：@java.lang.Deprecated()





![image-20220909075742959](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062329274.png)





![image-20220909075723323](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062329871.png)



![image-20220909075802016](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062329417.png)



```java
@Test
    public void api_02() throws Exception {
        Class<?> aClass = Class.forName("com.momo.reflection.question.Person");
        for (Field declaredField : aClass.getDeclaredFields()) {
            System.out.println("本类中所有属性：" + declaredField.getName()
            + "该属性修饰符值：" + declaredField.getModifiers()
            + "该属性类型：" + declaredField.getType());
        }

        for (Method declaredMethod : aClass.getDeclaredMethods()) {
            System.out.println("本类中所有方法：" + declaredMethod.getName()
            + "该方法访问修饰符值：" + declaredMethod.getModifiers()
            + "该方法返回类型：" + declaredMethod.getReturnType());

            //输出当前方法形参数组情况
            for (Class<?> parameterType : declaredMethod.getParameterTypes()) {
                System.out.println("该方法的形参类型=" + parameterType);
            }
        }

        for (Constructor<?> declaredConstructor : aClass.getDeclaredConstructors()) {
            System.out.println("本类中所有构造器：" + declaredConstructor.getName());
            for (Class<?> parameterType : declaredConstructor.getParameterTypes()) {
                System.out.println("该构造器形参类型：" + parameterType);
            }
        }
    }
```



### 10.反射暴破

![image-20220909080916043](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062330573.png)



```java
package com.momo.reflection;

import java.lang.reflect.Constructor;

/**
 * @author momo~
 * @version 1.0
 * 演示通过反射机制创建对象
 */
public class ReflectCreateInstance {
    public static void main(String[] args) throws Exception {
        //通过User类的Class对象
        Class<?> aClass = Class.forName("com.momo.reflection.User");
        //通过public的无参构造器创建实例
        Object o = aClass.newInstance();
        System.out.println(o);
        //通过public的有参构造器创建实例
        Constructor<?> constructor = aClass.getConstructor(String.class);
        Object user01 = constructor.newInstance("milan");
        System.out.println(user01);
        //通过非public的有参构造器创建实例
        Constructor<?> declaredConstructor = aClass.getDeclaredConstructor(int.class, String.class);
        declaredConstructor.setAccessible(true);//暴破，使用反射可以访问private修饰符
        Object user02 = declaredConstructor.newInstance(22, "tom");
        System.out.println(user02);

    }
}
class User{
    private int age = 10;
    private String name = "momo";

    public User(){
    }

    public User(String name){
        this.name = name;
    }

    private User(int age,String name){
        this.name = name;
        this.age = age;
    }

    public String toString(){
        return "User [age=" + age + ",name:" + name + "]";
    }
}
```



![image-20220909082752622](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062330046.png)



```java
package com.momo.reflection;

import java.lang.reflect.Field;

/**
 * @author momo~
 * @version 1.0
 * 演示反射操作属性
 */
public class ReflectAccessProperty {
    public static void main(String[] args) throws Exception {
        //得到Student类对应的Class对象
        Class<?> aClass = Class.forName("com.momo.reflection.Student");
        //创建对象
        Object o = aClass.newInstance();
        //使用反射得到age属性对象
        Field age = aClass.getField("age");
        age.set(o,88);//通过反射操作属性
        System.out.println(o);

        //使用反射操作name属性
        Field name = aClass.getDeclaredField("name");
        name.setAccessible(true);//对name进行爆破，进行操作
        name.set(o,"momo");
        System.out.println(o);
    }
}

class Student{
    public int age;
    private static String name;

    public Student(){
    }

    @Override
    public String toString() {
        return "Student{" +
                "age=" + age +
                ", name='" + name + '\'' +
                '}';
    }
}


```



![image-20220909084134419](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062330944.png)



```java
package com.momo.reflection;

import java.lang.reflect.Method;

/**
 * @author momo~
 * @version 1.0
 * 演示通过反射调用方法
 */
public class ReflectAccessMethod {
    public static void main(String[] args) throws Exception {

        //1.得到Boss类对应的Class对象
        Class<?> aClass = Class.forName("com.momo.reflection.Boss");
        //2.创建对象
        Object o = aClass.newInstance();
        //3.1 调用public的hi方法
        Method hi = aClass.getMethod("hi", String.class);
        //3.2 调用
        hi.invoke(o, "momo");
        //4.1 调用private static 方法
        Method say = aClass.getDeclaredMethod("say", int.class, String.class, char.class);
        //暴破
        say.setAccessible(true);
        say.invoke(o,15,"milan",'男');
        //因为是静态方法
        System.out.println(say.invoke(null,200,"tom",'女'));
        //在反射中，如果方法有返回值，统一返回Object,但运行类型与方法定义类型一致
        Object o1 = say.invoke(o, 300, "tom", '男');
        
    }
}
class Boss{
    public int age;
    private static String name;

    public Boss(){}

    private static String say(int n,String s,char c){
        return n + " " + s + " " + c;
    }

    public void hi(String s){
        System.out.println("hi" + s);
    }
}
```





### 11.课后



![image-20220909085802054](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062330465.png)



```java
package com.momo.reflection;

import java.lang.reflect.Field;
import java.lang.reflect.Method;

/**
 * @author momo~
 * @version 1.0
 */
public class Homework01 {
    public static void main(String[] args) throws Exception {
        Class<?> aClass = Class.forName("com.momo.reflection.PrivateTest");
        Object o = aClass.newInstance();
        Field name = aClass.getDeclaredField("name");
        name.setAccessible(true);
        name.set(o,"momo");
        Method getName = aClass.getMethod("getName");
        Object invoke = getName.invoke(o);
        System.out.println(invoke);
    }
}

class PrivateTest{
    private String name = "hellokitty";

    public String getName() {
        return name;
    }

}

```



![image-20220909091137271](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062330464.png)



```java
package com.momo.reflection;

import java.io.File;
import java.lang.reflect.Constructor;

/**
 * @author momo~
 * @version 1.0
 */
public class Homework02 {
    public static void main(String[] args) throws Exception {
        Class<?> aClass = Class.forName("java.io.File");
        for (Constructor<?> declaredConstructor : aClass.getDeclaredConstructors()) {
            System.out.println(declaredConstructor);
        }

        Constructor<?> constructor = aClass.getConstructor(String.class);
        File file = (File) constructor.newInstance("E:\\mynew.txt");
        file.createNewFile();
    }
}

```



## 19. MySQL基础

### 1.数据库作用

![image-20220910124901995](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062330052.png)



![image-20220910124926103](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062330612.png)



![image-20220910124938744](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062330129.png)



### 2.数据库安装与卸载

![image-20220910140140240](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062330262.png)

https://blog.csdn.net/qq_59636442/article/details/123058454

https://zhuanlan.zhihu.com/p/86650613?from_voters_page=true



卸载

https://blog.csdn.net/q556672239/article/details/88626950

net start ***mysql***    开启服务

net stop ***mysql***    停止服务

sc delete ***mysql***    删除服务



![image-20220910141157832](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062330176.png)





![image-20220910141737523](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062330548.png)





### 3.图形化管理软件

![image-20220910141937202](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062330191.png)



破解：http://www.itmind.net/17781.html



### 4.MySQL三层结构

![image-20220910153526070](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062330776.png)





![image-20220910154247675](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062330360.png)



![image-20220910154952544](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062331777.png)





![image-20220910155043854](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062331601.png)



### 5.MySQL三层架构

对于数据库的认识，相信很大一部分人像我一样只停留在写各种SQL、优化各种查询语句以及索引的建立之上，只是停留在“会用”的基础上。但是如果想要充分发挥MySQL的性能，就必须要了解其作为最流行的关系型数据库背后的各种优秀设计思想和特点，只有这样才能更好的使用它。

        目前最普遍的认识是将MySQL分为三层，正如标题所写的连接认证，解析优化和存储引擎。每一层的作用各不相同，但是各个之间是相互协同，相互依存的关系。可以先看下图的各个组件协同工作的架构图,然后再来深入分析各层之间的作用。

![image-20220910160154338](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062331094.png)

#### 一、连接认证

​        这一层提供的服务并不是MySQL所独有的，大多数基于网络的客户端/服务器的工具或服务都有类似的架构，所以参考这些架构，就可以清楚的了解到在这层MySQL的作用——连接处理、授权认证等。

        对于连接，并不是每一个客户端连接成功后服务器会创建一个新的线程，用完则销毁。事实上，服务端会提前帮我们缓存一部分线程，并不需要频繁的去创建或销毁线程。而且这个参数也是可以通过配置文件thread_cache_size参数来控制线程的数量。当一个客户端连接成功后会由服务器分配一个线程给这个客户端，这个客户端连接的查询只会在分配的这个线程中单独使用。
    
        授权认证是指当一个客户端或者应用连接到MySQL服务器时，服务器会先对其进行身份的认证，认证的方式最普遍的就是使用用户名+主机地址+密码的方式进行认证。当然也有通过证书进行认证连接，如下图的Navicat连接MySQL所示。



         认证完成以后，并不是你就能进入到下一步的操作，此时服务器仍然会继续进行校验，即对客户端提交的语句验证该客户端是否具有执行该语句的权限，例如是否允许对数据库（mysql）中的表（user）执行select语句的权限。

#### 二、编译优化

​       这一层可以说是MySQL的核心服务，因为在这一层中MySQL主要做的就是查询解析、分析、优化、缓存以及内置函数（日期、时间）等。而且涉及到跨存储引擎的功能（存储过程、触发器、试图）也是在这一层实现的。 

        一条查询语句的执行，首先服务器会去缓存中查询，如果能够找到对应的查询，服务器就不必再执行查询解析、优化和执行的整个过程，而是直接返回查询缓存中的结果集。反之，下一步就会进行SQL解析。MySQL在解析查询的同时，会创建内部的解析树，然后对其进行各种优化，包括重写查询、决定表的读取顺序以及选择合适的索引等。当然我们也可以通过特殊的关键字来提示优化器，人为影响它的决策过程，例如关键词STRAIGHT_JOIN、HIGH_PRIORITY等。当然我们也可以通过关键词来查看优化器解释（explain）优化过程的各个因素，从而知道如何进行优化决策，并提供一个参考的基准，便于用户重构查询和schema或者修改相关配置。
    
        在优化过程中，优化器并不会关心表是使用的什么存储引擎，但是存储引擎对于优化查询是存在影响的。优化器请求存储引擎提供容量或某个具体操作的开销信息，以及表数据的统计信息等。例如，某些存储引擎的某种索引，可能对一些特定的查询有优化。

#### 三、存储引擎

​        存储引擎主要是负责MySQL中数据的存储和提取，采用的方式与文件系统管理的方式是大同小异的。MySQL会将每个数据库（schema）保存为数据目录下的一个子目录，创建表时，MySQL会在这个子目录下创建一个与表同名的.frm文件来保存表的定义，因此我们在学习的MySQL就知道MySQL中表的大小写在不同的系统上（Windows和Linux）是有区别的，这一切都是因为MySQL使用文件系统的目录和文件来保存数据库和表的定义。通过命令show variables like 'datadir'可以查看这些文件的存储地址。



         对于不同的存储引擎在保存数据和索引的方式是不同的，但是表的定义这些都是在MySQL服务层同一处理的，即在上面的第二层实现。可以通过命令show table status命令查看表的相关具体信息。具体的就不展开说明，只说明其中几个重要的。Engine是指明存储引擎的类型，这里默认的是使用InnoDB。Row_format是行的格式，可选项是Dynamic(行长度可变，包含可变长度字段，如VARCHAR2或BLOB)、Fixed（行长度固定的）、Compressed（只在压缩表中存在）。



1.InnoDB存储引擎
        InnoDB是MySQL 5.1后默认的存储引擎，之前是MyISAM。InnoDB有一个非常大的特点就是默认支持事务，它被设计来处理大量的短期事务。InnoDB的数据是存储在表空间中，也就是一系列的数据文件中（ibdata）。



         InnoDB采用MVCC来支持高并发，并且实现了四个标准的隔离级别。其默认级别是可重复读（Repeatable Read），并且通过间隙锁策略防止幻读的出现。间隙锁使得InnoDB不仅仅锁定查询涉及的行，还会多索引中的间隙进行锁定，以防止幻影行的插入。

2.MyISAM存储引擎
     MyISAM提供了大量的特性，包括全文索引、压缩、空间函数等，但是唯一的缺点就是不支持事务和行级锁。MyISAM会将表存储在两个文件中：数据文件和索引文件，分别以.MYD和.MYI为扩展名。在上面我们说过Row_format这个表属性，MyISAM会根据表的定义来决定哪种方式，MyISAM表可以存储的行记录数一般受限于可用的磁盘空间或操作系统中单个文件的最大尺寸。在MySQL5.0中，MyISAM表如果是变长行，则默认配置只能处理256TB的数据，因为指向数据记录的指针长度是6个字节。而早版本中，指针长度默认是4字节，所以只能处理4GB的数据。



         在上面的Row_format中的Compressed是针对与MyISAM，此类表数据在创建并导入以后，不会再进行修改操作，这就非常适合此种存储引擎。使用方式是使用myisampack对MyISAM表进行压缩。压缩表是不能进行修改的（除非先将表接触压缩，修改数据，然后再次压缩）。压缩表可以极大地减少磁盘空间占用，因此可以减少磁盘I/O,从而提升查询性能。

3.Archive存储引擎
        这种存储引擎只支持Insert和Select操作，这就非常适合记录日志型应用的。Archive引擎会缓存所有的写并利用zlib对插入的行进行压缩，所以比MyISAM表的磁盘I/O更少。但是每次Select查询都需要执行全表扫描。所以Archive类适合日志和数据采集类引用。

        另外Archive支持行级锁和专用的缓冲区，所以可以实现高并发的插入。在一个查询开始直到返回表中存在的所有行数之前，Archive引擎会阻止其他的Select执行，以实现一致性读。另外也实现了在批量插入在完成之前对读操作是不可见的。
    
        虽然存储引擎的种类有很多，但是服务器通过API与存储引擎进行通信，这些API屏蔽了不同存储引擎之间的差异，而且API包含了几十个底层函数，用于执行开始一个事务、根据主键提取一行记录的这些操作。存储引擎本身不会去解析SQL，而且不同存储引擎之间也不会进行通信，只是简单地响应上层服务器的请求。


### 6.Java操作数据库

![image-20220910160440135](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062331531.png)



```java
/**
 * @author momo~
 * @version 1.0
 * 演示Java操作数据库
 */
public class JavaMysql {
    public static void main(String[] args) throws Exception {
        Class.forName("com.mysql.jdbc.Driver");
        Connection connection = DriverManager.getConnection("jdbc:mysql://");
        String sql = "";
        Statement statement = connection.createStatement();
        statement.executeUpdate(sql);
        
        statement.cancel();
        connection.close();
        System.out.println("成功");
    }
}
```



### 7.库操作

#### 7.1 创建数据库

![image-20220910162707365](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062331638.png)



```mysql
#删除指定数据库
DROP DATABASE momo_db01
#创建数据库
CREATE DATABASE momo_db01
#创建一个使用utf8字符集的数据库
CREATE DATABASE momo_db02 CHARACTER SET utf8
#创建一个使用utf8字符集，并带校对规则的数据库

CREATE TABLE

CREATE TABLE `t1` (
  `id` INT NOT NULL,
  `name` VARCHAR(255) COLLATE utf8mb3_bin DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=INNODB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_bin

CREATE DATABASE momo_db03 CHARACTER SET utf8 `t2`
#校对规则 utf8_bin 区分大小写 utf8_general_ci 不区分大小写

#查询
SELECT * FROM t1 WHERE NAME = 'tom';
SELECT * FROM t2 WHERE NAME = 'tom';
```



#### 7.2 查询数据库

![image-20220910165145785](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062331599.png)



```mysql
#演示删除和查询数据库
#查看当前数据库服务器中的所有数据库
SHOW DATABASES;
#查看前面创建的数据库的定义信息
SHOW CREATE DATABASE db01

#在创建数据库或表时为了规避关键字使用反引号
CREATE DATABASE `create`;
DROP DATABASE `create`;

```



#### 7.3 备份恢复数据库及表

![image-20220910171334433](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062331402.png)



![image-20220910174905518](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062331821.png)



```mysql
#备份数据库
mysqldump -u root -p -B db01 db03 > D:\\benfen.sql
#删除数据库
DROP DATABASE db03;
#恢复数据
SOURCE D:\\benfen.sql

#备份表
mysqldump -u root -p db01 users > D:\\benfen.sql


```



### 8.表操作

#### 1 创建表

![image-20220911085736809](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062331842.png)



```mysql
CREATE DATABASE db02;
USE db02;
CREATE TABLE `user`(
      id INT,
      `name` VARCHAR(255),
      `password` VARCHAR(255),
      `birthday` DATE)
CHARACTER SET utf8mb4 COLLATE utf8mb4_bin ENGINE=INNODB;
```



#### 2 列类型（常用数据类型）

![image-20220911091527144](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062331405.png)



![image-20220911092812106](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062331894.png)

![image-20220911092704881](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062331213.png)



#### 3 列类型之整型

![image-20220911094539490](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062331710.png)





![image-20220911095245947](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062331898.png)



```mysql
#演示整型使用
#演示tinyint有符号与无符号情况使用
#有符号 -128 ~ 127 
#无符号 0 ~ 255
CREATE TABLE tinytable (id TINYINT);

CREATE TABLE untinytable(id TINYINT UNSIGNED);

INSERT INTO tinytable VALUES(126);

INSERT INTO untinytable VALUES(0);

SELECT * FROM tinytable;

SELECT * FROM untinytable;
```



#### 4 列类型之bit

![image-20220911100451698](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062332061.png)



```mysql
#演示bit类型使用
#说明
#1.bit(m) m在1~64
#2. 添加数据 范围按照你给的位数来确定，比如m = 8表示一个字节 0~255
#3.显示按照bit
#4. 查询时，仍然可以按照位数来查询
CREATE TABLE bittable (num BIT(8));

INSERT INTO bittable VALUES(255);
SELECT * FROM bittable;
SELECT * FROM bittable WHERE num = 1;
```



#### 5 列类型之小数型

![image-20220911102310404](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062332882.png)



```mysql
#演示decimal类型、foloat、double使用
#创建表
CREATE TABLE dec01(
	num1 FLOAT,
	num2 DOUBLE,
	num3 DECIMAL(30,20));
#添加数据
INSERT INTO dec01 VALUES(88.1234567890,88.1234567890,88.1234567890);
SELECT * FROM dec01;

#decimal可以存放很大的数据
CREATE TABLE dec02(
	num DECIMAL(65));
INSERT INTO dec02 VALUES(898898989888999898989898989989899);
SELECT * FROM dec02;

CREATE TABLE big01(
	num BIGINT UNSIGNED);
INSERT INTO big01 VALUES(898898989888999898989898989989899);#报错
SELECT * FROM big01;#无数据
```



#### 6 列类型之字符串

![image-20220911142245227](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062332747.png)



```mysql
#演示字符串类型使用char varchar
#注释的快捷键 shift+ctrl+c，注释注销shift+ctrl+r
#char(size)
#固定长度字符串 最大255字符
#varchar(size) 
#可变长度字符串 最大65532字节【utf8编码最大21844字符，1~3字节用于记录大小】
#如果表的编码是utf8 varchar(size) size = (65535-3) / 3 =21844
#如果表的编码是gbk varchar(size) size = (65535-3) / 2 = 32766

CREATE TABLE char01(
	`name` CHAR(255));#正确
	
CREATE TABLE varchar01(
	`name` VARCHAR(21844) CHARSET utf8);#正确
	
CREATE TABLE varchar02(
	`name` VARCHAR(32767) CHARSET gbk);#报错

CREATE TABLE varchar03(
	`name` VARCHAR(32766) CHARSET gbk);#正确
	
DROP TABLE varchar01;
```



![image-20220911145500887](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062332505.png)





![image-20220911151110062](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062332127.png)





![image-20220911151316802](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062332524.png)



![image-20220911151432326](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062332459.png)



```mysql
#---------------------------
#演示字符串类型的使用细节
#char(4) 和 varchar(4) 这个4表示的是字符，而不是字节，不区分字母汉字
CREATE TABLE var01(
	`name` CHAR(4));
INSERT INTO var01 VALUES('abcd');
INSERT INTO var01 VALUES('天天向上');
INSERT INTO var01 VALUES('45pp');
SELECT * FROM var01;

CREATE TABLE varchar04(
	`name` VARCHAR(4));
INSERT INTO varchar04 VALUES('kkkk');
INSERT INTO varchar04 VALUES('等哈说8');
SELECT * FROM varchar04;

#如果varchar不够用，可以使用mediumtext或者longtext
#如果想简单点，可以使用text
CREATE TABLE text01(
	content1 TEXT,
	content2 MEDIUMTEXT,
	content3 LONGTEXT);
INSERT INTO text01 VALUES('今天是星期几','今天是星期几','今天是星期几');
SELECT * FROM text01;
```



#### 7 列类型之日期类型

![image-20220911152352637](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062332913.png)





```mysql
#演示时间相关类型
#创建一张表date,datetime,timestamp
CREATE TABLE date01(
	birthday DATE,-- 生日，年月日
	job_time DATETIME,-- 入职时间，年月日时分秒
	login_time TIMESTAMP
	NOT NULL DEFAULT
	CURRENT_TIMESTAMP ON UPDATE
	CURRENT_TIMESTAMP);-- 登录时间，时间戳，需要设置更新

SELECT * FROM date01;
INSERT INTO date01(birthday,job_time) VALUES('2022-11-11','2022-11-12');

-- 如果我们更新了表的某条记录，login_time会以当前时间更新
```



**创建表练习**

![image-20220911153833165](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062332031.png)



```mysql
#练习
CREATE TABLE emp(
	id INT,
	`name` VARCHAR(32),
	sex CHAR(1),
	birthday DATE,
	entry_date DATETIME,
	job VARCHAR(32),
	salary DOUBLE,
	`resume` MEDIUMTEXT) CHARSET utf8 COLLATE utf8_bin ENGINE INNODB;

INSERT INTO emp VALUES(2,'milan','女','2008-12-13','2022-6-9 11-11-22','程序员',3000,'今天是星期几');

SELECT * FROM emp;
```



#### **8. 修改表**

![image-20220911155633697](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062332700.png)



![image-20220911155913839](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062332486.png)



```mysql
#练习2
ALTER TABLE emp 
	ADD image VARCHAR(32) NOT NULL DEFAULT '' 
	AFTER RESUME;
DESC emp;
	
ALTER TABLE emp MODIFY job VARCHAR(60);

ALTER TABLE emp DROP sex;

RENAME TABLE emp TO employee;
DESC employee;

ALTER TABLE employee CHARSET utf8;

ALTER TABLE employee CHANGE `name` user_name VARCHAR(20);
```



#### 9. CRUD

![image-20220911161902556](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062332321.png)



##### **insert**

![image-20220911162035165](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062332720.png)



```mysql
CREATE TABLE goods(
	id INT,
	goods_name VARCHAR(10),
	price DOUBLE);
INSERT INTO goods(id,goods_name,price)
	VALUES(1,'tom',223);
	
INSERT INTO goods VALUES(2,'milan',444);

SELECT * FROM goods;
```



**insert细节**

![image-20220911163649811](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062332730.png)



##### **update**

![image-20220911165733908](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062332507.png)



**update细节**

![image-20220911171333011](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062332358.png)



```mysql
#演示update语句
#将employee表中所有员工薪水修改为5000元
SELECT * FROM employee;
UPDATE employee SET salary = 5000;
#将姓名为momo的员工薪水修改为3000元
UPDATE employee SET salary = 3000 WHERE user_name = 'momo';
#将tom的薪水在原有基础上增加1000元
UPDATE employee SET 
	salary = salary + 1000 WHERE user_name = 'tom';
	
#修改多个列
UPDATE employee SET 
	salary = salary + 1000,job = '算命'
	WHERE user_name = 'tom';
```



##### **delete**

![image-20220911171831603](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062333037.png)



delete细节

![image-20220911172435070](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062333555.png)



```mysql
#演示dalete操作
#删除表中名称为milan的记录
SELECT * FROM employee;
DELETE FROM employee 
	WHERE user_name = 'milan';

#删除表中所有记录
DELETE FROM employee;
```



##### select

![image-20220911173336166](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062333898.png)



![image-20220912081828062](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062333381.png)



```mysql
#student表
CREATE TABLE student(
	id INT NOT NULL DEFAULT 1,
	`name` VARCHAR(20) NOT NULL DEFAULT '',
	chinese FLOAT NOT NULL DEFAULT 0.0,
	english FLOAT NOT NULL DEFAULT 0.0,
	math FLOAT NOT NULL DEFAULT 0.0);
	
INSERT INTO student(id,`name`,chinese,english,math) VALUES(1,'momo',89,78,90);
INSERT INTO student(id,`name`,chinese,english,math) VALUES(2,'张飞',67,98,56);
INSERT INTO student(id,`name`,chinese,english,math) VALUES(3,'宋江',87,78,77);
INSERT INTO student(id,`name`,chinese,english,math) VALUES(4,'关羽',88,98,90);
INSERT INTO student(id,`name`,chinese,english,math) VALUES(5,'赵云',82,84,67);
INSERT INTO student(id,`name`,chinese,english,math) VALUES(6,'欧阳冯',55,85,45);
INSERT INTO student(id,`name`,chinese,english,math) VALUES(7,'黄蓉',75,65,30);

#select 重点难点
SELECT * FROM student;
#查询固定列
SELECT `name`,english FROM student;
#去重
SELECT DISTINCT * FROM student;
SELECT DISTINCT english FROM student;
```



![image-20220912082547239](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062333880.png)



![image-20220912082634962](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062333358.png)



```mysql
#查询每个学生的总分
SELECT `name`,(chinese + english + math) AS con FROM student;
#在所有学生总分加10分的情况
SELECT `name`,((chinese + english + math) + 10) AS con FROM student;
#使用别名表示学生分数
SELECT `name`,((chinese + english + math) + 10) AS con FROM student;
```



![image-20220912083415098](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062333745.png)



![image-20220912083545819](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062333231.png)



![image-20220912090918976](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062333282.png)



```mysql
#查询姓名为赵云的学生成绩
SELECT * FROM student WHERE `name` = '赵云';
#查询英语成绩大于90分的同学
SELECT * FROM student WHERE english > 90;
#查询总分大于200分的所有同学
SELECT `name`,(chinese + english + math) AS '总分' FROM student WHERE (chinese + english + math) > 200;
#查询math大于60并且id大于4的学生成绩
SELECT * FROM student WHERE math > 60 AND id > 4;
#查询英语成绩大于语文成绩的同学
SELECT * FROM student WHERE english > chinese;
#查询总分大于200分并且数学成绩小于语文成绩的姓张的学生
SELECT * FROM student 
	WHERE (chinese + english + math) > 200 
	AND math < chinese 
	AND `name` LIKE '张%';
	
#查询语文分数在70~80之间的同学
SELECT `name`,chinese FROM student WHERE chinese BETWEEN 70 AND 80; 
#查询总分为189，190，191的同学
SELECT `name`,(chinese + english + math) AS '总分' FROM student 
	WHERE(chinese + english + math) IN (189,221,242);
#查询所有姓李或者姓宋的学生成绩
SELECT * FROM student WHERE `name` LIKE '张%' OR `name` LIKE '宋%';
#查询数学比语文多1分的同学
SELECT `name`,chinese,math FROM student WHERE (math - chinese = 1);

#查询英语分数在80~90之间的同学
SELECT * FROM student WHERE english BETWEEN 80 AND 90;
#查询数学分数为89，90，91的同学
SELECT * FROM student WHERE math IN (89,90,91);
#查询所有姓张的学生成绩
SELECT * FROM student WHERE `name` LIKE '张%'; 
#查询数学分数>80,语文分数>80的同学
SELECT * FROM student WHERE math > 80 AND chinese > 80;
```



![image-20220912091621324](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062333828.png)



```mysql
#演示order by 使用
SELECT * FROM student ORDER BY math ASC;

SELECT `name`,(chinese + english + math) AS total FROM student
	ORDER BY total DESC;

SELECT `name`,(chinese + english + math) AS total FROM student 
	WHERE `name` LIKE '张%'
	ORDER BY total;
```



#### 10.统计函数

![image-20220912093222234](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062333733.png)



```mysql
#演示mysql统计函数的使用
#统计一个班共有多少个学生
SELECT COUNT(*) FROM student;
#统计数学成绩大于90的学生有多少个？
SELECT COUNT(*) FROM student WHERE math > 60;
#统计总分大于250的人数有多少？
SELECT COUNT(*) FROM student
	WHERE (chinese + english + math) > 250; 
#conunt(*) 和 count(列)的区别
-- count(*)返回满足条件的记录的行数
-- count(列)：统计满足条件的某列有多少个，但是会排除为null

CREATE TABLE isnull01(
	`name` VARCHAR(20));

INSERT INTO isnull01 VALUES('tom');
INSERT INTO isnull01 VALUES('jack');
INSERT INTO isnull01 VALUES('momo');
INSERT INTO isnull01 VALUES(NULL);

SELECT * FROM isnull01;
-- count(*)包括了所有的列，相当于行数，在统计结果的时候，不会忽略列值为NULL
SELECT COUNT(*) FROM isnull01
-- count(列名)只包括列名那一列，在统计结果的时候，会忽略列值为空（这里的空不是只空字符串或者0，而是表示null）的计数，即某个字段值为NULL时，不统计。
SELECT COUNT(`name`) FROM isnull01;
```





![image-20220912100530537](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062333408.png)



![image-20220912101558006](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062333323.png)



![image-20220912101830617](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062333591.png)



```mysql
#演示sum、avg、max、min
#统计一个班数学总成绩
SELECT SUM(math) AS math_total FROM student;
#统计一个班语文、英语、数学各科的总成绩
SELECT SUM(chinese) AS chi_total,SUM(english) AS eng_total,SUM(math) AS mat_total
	FROM student;
#统计一个班语文、英语、数学的成绩总和
SELECT SUM(chinese + english + math) FROM student;
#统计一个班语文成绩平均分
SELECT AVG(chinese) FROM student;
#求班级总分平均分
SELECT AVG(chinese + english + math) FROM student;
#求班级最高分和最低分
SELECT MAX(chinese + english + math),MIN(chinese + english + math)
	FROM student;
#求班级数学最高分和最低分
SELECT MAX(math),MIN(math) FROM student;
```



#### 11.分组统计

![image-20220912102400956](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062333247.png)



```mysql
#分组
CREATE TABLE dept( -- 部门表
	deptno MEDIUMINT UNSIGNED NOT NULL DEFAULT 0,
	dname VARCHAR(20) NOT NULL DEFAULT '',
	loc VARCHAR(13) NOT NULL DEFAULT '');

INSERT INTO dept VALUES(10,'ACCOUNTING','NEW YORK'),(20,'RESEARCH','DALLS'),
	(30,'SALES','CHICAGO'),(40,'OPERATIONS','BOSTON');
	
SELECT * FROM dept;
	
#创建表emp雇员
CREATE TABLE emp(
	empno MEDIUMINT UNSIGNED NOT NULL DEFAULT 0,-- 编号
	ename VARCHAR(9) NOT NULL DEFAULT '',-- 名字
	job VARCHAR(9) NOT NULL DEFAULT '',-- 工作
	mgr MEDIUMINT UNSIGNED,-- 上级编号
	hiredate DATE NOT NULL,-- 入职时间
	sal DECIMAL(7,2) NOT NULL,-- 薪水
	comm DECIMAL(7,2),-- 红利
	deptno MEDIUMINT UNSIGNED NOT NULL DEFAULT 0);-- 部门编号

INSERT INTO emp VALUES(7369,'SMITH','CLERK',7902,'1990-12-17',800.00,NULL,20),
	              (7499,'ALLEN','SALESMAN',7698,'1991-2-20',1600.00,300.00,30),
	              (7521,'WARD','SALESMAN',7698,'1991-2-22',1250.00,500.00,30),
	              (7566,'JONES','MANAGER',7869,'1991-4-2',2975.00,NULL,20),
	              (7654,'MAETIN','SALESMAN',7698,'1991-9-28',1250.00,1400.00,30),
	              (7698,'BLAKE','MANAGER',7839,'1991-5-1',2850.00,NULL,30),
	              (7782,'CLARK','MANAGER',7839,'1991-6-9',2450.00,NULL,10),
	              (7839,'KING','PRESIDENT',NULL,'1991-11-17',5000.00,NULL,10),
	              (7844,'TURNER','SALESMAN',7698,'1991-9-8',1500.00,NULL,30),
	              (7900,'JAMES','CLERK',7698,'1991-12-3',980.00,NULL,30),
	              (7902,'FORD','ANALYST',7566,'1991-12-3',3000.00,NULL,20),
	              (7934,'MELLER','CLERK',7782,'1992-1-23',1300.00,NULL,10);
	          	
SELECT * FROM emp;              


#工资级别表
CREATE TABLE salgrade(	
	grade MEDIUMINT UNSIGNED NOT NULL DEFAULT 0,
	losal DECIMAL(17,2) NOT NULL,
	hisal DECIMAL(17,2) NOT NULL);

INSERT INTO salgrade VALUES(1,700,1200),(2,1201,1400),(3,1401,2000),(4,2001,3000),(5,3001,9999);
	
SELECT *FROM salgrade;
DROP TABLE salgrade;

#显示每个部门的平均工资和最高工资
SELECT AVG(sal),MAX(sal),deptno FROM emp GROUP BY deptno;

#显示每个部门的每种岗位的平均工资和最低工资
SELECT AVG(sal),MIN(sal),deptno,job FROM emp GROUP BY deptno,job;

#显示平均工资低于2000的部门号和他的平均工资
SELECT deptno,AVG(sal) AS avgsal FROM emp GROUP BY deptno HAVING avgsal < 2000;  

```



#### 12.字符串函数

![image-20220912141339035](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062334896.png)



```mysql
#演示字符串相关函数使用
-- CHARSET(str) 返回字符串字符集
SELECT CHARSET(ename) FROM emp;

-- 连接字符串
SELECT CONCAT(ename,'job is',job) FROM emp;

-- INSTR(string,substring)返回substring在string中出现的位置，没有则返回0
-- DUAL亚元表，可做默认表使用
SELECT INSTR('hanshunping','ping') FROM DUAL;

-- UCASE(string2) 转换成大写
SELECT UCASE(ename) FROM emp;
-- LCASE(string2) 转换成小写
SELECT LCASE(ename) FROM emp;

-- LEFT(string2,length) 从string2中的左边起取length个字符
SELECT * FROM emp;
SELECT LEFT(ename,2) FROM emp;
SELECT RIGHT(ename,2) FROM emp;

-- LENGTH(string) string长度
SELECT LENGTH(ename) FROM emp;

-- replace(str,search_str,replace_str)
-- 在str中用replace_str替换search_str

SELECT * FROM emp;
SELECT ename,REPLACE(job,'MANAGER','经理') FROM EMP;

-- STRCMP(string1,string2)
-- 比较大小
SELECT STRCMP('hsp','csp') FROM DUAL;

-- SUBSTRING(str,position,length)
SELECT SUBSTRING(ename,1,2) FROM emp;

-- LTRTM(string2) RTRIM(string2) TRIM(string3)
-- 去除空格
SELECT LTRIM('  MOMO') FROM DUAL;
SELECT RTRIM('MOMO  ') FROM DUAL;
SELECT TRIM('  MOMO  ') FROM DUAL;

#以首字母小写的方式显示所有员工emp表的姓名

SELECT CONCAT(LCASE(LEFT(ename,1)), SUBSTRING(ename,2)) AS lcase_name FROM emp;

SELECT CONCAT(LCASE(SUBSTRING(ename,1,1)), SUBSTRING(ename,2)) AS lcase_name FROM emp;

 

```



#### 13.数字函数

![image-20220912145829191](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062334359.png)



```mysql
#演示mysql数学函数
-- ABS(num) 绝对值
SELECT ABS(-1) FROM DUAL;

-- BIN(decimal_number)十进制转二进制
SELECT BIN(10) FROM DUAL;

-- ceiling(number) 向上取整
SELECT CEILING(-1.1) FROM DUAL;

-- floor(number) 向下取整 
SELECT FLOOR(1.1) FROM DUAL;

-- conv(number,from_base,to_base) 进制转换
# 把十进制的8转成二进制输出
SELECT CONV(8,10,2) FROM DUAL;

-- FORMAT(number,decimal_place) 保留小数位数
SELECT FORMAT(78.123456,2) FROM DUAL;

-- HEX(Decimal Number) 转十六进制

-- LEAST(number1,numner2...) 求最小值
SELECT LEAST(0,1,-10,4) FROM DUAL;

-- MOD(number,number) 求余
SELECT MOD(10,3) FROM DUAL;

-- RAND([seed] RAND[seed]) 返回随机数，0 <= rand <= 1.0
-- rand(seed) seed不变，随机数不变
SELECT RAND() FROM DUAL;

```



#### 14.日期函数

![image-20220912153520496](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062334178.png)





![image-20220912153648010](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062334782.png)



![image-20220912160713610](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062334608.png)





![image-20220912160726109](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062334761.png)



```mysql
#演示日期时间相关函数
-- current_date() 当前日期
SELECT CURRENT_DATE FROM DUAL;

-- current_time() 当前时间
SELECT CURRENT_TIME FROM DUAL;

-- current_timestamp() 当前时间戳
SELECT CURRENT_TIMESTAMP FROM DUAL;

CREATE TABLE mes(
	id INT,
	content VARCHAR(30),
	send_time DATETIME);
	
INSERT INTO mes 
	VALUES(1,'北京新闻',CURRENT_TIMESTAMP());
	
INSERT INTO MES VALUES(2,'上海新闻',NOW());
INSERT INTO MES VALUES(3,'广州新闻',NOW());


SELECT * FROM mes;
DROP TABLE mes;

#显示所有新闻信息，发布日期只显示日期，不显示时间
SELECT id,content, DATE(send_time) FROM mes;

#查询十分钟内发布的新闻
SELECT * FROM mes WHERE DATE_ADD(send_time,INTERVAL 10 MINUTE) >= NOW();

#求2011-11-11和1990-1-1之间相差多少天

SELECT DATEDIFF('2011-11-11','1990-1-1') FROM DUAL;

#求你活了多少天
SELECT DATEDIFF(NOW(),'1998-1-26') FROM DUAL;

#如果能活到80岁，求你还能活多少天
SELECT DATEDIFF(DATE_ADD('1998-1-26',INTERVAL 80 YEAR),NOW()) FROM DUAL;
```





![image-20220912161203555](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062334613.png)



![image-20220912161347236](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062334611.png)



```mysql
-- unix_timestamp()：返回自1970-1-1到现在的毫秒数
SELECT UNIX_TIMESTAMP() FROM DUAL;

-- form_unixtime():可以把一个unix_timestamp秒数时间戳，转化成指定格式
-- %Y-%M-%d 格式是规定好的，表示年月日
-- 开发中，可以存放一个整数，然后表示时间，通过FORM_UNIXTIME转换
SELECT FROM_UNIXTIME(1618483484,'%Y-%m-%d') FROM DUAL;
SELECT FROM_UNIXTIME(1618483100,'%Y-%m-%d %H:%i:%s') FROM DUAL;
```



#### 15.加密函数

 ![image-20220913132341193](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062334766.png)



![image-20220913135007676](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062334546.png)



```mysql
#加密函数
-- USER() 查询用户
-- 查看登录到mysql的用户及登录ip
SELECT USER() FROM DUAL;

-- database() 数据库名称
SELECT DATABASE();

-- MD5(str) 密码加密
-- 存放的是加密后的密码
SELECT MD5('momo') FROM DUAL;
SELECT LENGTH(MD5('momo')) FROM DUAL;

-- 用户表，存放密码
CREATE TABLE md5_users(
	id INT,
	`name` VARCHAR(32) NOT NULL DEFAULT '',
	pwd CHAR(32) NOT NULL DEFAULT '');
	
INSERT INTO md5_users VALUES(1,'tom','123456789');
INSERT INTO md5_users VALUES(2,'milan',MD5('123456789'));
SELECT * FROM md5_users WHERE `name` = 'milan' AND pwd = MD5('123456789');
	
-- 涉及sql注入

-- PASSWORD(str)  加密函数
SELECT PASSWORD('') FROM DUAL;

-- select * from mysql.user \G
-- mysql.user 表示数据库.表

SELECT * FROM mysql.user
```



#### 16.流程控制函数

![image-20220913135100640](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062334427.png)



![image-20220913141941543](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062334045.png)





```mysql
#流程控制函数
-- IF(expr1，expr2,expr3) 如果expr1为true，则返回expr2，否则返回expr3
select if(true,'北京','上海') from dual;
SELECT IF(false,'北京','上海') FROM DUAL;

-- IFNULL(expr1,expr2) 如果expr1不为空，则返回expr1，否则返回expr2
select ifnull(null,'momo') from dual;
SELECT IFNULL('tom','momo') FROM DUAL;

SELECT CASE 
	WHEN expr1 THEN expr2 
	WHEN expr3 THEN expr4 
	ELSE expr5 END;
-- 类型多重分支

SELECT CASE 
	WHEN true THEN 'jack' 
	WHEN false THEN 'tom' 
	ELSE 'default' END;
	
#查询emp表，如果comm是null，则显示0.0
-- 判空 is null  
-- 判非空 is not null
select ename,if(comm is null,0.0,comm) from emp;

SELECT ename,IFnull(comm,0.0) FROM emp;

-- 如果emp表的job是clerk则显示职员，如果manager则显示经理，
-- 如果salesman则显示销售人员，其他正常显示

select * from emp;

select ename,(select case 
	when job = 'CLERK' THEN '职员'
	when job = 'MANAGER' THEN '经理'
	when job = 'SALESMAN' THEN '销售人员'
	else job end) from emp;
```



![image-20220913141908530](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062334657.png)



#### 17.查询增强

![image-20220913142109642](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062334146.png)



![image-20220913142348271](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062334298.png)



```mysql
#查询增强
SELECT * FROM emp;
SELECT * FROM dept;
SELECT * FROM salgrade;

-- 使用where字句
# 查询1992.1.1后入职的员工
# MySQL中日期类型可以直接比较
SELECT ename,hiredate FROM emp 
	WHERE hiredate > '1992-01-01';
	
#模糊查询 like % _
-- %:表示0到多个字符 
-- _:表示单个字符

# 显示首字母为s的员工姓名和工资
SELECT * FROM emp;
SELECT ename,sal FROM emp 
	WHERE ename LIKE 's%';


# 显示第二个字符为大写o的所有员工的姓名和工资
SELECT ename,sal FROM emp WHERE ename LIKE '_O%';

# 显示没有上级雇员的情况
SELECT * FROM emp WHERE mgr IS NULL;

# 查询表结构
DESC emp;
```





![image-20220913145050745](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062335612.png)



```mysql

# 排序增强

# 按照工资从低到高升序，显示雇员信息
SELECT * FROM emp ORDER BY sal;

# 按照部门号升序而雇员工资降序排列，显示雇员信息
SELECT * FROM emp ORDER BY deptno, sal DESC;
```



#### 18.分页查询

![image-20220913145213811](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062335269.png)

![image-20220913150210921](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062335927.png)



```mysql
# 分页查询
SELECT * FROM emp;
SELECT * FROM emp ORDER BY empno LIMIT 0,3;
SELECT * FROM emp ORDER BY empno LIMIT 3,3;
SELECT * FROM emp ORDER BY empno LIMIT 6,3;

# 推导公式
SELECT * FROM emp 
	ORDER BY empno 
	LIMIT 每页显示记录数 * （第几页 - 1,每页显示记录数;

# 按照雇员的emp号降序取出，每页显示5条记录，
SELECT * FROM emp ORDER BY empno DESC LIMIT 0,5;
```



#### 19.分组增强

![image-20220913150621654](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062335907.png)



```mysql
# 增强group by使用
# 显示每种岗位的雇员总数，平均工资
SELECT * FROM emp;
SELECT COUNT(*),job,FORMAT(AVG(sal),2) FROM emp GROUP BY job;

# 显示雇员总数，以及获得补助的雇员数
SELECT COUNT(*),COUNT(comm) FROM emp;

# 显示没有获得补助的雇员数
SELECT COUNT(IF(comm IS NULL,1,NULL)) FROM emp;
SELECT COUNT(*) - COUNT(comm) FROM emp;

# 显示管理者的总人数
SELECT COUNT(DISTINCT mar)
	FROM emp;

# 显示雇员工资的最大差额
SELECT MAX(sal) - MIN(sal) FROM emp;
```



#### 20.多字句查询

![image-20220913152606740](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062335148.png)



```mysql
# 统计各部门平均工资，并且大于1000，按照平均工资降序排序，取出前两行
SELECT ename,AVG(sal) FROM emp 
	GROUP BY deptno 
	HAVING AVG(sal) > 1000
	ORDER BY AVG(sal) DESC
	LIMIT 0,2;
```



#### 21.多表笛卡尔集

![image-20220913153307092](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062335237.png)



![image-20220913153441812](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062335734.png)



![image-20220913154215806](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062335732.png)





![image-20220913155304147](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062335025.png)



```mysql
#多表查询
-- 显示雇员名字、雇员工资、所在部门名称【笛卡尔集】
SELECT * FROM emp;
SELECT * FROM dept;
SELECT ename,sal,dname FROM emp,dept
	WHERE emp.deptno = dept.deptno;
```



#### 22.多表查询

![image-20220913155501405](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062335067.png)



```mysql
#多表查询
-- 显示雇员名字、雇员工资、所在部门名称【笛卡尔集】
SELECT * FROM emp;
SELECT * FROM dept;
SELECT * FROM salgrade;
SELECT ename,sal,dname FROM emp,dept
	WHERE emp.deptno = dept.deptno;

# 显示部门名为10的部门名、员工名和工资
SELECT dname,ename,sal,dept.deptno FROM emp,dept 
	WHERE emp.deptno = dept.deptno 
	AND dept.deptno = 10;	
	
# 显示各个员工的姓名、工资、及其工资的级别
SELECT ename,sal,grade FROM emp,salgrade 
	WHERE sal >= losal AND sal <= hisal;

SELECT ename,sal,grade FROM emp,salgrade
	WHERE sal BETWEEN losal AND hisal;
	
# 显示雇员名、雇员工资及所在部门的名字，并按照部门排序
SELECT ename,sal,dname,emp.deptno FROM emp,dept 
	WHERE emp.deptno = dept.deptno
	ORDER BY emp.deptno DESC;
```



#### 23.自连接

![image-20220914144138646](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062335407.png)



```mysql
# 自连接
# 一张表当成两张表使用
# 不同表、不同列取别名
SELECT * FROM emp;
SELECT worker.ename AS '职员名',boss.ename AS '上级名'
	FROM emp worker,emp boss
	WHERE worker.mgr = boss.empno;
```



#### 24.多行子查询

![image-20220914145347802](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062335609.png)



```mysql
# 子查询
# 单行子查询
# 显示与SMITH同一部门的所有员工
SELECT deptno FROM emp WHERE ename = 'SMITH';
SELECT * FROM emp 
	WHERE deptno = (
	SELECT deptno 
	FROM emp 
	WHERE ename = 'SMITH'
	);
	
# 多行子查询
# 查询和部门10的工作相同的雇员的名字、岗位、工资、部门号，但是不含10自己的
SELECT DISTINCT job FROM emp WHERE deptno = 10;
SELECT ename,job,sal,deptno FROM emp 
	WHERE job IN(
	SELECT DISTINCT job FROM emp WHERE deptno = 10
	) AND deptno != 10;
```



#### 25.子查询临时表

![image-20220914150943801](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062335436.png)



```mysql
# 子查询临时表
# 查询ecshop中各个类别中，价格最高的商品
-- 先得到各个类别中，价格最高的商品，当作临时表
-- 把子查询当作临时表可以解决很多复杂的查询

SELECT cat_id,MAX(shop_price)
	FROM esc_goods
	GROUP BY cat_id;
SELECT goods_id,ecs_goods.cat_id,goods_name,shop_price
		FROM(
			SELECT cat_id,MAX(shop_price)
			FROM esc_goods
			GROUP BY cat_id
		) temp,ecs_goods
		WHERE temp.cat_id = ecs_goods.cat_id
		AND temp.max_price = ecs_goods.shop_price;
```



#### 26.all及any

![image-20220914154456182](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062336080.png)



```mysql
# all及any
# 显示工资比部门30的所有员工的工资高的员工的姓名、工资和部门号
SELECT sal FROM emp WHERE deptno = 30;
SELECT ename,sal,deptno FROM emp 
	WHERE sal > ALL(SELECT sal FROM emp WHERE deptno = 30);
```



![image-20220914154735991](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062336006.png)

```mysql
# 显示工资比部门30的其中一个员工的工资高的员工的姓名、工资和部门号
SELECT ename,sal,deptno FROM emp 
	WHERE sal > ANY(SELECT sal FROM emp WHERE deptno = 30);
```



#### 27.多列子查询

![image-20220914154756446](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062336195.png)



```mysql
# 多列子查询
# 查询与ALLEN的部门和岗位完成相同的所有雇员（不含本人）
# （字段1，字段2...） = (select 字段1，字段2 from ...)
SELECT * FROM dept;
SELECT deptno,job FROM emp WHERE ename = 'SMITH';
SELECT * FROM emp
	WHERE (deptno,job) = 
	(SELECT deptno,job FROM emp WHERE ename = 'ALLEN')
	AND ename != 'ALLEN';
	
SELECT * FROM student
	WHERE (math,english,chinese) = 
	(SELECT math,english,chinese FROM student WHERE `name` = '宋江');
```



**子查询练习**

![image-20220914160505592](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062336401.png)



```mysql
# 练习1	
SELECT deptno,AVG(sal) AS avg_sal FROM emp GROUP BY deptno; 
SELECT ename,sal,temp.avg_sal,emp.deptno FROM 
	(SELECT deptno,AVG(sal) AS avg_sal FROM emp GROUP BY deptno) temp,emp
	WHERE temp.deptno = emp.deptno AND emp.sal > temp.avg_sal;
```



![image-20220914161921986](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062336008.png)



```mysql
# 练习2
SELECT deptno,MAX(sal) AS max_sal FROM emp GROUP BY deptno;
SELECT ename,sal,temp.max_sal,emp.deptno
	FROM emp,(
		SELECT deptno,MAX(sal) AS max_sal 
		FROM emp 
		GROUP BY deptno
	)temp
	WHERE emp.deptno = temp.deptno 
	AND emp.sal = temp.max_sal;
```



![image-20220914162932125](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062336059.png)



```mysql
# 练习3
SELECT COUNT(*),deptno FROM emp GROUP BY deptno;
SELECT dname,dept.deptno,loc,temp.per_number AS '人数'
	FROM dept,
	(SELECT COUNT(*) AS per_number,deptno FROM emp GROUP BY deptno) temp
	WHERE temp.deptno = dept.deptno;
```



#### 28.表复制和去重

![image-20220914170354393](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062336148.png)



```mysql
# 表复制和去重
# 为了对某个sql语句进行效率测试，需要海量数据，使用此法创建海量数据
CREATE TABLE my_tab01(
	id INT,
	`name` VARCHAR(32),
	sal DOUBLE,
	job VARCHAR(32),
	deptno INT);
DESC my_tab01;
SELECT * FROM my_tab01;

-- 演示自我复制
-- 先把emp表的记录复制到my_tab01表
INSERT INTO my_tab01(id,`name`,sal,job,deptno)
	SELECT empno,ename,sal,job,deptno FROM emp;
	
-- 自我复制
INSERT INTO my_tab01
	SELECT * FROM my_tab01;

-- 删除一张表重复记录
-- 1.创建表my_tab02
-- 2.让my_tab02有重复记录
CREATE TABLE my_tab02 LIKE emp;
DESC my_tab02;
INSERT INTO my_tab02 
	SELECT * FROM emp;
SELECT * FROM my_tab02;

-- 去重
-- 创建一张临时表my_ttmp,结构与my_tab02一样
CREATE TABLE my_tmp LIKE my_tab02;
-- 把my_tmp的记录通过distinct关键字处理后复制到my_tmp
INSERT INTO my_tmp 
	SELECT DISTINCT * FROM my_tab02;
-- 清除掉my_tab02记录
SELECT * FROM my_tmp;
DELETE FROM my_tab02;
-- 把my_tmp记录复制到my_tab02
INSERT INTO my_tab02
	SELECT * FROM my_tmp;
-- drop掉my_tmp
DROP TABLE my_tmp;

SELECT * FROM my_tab02;
```



#### 29.合并查询

![image-20220914170530843](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062336561.png)



![image-20220914191355130](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062336356.png)



```mysql
# union合并查询
-- union all将两个查询结果合并,不去重
SELECT ename,sal,job FROM emp WHERE sal > 2000
UNION ALL
SELECT ename,sal,job FROM emp WHERE job = 'MANAGER';
	
-- union 将两个查询结果合并,去重
SELECT ename,sal,job FROM emp WHERE sal > 2000
UNION 
SELECT ename,sal,job FROM emp WHERE job = 'MANAGER';
```



#### 30.(左、右)外连接

![image-20220914191720530](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062336255.png)



![image-20220914192515840](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062336389.png)



![image-20220914194417926](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062336964.png)



```mysql
# 外连接
# 列出部门名称和这些部门的员工名称和工作，同时要求显示出没有员工的部门
SELECT * FROM dept;
SELECT dname,ename,job FROM emp,dept 
	WHERE emp.deptno = dept.deptno
	ORDER BY dname;

CREATE TABLE stu(
	id INT,
	`name` VARCHAR(32));
INSERT INTO stu VALUES(1,'jack'),(2,'tom'),(3,'kety'),(4,'noon');
SELECT * FROM stu;

CREATE TABLE exam(
	id INT,
	grade INT);
INSERT INTO exam VALUES(1,56),(2,76),(11,8);
SELECT * FROM exam;
	
# 使用左外连接（显示所有人的成绩，如果没有成绩，也要显示该人的姓名和id，成绩显示为空）
SELECT exam.grade AS '成绩',stu.id,stu.`name` 
	FROM stu LEFT JOIN exam
	ON stu.id = exam.id;


# 右外连接，显示所有成绩，如果没有名字匹配，显示空
SELECT `name`,grade 
	FROM stu RIGHT JOIN exam
	ON stu.id = exam.id;
```



![image-20220914195503409](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062359532.png)



```mysql
# 列出部门名称和这些部门的员工信息，同时要求显示出没有员工的部门名
# 左外连接
SELECT dname,emp.* 
	FROM dept LEFT JOIN emp
	ON dept.deptno = emp.deptno;
SELECT * FROM dept;
# 右外连接
SELECT dname,emp.* 
	FROM emp RIGHT JOIN dept
	ON dept.deptno = emp.deptno;

```





#### 31.主键

![image-20220914195556822](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062336448.png)



![image-20220914195709216](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062336619.png)



![image-20220918164059308](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062336115.png)



```mysql
# 主键使用
create table prim_key(
	id int primary key,
	`name` varchar(32),
	email varchar(32));
# 主键列的值不能重复
INSERT INTO prim_key
	values(1,'jack','jack@souhu.com');
INSERT INTO prim_key
	VALUES(2,'tom','tom@souhu.com');
INSERT INTO prim_key
	VALUES(3,'milan','milan@souhu.com');
select * from prim_key;

# 主键使用细节
-- 主键不能重复且默认不能为空】、
INSERT INTO prim_key
	VALUES(3,'milan','milan@souhu.com');
-- 一张表中最多有一个主键，但可以是复合主键
create table prim_key02(  -- 报错
	id int primary key,
	`name` varchar(32), PRIMARY KEY,
	email varchar(32));

CREATE TABLE prim_key02(  -- 复合主键（id+name）
	id INT,
	`name` VARCHAR(32),
	email VARCHAR(32),
	primary key(id,`name`));
	
insert into prim_key02 values(1,'jack','jack@souhu.com');
INSERT INTO prim_key02 VALUES(1,'tom','tom@souhu.com');-- 添加成功

INSERT INTO prim_key02 VALUES(1,'jack','jack@souhu.com');
INSERT INTO prim_key02 VALUES(1,'jack','jack@souhu.com');-- 添加失败

select * from prim_key02;

# 主键指定方式
-- 1.id INT PRIMARY KEY
-- 2.PRIMARY KEY(id)
	
desc prim_key02;
	
# 实际开发中每个表往往都有主键	
```



#### 32.unique

![image-20220918165633564](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062337859.png)



```mysql
# unique使用
CREATE TABLE unique01(
	id INT UNIQUE, -- 表示id列不可以重复
	`name` VARCHAR(32),
	email VARCHAR(32));

INSERT INTO unique01 VALUES(1,'tom','tom@souhu.com');
INSERT INTO unique01 VALUES(1,'jack','jack@souhu.com');

-- unique 使用细节
-- 如果没有指定not null,则unique字段a可以有多个null
-- 如果一个字段是unique not null,则使用效果类似于primary key；
INSERT INTO unique01 VALUES(NULL,'null','null@souhu.com');-- 添加成功
SELECT * FROM unique01;
-- 一张表可以有多个unique字段,如下
CREATE TABLE unique02(
	id INT UNIQUE,
	`name` VARCHAR(32) UNIQUE,
	email VARCHAR(32));
SELECT * FROM unique02;
DESC unique02;
```



#### 33.外键

![image-20220918170842859](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062337686.png)



![image-20220918171553990](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062337472.png)





![image-20220918172959981](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062337053.png)



```mysql
# 外键演示
-- 主表
CREATE TABLE my_class(
	id INT PRIMARY KEY,
	`name` VARCHAR(32) NOT NULL DEFAULT '');
	
-- 创建外键所在表
CREATE TABLE my_stu(
	id INT PRIMARY KEY,-- 学生编号
	`name` VARCHAR(32) NOT NULL DEFAULT '',
	class_id INT,
	-- 指定外键
	FOREIGN KEY(class_id) REFERENCES my_class(id));
	
-- 测试
INSERT INTO my_class VALUES(100,'java'),(200,'php');
SELECT * FROM my_class;

INSERT INTO my_stu VALUES(1,'tom',100);
INSERT INTO my_stu VALUES(2,'jack',200);

SELECT * FROM my_stu;

INSERT INTO my_stu VALUES(3,'milan',300); -- 失败
```



#### 34.check

![image-20220918173559424](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062337415.png)



```mysql
# 演示check 检查约束
-- MySQL5.7目前不支持check，只做语法校验，但不会生效
CREATE TABLE check01(
	id INT PRIMARY KEY,
	`name` VARCHAR(32),
	sex VARCHAR(6) CHECK(sex IN('man','woman')),
	sal DOUBLE CHECK(sal > 1000 AND sal < 2000));


INSERT INTO check01 VALUES(1,'jack','mid',200);-- MySQL8.0已经生效


```



```mysql
在 test_db 数据库中创建 tb_emp7 数据表，要求 salary 字段值大于 0 且小于 10000，SQL 语句和运行结果如下所示。
```

```mysql
mysql> CREATE TABLE tb_emp7
    -> (
    -> id INT(11) PRIMARY KEY,
    -> name VARCHAR(25),
    -> deptId INT(11),
    -> salary FLOAT,
    -> CHECK(salary>0 AND salary<100),
    -> FOREIGN KEY(deptId) REFERENCES tb_dept1(id)
    -> );
Query OK, 0 rows affected (0.37 sec)
```



#### 35.商店表设计

![image-20220918174631416](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062337263.png)



```mysql
# 商店数据库 shop_db,记录客户及其购物情况，由下面三个表组成：
# 商品表goods(商品号goods_id,商品名goods_name,单价unitprice,
# 商品类别category,供应商provider)
# 客户表customer(客户号customer_id,姓名name,住址address，电邮email,
# 性别sex,身份证card_id);
# 购买订单号purchase(购买订单号order_id,客户号customer_id,商品号goods_id,
# 购买数量nums);

-- 建表，在定义中要求声明[进行合理设计]：
-- 每个表的主外键
-- 客户的姓名不能为空值
-- 电邮不能够重复
-- 客户的性别【男/女】check枚举
-- 单价unitprice在1.0-9999.99之间 check

CREATE DATABASE shop_db;
USE shop_db;
-- 商品表
CREATE TABLE goods  
	(goods_id INT PRIMARY KEY,
	goods_name VARCHAR(25) NOT NULL DEFAULT '',
	unitprice DECIMAL(10,2) NOT NULL DEFAULT 0 CHECK(unitprice >= 1.0 AND unitprice <= 9999.99),
	category INT NOT NULL DEFAULT 0,
	provider VARCHAR(25) NOT NULL DEFAULT '');
-- 客户表
CREATE TABLE customer
	(customer_id INT PRIMARY KEY,
	`name` VARCHAR(25) NOT NULL DEFAULT '',
	address VARCHAR(25) NOT NULL DEFAULT '',
	email VARCHAR(25) UNIQUE NOT NULL,
--	sex check(sex in('男','女')),
	sex ENUM('男','女') NOT NULL,
	card_id CHAR(18));
-- 订单表
CREATE TABLE purchase 
	(order_id INT PRIMARY KEY,
	customer_id INT,
	goods_id INT,
	nums INT NOT NULL DEFAULT 0,
	FOREIGN KEY(customer_id) REFERENCES customer(customer_id),
	FOREIGN KEY(goods_id) REFERENCES goods(goods_id));

```



#### 36.自增长

![image-20221007174724727](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062337625.png)



![image-20221007180734947](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062337487.png)



```mysql
# 演示自增长
CREATE TABLE auto_increment01
	(id INT PRIMARY KEY AUTO_INCREMENT,
	email VARCHAR(32) NOT NULL DEFAULT '',
	`name` VARCHAR(32) NOT NULL DEFAULT '');

DESC auto_increment01;
INSERT INTO auto_increment01 VALUES(NULL,'jack@qq.com','jack');
SELECT * FROM auto_increment01;
INSERT INTO auto_increment01 VALUES(NULL,'tom@qq.com','tom');
INSERT INTO auto_increment01 (email,`name`) VALUES ('hsp@qq.com','hsp');

-- 修改默认自增长开始值
CREATE TABLE auto_increment02
	(id INT PRIMARY KEY AUTO_INCREMENT,
	email VARCHAR(32) NOT NULL DEFAULT '',
	`name` VARCHAR(32) NOT NULL DEFAULT '');
ALTER TABLE auto_increment02 AUTO_INCREMENT = 100;
INSERT INTO auto_increment02 VALUES(NULL,'jack@qq.com','jack');
SELECT * FROM auto_increment02;

-- 可强制指定值
INSERT INTO auto_increment02 VALUES(666,'jack@qq.com','jack');
```



### 9. MySQL索引

![image-20221007180913738](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062337449.png)



```mysql
# 演示mysql索引

DROP DATABASE tmp;

-- 创建测试数据库 tmp
CREATE DATABASE tmp;

SET GLOBAL log_bin_trust_function_creators=TRUE;

CREATE TABLE dept( /*部门表*/
deptno MEDIUMINT   UNSIGNED  NOT NULL  DEFAULT 0,
dname VARCHAR(20)  NOT NULL  DEFAULT "",
loc VARCHAR(13) NOT NULL DEFAULT ""
) ;

#创建表EMP雇员
CREATE TABLE emp
(empno  MEDIUMINT UNSIGNED  NOT NULL  DEFAULT 0, /*编号*/
ename VARCHAR(20) NOT NULL DEFAULT "", /*名字*/
job VARCHAR(9) NOT NULL DEFAULT "",/*工作*/
mgr MEDIUMINT UNSIGNED NOT NULL DEFAULT 0,/*上级编号*/
hiredate DATE NOT NULL,/*入职时间*/
sal DECIMAL(7,2)  NOT NULL,/*薪水*/
comm DECIMAL(7,2) NOT NULL,/*红利*/
deptno MEDIUMINT UNSIGNED NOT NULL DEFAULT 0 /*部门编号*/
) ;

#工资级别表
CREATE TABLE salgrade
(
grade MEDIUMINT UNSIGNED NOT NULL DEFAULT 0,
losal DECIMAL(17,2)  NOT NULL,
hisal DECIMAL(17,2)  NOT NULL
);

#测试数据
INSERT INTO salgrade VALUES (1,700,1200);
INSERT INTO salgrade VALUES (2,1201,1400);
INSERT INTO salgrade VALUES (3,1401,2000);
INSERT INTO salgrade VALUES (4,2001,3000);
INSERT INTO salgrade VALUES (5,3001,9999);

DELIMITER $$

#创建一个函数，名字 rand_string，可以随机返回我指定的个数字符串
CREATE FUNCTION rand_string(n INT)
RETURNS VARCHAR(255) #该函数会返回一个字符串
BEGIN
#定义了一个变量 chars_str， 类型  varchar(100)
#默认给 chars_str 初始值   'abcdefghijklmnopqrstuvwxyzABCDEFJHIJKLMNOPQRSTUVWXYZ'
 DECLARE chars_str VARCHAR(100) DEFAULT
   'abcdefghijklmnopqrstuvwxyzABCDEFJHIJKLMNOPQRSTUVWXYZ'; 
 DECLARE return_str VARCHAR(255) DEFAULT '';
 DECLARE i INT DEFAULT 0; 
 WHILE i < n DO
    # concat 函数 : 连接函数mysql函数
   SET return_str =CONCAT(return_str,SUBSTRING(chars_str,FLOOR(1+RAND()*52),1));
   SET i = i + 1;
   END WHILE;
  RETURN return_str;
  END $$


 #这里我们又自定了一个函数,返回一个随机的部门号
CREATE FUNCTION rand_num( )
RETURNS INT(5)
BEGIN
DECLARE i INT DEFAULT 0;
SET i = FLOOR(10+RAND()*500);
RETURN i;
END $$

 #创建一个存储过程， 可以添加雇员
CREATE PROCEDURE insert_emp(IN START INT(10),IN max_num INT(10))
BEGIN
DECLARE i INT DEFAULT 0;
#set autocommit =0 把autocommit设置成0
 #autocommit = 0 含义: 不要自动提交
 SET autocommit = 0; #默认不提交sql语句
 REPEAT
 SET i = i + 1;
 #通过前面写的函数随机产生字符串和部门编号，然后加入到emp表
 INSERT INTO emp VALUES ((START+i) ,rand_string(6),'SALESMAN',0001,CURDATE(),2000,400,rand_num());
  UNTIL i = max_num
 END REPEAT;
 #commit整体提交所有sql语句，提高效率
   COMMIT;
 END $$

 #添加8000000数据
CALL insert_emp(100001,8000000)$$

#命令结束符，再重新设置为;
DELIMITER ;

SELECT COUNT(*) FROM emp;

-- 无索引查询  4.3秒查询速度
SELECT * FROM emp
	WHERE empno = 1234567;

-- 使用索引优化,索引本身占用空间——0.001秒
-- NO emp (empno)表示在emp表的empno列创建索引
CREATE INDEX empno_index ON emp (empno)

SELECT * FROM emp
	WHERE empno = 1234568;

-- 索引只对创建索引的列（字段）有效 4.802秒
SELECT * FROM emp WHERE ename = 'momo';

CREATE INDEX ename_index ON emp (ename);
SELECT * FROM emp WHERE ename = 'aaaaaa'; -- 0.001秒
```



![image-20221007195735898](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062337628.png)



![image-20221007201539625](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062337701.png)



![image-20221007201625189](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062337303.png)





![image-20221007201644978](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062337027.png)



![image-20221007202350903](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062337104.png)



![image-20221007204249918](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062337620.png)



```mysql
# 演示MySQL索引的使用
# 创建索引
CREATE TABLE t25
	(id INT,
	`name` VARCHAR(32));

-- 查询表是否有索引
SHOW INDEXES FROM t25;

-- 添加索引
-- 添加唯一索引
CREATE UNIQUE INDEX id_index ON t25 (id);
-- 方式1 添加普通索引
CREATE INDEX id_index ON t25 (id);
-- 1.如果某列的值不重复，则优先考虑使用unique索引，否者使用普通索引

-- 方式2 添加普通索引
ALTER TABLE t25 ADD INDEX id_index (id);

-- 添加主键索引
CREATE TABLE t26 (
	id INT PRIMARY KEY,-- 主键本身就有索引
	`name` VARCHAR(32));
ALTER TABLE t26 ADD PRIMARY KEY (id)

-- 删除索引
DROP INDEX id_index ON t25;

-- 删除主键索引
ALTER TABLE t25 DROP PRIMARY KEY;

-- 修改索引，先删除再添加

-- 查询索引
SHOW INDEX FROM tab_name;
SHOW INDEXES FROM tab_name;
SHOW KEYS FROM t25;
DESC t25;

```



```mysql
-- 索引练习题
# 建立索引（主键）课后练习
# 要求：创建一张订单表order(id号，商品名，订购人，数量)。要求id号为主键，
# 请使用2中方式来创建主键（提示：为了练习方便，可以是order1，order2）
CREATE TABLE `order` (
	id INT PRIMARY KEY,
	goods_name VARCHAR(23) NOT NULL DEFAULT '',
	order_per VARCHAR(23) NOT NULL DEFAULT '',
	order_nums INT NOT NULL DEFAULT 0);
ALTER TABLE `order` ADD PRIMARY KEY (id);



-- 建立索引（唯一）课后练习
# 要求：
# 创建一张特价菜谱表menu（id号，菜谱名，厨师，点餐人身份证，价格）要求id号为主键，点餐人
# 身份证是unique，请使用两种方式来创建unique（提示，为了练习方便，可以是menu1，menu2）
CREATE TABLE menu (
	id INT PRIMARY KEY,
	menu_name VARCHAR(23) NOT NULL DEFAULT '',
	menu_chushi VARCHAR(23) NOT NULL DEFAULT '',
	sfz CHAR(18) UNIQUE,
	price DECIMAL(10,2) NOT NULL DEFAULT 0);
CREATE UNIQUE INDEX sfz_index ON menu (sfz);

-- 建立索引（普通）课后练习
# 要求：
# 创建一张运动员表sportman(id号，名字，特长)要求id号为主键，名字为普通索引，请使用2中方式
# 来创建索引（提示，为了练习方便，可以是不同表名）
CREATE TABLE sportman (
	id INT PRIMARY KEY,
	`name` VARCHAR(23) NOT NULL DEFAULT '',
	hobby VARCHAR(23) NOT NULL DEFAULT '');
CREATE INDEX name_index ON sportman (`name`);
ALTER sportman ADD INDEX name_index (`name`);
```



![image-20221007210753666](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062338683.png)



### 10.MySQL事务

![image-20221007211534224](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062338180.png)



![image-20221007211612547](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062338869.png)





![image-20221007212227757](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062338723.png)



![image-20221007213632213](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062338141.png)



```mysql
# 演示事务
# 1. 创建一张测试表
CREATE TABLE t27 (
	id INT,
	`name` VARCHAR(32));

-- 开始事务
START TRANSACTION;
-- 设置保存点a
SAVEPOINT a;
-- 执行dml操作1
INSERT INTO t27 VALUES(100,'tom');
SELECT * FROM t27;

-- 设置保存点b
SAVEPOINT b;
-- 执行dml操作2
INSERT INTO t27 VALUES(200,'jack');
-- 回退到保存点b
ROLLBACK TO b;

ROLLBACK TO a;

-- 回退到事务开始
ROLLBACK;

-- 提交操作,无法回退
COMMIT;
```



![image-20221007214439445](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062338817.png)



**MySQL隔离级别**

![image-20221007214655430](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062338434.png)



![image-20221007215202725](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062338691.png)



![image-20221007215213253](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062338047.png)



![image-20221007222355769](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062338591.png)



**MySQLACID特性**

![image-20221007222903793](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062338859.png)



**MySQL存储引擎**

![image-20221007223556073](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062338389.png)



![image-20221007224018454](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062338269.png)





![image-20221007224031211](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062338100.png)



![image-20221007224539181](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062338845.png)



 ![image-20221008004947840](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062338810.png)



![image-20221008005518500](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062338521.png)



![image-20221008005641671](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062339195.png)



### 11.视图

![image-20221008005723155](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062339346.png)



![image-20221008010058466](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062339174.png)



![image-20221008010852976](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062339684.png)





![image-20221008010944786](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062339672.png)



```mysql
# 演示视图
-- 创建一个视图emp_view01,只能查询emp表的（empno、ename、job和deptno）信息

-- 创建视图
CREATE VIEW emp_view01
	AS 
	SELECT empno,ename,job,deptno FROM emp;

-- 查看视图
DESC emp_view01;
SELECT * FROM emp_view01;

-- 查看创建视图的指令
SHOW CREATE VIEW emp_view01;

-- 删除视图
DROP VIEW emp_view01;
```





![image-20221008011734115](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062339399.png)



```mysql
-- 修改视图
UPDATE  emp_view01
	SET job = 'MANAGER'
	WHERE EMPNO = 7369;

SELECT * FROM emp;-- 查询基表

-- 修改基表影响视图

-- 视图中可以再使用视图
-- 从视图emp_view01中选出empno，ename做新视图

CREATE VIEW emp_view02
	AS 
	SELECT empno,ename FROM emp_view01
```



视图实践

![image-20221008013123252](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062339725.png)



![image-20221008013525996](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062339185.png)



```mysql
-- 视图练习
CREATE VIEW emp_view03
	AS
	SELECT empno,ename,dname,grade
	FROM emp,dept,salgrade
	WHERE emp.deptno = dept.deptno 
	AND (sal BETWEEN losal AND hisal);

DESC emp_view03;
SELECT * FROM emp_view03;
```



### 12.MySQL用户管理

![image-20221008014545398](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062339222.png)



![image-20221008014639747](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062339972.png)





![image-20221008020139198](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062339045.png)





![image-20221008020259304](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062339912.png)



```mysql
# 演示MySQL用户管理
-- 做项目开发时，可以根据不同的开发人员赋给相应的MySQL开发权限
-- 所以，mysql数据库管理人员根据需要创建不同的用户赋给相应权限

-- 创建新的用户
-- 'hsp_edu'@'localhost' 表示用户的完整信息 'hsp_edu' 用户名 'loaclhost'登录的ip
-- 123456 密码，但是注意存放到mysql.user表中时，是password('123456')加密后的密码
CREATE USER 'hsp_edu'@'localhost' IDENTIFIED BY '123456'

SELECT * FROM mysql.user

-- 修改自己的密码
SET PASSWORD = PASSWORD('abc');

-- 修改其他人的密码，需要权限
SET PASSWORD FOR 'root'@'localhost' = PASSWORD('123456');

-- root用户修改其他人的密码
SET PASSWORD FOR 'hsp_edu'@'locajhost' = PASSWORD('123456')
```



![image-20221008020813469](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062339104.png)



**MySQL用户权限**

![image-20221008021010958](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062339013.png)



![image-20221008021348513](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062339674.png)



![image-20221008021421602](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062340845.png)





```mysql
-- 演示用户权限管理
-- 创建用户momo密码123，从本地登录
CREATE USER 'momo'@'localhost' IDENTIFIED BY '123456';

-- 默认情况下，momo用户只能看到一个默认的系统数据库

-- 使用root用户创建testdb,表news
CREATE TABLE news(
	id INT,
	content VARCHAR(32));
	
INSERT INTO news VALUES(100,'北京');

-- 给momo用户添加news表和添加news的权限
GRANT SELECT ,INSERT 
	 ON tmp.news
	 TO 'momo'@'localhost'
	 
	 
GRANT UPDATE
	 ON tmp.news
	 TO 'momo'@'localhost'


SELECT * FROM news;

-- 修改momom密码为abc
SET PASSWORD FOR 'momo'@'localhost' = PASSWORD('abc');

-- 演示回收权限
REVOKE SELECT,UPDATE,INSERT ON tmp.news FROM 'momo'@'localhost'
REVOKE ALL ON tmp.news FROM 'momo'@'localhost'

-- 删除用户
DROP USER 'momo'@'localhost';
```



![image-20221008023539252](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062340630.png)



```mysql
# 用户管理细节
# 在创建用户时，如果不指定host，则为%，%表示所有ip都有连接权限
create user jack

select `host`,`user` from mysql.user

-- 你也可以这样指定
create user 'smith'@'192.168.1.%' 

-- 在删除用户时，如果host不是%，需要明确指定'用户'@'host值'
drop user jack
drop user 'smith'@'192.168.1.%' 
```



13.MySQL练习

![image-20221008121652984](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062340702.png)



![image-20221008125104613](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062340685.png)



```mysql
# 写出查看dept表和emp表的结构的sql语句
DESC dept;
SELECT * FROM dept;
DESC emp;

# 使用简单查询语句完成
# 显示所有部门名称
SELECT dname FROM dept;
# 显示所有雇员及其全年收入13月（工资+补足），并指定列别名“年收入”
SELECT ename,(sal + IFNULL (comm,0))*13 AS "年收入" FROM emp;

# 限制查询数据
#显示工资超过2850的雇员姓名和工资
SELECT ename,sal FROM emp WHERE sal > 2850;
#显示工资不在1500到2850之间的所有雇员及其工资
SELECT ename,sal FROM emp WHERE sal < 1500 OR sal > 2850;
#显示编号为7566的雇员姓名及所在部门编号
SELECT ename,deptno FROM emp WHERE empno = 7566;
#显示部门10和30中工资超过1500的雇员及工资
SELECT ename,sal FROM emp WHERE (deptno = 10 OR deptno = 30) AND sal > 1500;
#显示无管理者的雇员及岗位
SELECT ename,job FROM emp WHERE mgr IS NULL;

# 排序
# 显示在1991年2月1日到1991年5月1日之间雇用的雇员名，岗位及雇佣日期
#并以雇佣日期进行排序
SELECT ename,job,hiredate FROM emp WHERE hiredate BETWEEN "1991-2-1" AND "1991-5-1" ORDER BY hiredate;
# 显示获得补助的所有雇员名，工资及补助并进行工资降序排序
SELECT ename,sal,comm FROM emp ORDER BY sal DESC;
```



![image-20221008125218875](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062340817.png)



```mysql
/*根据emp员工表，写出正确的sql
1.选择部门30中的所有员工*/
SELECT ename,deptno FROM emp WHERE deptno = 30;
/*2.列出所有办事员clerk的姓名，编号，和部门编号*/
SELECT ename,empno,deptno,job FROM emp WHERE job = "CLERK";
/*3.找出佣金高于薪水的员工*/
SELECT * FROM emp WHERE sal < IFNULL (comm,0);
/*4.找出佣金高于薪水60%的员工*/
SELECT * FROM emp WHERE sal*0.6 < IFNULL (comm,0);
/*5.找出部门10中所有经理manager和部门20中所有办事员clerk的详细资料
*/SELECT ename,job FROM emp WHERE (deptno = 10 AND job = "MANAGER") OR (deptno = 20 AND job = "CLERK")
# 6.找出部门10中所有经理，部门20中所有办事员，还有既不是经理又不是办事员但其薪金大于或等于2000的所有员工的详细资料
SELECT ename,job FROM emp WHERE (deptno = 10 AND job = "MANAGER") OR (deptno = 20 AND job = "CLERK") OR (job != "MANAGER" AND job != "CLERK" AND sal >= 2000)
# 7.查找收取佣金的员工的不同工作
SELECT DISTINCT ename,job FROM emp WHERE comm IS NOT NULL;
#8.找出不收佣金或收取佣金低于100的员工
SELECT * FROM emp WHERE comm IS NULL OR IFNULL (comm,0) < 100;
#9.找出各月倒数第三天受雇的所有员工
SELECT * FROM emp WHERE LAST_DAY(hiredate) - 2 = hiredate; 
#10.找出早于12年前受雇的员工
SELECT * FROM emp WHERE DATE_ADD(hiredate,INTERVAL 12 YEAR) < NOW();
#11.以首字母小写的方式显示所有员工的姓名
SELECT CONCAT(LCASE(SUBSTRING(ename,1,1)),SUBSTRING(ename,2))ename FROM emp;
#12.显示正好为5个字符的员工的姓名
SELECT * FROM emp WHERE LENGTH(ename) = 5;
```



![image-20221008133539029](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062340369.png)



```mysql
# 显示不带有"R"的员工的姓名
SELECT * FROM emp WHERE ename NOT LIKE '%R%';
# 显示所有员工姓名的前三个字符
SELECT LEFT(ename,3) FROM emp;
SELECT SUBSTRING(ename,1,3) FROM emp;
# 显示所有员工的姓名，用a替换所有“A”
SELECT REPLACE(ename,'A','a') FROM EMP;
# 显示满10年服务年限的员工的姓名和受雇日期
SELECT ename,hiredate FROM emp WHERE DATE_ADD(hiredate,INTERVAL 10 YEAR) <= NOW();
# 显示员工的详细资料，按姓名排序
SELECT * FROM emp ORDER BY ename;
# 显示员工的姓名和受雇日期，根据器服务年限，将最老的员工排在前面
SELECT * FROM emp ORDER BY hiredate;

# 显示所有员工的姓名、工作和薪水，按工作降序排序，若工作相同则按薪金排序
SELECT ename,job,sal FROM emp ORDER BY job DESC,sal;
# 显示所有员工的姓名、加入公司的年份和月份，按照受雇日期所在月排序，若是月份相同则将最早年份的员工排在最前面
SELECT ename,CONCAT(YEAR(hiredate),'-',MONTH(hiredate))  FROM emp ORDER BY MONTH(hiredate),YEAR(hiredate);
# 显示在一个月为30天的情况下所有员工的日薪金，忽略余数
SELECT FLOOR(sal / 30) FROM emp; 
# 找出在（任何月份）2月受聘的所有员工
SELECT * FROM emp WHERE MONTH(hiredate) = 2; 
# 对于每个员工，显示器加入公司的天数
SELECT ename,DATEDIFF(NOW(),hiredate) FROM emp;
# 显示姓名字段的任何位置包含“A”的所有员工的姓名
SELECT * FROM emp WHERE ename LIKE '%A%';
# 以年月日的方式显示所有员工的服务年限（大概）
SELECT ename,DATEDIFF(NOW(),hiredate) / 365 AS "工作年",
	FLOOR(DATEDIFF(NOW(),hiredate) % 365 / 30) AS "工作月",
	DATEDIFF(NOW(),hiredate) % 31 AS "工作天" FROM emp;
```



![image-20221008160831753](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062340552.png)



```mysql
# 列出至少有一个员工的所有部门
SELECT COUNT(*) AS c,deptno FROM emp GROUP BY deptno HAVING c > 1;
# 列出薪金比“SMITH”多的所有员工
SELECT * FROM emp 
	WHERE sal > 
	(SELECT sal FROM emp WHERE ename = "SMITH");
# 列出受雇日期晚于其直接上级的所有员工】
SELECT worker.ename AS '员工名',worker.hiredate AS '员工入职时间', 
	leader.ename AS '上级名',leader.hiredate AS '上级入职时间' 
	FROM emp worker,emp leader
	WHERE worker.hiredate > leader.hiredate
	AND worker.mgr = leader.empno;
# 列出部门名称和这些部门的员工信息，同时列出那些没有员工的部门
SELECT dname,emp.* FROM dept LEFT JOIN emp ON dept.deptno = emp.deptno
# 列出所有“CLERK”(办事员)的姓名及其部门名称
SELECT ename,dname FROM emp,dept WHERE emp.deptno = dept.deptno AND emp.job = "CLERK";
# 列出最低薪金大于1500的各种工作
SELECT MIN(sal) AS min_sal, job FROM emp GROUP BY job HAVING min_sal > 1500;
# 列出在部门“SALES”（销售部）工作的员工的姓名
SELECT ename,dname FROM emp,dept WHERE emp.deptno = dept.deptno AND dname = "SALES";
# 列出薪金高于公司平均薪金的所有员工
SELECT * FROM emp WHERE sal > (SELECT AVG(sal) FROM emp);




# 列出与“SMITH”从事相同工作的所有员工
SELECT * FROM emp 
	WHERE job = 
(SELECT job FROM emp WHERE ename = "SMITH");

# 列出薪金高于在部门30工作的所有员工的薪金的员工姓名和薪金
SELECT ename,sal FROM emp 
	WHERE sal > 
	(SELECT MAX(sal) FROM emp WHERE deptno = 30);
	
	
# 列出在每个部门工作的员工数量、平均工资、平均服务期限
SELECT COUNT(*),FORMAT(AVG(sal),2),AVG(DATEDIFF(NOW(),hiredate)) FROM emp GROUP BY deptno

# 列出所有员工的姓名、部门名称和工资
SELECT ename,dname,sal FROM emp,dept WHERE emp.deptno = dept.deptno;

# 列出所有部门的详细信息和部门人数
SELECT dept.*,tmp.c 
	FROM dept,(SELECT COUNT(*) AS c,deptno FROM emp GROUP BY deptno)
	tmp
	WHERE dept.deptno = tmp.deptno;
	
# 列出所有各种工作的最低工资
SELECT MIN(sal),job FROM emp GROUP BY job;

# 列出经理的最低薪金
SELECT MIN(sal) FROM emp WHERE job = "MANAGER";

# 列出所有员工的年工资，按年薪从低到高排序
SELECT eanme,(sal + IFNULL(comm,0)) * 12 year_sal FROM emp ORDER BY year_sal;
```



![image-20221008161057195](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062340425.png)



![image-20221008161318640](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062340065.png)





```mysql
CREATE DATABASE school01;
USE school01;

CREATE TABLE department(
	department_id VARCHAR(32) PRIMARY KEY,
	deptname VARCHAR(32) UNIQUE NOT NULL);

INSERT INTO department VALUES(001,'数学'),
	(002,'计算机'),
	(003,'化学'),
	(004,'中文'),
	(005,'经济');


CREATE TABLE class(
	class_id INT PRIMARY KEY,
	`subject` VARCHAR(32) NOT NULL DEFAULT '',
	deptname VARCHAR(32),
	enrolltime YEAR NOT NULL,
	num INT NOT NULL DEFAULT 0,
	FOREIGN KEY(deptname) REFERENCES department(deptname));
	
DROP TABLE class;
DROP TABLE department;
DROP TABLE student;

DROP DATABASE school01;

INSERT INTO class VALUES(101,'软件','计算机','1995',20),
	(102,'微电子','计算机','1996',30),
	(111,'无机化学','化学','1995',29),
	(112,'高分子化学','化学','1996',25),
	(121,'统计数学','数学','1995',20),
	(131,'现代语言','中文','1996',20),
	(141,'国际贸易','经济','1997',30),
	(142,'国际金融','经济','1996',14);
	
CREATE TABLE student(
	syudent_id INT PRIMARY KEY,
	`name` VARCHAR(23) NOT NULL DEFAULT '',
	age INT NOT NULL DEFAULT 0,
	class_id INT,
	FOREIGN KEY(class_id) REFERENCES class(class_id)
	);
INSERT INTO student VALUES(8101,'张三',18,101),
	(8102,'钱四',16,121),
	(8103,'王玲',17,131),
	(8105,'李飞',19,102),
	(8109,'赵四',18,141),
	(8110,'李可',20,142),
	(8201,'张飞',18,111),
	(8302,'周瑜',16,112),
	(8203,'王亮',17,111),
	(8305,'董庆',19,102),
	(8409,'赵龙',18,101),
	(8510,'李丽',20,142);


# 完成以下查询功能
-- 3.1找出所有姓李的学生
SELECT * FROM student WHERE `name` LIKE "李%";
-- 3.2列出所有开设超过1个专业的系的名字

SELECT COUNT(*) AS nums,deptname FROM class GROUP BY deptname HAVING nums > 1;
-- 3.3列出人数大于等于30的系的编号和名字


SELECT tmp.*,department.departmentid
	FROM department,(
	SELECT SUM(num) AS nums,deptname FROM class GROUP BY deptname HAVING nums >= 30)
	temp
	WHERE department.deptname = tmp.department;

# 添加数据

INSERT INTO department VALUES(001,'数学');

# 学生张三退学，请更新相关的表

START TRANSACTION;

UPDATE calss SET num = num - 1
	WHERE calss_id = 
	(SELECT class_id FROM student WHERE `name` = '张三');

DELETE FROM student WHERE `name` = '张三';
COMMIT;
```





## 20. JDBC和连接池

![image-20221008200324976](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062340234.png)



![image-20221008202621259](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062340840.png)



![image-20221008204554681](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062340430.png)



![image-20221008204827778](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062341131.png)



![image-20221008204955326](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062341517.png)





#### 1.jdbc模拟实现

```java
package com.momo.jdbc01;

/**
 * @author momo~
 * @version 1.0
 */
public interface JdbcInterface {

    //连接
    public Object getConnection();

    //crud

    public void crud();

    //关闭连接
    public void close();


}

```



```java
package com.momo.jdbc01;

/**
 * @author momo~
 * @version 1.0
 * 模拟mysql数据库实现了jdbc接口，MySQL厂商开发
 */
public class MysqlJdbcImpl implements JdbcInterface{
    @Override
    public Object getConnection() {
        System.out.println("得到MySQL的连接");
        return null;
    }

    @Override
    public void crud() {
        System.out.println("完成MySQL增删改查");
    }

    @Override
    public void close() {
        System.out.println("关闭MySQL的连接");
    }
}

```



```java
package com.momo.jdbc01;

/**
 * @author momo~
 * @version 1.0
 * 模拟Oracle数据库实现jdbc
 */
public class OracleJDBCimpl implements JdbcInterface{
    @Override
    public Object getConnection() {
        System.out.println("得到oracle数据库的连接");
        return null;
    }

    @Override
    public void crud() {
        System.out.println("完成对oracle数据库的增删改查");
    }

    @Override
    public void close() {
        System.out.println("断开oracle数据库的连接");
    }
}

```



```java
package com.momo.jdbc01;

/**
 * @author momo~
 * @version 1.0
 */
public class TestJDBC {
    public static void main(String[] args) {
        //完成对mysql的操作
        JdbcInterface jdbcInterface = new MysqlJdbcImpl();
        jdbcInterface.getConnection();//通过接口调用实现类
        jdbcInterface.crud();
        jdbcInterface.close();

        //完成对Oracle的操作
        JdbcInterface jdbcInterface2 = new OracleJDBCimpl();
        jdbcInterface2.getConnection();//通过接口调用实现类
        jdbcInterface2.crud();
        jdbcInterface2.close();
    }
}

```



#### 2.jdbc入门

![image-20221008205542573](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062341221.png)



![image-20221008205706514](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062341949.png)



![image-20221008211605885](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062341497.png)



```java
package com.momo.jdbc02;

import com.mysql.jdbc.Driver;

import java.sql.Connection;
import java.sql.SQLException;
import java.sql.Statement;
import java.util.Properties;

/**
 * @author momo~
 * @version 1.0
 * 这是第一个Jdbc程序，完成简单的操作
 */
public class Jdbc01 {
    public static void main(String[] args) throws SQLException {
        //前置工作，在项目下创建一个文件夹比如libs
        //将mysql.jar拷贝至该目录下，add library,加入到项目中
        //注册驱动
        Driver driver = new Driver();//创建Driver对象

        //得到连接
        //jdbc:mysql://
        //loaclhost:3306
        //jdbc_01
        String url = "jdbc:mysql://localhost:3306/jdbc_01";
        //将用户名和密码放入到Properties对象中
        Properties properties = new Properties();
        properties.setProperty("user","root");//用户
        properties.setProperty("password","root");//密码
        Connection connect = driver.connect(url, properties);

        //执行sql
//        String sql = "insert into actor values(null,'刘德华','男','1994-1-2','110')";
//        String sql = "update actor set name = '周星驰' where id = 1";
        String sql = "delete from actor where id = 1";
        //statement 用于执行静态SQL语句并返回其生成的结果的对象
        Statement statement = connect.createStatement();
        int rows = statement.executeUpdate(sql);//如果是dml语句，返回的是影响的行数

        System.out.println(rows > 0 ? "成功" : "失败");

        //关闭连接
        statement.close();
        connect.close();
    }
}
```





#### 3.连接数据库的五种方式

![image-20221008214954310](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062341010.png)



![image-20221008215036814](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062341105.png)





![image-20221008220246958](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062341965.png)





![image-20221008220940538](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062341779.png)

![image-20221008222410745](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062341523.png)





![image-20221008222422252](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062341957.png)



```java
package com.momo.jdbc02;

import com.mysql.jdbc.Driver;
import org.junit.jupiter.api.Test;

import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.util.Properties;

/**
 * @author momo~
 * @version 1.0
 * 分析JAVA连接MySQL五种方式
 */
public class JdbcConn {

    //方式1
    @Test
    public void connect01() throws SQLException {
        Driver driver = new Driver();//创建Driver对象
        String url = "jdbc:mysql://localhost:3306/jdbc_01";
        //将用户名密码放到Properties对象
        Properties properties = new Properties();
        properties.setProperty("user","root");
        properties.setProperty("password","root");
        Connection connect = driver.connect(url, properties);
        System.out.println(connect);

    }

    //方式2
    @Test
    public void connect02() throws ClassNotFoundException, InstantiationException, IllegalAccessException, SQLException {
        //使用反射加载Driver类,动态加载，减少依赖
        Class<?> aClass = Class.forName("com.mysql.jdbc.Driver");
        Driver driver = (Driver)aClass.newInstance();

        String url = "jdbc:mysql://localhost:3306/jdbc_01";
        //将用户名密码放到Properties对象
        Properties properties = new Properties();
        properties.setProperty("user","root");
        properties.setProperty("password","root");
        Connection connect = driver.connect(url, properties);
        System.out.println(connect);

    }

    //方式3 使用DriverManager替代Driver进行统一管理
    @Test
    public void connect03() throws ClassNotFoundException, InstantiationException, IllegalAccessException, SQLException {
        //使用反射加载Driver类,动态加载，减少依赖
        Class<?> aClass = Class.forName("com.mysql.jdbc.Driver");
        Driver driver = (Driver)aClass.newInstance();

        //创建url与user、password
        String url = "jdbc:mysql://localhost:3306/jdbc_01";
        String user = "root";
        String password = "root";

        DriverManager.registerDriver(driver);//注册Driver驱动

        Connection connection = DriverManager.getConnection(url, user, password);
        System.out.println(connection);

    }

    //推荐使用 底层静态代码块已经做了工作
    //方式4
    public void connect04() throws ClassNotFoundException, SQLException {
        //使用反射加载了Driver类
        //在加载Driver类时，
        Class.forName("com.mysql.jdbc.Driver");

        //创建url与user、password
        String url = "jdbc:mysql://localhost:3306/jdbc_01";
        String user = "root";
        String password = "root";

        Connection connection = DriverManager.getConnection(url, user, password);

        System.out.println(connection);
    }


    //方式5(优化方式4)
    public void connect05() throws ClassNotFoundException, IOException, SQLException {
        //通过Properties对象获取配置文件信息
        Properties properties = new Properties();
        properties.load(new FileInputStream("src\\mysql.properties"));

        String user = properties.getProperty("user");
        String password = properties.getProperty("password");
        String driver = properties.getProperty("driver");
        String url = properties.getProperty("url");

        Class.forName(driver);

        Connection connection = DriverManager.getConnection(url, user, password);

        System.out.println(connection);
    }

}
```



![image-20221008223844624](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062341555.png)



```java
package com.momo.JDBCExercise;

import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;
import java.util.Properties;

/**
 * @author momo~
 * @version 1.0
 */
public class JDBCExercise01 {
    public static void main(String[] args) throws IOException, ClassNotFoundException, SQLException {
        //使用方式5
        Properties properties = new Properties();
        properties.load(new FileInputStream("src\\mysql.properties"));

        String url = properties.getProperty("url");
        String user = properties.getProperty("user");
        String password = properties.getProperty("password");
        String driver = properties.getProperty("driver");

        Class.forName(driver);

        Connection connection = DriverManager.getConnection(url, user, password);

        //执行sql
        String sql1 = "create table news (id int primary key,content varchar(32) not null default '')";
        String sql2 = "insert into news values(1,'上海新闻'),(2,'香港新闻'),(3,'长沙新闻'),(4,'明娜几岁'),(5,'敬你一杯')";
        String sql3 = "update news set content = '一个新的消息' where id = 1";
        String sql4 = "delete from news where id = 3";

        Statement statement = connection.createStatement();
        int i = statement.executeUpdate(sql3);

        System.out.println(i > 0 ? "ok" : "file");

        connection.close();
        statement.close();


    }
}

```



![image-20221023215634183](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062341041.png)



```java
public class JDBCExercise02 {
    public static void main(String[] args) throws IOException, ClassNotFoundException, SQLException {
        Properties properties = new Properties();
        properties.load(new FileInputStream("src//mysql.properties"));

        String user = properties.getProperty("user");
        String password = properties.getProperty("password");
        String url = properties.getProperty("url");
        String driver = properties.getProperty("driver");


        Class.forName(driver);

        Connection connection = DriverManager.getConnection(url, user, password);

        //执行sql
        String sql1 = "create table actor(id int primary ley,name varchar(25))";
        String sql2 = "insert into actor values(1,'张三'),(2,'李四'),(3,'王强'),(4,'璐璐'),(5,'吴克')";
        String sql3 = "update actor set name = 'ht' where id = 1";
        String sql4 = "delete from actor where id = 3 ";

        Statement statement = connection.createStatement();
        statement.executeUpdate(sql1);

        connection.close();
        statement.close();
    }
}

```



#### 4.ResultSet结果集

![image-20221023220101256](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062342171.png)



![image-20221023223332177](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062342687.png)



```java
package com.momo.resultset_;

import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.sql.*;
import java.util.Properties;

/**
 * @author momo~
 * @version 1.0
 * 演示select 语句返回ResultSet，并取出结果
 */
public class ResultSet_ {
    public static void main(String[] args) throws IOException, ClassNotFoundException, SQLException {
        //使用方式5
        Properties properties = new Properties();
        properties.load(new FileInputStream("src\\mysql.properties"));

        String url = properties.getProperty("url");
        String user = properties.getProperty("user");
        String password = properties.getProperty("password");
        String driver = properties.getProperty("driver");

        //1.注册驱动
        Class.forName(driver);

        //2.得到连接
        Connection connection = DriverManager.getConnection(url, user, password);

        //3.得到Statement
        Statement statement = connection.createStatement();

        //4.组织sql
        String sql = "select id,name,sex,borndate from actor";

        //执行给定的sql语句，该语句返回单个ResultSet对象
        ResultSet resultSet = statement.executeQuery(sql);

        //使用while循环取出数据
        while(resultSet.next()){
            int id = resultSet.getInt(1);
            String name = resultSet.getString(2);
            String sex = resultSet.getString(3);
            Date date = resultSet.getDate(4);
            System.out.println(id + "\t" + name + "\t" + sex + "\t" + date);
        }

        //关闭连接
        resultSet.close();
        statement.close();
        connection.close();
    }
}

```



#### 5.SQL注入

![image-20221024195806182](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062342623.png)



```mysql
-- 演示SQL注入
-- 创建一张表
CREATE TABLE `admin`(
	`name` VARCHAR(32) NOT NULL UNIQUE,
	pwd VARCHAR(32) NOT NULL DEFAULT '') CHARACTER SET utf8;
	
-- 添加数据
INSERT INTO `admin` VALUES('tom','123');

-- 查找某个管理是否存在
SELECT * FROM ADMIN WHERE `name` = 'tom' AND pwd = '123';

-- sql注入
-- 用户名为 1' or
-- 密码为 or '1' = '1
SELECT * FROM ADMIN WHERE `name` = '1' OR' and pwd = 'OR '1' = '1';
```



![image-20221024205827835](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062342831.png)









#### 6.Statement   ![image-20221024201655615](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062359497.png)

```java
package com.momo.Statement_;

import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.sql.*;
import java.util.Properties;
import java.util.Scanner;

/**
 * @author momo~
 * @version 1.0
 * 演示statement的注入问题
 */
public class Statement_ {
    public static void main(String[] args) throws IOException, ClassNotFoundException, SQLException {

        Scanner scanner = new Scanner(System.in);

        //让用户输入管理员名字和密码
        System.out.println("请输入管理员名字：");
        String admin_name = scanner.nextLine();
        System.out.println("请输入管理员密码：");
        String admin_pwd = scanner.nextLine();

        //通过properties对象获取配置文件信息
        Properties properties = new Properties();
        properties.load(new FileInputStream("src\\mysql.properties"));

        //获取相关的值
        String url = properties.getProperty("url");
        String user = properties.getProperty("user");
        String password = properties.getProperty("password");
        String driver = properties.getProperty("driver");

        //1.注册驱动
        Class.forName(driver);

        //2.得到连接
        Connection connection = DriverManager.getConnection(url, user, password);

        //3.得到Statement
        Statement statement = connection.createStatement();

        //4.组织sql
        String sql = "select name,pwd from admin " +
                "where name = '"+ admin_name +"' and" +
                " pwd = '"+admin_pwd+"'";
        ResultSet resultSet = statement.executeQuery(sql);
        if (resultSet.next()){
            System.out.println("恭喜，登录成功");
        } else {
            System.out.println("抱歉 登录失败");
        }
    }
}

```



#### 7.预处理查询 preparedstatement

![image-20221024211311949](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062342540.png)



![image-20221024214309983](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062342720.png)



```java
package com.momo.preparedstatement_;

import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.sql.*;
import java.util.Properties;
import java.util.Scanner;

/**
 * @author momo~
 * @version 1.0
 * 演示预处理查询
 */
public class PreparedStatement_ {
    public static void main(String[] args) throws IOException, ClassNotFoundException, SQLException {

        Scanner scanner = new Scanner(System.in);

        System.out.println("请输入管理员姓名：");
        String admin_name = scanner.nextLine();
        System.out.println("请输入管理员密码：");
        String admin_pwd = scanner.nextLine();

        //创建properties对象取出配置信息
        Properties properties = new Properties();
        properties.load(new FileInputStream("src\\mysql.properties"));

        //读取配置信息
        String url = properties.getProperty("url");
        String user = properties.getProperty("user");
        String password = properties.getProperty("password");
        String driver = properties.getProperty("driver");

        //1.注册驱动
        Class.forName(driver);

        //2.得到连接
        Connection connection = DriverManager.getConnection(url, user, password);

        //得到sql
        // ? 相当于占位符
        String sql = "select name,pwd from admin where name = ? and pwd = ?";


        //3.得到preparedstatement
        //给?赋值
        PreparedStatement preparedStatement = connection.prepareStatement(sql);
        preparedStatement.setString(1,admin_name);
        preparedStatement.setString(2,admin_pwd);

        ResultSet resultSet = preparedStatement.executeQuery();
        if (resultSet.next()){
            System.out.println("恭喜 登录成功");
        } else {
            System.out.println("抱歉 登录失败");
        }

        resultSet.close();
        preparedStatement.close();
        connection.close();

    }
}

```



#### 8.预处理DML

```java
package com.momo.preparedstatement_;

import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;
import java.util.Properties;
import java.util.Scanner;

/**
 * @author momo~
 * @version 1.0
 */
public class preparedstatement_dml {
    public static void main(String[] args) throws ClassNotFoundException, IOException, SQLException {

        Scanner scanner = new Scanner(System.in);

        System.out.println("请输入管理员名称：");
        String admin_name = scanner.nextLine();
        System.out.println("请输入管理员密码：");
        String admin_pwd = scanner.nextLine();

        //创建properties对象读取配置文件
        Properties properties = new Properties();
        properties.load(new FileInputStream("src\\mysql.properties"));

        //读取配置文件信息
        String url = properties.getProperty("url");
        String user = properties.getProperty("user");
        String password = properties.getProperty("password");
        String driver = properties.getProperty("driver");

        //1.注册驱动
        Class.forName(driver);

        //2.得到连接
        Connection connection = DriverManager.getConnection(url, user, password);

        //编写sql
        String sql = "insert into admin values(?,?)";

        //3.得到Preparedstatement
        PreparedStatement preparedStatement = connection.prepareStatement(sql);
        preparedStatement.setString(1,admin_name);
        preparedStatement.setString(2,admin_pwd);

        //4.
        int rows = preparedStatement.executeUpdate();

        System.out.println(rows > 0 ? "true" : "false");

        //关闭连接
        connection.close();
        preparedStatement.close();

    }
}

```



![image-20221025203753749](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062342092.png)



```java
package com.momo.preparedstatement_;

import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.sql.*;
import java.util.Properties;

/**
 * @author momo~
 * @version 1.0
 * preparedstatement预处理练习，防止sql注入
 */
public class PreparedstatementExercise {
    public static void main(String[] args) throws IOException, ClassNotFoundException, SQLException {
        //创建properties对象取出配置文件信息
        Properties properties = new Properties();
        properties.load(new FileInputStream("src\\mysql.properties"));

        //获取相应的值
        String url = properties.getProperty("url");
        String user = properties.getProperty("user");
        String password = properties.getProperty("password");
        String driver = properties.getProperty("driver");

        //注册驱动
        Class.forName(driver);

        //得到连接
        Connection connection = DriverManager.getConnection(url,user,password);

        //sql
        String sql1 = "create table admin02(id int primary key,name varchar(32) not null default '')";
        String sql2 = "insert into admin02 values(1,'tom'),(2,'smith'),(3,'momo'),(4,'jack'),(5,'patton')";
        String sql3 = "update admin02 set name = 'king' where name = 'tom'";
        String sql4 = "delete from admin02 where id = 3";
        String sql5 = "select * from admin02";

        //得到Preparedstatement
        //创建数据库
//        PreparedStatement preparedStatement = connection.prepareStatement(sql1);
//        int rows = preparedStatement.executeUpdate();
//        System.out.println(rows > 0 ? "成功" : "失败");

        //DML 数据操作语言
        //添加数据
//        PreparedStatement preparedStatement = connection.prepareStatement(sql2);
//        int rows = preparedStatement.executeUpdate();
//        System.out.println(rows > 0 ? "成功" : "失败");

        //修改数据
//        PreparedStatement preparedStatement = connection.prepareStatement(sql3);
//        int rows = preparedStatement.executeUpdate();
//        System.out.println(rows > 0 ? "成功" : "失败");

        //删除数据
//        PreparedStatement preparedStatement = connection.prepareStatement(sql4);
//        int rows = preparedStatement.executeUpdate();
//        System.out.println(rows > 0 ? "成功" : "失败");

        //DQL 数据查询语言
        PreparedStatement preparedStatement = connection.prepareStatement(sql5);
        ResultSet resultSet = preparedStatement.executeQuery();
        while (resultSet.next()){
            int anInt = resultSet.getInt(1);
            String string = resultSet.getString(2);
            System.out.println(anInt + "\t" + string);
        }
        
        //关闭连接
        connection.close();
        preparedStatement.close();
        
    }
}

```



#### 9.JDBC API

![image-20221025212444459](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062342850.png)



#### 10.JDBC Utils开发

![image-20221025212543483](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062342747.png)



![image-20221025212845444](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062343196.png)





JDBCUtils

```java
package com.momo.Utils;

import java.io.FileInputStream;
import java.io.IOException;
import java.sql.*;
import java.util.Properties;

/**
 * @author momo~
 * @version 1.0
 * 这是一个工具类，完成MySQL的连接和关闭资源
 */
public class JDBCUtils {
    //定义相关的属性（4个），因为只需要一份，所以static
    private static String user;     //用户名
    private static String password; //密码
    private static String url;      //url
    private static String driver;   //驱动名

    //在static代码块中初始化
    static {
        try {
            Properties properties = new Properties();
            properties.load(new FileInputStream("src\\mysql.properties"));
            //读取相关属性
            user = properties.getProperty("user");
            password = properties.getProperty("password");
            url = properties.getProperty("url");
            driver = properties.getProperty("driver");
        } catch (IOException e) {
            //在实际开发中，我们这样处理
            //1.将编译异常转成运行异常
            //2.调用者，可以选择捕获异常，也可以默认处理该异常
            throw new RuntimeException(e);
        }
    }

    //连接数据库,返回Connection
    public static Connection getConnection(){
        try {
            return DriverManager.getConnection(url,user,password);
        } catch (SQLException e) {
            throw new RuntimeException(e);
        }
    }

    //关闭资源
    /*
        1.Result 结果集
        2.Statement 或者 PreparedStatement
        3.Connection
        4.如果需要关闭资源，就传入对象，否者传入null
     */

    public static void close(ResultSet set, Statement statement,Connection connection){
        try {
            //判断是否为null
            if (set != null){
                set.close();
            }
            if (statement != null){
                statement.close();
            }
            if (connection != null){
                connection.close();
            }
        } catch (SQLException e) {
            throw new RuntimeException(e);
        }
    }


}

```



```java
package com.momo.Utils;

import org.junit.jupiter.api.Test;

import java.sql.Connection;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.util.Date;

/**
 * @author momo~
 * @version 1.0
 * 演示如何使用JDBCUtils工具类，完成dml与select
 */
public class JDBCUtils_Use {
    public static void main(String[] args) {

    }

    @Test
    public void testDML(){//DML
        //1.得到连接
        Connection connection = null;

        //2.sql
        String sql = "update actor set name = ? where id = ?";

        //3.创建PreparedStatement对象
        PreparedStatement preparedStatement = null;
        try {
            connection = JDBCUtils.getConnection();
            preparedStatement = connection.prepareStatement(sql);
            preparedStatement.setString(1,"周星驰");
            preparedStatement.setInt(2,4);
            preparedStatement.executeUpdate();
        } catch (SQLException e) {
            throw new RuntimeException(e);
        } finally {
            //关闭资源
            JDBCUtils.close(null,preparedStatement,connection);
        }
    }

    @Test
    public void testSelect(){
        //1.得到连接
        Connection connection = null;

        //2.sql
        String sql = "select * from actor";

        //3.创建PreparedStatement对象
        PreparedStatement preparedStatement = null;
        ResultSet set = null;
        try {
            connection = JDBCUtils.getConnection();
            preparedStatement = connection.prepareStatement(sql);
            set = preparedStatement.executeQuery();
            while (set.next()){
                int id = set.getInt("id");
                String name = set.getString("name");
                String sex = set.getString("sex");
                Date borndate = set.getDate("borndate");
                String phone = set.getString("phone");
                System.out.println(id + "\t" + name + "\t" + sex + "\t" + borndate + "\t" + phone);
            }
        } catch (SQLException e) {
            throw new RuntimeException(e);
        } finally {
            //关闭资源
            JDBCUtils.close(set,preparedStatement,connection);
        }
    }
}

```



#### 11.事务

![image-20221026133622173](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062343832.png)



```java
commit()
```

使自上次提交/回滚以来所做的所有更改都将永久性，并释放此 `Connection`对象当前持有的任何数据库锁。

```java
setAutoCommit(boolean autoCommit)
```

将此连接的自动提交模式设置为给定状态。

```java
rollback()
```

撤消在当前事务中所做的所有更改，并释放此 `Connection`对象当前持有的任何数据库锁。



![image-20221026153208320](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062343869.png)



```java
package com.momo.transaction_;

import com.momo.Utils.JDBCUtils;
import org.junit.jupiter.api.Test;

import java.sql.Connection;
import java.sql.PreparedStatement;
import java.sql.SQLException;

/**
 * @author momo~
 * @version 1.0
 * 演示在JDBC中使用事务
 */
public class Transaction {

    @Test
    public void noTransaction(){
        //操作转账业务
        //1.得到连接
        Connection connection = null;

        //2.sql
        String sql = "update account set balance = balance - 100 where id = 1";
        String sql2 = "update account set balance = balance + 100 where id = 2";

        //3.创建PreparedStatement对象
        PreparedStatement preparedStatement = null;
        try {
            connection = JDBCUtils.getConnection();
            preparedStatement = connection.prepareStatement(sql);
            preparedStatement.executeUpdate();

            int i = 1 / 0;//抛出异常
            preparedStatement = connection.prepareStatement(sql2);
            preparedStatement.executeUpdate();
        } catch (SQLException e) {
            throw new RuntimeException(e);
        } finally {
            //关闭资源
            JDBCUtils.close(null,preparedStatement,connection);
        }
    }

    //事务解决
    @Test
    public void useTransaction(){
        //操作转账业务
        //1.得到连接
        Connection connection = null;

        //2.sql
        String sql = "update account set balance = balance - 100 where id = 1";
        String sql2 = "update account set balance = balance + 100 where id = 2";

        //3.创建PreparedStatement对象
        PreparedStatement preparedStatement = null;
        try {
            connection = JDBCUtils.getConnection();

            //将connection设置为不自动提交
            connection.setAutoCommit(false);

            preparedStatement = connection.prepareStatement(sql);
            preparedStatement.executeUpdate();

//            int i = 1 / 0;//抛出异常
            preparedStatement = connection.prepareStatement(sql2);
            preparedStatement.executeUpdate();

            //提交事务
            connection.commit();
        } catch (SQLException e) {
            //这里进行回滚，即撤销sql
            //默认回滚到事务开始状态
            System.out.println("执行发生了异常，撤销执行的sql");
            try {
                connection.rollback();
            } catch (SQLException ex) {
                throw new RuntimeException(ex);
            }
            throw new RuntimeException(e);
        } finally {
            //关闭资源
            JDBCUtils.close(null,preparedStatement,connection);
        }
    }
}

```



#### 12.批处理

![image-20221026154125488](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062343093.png)



![image-20221026154208743](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062343672.png)



```java
//传统方法，添加5000条数据到admin2
    @Test
    public void noBatch() throws SQLException {
        Connection connection = JDBCUtils.getConnection();
        String sql = "insert into admin2 values(null,?,?)";
        PreparedStatement preparedStatement = connection.prepareStatement(sql);

        System.out.println("开始执行");
        long start = System.currentTimeMillis();

        for (int i = 0; i < 5000; i++) {
            preparedStatement.setString(1,"jack" + i);
            preparedStatement.setString(2,"666");
            preparedStatement.executeUpdate();
        }

        long end = System.currentTimeMillis();
        System.out.println("传统方式耗时：" + (end - start));

        //关闭连接
        JDBCUtils.close(null,preparedStatement,connection);
    }
```

![image-20221026160416441](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062343860.png)



```java
//使用批量方式添加数据
    @Test
    public void Batch() throws SQLException {
        Connection connection = JDBCUtils.getConnection();
        String sql = "insert into admin2 values(null,?,?)";
        PreparedStatement preparedStatement = connection.prepareStatement(sql);

        System.out.println("开始执行");
        long start = System.currentTimeMillis();

        for (int i = 0; i < 5000; i++) {
            preparedStatement.setString(1,"jack" + i);
            preparedStatement.setString(2,"666");
            //将sql语句加入到批处理包中，看源码
            preparedStatement.addBatch();
            //当有1000条数据时，批量执行
            if ((i + 1) % 1000 == 0){
                preparedStatement.executeBatch();
                //清空
                preparedStatement.clearBatch();
            }
        }

        long end = System.currentTimeMillis();
        System.out.println("批处理方式耗时：" + (end - start));

        //关闭连接
        JDBCUtils.close(null,preparedStatement,connection);
    }
```



![image-20221026160607631](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062343459.png)



![image-20221026161105623](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062343412.png)





![image-20221026162205991](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062343607.png)



#### 13.数据库连接池

 ![image-20221027131736774](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062343352.png)



```java
    @Test
    public void testCon(){
        //看看连接-关闭 connection会耗时多久
        long start = System.currentTimeMillis();
        for (int i = 0; i < 5000; i++) {
            //使用传统JDBC方式，得到连接
            Connection connection = JDBCUtils.getConnection();
            //相关工作
            //关闭连接
            JDBCUtils.close(null,null,connection);
        }
        long end = System.currentTimeMillis();
        System.out.println("传统方式5000次耗时：" +(end - start));
    }
```

![image-20221027141125517](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062344101.png)



![image-20221027132806057](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062344754.png)





![image-20221027133126199](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062344745.png)





![image-20221027133822716](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062344156.png)



![image-20221027134057141](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062344092.png)





##### 1.C3P0

```java
/**
 * @author momo~
 * @version 1.0
 * 演示数据库连接池C3P0的使用
 */
public class C3P0_ {
    //方式1：相关参数，在程序中指定 user,url,password
    public void testC3P0_01() throws IOException, PropertyVetoException, SQLException {
        //1.创建一个数据源对象
        ComboPooledDataSource comboPooledDataSource = new ComboPooledDataSource();
        //2.通过配置文件mysql.properties获取相关连接信息
        Properties properties = new Properties();
        properties.load(new FileInputStream("src\\mysql.properties"));
        //读取相关属性
        String url = properties.getProperty("url");
        String user = properties.getProperty("user");
        String password = properties.getProperty("password");
        String driver = properties.getProperty("driver");

        //给数据源设置相关参数
        //连接管理是由comboPooledDataSource管理
        comboPooledDataSource.setDriverClass(driver);
        comboPooledDataSource.setJdbcUrl(url);
        comboPooledDataSource.setUser(user);
        comboPooledDataSource.setPassword(password);

        //设置初始化连接数
        comboPooledDataSource.setInitialPoolSize(10);
        //设置最大连接数
        comboPooledDataSource.setMaxPoolSize(50);
        //测试连接池效率 5000次

        long start = System.currentTimeMillis();
        for (int i = 0; i < 5000; i++) {
            Connection connection = comboPooledDataSource.getConnection();
//            System.out.println("连接成功");
            connection.close();
        }
        long end = System.currentTimeMillis();
        System.out.println("C3P0连接池5000次连接MySQL耗时：" + (end - start));
//        Connection connection = comboPooledDataSource.getConnection();
//        System.out.println("连接成功");
//        connection.close();
    }
}
```



![image-20221027141252294](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062344576.png)



```java
//第二种方式 使用配置文件模板来完成
    //1.将c3p0提供的c3p0.config.xml拷贝到src目录下
    //2.该文件制指定了连接数据库和连接池的相关参数
    @Test
    public void testC3P0_02() throws SQLException {
        ComboPooledDataSource momo_edu = new ComboPooledDataSource("momo_edu");
        //测试5000次连接mysql
        long start = System.currentTimeMillis();
        for (int i = 0; i < 5000; i++) {
            Connection connection = momo_edu.getConnection();
//            System.out.println("连接成功2");
            connection.close();
        }
        long end = System.currentTimeMillis();
        System.out.println("C3P0的第二种方式耗时：" + (end - start));
    }
```



```xml
<?xml version="1.0" encoding="UTF-8"?>
 
<c3p0-config>
  <default-config>   
    <property name="driverClass">com.mysql.jdbc.Driver</property>
    <property name="jdbcUrl">jdbc:mysql://localhost:3306/jdbc_01</property>
    <property name="user">root</property>
    <property name="password">root</property>
 
    <property name="initialPoolSize">10</property>
    <property name="maxIdleTime">30</property>
    <property name="maxPoolSize">100</property>
    <property name="minPoolSize">10</property>
  </default-config>
 
  <named-config name="momo_edu">
    <property name="driverClass">com.mysql.jdbc.Driver</property>
    <property name="jdbcUrl">jdbc:mysql://localhost:3306/jdbc_01</property>
    <property name="user">root</property>
    <property name="password">root</property>
 
    <property name="initialPoolSize">10</property>
    <property name="maxIdleTime">30</property>
    <property name="maxPoolSize">100</property>
    <property name="minPoolSize">10</property>
  </named-config>
</c3p0-config>
```



![image-20221027144253007](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062344884.png)



##### 2.Druid（德鲁伊）





```java
@Test
    public void testDruid() throws Exception {
        //1.加入Druid jar包
        //2.加入配置文件 druid.properties,将该文件拷贝至项目的src目录下
        //3.创建Properties对象，读取配置文件
        Properties properties = new Properties();
        properties.load(new FileInputStream("src\\druid.properties"));

        //4.创建一个指定参数的数据库连接池，Druid连接池
        DataSource dataSource = DruidDataSourceFactory.createDataSource(properties);

        long start = System.currentTimeMillis();
        for (int i = 0; i < 500000; i++) {
            Connection connection = dataSource.getConnection();
            connection.close();
        }
        long end = System.currentTimeMillis();
        System.out.println("druid连接池 操作500000耗时：" + (end - start));
    }
```



```properties
#key=value
driverClassName=com.mysql.jdbc.Driver
url=jdbc:mysql://localhost:3306/jdbc_01?rewriteBatchedStatements=true
username=root
password=root
#initial connection Size
initialSize=10
#min idle connection size
minIdle=5
#max active connection size
maxActive=50
#max wait time (5000 mil seconds)
maxWait=5000
```



![image-20221027151611385](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062344982.png)





德鲁伊工具类

```java
public class JDBCUtilsExercise {
    @Test
    public void testSelect(){

        //1.得到连接
        Connection connection = null;

        //2.sql
        String sql = "select * from actor";

        //3.创建PreparedStatement对象
        PreparedStatement preparedStatement = null;
        ResultSet set = null;
        try {
            connection = JDBCUtilsByDruid.getConnection();
            preparedStatement = connection.prepareStatement(sql);
            set = preparedStatement.executeQuery();
            while (set.next()){
                int id = set.getInt("id");
                String name = set.getString("name");
                String sex = set.getString("sex");
                Date borndate = set.getDate("borndate");
                String phone = set.getString("phone");
                System.out.println(id + "\t" + name + "\t" + sex + "\t" + borndate + "\t" + phone);
            }
        } catch (SQLException e) {
            throw new RuntimeException(e);
        } finally {
            //关闭资源
            JDBCUtilsByDruid.close(set,preparedStatement,connection);
        }
    }
}
```







#### 14.Apache_DBUtils

![image-20221027164224523](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062344671.png)



自定义封装

```java
public class JDBCUtilsExercise {
    @Test
    public void testSelect(){

        //1.得到连接
        Connection connection = null;

        //2.sql
        String sql = "select * from actor";

        //3.创建PreparedStatement对象
        PreparedStatement preparedStatement = null;
        ResultSet set = null;

        ArrayList<Actor> list = new ArrayList<>();

        try {
            connection = JDBCUtilsByDruid.getConnection();
            preparedStatement = connection.prepareStatement(sql);
            set = preparedStatement.executeQuery();
            while (set.next()){
                int id = set.getInt("id");
                String name = set.getString("name");
                String sex = set.getString("sex");
                Date borndate = set.getDate("borndate");
                String phone = set.getString("phone");
//                System.out.println(id + "\t" + name + "\t" + sex + "\t" + borndate + "\t" + phone);
                //把得到的resultset记录，封装到Actor对象，放入到list集合
                list.add(new Actor(id,name,sex,borndate,phone));
            }
            System.out.println("list集合数据=" + list);
        } catch (SQLException e) {
            throw new RuntimeException(e);
        } finally {
            //关闭资源
            JDBCUtilsByDruid.close(set,preparedStatement,connection);
        }
    }
}
```



![image-20221027183022727](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062344196.png)



![image-20221027193211718](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062344261.png)



```java
public class DBUtils_USE {
    //使用apache DBUtils工具类 + druid完成对表的crud
    public void testQueryMany() throws SQLException {//返回结果是多行的情况
        //1.得到连接druid
        Connection connection = JDBCUtilsByDruid.getConnection();
        //2.使用DBUtils类和接口，先引入DBUtils相关jar，加入到本地project
        //3.创建QueryRunner
        QueryRunner queryRunner = new QueryRunner();
        //4.可以执行相关方法，返回ArrayList结果集
        String sql = "select * from actor where id >= ?";
        //(1)query()方法就是执行sql语句，得到resultset封装到ArrayList集合中
        //(2)返回集合
        //(3)connection:连接
        //(4)sql:执行的sql语句
        //(5)new BeanListHandler<>(Actor.class):
        List<Actor> list = queryRunner.query(connection, sql, new BeanListHandler<>(Actor.class),1);

        System.out.println("输出集合的信息");
        for (Actor actor : list) {
            System.out.println(actor);
        }

        //释放资源
        JDBCUtilsByDruid.close(null,null,connection);

    }

    //演示apache-dbutils + druid完成返回的结果是单行记录（单个对象）
    @Test
    public void testQuerySingle() throws SQLException {
        //1.得到连接druid
        Connection connection = JDBCUtilsByDruid.getConnection();
        //2.使用DBUtils类和接口，先引入DBUtils相关的jar，加入到本地project
        //3.创建QueryRunner
        QueryRunner queryRunner = new QueryRunner();
        //4.执行相关方法，返回单个对象
        String sql = "select * from actor where id = ?";
        //返回的是单行记录、单个对象，使用的是BeanHandler
        Actor actor = queryRunner.query(connection, sql, new BeanHandler<>(Actor.class));
        System.out.println(actor);

        //释放资源
        JDBCUtilsByDruid.close(null,null,connection);
    }


    //演示apache-dbutils + druid完成返回的结果是单行记录（单个对象）
    @Test
    public void testScalar() throws SQLException {
        //1.得到连接druid
        Connection connection = JDBCUtilsByDruid.getConnection();
        //2.使用DBUtils类和接口，先引入DBUtils相关的jar，加入到本地project
        //3.创建QueryRunner
        QueryRunner queryRunner = new QueryRunner();
        //4.执行相关方法，返回单个对象
        String sql = "select name from actor where id = ?";
        //返回的是单行单列，单个对象，使用的是ScalarHandler
        Object obj = queryRunner.query(connection, sql, new ScalarHandler<>(), 4);
        System.out.println(obj);

        //释放资源
        JDBCUtilsByDruid.close(null,null,connection);
    }


    //Apache_DBUtils + Druid 完成DML
    @Test
    public void testDML() throws SQLException {
        //1.得到连接druid
        Connection connection = JDBCUtilsByDruid.getConnection();
        //2.使用DBUtils类和接口，先引入DBUtils相关的jar，加入到本地project
        //3.创建QueryRunner
        QueryRunner queryRunner = new QueryRunner();

        //4.sql
//        String sql = "update actor set name = ? where id = ?";
//        String sql2 = "insert into actor values(null,'林青霞','女','1991-1-2','113')";
//        String sql2 = "insert into actor values(null,?,?,?,?)";
        String sql3 = "delete from actor where id = ?";


        //(1)执行DML操作是queryRunner.update()
        //(2)返回的是受影响的行数
//        int affectedRow = queryRunner.update(connection, sql, "张三丰", 4);
//        int affectedRow = queryRunner.update(connection, sql2, "林青霞","女","1991-1-2","113");
        int affectedRow = queryRunner.update(connection, sql3, 5);
        System.out.println(affectedRow > 0 ? "执行成功" : "无影响");

        //释放资源
        JDBCUtilsByDruid.close(null,null,connection);
    }
```



![image-20221027211119164](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062345738.png)





#### 15.BasicDao

![image-20221027212831916](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062345364.png)



![image-20221027213736693](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062345125.png)





![image-20221027213041130](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062345366.png)





![image-20221028221810416](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062345028.png)



```java
package com.momo.dao_.dao;

import com.momo.dao_.domain.Actor;

/**
 * @author momo~
 * @version 1.0
 */
public class ActorDAO extends BasicDAO<Actor>{
    //1.继承自BasicDAO
    //2.根据业务需求，可以编写特有的方法
}
```



```java
package com.momo.dao_.dao;

import com.momo.dao_.utils.JDBCUtilsByDruid;
import org.apache.commons.dbutils.QueryRunner;
import org.apache.commons.dbutils.handlers.BeanHandler;
import org.apache.commons.dbutils.handlers.BeanListHandler;
import org.apache.commons.dbutils.handlers.ScalarHandler;
import org.junit.jupiter.api.Test;

import java.sql.Connection;
import java.sql.SQLException;
import java.util.List;
import java.util.Objects;

/**
 * @author momo~
 * @version 1.0
 * 开发BasicDAO,是其他DAO的父类
 */
public class BasicDAO<T> {  //泛型指定具体类型

    private QueryRunner qr = new QueryRunner();

    //开发通用的dml方法，针对任意的表
    @Test
    public int update(String sql,Object... parameters){
        Connection connection = null;

        try {
            connection = JDBCUtilsByDruid.getConnection();
            int update = qr.update(connection, sql, parameters);
            return update;
        } catch (SQLException e) {
            throw new RuntimeException(e);
        } finally {
            JDBCUtilsByDruid.close(null,null,connection);
        }
    }

    /**
     *
     * @param sql sql语句，可以有？
     * @param clazz 传入一个类的Class对象，比如Actor.class
     * @param parameters 传入？的具体的值，可以是多个
     * @return 根据Actor.class 返回对应的ArrayList集合
     */
    //返回多个对象（即查询的结果是多行），针对任意表
    @Test
    public List<T> queryMulti(String sql,Class<T> clazz,Object... parameters){
        Connection connection = null;
        try {
            connection = JDBCUtilsByDruid.getConnection();
            return qr.query(connection,sql,new BeanListHandler<>(clazz),parameters);
        } catch (SQLException e) {
            throw new RuntimeException(e);
        } finally {
            JDBCUtilsByDruid.close(null,null,connection);
        }
    }

    //查询单行结果的通用方法
    @Test
    public T querySingle(String sql,Class<T> clazz,Object... parameters){
        Connection connection = null;
        try {
            connection = JDBCUtilsByDruid.getConnection();
            return qr.query(connection,sql,new BeanHandler<>(clazz),parameters);
        } catch (SQLException e) {
            throw new RuntimeException(e);
        } finally {
            JDBCUtilsByDruid.close(null,null,connection);
        }
    }

    //查询单行单列的方法，即返回单值的方法
    @Test
    public Objects queryScalar(String sql, Object... parameters){
        Connection connection = null;
        try {
            connection = JDBCUtilsByDruid.getConnection();
            return qr.query(connection,sql,new ScalarHandler<>(),parameters);
        } catch (SQLException e) {
            throw new RuntimeException(e);
        } finally {
            JDBCUtilsByDruid.close(null,null,connection);
        }
    }
}

```



```java
package com.momo.dao_.dao;

/**
 * @author momo~
 * @version 1.0
 */
public class GoodsDAO extends BasicDAO{
    //1.继承自BasicDAO
    //2.根据业务需求，可以编写特有的方法
}

```



```java
package com.momo.dao_.domain;

import java.util.Date;

/**
 * @author momo~
 * @version 1.0
 * Actor对象和actor表的记录对应
 */
public class Actor {
    private Integer id;
    private String name;
    private String sex;
    private Date borndate;
    private String phone;

    public Actor(){
    }

    public Actor(Integer id, String name, String sex, Date borndate, String phone) {
        this.id = id;
        this.name = name;
        this.sex = sex;
        this.borndate = borndate;
        this.phone = phone;
    }

    public Integer getId() {
        return id;
    }

    public void setId(Integer id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getSex() {
        return sex;
    }

    public void setSex(String sex) {
        this.sex = sex;
    }

    public Date getBorndate() {
        return borndate;
    }

    public void setBorndate(Date borndate) {
        this.borndate = borndate;
    }

    public String getPhone() {
        return phone;
    }

    public void setPhone(String phone) {
        this.phone = phone;
    }

    @Override
    public String toString() {
        return "Actor{" +
                "id=" + id +
                ", name='" + name + '\'' +
                ", sex='" + sex + '\'' +
                ", borndate=" + borndate +
                ", phone='" + phone + '\'' +
                '}'+"\n";
    }
}

```



```java
package com.momo.dao_.domain;

/**
 * @author momo~
 * @version 1.0
 * Goods对象和goods表的记录对应
 */
public class Goods {
    private Integer id;
    private String goods_name;
    private Double price;

    public Goods() {
    }

    public Goods(Integer id, String goods_name, Double price) {
        this.id = id;
        this.goods_name = goods_name;
        this.price = price;
    }

    public Integer getId() {
        return id;
    }

    public void setId(Integer id) {
        this.id = id;
    }

    public String getGoods_name() {
        return goods_name;
    }

    public void setGoods_name(String goods_name) {
        this.goods_name = goods_name;
    }

    public Double getPrice() {
        return price;
    }

    public void setPrice(Double price) {
        this.price = price;
    }

    @Override
    public String toString() {
        return "Goods{" +
                "id=" + id +
                ", goods_name='" + goods_name + '\'' +
                ", price=" + price +
                '}';
    }
}

```



```java
package com.momo.dao_.test;

import com.momo.dao_.dao.ActorDAO;
import com.momo.dao_.dao.GoodsDAO;
import com.momo.dao_.domain.Actor;
import com.momo.dao_.domain.Goods;
import org.junit.jupiter.api.Test;

import javax.jws.soap.SOAPBinding;
import java.util.Objects;

/**
 * @author momo~
 * @version 1.0
 */
public class TestDAO {
    //测试ActorDAO 对actor表crud操作

    public void testActorDAO(){
        ActorDAO actorDAO = new ActorDAO();

        //1.查询
        for (Actor actor : actorDAO.queryMulti("select * from actor where id = ?", Actor.class, 1)) {
            System.out.println(actor);
        }

        //2.查询单行记录
        Actor actor = actorDAO.querySingle("select * from actor where id = ?", Actor.class, 6);
        System.out.println(actor);

        //3.查询单行单列
        Objects objects = actorDAO.queryScalar("select name from actor where id = ?", 6);
        System.out.println(objects);

        //4.dml操作
        int update = actorDAO.update("insert into actor values(null,?,?,?,?)", "张无忌", "男", "23", "199-2-6");
        System.out.println(update > 0 ? "执行成功" : "执行没有影响");

    }

    @Test
    public void testGoodsDAO(){
        GoodsDAO goodsDAO = new GoodsDAO();

        //1.查询
        for (Object o1 : goodsDAO.queryMulti("select * from goods where id = ?", Goods.class, 1)) {
            System.out.println(o1);
        }

        //2.查询单行记录
        Object o2= goodsDAO.querySingle("select * from goods where id = ?", Goods.class, 1);
        System.out.println(o2);

        //3.查询单行单列
        Objects o3 = goodsDAO.queryScalar("select name from goods where id = ?", Goods.class, 1);
        System.out.println(o3);

        //4.DML操作
        int update = goodsDAO.update("insert into goods values(null,?,?)", "smith", 20);
        System.out.println(update > 0 ? "执行成功" : "执行没有影响");

    }
}

```





```java
package com.momo.dao_.utils;

import com.alibaba.druid.pool.DruidDataSourceFactory;

import javax.sql.DataSource;
import java.io.FileInputStream;
import java.sql.Connection;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;
import java.util.Properties;

/**
 * @author momo~
 * @version 1.0
 * 基于Druid数据库连接池的工具类
 */
public class JDBCUtilsByDruid {

    private static DataSource ds;

    //在静态代码块中完成ds初始化

    static {
        Properties properties = new Properties();
        try {
            properties.load(new FileInputStream("src\\druid.properties"));
            ds = DruidDataSourceFactory.createDataSource(properties);
        } catch (Exception e) {
            throw new RuntimeException(e);
        }

    }

    //编写getConnection方法
    public static Connection getConnection() throws SQLException {
        return ds.getConnection();
    }

    //关闭连接，在数据库连接池技术中不是真的断掉连接，而是把使用的Connection对象放回连接池
    public static void close(ResultSet resultSet, Statement statement,Connection connection){
        try {
            if (resultSet != null){
                resultSet.close();
            }

            if (statement != null){
                statement.close();
            }

            if (connection != null){
                connection.close();
            }
        } catch (SQLException e) {
            throw new RuntimeException(e);
        }


    }

}

```



## 21.项目—餐饮系统

![image-20221120210450391](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062345983.png)



![image-20221120212030074](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062346080.png)





**1.准备工具类，搭建项目整体结构**

![image-20221120214302416](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062346573.png)



**2.显示菜单，准备界面**

![image-20221120214344754](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062345570.png)



**3.验证用户登录**

![image-20221120223118596](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062346817.png)



**4.显示餐桌状态**

![image-20221123192819110](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062346157.png)



**5.订座**

![image-20221124103456271](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062346251.png)



**6.显示菜单**

![image-20221124103443987](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062346576.png)



**7.点餐**

![image-20230126214600479](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062346848.png)



![image-20230126214842717](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062347055.png)



**8.查看账单**

![image-20230127115651447](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062347029.png)



**9.结账**

![image-20230127164427322](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062347706.png)



**10.多表查询**

![image-20230127211843788](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062347811.png)



**11.分表扩展**

![image-20230127215826518](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062347327.png)



![image-20230127220139611](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062347556.png)



![image-20230127220410917](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062347692.png)



项目代码：

![image-20230127220526408](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062347589.png)



![image-20230127220556587](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062347332.png)

```java
package com.momo.mhl.dao;


import com.momo.mhl.utils.JDBCUtilsByDruid;
import org.apache.commons.dbutils.QueryRunner;
import org.apache.commons.dbutils.handlers.BeanHandler;
import org.apache.commons.dbutils.handlers.BeanListHandler;
import org.apache.commons.dbutils.handlers.ScalarHandler;
import org.junit.jupiter.api.Test;

import java.sql.Connection;
import java.sql.SQLException;
import java.util.List;
import java.util.Objects;

/**
 * @author momo~
 * @version 1.0
 * 开发BasicDAO,是其他DAO的父类
 */
public class BasicDAO<T> {  //泛型指定具体类型

    private QueryRunner qr = new QueryRunner();

    //开发通用的dml方法，针对任意的表
    @Test
    public int update(String sql, Object... parameters) {
        Connection connection = null;

        try {
            connection = JDBCUtilsByDruid.getConnection();
            int update = qr.update(connection, sql, parameters);
            return update;
        } catch (SQLException e) {
            throw new RuntimeException(e);
        } finally {
            JDBCUtilsByDruid.close(null, null, connection);
        }
    }

    /**
     * @param sql        sql语句，可以有？
     * @param clazz      传入一个类的Class对象，比如Actor.class
     * @param parameters 传入？的具体的值，可以是多个
     * @return 根据Actor.class 返回对应的ArrayList集合
     */
    //返回多个对象（即查询的结果是多行），针对任意表
    @Test
    public List<T> queryMulti(String sql, Class<T> clazz, Object... parameters) {
        Connection connection = null;
        try {
            connection = JDBCUtilsByDruid.getConnection();
            return qr.query(connection, sql, new BeanListHandler<>(clazz), parameters);
        } catch (SQLException e) {
            throw new RuntimeException(e);
        } finally {
            JDBCUtilsByDruid.close(null, null, connection);
        }
    }

    //查询单行结果的通用方法
    @Test
    public T querySingle(String sql, Class<T> clazz, Object... parameters) {
        Connection connection = null;
        try {
            connection = JDBCUtilsByDruid.getConnection();
            return qr.query(connection, sql, new BeanHandler<>(clazz), parameters);
        } catch (SQLException e) {
            throw new RuntimeException(e);
        } finally {
            JDBCUtilsByDruid.close(null, null, connection);
        }
    }

    //查询单行单列的方法，即返回单值的方法
    @Test
    public Objects queryScalar(String sql, Object... parameters) {
        Connection connection = null;
        try {
            connection = JDBCUtilsByDruid.getConnection();
            return qr.query(connection, sql, new ScalarHandler<>(), parameters);
        } catch (SQLException e) {
            throw new RuntimeException(e);
        } finally {
            JDBCUtilsByDruid.close(null, null, connection);
        }
    }
}

```



![image-20230127220756129](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062347873.png)

```java
package com.momo.mhl.dao;

import com.momo.mhl.domain.Bill;

/**
 * @author momo~
 * @version 1.0
 */
public class BillDAO extends BasicDAO<Bill>{
}

```



![image-20230127220828088](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062347784.png)

```java
package com.momo.mhl.dao;

import com.momo.mhl.domain.DiningTable;

/**
 * @author momo~
 * @version 1.0
 */
public class DiningTableDAO extends BasicDAO<DiningTable>{
    //可做特有操作
}

```



![image-20230127220851735](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062347685.png)

```java
package com.momo.mhl.dao;

import com.momo.mhl.domain.Employee;

/**
 * @author momo~
 * @version 1.0
 */
public class EmployeeDAO extends BasicDAO<Employee>{
    //可做特有操作
}

```



![image-20230127220913819](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062347416.png)

```java
package com.momo.mhl.dao;

import com.momo.mhl.domain.Menu;

/**
 * @author momo~
 * @version 1.0
 */
public class MenuDAO extends BasicDAO<Menu>{
    //可做特有操作
}

```



![image-20230127220935205](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062347772.png)

```java
package com.momo.mhl.dao;

import com.momo.mhl.domain.MultiTableBean;

/**
 * @author momo~
 * @version 1.0
 */
public class MultiTableDAO extends BasicDAO<MultiTableBean>{
}

```



![image-20230127220956033](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062347474.png)

```java
package com.momo.mhl.domain;

import java.util.Date;

/**
 * @author momo~
 * @version 1.0
 * Bill是javabean和bill对应
 * CREATE TABLE bill(
 * id INT PRIMARY KEY AUTO_INCREMENT,#自增主键
 * billId VARCHAR(50) NOT NULL DEFAULT '',
 * menuId INT NOT NULL DEFAULT 0,#菜品编号
 * nums INT NOT NULL DEFAULT 0,#份数
 * money DOUBLE NOT NULL DEFAULT 0,#金额
 * diningTableId INT NOT NULL DEFAULT 0,#餐桌
 * billDate DATETIME NOT NULL,#订单日期
 * state VARCHAR(50) NOT NULL DEFAULT ''
 * )CHARSET=utf8;
 */
public class Bill {
    private Integer id;
    private String billId;
    private Integer menuId;
    private Integer nums;
    private Double money;
    private Integer diningTableId;
    private Date billDate;
    private String state;

    public Bill() {
    }

    public Bill(Integer id, String billId, Integer menuId, Integer nums, Double money, Integer diningTableId, Date billDate, String state) {
        this.id = id;
        this.billId = billId;
        this.menuId = menuId;
        this.nums = nums;
        this.money = money;
        this.diningTableId = diningTableId;
        this.billDate = billDate;
        this.state = state;
    }

    public Integer getId() {
        return id;
    }

    public void setId(Integer id) {
        this.id = id;
    }

    public String getBillId() {
        return billId;
    }

    public void setBillId(String billId) {
        this.billId = billId;
    }

    public Integer getMenuId() {
        return menuId;
    }

    public void setMenuId(Integer menuId) {
        this.menuId = menuId;
    }

    public Integer getNums() {
        return nums;
    }

    public void setNums(Integer nums) {
        this.nums = nums;
    }

    public Double getMoney() {
        return money;
    }

    public void setMoney(Double money) {
        this.money = money;
    }

    public Integer getDiningTableId() {
        return diningTableId;
    }

    public void setDiningTableId(Integer diningTableId) {
        this.diningTableId = diningTableId;
    }

    public Date getBillDate() {
        return billDate;
    }

    public void setBillDate(Date billDate) {
        this.billDate = billDate;
    }

    public String getState() {
        return state;
    }

    public void setState(String state) {
        this.state = state;
    }

    @Override
    public String toString() {
        return id +
                "\t\t" + menuId +
                "\t\t\t" + nums +
                "\t\t\t" + money +
                "\t" + diningTableId +
                "\t\t" + billDate +
                "\t\t" + state;
    }
}

```



![image-20230127221022500](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062347274.png)

```java
package com.momo.mhl.domain;

/**
 * @author momo~
 * @version 1.0
 * 这是一个javabean和diningTable表对应
 * id INT PRIMARY KEY AUTO_INCREMENT,
 * state VARCHAR(20) NOT NULL DEFAULT '',#餐桌状态
 * orderName VARCHAR(50) NOT NULL DEFAULT '',#点餐人姓名
 * orderTel VARCHAR(20) NOT NULL DEFAULT ''#点餐人电话
 */
public class DiningTable {
    private Integer id;
    private String state;
    private String orderName;
    private String orderTel;

    public DiningTable() {
    }

    public DiningTable(Integer id, String state, String orderName, String orderTel) {
        this.id = id;
        this.state = state;
        this.orderName = orderName;
        this.orderTel = orderTel;
    }

    public Integer getId() {
        return id;
    }

    public void setId(Integer id) {
        this.id = id;
    }

    public String getState() {
        return state;
    }

    public void setState(String state) {
        this.state = state;
    }

    public String getOrderName() {
        return orderName;
    }

    public void setOrderName(String orderName) {
        this.orderName = orderName;
    }

    public String getOrderTel() {
        return orderTel;
    }

    public void setOrderTel(String orderTel) {
        this.orderTel = orderTel;
    }

    @Override
    public String toString() {
        return id + "\t\t\t" + state;
    }
}

```



![image-20230127221051044](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062348325.png)

```java
package com.momo.mhl.domain;

/**
 * @author momo~
 * @version 1.0
 * 这是一个javabean 和 employee表对应
 * -- 创建用户employee表
 * CREATE TABLE employee(
 * 	id INT PRIMARY KEY AUTO_INCREMENT,#主键
 * 	empId VARCHAR(10) NOT NULL DEFAULT '',#员工号
 * 	pwd CHAR(32) NOT NULL DEFAULT '',#密码
 * 	`name` VARCHAR(50) NOT NULL DEFAULT '',#姓名
 * 	job VARCHAR(50) NOT NULL DEFAULT '')CHARSET=utf8#工作
 */
public class Employee {
    private Integer id;
    private String empId;
    private String pwd;
    private String name;
    private String Job;

    public Employee() {
    }

    public Employee(Integer id, String empId, String pwd, String name, String job) {
        this.id = id;
        this.empId = empId;
        this.pwd = pwd;
        this.name = name;
        Job = job;
    }

    public Integer getId() {
        return id;
    }

    public void setId(Integer id) {
        this.id = id;
    }

    public String getEmpId() {
        return empId;
    }

    public void setEmpId(String empId) {
        this.empId = empId;
    }

    public String getPwd() {
        return pwd;
    }

    public void setPwd(String pwd) {
        this.pwd = pwd;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getJob() {
        return Job;
    }

    public void setJob(String job) {
        Job = job;
    }
}

```



![image-20230127221115905](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062348242.png)

```java
package com.momo.mhl.domain;

/**
 * @author momo~
 * @version 1.0
 * 该类（javabean）和menu表对应
 * 	id int primary key auto_increment,
 * 	`name` varchar(50) not null default '',#菜品名称
 * 	`type` varchar(50) not null default '',#菜品种类
 * 	price double not null default 0#价格
 */
public class Menu {
    private Integer id;
    private String name;
    private String type;
    private Double price;

    public Menu() {
    }

    public Menu(Integer id, String name, String type, Double price) {
        this.id = id;
        this.name = name;
        this.type = type;
        this.price = price;
    }

    public Integer getId() {
        return id;
    }

    public void setId(Integer id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getType() {
        return type;
    }

    public void setType(String type) {
        this.type = type;
    }

    public Double getPrice() {
        return price;
    }

    public void setPrice(Double price) {
        this.price = price;
    }

    @Override
    public String toString() {
        return id +"\t\t\t"+ name + "\t\t" + type + "\t\t" + price;
    }
}

```



![image-20230127221136828](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062348835.png)

```java
package com.momo.mhl.domain;

import java.util.Date;

/**
 * @author momo~
 * @version 1.0
 * 这是一个javabean，可以和多张表进行对应
 */
public class MultiTableBean {
    private Integer id;
    private String billId;
    private Integer menuId;
    private Integer nums;
    private Double money;
    private Integer diningTableId;
    private Date billDate;
    private String state;

    //增加一个来自menu表的name
    private String name;

    //增加一个来自menu表的price
    private Double price;

    public MultiTableBean() {
    }

    public MultiTableBean(Integer id, String billId, Integer menuId, Integer nums, Double money, Integer diningTableId, Date billDate, String state, String name, Double price) {
        this.id = id;
        this.billId = billId;
        this.menuId = menuId;
        this.nums = nums;
        this.money = money;
        this.diningTableId = diningTableId;
        this.billDate = billDate;
        this.state = state;
        this.name = name;
        this.price = price;
    }

    public Double getPrice() {
        return price;
    }

    public void setPrice(Double price) {
        this.price = price;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public Integer getId() {
        return id;
    }

    public void setId(Integer id) {
        this.id = id;
    }

    public String getBillId() {
        return billId;
    }

    public void setBillId(String billId) {
        this.billId = billId;
    }

    public Integer getMenuId() {
        return menuId;
    }

    public void setMenuId(Integer menuId) {
        this.menuId = menuId;
    }

    public Integer getNums() {
        return nums;
    }

    public void setNums(Integer nums) {
        this.nums = nums;
    }

    public Double getMoney() {
        return money;
    }

    public void setMoney(Double money) {
        this.money = money;
    }

    public Integer getDiningTableId() {
        return diningTableId;
    }

    public void setDiningTableId(Integer diningTableId) {
        this.diningTableId = diningTableId;
    }

    public Date getBillDate() {
        return billDate;
    }

    public void setBillDate(Date billDate) {
        this.billDate = billDate;
    }

    public String getState() {
        return state;
    }

    public void setState(String state) {
        this.state = state;
    }

    @Override
    public String toString() {
        return  id +
                "\t\t" + menuId +
                "\t\t\t" + nums +
                "\t\t\t" + money +
                "\t" + diningTableId +
                "\t\t" + billDate +
                "\t\t" + state +
                "\t\t" + name +
                "\t\t" + price;
    }
}

```



![image-20230127221159042](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062348657.png)

```java
package com.momo.mhl.service;

import com.momo.mhl.dao.BillDAO;
import com.momo.mhl.dao.MultiTableDAO;
import com.momo.mhl.domain.Bill;
import com.momo.mhl.domain.MultiTableBean;

import java.util.List;
import java.util.UUID;

/**
 * @author momo~
 * @version 1.0
 * 处理和账单相关的业务逻辑
 */
public class BillService {
    //定义BillDao属性
    private BillDAO billDAO = new BillDAO();

    private MenuService menuService = new MenuService();

    private DiningTableService diningTableService = new DiningTableService();

    private MultiTableDAO multiTableDAO = new MultiTableDAO();

    //思考
    //编写点餐的方法
    //1.生成账单

    //3.如果成功返回true，否则返回false
    public boolean orderMenu(int menuId,int nums,int diningTableId){
        //生成一个账单号，UUID
        String billID = UUID.randomUUID().toString();

        //将账单生成到bill表，要求直接计算账单金额
        int update = billDAO.update("insert into bill values(null,?,?,?,?,?,now(),'未结账')",
        billID,menuId,nums,menuService.getMenuById(menuId).getPrice() * nums,diningTableId);

        if (update <= 0){
            return false;
        }

        //2.需要更新对应餐桌的状态
        return diningTableService.updateDiningTableState(diningTableId,"就餐中");
    }

    //返回所有账单，提供给View调用
    public List<Bill> list(){
        return billDAO.queryMulti("select * from bill",Bill.class);
    }

    //查看某个餐桌是否有未结账的账单
    public boolean hasPayBillByDiningTableId(int diningTableId){
        Bill bill = billDAO.querySingle("SELECT * FROM bill WHERE diningTableId = ? AND state = '未结账' LIMIT 0,1",Bill.class,diningTableId);
        return bill != null;
    }

    //完成结账【如果餐桌存在，并且该餐桌有未结账的账单】
    public boolean payBill(int diningTableId,String payMode){
        //1.修改bill表
        int update = billDAO.update("update bill set state = ? where diningTableId = ? and state = '未结账'",payMode,diningTableId);
        if (update <= 0 ){
            return false;
        }

        //2.修改diningTable表
        //不要直接在这里操作，而是应该调用DiningTableService方法
        if (!diningTableService.updateDiningTableTOFree(diningTableId,"空")){
            return false;
        }
        return true;
    }

    //返回所有账单，提供给View调用
    public List<MultiTableBean> list2(){
        return multiTableDAO.queryMulti("SELECT bill.*,`name`,price " +
                "FROM bill,menu " +
                "WHERE bill.menuId = menu.id;", MultiTableBean.class);
    }

}

```



![image-20230127221218605](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062348940.png)

```java
package com.momo.mhl.service;

import com.momo.mhl.dao.DiningTableDAO;
import com.momo.mhl.domain.DiningTable;

import java.util.List;


/**
 * @author momo~
 * @version 1.0
 */
public class DiningTableService {
    //定义一个DiningTableDAO对象
    private DiningTableDAO diningTableDAO = new DiningTableDAO();

    //返回所有餐桌信息
    public List<DiningTable> list(){
        return diningTableDAO.queryMulti("select id,state from diningTable",DiningTable.class);
    }

    //根据id，查询对应的餐桌DiningTable对象
    //如果返回null，表示id编号对应的餐桌不存在
    public DiningTable getDiningTableById(int id){
        return diningTableDAO.querySingle("select * from diningTable where id = ?",DiningTable.class,id);
    }

    //如果餐桌可以预定，调用方法，对其状态进行更新（包括预定人的名字和电话）
    public boolean orderDiningTable(int id,String orderName,String orderTel){
        int update = diningTableDAO.update("update diningTable set state = '已经预定',orderName = ?,orderTel = ? where id = ?", orderName, orderTel,id);
        return update > 0;
    }

    //需要一个更新餐桌状态的方法
    public boolean updateDiningTableState(int id,String state){
        int update = diningTableDAO.update("update diningTable set state = ? where id = ?",state,id);
        return update > 0;
    }

    //提供方法，将指定餐桌设置为空闲状态
    public boolean updateDiningTableTOFree(int id,String state){
        int update = diningTableDAO.update("update diningTable set state = ?,orderName = '',orderTel = '' where id = ?",state,id);
        return update > 0;
    }
}

```



![image-20230127221238780](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062348535.png)

```java
package com.momo.mhl.service;

import com.momo.mhl.dao.EmployeeDAO;
import com.momo.mhl.domain.Employee;

/**
 * @author momo~
 * @version 1.0
 * 该类完成对employee表的各种操作（通过调用EmployeeDao对象完成）
 */
public class EmployeeService {

    //定义一个EmployeeDAO属性
    private EmployeeDAO employeeDAO = new EmployeeDAO();

    //方法，根据empId 和 pwd 返回一个Employee对象
    //如果查询不到，就返回null
    public Employee getEmployeeByIdAndPwd(String empId,String pwd){
        return employeeDAO.querySingle("select * from employee where empId = ? and pwd = md5(?)",Employee.class,empId,pwd);
    }
}

```



![image-20230127221259305](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062348692.png)

```java
package com.momo.mhl.service;

import com.momo.mhl.dao.MenuDAO;
import com.momo.mhl.domain.Menu;

import java.util.List;

/**
 * @author momo~
 * @version 1.0
 * 完成对menu表的各种操作
 */
public class MenuService {

    //定义MenuDAO
    private MenuDAO menuDAO = new MenuDAO();

    //返回所有的菜品，返回给界面使用
    public List<Menu> list(){
        return menuDAO.queryMulti("select * from menu",Menu.class);
    }

    //需要方法，根据id，返回Menu对象
    public Menu getMenuById(int id){
        return menuDAO.querySingle("select * from menu where id = ?",Menu.class,id);
    }
}

```



![image-20230127221327112](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062348401.png)

```java
package com.momo.mhl.utils;

import com.alibaba.druid.pool.DruidDataSourceFactory;

import javax.sql.DataSource;
import java.io.FileInputStream;
import java.sql.Connection;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;
import java.util.Properties;

/**
 * @author momo~
 * @version 1.0
 * 基于Druid数据库连接池的工具类
 */
public class JDBCUtilsByDruid {

    private static DataSource ds;

    //在静态代码块中完成ds初始化

    static {
        Properties properties = new Properties();
        try {
            properties.load(new FileInputStream("src\\druid.properties"));
            ds = DruidDataSourceFactory.createDataSource(properties);
        } catch (Exception e) {
            throw new RuntimeException(e);
        }
    }

    //编写getConnection方法
    public static Connection getConnection() throws SQLException {
        return ds.getConnection();
    }

    //关闭连接，在数据库连接池技术中不是真的断掉连接，而是把使用的Connection对象放回连接池
    public static void close(ResultSet resultSet, Statement statement,Connection connection){
        try {
            if (resultSet != null){
                resultSet.close();
            }

            if (statement != null){
                statement.close();
            }

            if (connection != null){
                connection.close();
            }
        } catch (SQLException e) {
            throw new RuntimeException(e);
        }
    }
}

```



![image-20230127221352986](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062348880.png)

```java
package com.momo.mhl.utils;

import java.sql.Connection;
import java.sql.SQLException;

/**
 * @author momo~
 * @version 1.0
 */
public class Test {
    public static void main(String[] args) throws SQLException {
        //测试Utility工具类
        System.out.println("请输入一个整数：");
        int i = Utility.readInt();
        System.out.println("i=" + i);

        //测试一下JDBCUtilsByDruid
        Connection connection = JDBCUtilsByDruid.getConnection();
        System.out.println(connection);
    }
}

```



![image-20230127221410993](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062348107.png)

```java
package com.momo.mhl.utils;

/**
 工具类的作用:
 处理各种情况的用户输入，并且能够按照程序员的需求，得到用户的控制台输入。
 */

import java.util.*;
/**

 */
public class Utility {
    //静态属性。。。
    private static Scanner scanner = new Scanner(System.in);


    /**
     * 功能：读取键盘输入的一个菜单选项，值：1——5的范围
     * @return 1——5
     */
    public static char readMenuSelection() {
        char c;
        for (; ; ) {
            String str = readKeyBoard(1, false);//包含一个字符的字符串
            c = str.charAt(0);//将字符串转换成字符char类型
            if (c != '1' && c != '2' &&
                    c != '3' && c != '4' && c != '5') {
                System.out.print("选择错误，请重新输入：");
            } else break;
        }
        return c;
    }

    /**
     * 功能：读取键盘输入的一个字符
     * @return 一个字符
     */
    public static char readChar() {
        String str = readKeyBoard(1, false);//就是一个字符
        return str.charAt(0);
    }
    /**
     * 功能：读取键盘输入的一个字符，如果直接按回车，则返回指定的默认值；否则返回输入的那个字符
     * @param defaultValue 指定的默认值
     * @return 默认值或输入的字符
     */

    public static char readChar(char defaultValue) {
        String str = readKeyBoard(1, true);//要么是空字符串，要么是一个字符
        return (str.length() == 0) ? defaultValue : str.charAt(0);
    }

    /**
     * 功能：读取键盘输入的整型，长度小于2位
     * @return 整数
     */
    public static int readInt() {
        int n;
        for (; ; ) {
            String str = readKeyBoard(10, false);//一个整数，长度<=10位
            try {
                n = Integer.parseInt(str);//将字符串转换成整数
                break;
            } catch (NumberFormatException e) {
                System.out.print("数字输入错误，请重新输入：");
            }
        }
        return n;
    }
    /**
     * 功能：读取键盘输入的 整数或默认值，如果直接回车，则返回默认值，否则返回输入的整数
     * @param defaultValue 指定的默认值
     * @return 整数或默认值
     */
    public static int readInt(int defaultValue) {
        int n;
        for (; ; ) {
            String str = readKeyBoard(10, true);
            if (str.equals("")) {
                return defaultValue;
            }

            //异常处理...
            try {
                n = Integer.parseInt(str);
                break;
            } catch (NumberFormatException e) {
                System.out.print("数字输入错误，请重新输入：");
            }
        }
        return n;
    }

    /**
     * 功能：读取键盘输入的指定长度的字符串
     * @param limit 限制的长度
     * @return 指定长度的字符串
     */

    public static String readString(int limit) {
        return readKeyBoard(limit, false);
    }

    /**
     * 功能：读取键盘输入的指定长度的字符串或默认值，如果直接回车，返回默认值，否则返回字符串
     * @param limit 限制的长度
     * @param defaultValue 指定的默认值
     * @return 指定长度的字符串
     */

    public static String readString(int limit, String defaultValue) {
        String str = readKeyBoard(limit, true);
        return str.equals("")? defaultValue : str;
    }


    /**
     * 功能：读取键盘输入的确认选项，Y或N
     * 将小的功能，封装到一个方法中.
     * @return Y或N
     */
    public static char readConfirmSelection() {
        System.out.println("请输入你的选择(Y/N): 请小心选择");
        char c;
        for (; ; ) {//无限循环
            //在这里，将接受到字符，转成了大写字母
            //y => Y n=>N
            String str = readKeyBoard(1, false).toUpperCase();
            c = str.charAt(0);
            if (c == 'Y' || c == 'N') {
                break;
            } else {
                System.out.print("选择错误，请重新输入：");
            }
        }
        return c;
    }

    /**
     * 功能： 读取一个字符串
     * @param limit 读取的长度
     * @param blankReturn 如果为true ,表示 可以读空字符串。
     * 					  如果为false表示 不能读空字符串。
     *
     *	如果输入为空，或者输入大于limit的长度，就会提示重新输入。
     * @return
     */
    private static String readKeyBoard(int limit, boolean blankReturn) {

        //定义了字符串
        String line = "";

        //scanner.hasNextLine() 判断有没有下一行
        while (scanner.hasNextLine()) {
            line = scanner.nextLine();//读取这一行

            //如果line.length=0, 即用户没有输入任何内容，直接回车
            if (line.length() == 0) {
                if (blankReturn) return line;//如果blankReturn=true,可以返回空串
                else continue; //如果blankReturn=false,不接受空串，必须输入内容
            }

            //如果用户输入的内容大于了 limit，就提示重写输入
            //如果用户如的内容 >0 <= limit ,我就接受
            if (line.length() < 1 || line.length() > limit) {
                System.out.print("输入长度（不能大于" + limit + "）错误，请重新输入：");
                continue;
            }
            break;
        }

        return line;
    }
}


```



![image-20230127221430600](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062348031.png)

```java
package com.momo.mhl.view;

import com.momo.mhl.domain.*;
import com.momo.mhl.service.BillService;
import com.momo.mhl.service.DiningTableService;
import com.momo.mhl.service.EmployeeService;
import com.momo.mhl.service.MenuService;
import com.momo.mhl.utils.Utility;

import java.util.List;

/**
 * @author momo~
 * @version 1.0
 * 主界面
 */
public class MHLView {

    //控制菜单退出
    private boolean loop = true;

    //接收用户一级菜单输入
    private String key = "";

    //定义EmployeeService属性
    private EmployeeService employeeService = new EmployeeService();

    //接收用户二级菜单输入
    private String twoKey = "";

    //调用DiningTable的属性
    private DiningTableService diningTableService = new DiningTableService();

    //定义MenuService属性
    private MenuService menuService = new MenuService();

    //定义BillService属性
    private BillService billService = new BillService();

    public static void main(String[] args) {
        new MHLView().mainMenu();
    }

    //显示主菜单
    public void mainMenu(){
        while (loop){
            System.out.println("==============满汉楼==============");
            System.out.println("\t\t 1 登录满汉楼");
            System.out.println("\t\t 2 退出满汉楼");
            System.out.print("请输入您的选择：");
            key = Utility.readString(1);
            switch (key){
                case "1":
                    System.out.println("请输入员工号：");
                    String empId = Utility.readString(10);
                    System.out.println("请输入密 码：");
                    String pwd = Utility.readString(50);
                    Employee employee = employeeService.getEmployeeByIdAndPwd(empId, pwd);
                    if (employee != null){
                        System.out.println("已经成功登录满汉楼");
                        while (loop){
                            System.out.println("============满汉楼二级菜单============");
                            System.out.println("\t\t 1 显示餐桌状态");
                            System.out.println("\t\t 2 预定餐桌");
                            System.out.println("\t\t 3 显示所有菜品");
                            System.out.println("\t\t 4 点餐服务");
                            System.out.println("\t\t 5 查看账单");
                            System.out.println("\t\t 6 结账");
                            System.out.println("\t\t 9 退出满汉楼");
                            System.out.print("请输入您的选择：");
                            twoKey = Utility.readString(1);
                            switch (twoKey){
                                case "1":
                                    listDiningTable();
                                    break;
                                case "2":
                                    dinZuo();
                                    break;
                                case "3":
                                    listMenu();
                                    break;
                                case "4":
                                    orderMenu();
                                    break;
                                case "5":
                                    listBill();
                                    break;
                                case "6":
                                    payBill();
                                    break;
                                case "9":
                                    loop = false;
                                    break;
                                default:
                                    System.out.println("输入有误，请重新输入");
                            }
                        }
                    } else {
                        System.out.println("密码错误，登录失败");
                    }
                    break;
                case "2":
                    loop = false;
                    break;
                default:
                    System.out.println("输入有误，请重新输入");
            }
        }
        System.out.println("已退出满汉楼系统");
    }

    //显示订单界面
    public void listDiningTable(){
        System.out.println("\n餐桌编号\t\t餐桌状态");
        for (DiningTable diningTable : diningTableService.list()) {
            System.out.println(diningTable);
        }
        System.out.println("============餐桌显示至此毕============");
    }

    //完成订座
    public void dinZuo(){
            System.out.println("=============预定餐桌=============");
            System.out.println("请选择要预定餐桌编号（-1退出）");
            int num = Utility.readInt();
            if (num == -1){
                System.out.println("=============取消预定=============");
                return;
            }
            DiningTable diningTableById = diningTableService.getDiningTableById(num);
            if (diningTableById != null){
                if (!("空".equals(diningTableById.getState()))){
                    System.out.println("餐桌已经有人");
                    return;
                }
                if (Utility.readConfirmSelection() == 'Y'){
                    System.out.println("预定人名字：");
                    String dinName = Utility.readString(10);
                    System.out.println("预定人电话：");
                    String dinTel = Utility.readString(50);

                    if (diningTableService.orderDiningTable(num, dinName, dinTel)){
                        System.out.println("=============预定成功=============");
                    } else {
                        System.out.println("=============预定失败=============");
                    }
                } else {
                    System.out.println("=============取消预定=============");
                }
            } else {
                System.out.println("餐桌不存在");
            }
    }

    //显示所有菜品
    public void listMenu(){
        System.out.println("\n菜品编号\t\t菜品名\t\t类别\t\t价格");
        for (Menu menu : menuService.list()) {
            System.out.println(menu);
        }
        System.out.println("=============菜单显示完毕=============");
    }

    //完成点餐
    public void orderMenu(){
        System.out.println("===============点餐服务===============");
        System.out.println("请输入点餐的桌号（-1退出）：");
        int orderDiningTableId = Utility.readInt();
        if (orderDiningTableId == -1){
            System.out.println("===============取消点餐===============");
            return;
        }

        //验证餐桌号是否存在
        DiningTable diningTableById = diningTableService.getDiningTableById(orderDiningTableId);
        if (diningTableById == null){
            System.out.println("=============餐桌号不存在=============");
            return;
        }

        System.out.println("请输入点餐的菜品号（-1退出）：");
        int orderMenuId = Utility.readInt();
        if (orderMenuId == -1){
            System.out.println("===============取消点餐===============");
            return;
        }

        //验证菜品编号是否存在
        Menu menuById = menuService.getMenuById(orderMenuId);
        if (menuById == null){
            System.out.println("============菜品编号不存在=============");
            return;
        }

        System.out.println("请输入点餐的菜品量（-1退出）：");
        int orderNums = Utility.readInt();
        if (orderNums == -1){
            System.out.println("===============取消点餐===============");
            return;
        }



        //点餐
        if (billService.orderMenu(orderMenuId,orderNums,orderDiningTableId)){
            System.out.println("============点餐成功=============");
        }else {
            System.out.println("============点餐失败=============");
        }
    }

    //显示账单信息
    public void listBill(){
//
//        List<Bill> bills = billService.list();
//
//        System.out.println("\n编号\t\t菜品号\t\t菜品量\t\t金额\t\t桌号\t\t日期\t\t\t\t\t\t\t状态");
//        for (Bill bill : bills) {
//            System.out.println(bill);
//        }
//        System.out.println("============显示完毕=============");

        System.out.println("\n编号\t\t菜品号\t\t菜品量\t\t金额\t\t桌号\t\t日期\t\t\t\t状态\t\t菜品名\t\t价格");

        for (MultiTableBean multiTableBean : billService.list2()) {
            System.out.println(multiTableBean);
        }
        System.out.println("============显示完毕=============");
    }

    //完成结账
    public void payBill(){
        System.out.println("============结账服务=============");
        System.out.println("请选择要结账的餐桌编号（-1退出）:");
        int diningTableId = Utility.readInt();
        if (diningTableId == -1){
            System.out.println("============取消结账=============");
            return;
        }
        //验证餐桌是否存在
        DiningTable diningTableById = diningTableService.getDiningTableById(diningTableId);
        if (diningTableById == null){
            System.out.println("==========结账餐桌不存在===========");
            return;
        }

        //验证餐桌是否有需要结账的账单
        if (!billService.hasPayBillByDiningTableId(diningTableId)){
            System.out.println("==========餐桌未有未结账账单===========");
            return;
        }
        System.out.println("结账方式（现金、支付宝、微信）回车表示退出：");
        String payMode = Utility.readString(20, "");//如果回车，则返回""
        if ("".equals(payMode)){
            System.out.println("============取消结账=============");
            return;
        }

        char key = Utility.readConfirmSelection();
        if (key == 'Y'){
            if (billService.payBill(diningTableId,payMode)){
                System.out.println("============完成结账=============");
            } else {
                System.out.println("============结账失败=============");
            }
        } else {
            System.out.println("============取消结账=============");
        }
    }

}

```



## 22.正则表达式

**Regular Expression**

![image-20230128113957403](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062348839.png)



```java
package com.momo.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

/**
 * @author momo~
 * @version 1.0
 * 体验正则表达式
 */
public class Regexp01 {
    public static void main(String[] args) {
        //假定，编写了爬虫，从百度页面得到了如下文本
        String content = "Java语言是易学的。　　" +
                "Java语言的语法与C语言和C++语言很接近，使得大多数程序员很容易学习和使用Java。" +
                "另一方面，Java丢弃了C++中很少使用的、很难理解的、令人迷惑的那些特性，如操作符重载、多继承、自动的强制类型转换。" +
                "特别地，Java语言不使用指针，而是引用。并提供了自动的废料收集，使得程序员不必为内存管理而担忧。　　" +
                "Java语言是强制面向对象的。10086　　" +
                "Java语言提供类、接口和继承等原语，为了简单起见，只支持类之间的单继承，但支持接口之间的多继承，并支持类与接口之间的实现机制(关键字为implements)。" +
                "Java语言全面支持动态绑定，而C++语言只对虚函数使用动态绑定。总之，Java语言是一个纯的面向对象程序设计语言。　　" +
                "Java语言是分布式的。　　" +
                "Java语言支持Internet应用的开发，在基本的Java应用编程接口中有一个网络应用编程接口(java net)，它提供了用于网络应用编程的类库，包括URL、URLConnection、Socket、ServerSocket等。" +
                "Java的RMI(远程方法激活)机制也是开发分布式应用的重要手段。　　" +
                "Java语言是健壮的。　　" +
                "Java的强类型机制、异常处理、垃圾的自动收集等是Java程序健壮性的重要保证。对指针的丢弃是Java的明智选择。" +
                "Java的安全检查机制使得Java更具健壮性。　　" +
                "Java语言是安全的。　　" +
                "Java通常被用在网络环境中，为此，Java提供了一个安全机制以防恶意代码的攻击。" +
                "除了Java语言具有的许多安全特性以外，Java对通过网络下载的类具有一个安全防范机制(类ClassLoader)，如分配不同的名字空间以防替代本地的同名类、字节代码检查，并提供安全管理机制(类SecurityManager)让Java应用设置安全哨兵。";
        //提取文章所有英文单词
        //1.传统方法，使用遍历方式，代码量大，效率低下
        //2.使用正则表达式

        //1.创建一个Pattern对象，模式对象，理解为一个正则表达式对象
//        Pattern pattern = Pattern.compile("[a-zA-Z]+");
//        //2.创建匹配器对象
//        Matcher matcher = pattern.matcher(content);
//        //3.开始循环匹配
//        while (matcher.find()){
//            System.out.println("找到：" + matcher.group(0));
//        }

        //提取文章所有数字
//        Pattern pattern02 = Pattern.compile("[0-9]+");
//        //2.创建匹配器对象
//        Matcher matcher02 = pattern02.matcher(content);
//        //3.开始循环匹配
//        while (matcher02.find()){
//            System.out.println("找到：" + matcher02.group(0));
//        }

        //提取文章所有英文单词和数字
//        Pattern pattern = Pattern.compile("([a-zA-Z]+)|([0-9]+)");
//        //2.创建匹配器对象
//        Matcher matcher = pattern.matcher(content);
//        //3.开始循环匹配
//        while (matcher.find()){
//            System.out.println("找到：" + matcher.group(0));
//        }

        //提取标题
        //<a target="_blank" href="https://news.sina.com.cn/c/2023-01-28/doc-imycteas0336628.shtml">民航局：春节假期民航运送旅客900万人次</a>

        String content2 = "</div>\n" +
                "\n" +
                "<div id=\"ad_entry_b2\">\n" +
                "    <ul class=\"list_14\" data-sudaclick=\"blk_news_1\">\n" +
                "\t\t\t    <li><a target=\"_blank\" href=\"https://news.sina.com.cn/c/2023-01-28/doc-imycteas0336628.shtml\">民航局：春节假期民航运送旅客900万人次</a></li>\t    <li><a target=\"_blank\" href=\"https://news.sina.com.cn/c/2023-01-28/doc-imycteav3848300.shtml\">病毒有点传不动了？新冠感染率呈下降趋势 专家解读</a></li>\t    <li><a target=\"_blank\" href=\"https://news.sina.com.cn/w/2023-01-28/doc-imycsxus3559272.shtml\">美媒：美法院公布佩洛西丈夫遭袭事件相关音视频资料</a></li>\t    <li><a target=\"_blank\" href=\"https://k.sina.cn/article_6189120710_m170e67cc6033015c3b.html?from=mil\">现场！舰艇编队南海作战支援演练</a></li>\t    <li><a target=\"_blank\" href=\"https://news.sina.com.cn/s/2023-01-28/doc-imycrwie3647339.shtml\">各地频现“不夜城” 专家分析：或将很快过气</a></li>\t\t</ul>\n" +
                "\t\t<!-- 虚线开始 -->\n" +
                "\t\t<div class=\"line_01\"></div>\n" +
                "\t\t<!-- 虚线结束 -->\n" +
                "\t\t<ul class=\"list_14\" data-sudaclick=\"blk_news_2\">\t    <li><a target=\"_blank\" href=\"https://news.sina.com.cn/w/2023-01-28/doc-imycsxus3495852.shtml\">美国前副总统彭斯：不知道机密文件在自己家中</a></li>\t    <li><a target=\"_blank\" href=\"https://k.sina.cn/article_5347795977_m13ec0e409033011e49.html?from=mood\">春节假期结束踏归途：打包好牵挂又开始想家</a></li>\t    <li><a target=\"_blank\" href=\"https://news.sina.com.cn/c/2023-01-28/doc-imycspey0362382.shtml\">日本炒作中国“经济胁迫”图什么？</a></li>\t    <li><a target=\"_blank\" href=\"https://news.sina.com.cn/w/2023-01-28/doc-imycteaq3502095.shtml\">要完坦克又想要战机？德国防长表态</a></li>\t    <li><a target=\"_blank\" href=\"https://k.sina.cn/article_5347795977_m13ec0e409020011e4n.html?from=society\">男子烧香点烛迎财神 困意上头打个盹把家给烧了</a></li>\t\t</ul>\n" +
                "\t\t<!-- 虚线开始 -->\n" +
                "\t\t<div class=\"line_01\"></div>\n" +
                "\t\t<!-- 虚线结束 -->\n" +
                "\t\t<ul class=\"list_14\" data-sudaclick=\"blk_news_3\">\t    <li><a target=\"_blank\" href=\"https://k.sina.com.cn/article_5347795977_m13ec0e409033011e4c.html?from=news&subch=onews\">春运返程中的全能武警：保驾护航清雪开路</a></li>\t    <li><a target=\"_blank\" href=\"https://news.sina.com.cn/c/2023-01-28/doc-imycsxuu0372464.shtml\">三亚海鲜餐饮协会:建议各类珍稀海产品加价率50%以内</a></li>\t    <li><a target=\"_blank\" href=\"https://video.sina.com.cn/p/finance/2023-01-28/detail-imycsxuu0355144.d.html\">马斯克见白宫官员讨论电动车生产，没聊管理推特事宜</a></li>\t    <li><a target=\"_blank\" href=\"https://news.sina.com.cn/c/2023-01-28/doc-imycsxuu0290060.shtml\">山西省吕梁市柳林县康家沟村发生山体滑坡致4人被困</a></li>\t    <li><a target=\"_blank\" href=\"https://news.sina.com.cn/c/2023-01-28/doc-imycteaq3484098.shtml\">记者亲历江南小镇：疫情淡去，人气回来</a></li>\n" +
                "\t</ul>\n" +
                "\t<!-- 虚线开始 -->\n" +
                "\t<div class=\"line_01\"></div>\n" +
                "\t<!-- 虚线结束 -->\n" +
                "\t<ul class=\"list_14\" data-sudaclick=\"blk_news_4\">\n" +
                "\t    <li><a target=\"_blank\" href=\"https://finance.sina.com.cn/jjxw/2023-01-28/doc-imycstnu3566580.shtml\">假期结束 全国铁路公路民航水路昨日迎返程客流高峰</a></li>\n" +
                "<li><a target=\"_blank\" href=\"https://finance.sina.com.cn/jjxw/2023-01-28/doc-imycsxuu0267252.shtml\">2023年春节档票房67.34亿元 电影市场迎来“开门红”</a></li>\n" +
                "\t\t\t<li data-client=\"throw\">\n" +
                "\t\t<ins class=\"sinaads\" data-ad-pdps=\"PDPS000000067814\" data-ad-width=\"360\" data-ad-height=\"26\" data-ad-type=\"embed\"></ins>\n" +
                "   <script>(sinaads = window.sinaads || []).push({});</script>\n" +
                "\t</li>\n" +
                "\t</ul>\n" +
                "</div>\n" +
                "<!-- 重点新闻1号位 结束 -->\n" +
                "<!-- 新闻中心要闻区 end --><!--online-edit-push[[{\"link\":\"https://news.sina.com.cn/c/xl/2023-01-28/doc-imycquvu0612173.shtml  \",\"pushList\":[{\"type\":1,\"value\":\"22515\",\"needPush\":0},{\"type\":1,\"value\":\"23428\",\"needPush\":0},{\"type\":2,\"value\":\"1\",\"needPush\":0},{\"type\":2,\"value\":\"2\",\"needPush\":0},{\"type\":2,\"value\":\"3\",\"needPush\":0},{\"type\":2,\"value\":\"4\",\"needPush\":0},{\"type\":2,\"value\":\"8\",\"needPush\":0}]},{\"link\":\"https://news.sina.com.cn/c/xl/2023-01-28/doc-imycrrzk0544761.shtml  \",\"pushList\":[{\"type\":1,\"value\":\"22515\",\"needPush\":0},{\"type\":1,\"value\":\"23428\",\"needPush\":0},{\"type\":2,\"value\":\"1\",\"needPush\":0},{\"type\":2,\"value\":\"2\",\"needPush\":1},{\"type\":2,\"value\":\"3\",\"needPush\":0},{\"type\":2,\"value\":\"4\",\"needPush\":0},{\"type\":2,\"value\":\"8\",\"needPush\":0}]},{\"link\":\"https://news.sina.com.cn/c/xl/2023-01-28/doc-imycsxux3961061.shtml\",\"pushList\":[{\"type\":1,\"value\":\"22515\",\"needPush\":0},{\"type\":1,\"value\":\"23428\",\"needPush\":0},{\"type\":2,\"value\":\"1\",\"needPush\":0},{\"type\":2,\"value\":\"2\",\"needPush\":1},{\"type\":2,\"value\":\"3\",\"needPush\":0},{\"type\":2,\"value\":\"4\",\"needPush\":0},{\"type\":2,\"value\":\"8\",\"needPush\":0}]},{\"link\":\" https://news.sina.com.cn/o/2023-01-28/doc-imycsxus3523644.shtml\",\"pushList\":[{\"type\":1,\"value\":\"22515\",\"needPush\":0},{\"type\":1,\"value\":\"23428\",\"needPush\":0},{\"type\":2,\"value\":\"1\",\"needPush\":0},{\"type\":2,\"value\":\"2\",\"needPush\":0},{\"type\":2,\"value\":\"3\",\"needPush\":0},{\"type\":2,\"value\":\"4\",\"needPush\":0},{\"type\":2,\"value\":\"8\",\"needPush\":0}]},{\"link\":\"https://k.sina.com.cn/article_1686546714_6486a91a02001tq7w.html?from=news&subch=onews\",\"pushList\":[{\"type\":1,\"value\":\"22515\",\"needPush\":0},{\"type\":1,\"value\":\"23428\",\"needPush\":0},{\"type\":2,\"value\":\"1\",\"needPush\":0},{\"type\":2,\"value\":\"2\",\"needPush\":0},{\"type\":2,\"value\":\"3\",\"needPush\":0},{\"type\":2,\"value\":\"4\",\"needPush\":0},{\"type\":2,\"value\":\"8\",\"needPush\":0}]},{\"link\":\"https://k.sina.com.cn/article_1893892941_70e2834d02001ckv8.html?from=society\",\"pushList\":[{\"type\":1,\"value\":\"22515\",\"needPush\":0},{\"type\":1,\"value\":\"23428\",\"needPush\":0},{\"type\":2,\"value\":\"1\",\"needPush\":0},{\"type\":2,\"value\":\"2\",\"needPush\":0},{\"type\":2,\"value\":\"3\",\"needPush\":0},{\"type\":2,\"value\":\"4\",\"needPush\":0},{\"type\":2,\"value\":\"8\",\"needPush\":0}]},{\"link\":\"https://news.sina.com.cn/c/2023-01-28/doc-imycteav3840530.shtml\",\"pushList\":[{\"type\":1,\"value\":\"22515\",\"needPush\":0},{\"type\":1,\"value\":\"23428\",\"needPush\":1},{\"type\":2,\"value\":\"1\",\"needPush\":0},{\"type\":2,\"value\":\"2\",\"needPush\":0},{\"type\":2,\"value\":\"3\",\"needPush\":0},{\"type\":2,\"value\":\"4\",\"needPush\":0},{\"type\":2,\"value\":\"8\",\"needPush\":0}]},{\"link\":\"https://news.sina.com.cn/c/2023-01-27/doc-imycrmtn0566629.shtml\",\"pushList\":[{\"type\":1,\"value\":\"22515\",\"needPush\":0},{\"type\":1,\"value\":\"23428\",\"needPush\":0},{\"type\":2,\"value\":\"1\",\"needPush\":0},{\"type\":2,\"value\":\"2\",\"needPush\":0},{\"type\":2,\"value\":\"3\",\"needPush\":0},{\"type\":2,\"value\":\"4\",\"needPush\":0},{\"type\":2,\"value\":\"8\",\"needPush\":0}]}]]online-edit-push-->\t<!-- 抓站_要闻 end -->\n" +
                "\t\n" +
                "\t\n" +
                "</div>";

        Pattern pattern = Pattern.compile("<a target=\"_blank\" href=\"(\\S*)\">(\\S*)</a>");
        //2.创建匹配器对象
        Matcher matcher = pattern.matcher(content2);
        //3.开始循环匹配
        while (matcher.find()) {
            System.out.println("找到：" + matcher.group(1));
        }
    }

}

```



![image-20230128135650425](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062348782.png)



![image-20230128140030895](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062348763.png)



![image-20230128140354828](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062348870.png)



#### **正则表达式底层实现**

![image-20230128140809759](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062348871.png)



![image-20230128140828522](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062348892.png)



```java
package com.momo.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

/**
 * @author momo~
 * @version 1.0
 * 分析java的正则表达式底层实现(重要)
 */
public class RegTheory {
    public static void main(String[] args) {

        String content = "1123煞风景啊圣诞节大5566十九大" +
                "8654你都按哈佛觉得垃圾";

        //匹配所有四个数字的字符串
        //1. \\d :表示一个任意数字
        String regStr = "(\\d\\d)(\\d\\d)";
        //2.创建模式对象【即正则表达式对象】
        Pattern pattern = Pattern.compile(regStr);
        //3.创建匹配器
        //按照正则表达式的规则去匹配
        Matcher matcher = pattern.matcher(content);
        //4.开始匹配
        /**
         * matcher.find() 完成的任务
         * 什么是分组： (\\d\\d)(\\d\\d),()第一组，()第二组
         *
         */
        while (matcher.find()){
            //1.如果正则表达式有(),表示分组
            //2.取出匹配的字符串规则如下
            //3.group(0)表示匹配到的子字符串
            //4.group(1)表示匹配到的子字符串的第一组
            //5.group(2)表示匹配到的子字符串的第二组，依此类推
            //6.但是不能数组下标越界
            System.out.println("找到：" + matcher.group(0));
            System.out.println("第一组()匹配的值=" + matcher.group(1));
            System.out.println("第二组()匹配的值=" + matcher.group(2));
            /**
             * 找到：1123
             * 第一组()匹配的值=11
             * 第二组()匹配的值=23
             * 找到：5566
             * 第一组()匹配的值=55
             * 第二组()匹配的值=66
             * 找到：8654
             * 第一组()匹配的值=86
             * 第二组()匹配的值=54
             */

        }

    }
}

```



#### **正则表达式语法**

![image-20230128145809688](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062348808.png)



##### **正则表达式转义符**

![image-20230128150709133](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302070000814.png)



![image-20230128150912974](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062348563.png)

```java
package com.momo.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

/**
 * @author momo~
 * @version 1.0
 * 演示转义字符的使用
 */
public class RegExp02 {
    public static void main(String[] args) {
        String content = "abc$(123(oop)";

        String regStr = "\\(";

        Pattern compile = Pattern.compile(regStr);
        Matcher matcher = compile.matcher(content);

        while (matcher.find()){
            System.out.println("找到：" + matcher.group(0));
        }
    }
}

```



##### **字符匹配符**

![image-20230128151049375](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349013.png)



![image-20230128151906853](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349946.png)



![image-20230128151939178](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349690.png)



```JAVA
package com.momo.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

/**
 * @author momo~
 * @version 1.0
 */
public class RegExp03 {
    public static void main(String[] args) {
        String content = "a11c8abcABC";

//        String regStr = "[a-z]";
//        String regStr = "[A-Z]";
//        String regStr = "abc";//默认区分大小写
        String regStr = "(?i)abc";//设置不区分大小写
        //(?i)abc 表示abc都不区分大小写
        //a(?i)bc 表示bc不区分大小写，其辐射范围为后面
        //a((?i)b)c 表示只有b不区分大小写
        //Pattern.CASE_INSENSITIVE设置为不区分大小写
        //Pattern pattern = Pattern.compile(regStr,Pattern.CASE_INSENSITIVE);

        //[0-9]:匹配0-9之间的任意一个字符
        //[a-z]:匹配a-z之间的任意一个字符
        //[A-Z]:匹配A-Z之间的任意一个字符

        //[^a-z]:匹配不是a-z中的任意一个字符
        //[^A-Z]:匹配不是A-Z中的任意一个字符
        //[^0-9]:匹配不是0-9中的任意一个字符

        //[abcd]:匹配在abcd中的任意一个字符
        //[^abcd]表示可以匹配不是abcd中的任意一个字符

        // \\d == [0-9],匹配0-9的任意一个数字
        // \\D == [^0-9],匹配不是0-9的任意一个数字
        // \\w == [a-zA-Z0-9]
        // \\W == [^a-zA-Z0-9]
        // \\s 匹配任意空白字符
        // \\S 匹配任意非空白字符
        // . 匹配除\n之外所有字符 本身需要使用\\.

        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(content);
        while (matcher.find()){
            System.out.println("找到：" + matcher.group(0));
        }
    }
}

```



![image-20230128154605389](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349221.png)



##### 选择匹配符

![image-20230128170959460](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349279.png)



```java
package com.momo.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

/**
 * @author momo~
 * @version 1.0
 * 选择匹配符 |
 */
public class RegExp04 {
    public static void main(String[] args) {
        String content = "hutao胡等哈说的话";
        String regStr = "hu|胡";

        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(content);

        while (matcher.find()){
            System.out.println("找到：" + matcher.group(0));
        }
    }
}

```



##### 限定符



![image-20230128171052142](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349746.png)



![image-20230128171625767](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349829.png)



![image-20230128173445418](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349089.png)

![image-20230128173413379](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302070000092.png)

![image-20230128173512045](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349879.png)



```java
package com.momo.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

/**
 * @author momo~
 * @version 1.0
 * 演示限定符的使用
 */
public class RegExp05 {
    public static void main(String[] args) {
        String content = "1111111aaa";
//        String regStr = "a{3}";// 等于 aaa
//        String regStr = "1{4}"; //等于 1111
//        String regStr = "\\d{2}"; //等于 两位任意数字字符

        //细节：java匹配默认贪婪匹配,尽可能匹配多的
//        String regStr = "1{4,5}";//匹配1111 或者 11111

//        String regStr = "\\d{2,5}";//匹配2位数或者3位数或者4位数或者5位数
        /**
         * 找到：11111
         * 找到：11
         */

        // + 一个或者多个  \\d+
//        String regStr = "1+";

        // * 零个或者多个  \\d*

        // ？零个或者一个  \\d?
        String regStr = "\\d?";

        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(content);

        while (matcher.find()){
            System.out.println("找到：" + matcher.group(0));
        }
    }
}

```



##### 定位符

![image-20230128174206115](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349826.png)



```java
package com.momo.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

/**
 * @author momo~
 * @version 1.0
 */
public class RegExp06 {
    public static void main(String[] args) {
        String content = "123-abc abc";

        //以至少1个数字开头，后接任意个小写字母的字符串
//        String regStr = "^[0-9]+[a-z]*";

        //以至少1个数字开头，以至少一个小写字母结束
        //String regStr = "^[0-9]+\\-[a-z]$";

        //表示匹配边界的abc[这里的边界是：被匹配字符串最后，也可以是空格的子字符串的后面]
        String regStr = "abc\\b";

        // \\B则跟\\b取反，表示不匹配边界的abc
        //String regStr = "abc\\B";

        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(content);

        while (matcher.find()){
            System.out.println("找到：" + matcher.group(0));
        }
    }
}

```



##### 分组

###### 捕获分组

![image-20230128195800387](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349392.png)



```java
package com.momo.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

/**
 * @author momo~
 * @version 1.0
 */
public class RegExp07 {
    public static void main(String[] args) {
        String content = "糊里糊涂7786 8823abc";

//        String regStr = "(\\d\\d)(\\d\\d)";
        String regStr = "(?<mo>\\d\\d)(?<g1>\\d\\d)";

        Pattern pattern = Pattern.compile(regStr);

        Matcher matcher = pattern.matcher(content);

        while (matcher.find()){
            System.out.println("找到：" + matcher.group(0));
            System.out.println("找到：" + matcher.group(1));
            System.out.println("找到：" + matcher.group("mo"));
            System.out.println("找到：" + matcher.group(2));
            System.out.println("找到：" + matcher.group("g1"));
        }
    }
}
```





###### 非捕获分组

![image-20230128201433379](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349820.png)



![image-20230128201831185](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349904.png)



```java
package com.momo.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

/**
 * @author momo~
 * @version 1.0
 * 演示非捕获分组
 */
public class RegExp08 {
    public static void main(String[] args) {
        String content = "今天是星期一 星期二 星期三";

        //String regStr = "星期一|星期二|星期三";
        //等价于非捕获分组
        //String regStr = "星期(?:一|二|三)";
        //String regStr = "星期(?=一|二)";
        String regStr = "星期(?!一)";

        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(content);

        while (matcher.find()){
            System.out.println("找到：" + matcher.group(0));
        }
    }
}

```



**非贪婪匹配**

![image-20230128205027655](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349557.png)



```java
package com.momo.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

/**
 * @author momo~
 * @version 1.0
 * 演示非贪婪匹配
 */
public class Regexp09 {
    public static void main(String[] args) {
        String content = "abc111223";

        //默认贪婪匹配
        //String regStr = "\\d+";
        /**找到：111223
         */

        //改为非贪婪匹配
        String regStr = "\\d+?";
        /**找到：1
         找到：1
         找到：1
         找到：2
         找到：2
         找到：3
         */

        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(content);

        while (matcher.find()){
            System.out.println("找到：" + matcher.group(0));
        }
    }
}

```



#### **正则表达式实例**

![image-20230128212820980](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349699.png)



```java
package com.momo.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

/**
 * @author momo~
 * @version 1.0
 * 验证正则表达式实例
 */
public class RegExp10 {
    public static void main(String[] args) {
        //验证汉字
//        String content = "今天是星期五";
//
//        String regStr = "^[\u0391-\uffe5]+$";
//
//        Pattern pattern = Pattern.compile(regStr);
//        Matcher matcher = pattern.matcher(content);
//
//        if (matcher.find()){
//            System.out.println("满足条件");
//        } else {
//            System.out.println("不满足条件");
//        }

        //验证邮政编码
        //要求1-9开头的6个数。

//        String content = "123456";
//
//        String regStr = "^[1-9]\\d{5}$";
//
//        Pattern pattern = Pattern.compile(regStr);
//        Matcher matcher = pattern.matcher(content);
//
//        if (matcher.find()){
//            System.out.println("满足条件");
//        } else {
//            System.out.println("不满足条件");
//        }

        //验证QQ号码
        //1-9开头的一个（5位数到10位数）
//        String content = "123456";
//
//        String regStr = "^[1-9]\\d{4,9}$";
//
//        Pattern pattern = Pattern.compile(regStr);
//        Matcher matcher = pattern.matcher(content);
//
//        if (matcher.find()){
//            System.out.println("满足条件");
//        } else {
//            System.out.println("不满足条件");
//        }

        //验证手机号码
        //必须以13、14、15、18开头的11位数
        String content = "15145465456";

//        String regStr = "^(13|14|15)\\d{9}$";
        String regStr = "^1[3|4|5]\\d{9}$";

        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(content);

        if (matcher.find()){
            System.out.println("满足条件");
        } else {
            System.out.println("不满足条件");
        }

        //验证URL

    }
}

```





**验证复杂url**

```java
package com.momo.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

/**
 * @author momo~
 * @version 1.0
 * 演示正则表达式的使用
 */
public class RegExp11 {
    public static void main(String[] args) {

        String url = "https://www.bilibili.com/video/BV1fh411y7R8?p=894&spm_id_from=pageDriver&vd_source=0b20513356bc4e81a7d83b2a9a6c4019";

        //[]中符号.%#等表示其本身
        String regStr = "^((http|https)://)?([\\w-]+\\.)+[\\w-]+(\\/[\\w-?=&/%.#]*)?$";

        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(url);

        if (matcher.find()){
            System.out.println("满足格式");
        } else {
            System.out.println("不满足格式");
        }
    }
}

```



#### **Pattern类**

![image-20230204204250124](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349428.png)



![image-20230204205354040](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349508.png)



```java
package com.momo.regexp;

import java.util.regex.Pattern;

/**
 * @author momo~
 * @version 1.0
 * 演示matches方法，用于整体匹配，验证输入字符串是否匹配时使用
 */
public class PatternMethod {
    public static void main(String[] args) {
        String content = "hello momo";
//        String regStr = "momo";//false
//        String regStr = "hello momo";//true
        String regStr = "hello.*";//true

        boolean matches = Pattern.matches(regStr, content);
        System.out.println("验证是否整体匹配：" + matches);
    }
}

```



#### **Matcher类**

![image-20230204211244810](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349914.png)



```java
package com.momo.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

/**
 * @author momo~
 * @version 1.0
 * Matcher类的常用方法
 */
public class MatcherMethod {
    public static void main(String[] args) {
        String content = "hello momo kkl hello oop hello";
        String regStr = "hello";

        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(content);
        while (matcher.find()){
            System.out.println("======");
            System.out.println(matcher.start());
            System.out.println(matcher.end());
            System.out.println("找到:" + content.substring(matcher.start(), matcher.end()));
        }

        //整体匹配
        System.out.println("整体匹配" + matcher.matches());

        //替换,如果content中有momo则替换成huhu
        regStr = "momo";
        pattern = Pattern.compile(regStr);
        matcher = pattern.matcher(content);

        //返回的字符串才是替换后的字符串
        String newContent = matcher.replaceAll("huhu");
        System.out.println("newContent" + newContent);
        System.out.println("content" + content);

    }
}

```





#### 反向引用

![image-20230204211541964](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349117.png)



![image-20230204211554390](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349293.png)



![image-20230204214447654](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349459.png)



```java
package com.momo.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

/**
 * @author momo~
 * @version 1.0
 */
public class RegExp12 {
    public static void main(String[] args) {
        String content = "12312-333999111hello1221 1112 kl335 momo85 99";

        //找到两个连续相同的数字
        //String regStr01 = "(\\d)\\1";

        //找到三个连续相同的数字
        //String regStr = "(\\d)\\1{2}";

        //找到匹配个位与千位相同,十位与百位相同,例如1551 3663
        //String regStr = "(\\d)(\\d)\\2\\1";

        /**
         * 请在字符串中检索商品编号,形式如下:12312-333999111
         * 要求满足前面是一个五位数,然后一个-号,然后是一个九位数,要求连续三位数相同
         */

        String regStr = "\\d{5}-(\\d)\\1{2}(\\d)\\2{2}(\\d)\\3{2}";



        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(content);

        while (matcher.find()){
            System.out.println("找到:" + matcher.group(0));
        }
    }
}
```



#### 结巴去重

![image-20230204214542402](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062349888.png)



```java
package com.momo.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

/**
 * @author momo~
 * @version 1.0
 */
public class RegExp13 {
    public static void main(String[] args) {
        String content = "我...我要...学学学......编程java";

        //结巴去重
        //去掉.
        String regStr = "\\.";//. 与 \\. 记得转义
        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(content);

        content = matcher.replaceAll("");

        //System.out.println(content);
        //去掉重复元素

        //使用(.)\\1+
        //使用 反向引用$1 来替换匹配到的内容

//        pattern = Pattern.compile("(.)\\1+");
//        matcher = pattern.matcher(content);
//
//        while (matcher.find()){
//            System.out.println(matcher.group(0));
//            //我我
//            //学学学
//        }
//
//        //使用反向引用$1来替换匹配到的内容
//        content = matcher.replaceAll("$1");//核心去重
//
//        System.out.println(content);//我要学编程java

        //使用一条语句去重
        content = Pattern.compile("(.)\\1+").matcher(content).replaceAll("$1");
        System.out.println(content);

    }
}

```



#### 替换分割



![image-20230204221411478](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062350463.png)



```java
public class RegExp14 {
    public static void main(String[] args) {
        String content = "Java programming language具有大部分编程语言所共有的一些特征，" +
                "被特意设计用于互联网的分布式环境。Java具有类似于C++语言的\"形式和感觉\"，" +
                "但它要比C++语言更易于使用，而且在编程时彻底采用了一种\"以对象为导向\"的方式。" +
                "使用Java编写的应用程序JDK1.3，既可以在一台单独的电脑上运行，也可以被分布在一个网络的服务器端和客户端运行。" +
                "另外，Java还可以被用来编写容量很小的JDK1.4应用程序模块或者applet，做为网页的一部分使用。" +
                "applet可使网页使用者和网页之间进行交互式操作。";

        //使用正则表达式方式将jdk1.3与jdk1.4替换成jdk
        content = content.replaceAll("JDK1\\.3|JDK1\\.4","JDK");

        System.out.println(content);
    }
}
```



![image-20230204222058318](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062350111.png)



```java
//要求手机号必须以139 136开头
        content = "13554546975";

        if (content.matches("(139|136)\\d{8}")){
            System.out.println("成功");
        } else {
            System.out.println("失败");
        }
```



![image-20230204222544356](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062350363.png)



```java
package com.momo.regexp;

/**
 * @author momo~
 * @version 1.0
 */
public class RegExp14 {
    public static void main(String[] args) {
        String content = "Java programming language具有大部分编程语言所共有的一些特征，" +
                "被特意设计用于互联网的分布式环境。Java具有类似于C++语言的\"形式和感觉\"，" +
                "但它要比C++语言更易于使用，而且在编程时彻底采用了一种\"以对象为导向\"的方式。" +
                "使用Java编写的应用程序JDK1.3，既可以在一台单独的电脑上运行，也可以被分布在一个网络的服务器端和客户端运行。" +
                "另外，Java还可以被用来编写容量很小的JDK1.4应用程序模块或者applet，做为网页的一部分使用。" +
                "applet可使网页使用者和网页之间进行交互式操作。";

        //使用正则表达式方式将jdk1.3与jdk1.4替换成jdk
        content = content.replaceAll("JDK1\\.3|JDK1\\.4","JDK");

        System.out.println(content);

        //要求手机号必须以139 136开头
        content = "13554546975";

        if (content.matches("(139|136)\\d{8}")){
            System.out.println("成功");
        } else {
            System.out.println("失败");
        }

        //要求按照# 或者 - 或者 ~ 或者数字分割
        content = "hello#abc-hack123smith~北京";
        for (String split : content.split("#|-|~|\\d+")) {
            System.out.println(split);
        }

    }
}



```



#### 相关实例

![image-20230205204416258](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062350946.png)

```java
package com.momo.regexp;

/**
 * @author momo~
 * @version 1.0
 */
public class Homework01 {
    public static void main(String[] args) {
        //规定电子邮件规则
        //只能有一个@
        //@前面是用户名，可以是a-z A-Z 0-9 _ - 字符
        //@后面是域名，并且域名只能是英文字母，比如sousu.com
        //写出对应的正则表达式，验证输入字符串是否满足规则
        String content = "momo@hutao.com";
        String regStr = "^[\\w-_]+@([a-zA-Z]+\\.)+[a-zA-Z]+$";

        if (content.matches(regStr)){
            System.out.println("匹配成功");
        } else {
            System.out.println("匹配失败");
        }
    }
}

```



![image-20230205215618231](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062350399.png)



```java
package com.momo.regexp;

/**
 * @author momo~
 * @version 1.0
 */
public class Homework02 {
    public static void main(String[] args) {
        //要求验证是不是整数或者小数
        //提示：这个题目要考虑正数和负数
        //比如：123 -123 34.89 -87.9 -0.01等

        String content = "-789.789";
        String regStr = "^[-+]?([1-9]\\d*|0)(\\.\\d+)?$";

        if (content.matches(regStr)){
            System.out.println("匹配成功");
        } else {
            System.out.println("匹配失败");
        }

    }
}

```





![image-20230205221735586](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062350684.png)



```java
package com.momo.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

/**
 * @author momo~
 * @version 1.0
 */
public class Homework03 {
    public static void main(String[] args) {
        String content = "http://www.soushu.com:8080//abc/index.html";

        String regStr = "^([a-zA-Z]+)://([a-zA-Z.]+):(\\d+)[\\w-/]*/([\\w.]+)$";

        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(content);

        //整体匹配，如果匹配成功，可以通过group(x),获取对应分组
        if (matcher.matches()){
            System.out.println("整体匹配=" + matcher.group(0));
            System.out.println("协议：" + matcher.group(1));
            System.out.println("域名：" + matcher.group(2));
            System.out.println("端口：" + matcher.group(3));
            System.out.println("文件：" + matcher.group(4));
        } else {
            System.out.println("没有匹配成功");
        }
    }
}

```



#### Java正则表达式大全

![image-20230206111912050](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062350903.png)



![image-20230206112408389](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062350491.png)



![image-20230206112434249](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062350844.png)





## 23.马踏棋盘

![image-20230206150218878](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062350457.png)



![image-20230206150539667](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062350728.png)



![image-20230206151337913](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062350893.png)



![image-20230206164535941](https://cdn.jsdelivr.net/gh/Momo-web/Java-note/img/202302062350139.png)



```java
package com.momo;

import java.awt.*;
import java.util.ArrayList;
import java.util.Comparator;

/**
 * @author momo~
 * @version 1.0
 */
public class HorseChessBoard {
    private static int X = 6;//表示col
    private static int Y = 6;//表示row
    private static int[][] chessBoard = new int[X][Y];//棋盘
    private static boolean[] visited = new boolean[X * Y];//记录某个位置是否走过
    private static boolean finished = false;//记录马儿是否遍历完棋盘

    public static void main(String[] args) {

        int row = 5;
        int col = 5;

        //测试一把
        long start = System.currentTimeMillis();

        traversalChessBoard(chessBoard,row - 1,col - 1,1);

        long end = System.currentTimeMillis();

        System.out.println("遍历耗时：" + (end - start));


        //输出当前这个棋盘的情况
        for (int[] ints : chessBoard) {
            for (int step : ints) {
                System.out.print(step + "\t");
            }
            System.out.println();
        }
    }

    //写一个方法，对ps的各个位可以走的下一个位置的次数进行排序，把可能走的下一个位置从小到大排序
    public static void sort(ArrayList<Point> ps){
        ps.sort(new Comparator<Point>() {
            @Override
            public int compare(Point o1, Point o2) {
                return next(o1).size() - next(o2).size();
            }
        });
    }

    //编写最核心的算法，遍历棋盘，如果遍历成功，就把finished 设置为true
    //并且，将马儿走的每一步step，记录到chessBoard
    public static void traversalChessBoard(int[][] chessBoard,int row,int col,int step){
        //先把step记录到chessBoard
        chessBoard[row][col] = step;
        //把这个位置设置为已经访问
        visited[row * X + col] = true;
        //获取当前这个位置可以走的下一个位置有哪些
        ArrayList<Point> ps = next(new Point(col, row));
        sort(ps);//算法核心
        //遍历
        while (!ps.isEmpty()){
            //取出一个位置
            Point p = ps.remove(0);
            //判断该位置是否走过
            if (!visited[p.y * X + p.x]){
                //递归遍历
                traversalChessBoard(chessBoard,p.y,p.x,step + 1);
            }
        }

        if (step < X * Y && !finished){
            //重置
            chessBoard[row][col] = 0;
            visited[row * X + col] = false;
        } else {
            finished = true;
        }
    }

    public static ArrayList<Point> next(Point curPoint){
        //创建一个ArrayList
        ArrayList<Point> ps = new ArrayList<>();

        //创建一个Point对象(点/位置)，准备放入到ps
        Point p1 = new Point();

        //判断是否可以走5位置
        if ((p1.x = curPoint.x - 2) >= 0 && (p1.y = curPoint.y - 1) >= 0){
            ps.add(new Point(p1));
        }

        //判断是否可以走6位置
        if ((p1.x = curPoint.x - 1) >= 0 && (p1.y = curPoint.y - 2) >= 0){
            ps.add(new Point(p1));
        }
        //判断是否可以走7位置
        if ((p1.x = curPoint.x + 1) < X && (p1.y = curPoint.y - 2) >= 0){
            ps.add(new Point(p1));
        }
        //判断是否可以走0位置
        if ((p1.x = curPoint.x + 2 ) < X && (p1.y = curPoint.y - 1) >= 0){
            ps.add(new Point(p1));
        }
        //判断是否可以走1位置
        if ((p1.x = curPoint.x + 2) < X && (p1.y = curPoint.y + 1) < Y){
            ps.add(new Point(p1));
        }
        //判断是否可以走2位置
        if ((p1.x = curPoint.x + 1) < X && (p1.y = curPoint.y + 2) < Y){
            ps.add(new Point(p1));
        }
        //判断是否可以走3位置
        if ((p1.x = curPoint.x - 1) >= 0 && (p1.y = curPoint.y + 2) < Y){
            ps.add(new Point(p1));
        }
        //判断是否可以走4位置
        if ((p1.x = curPoint.x - 2) >= 0 && (p1.y = curPoint.y + 1) < Y){
            ps.add(new Point(p1));
        }

        return ps;
    }
}

```





