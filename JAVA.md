# 阶段一 JAVASE基础

## 第一章 Java基础语法

### 环境搭建

#### JAVA简介

Java三大技术平台

Java SE：Java语言的标准版，用于桌面应用的开发，==是其他两个版本的基础==，学习JavaSE是为了JavaEE开发==打基础==

Java ME：Java语言的小型版，用于嵌入式电子设备或者小型移动设备

Java EE：Java语言的企业版，用于企业应用开发，包括web方向开发



#### JDK的下载和安装

JDK：Java开发工具包

通过官方网站获取JDK ( https: //www.oracle.com/ )
直接下载地址: https: //www.oracle.com/java/technologies/javase-downloads.html

==针对不同的操作系统，下载对应的JDK==

建议安装路径中不要包含中文和空格



#### JDK的安装目录

1. bin：存放JDK的各种工具命令javac命令和java命令就在该目录下
2. conf：存放JDK的相关配置文件
3. include：存放一些平台特定的头文件
4. jmods：存放JDK的各种模块
5. legal：存放JDK各模块的授权文件
6. lib：JDK工具的一些补充JAR包



#### 第一个程序

Java程序开发流程：编写程序(源文件.java)，编译程序(字节码文件.class)，运行程序

编写文档保存名字为HelloWorld.java

```java

pubilc class HelloWorld{
	pubilc static void main(String[] args){
		System.out.printfln("helloworld");
	}
}
```

在保存文件的文件夹中，在地址栏中输入cmd回车，打开dos命令框

输入

```
javac HelloWorld.java
```

编译源代码，得到字节码文件HelloWorld.class文件

输入

```
java HelloWorld
```

运行程序得到

```
helloworld
```

==常见问题==

1. 单词大小写写错
2. 符号要用英语符号
3. java11后可以直接使用java命令运行java源代码，不需要使用javac编译程序



#### 常用DOS命令

1. 打开命令指示符窗口

   ①直接在地址栏输入cmd，回车

   ②通过运行窗口打开：win+R → 输入cmd → 确定

2. dir → 展示当前文件夹内文件

3. D: → 切换到D盘

4. cd 文件夹 → 进入文件夹

5. cd .. → 返回上一级

6. cd \ → 回到根目录

7. cls → 清屏

8. exit → 关闭



#### path环境变量

path环境变量的作用

它提供了windows命令行中指令的可执行文件（比如：.exe文件）路径，让我们在命令行中输入命令时，能够找到对应的可执行文件执行（让命令在命令行中使用有效）

配置JAVA_HOME变量，变量值为JDK安装目录

编辑Path环境变量，新建%JAVA_HOME%\bin，上移到最上面



#### IDEA概述和安装

IDEA：全称intellij IDEA，用于Java语言开发的集成环境

集成环境：把代码编写，编译，运行调试多种功能综合到一起的开发工具

IDEA下载和安装

下载：https://www.jetbrains.com/idea

安装：建议修改安装路径



#### IDEA中的HelloWorld

1. 新建项目，创建一个空项目javase_code
2. 点击文件→项目结构，新建模块，选择Java模块，编辑模块名字idea_test，完成确定
3. 将idea_test展开，在src新建软件包com.itheima
4. 在com.itheima中新建类HelloWorld
5. 在代码区域编写以下代码（快捷输入main，sout）

```java
package com.itheima;

public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}

```

运行得到结果

```
Hello World!
```





IDEA中代码结构

+ 项目（project）
+ 模块（module）
+ 包（package）
+ 类（class）



#### IDEA中基本配置&注释

基本设置详情自行在文件→设置中调整

在HelloWorld.java中添加注释

```java
package com.itheima;

/*
    Java程序中最基本的组成单位是类

    类的定义格式是：
        public class 类名{

        }
 */

public class HelloWorld {
    /*
        这是main方法
        main方法是程序的入口方法，代码的执行是从main方法开始的
     */
    public static void main(String[] args) {
        //这是输出语句，能够将“”里面的内容输出到控制台，并且“”里面的内容是可以修改的
        System.out.println("Hello World!");
    }
}

```



#### IDEA中常用的快捷键

+ main方法：mian或者psvm，回车
+ 输出语句：sout，回车
+ CTRL+D：复制数据到下一行
+ CTRL+X：剪切数据，可以用来删除所在行
+ CTRL+alt+L：格式化代码，建议自己写的时候就注意格式
+ CTRL+/：对所选中的代码添加单行注释，如果想取消注释，再来一次
+ CTRL+shift+/：对选中的代码添加多行注释，如果想取消注释，再来一次



#### IDEA中模块操作

+ 新建模块

  文件 → 项目结构 → 模块 → 新建模块 → idea_demo

+ 删除模块

  选中模块 → 右键 → 移除模块（在列表中移除，源文件任存在）

+ 导入模块

  文件 → 项目结构 → 模块 → 导入模块 → 选择需要导入的模块 → 完成 → 选择JDK



### 数据类型&标识符

#### 字面量

字面量概述

+ 直接写出来的人可以理解的数据，在Java中叫做字面量
+ 是用来表示源代码中一个固定值的
+ 举例：“Helloworld”，666，13.14

字面量分类

字符串字面量，整数字面量，小数字面量，字符字面量，布尔字面量

1. 新建模块itheima-literals
2. 新建软件包com.itheima
3. 新建类LiteralDemo
4. 在LiteralDemo.java写下以下代码

```java
package com.itheima;

/*
    字符串字面量： 用双引号括起来的内容“HelloWorld”，“黑马程序员”
    整数字面量：  不带小数的数字，666，-88
    小数字面量：  带小数的数字，13.14，-5.21
    字符字面量：  用单引号括起来的内容，'A'，'0'，'我'
    布尔字面量：  布尔值，表示真假，true，false
*/

public class LiteralDemo {
    public static void main(String[] args) {
        //字符串字面量
        System.out.println("HelloWorld");
        System.out.println("黑马程序员");

        //整数字面量
        System.out.println(666);
        System.out.println(-88);

        //小数字面量
        System.out.println(13.14);
        System.out.println(-5.21);

        //字符字面量
        System.out.println('A');
        System.out.println('0');
        System.out.println('我');

        //布尔字面量
        System.out.println(true);
        System.out.println(false);
    }
}

```

运行程序，得到结果

```
HelloWorld
黑马程序员
666
-88
13.14
-5.21
A
0
我
true
false
```



#### 数据类型

数据类型概述

+ Java语言是强类型语言，对于每一种数据都给出了明确的类型
+ 不同的数据类型分配了不同的内存空间
+ 不同的内存空间，所存储的数据大小是不一样的

| 数据类型 | 关键字         | 占用内存 |
| -------- | -------------- | -------- |
| 整数     | byte           | 1        |
|          | short          | 2        |
|          | int（默认）    | 4        |
|          | long           | 8        |
| 浮点数   | float          | 4        |
|          | double（默认） | 8        |
| 字符     | char           | 2        |
| 布尔     | boolean        | 1        |

#### 变量

变量就是内存中的存储空间，空间中存储的数据是可以发生改变

变量的定义格式

+ 格式：数据类型 变量名 = 变量值
+ 范例：int price = 998；
+ 根据变量名进行使用，可以输出，也可以修改值

1. 新建模块itheima-variable
2. 新建软件包com.itheima
3. 新建Java类VariableDemo01
4. 在VariableDemo中写下以下代码

```java
package com.itheima;

/*
    格式：数据类型 变量名 = 变量值
 */

public class VariableDemo01 {
    public static void main(String[] args) {
        //定义一个int类型的变量，用来表示价格
        int price = 998;

        //输出变量
        System.out.println(price);

        //修改变量
        price = 888;

        //再次输出变量
        System.out.println(price);
    }
}

```

运行程序，得到结果

```
998
888
```

==注意事项==

+ 在同一范围内，变量名不能重复
+ 没有初始化的变量不能输出
+ 变量的数据不能超过范围
+ 定义long类型变量，数据后面加L
+ 定义float数据变量，数据后面加F



#### 关键字

关键字概述

关键字：就是Java语言赋予了特定含义的单词

关键字特点：

+ 关键字的字母全部小写
+ 常用的代码编辑器，针对关键字有特殊的颜色标记，非常直观



#### 标识符

标识符规则

组成规则：由数字、字母、下划线和美元符组成

注意事项

+ 不能以数字开头
+ 不能是关键字
+ 区分大小写

命名约定

小驼峰命名法：方法、变量

+ 约定1：标识符一个单词的时候，首字母小写
+ 范例1：name
+ 约定2：标识符是多个单词的时候，第一个单词首字母小写，其他单词首字母大写
+ 范例2：firstName

大驼峰命名法：类

+ 约定1：标识符一个单词的时候，首字母大写
+ 范例1：Hello
+ 约定2：标识符多个单词的时候，每个单词首字母大写
+ 范例2：HelloWorld



### 运算符

#### 算术运算符

运算符和表达式概述

运算符：对字面量或者变量进行操作的符号

表达式：用运算符把字面量或者变量连接起来符合Java语法的式子就可以称为表达式，不同运算符连接的表达式体现的是不同类型的表达式

加（+）、减（-）、乘（*）、除（\）、取余（%）

1. 新建模块itheima-operator
2. 新建软件包com.itheima
3. 新建Java类OperatorTest
4. 在OperatorTest.java中写下以下代码

```java
package com.itheima;

/*
    需求：定义一个三位数拆解成个位、十位、百位，输出在控制台
 */

public class OperatorTest {
    public static void main(String[] args) {
        //定义一个三位数
        int number = 123;

        //获取个十百位数据
        int ge = number % 10;
        int shi = number / 10 % 10;
        int bai = number / 100 % 10;

        //输出结果
        System.out.println("个位是" + ge);
        System.out.println("十位是" + shi);
        System.out.println("百位是" + bai);
    }
}

```

运行程序，得到以下结果

```
个位是3
十位是2
百位是1
```



#### +操作的三种情况

+ 数字相加

  ```java
  int a = 10;
  double b = 13.14;
  System.out.println(a + b);
  //运行结果：23.14
  ```

  ==隐式转换==：把表示数据范围小的的数值或者变量赋值给另一个表示数据范围大的数据

  ==强制转换==：格式：数据类型 变量名 = （数据类型）（数值或变量）

+ 字符相加

  + 'A'   65   A-Z是连续的
  + 'a'   97   a-z是连续的
  + '0'   48   0-9是连续的

+ 字符串相加

  ```Java
  System.out.println("it" + "heima");
  System.out.println("itheima" + 666);
  System.out.println(666 + "itheima");
  //运行结果：itheima
  //运行结果：itheima666
  //运行结果：666itheima
  System.out.println("itheima" + 6+66);
  System.out.println(1 + 99 + "itheima");
  //运行结果：itheima666
  //运行结果：100itheima
  ```



#### 赋值运算符 =

将=右边的值赋值给左边

a += b  → a = a + b



#### 顺序语句

+ 分支语句if-else
+ 循环结构for
+ 顺序语句



#### Debug的使用

Debug概述

Debug：是供程序员使用的调试工具，它可以用于查看程序的执行流程，也可以用于追踪程序执行过程来调试程序

Debug操作流程

Debug，又被称作断点调试，断点其实是一个标记，告诉我们从哪里开始查看

1. 添加断点
2. Debug执行程序
3. 执行步过，执行下一步语句
4. 在调试器查看变量，在控制台查看结果和进行操作
5. 点一下断点就可以取消断点



### 逻辑控制语句

#### if语句格式

格式：

if（结果为Boolean类型的表达式）{

​	语句体；

}

范例：

```java
boolean isGreen = true;
if(isGreen){
    System.out.println("绿灯行");
}
//运行结果：绿灯行
boolean isGreen = true;
isGreen = false;
if(isGreen){
    System.out.println("绿灯行");
}
//运行结果：
```

if（结果为Boolean类型的表达式）{

​	语句体；

} ekse{

​	语句体；

}

范例：

```java
boolean isGreen = true;
isGreen = false;
if(isGreen){
    System.out.println("绿灯行");
} else {
    System.out.println("不是绿灯，不允许通行")
}
//运行结果：不是绿灯，不允许通行
```

```java
int light = 2;
if(light == 1){
	System.out.println("红灯停");
}else if(light == 2){
	System.out.println("绿灯行");
}else if(light == 3){
	System.out.println("黄灯等一等");
}
//运行结果：绿灯行
```



#### 关系运算符

| ==   | 等于     |
| ---- | -------- |
| !=   | 不等于   |
| >    | 大于     |
| >=   | 大于等于 |
| <    | 小于     |
| <=   | 小于等于 |



#### 逻辑运算符

| &&   | 与，并且 |
| ---- | -------- |
| \|\| | 或，或者 |
| !    | 非，相反 |



#### 三元运算符

格式：关系表达式 ? 表达式1 : 表达式2;

范例：a > b ? a : b

运算规则：

1. 首先计算关系表达式的值
2. 如果结果为true，表达式1为运算结果
3. 如果结果为false，表达式2为运算结果

```java
int a = 10;
int b = 20;
int max = a > b ? a : b;
System.out.println("较大的是：" + max);
//运行结果：较大的是20
```



#### switch语句

格式：

switch(表达式){

​	case 值1：

​		语句体1；

​		break；

​	case 值2：

​		语句体2；

​		break；

…

​	default：

​		语句体n+1；

​		break；

}

```java
int light = 1;
switch (light){
    case 1:
        System.out.println("红灯停");
        break;
    case 2:
        System.out.println("绿灯行")
        break;
    case 3:
    	System.out,printfln("黄灯等一等")
        break;
    default:
    	System.out.println("信号灯异常")
        break;
}
//运行结果：红灯停
```



### 循环

#### for循环

格式：

for(初始化语句;条件判断语句;条件控制语句){

​	循环体语句；

}

格式说明

+ 初始化语句：这里可以是一条或者多条语句，这些语句用来完成初始化操作
+ 条件判断语句：这里使用一个结果值为Boolean类型的表达式，这个表达式能决定是否执行循环体语句
+ 循环体语句：这里可以是任意语句，这些语句可能被多次执行
+ 条件控制语句：这里通常是使用一条语句来改变变量的值，从而达到控制循环是否继续向下执行的效果

```java
for(int i = 1; i <= 5; i ++){
    System.out.println("HelloWorld");
}
//运行结果：HelloWorld
//运行结果：HelloWorld
//运行结果：HelloWorld
//运行结果：HelloWorld
//运行结果：HelloWorld
```



#### while循环

格式：

while(条件判断语句){

​	循环体语句；

​	条件控制语句；

}

```java
int i = 1;
while(i <= 5){
    System.out.println("HelloWorld");
    i ++;
}
//运行结果：1
//运行结果：2
//运行结果：3
//运行结果：4
//运行结果：5
```



#### do-while循环

格式：

do{

​	循环体语句；

​	条件控制语句；

}while(条件控制语句);

```java
int i = 1;
do{
    System.out.println("HelloWorld");
}while(i <= 3)
//运行结果：HelloWorld
//运行结果：HelloWorld
//运行结果：HelloWorld
```



#### 跳转控制语句

+ continue

  跳过某次循环体内容的执行，继续下一次循环

+ break

  中止循环



### 类&方法

#### 方法概述

什么是方法

+ 方法（method）：就是完成特定功能的代码块

  pubilc static void main(){} ：定义一个main方法



#### 方法的定义和调用

方法定义

+ 格式

  public static void 方法名(){

  ​	方法体

  }

+ 范例

  public static void isEveryNumber(){

  ​	方法体

  }

方法调用

```java
public static void mian(String[] args){
    printHW();
}
public static void printHW(){
    System.out.println("HelloWorld");
}
//运行结果：HelloWorld
```



#### Debug查看方法调用

1. 设置断点
2. Debug运行
3. 在调用方法的时候选择步入（step into）



### 形参&实参

#### 带参数方法的定义和调用

方法定义

+ 格式：pubic static void 方法名(参数){…}

+ 格式（单个参数）：public static void 方法名（数据类型 变量名）{…}
+ 格式（多个参数）：public static void 方法名（数据类型 变量名1，数据类型 变量名2，…）{…}

==注意==

+ 带参数方法定义时，参数中的数据类型与变量名都不能缺少，缺少任意一个程序将报错
+ 带参数方法定义时，多个参数之间使用逗号分开

方法调用

```java
public static void main(String[] args){
    isEvenNunber(10);
}
public static void isEvenNumber(int number){
    if(number % 2 == 0){
        System.out.println(true);
    } else {
        System.out.println(false);
    }
}
//运行结果：true
```



#### 带返回值方法的定义和调用

方法定义

+ 格式：

  public static 数据类型 方法名 （参数）{

  ​	return 数据；

  }

方法调用

```java
public static void main(String[] args){
    boolean flag = isEvenNunber(10);
    System.out.println(flag);
}
public static boolean isEvenNumber(int number){
    if(number % 2 == 0){
        return true;
    } else {
        return false;
    }
}
//运行结果：true
```



#### 方法的注意事项

+ 方法不能嵌套定义
+ void表示无返回值，可以省略return，也可以单独写return，后面不加数据



#### 方法通用格式

public static 返回值类型 方法名（参数）{

​	方法体；

​	return 数据；

}

+ public static：修饰符，目前先记住这个格式
+ 返回值类型：方法操作完后返回的数据类型
+ 方法名：调用方法时候使用的标识
+ 参数：由数据类型和变量名组成，多个参数之间用逗号隔开
+ 方法体：完成功能的代码块
+ return：方法操作完毕，返回数据



#### 方法重载

什么是方法重载

方法重载指同一个类中定义的多个方法之间的关系，满足下列条件的多个方法相互构成重载

+ 多个方法在一个类中
+ 多个方法具有相同的方法名
+ 多个方法的参数不相同，类型不同或者数量不同



## 第二章 面向对象基础

### 面向对象基础

面向对象介绍

+ 并不是一个技术，而是一种编程指导思想
+ 以什么形式组织代码；以什么思路解决问题

为什么要用面向对象编程

+ 因为生活中，我们解决问题时，就是采用这种指导思想去解决问题。所以，我们写程序去解决问题时，如果也能采用这种指导思想就会使编程变得非常简单，程序也便于人理解



#### 类和对象

什么是类

+ 类是对现实生活中一类具有共同属性和行为的事物的抽象
+ 我们可以将其理解为对象的设计图

什么是对象

+ 是能够看得到的摸得着的真实存在的实体
+ 小结：类是对象的抽象，对象是类的实体

对象的属性和行为

+ 属性：对象具有的各种特征，每个对象的每个属性都拥有特定的值
+ 行为：对象能够执行的操作



#### 类的定义

+ 类是什么：是对现实生活中一类具有共同属性和行为的事物的抽象，确定对象将会拥有的属性和行为

类的组成：属性和行为

+ 属性：在类中通过成员变量来体现（类中方法外的变量）
+ 行为：在类中通过成员方法来体现（和前面的方法相比去掉static关键字）

类的定义步骤

1. 定义类
2. 编写类的成员变量
3. 编写类的成员方法

```
pubilc class 类名{
	//成员变量
	变量1的数据类型 变量1;
	变量2的数据类型 变量2;
	…
	//成员方法
	方法1；
	方法2；
	…
}
```

例子：

```java
public class Phone{
    //成员变量
    String brand;
    int price;
    //成员方法
    public void call(){
        System.out.println("打电话");
    }
    public void sendMessage(){
        System.out.println("发短信");
    }
}
```



#### 对象的使用

创建对象

+ 格式：类名 对象名 = new 类名();
+ 范例：Phone p = new Phone();

使用对象

1. 使用成员变量
   + 格式：对象名.变量名
   + 范例：p.brand
2. 使用成员方法
   + 格式：对象名.方法名（参数）
   + 范例：p.call()

在一个软件包内创建Phone.java和PhoneDemo.java

Phone.java定义类

```java
package com.itheima;

public class Phone {
    String brand;
    int price;

    public void call(){
        System.out.println("打电话");
    }

    public void sendMessage(){
        System.out.println("发短信");
    }
}

```

PhoneDemo.java创建对象，使用对象

```java
package com.itheima;

public class PhoneDemo {
    public static void main(String[] args) {
        Phone p = new Phone();
        p.brand = "小米";
        p.price = 2999;

        System.out.println(p.brand);
        System.out.println(p.price);

        p.call();
        p.sendMessage();
    }
}
//运行结果：小米
//运行结果：2999
//运行结果：打电话
//运行结果：发短信
```



#### Java内存分配

+ Java程序在运行时，需要在内存中分配空间。为了提高运算效率，就对空间进行了不同区域的划分，因为每一片区域都有特定的处理数据方法和内存管理方法。

栈：所有局部变量都会在栈内存中创建

+ 局部变量：定义在方法中的变量或者方法声明上的变量
+ 方法执行都会加载到栈中
+ 局部变量特点：随着方法的调用而存在，随着方法的调用完毕而消失

堆：所有的对象及其对应的实例变量和数组都将存储在此处

+ 简单理解为：new出来的东西，都存储在堆内存
+ 每一个new出来的东西都有一个地址值，使用完毕，会在垃圾回收器空闲时被回收
+ 实例变量（成员变量）有初始值
  + 基本数据类型：整数：0，浮点数0.0，布尔：false，字符：空字符
  + 引用数据类型：null



#### 对象内存图

单个对象

```java
public class StudentTest01{
    public static void main(String[] args){
        Student s = new Student();
        System.out.println(s);
        
        System.out.println(s.name + "," + s.age);
        
        s.name = "张曼玉";
        s.age = 28;
        System.out.println(s.name + "," + s.age);
        
        s.study();
        s.doHomework();
    }
}
//运行结果：001
//运行结果：null,0
//运行结果：张曼玉,28
//运行结果：好好学习
//运行结果：多做练习
```

1. 先在栈内存缓存方法main，缓存Student s的地址
2. 在堆内存缓存对象new Student，和初始化它的成员变量
3. 输出Student s的地址
4. 改变堆内存中new Student的成员变量
5. 输出堆内存中new Student的成员变量
6. 在栈内存缓存s.study方法
7. 运行s.study方法
8. 释放栈内存中的s.study方法
9. 在栈内存缓存s.doHomework方法
10. 运行s.doHomework方法
11. 释放栈内存中的s.doHomework方法
12. 在栈内存释放main方法



多个对象

```java
public class StudentTest02{
    public static void main(String[] args){
        Student s1 = new Student();
        s1.name = "林青霞";
        s1.age = 30;
        System.out.println(s1.name + "," + s1.age);
        
        s1.study();
        s1.doHomework();
        
        Student s2 = new Student();
        s2.name = "张曼玉";
        s2.age = 28;
        System.out.println(s2.name + "," + s2.age);
        
        s2.study();
        s2.doHomework();
    }
}
//运行结果：林青霞，30
//运行结果：好好学习
//运行结果：多做练习
//运行结果：张曼玉，28
//运行结果：好好学习
//运行结果：多做练习
```

1. 在栈内存缓存main方法，缓存Student s1的地址
2. 在堆内存缓存对象new Student，和初始化它的成员变量
3. 改变堆内存中new Student的成员变量
4. 输出堆内存中new Student的成员变量
5. 在栈内存缓存s.study方法
6. 运行s.study方法
7. 释放栈内存中的s.study方法
8. 在栈内存缓存s.doHomework方法
9. 运行s.doHomework方法
10. 释放栈内存中的s.doHomework方法
11. 缓存Student s2的地址
12. 在堆内存缓存对象new Student，和初始化它的成员变量
13. 改变堆内存中new Student的成员变量
14. 输出堆内存中new Student的成员变量
15. 在栈内存缓存s.study方法
16. 运行s.study方法
17. 释放栈内存中的s.study方法
18. 在栈内存缓存s.doHomework方法
19. 运行s.doHomework方法
20. 释放栈内存中的s.doHomework方法
21. 在栈内存释放main方法



多个引用指向相同

```java
public class StudentTest03{
    Student s1 = new Student();
    s1.name = "林青霞";
    s1.age = 30;
    System.out.println(s1.name + "," + s1.age);
    
    Student s2 = s1;
    s2.name = "张曼玉";
    s2.age = 28;
    System.out.println(s1.name + "," + s1.age);
    System.out.println(s2.name + "," + s2.age);
}
```

1. 在栈内存缓存main方法，缓存Student s1的地址
2. 在堆内存缓存对象new Student，和初始化它的成员变量
3. 改变堆内存中new Student的成员变量
4. 输出堆内存中new Student的成员变量
5. 在栈内存缓存Student s2的地址，将s1的地址赋值给它
6. 改变堆内存中new Student的成员变量
7. 输出堆内存中new Student的成员变量
8. 输出堆内存中new Student的成员变量



### 关键字&构造方法

#### 成员变量和局部变量的区别

```java
public class Student{
    String name;
    
    public void study(){
        int i = 0;
        System.out.println("好好学习");
    }
    
    public void doHomework(){
        System.out.println("多做练习");
        int j = 0;
    }
    
    int age;
}
```

成员变量：name，age；局部变量：i，j

| 区别           | 成员变量                                   | 局部变量                                       |
| -------------- | ------------------------------------------ | ---------------------------------------------- |
| 类中位置不同   | 类中方法外                                 | 方法内或者方法声明上                           |
| 内存中位置不同 | 堆内存                                     | 栈内存                                         |
| 生命周期不同   | 随着对象的存在而存在，随着对象的消失而消失 | 随着方法的调用而存在，随着方法的调用完毕而消失 |
| 初始化值不同   | 有默认的初始化值                           | 没有默认的初始化值，必须先定义，赋值，才能使用 |



#### private关键字

+ 是一个权限修饰符
+ 可以修饰成员（成员变量和成员方法）
+ 作用是保护成员不被别的类使用，被private修饰的成员只能在本类中才能使用

针对private修饰的成员变量，如果需要被其他类使用，提供两个相应操作：

+ 提供“get变量名（）”方法，用于获取成员变量的值，方法用public修饰
+ 提供“set变量名（参数）”方法，用于设置成员变量的值，方法用public修饰



新建java类Student.java

```java
package com.itheima_01;

public class Student {
    //成员变量
    String name;
    private int age;

    public void setAge(int a){
        age = a;
    }

    public  void show(){
        System.out.println(name + "," + age);
    }
}

```

新建java类StudentDemo.java

```java
package com.itheima_01;

public class StudentDemo {
    public static void main(String[] args) {
        Student s = new Student();

        s.name = "林青霞";
        
        s.setAge(30);
        s.show();
    }
}
//运行结果：林青霞，30
```



#### this关键字

1. this限定的变量用于指代成员变量
   + 方法的形参如果与成员变量同名，不带this修饰的变量指的是形参，而不是成员变量
   + 方法的形参没有与成员变量同名，不带this修饰的变量指的是成员变量
2. 什么时候使用this呢？解决局部变量隐藏成员变量
3. this：方法被哪个对象调用，this就代表哪个对象



Student.java

```java
package com.itheima_02;

public class Student {
    private String name;

    public void setName(String name){
        this.name = name;
    }

    public String getName(){
        return name;
    }
}

```

StudentDemo.java

```java
package com.itheima_02;

public class StudentDemo {
    public static void main(String[] args) {
        Student s = new Student();

        s.setName("林青霞");
        System.out.println(s.getName());
    }
}
//运行结果：林青霞
```



#### 封装

1. 封装概念
   + 是面向对象三大特征之一（封装、继承、多态）
   + 是面向对象编程语言对客观世界的模拟，客观世界里成员变量都是隐藏在对象内部的，外部是无法直接操作的
2. 封装原则
   + 将类的某些信息隐藏在类内部，不允许外部程序直接访问，而是通过该类提供的方法来实现对隐藏信息的操作和访问
   + 成员变量private，提供对应的getXXXX()/setXXXX()方法
3. 封装好处
   + 通过方法来控制成员变量的操作，提高了代码安全性
   + 把代码用方法进行封装，提高了代码的复用性



#### 构造方法

构造方法概述

+ 构造方法是一种特殊的方法
+ 作用：创建对象
+ 功能：主要是完成对对象数据的初始化

Student.java

```java
package com.itheima_03;

public class Student {
    private String name;
    private int age;

    public Student(){
        System.out.println("无参构造函数");
    }

    public void show(){
        System.out.println(name + "," + age);
    }
}

```

StudentDemo.java

```java
package com.itheima_03;

public class StudentDemo {
    public static void main(String[] args) {
        Student s1 = new Student();
        s1.show();
    }
}
//运行结果：无参构造函数
//运行结果：null，0
```



#### 构造函数的注意事项

1. 构造方法的创建
   + 如果没有定义构造方法，系统将给出一个默认的无参构造方法
   + 如果定义了构造方法，系统将不再提供默认的构造方法
2. 构造方法的重载
   + 如果自定义了带参构造方法，还要使用无参构造方法，就必须再写一个无参构造方法
3. 推荐的使用方法
   + ==永远提供无参构造方法==



#### Javabean

+ 就是一个Java中的类，其中对象可以用于在程序中封装数据
+ 举例：学生类，手机类

标准的Javabean须满足如下要求：

+ 成员变量使用private修饰
+ 提供每一个成员变量对应的setXXX()/getXXX()
+ 提供一个无参构造方法



## 第三章 API基础

### Scanner&Random

#### API概述

+ API(Application Programing Interface)：应用程序编程接口
+ Java API：指的就是JDK中提供的各种功能的Java类。
  这些类将底层的实现封装了起来，我们不需要关心这些类如何实现，只需要学习这些类如何使用即可，我们可以通过帮助文档来学习这些类如何使用

帮助文档的使用流程

+ 打开帮助文档
+ 找到索引，输入要学习的类
+ 看类所在包：Java.lang包下的类在使用的时候不需要导包
+ 看类的描述：类是干什么的
+ 看类的构造方法：创建对象使用
+ 看类的成员方法：完成功能使用



#### 包和导包

包

+ 其实就是文件夹
+ 作用：对类进行分类管理

包的定义格式

+ 格式：package 包名；
+ 注意：包名一般是公司域名反写，并且多级包用 . 分开
+ 举例：www.itheima.com
+ 范例：package com.itheima;

1. 新建包com.itheima和com.itheima01
2. 在com.itheima中新建Java类Student和StudentDemo
3. 在com.itheima01中新建Java类StudentDemo

Student.java

```java
package com.itheima;

public class Student {

    public void study(){
        System.out.println("好好学习");
    }
}

```

StudentDemo.java（同包）

```java
package com.itheima;

public class StudentTest {
    public static void main(String[] args) {
        Student s = new Student();
        s.study();
    }
}
//运行结果：好好学习
```

StudentDemo.java（不同包）

```java
package com.itheima01;

public class StudentTest {
    public static void main(String[] args) {
        com.itheima.Student s = new com.itheima.Student();
        s.study();
    }
}
//运行结果：好好学习
```

导包

使用不同包下的类时，使用的时候要写类的全路径，写起来太麻烦了，为了简化带包的操作，Java就提供了导包的操作

导包的格式

+ import 包名；
+ import com.itheima.Student;

```java
package com.itheima02;

import com.itheima.Student;

public class StudentTest {
    public static void main(String[] args) {
        Student s = new Student();
        s.study();
    }
}
//运行结果：好好学习
```



#### Scanner基本使用

+ 一个简单的文本扫描程序，可以获取基本类型数据和字符串数据

构造方法

+ Scanner(InputStream source)：创建Scanner对象
  + System.in：对应的是InputStream类型，可以表示键盘输入
  + Scanner sc = new Scanner(System.in);

成员方法

+ int nextInt()：获取一个int类型的数据
  + int i = sc.nextInt();

```java
package com.itheima;

import java.util.Scanner;

public class ScannerDemo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("输入一个整数");
        int i = sc.nextInt();

        System.out.println("你输入的是" + i);
    }
}
//运行结果：输入一个整数
//3
//运行结果：你输入的是3
```



#### Random基本使用

创建随机数

```java
package com.itheima;

import java.util.Random;

public class RandomDemo {
    public static void main(String[] args) {
        Random r = new Random();

        int i = r.nextInt(10);
        System.out.println(i);
    }
}
//运行结果：输出0-9的随机数
```



### GUI

#### GUI概述

+ Graphical User Interface（图形用户接口）
+ 用图形的方式，来显示计算机操作的界面

java.awt包：

+ Abstract Window Toolkit（抽象窗口工具包），需要调用本地系统方法实现功能，属重量级控件

javax.swing包：

+ 在awt的基础上，建立的一套图形界面系统，提供了更多的组件，而且完全由java实现。增强了移植性，属轻量级控件
+ 组件：是具有图形表示的对象，该图形表示可以显示在屏幕上并且可以与用户交互

常用GUI组件

+ 基本组件
  + JButton
  + JLabel
  + JTextField
  + JTextArea
+ 容器组件
  + Panel
    + JPanel
  + Window
    + Frame
      + JFrame



#### JFrame_初识窗体

JFrame

+ 是一个顶层窗口

构造方法

+ JFrame()：构造一个最初不可见的新窗体

成员方法

+ void setVisible(boolean b)：显示或隐藏此窗体具体取决于参数b的值
+ void setSize(int width,int height)：调整组件的大小，使其宽度为width，高度为height，单位是像素

```java
package com.itheima;

import javax.swing.*;

public class JFrameDemo01 {
    public static void main(String[] args) {
        JFrame jf = new JFrame();

        //窗体大小
        jf.setSize(400,300);

        //窗体可见
        jf.setVisible(true);
    }
}
//运行结果：创建一个空白窗体
```



#### JFrame_常用设置

成员方法

+ void setTitle(String title)：设置窗体标题
+ void setLocationRelativeTo(Component c)：设置位置，值为null，则窗体位于屏幕中央
+ void setDefaultCloseOperation(int operation)：设置窗体关闭时默认操作
  + 整数3表示：窗体关闭时退出应用程序
+ void setAlwaysOnTop(boolearn alwaysOnTop)：设置此窗口是否应始终位于其他窗口之上

```java
package com.itheima;

import javax.swing.*;

public class JFrameDemo02 {
    public static void main(String[] args) {
        JFrame jf = new JFrame();

        //设置窗体标题
        jf.setTitle("Java学习实验窗口");
        //窗体大小
        jf.setSize(400,300);
        //窗口关闭退出程序
        jf.setDefaultCloseOperation(3);
        //设置窗体位于中央
        jf.setLocationRelativeTo(null);
        //窗体始终在最上面
        jf.setAlwaysOnTop(true);

        //窗体可见
        jf.setVisible(true);
    }
}

```



#### JButton_窗口中添加按钮

JButton：按钮的实现

构造方法

+ JButton(String text)：创建一个带文本的按钮

成员方法

+ void setSize(int width,int height)：设置大小
+ void setLocation(int x,int y)：设置位置（x坐标，y坐标）
+ void setBounds(int x,int y,int width,int height)：设置位置和大小

和窗体相关的操作

+ 取消窗体默认布局：窗体对象.setLayout(null);
+ 把按钮添加到窗体：窗体对象 .add(按钮对象);

```java
package com.itheima;

import javax.swing.*;

public class JFrameDemo03 {
    public static void main(String[] args) {
        JFrame jf = new JFrame();

        jf.setTitle("Java学习实验窗口");
        jf.setSize(400,300);
        jf.setDefaultCloseOperation(3);
        jf.setLocationRelativeTo(null);
        jf.setAlwaysOnTop(true);
        //取消窗体默认布局
        jf.setLayout(null);

        //添加按钮
        JButton btn = new JButton("我是按钮");
        //设置大小
        btn.setSize(100,20);
        //设置位置
        btn.setLocation(100,100);
        //上面两个可以用btn.setBounds(100,100,100,20);代替

        //添加按钮2
        JButton btn2 = new JButton("我是按钮2");
        btn2.setBounds(100,130,100,20);

        //将按钮添加到窗体上
        jf.add(btn);
        jf.add(btn2);

        //窗体可见
        jf.setVisible(true);
    }
}
//运行结果：上个窗口加了两个按钮
```



#### JLabel_显示文本和图像

短文本字符串或图像的显示区域

构造方法

+ JLabel(String text)：使用指定的文本创建JLabel实例
+ JLabel(Icon image)：使用指定的图像创建JLabel实例
  + ImageIcon(String filename)：从指定文件创建ImageIcon
  + 文件路径：绝对路径和相对路径
  + 绝对路径：完整的路径名，不需要任何其他信息就可以定位它所表示的文件
  + 相对路径：必须使用取自其他路径名的信息进行解释

成员方法

+ void setBounds(int x,int y,int width,int height)：设置位置和大小

```java
package com.itheima;

import javax.swing.*;

public class JLabelDemo {
    public static void main(String[] args) {
        JFrame jf = new JFrame();

        jf.setTitle("Java学习实验窗口");
        jf.setSize(400,300);
        jf.setDefaultCloseOperation(3);
        jf.setLocationRelativeTo(null);
        jf.setAlwaysOnTop(true);
        jf.setLayout(null);

        //创建JLabel文本实例
        JLabel jLabel = new JLabel("好好学习");
        jLabel.setBounds(0,0,100,20);

        //创建JLabel图像实例
        JLabel jLabel1 = new JLabel(new ImageIcon("itheima-api-gui\\image\\earth.png"));
        jLabel1.setBounds(50,50,200,200);

        jf.add(jLabel);
        jf.add(jLabel1);

        jf.setVisible(true);
    }
}
//运行结果：显示了好好学习和一张地球照片
```



#### GUI案例_用户登录

文本输入框：JTextField 输入框 = new JTextField();

密码输入框：JPasswordField 输入框 = new JPasswordField();

```java
package com.itheima;

import javax.swing.*;

public class UserLogin {
    public static void main(String[] args) {
        JFrame jf = new JFrame();

        jf.setTitle("用户登录");
        jf.setSize(400,300);
        jf.setDefaultCloseOperation(3);
        jf.setLocationRelativeTo(null);
        jf.setAlwaysOnTop(true);
        jf.setLayout(null);

        //显示用户名文本
        JLabel usernameLabel = new JLabel("用户名");
        usernameLabel.setBounds(50,50,50,20);
        jf.add(usernameLabel);

        //用户名输入框
        JTextField usernameField = new JTextField();
        usernameField.setBounds(150,50,180,20);
        jf.add(usernameField);

        //显示密码文本
        JLabel passwordLabel = new JLabel("密码");
        passwordLabel.setBounds(50,100,50,20);
        jf.add(passwordLabel);

        //密码输入框
        JPasswordField passwordField = new JPasswordField();
        passwordField.setBounds(150,100,180,20);
        jf.add(passwordField);

        //登录按钮
        JButton loginButton = new JButton("登录");
        loginButton.setBounds(50,200,280,20);
        jf.add(loginButton);

        jf.setVisible(true);
    }
}
//运行结果：用户登陆界面
```



#### GUI案例_聊天室

区域文本框：JTextArea 文本框 = new JTextArea();

```java
package com.itheima;

import javax.swing.*;

public class ChatRoom {
    public static void main(String[] args) {
        JFrame jf = new JFrame();

        jf.setTitle("聊天室");
        jf.setSize(400,300);
        jf.setDefaultCloseOperation(3);
        jf.setLocationRelativeTo(null);
        jf.setAlwaysOnTop(true);
        jf.setLayout(null);

        //显示聊天记录
        JTextArea messageArea = new JTextArea();
        messageArea.setBounds(10,10,360,200);
        jf.add(messageArea);

        //输入聊天文本框
        JTextField messageFiled = new JTextField();
        messageFiled.setBounds(10,230,180,20);
        jf.add(messageFiled);

        //发送按钮
        JButton sendButton = new JButton("发送");
        sendButton.setBounds(200,230,70,20);
        jf.add(sendButton);

        //清空按钮
        JButton clearButton = new JButton("清空内容");
        clearButton.setBounds(280,230,100,20);
        jf.add(clearButton);

        jf.setVisible(true);
    }
}
//显示一个聊天室界面
```



#### 事件监听机制_给按钮添加事件

事件监听机制

+ 事件源：事件发生的地方。可以是按钮，窗体，图片等
+ 事件：发生了什么事情。例如：鼠标点击了事件，键盘按下了事件等
+ 事件绑定：把事件绑定到事件源上，当发生了某个事件，则触发对应的处理逻辑
  + 事件源对象.addXXXXListener(事件);

```java
package com.itheima;

import javax.swing.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class ActionListenerDemo {
    public static void main(String[] args) {
        JFrame jf = new JFrame();

        jf.setTitle("事件监听事件");
        jf.setSize(400,300);
        jf.setDefaultCloseOperation(3);
        jf.setLocationRelativeTo(null);
        jf.setAlwaysOnTop(true);
        jf.setLayout(null);

        JButton jButton = new JButton("点我");
        jButton.setBounds(0,0,100,100);
        jf.add(jButton);

        jButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                System.out.println("Hello World!");
            }
        });

        jf.setVisible(true);
    }
}
//运行结果：点击按钮，输出HEllo World！
```



### String&时间格式

#### String_构造方法

String

+ String类表示字符串。Java程序中的所有字符串文字（例如"abc"）都实现为此类的实例

构造方法

+ String()：初始化新创建的String对象，使其表示空字符序列
+ String(String original)：初始化新创建的String对象，使其表示与参数相同的字符序列

```java
package com.itheima;

public class StringDemo01 {
    public static void main(String[] args) {
        //空的字符串对象
        String s1 = new String();
        System.out.println();

        String s2 = new String("hello");
        System.out.println(s2);
        System.out.println(s2.length());

        String s3 = "world";
        System.out.println(s3);
        System.out.println(s3.length());
    }
}
//运行结果：hello
//运行结果：5
//运行结果：world
//运行结果：5
```



#### String_成员方法

+ int length()：返回此字符串的长度
+ boolean equals(Object anObject)：将此字符串与指定对象进行比较
+ boolean equalslgnoreCase(String anotherString)：将此String与另一个String比较，忽略大小写
+ String trim()：返回一个字符串，其值为此字符串，删除了所有前导和尾随空格

```java
package com.itheima;

public class StringDemo02 {
    public static void main(String[] args) {
        String s1 = "itheima";
        String s2 = "itheima";
        String s3 = "Itheima";

        //将两个字符串进行比较
        System.out.println(s1.equals(s2));
        System.out.println(s1.equals(s3));

        //将两个字符串进行比较（忽略大小写）
        System.out.println(s1.equalsIgnoreCase(s2));
        System.out.println(s1.equalsIgnoreCase(s3));

        String s4 = " itheima ";
        //去除前导和尾随的空格
        System.out.println(s4);
        System.out.println(s4.trim());
    }
}
//运行结果：true
//运行结果：false
//运行结果：true
//运行结果：true
//运行结果： itheima 
//运行结果：itheima
```



#### GUI案例_用户登录实现

弹出提示框：JOptionPane.showMessageDialog(窗体,"内容");

```java
package com.itheima;

import javax.swing.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class UserLogin {
    public static void main(String[] args) {
        JFrame jf = new JFrame();

        jf.setTitle("用户登录");
        jf.setSize(400,300);
        jf.setDefaultCloseOperation(3);
        jf.setLocationRelativeTo(null);
        jf.setAlwaysOnTop(true);
        jf.setLayout(null);

        //显示用户名文本
        JLabel usernameLabel = new JLabel("用户名");
        usernameLabel.setBounds(50,50,50,20);
        jf.add(usernameLabel);

        //用户名输入框
        JTextField usernameField = new JTextField();
        usernameField.setBounds(150,50,180,20);
        jf.add(usernameField);

        //显示密码文本
        JLabel passwordLabel = new JLabel("密码");
        passwordLabel.setBounds(50,100,50,20);
        jf.add(passwordLabel);

        //密码输入框
        JPasswordField passwordField = new JPasswordField();
        passwordField.setBounds(150,100,180,20);
        jf.add(passwordField);

        //登录按钮
        JButton loginButton = new JButton("登录");
        loginButton.setBounds(50,200,280,20);
        jf.add(loginButton);


        //定义用户信息
        String name = "itheima";
        String pwd = "123456";

        loginButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                String username = usernameField.getText();
                String password = passwordField.getText();

                if(username.length()<6 || username.length()>12){
                    JOptionPane.showMessageDialog(jf,"用户名长度为6-12位，请重新输入");
                    usernameField.setText("");
                    return;
                }

                if(password.length()<6 || password.length()>12){
                    JOptionPane.showMessageDialog(jf,"密码长度为6-12位，请重新输入");
                    passwordField.setText("");
                    return;
                }

                if(username.equals(name) && password.equals(pwd)){
                    JOptionPane.showMessageDialog(jf,"登陆成功");
                }else{
                    JOptionPane.showMessageDialog(jf,"用户名或密码错误，请重新输入");
                }
            }
        });

        jf.setVisible(true);
    }
}

```



#### Integer_构造方法

+ Integer类在对象中包装基本类型int的值

构造方法

+ Integer(int value)：根据int值创建Integer对象（过时）
+ Integer(String s)：根据String值创建Integer对象（过时）

成员方法

+ static Integer valueOf(int i)：返回表示指定的int值的Integer实例
+ statuc Integer valueOf(String s)：返回一个保存指定值的Intteger对象String

```java
package com.itheima;

public class IntegerDemo01 {
    public static void main(String[] args) {
//        Integer i = new Integer(100);
//        Integer s = new Integer("100");

        Integer i = Integer.valueOf(100);
        Integer s = Integer.valueOf("100");

        System.out.println(i);
        System.out.println(s);
    }
}
//运行结果：100
//运行结果：100
```



#### Integer_int和String的相互转换

int转换为String

+ static String valueOf(int i)：返回int参数的字符串表示形式。该方法是String类中的方法

String转换为int

+ static int parseInt(String s)：将字符串解析为int类型。该方法是Integer类中的方法

```java
package com.itheima;

public class IntegerDemo02 {
    public static void main(String[] args) {
        //int--string
        int number = 100;
        //方法1
        String s1 = number + "";
        System.out.println(s1);
        //方法2
        String s2 = String.valueOf(number);
        System.out.println(s2);

        //String--int
        String s = "100";
        //方法1
        Integer i = Integer.valueOf(s);
        int x = i.intValue();
        System.out.println(x);
        //方法2
        int y = Integer.parseInt(s);
        System.out.println(y);
    }
}
//运行结果：100
//运行结果：100
//运行结果：100
//运行结果：100
```



#### GUI案例_猜数字

要求：

1. 系统产生一个1-100之间的随机数
2. 猜的内容不能为空
3. 每次根据猜的数字给出相应的提示

```java
package com.itheima;

import javax.swing.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.util.Random;

public class GuessNumber {
    public static void main(String[] args) {
        JFrame jf = new JFrame();

        jf.setTitle("猜数字");
        jf.setSize(400, 300);
        jf.setDefaultCloseOperation(3);
        jf.setLocationRelativeTo(null);
        jf.setAlwaysOnTop(true);
        jf.setLayout(null);

        Random r = new Random();
        int number = r.nextInt(100) + 1;

        JLabel messageLabel = new JLabel("在1-100中猜数字");
        messageLabel.setBounds(70, 50, 350, 20);
        jf.add(messageLabel);

        JTextField numberField = new JTextField();
        numberField.setBounds(120, 100, 150, 20);
        jf.add(numberField);

        JButton guessButton = new JButton("我猜");
        guessButton.setBounds(150, 150, 100, 20);
        jf.add(guessButton);

        guessButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                String stringNumber = numberField.getText().trim();
                if (stringNumber.equals("")) {
                    JOptionPane.showMessageDialog(jf, "猜的数字不能为空");
                    return;
                }

                int guessNumber = Integer.parseInt(stringNumber);

                if (guessNumber > number) {
                    JOptionPane.showMessageDialog(jf, "你猜的数字" + guessNumber + "大了");
                    numberField.setText("");
                } else if (guessNumber < number) {
                    JOptionPane.showMessageDialog(jf, "你猜的数字" + guessNumber + "小了");
                    numberField.setText("");
                }else {
                    JOptionPane.showMessageDialog(jf,"恭喜你猜中了");
                }
            }
        });

        jf.setVisible(true);
    }
}

```



#### Integer_自动装箱和拆箱

+ 装箱：把基本数据类型转换为对应的包装类类型
+ 拆箱：把包装类类型转换为对应的基本数据类型

```java
package com.itheima;

public class IntegerDemo03 {
    public static void main(String[] args) {
        //自动装箱
        Integer ii = 100;
        //Integer ii = Integer.valueOf(100);

        //自动拆箱
        ii += 100;
        /*
            ii += 100;
            ii = ii.intValue() + 100;
            ii = 300;
         */
        System.out.println(ii);
    }
}
//运行结果：200
```



#### Date_构造方法

+ Date类表示特定的时刻，精度为毫秒

构造方法

+ Date()：分配Date对象并对其进行初始化，使其表示分配时间，测量Date到毫秒
+ Date(long date)：分配Date对象并初始化它以表示自标准基准时间以来的指定毫秒数，即1970年1月1日00:00:00

```java
package com.itheima_01;

import java.util.Date;

public class DateDemo {
    public static void main(String[] args) {
        Date d1 = new Date();
        System.out.println(d1);

        Date d2 = new Date(1000 * 60 * 60);
        System.out.println(d2);
    }
}
//运行结果：Mon Aug 29 19:59:36 CST 2022
//运行结果：Thu Jan 01 09:00:00 CST 1970
```



#### SimpleDateFormat_Date和String的相互转化

SimpleDateFormat

+ SimpleDateFormat是一个用于以区域设置敏感的方式格式化和解析日期的具体类。我们重点学习日期格式化和解析
+ 日期和时间格式由日期和时间模式字符串指定，在日期和时间模式字符串中，从'A'到'Z'以及从'a'到'z'引号的字母被解释为表示日期或时间字符串的组成的模式字母
+ 常用模式字母：y年，M月，d日，H时，m分，s秒
  + 举例：2021年10月27日11：11：11
  + 模式：yyyy年MM月dd日HH：mm：ss

构造方法

+ SimpleDateFormat()：构造一个SimpleDateFormate，使用默认模式和日期格式
+ SimpleDateFormat(String pattern)：构造一个SimpleDateFormat使用给定的模式和默认的日期格式

格式化（从Date到String）

+ String format(Date date)：将日期格式化成日期/时间字符串

解析（从String到Date）

+ Dateparse(String source)：从给定字符串的开始解析文本以生成日期

```java
package com.itheima_01;

import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

public class SimpleDateFormatDemo {
    public static void main(String[] args) throws ParseException {
        //格式化
        Date d = new Date();

        SimpleDateFormat sdf1 = new SimpleDateFormat();
        String s1 = sdf1.format(d);
        System.out.println(s1);

        SimpleDateFormat sdf2 = new SimpleDateFormat("yyyy年MM月dd日 HH：mm：ss");
        String s2 = sdf2.format(d);
        System.out.println(s2);

        //解析
        String s3 = "2021-10-27 11:11:11";
        SimpleDateFormat sdf3 = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
        Date dd = sdf3.parse(s3);
        System.out.println(dd);
    }
}
//运行结果：2022/8/29 下午8:28
//运行结果：2022年08月29日 20：28：54
//运行结果：Wed Oct 27 11:11:11 CST 2021
```



### 数组的基本使用

#### 数组概述

什么是数组

+ 数组（array）：是一种用于存储多个相同数据类型的存储类型（可以理解为容器）



#### 数组定义和静态初始化

数组定义格式

+ 格式1：数据类型[] 变量名；
+ 范例：int[] arr;
+ 定义了一个int类型的数组，数组名是arr
+ 格式2：数据类型 变量名[];
+ 范例：int arr[];
+ 定义了一个int类型的变量，变量名是arr数组
+ 推荐格式1

数组初始化概述

+ Java中的数组必须先初始化，然后才能使用
+ 所谓初始化：即使为数组中的数组元素分配内存空间，并为每个数组元素赋值
+ 注意：数组中每一个数据，我们称之为数组中的元素

数组初始化方式

+ 静态初始化
+ 动态初始化

静态初始化：初始化时指定每个数组元素的初始值，由系统决定数组长度

+ 格式：数据类型[] 变量名 = new 数据类型[]{数据1，数据2，数据3……}；
+ 范例：int arr[] = new int[]{1,2,3};
+ 简化格式：数据类型[] 变量名 = {数据1，数据2，数据3……}；
+ 范例：int[] arr = {1,2,3};



#### 数组元素访问_获取和修改

数组元素访问

+ 数组变量访问方法
+ 格式：数组名

数组内部保存的数据的访问方法

+ 格式：格式：数组名[索引]

```java
package com.itheima_01;

public class ArrayDemo {
    public static void main(String[] args) {
        int[] scores = {93,96,99};

        System.out.println(scores.length);
        System.out.println(scores);

        System.out.println(scores[0]);

        scores[1] = 90;
        System.out.println(scores[1]);
    }
}
//运行结果：3
//运行结果：[I@776ec8df
//运行结果：93
//运行结果：90
```



#### 数组动态初始化

数组动态初始化：初始化时只指定数组长度，由系统为数组分配初始值

+ 格式：数据类型[] 变量名 = new 数据类型[数组长度]；
+ 范例：int[] arr = new int[3];

使用场景

+ 静态初始化：开始就存入元素值，适合一开始就确定元素值的业务场景
+ 动态初始化：指定数组长度，后期赋值，适合开始知道数据数量，但是不确定具体元素值的业务场景
+ 注意：两种初始化的方式是独立的，不可以混用

```java
package com.itheima_02;

public class ArrayDemo {
    public static void main(String[] args) {
        int[] arr = new int[3];

        arr[1] = 5;

        for(int i = 0;i < arr.length;i++){
            System.out.println(arr[i]);
        }
    }
}
//运行结果：0
//运行结果：5
//运行结果：0
```



### 二维数组

#### 二维数组概述

二维数组：元素为一维数组的数组

定义格式：

+ ==数据类型[]\[] 变量名;	int[]\[] arr;==
+ 数据类型 变量名[]\[];	int arr[]\[];
+ 数据类型[] 变量名[];	int[] arr[];



#### 二维数组初始化

+ 静态初始化
  + 格式：数据类型[]\[] 变量名 = new 数据类型[]\[]{{元素},{元素}}；
  + 范例：int[]\[] arr = new int[]\[]{{1,2,3},{4,5,6},{7,8,9}};
  + 解读：定义了一个二维数组，二维数组中有三个元素（一维数组），每个一维数组有三个元素（int类型数据）
  + 注意：一维数组中元素的个数可以是不同的
  + 简化格式：数据类型[]\[] 变量名 = {{元素},{元素}}；
  + 范例：int[]\[] arr = {{1,2,3},{4,5,6},{7,8,9}};
+ 动态初始化
  + 格式：数据类型[]\[] 变量名 = new 数据类型[m]\[n];
  + 范例：int[]\[] arr = new int[2]\[3];
  + 解读：定义了一个二维数组，二维数组中有两个元素（一维数组），每个一维数组有三个元素（int类型数据）



#### 二维数组元素访问

+ 获取二维数组：数组名
+ 获取每一个一维数组：数组名[索引]
+ 获取每一个二维数组元素：数组名[索引]\[索引]

```java
package com.itheima_03;

public class ArrayDemo {
    public static void main(String[] args) {
        int[][] arr = {{1,2,3},{4,5,6}};

        System.out.println(arr);
        System.out.println(arr[0]);

        System.out.println(arr[0][1]);
    }
}
//运行结果：[[I@776ec8df
//运行结果：[I@4eec7777
//运行结果：2
```



### 继承

#### 继承概述

什么是继承

+ 继承是面向对象三大特征之一（封装，继承和多态）
+ 可以使得子类具有父类的属性和方法，还可以在子类中重新定义，追加属性和方法

继承的格式

+ 格式：public class 子类名 extends 父类名{}
+ 范例：public class Zi extends Fu {}
+ Fu：是父类，也被称为基类、超类
+ Zi：是子类，也被称为派生类

继承的使用

+ JLabel
+ JButton
+ JTextField
+ JTextArea

+ public void setBounds(int x,int y,int width,int height)

+ 继承好处之一：提高代码的复用性

继承的使用

app.java

```java
package com.itheima02;

public class app {
    public static void main(String[] args) {
        UserLoginFrame userLoginFrame = new UserLoginFrame();
    }
}

```

UserLoginFrame.java

```java
package com.itheima02;

import javax.swing.*;

public class UserLoginFrame extends JFrame{

    public UserLoginFrame(){
        //窗体初始化
        initFrame();

        //绘制窗体
        PrintView();

        this.setVisible(true);
    }

    public void initFrame(){
        this.setTitle("用户登录");
        this.setSize(400,300);
        this.setDefaultCloseOperation(3);
        this.setLocationRelativeTo(null);
        this.setAlwaysOnTop(true);
        this.setLayout(null);
    }

    public void PrintView(){
        //显示用户名文本
        JLabel usernameLabel = new JLabel("用户名");
        usernameLabel.setBounds(50,50,50,20);
        this.add(usernameLabel);

        //用户名输入框
        JTextField usernameField = new JTextField();
        usernameField.setBounds(150,50,180,20);
        this.add(usernameField);

        //显示密码文本
        JLabel passwordLabel = new JLabel("密码");
        passwordLabel.setBounds(50,100,50,20);
        this.add(passwordLabel);

        //密码输入框
        JPasswordField passwordField = new JPasswordField();
        passwordField.setBounds(150,100,180,20);
        this.add(passwordField);

        //登录按钮
        JButton loginButton = new JButton("登录");
        loginButton.setBounds(50,200,280,20);
        this.add(loginButton);
    }
}

```



#### 动漫拼图案例

##### 窗体绘制

实现步骤：

1. 新建模块：itheima-picture-puzzle；在模块的src下新建一个包com.itheima
2. 在com.itheima这个包下定义类：PictureFrame，继承自JFrame
3. 在PictureFrame类中编写无参构造方法，在构造方法中调用两个方法：
   + 第一个方法：initFrame()，用于窗体的基本设置
   + 第二个方法：setVisible()，用于设置窗体可见
4. 在initFrame()方法中编写代码，进行窗体的基本设置
   + 窗体大小
   + 窗体标题
   + 窗体居中
   + 窗体关闭时退出应用程序
   + 窗体位于其他窗口之上
   + 取消窗体默认布局
5. 在com.itheima包下定义测试类：App；创建PictureFrame的对象进行测试

PictureFrame.java

```java
package com.itheima;

import javax.swing.*;

public class PictureFrame extends JFrame {
    public PictureFrame(){
        //用于窗体的基本设置
        initFrame();

        //设置窗体可见
        this.setVisible(true);
    }

    //用于窗体的基本设置
    public void initFrame(){
        //设置窗体大小
        this.setSize(960,565);
        //窗体标题
        this.setTitle("拼图");
        //窗体居中
        this.setLocationRelativeTo(null);
        //窗体关闭时退出应用程序
        this.setDefaultCloseOperation(3);
        //窗体位于其他窗体之上
        this.setAlwaysOnTop(true);
        //取消窗体默认布局
        this.setLayout(null);
    }
}

```

App.java

```java
package com.itheima;

public class App {
    public static void main(String[] args) {
        PictureFrame pf = new PictureFrame();
    }
}

```



##### 窗体上组件绘制

```java
    public void paintView(){
        //创建面板
        JPanel imagePanel = new JPanel();
        imagePanel.setBounds(150,114,360,360);
        imagePanel.setLayout(null);
        //遍历二维数组，得到图片编号
        for(int i = 0;i < dates.length;i++){
            for(int j = 0;j < dates[i].length;j++){
                //创建JLabel对象，加载图片的编号
                JLabel imageLabel = new JLabel(new ImageIcon("itheima-picture-puzzle\\images\\"+dates[i][j]+".png"));
                //调整图片的位置
                imageLabel.setBounds(j*90,i*90,90,90);
                imagePanel.add(imageLabel);
            }
        }
        //把面板添加到窗体上
        this.add(imagePanel);

        //参照图
        JLabel referImageLabel = new JLabel(new ImageIcon("itheima-picture-puzzle\\images\\finish.png"));
        referImageLabel.setBounds(574,114,121,121);
        this.add(referImageLabel);

        //上下左右、完成、重置按钮
        JButton upButton = new JButton(new ImageIcon("itheima-picture-puzzle\\images\\up.png"));
        upButton.setBounds(732,265,57,57);
        this.add(upButton);

        JButton leftButton = new JButton(new ImageIcon("itheima-picture-puzzle\\images\\left.png"));
        leftButton.setBounds(650,347,57,57);
        this.add(leftButton);

        JButton downButton = new JButton(new ImageIcon("itheima-picture-puzzle\\images\\down.png"));
        downButton.setBounds(732,347,57,57);
        this.add(downButton);

        JButton rightButton = new JButton(new ImageIcon("itheima-picture-puzzle\\images\\right.png"));
        rightButton.setBounds(813,347,57,57);
        this.add(rightButton);

        JButton endButton = new JButton(new ImageIcon("itheima-picture-puzzle\\images\\end.png"));
        endButton.setBounds(626,444,108,45);
        this.add(endButton);

        JButton returnButton = new JButton(new ImageIcon("itheima-picture-puzzle\\images\\return.png"));
        returnButton.setBounds(786,444,108,45);
        this.add(returnButton);

        //展示背景图
        JLabel backgroungLabel = new JLabel(new ImageIcon("itheima-picture-puzzle\\images\\ground.png"));
        backgroungLabel.setBounds(0,0,960,530);
        this.add(backgroungLabel);
    }
```



##### 图片打乱

```java
    public void randdomData(){
        Random r = new Random();
        for (int i = 0;i < dates.length;i++){
            for(int j = 0;j < dates[i].length;j++){
                int x = r.nextInt(dates.length);
                int y = r.nextInt(dates[i].length);

                int temp = dates[i][j];
                dates[i][j] = dates[x][y];
                dates[x][y] = temp;
            }
        }
    }
```



##### 记录0号图片索引

```java
    private int x0;
    private int y0;

    public void randdomData(){
        Random r = new Random();
        for (int i = 0;i < dates.length;i++){
            for(int j = 0;j < dates[i].length;j++){
                int x = r.nextInt(dates.length);
                int y = r.nextInt(dates[i].length);

                int temp = dates[i][j];
                dates[i][j] = dates[x][y];
                dates[x][y] = temp;
            }
        }

        wc:for (int i = 0; i < dates.length; i++) {
            for (int j = 0;j < dates.length; j++) {
                if(dates[i][j] == 0){
                    x0 = i;
                    y0 = j;
                    break wc;
                }
            }
        }
    }
```



##### 给按钮添加事件

```java
    //给按钮添加事件
    public void addButtonEvent(){
        upButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {

            }
        });

        leftButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {

            }
        });

        downButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {

            }
        });

        rightButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {

            }
        });

        endButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {

            }
        });

        returnButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {

            }
        });
    }
```



##### 移动事件及重绘面板

```java
    //移动图案绘制
    public void rePrintView(){
        //清除画板上的图案
        imagePanel.removeAll();

        //重新绘制窗体
        for(int i = 0;i < dates.length;i++){
            for(int j = 0;j < dates[i].length;j++){
                //创建JLabel对象，加载图片的编号
                JLabel imageLabel = new JLabel(new ImageIcon("itheima-picture-puzzle\\images\\"+dates[i][j]+".png"));
                //调整图片的位置
                imageLabel.setBounds(j*90,i*90,90,90);
                imagePanel.add(imageLabel);
            }
        }
        //重新绘制
        imagePanel.repaint();
    }

    //给按钮添加事件
    public void addButtonEvent(){
        upButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                if(x0 == 0){
                    return;
                }

                dates[x0][y0] = dates[x0-1][y0];
                dates[x0-1][y0] = 0;
                x0 = x0 - 1;

                //重绘画板
                rePrintView();
            }
        });

        leftButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                if(y0 == 0){
                    return;
                }

                dates[x0][y0] = dates[x0][y0-1];
                dates[x0][y0-1] = 0;
                y0 = y0 - 1;

                //重绘画板
                rePrintView();
            }
        });

        downButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                if(x0 == 3){
                    return;
                }

                dates[x0][y0] = dates[x0+1][y0];
                dates[x0+1][y0] = 0;
                x0 = x0 + 1;

                //重绘画板
                rePrintView();
            }
        });

        rightButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                if(y0 == 3){
                    return;
                }

                dates[x0][y0] = dates[x0][y0+1];
                dates[x0][y0+1] = 0;
                y0 = y0 + 1;

                //重绘画板
                rePrintView();
            }
        });

        endButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {

            }
        });

        returnButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {

            }
        });
    }
```



##### 完全体

```java
package com.itheima05;

import javax.swing.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.util.Random;

public class PictureFrame extends JFrame {
    //定义二维数组，用于存储图片的编号
    private int[][] dates = {
            {1,2,3,4},
            {5,6,7,8},
            {9,10,11,12},
            {13,14,15,0}
    };

    //定义成功后的数组
    private int[][] winDates = {
            {1,2,3,4},
            {5,6,7,8},
            {9,10,11,12},
            {13,14,15,0}
    };

    //上下左右、完成、重置按钮
    private JButton upButton;
    private JButton downButton;
    private JButton leftButton;
    private JButton rightButton;
    private JButton endButton;
    private JButton returnButton;

    //定义面板
    private JPanel imagePanel;

    private int x0;
    private int y0;
    public PictureFrame(){
        //用于窗体的基本设置
        initFrame();
        //二维数组元素打乱
        randdomData();
        //窗体上组件的绘制
        paintView();
        //给按钮添加事件
        addButtonEvent();

        //设置窗体可见
        this.setVisible(true);
    }

    //判断移动是否成功
    public boolean isSuccess(){
        for(int i = 0;i < dates.length;i++){
            for(int j = 0;j < dates.length;j++){
                if(dates[i][j] != winDates[i][j]){
                    return false;
                }
            }
        }
        return true;
    }

    //移动成功
    public void success(){
        dates = new int[][]{
                {1,2,3,4},
                {5,6,7,8},
                {9,10,11,12},
                {13,14,15,16}
        };
        //按钮不能点击
        upButton.setEnabled(false);
        downButton.setEnabled(false);
        leftButton.setEnabled(false);
        rightButton.setEnabled(false);
        rePrintView();
    }

    //移动图案绘制
    public void rePrintView(){
        //清除画板上的图案
        imagePanel.removeAll();

        //重新绘制窗体
        for(int i = 0;i < dates.length;i++){
            for(int j = 0;j < dates[i].length;j++){
                //创建JLabel对象，加载图片的编号
                JLabel imageLabel = new JLabel(new ImageIcon("itheima-picture-puzzle\\images\\"+dates[i][j]+".png"));
                //调整图片的位置
                imageLabel.setBounds(j*90,i*90,90,90);
                imagePanel.add(imageLabel);
            }
        }
        //重新绘制
        imagePanel.repaint();
    }

    //给按钮添加事件
    public void addButtonEvent(){
        upButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                if(x0 == 0){
                    return;
                }

                dates[x0][y0] = dates[x0-1][y0];
                dates[x0-1][y0] = 0;
                x0 = x0 - 1;

                if(isSuccess()){
                    success();
                }

                //重绘画板
                rePrintView();
            }
        });

        leftButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                if(y0 == 0){
                    return;
                }

                dates[x0][y0] = dates[x0][y0-1];
                dates[x0][y0-1] = 0;
                y0 = y0 - 1;

                if(isSuccess()){
                    success();
                }

                //重绘画板
                rePrintView();
            }
        });

        downButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                if(x0 == 3){
                    return;
                }

                dates[x0][y0] = dates[x0+1][y0];
                dates[x0+1][y0] = 0;
                x0 = x0 + 1;

                if(isSuccess()){
                    success();
                }

                //重绘画板
                rePrintView();
            }
        });

        rightButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                if(y0 == 3){
                    return;
                }

                dates[x0][y0] = dates[x0][y0+1];
                dates[x0][y0+1] = 0;
                y0 = y0 + 1;

                if(isSuccess()){
                    success();
                }

                //重绘画板
                rePrintView();
            }
        });

        endButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                success();
            }
        });

        returnButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                dates = new int[][]{
                        {1,2,3,4},
                        {5,6,7,8},
                        {9,10,11,12},
                        {13,14,15,0}
                };
                randdomData();
                rePrintView();
                upButton.setEnabled(true);
                downButton.setEnabled(true);
                leftButton.setEnabled(true);
                rightButton.setEnabled(true);
            }
        });
    }

    //二维数组元素打乱
    public void randdomData(){
        Random r = new Random();
        for (int i = 0;i < dates.length;i++){
            for(int j = 0;j < dates[i].length;j++){
                int x = r.nextInt(dates.length);
                int y = r.nextInt(dates[i].length);

                int temp = dates[i][j];
                dates[i][j] = dates[x][y];
                dates[x][y] = temp;
            }
        }

        wc:for (int i = 0; i < dates.length; i++) {
            for (int j = 0;j < dates.length; j++) {
                if(dates[i][j] == 0){
                    x0 = i;
                    y0 = j;
                    break wc;
                }
            }
        }
    }

    //窗体上组件的绘制
    public void paintView(){
        //创建面板
        imagePanel = new JPanel();
        imagePanel.setBounds(150,114,360,360);
        imagePanel.setLayout(null);
        //遍历二维数组，得到图片编号
        for(int i = 0;i < dates.length;i++){
            for(int j = 0;j < dates[i].length;j++){
                //创建JLabel对象，加载图片的编号
                JLabel imageLabel = new JLabel(new ImageIcon("itheima-picture-puzzle\\images\\"+dates[i][j]+".png"));
                //调整图片的位置
                imageLabel.setBounds(j*90,i*90,90,90);
                imagePanel.add(imageLabel);
            }
        }
        //把面板添加到窗体上
        this.add(imagePanel);

        //参照图
        JLabel referImageLabel = new JLabel(new ImageIcon("itheima-picture-puzzle\\images\\finish.png"));
        referImageLabel.setBounds(574,114,121,121);
        this.add(referImageLabel);

        //上下左右、完成、重置按钮
         upButton = new JButton(new ImageIcon("itheima-picture-puzzle\\images\\up.png"));
        upButton.setBounds(732,265,57,57);
        this.add(upButton);

         leftButton = new JButton(new ImageIcon("itheima-picture-puzzle\\images\\left.png"));
        leftButton.setBounds(650,347,57,57);
        this.add(leftButton);

         downButton = new JButton(new ImageIcon("itheima-picture-puzzle\\images\\down.png"));
        downButton.setBounds(732,347,57,57);
        this.add(downButton);

         rightButton = new JButton(new ImageIcon("itheima-picture-puzzle\\images\\right.png"));
        rightButton.setBounds(813,347,57,57);
        this.add(rightButton);

         endButton = new JButton(new ImageIcon("itheima-picture-puzzle\\images\\end.png"));
        endButton.setBounds(626,444,108,45);
        this.add(endButton);

         returnButton = new JButton(new ImageIcon("itheima-picture-puzzle\\images\\return.png"));
        returnButton.setBounds(786,444,108,45);
        this.add(returnButton);

        //展示背景图
        JLabel backgroungLabel = new JLabel(new ImageIcon("itheima-picture-puzzle\\images\\ground.png"));
        backgroungLabel.setBounds(0,0,960,530);
        this.add(backgroungLabel);
    }

    //用于窗体的基本设置
    public void initFrame() {
        //设置窗体大小
        this.setSize(960, 565);
        //窗体标题
        this.setTitle("拼图");
        //窗体居中
        this.setLocationRelativeTo(null);
        //窗体关闭时退出应用程序
        this.setDefaultCloseOperation(3);
        //窗体位于其他窗体之上
        this.setAlwaysOnTop(true);
        //取消窗体默认布局
        this.setLayout(null);
    }
}

```



# 阶段二JAVASE进阶



## 面向对象基础

### 面向过程和面向对象思想对比

+ 面向过程编程（Procedure Oriented Programming）
  + 是一种以过程为中心的编程思想，实现功能的每一步，都是自己实现的
+ 面向对象编程（object oriented programming）
  + 是一种以对象为中心的编程思想，通过指挥对象实现具体的功能



### 类和对象的关系

什么是类

+ 类是对现实中一类具有共同属性和行为的事物的抽象

  【类】是对事物，也就是对象的一种描述，可以将类理解为一张设计图，根据设计图，可以创建出具体存在的事物，==根据类去创建对象==

类的组成

+ 属性

  该事物的各种特征

+ 行为

  该事物存在的功能（能做的事）



### 类的定义

类的组成：属性和行为

+ 属性：在代码中通过成员变量来体现（类中方法外的变量）
+ 行为：在代码中通过成员方法来体现（和前面的方法相比去掉static关键字即可）

```java
package com.itheima.object01;

public class Student {
    //属性：姓名，年龄
    //成员变量
    String name;
    int age;

    //行为：学习
    //成员方法
    public void Study(){
        System.out.println("学习");
    }
}

```



### 对象的创建和使用

创建对象

+ 格式：类名 对象名  = new 类名();
+ 范例：Student s = new Student();

使用对象

1. 使用成员变量
   + 格式：对象名.变量名
   + 范例：s.name
2. 使用成员方法
   + 格式：对象名.方法名
   + 范例：s.study();

```java
package com.itheima.object01;

public class TestStudent {
    public static void main(String[] args) {
        //创建对象
        Student stu = new Student();
        //调用成员变量
        System.out.println(stu.name);
        System.out.println(stu.age);

        stu.name = "张三";
        stu.age = 13;

        System.out.println(stu.name);
        System.out.println(stu.age);

        //成员方法
        stu.Study();
    }
}

```



### 成员变量和局部变量的区别

成员变量：类中方法外的变量

局部变量：方法中的变量

| 区别           | 成员变量                                   | 局部变量                                       |
| -------------- | ------------------------------------------ | ---------------------------------------------- |
| 类中位置不同   | 类中方法外                                 | 方法内或者方法声明上（形参）                   |
| 内存中位置不同 | 堆内存                                     | 栈内存                                         |
| 生命周期不同   | 随着对象的存在而存在，随着对象的消失而消失 | 随着方法的调用而存在，随着方法的调用完毕而消失 |
| 初始化值不同   | 有默认的初始化值                           | 没有默认的初始化值，必须先定义，赋值，才能使用 |



### private关键字

+ 是一个权限修饰符
+ 可以修饰成员（成员方法和成员变量）
+ 被private修饰的成员只能在本类中才能访问

针对private修饰的成员变量，如果需要被其他类使用，提供相应的操作

+ 提供“get变量名()”方法，用于获取成员变量的值，方法用public修饰
+ 提供“set变量名()”方法，用于设置成员变量的值，方法用public修饰

Student.java

```java
package com.itheima.object02;

public class Student {
    String name;
    private int age;

    public void setAge(int a){
        if(a >=0 && a <= 120){
            age = a;
        }else{
            System.out.println("年龄不符合");
        }
    }

    public int getAge(){
        return age;
    }

    public void show(){
        System.out.println(name + "…" + age);
    }
}

```



### private关键字的使用

Student.java

```java
package com.itheima.test02;

public class Student {
    private String name;
    private int age;

    public void setName(String n){
        name = n;
    }

    public String getName(){
        return name;
    }

    public void setAge(int a){
        if(a >= 0 && a <= 120){
            age = a;
        }else {
            System.out.println("年龄不符合要求");
        }
    }

    public int getAge(){
        return age;
    }

    public void show(){
        System.out.println(name + "……" + age);
    }
}

```

TestStudent.java

```java
package com.itheima.test02;

public class TestStudent {
    public static void main(String[] args) {
        Student stu = new Student();
        stu.setName("张三");
        stu.setAge(23);

        System.out.println(stu.getName());
        System.out.println(stu.getAge());

        stu.show();
    }
}

```



### this关键字

this关键字的作用：可以调用本类的成员（变量，方法）解决局部变量和成员变量的重名问题

this：代表所在类的对象引用

+ 方法被哪个对象调用，this就代表哪个对象

```java
package com.itheima.test02;

public class Student {
    private String name;
    private int age;

    public void setName(String name){
        this.name = name ;
    }

    public String getName(){
        return name;
    }

    public void setAge(int age ){
        if(age >= 0 && age <= 120){
            this.age = age;
        }else {
            System.out.println("年龄不符合要求");
        }
    }

    public int getAge(){
        return age;
    }

    public void show(){
        System.out.println(name + "……" + age);
    }
}

```



### 封装

+ 面向对象三大特征之一（封装，继承，多态）
+ 隐藏实现细节，仅对外暴露公共的访问方式
+ 封装常见的体现：
  1. 私有成员变量，提供setXxx和getXxx方法
  2. 将代码抽取到方法中，这是对代码的一种封装
  3. 将属性抽取到类当中，这是对数据的一种封装
+ 封装的好处：
  + 提高了代码的安全性
  + 提高了代码的复用性



### 构造方法的格式和执行时机

构造方法概述

+ 构造、创建对象的时候，所调用的方法
+ 格式：
  1. 方法名与类名相同，大小写也要一致
  2. 没有返回值类型，连void都没有
  3. 没有具体的返回值（不能由return带回结果数据）
+ 执行时机：
  1. 创建对象的时候调用，每创建一次对象，就会执行一次构造方法
  2. 不能手动调用构造方法

```java
package com.itheima.constructor;

public class Student {
    public Student(){
        System.out.println("student构造方法");
    }
}

```



### 构造方法的作用

+ 作用：用于给对象的数据（属性）进行初始化

Student.java

```java
package com.itheima.constructor;

public class Student {
    private String name;
    private int age;

    public Student(String name,int age){
        System.out.println("student构造方法");
        this.name = name;
        this.age = age;
    }

    public void show(){
        System.out.println(name + "…" + age);
    }
}

```

TestStudent.java

```java
package com.itheima.constructor;

public class TestStudent {
    public static void main(String[] args) {
        Student stu = new Student("张三",18);
        stu.show();
    }
}

```



### 构造方法注意事项

1. 构造方法的创建
   + 如果没有定义构造方法，系统将给出一个默认的无参构造方法
   + 如果定义了构造方法，系统将不再提供默认的构造方法
2. 构造方法的重载
   + 如果自定义了带构造方法，还要使用无参构造方法，就必须要写一个无参构造方法
3. 推荐的使用方法
   + 无论是否使用，都手动书写无参构造方法，和带参数构造方法



### 标准类的代码编写和使用

标准类制作

1. 成员变量
   + 使用private修饰
2. 构造方法
   + 提供一个无参构造方法
   + 提供一个带多个参数的构造方法
3. 成员方法
   + 提供每一个成员变量对应的setXxx()/getXxx()
   + 提供一个显示对象信息的show()
4. 创建对象并为其成员变量赋值的两种方法
   + 无参构造方法创建对象后使用setXxx()赋值
   + 使用带参构造方法直接创建带有属性值的对象

Student.java

```java
package com.itheima.test03;

public class Student {
    private String name;
    private int age;

    public Student(){

    }
    public Student(String name,int age){
        this.name = name;
        this.age = age;
    }

    public void setName(String name){
        this.name = name;
    }

    public String getName() {
        return name;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public int getAge() {
        return age;
    }

    public void show(){
        System.out.println(name+"……"+age);
    }
}

```

TestStudent.java

```java
package com.itheima.test03;

public class TestStudent {
    public static void main(String[] args) {
        Student stu1 = new Student();
        stu1.setName("张三");
        stu1.setAge(23);
        stu1.show();

        Student stu2 = new Student("李四",25);
        stu2.show();
    }

}

```



## 常用API

API概述：API（Application Programming Interface）：应用程序编程接口

### String类

#### 键盘录入字符串

```java
package com.itheima.api;

import java.util.Scanner;

public class Demo1Scanner {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入");

        String s = sc.nextLine();

        System.out.println(s);
    }
}

```



#### String概述

String类在java.lang包下，所以使用的时候不需要导包

String类代表字符串，Java程序中的所有字符串文字（例如“abc”）都被实现为此类的实例，也就是说，Java程序中所有的双引号字符串，都是String类的对象

字符串不可变，它们的值在创建后不能被改变

```java
package com.itheima.string;

public class Demo1String {
    public static void main(String[] args) {
        String s1 = "abc123";
        int length = s1.length();
        System.out.println(length);
        
        s1 = "def";
        System.out.println(s1);
    }
}

```



#### String类中常见的构造方法

| 方法名                         | 说明                                    |
| ------------------------------ | --------------------------------------- |
| pubilc String()                | 创建一个空白字符串对象，不含有任何内容  |
| public String(char chs)        | 根据字符数组的内容来创建字符串对象      |
| public String(String original) | 根据传入的字符串内容，来创建字符串对象  |
| String s = "abc";              | 直接赋值的方式创建字符串对象，内容是abc |

```java
package com.itheima.string;

public class Demo2StringConstructor {
    public static void main(String[] args) {
        String s1 = new String();
        System.out.println(s1);

        char[] chs = {'a','b','c'};
        String s2 = new String(chs);
        System.out.println(s2);

        String s3 = new String("123");
        System.out.println(s3);
    }
}

```



#### 创建字符串对象的区别对比

+ 问题：构造方法创建对象，双引号也能创建字符串对象，有什么区别吗？

+ 注意：==号做比较

  + 基本数据类型：比较的是具体的值

    ```java
    int a = 10;
    int b = 10;
    System.out.println(a == b);
    //false
    ```

  + 引用数据类型：比较地址值

    ```java
    Student s1 = new Student(23);
    Student S2 = S1;
    System.out.println(s1 == s2);
    //true
    ```

  + 问题：下列代码的运行结果是？
  
    ```java
    String s1 = "abc";
    String s2 = "abc";
    System.out.println(s1 == s2);
    
    char[] chs = {'a','b','c'};
    String s3 = new String(chs);
    Sreing s4 = new String(chs);
    System.out.println(s3 == s4);
    //true
    //false
    ```



以双引号给出的字符串，只要字符序列 相同（顺序和大小写），无论程序代码中出现几次，JVM都只会建立一个String对象，并在字符串常量池中维护

```java
String s1 = "abc";
String s2 = "abc";
```

+ 字符串常量池：当使用双引号创建字符串对象的时候，系统会检查字符串是否在字符串常量池中存在；不存在：创建；存在：直接复用



通过new创建的字符串对象，每一次new都会申请一个内存空间，虽然内容相同，但是地址值不同

```java
char[] chs = {'a','b','c'};
String s3 = new String(chs);
Sreing s4 = new String(chs);
```

上面的代码中，JVM会首先创建一个字符数组，然后每一次new的时候都会有一个新的地址



#### String字符串的特点

+ Java程序中所有的双引号字符串，都是String类的对象
+ 字符串不可变，它们的值在创建后不能被更改
+ 虽然String的值是不可变的，但是它们可以被共享



问题：下列代码的运行结果？

```java
String s1 = "abc";
String s2 = "ab";
String s3 = s2 + "c";
System.out.println(s1 == s3);
//false
```

当字符串之间使用+号串联（拼接）的时候，系统底层会自动创建一个StringBuilder对象，然后再调用其append方法完成拼接，拼接后，再调用其toString方法转换为String类型



问题：下列代码的运行结果是？

```java
String s1 = "abc";
String s2 = "a" + "b" + "c";
System.out.println(s1 == s2);
//true
```

Java存在常量优化机制，在编译的时候，就会将"a"+"b"+"c"拼接成"abc"



#### 字符串的比较

使用==做比较

+ 基本类型：比较的是数据值是否相同
+ 引用类型：比较的是地址符是否相同

字符串是对象，它比较内容是否相同，是通过一个方法来实现的，这个方法叫equals()

+ public boolean equals(Object anObject)：将此字符串与指定对象进行比较，由于我们比较的是字符串对象，所以参数直接传递一个字符串

```java
package com.itheima.stringmethod;

public class Demo1Equals {
    public static void main(String[] args) {
        String s1 = "abc";
        String s2 = "ABC";
        String s3 = "abc";

        System.out.println(s1.equals(s2));
        System.out.println(s1.equals(s3));

        //比较忽略大小写
        System.out.println(s1.equalsIgnoreCase(s2));
    }
}
//false
//true
//true
```



#### 用户登录案例

需求：已知用户名和密码，请用程序实现模拟用户登录，总共给三次机会，登录之后，给出相应提示

思路：

1. 已知用户名和密码，定义两个字符串表示即可
2. 键盘录入要登录的用户名和密码，用Scanner实现
3. 拿键盘录入的用户名，密码和已知的用户名，密码进行比较，字符串的内容比较，用equals()方法实现
4. 用循环实现多次机会，这里的次数用for循环实现，并在登陆成功的时候，使用break结束循环

```java
package com.itheima.test;

import java.util.Scanner;

public class Test1 {
    public static void main(String[] args) {
        String username = "admin";
        String password = "123456";

        for(int i = 1;i<=3;i++){
            Scanner sc = new Scanner(System.in);
            System.out.println("请输入用户名");
            String scUsername = sc.nextLine();
            System.out.println("请输入密码");
            String scPassword = sc.nextLine();

            if(username.equals(scUsername) && password.equals(scPassword)){
                System.out.println("登录成功");
                break;
            }else{
                if(i == 3){
                    System.out.println("次数已使用完，明天再来");
                }else{
                    System.out.println("登录失败。您还剩余"+(3-i)+"次机会");
                }
            }
        }
    }
}

```



#### 字符串的遍历

需求：键盘录入一个字符串，使用程序实现控制台遍历该字符串

思路1：

1. 键盘录入一个字符串，用Scanner实现
2. 遍历字符串，首先要能获取到字符串中的每一个字符
   + public char charAt(int index)：返回指定索引处的char值，字符串的索引也是从0开始的
3. 遍历字符串，其次要能够获取字符串的长度
   + public int length()：返回此字符串的长度
   + 数组的长度：数组名.length
   + 字符串的长度：字符串对象.length()
4. 遍历

```java
package com.itheima.test;

import java.util.Scanner;

public class test2 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入：");
        String s = sc.nextLine();

        for (int i = 0; i < s.length(); i++) {
            char c = s.charAt(i);
            System.out.println(c);
        }
    }
}

```



思路2：

1. 键盘录入一个字符串，用Scanner实现
2. 将字符串拆分为字符数组
   + public char[] toCharArray()：将当前的字符串拆分为字符数组并返回

```java
package com.itheima.test;

import java.util.Scanner;

public class test2 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入：");
        String s = sc.nextLine();

        for (int i = 0; i < s.length(); i++) {
            char c = s.charAt(i);
            System.out.println(c);
        }
    }
}

```



#### 统计字符次数

需求：键盘录入一个字符串，统计字符串大写字母字符，小写字母字符，数字字符出现的次数（不考虑其他字符）

思路：

1. 键盘录入一个字符串，用Scanner实现
2. 要统计三种类型的字符个数，需定义三个统计变量，初始值都为0
3. 遍历字符串，得到每一个字符
4. 判断该字符属于哪种类型，然后对应类型的统计变量+1
   + 大写字母：ch>='A'&&ch<='Z'
   + 小写字母：ch>='a'&&ch<='z'
   + 数字：ch>='0'&&ch<='9'
5. 输出三种类型字符的个数

```java
package com.itheima.test;

import java.util.Scanner;

public class Test4 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入：");
        String s = sc.nextLine();
        int bigCount = 0;
        int smallCount = 0;
        int numberCount = 0;
        char[] chars = s.toCharArray();

        for (int i = 0; i < chars.length; i++) {
            char c = chars[i];
            if (c >= 'A' && c <= 'Z') {
                bigCount++;
            } else if (c >= 'a' && c <= 'z') {
                smallCount++;
            } else if (c >= '0' && c <= '9') {
                numberCount++;
            }
        }

        System.out.println("大写字母字符个数为" + bigCount);
        System.out.println("小写字母字符个数为" + smallCount);
        System.out.println("数字字符个数为" + numberCount);
    }
}

```



#### 字符串截取

String substring(int beginIndex)：从传入的索引开始一直截取到末尾

String substring(int beginIndex,int endIndex)：从beginIndex开始，截取到endIndex处
