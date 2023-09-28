# 肖成康的Java笔记

## 第一周Java程序（计算）

### 第一个Java程序（输出）

1. 新建==Java项目=="first Java program"；
2. 在==src==里新建软件包"Hello"；
3. 在"Hello"软件包里新建==Java类=="hello"；(自动生成为hello.java)
4. 在hello.java中写下第一个Java程序；

```java
package Hello;

public class hello{
	public static void main(String[] args){
	    System.out.println("hello world");
  }
}

```

+ package[^1]：下列程序代码打包为程序包
+ public class[^2]：设计一个类
+ public static  void main[^3] ()：main方法，即程序入口
+ String[] args[^4]：非固定数组名字
+ System.out.println[^5]\("hello world")：向外输出"hello world"，并回车

运行程序，显示

```
hello world
```

### 第二个Java 程序（变量和计算）

1. 在==src==新建软件包"Variate"
2. 在"Variate"软件包里新建Java类"variate"；
3. 在variate.java里写下第二个Java程序；


```java
package Variate;

import java.util.Scanner;

public class variate{
	public static void main(String[] args){
		Scanner in = new Scanner(System.in);
        System.out.println(in.nextLine());
        System.out.println(2+3+"=2+3="+2+3);
        System.out.println("2+3="+(2+3));
  }
}
```

* import java.util.Scanner[^6]：导入java.utl的Scanner类
* Scanner in = new Scanner(System.in)[^7]：定义变量in
* System.out.println(in.nextLine())：输出用户输入的一整行，并回车
* System.out.println(2+3+"=2+3="+2+3)：计算2+3输出"=2+3="输出23，并回车
* System.out.println("2+3="+(2+3))：输出"2+3"计算2+3，并回车

运行程序，输入

```
hello
```

显示结果

```
echo:hello
5=2+3=23
2+3=5
```

### 第三个Java程序（变量和计算）

1. 在==src==新建软件包"Calculate"；
2. 在"Calculate"软件包里新建Java类"calculate"；
3. 在calcullate.java里写下第三个Java程序；

```java
package Calculate;

import java.util.Scanner;

public class calculate {

    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        final int number=99;
        int amount;
        int price;
        System.out.print("请输入票面：");
        amount = in.nextInt();
        System.out.print("请输入价格:");
        price = in.nextInt();
        System.out.println(amount+"-"+price+"="+(amount-price));
        System.out.println(number);
    }
}
```

* final int number[^8]=99：定义不变常量number为99
* int price[^9]：定义整数变量price
* System.out.print[^10]\("请输入票面：")：输出，不回车
* amount = in.nextInt()[^11]：将用户输入的整数赋值给amount

运行程序，输入

```
请输入票面：100
请输入价格：34
```

显示结果

```
100-34=66
99
```

### 第四个Java程序（浮点数）

1. 在==src==新建软件包"Calculateflout"；
2. 在"Calculateflout"软件包里新建Java类"calculateflout"；
3. 在calcullateflout.java里写下第四个Java程序；

```java
package Variateflout;

import java.util.Scanner;

public class variateflout {

    public static void main(String[] args){
        int foot;
        double inch;
        Scanner in = new Scanner(System.in);
        foot=in.nextInt();
        inch=in.nextDouble();
        System.out.println("foot="+foot+",inch="+inch);
        System.out.println((foot+inch/12)*0.3048);
        System.out.println((int)((foot+inch/12)*0.3048*100));
        System.out.println("1.2-1.1="+(1.2-1.1));
    }
}

```

+ double inch[^12]：定义一个双精度浮点数变量inch
+ inch=in.nextDouble()[^13]：将用户输入的双精度浮点数赋值给inch
+ (int)((foot+inch/12)*0.3048\*100)[^14]：将后面的计算结果的双精度浮点数类型强制转换整数类型

运行程序，输入

```
5 7
```

显示结果

```
foot=5,inch=7.0
1.7018
170
1.2-1.1=0.09999999999999987
```

## 第二周Java程序（判断）

### 第一个Java程序（比较）

1. 新建==Java项目=="second Java program"；
2. 在==src==里新建软件包"Compare"；
3. 在"compare"软件包里新建==Java类=="compar"；
4. 在compare.java中写下第一个Java程序；

```java
package Compare;

public class compare {

    public static void main(String[] args){
        double a=1.0;
        double b=0.1+0.1+0.1+0.1+0.1+0.1+0.1+0.1+0.1+0.1;
        System.out.println("a="+a+";b="+b);
        System.out.println(Math.abs(a-b)<1e-6);
    }
}
```

+ Math.bas(a-b)<1e-6[^15]：将a-b的绝对值与0.000001做小于比较
+ <,>,<=,>=,==,!=[^16]：小于，大于，小于等于，大于等于，等于，不等于

运行程序，得到结果

```
a=1.0;b=0.9999999999999999
true
```

### 第二个Java程序（判断）

1. 在==src==新建软件包"Decide"；
2. 在"Decide"软件包里新建Java类"decide"；
3. 在decide.java里写下第二个Java程序；

```java
package Decide;

import java.util.Scanner;

public class decide {
    public static void main(String[] args){
        int x;
        int y;
        Scanner in = new Scanner(System.in);
        x = in.nextInt();
        y = in.nextInt();
        if (x>=y)
            System.out.println("max="+x);
        else
            System.out.println("max="+y);
    }
}
```

if(A){B}else{C}[^17]：如果A成立，执行B，否则执行C

执行程序，输入

```
3  5
```

得到结果

```
max=5
```

### 第三个Java程序（嵌套）

1. 在src新建软件包"Nest"；
2. 在"Nest"软件包里新建Java类"nest"；
3. 在nest.java里写下第三个Java程序；

```
package Nest;

import java.util.Scanner;

public class next {
    public static void main(String[] args){
        int x,y,z;
        Scanner in = new Scanner(System.in);
        x=in.nextInt();
        y=in.nextInt();
        z=in.nextInt();
        if(x>=y){
            if(x>=z){
                System.out.println("max="+x);
            }
            else{
                System.out.println("max="+z);
            }
        }else{
            if(y>=z){
                System.out.println("max="+y);
            }
            else{
                System.out.println("max="+z);
            }
        }
    }
}
```

运行程序，输入

```
3 5 7
```

得出结果

```
max=7
```

### 第四个Java程序（级联）

1. 在src新建软件包"Cascade"；
2. 在"Cascade"软件包里新建Java类"cascade"；
3. 在cascade.java里写下第四个Java程序；

```Java
package Cascade;

import java.util.Scanner;

public class cascade {

    public static void main(String[] args) {
        /*分段函数
        f(x)=-x(x<0)
        f(x)=0(x=0)
        f(x)=2x(x>0)
         */
        int x;
        Scanner in = new Scanner(System.in);
        x=in.nextInt();
        if (x < 0) {
            System.out.println("f(x)=" + x * -1);
        }
        else if(x==0){
            System.out.println("f(x)=0");
        }
        else{
            System.out.println("f(x)="+2*x);
        }
    }
}
```

if(){}else if(){}else{}[^18]：级联判断语句

运行程序，输入

```
5
```

输出结果

```
10
```

### 第五个Java程序（分支）

1. 在src新建软件包"Branch"；
2. 在"Branch"软件包里新建Java类"branch"；
3. 在branch.java里写下第五个Java程序；

```Java
package Branch;

import java.util.Scanner;

public class branch {
    public static void main(String[] args) {
        int mark;
        Scanner in = new Scanner(System.in);
        mark=in.nextInt();
        mark=mark/10;
        switch (mark){
            case 10:
                System.out.println(100);
                break;
            case 9:
                System.out.println(9);
                break;
            case 8:
                System.out.println(8);
                break;
            case 7:
                System.out.println(7);
                break;
            case 6:
                System.out.println(6);
                break;
            default:
                System.out.println("不合格");
                break;
        }
    }
}
```

+ switch case[^19]：switch（x)则运行case x后面的程序，直到break

## 第三周Java程序（循环）

### 第一个Java程序（while）

1. 新建Java项目"third Java program"；
2. 在src里新建软件包"Circle"；
3. 在"Circle"软件包里新建Java类"circle"；
4. 在circle.java中写下第一个Java程序；

```java
package Circle;

import java.util.Scanner;

public class circle {
    public static void main(String[] args) {
        int balance=0;
        int amount;
        Scanner in = new Scanner(System.in);
        while (true){
            amount=in.nextInt();
            balance=balance+amount;
            if(balance>=10){
                System.out.println("找余："+(balance-10));
                balance=0;
            }
        }
    }
}
```

+ while(A){B}[^20]：当A成立时，循环运行B

运行程序，输入

```
12
5
8
```

得到结果

```
找余：2
找余：3
```

### 第二个Java程序（do while）

2. 在src里新建软件包"Circledo"；
3. 在"Circledo"软件包里新建Java类"circledo"；
4. 在circledo.java中写下第二个Java程序；

```java
package Circledo;

import java.util.Scanner;

public class circledo {
    public static void main(String[] args) {
        int number;
        int count=0;
        Scanner in = new Scanner(System.in);
        number=in.nextInt();
        do{
            number=number/10;
            count++;
        }while (number>0);
        System.out.println(count);
    }
}
```

+ do{A}while(B)[^21]：做A循环，如果条件B成立，再做一次A循环，再次判断B条件

运行程序，输入

```
573
```

得到结果

```
3
```

### 第三个Java程序（猜数游戏）

1. 在src里新建软件包"Guess"；
2. 在"Guess"软件包里新建Java类"guess"；
3. 在guess.java中写下第三个Java程序；

```java
package Guess;

import java.util.Scanner;

public class guess {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int number=(int)(Math.random()*100+1);
        int a=0;
        int b=100;
        int count=0;
        int guess;
        do{
            System.out.println("从"+a+"到"+b+"猜一个数");
            guess=in.nextInt();
            count++;
            if(guess<number){
                a=guess;
            }else {
                b=guess;
            }
        }while (guess!=number);
        System.out.println("恭喜你猜对了，数字是"+number+"你猜了"+count+"次");
    }
}
```

+ Math.random()[^22]：取一个[0,1)的随机数

运行程序，得到

```
一个猜从1-100的猜数游戏，记录猜数次数
```

## 第四周Java程序（循环控制）

### 第一个Java程序（for循环）

1. 新建Java项目"third Java program"；
2. 在src里新建软件包"Cyclic"；
3. 在"Cyclic"软件包里新建Java类"cyclic"；
4. 在cyclic.java中写下第一个Java程序；

```Java
package Cyclic;

import java.util.Scanner;

public class cyclic {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int number=in.nextInt();
        int i;
        int factor=1;
        for (i=1;i<=number;i++){
            factor*=i;
        }
        System.out.println(number+"!="+factor);
    }
}
```

+ for（A;B;C）{D}[^23]：A为初始条件，B为运行条件，CD为循环程序
+ factor*=i[^24]：可看作factor=factor\*(i)

运行程序，输入

```
3
```

得到结果

```
3！=6
```

### 第二个Java程序（判断素数）

1. 在src里新建软件包"Prime"；
2. 在"Prime"软件包里新建Java类"prime"；
3. 在prime.java中写下第二个Java程序；

```Java
package Prime;

import java.util.Scanner;

public class prime {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        boolean isprime=true;
        int number=in.nextInt();
        int i;
        OUT:
        for(i=2;i<number;i++){
            if(number%i==0){
                isprime=false;
                break OUT;
            }
        }
        if(isprime){
            System.out.println(number+"是素数");
        }else {
            System.out.println(number+"不是素数");
        }
    }
}
```

+ break OUT[^25]：离开OUT标号代表的循环
+ boolean[^26]：定义一个布尔变量，可为true和false
+ !,&&,||[^27]：非，与，或

运行程序，输入

```
13
```

得到结果

```
13是素数
```

## 第五周Java程序（数组）

### 第一个Java程序（数组）

1. 新建Java项目"fifth Java program"；
2. 在src里新建软件包"Array"；
3. 在"Array"软件包里新建Java类"array"；
4. 在array.java中写下第一个Java程序；

```java
package Array;

import java.util.Scanner;

public class array {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int count = in.nextInt();
        int[] group = new int[count];
        for (int i=0;i<group.length;i++){
            group[i]=in.nextInt();
        }
        double sum=0;
        for (int i=0;i<group.length;i++){
            sum += group[i];
        }
        double average = sum/count;
        System.out.println(average);
        for(int i=0;i<group.length;i++){
            if(group[i]>=average){
                System.out.print(group[i]+" ");
            }
        }
    }
}
```

+ int [] group = new int[count]：创建一个数组group，有count个单位
+ group.length：数组group的单位个数

运行程序，输入

```
4
1 2 3 4
```

得到结果

```
2.5
3 4
```

### 第二个Java程序（for-each）

1. 在src里新建软件包"Search"；
2. 在"Search"软件包里新建Java类"search"；
3. 在search.java中写下第二个Java程序；

```java
package Search;

import java.util.Scanner;

public class search {
    public static void main(String[] args) {
        boolean found=false;
        Scanner in = new Scanner(System.in);
        int[] data ={1,2,3,4,5,6,7,8,9,10};
        int x=in.nextInt();
        for(int k:data){
            if(x==k){
                found=true;
                break;
            }
        }
        if(found){
            System.out.println(x+"在其中");
        }else {
            System.out.println(x+"不在其中");
        }
    }
}
```

+ for(int k:data){A}[^28]：定义变量k为data数组中的元素，遍历数组data,执行循环A

运行程序，输入

```
15
```

得到结果

```
15不在其中
```

### 第三个Java程序（素数表）

1. 在src里新建软件包"Primegroup"；
2. 在"Primegroup"软件包里新建Java类"primegroup"；
3. 在primegroup.java中写下第三个Java程序；

```java
package Primegroup;

public class primegroup {
    public static void main(String[] args) {
        int[] prime = new int[10];
        prime[0]=2;
        int count=1;
        LOOP:
        for(int x=3;count<10;x++){
            for (int i=1;i<count;i++){
                if (x%prime[i]==0){
                    continue LOOP;
                }
            }
            prime[count++]=x;
        }
        for (int k:prime){
            System.out.print(k+" ");
        }
    }
}
```

+ continue LOOP[^29]：结束当前LOOP循环，开始下一轮LOOP循环

运行程序，得到结果

```
2 3 4 5 7 11 13 17 19 23
```

### 第四个Java程序（二维数组）

1. 在src里新建软件包"ChessOX"；
2. 在"chessOX"软件包里新建Java类"chessOX"；
3. 在chessOX.java中写下第四个Java程序；

```java
package ChessOX;

import java.util.Scanner;

public class chessOX {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        final int size=3;
        int[][] board = new int[size][size];
        boolean resultO=false;
        boolean resultX=false;
        int numberO=0;
        int numberX=0;
        for (int j=0;j<size;j++){
            for (int k=0;k<size;k++){
                board[j][k]=in.nextInt();
            }
        }
        for (int j=0;j<size;j++){
            for (int k=0;k<size;k++){
                if (board[j][k]==0){
                    numberO++;
                }else {
                    numberX++;
                }
            }
            if(numberO==3){
                resultO=true;
                break;
            }
            if(numberX==3){
                resultX=true;
                break;
            }
        }
        numberO=0;
        numberX=0;
        for (int k=0;k<size;k++){
            for (int j=0;j<size;j++){
                if (board[j][k]==0){
                    numberO++;
                }else {
                    numberX++;
                }
            }
            if(numberO==3){
                resultO=true;
                break;
            }
            if(numberX==3){
                resultX=true;
                break;
            }
        }
        numberO=0;
        numberX=0;
        for (int j=0;j<size;j++){
            if (board[j][j]==0){
                numberO++;
            }else {
                numberX++;
            }
        }
        if(numberO==3){
            resultO=true;
        }
        if(numberX==3){
            resultX=true;
        }
        numberO=0;
        numberX=0;
        for (int j=0;j<size;j++){
            if (board[j][2-j]==0){
                numberO++;
            }else {
                numberX++;
            }
        }
        if(numberO==3){
            resultO=true;
        }
        if(numberX==3){
            resultX=true;
        }
        if(resultO){
            System.out.println("0获胜");
        }
        if(resultX){
            System.out.println("1获胜");
        }
    }
}
```

+ int\[][] board = new int\[a]\[b][^30]：创建二维数组board，有a个元素，每个元素内有b个元素

运行程序，输入

```
0 1 0
1 0 1
0 1 1
```

得到结果

```
0获胜
```

## 第六周Java程序（使用对象）

### 第一个Java程序（单字符变量）

1. 新建Java项目"sixth Java program"；
2. 在src里新建软件包"Character"；
3. 在"Character"软件包里新建Java类"character"；
4. 在character.java中写下第一个Java程序；

```java
package Character;

public class character {
    public static void main(String[] args) {
        char word = 'A';
        final int count = 5;
        for (int i=0;i<count;i++){
            System.out.print(word);
            word += 1;
        }
    }
}
```

运行程序，得到结果

```
ABCDE
```

+ char word = 'A'[^31]：定义单字符变量word为A

### 第二个Java程序（包裹类型）

1. 在src里新建软件包"Parcel"；
2. 在"Parcel"软件包里新建Java类"parcel"；
3. 在parcel.java中写下第二个Java程序；

```java
package Parcel;

public class parcel {
    public static void main(String[] args) {
        System.out.println(Integer.MAX_VALUE);
        System.out.println(Character.isDigit('1'));
        System.out.println(Character.isLowerCase('I'));
        System.out.println(Character.toLowerCase('I'));
    }
}

```

运行程序，得到结果

```
2147483647
true
false
i
```

+ Integer.MAX_VALUE[^32]：显示integer类型的最大值
+ Character.isDigit('1')[^33]：判断'1'是不是十进制数
+ Character.isLowerCase('I')[^34]：判断'I'是不是小写字母
+ Character.toLowerCase('I')[^35]：将'I'变为小写字母

### 第三个Java程序（MATH类）

1. 在src里新建软件包"Mathtype"；
2. 在"Mathtype"软件包里新建Java类"mathtype"；
3. 在mathtype.java中写下第三个Java程序；

```Java
package Mathtype;

public class mathtype {
    public static void main(String[] args) {
        System.out.println(Math.abs(-12));
        System.out.println(Math.round(10.49));
    }
}
```

运行程序，得到结果

```
12
10
```

+ Math.abs(-12)[^36]：求-12的绝对值
+ Math.round(10.49)[^37]：对10.49做四舍五入

### 第四个Java程序（字符串）

1. 在src里新建软件包"Strings"；
2. 在"Strings"软件包里新建Java类"strings"；
3. 在strings.java中写下第四个Java程序；

```Java
package Strings;

public class strings {
    public static void main(String[] args) {
        String word1 = new String("hello");
        String word2 = " world";
        word1 += word2;
        System.out.println(word1);
        System.out.println(word1.equals("hello world"));
    }
}

```

运行程序，得到结果

```
hello world
true
```

+ String word1 = new String("hello")[^38]：定义一个字符串word1，管理内容为"hello"
+ String word2 = " word"[^39]：定义一个字符串word2，管理内容为" word"
+ A.equals("B")[^40]：判断A与B的内容是否相同

## 第七周Java程序（函数）

### 第一个Java程序（定义函数）

1. 新建Java项目"seventh Java program"；
2. 在src里新建软件包"Function"；
3. 在"Function"软件包里新建Java类"function"；
4. 在function.java中写下第一个Java程序；

```Java
package Function;

public class function {
    public static boolean isprime(int i){
        boolean result=true;
        for (int count=2;count<i;count++){
            if((i % count)==0){
                result = false;
                break;
            }
        }
        return result;
    }
    public static void main(String[] args) {
        System.out.print(2);
        for(int number = 3;number<50;number++){
            if(isprime(number)){
                System.out.print(" "+number);
            }
        }
    }
}
```

运行程序，得到结果

```
2 3 5 7 11 13 17 19 23 29 31 37 41 43 47
```

+ public static boolean isprime(int i)[^41]：定义函数名为isprime，输入值为整数变量，输出值为布尔变量
+ isprime(number)：调用自己定义的函数isprime

==PS==：函数传递过程为值，并非参数本身

## Java编程语言

[^1]:package
[^2]:public class
[^3]:public static  void main
[^4]:String[] args
[^5]:System.out.println
[^6]:import java.util.Scanner
[^7]:Scanner in = new Scanner(System.in)
[^8]:final int number
[^9]:int xxxxxxx
[^10]:System.out.print
[^11]:xxxxx=in.nextInt()
[^12]:double xxxxxx
[^13]:xxxxxx=in.nextDouble
[^14]:(int)(xxxxx)
[^15]:Math.abs()
[^16]:<,>,<=,>=,==,!=
[^17]:if(){}else{}
[^18]:if(){}else if(){}else{}
[^19]:switch case
[^20]:while(){}

[^21]:do{}while()

[^22]:Math.random()
[^23]:for（;;）{}
[^24]:*=

[^25]:break
[^26]:boolean
[^27]:!,&&,||

[^28]:for-each
[^29]:continue
[^30]:int\[][] xxxx = new int\[][]

[^31]:char xxxxxxxx

[^32]:Integer.MAX_VALUE
[^33]:Character.isDigit()
[^34]:Character.isLowerCase()
[^35]:Character.toLowerCase()

[^36]:Math.abs
[^37]:Math.round
[^38]:String xxxxxx = new String("")
[^39]:String xxxxxx = ""
[^40]:A.equals("B")

[^41]:public static xxxxxx yyyyy(zzzzz);
