# C++

## 01 Hello World

### 01 Hello World

```c++
#include<iostream>
using namespace std;

int main() {
	cout << "hello world" << endl;

	system("pause");

	return 0;
}
```



### 02 注释

```c++
#include<iostream>
using namespace std;

//单行注释

/*
* 多行注释
*/

int main() {

	return 0;
}
```



### 03 变量

```c++
#include<iostream>
using namespace std;

int main() {
	int a = 10;

	cout << "a = " << a << endl;

	return 0;
}
```



### 04 常量

```c++
#include<iostream>
using namespace std;

//1、#define 宏常量
#define Day 7

//2、const 修饰的变量
const int mouth = 12;

int main() {
	cout << "一周一共有：" << Day << "天" << endl;
	cout << "一年一共有：" << mouth << "月" << endl;

	return 0;
}
```



### 05 关键字

```c++
#include<iostream>
using namespace std;

//关键字不能作为变量名

int main() {

	return 0;
}
```



### 06 标识符命名规则

```c++
#include<iostream>
using namespace std;

//标识符命名规则
/*
* 1、标识符不可以是关键字
* 2、标识符是由字母、数字、下划线构成
* 3、标识符第一个字符只能是是字母和下划线
* 4、标识符是区分大小写的
*/
int main() {

	return 0;
}
```



## 02 数据类型

### 01 整型

```c++
#include<iostream>
using namespace std;

int main() {
	//整形
	//1、短整型（-32768 ~ 32767）
	short num1 = 32768;

	//2、整型
	int num2 = 32768;

	//3、长整形
	long num3 = 10;

	//4、长长整型
	long long num4 = 10;

	cout << "num1 = " << num1 << endl;
	cout << "num2 = " << num2 << endl;
	cout << "num3 = " << num3 << endl;
	cout << "num4 = " << num4 << endl;

	return 0;
}
```



### 02 sizeof关键字

```c++
#include<iostream>
using namespace std;

int main() {
	short num1 = 10;
	cout << "short占用内存空间为：" << sizeof(short) << endl;
	cout << "num1占用内存空间为：" << sizeof(num1) << endl;

	int num2 = 10;
	cout << "int占用内存空间为：" << sizeof(int) << endl;
	cout << "num2占用内存空间为：" << sizeof(num2) << endl;

	return 0;
}
```



### 03 实型（浮点型）

```c++
#include<iostream>
using namespace std;

int  main() {
	//1、单精度float
	float f1 = 3.1415926f;
	cout << "f1 = " << f1 << endl;

	//2、双精度double
	double d2 = 3.1415926;
	cout << "d2 = " << d2 << endl;

	//科学计数法
	float f2 = 3e2;
	cout << "f2 = " << f2 << endl;
	float f3 = 3e-2;
	cout << "f3 = " << f3 << endl;

	return 0;
}
```



### 04 字符型

```c++
#include<iostream>
using namespace std;

int main() {
	//字符串变量创建方式
	char ch = 'a';
	cout << ch << endl;

	//字符型变量所占内存大小
	cout << "char字符型变量所占内存：" << sizeof(char) << endl;

	//字符串常见错误
	//1、创建字符串变量要用单引号
	//2、创建字符串变量单引号内只能有一个字符

	//字符串变量对应ASCII编码
	cout << "a的ASCII编码是" << (int)'a' << endl;
	cout << "A的ASCII编码是" << (int)'A' << endl;

	return 0;
}
```



### 05 转义字符

```c++
#include<iostream>
using namespace std;

int main() {
	//转义字符
	
	//换行符 \n
	
	cout << "Hello\nWolrd" << endl;

	//反斜杠 \\

	cout << "Hello\\World" << endl;

	//水平制表符 \t

	cout << "123\tHello" << endl;
	cout << "1234\tWorld" << endl;

	return 0;
}
```



### 06 字符串型

```c++
#include<iostream>
#include<string.h>//用C++风格字符串包含该头文件
using namespace std;

int main() {
	//1、C风格字符串
	char str[] = "Hello World";
	cout << str << endl;

	//2、C++风格字符串
	string str2 = "Hello World";
	cout << str2 << endl;

	return 0;
}
```



### 07 布尔类型

```c++
#include<iostream>
using namespace std;

int main() {
	//1、创建bool数据类型
	bool flag = true;
	cout << flag << endl;
	flag = false;
	cout << flag << endl;

	//2、bool类型占用内存空间
	cout << sizeof(bool) << endl;
	return 0;
}
```



### 08 数据的输入

```c++
#include<iostream>
#include<string.h>
using namespace std;

int  main() {
	//1、整型
	int a = 0;
	cout << "请给整型变量a赋值：" << endl;
	cin >> a;
	cout <<"a = " << a << endl;

	//2、浮点型
	float f = 3.14f;
	cout << "请给浮点型变量f赋值：" << endl;
	cin >> f;
	cout << "f = " << f << endl;

	//3、字符型
	char ch = 'a';
	cout << "请给字符型变量ch赋值：" << endl;
	cin >> ch;
	cout << "ch = " << ch << endl;

	//4、字符串
	string str = "hello";
	cout << "请给字符串变量str赋值：" << endl;
	cin >> str;
	cout << "s = " << str << endl;

	//5、布尔类型
	bool flag = false;
	cout << "请给布尔类型flag赋值:" << endl;
	cin >> flag;
	cout << "flag = " << flag << endl;

	return 0;
}
```



## 03 运算符

### 01 算数运算符-加减乘除

```c++
#include<iostream>
using namespace std;

int main() {
	//加减乘除
	int a = 10;
	int b = 3;

	cout << a + b << endl;
	cout << a - b << endl;
	cout << a * b << endl;
	cout << a / b << endl;
	cout << a * 1.0 / b << endl;

	//取余
	cout << a % b << endl;

	return 0;
}
```



### 02 算数运算符-取模（取余）

```c++
#include<iostream>
using namespace std;

int main() {
	//取余
	int a = 10;
	int b = 3;

	cout << a % b << endl;

	b = 20;
	cout << a % b << endl;

	return 0;
}
```



### 03 算数运算符-递增递减

```c++
#include<iostream>
using namespace std;

int main() {
	//1、前置递增
	int a = 10;
	++a;
	cout << "a = " << a << endl;

	//2、后置递增
	int b = 10;
	b++;
	cout << "b = " << b << endl;

	//3、前置后置区别
	int a1 = 10;
	int b1 = ++a1;
	cout << "a1 = " << a1 << endl;
	cout << "b1 = " << b1 << endl;

	int a2 = 10;
	int b2 = a2++;
	cout << "a2 = " << a2 << endl;
	cout << "b2 = " << b2 << endl;

	return 0;
}
```



### 04 赋值运算符

```c++
#include<iostream>
using namespace std;

int main() {
	//赋值运算符
	int a = 10;

	// =
	a = 100;
	cout << "a = " << a << endl;

	// +=
	a = 10;
	a += 2;
	cout << "a = " << a << endl;

	// -=
	a = 10;
	a -= 2;
	cout << "a = " << a << endl;

	// *=
	a = 10;
	a *= 2;
	cout << "a = " << a << endl;

	// /=
	a = 10;
	a /= 2;
	cout << "a = " << a << endl;

	// %=
	a = 10;
	a %= 2;
	cout << "a = " << a << endl;

	return 0;
}
```



### 05 比较运算符

```c++
#include<iostream>
using namespace std;

int main() {
	//比较运算符
	int a = 10;
	int b = 20;

	//==
	cout << (a == b) << endl;

	//>=
	cout << (a >= b) << endl;

	//<=
	cout << (a <= b) << endl;

	//!=
	cout << (a != b) << endl;

	//>
	cout << (a > b) << endl;

	//<
	cout << (a < b) << endl;

	return 0;
}
```



### 06 逻辑运算符-非

```c++
#include<iostream>
using namespace std;

int main() {
	//逻辑运算符 非
	int a = 10;

	cout << !a << endl;
	cout << !!a << endl;

	return 0;
}
```



### 07 逻辑运算符-与

```c++
#include<iostream>
using namespace std;

int main() {
	//逻辑运算符 与
	int a = 10;
	int b = 10;

	cout << (a && b) << endl;

	a = 0;
	cout << (a && b) << endl;

	return 0;
}
```



### 08 逻辑运算符-或

```c++
#include<iostream>
using namespace std;

int main() {
	//逻辑运算符 或
	int a = 10;
	int b = 10;

	cout << (a || b) << endl;

	a = 0;
	cout << (a || b) << endl;

	b = 0;
	cout << (a || b) << endl;

	return 0;
}
```



## 04 程序流程结构

### 01 选择结构-单行if语句

```c++
#include<iostream>
using namespace std;

int main() {
	//选择结构 单行if语句
	int score = 0;
	cin >> score;

	cout << score << endl;
	if (score > 600) {
		cout << "一本" << endl;
	}

	return 0;
}
```



### 02 选择结构-多行if语句

```c++
#include<iostream>
using namespace std;

int main() {
	//选择结构-多行if语句
	int score = 0;
	cin >> score;

	if (score > 600) {
		cout << "一本" << endl;
	}else{
		cout << "不是一本" << endl;
	}

	return 0;
}
```



### 03 选择结构-多条件if语句

```c++
#include<iostream>
using namespace std;

int main() {
	int score = 0;
	cin >> score;

	if (score > 600) {
		cout << "一本" << endl;
	}else if (score > 500) {
		cout << "二本" << endl;
	}else if (score > 400) {
		cout << "三本" << endl;
	}else {
		cout << "没考上" << endl;
	}

	return 0;
}
```



### 04 选择结构-嵌套if语句

```c++
#include<iostream>
using namespace std;

int main() {
	int score = 0;
	cin >> score;

	if (score > 600) {
		if (score > 700) {
			cout << "清华" << endl;
		}else {
			cout << "北大" << endl;
		}
	}
	return 0;
}
```



### 05 选择结构-三个谁输出最大数

```c++
#include<iostream>
using namespace std;

int main() {
	int num1 = 0;
	int num2 = 0;
	int num3 = 0;

	cin >> num1;
	cin >> num2;
	cin >> num3;

	if (num1 > num2) {
		if (num1 > num3) {
			cout << num1 << endl;
		}else {
			cout << num3 << endl;
		}
	}else {
		if (num2 > num3) {
			cout << num2 << endl;
		}else {
			cout << num3 << endl;
		}
	}

	return 0;
}
```



### 06 选择结构-三目运算符

```c++
#include<iostream>
using namespace std;

int main() {
	int a = 0;
	int b = 0;

	cin >> a;
	cin >> b;

	cout << (a > b ? a : b) << endl;

	(a > b ? a : b) = 100;
	cout << "a = " << a << endl;
	cout << "b = " << b << endl;

	return 0;
}
```



### 07 选择结构-switch语句

```c++
#include<iostream>
using namespace std;

int main() {
	int n;
	cin >> n;

	switch (n)
	{
	case 10:
	case 9:
		cout << "经典" << endl;
		break;
	case 8:
	case 7:
		cout << "非常好" << endl;
		break;
	case 6:
	case 5:
		cout << "一般" << endl;
		break;
	default:
		cout << "烂" << endl;
		break;
	}

	return 0;
}
```



### 08 循环结构-while循环

```c++
#include<iostream>
using namespace std;

int main() {
	int n = 0;
	while (n < 10) {
		cout << n << endl;
		n++;
	}

	return 0;
}
```



### 09 猜数字

```c++
#include<iostream>
using namespace std;

int main() {
	int num = rand() % 10 + 1;
	cout << num << endl;

	int val = 0;
	cin >> val;
	while (num != val) {
		if (val > num) {
			cout << "大了" << endl;
		}else {
			cout << "小了" << endl;
		}
		cin >> val;
	}
	cout << "对了" << endl;

	return 0;
}
```



### 10 循环结构-dowhile循环

```c++
#include<iostream>
using namespace std;

int main() {
	int num = 0;
	do
	{
		cout << num << endl;
		num++;
	} while (num < 10);

	do
	{
		cout << num << endl;
		num++;
	} while (num < 1);
	return 0;
}
```



### 11 水仙花数

```c++
#include<iostream>
using namespace std;

int main() {
	int num = 100;

	do
	{
		int a = num % 10;
		int b = num / 10 % 10;
		int c = num / 100;

		if (a * a * a + b * b * b + c * c * c == num)
		{
			cout << num << endl;
		}

		num++;
	} while (num < 1000);

	return 0;
}
```



### 12 循环结构-for循环

```c++
#include<iostream>
using namespace std;

int main() {
	for (int i = 0; i < 10; i++)
	{
		cout << i << endl;
	}

	return 0;
}
```



### 13 敲桌子

```c++
#include<iostream>
using namespace std;

int main() {
	for (int i = 1; i <= 100; i++)
	{
		if (1 % 7 == 0 || i % 10 == 7 || i / 10 == 7)
		{
			cout << i << endl;
		}
	}

	return 0;
}
```



### 14 嵌套循环

```c++
#include<iostream>
using namespace std;

int main() {
	for (int i = 0; i < 10; i++)
	{
		for (int j = 0; j < 10; j++)
		{
			cout << "* ";
		}
		cout << endl;
	}

	return 0;
}
```



### 15 乘法口诀表

```c++
#include<iostream>
using namespace std;

int main() {
	for (int i = 1; i <= 9; i++)
	{
		for (int j = 1; j <= i; j++)
		{
			cout << i << "*" << j << "=" << i * j << " ";
		}
		cout << endl;
	}

	return 0;
}
```



### 16 跳转语句-break语句

```c++
#include<iostream>
using namespace std;

int main() {
	//break的使用时机
	//1、出现在switch语句中

	//2、出现在循环语句中
	for (int i = 0; i < 10; i++) {
		cout << i;
		if (i == 5)
		{
			break;
		}
	}
	cout << endl;

	//3、出现在嵌套循环中
	for (int i = 0; i < 10; i++) {
		for (int j = 0; j < 10; j++) {
			cout << j;
			if (j == 4)
			{
				break;
			}
		}
		cout << endl;
	}

	return 0;
}
```



### 17 跳转语句-continue语句

```c++
#include<iostream>
using namespace std;

int main() {
	for (int i = 0; i < 10; i++) {
		if (i % 2 == 0)
		{
			continue;
		}
		cout << i << endl;
	}

	return 0;
}
```



### 18 跳转语句-goto语句

```c++
#include<iostream>
using namespace std;

int main() {
	cout << "1.xxxx" << endl;
	cout << "2.xxxx" << endl;
	goto FLAG;
	cout << "3.xxxx" << endl;
	cout << "4.xxxx" << endl;
	FLAG:
	cout << "5.xxxx" << endl;

	return 0;
}
```



## 05 数组

### 01 一维数组-定义

```c++
#include<iostream>
using namespace std;

int main() {
	int arr[5];
	int arr2[] = { 1,2,3,4 };
	for (int i = 0; i < 5; i++)
	{
		arr[i] = i * 10;
	}

	for (int i = 0; i < 5; i++) {
		cout << arr[i] << endl;
	}

	return 0;
}
```



### 02 一维数组-数组名

```c++
#include<iostream>
using namespace std;

int main() {
	//数组名用途
	//1、查看整个数组占用内存大小
	int arr[5] = { 1,2,3,4,5 };
	cout << "整个数组占用内存：" << sizeof(arr) << endl;
	cout << "每个元素占用内存：" << sizeof(arr[0]) << endl;
	cout << "数组元素个数为" << sizeof(arr) / sizeof(arr[0]) << endl;

	//2、查看数组首地址
	cout << "数组首地址：" << (int)arr << endl;
	cout << "数组第一个元素地址：" << (int)&arr[0] << endl;
	cout << "数组第二个元素地址：" << (int)&arr[1] << endl;

	//数组名是常量，不可以进行赋值操作

	return 0;
}
```



### 03 五个数找出最大值

```c++
#include<iostream>
using namespace std;

int main() {
	int max = 0;
	int arr[5] = { 2,4,6,7,1 };
	for (int i = 0; i < 5; i++)
	{
		if (max < arr[i])
		{
			max = arr[i];
		}
	}
	cout << max << endl;

	return 0;
}
```



### 04 数组元素逆置

```c++
#include<iostream>
using namespace std;

int main() {
	int arr[] = { 1,2,3,4,5 };
	for (int i = 0; i < 5; i++)
	{
		cout << arr[i];
	}
	cout << endl;

	int start = 0;
	int end = sizeof(arr) / sizeof(arr[0]) - 1;

	while (start < end)
	{
		int flag = arr[start];
		arr[start] = arr[end];
		arr[end] = flag;

		start++;
		end--;
	}
	
	for (int i = 0; i < 5; i++)
	{
		cout << arr[i];
	}

	return 0;
}
```



### 05 冒泡排序

```c++
#include<iostream>
using namespace std;

int main() {
	int a[9] = { 4,2,8,0,5,7,1,3,9 };

	for (int i = 0; i < 9; i++)
	{
		cout << a[i] << " ";
	}
	cout << endl;

	for (int i = 8;i > 0; i--)
	{
		for (int j = 0; j < i; j++)
		{
			if (a[j] > a[j + 1])
			{
				int flag = a[j];
				a[j] = a[j + 1];
				a[j + 1] = flag;
			}
		}
	}

	for (int i = 0; i < 9; i++)
	{
		cout << a[i] << " ";
	}
	cout << endl;

	return 0;
}
```



### 06 二维数组-定义

```c++
#include<iostream>
using namespace std;

int main() {
	//二维数组的定义
	int arr1[2][3];
	int arr2[2][3] = { {1,2,3},{4,5,6} };
	int arr3[2][3] = { 1,2,3,4,5,6 };
	int arr4[][3] = { 1,2,3,4,5,6 };

	return 0;
}
```



### 07 二维数组-数组名

```c++
#include<iostream>
using namespace std;

int main() {
	//二维数组名用途
	int arr[2][3] = { {1,2,3},{4,5,6} };

	//1、可以查看占用内存空间大小
	cout << "二维数组占用的内存：" << sizeof(arr) << endl;
	cout << "二维数组一行占用的内存：" << sizeof(arr[0]) << endl;
	cout << "二维数组一个元素占用的内存：" << sizeof(arr[0][0]) << endl;

	cout << "二维数组行数：" << sizeof(arr) / sizeof(arr[0]) << endl;
	cout << "二维数组列数：" << sizeof(arr[0]) / sizeof(arr[0][0]) << endl;

	//2、可以查看二维数组首地址
	cout << "二维数组首地址：" << (int)arr << endl;
	cout << "二维数组第一行首地址" << (int)arr[0] << endl;
	cout << "二维数组第一个元素首地址" << (int)&arr[0][0] << endl;


	return 0;
}
```



### 08 考试成绩统计

```c++
#include<iostream>
#include<string.h>
using namespace std;

int main() {
	int scores[3][3] = { {100,100,100},{90,50,100},{60,70,80} };
	string names[3] = { "张三","李四","王五" };

	for (int i = 0; i < 3; i++)
	{
		int sum = 0;
		for (int j = 0; j < 3; j++)
		{
			sum += scores[i][j];
			cout << scores[i][j] << " ";
		}
		cout << names[i] << "的总分为：" << sum << endl;
	}

	return 0;
}
```



## 06 函数

### 01 函数的定义

```c++
#include<iostream>
using namespace std;

int sum(int num1, int num2) {
	int sum = num1 + num2;
	return sum;
}

int main() {

	return 0;
}
```



### 02 函数的调用

```c++
#include<iostream>
using namespace std;

int add(int num1, int num2) {
	int sum = num1 + num2;
	return sum;
}

int main() {
	int a = 10;
	int b = 20;

	int c = add(a, b);
	cout << c << endl;

	return 0;
}
```



### 03 函数-值传递

```c++
#include<iostream>
using namespace std;

void swap(int num1, int num2) {
	cout << "交换前：" << num1 << " " << num2 << endl;
	
	int temp = num1;
	num1 = num2;
	num2 = temp;

	cout << "交换后：" << num1 << " " << num2 << endl;
}

int main() {
	int a = 1;
	int b = 2;
	swap(a, b);

	cout << "交换后：" << a << " " << b << endl;

	return 0;
}
```



### 04 函数-常见样式

```c++
#include<iostream>
using namespace std;

//1、无参无返
void test01() {

}

//2、有参无返
void test02(int a) {

}

//3、无参有返
int test03() {
	return 0;
}

//4、有参有返
int test04(int a) {
	return 0;
}

int main() {

	return 0;
}
```



### 05 函数的声明

```c++
#include<iostream>
using namespace std;

//声明可以有多次，定义只能有一次

//声明
int max(int a, int b);

int main() {
	int a = 10;
	int b = 20;

	cout << max(a, b) << endl;

	return 0;
}
//定义
int max(int a, int b) {
	return a > b ? a : b;
}
```



### 06 函数的分文件编写

swap.h（头文件）

```c++
#include<iostream>
using namespace std;

//声明
void swap1(int a, int b);
```

swap.cpp（源文件）

```c++
#include"06 swap.h"

//定义
void swap1(int a, int b) {
	int temp = a;
	a = b;
	b = temp;
	cout << a << " " << b << endl;
}
```

函数的分文件编写.cpp（源文件）

```c++
#include<iostream>
using namespace std;

#include"06 swap.h"

int main() {
	int a = 10;
	int b = 20;
	swap1(a, b);

	return 0;
}
```



## 07 指针

### 01 指针的定义和使用

```c++
#include<iostream>
using namespace std;

int main() {
	int a = 10;
	int* p;

	p = &a;

	cout << "a的指针：" << &a << endl;
	cout << "指针p：" << p << endl;

	*p = 1000;

	cout << "a = " << a << endl;
	cout << "*p = " << *p << endl;

	return 0;
}
```



### 02 指针所占内存空间

```c++
#include<iostream>
using namespace std;

int main() {
	int a = 10;
	int* p = &a;

	cout << "sizeof(int *) = " << sizeof(int*) << endl;
	cout << "sizeof(float *) = " << sizeof(float*) << endl;
	cout << "sizeof(double *) = " << sizeof(double*) << endl;
	cout << "sizeof(char *) = " << sizeof(char*) << endl;

	return 0;
}
```



### 03 空指针

```c++
#include<iostream>
using namespace std;

int main() {
	//空指针
	//1、空指针用于给指针变量初始化
	int* p = NULL;

	//2、空指针不可以进行访问

	return 0;
}
```



### 04 野指针

```c++
#include<iostream>
using namespace std;

int main() {
	//野指针
	int* p = (int*)0x1100;

	return 0;
}
```



### 05 const修饰指针

```c++
#include<iostream>
using namespace std;

int main() {
	int a = 10;
	int b = 20;

	//1、const修饰指针
	const int* p = &a;
	//*p = 20;错误
	p = &b;
	cout << *p << endl;

	//2、const修饰常量
	int* const p2 = &a;
	*p2 = 100;
	//p2 = &b;错误
	cout << *p2 << endl;

	const int* const p3 = &a;
	//*p3 = 100;错误
	//p3 = &b;错误

	return 0;
}
```



### 06 指针和数组

```c++
#include<iostream>
using namespace std;

int main() {
	int arr[10] = { 1,2,3,4,5,6,7,8,9,0 };

	int* p = arr;

	cout << arr[0] << " " << *p << endl;

	p++;
	cout << *p << endl;

	cout << "指针遍历" << endl;

	int* p2 = arr;
	for (int i = 0; i < 10; i++) {
		cout << *p2 << endl;
		p2++;
	}

	return 0;
}
```



### 07 指针和函数

```c++
#include<iostream>
using namespace std;

void swap01(int a,int b) {
	int temp = a;
	a = b;
	b = temp;
}

void swap02(int* p1, int* p2) {
	int temp = *p1;
	*p1 = *p2;
	*p2 = temp;
}

int main() {
	int a = 10;
	int b = 20;
	
	swap01(a, b);
	cout << a << " " << b << endl;

	swap02(&a, &b);
	cout << a << " " << b << endl;

	return 0;
}
```



### 08 冒泡排序函数

```c++
#include<iostream>
using namespace std;

void bubbleSort(int* arr,int len){
	for (int i = 0; i < len - 1; i++)
	{
		for (int j = 0; j < len - i - 1; j++)
		{
			if (arr[j] > arr[j + 1])
			{
				int temp = arr[j];
				arr[j] = arr[j + 1];
				arr[j + 1] = temp;
			}
		}
	}
}

void printArray(int* arr, int len) {
	for (int i = 0; i < len; i++)
	{
		cout << arr[i] << endl;
	}
}

int main() {
	int arr[10] = { 4,3,6,8,1,2,10,8,7,5 };
	int len = sizeof(arr) / sizeof(arr[0]);

	bubbleSort(arr, len);
	printArray(arr, len);

	return 0;
}
```



## 08 结构体

### 01 结构体的定义和使用

```c++
#include<iostream>
#include<string.h>
using namespace std;

struct Student
{
	string name;
	int age;
	int score;
};

int main() {
	struct Student s1;
	s1.name = "张三";
	s1.age = 18;
	s1.score = 100;
	cout << s1.name << " " << s1.age << " " << s1.score << endl;

	struct Student s2 = { "李四",19,90 };
	cout << s2.name << " " << s2.age << " " << s2.score << endl;

	Student s3;

	return 0;
}
```



### 02 结构体数组

```c++
#include<iostream>
#include<string.h>
using namespace std;

struct Student
{
	string name;
	int age;
	int score;
};

int main() {
	struct Student stuArr[3] =
	{
		{"张三",18,100},
		{"李四",19,80},
		{"王五",20,90}
	};

	stuArr[2].age = 18;

	for (int i = 0; i < 3; i++) {
		cout << stuArr[i].name << " " << stuArr[i].age << " " << stuArr[i].score << endl;
	}

	return 0;
}
```



### 03 结构体指针

```c++
#include<iostream>
#include<string.h>
using namespace std;

struct Student
{
	string name;
	int age;
	int score;
};

int main() {
	Student S = { "张三",18,100 };
	Student* p = &S;

	cout << p->name << " " << p->age << " " << p->score << endl;

	return 0;
}
```



### 04 结构体嵌套结构体

```c++
#include<iostream>
#include<string.h>
using namespace std;

struct student {
	string name;
	int age;
	int score;
};

struct teacher {
	int id;
	string name;
	int age;
	struct student stu;
};

int main() {
	teacher t;
	t.id = 10000;
	t.name = "老王";
	t.age = 50;
	t.stu.name = "张三";
	t.stu.age = 18;
	t.stu.score = 100;

	cout << t.name << " " << t.stu.name << endl;

	return 0;
}
```



### 05 结构体做函数参数

```c++
#include<iostream>
#include<string.h>
using namespace std;

struct student
{
	string name;
	int age;
	int score;
};

void printStudent(student s) {
	cout << s.name << " " << s.age << " " << s.score << endl;
}

void printStudent2(student* p) {
	cout << p->name << " " << p->age << " " << p->score << endl;
}

int main() {
	student s = { "张三",18,100 };

	printStudent(s);

	student* p = &s;
	printStudent2(p);

	return 0;
}
```



### 06 结构体const使用场景

```c++
#include<iostream>
#include<string.h>
using namespace std;

struct student
{
	string name;
	int age;
	int score;
};

//防止修改操作
void printStudent3(const student* p) {
	cout << p->name << " " << p->age << " " << p->score << endl;
}

int main() {
	student s = { "张三",18,100 };

	printStudent3(&s);

	return 0;
}
```



### 07 结构体案例

```c++
#include<iostream>
#include<string.h>
using namespace std;

struct student {
	string name;
	int score;
};

struct teacher1 {
	string name;
	student sArr[5];
};

void allocatSpace(teacher1* tArr,int len){
	string nameSeed = "ABCDE";
	for (int i = 0; i < len; i++)
	{
		tArr[i].name = "Teacher_";
		tArr[i].name += nameSeed[i];

		for (int j = 0; j < 5; j++)
		{
			tArr[i].sArr[j].name = "Student_";
			tArr[i].sArr[j].name += nameSeed[j];

			tArr[i].sArr[j].score = 60;
		}
	}
}

void printInfo(teacher1 tArr[], int len) {
	for (int i = 0; i < len; i++)
	{
		cout << "老师姓名：" << tArr[i].name << endl;
		for (int j = 0; j < 5; j++)
		{
			cout << "学生名字：" << tArr[i].sArr[j].name <<
				"考试分数：" << tArr[i].sArr[j].score << endl;
		}
	}
}

int main() {
	teacher1 tArr[3];
	teacher1* p = tArr;
	int len = sizeof(tArr) / sizeof(tArr[0]);


	allocatSpace(p, len);
	printInfo(tArr, len);

	return 0;
}
```



### 08 结构体案例2

```c++
#include<iostream>
#include<string.h>
using namespace std;

struct hero {
	string name;
	int age;
};

void bubbleSort(struct hero heroArray[], int len) {
	for (int i = 0; i < len - 1; i++)
	{
		for (int j = 0; j < len - i - 1; j++)
		{
			if (heroArray[j].age > heroArray[j + 1].age)
			{
				hero temp = heroArray[j];
				heroArray[j] = heroArray[j + 1];
				heroArray[j + 1] = temp;
			}
		}
	}
}

int main() {
	hero heroArray[5] = { {"刘备",23},{"关羽",22},{"张飞",20}, {"赵云",21},{"貂蝉",19} };
	int len = sizeof(heroArray) / sizeof(heroArray[0]);

	for (int i = 0; i < len; i++) {
		cout << "名字" << heroArray[i].name << " 年龄：" << heroArray[i].age << endl;
	}
	cout << endl;

	bubbleSort(heroArray, len);

	for (int i = 0; i < len; i++) {
		cout << "名字" << heroArray[i].name << " 年龄：" << heroArray[i].age << endl;
	}

	return 0;
}
```



## 09 通讯录管理系统

```c++
#include<iostream>
#include<string.h>
using namespace std;
#define MAX 100

struct person{
	string name;
	string phone;
};

struct books{
	person arr[MAX];
	int size;
};

//显示菜单
void showMenu(){
	cout << "*************************" << endl;
	cout << "***** 1、添加联系人 *****" << endl;
	cout << "***** 2、显示联系人 *****" << endl;
	cout << "***** 3、删除联系人 *****" << endl;
	cout << "***** 4、查找联系人 *****" << endl;
	cout << "***** 5、修改联系人 *****" << endl;
	cout << "***** 6、清空联系人 *****" << endl;
	cout << "***** 0、退出通讯录 *****" << endl;
	cout << "*************************" << endl;
}

//添加联系人
void addPerson(books* abs) {
	if (abs->size == MAX)
	{
		cout << "通讯录已满" << endl;
		return;
	}
	else
	{
		cout << "请输入名字" << endl;
		cin >> abs->arr[abs->size].name;

		cout << "请输入电话" << endl;
		cin >> abs->arr[abs->size].phone;

		cout << "添加成功" << endl;

		abs->size++;
	}
	system("pause");
	system("cls");
}

//显示联系人
void showPerson(books* abs) {
	if (abs->size == 0)
	{
		cout << "当前通讯录为空" << endl;
	}
	else
	{
		for (int i = 0; i < abs->size; i++)
		{
			cout << "姓名：" << abs->arr[i].name << "\t电话：" << abs->arr[i].phone << endl;
		}
	}
	system("pause");
	system("cls");
}

//检测联系人是否存在
int isExist(books* abs, string name) {
	for (int i = 0; i < abs->size; i++)
	{
		if (abs->arr[i].name == name)
		{
			return i;
		}
	}
	return -1;
}

//删除联系人
void deletePerson(books* abs) {
	cout << "输入您需要删除的联系人" << endl;

	string name;
	cin >> name;

	int ret = isExist(abs, name);
	if (ret != -1)
	{
		for (int i = ret; i < abs->size; i++) {
			abs->arr[i] = abs->arr[i + 1];
		}
		abs->size--;

		cout << "删除成功" << endl;
	}
	else
	{
		cout << "查无此人" << endl;
	}

	system("pause");
	system("cls");
}

//查找联系人
void findPerson(books* abs) {
	cout << "请输入您需要查找的联系人" << endl;
	string name;
	cin >> name;

	int ret = isExist(abs, name);
	if (ret != -1)
	{
		cout << "姓名：" << abs->arr[ret].name << "\t电话：" << abs->arr[ret].phone << endl;
	}
	else
	{
		cout << "查无此人" << endl;
	}

	system("pause");
	system("cls");
}

//修改联系人
void modifyPerson(books* abs) {
	cout << "请输入您需要修改的联系人" << endl;
	string name;
	cin >> name;

	int ret = isExist(abs, name);

	if (ret != -1)
	{
		cout << "请输入名字" << endl;
		cin >> abs->arr[ret].name;

		cout << "请输入电话" << endl;
		cin >> abs->arr[ret].phone;

		cout << "修改成功" << endl;
	}
	else
	{
		cout << "查无此人" << endl;
	}

	system("pause");
	system("cls");
}

//清空联系人
void clearPerson(books* abs) {
	abs->size = 0;
	cout << "通讯录已清空" << endl;

	system("pause");
	system("cls");
}

int main() {
	books abs;
	abs.size = 0;

	int select = 0;

	while (true)
	{
		showMenu();
		cin >> select;

		switch (select)
		{
		case 1://1、添加联系人
			addPerson(&abs);
			break;
		case 2://2、显示联系人
			showPerson(&abs);
			break;
		case 3://3、删除联系人
			deletePerson(&abs);
			break;
		case 4://4、查找联系人
			findPerson(&abs);
			break;
		case 5://5、修改联系人
			modifyPerson(&abs);
			break;
		case 6://6、清空联系人
			clearPerson(&abs);
			break;
		case 0://0、退出通讯录
			cout << "欢迎下次使用" << endl;
			system("pause");
			return 0;
			break;
		default:
			break;
		}
	}

	return 0;
}
```



## 10 引用

### 01 引用的基本语法

```c++
#include<iostream>
using namespace std;

int main() {
	int a = 10;

	int& b = a;

	cout << "a = " << a << endl;
	cout << "b= " << b << endl;

	b = 20;

	cout << "a = " << a << endl;
	cout << "b= " << b << endl;

	return 0;
}
```



### 02 引用的注意事项

```c++
#include<iostream>
using namespace std;

int main() {
	//1、引用必须初始化
	//int &b;错误

	//2、引用在初始化之后，不可以改变
	//int a = 10;
	//int &b = a;
	//int c = 20;
	//b = c;将20赋值给了a和b

	return 0;
}
```



### 03 引用做函数参数

```c++
#include<iostream>
using namespace std;

void swap(int& a, int& b) {
	int temp = a;
	a = b;
	b = temp;
}

int main() {
	int a = 10;
	int b = 20;

	swap(a, b);

	cout << a << " " << b << endl;

	return 0;
}
```



### 04 引用作函数返回值

```c++
#include<iostream>
using namespace std;

//1、不要返回局部变量的引用
int& test01() {
	int a = 10;
	return a;
}

//2、函数调用可以作为左值
int& test02() {
	static int a = 10;
	return a;
}

int main() {
	int& a = test01();

	cout << a << endl;//10
	cout << a << endl;//乱码

	int& b = test02();

	cout << b << endl;//10
	cout << b << endl;//10
	
	test02() = 100;

	cout << b << endl;//100
	cout << b << endl;//100

	return 0;
}
```



### 05 引用的本质

```c++
#include<iostream>
using namespace std;

int main() {
	//引用的本质就是指针常量
	//但是所有的指针操作由编译器操作

	return 0;
}
```



### 06 常量引用

```c++
#include<iostream>
using namespace std;

void showValue(const int& val) {
	//val = 1000;错误
	cout << "val = " << val << endl;
}

int main() {
	//常量引用
	//使用场景：用来修饰形参，防止误操作

	//引用必须引一块合法的内存空间
	//int& ref = 10;错误
	const int& ref = 10;
	//int temp = 10; cosnt int &ref = temp;

	int a = 10;
	showValue(a);

	return 0;
}
```



## 11 函数提高

### 01 函数默认参数

```c++
#include<iostream>
using namespace std;

//如果传入值，就使用传入值，没有，则使用默认值
//从有默认值的变量开始，从左到右必须都有默认值
//int func(int a.int b = 30,int c){} 错误

//如果函数声明有默认参数，函数实现则不能有默认参数
//两个只能有一个有
/*
* int func(int a = 10, int b = 10);
* int func(int a = 20, int b = 20){} 错误
*/

int func(int a, int b = 30, int c = 30) {
	return a + b + c;
}

int main() {
	cout << func(10, 20, 30) << endl;
	cout << func(10) << endl;

	return 0;
}
```



### 02 函数占位参数

```c++
#include<iostream>
using namespace std;

void func(int) {
	cout << "this is a fun" << endl;
}
//占位参数还可以有默认参数
void func1(int = 10) {
	cout << "this is a fun" << endl;
}

int main() {
	func(10);
	func1();
	func1(20);

	return 0;
}
```



### 03 函数重载

```c++
#include<iostream>
using namespace std;

void func2() {
	cout << "func()函数调用" << endl;
}

void func2(int a) {
	cout << "func(int a)函数调用" << endl;
}

void func2(double a) {
	cout << "func(double a)函数调用" << endl;
}

int main() {
	func2();
	func2(10);
	func2(3.14);

	return 0;
}
```



### 04 函数重载注意事项

```c++
#include<iostream>
using namespace std;

//1、引用作为重载的条件
void func4(int& a) {
	cout << "func4(int& a)调用" << endl;
}

void func4(const int& a) {
	cout << "func4(const int& a)调用" << endl;
}

//2、函数重载碰到默认参数
void func4_2(int a) {
	cout << "func4_2(int a)调用" << endl;
}
void func4_2(int a,int = 10) {
	cout << "func4_2(int a,int = 10)调用" << endl;
}
//调用时发生错误

int main() {
	int a = 10;
	func4(a);
	func4(20);

	return 0;
}
```



## 12 类和对象

### 01 封装

#### 01 封装的意义

```c++
#include<iostream>
using namespace std;

const double PI = 3.14;

class Circle {
public:
	int m_r;

	double caculateZC() {
		return 2 * PI * m_r;
	}
};

int main() {
	Circle c1;
	c1.m_r = 10;

	cout << "圆的周长为：" << c1.caculateZC() << endl;

	return 0;
}
```



#### 02 封装案例

```c++
#include<iostream>
#include<string.h>
using namespace std;

class Student {
public:
	string m_Name;
	int m_Id;

	void showStudent() {
		cout << "姓名：" << m_Name << " 学号：" << m_Id << endl;
	}

	void getName(string name) {
		m_Name = name;
	}

	void getId(int id) {
		m_Id = id;
	}
};

int main() {
	Student s1;
	s1.m_Name = "张三";
	s1.m_Id = 1;
	s1.showStudent();

	Student s2;
	s2.getName("李四");
	s2.getId(2);
	s2.showStudent();

	return 0;
}
```



#### 03 封装的权限控制

```c++
#include<iostream>
#include<string.h>
using namespace std;

//访问权限
//公共权限 public		成员 类内可以访问 类外可以访问
//保护权限 protected	成员 类内可以访问 类外不可以访问 子类可访问
//私有权限 private		成员 类内可以访问 类外不可以访问 子类不可访问

class Person {
public:
	string m_Name;

protected:
	string m_Car;

private:
	int m_Password;

public:
	void func() {
		m_Name = "张三";
		m_Car = "拖拉机";
		m_Password = 123456;
	}
};

int main() {
	Person p1;
	p1.func();

	p1.m_Name = "李四";
	//p1.m_Car = "奔驰"; 错误
	//01.m_Password = 123; 错误

	return 0;
}
```



#### 04 struct和class区别

```c++
#include<iostream>
using namespace std;

//struct默认权限是公共权限 public
//class默认权限是私有权限 private

class C1 {
	int m_A; //私有
};

struct C2 {
	int m_A; //公共
};

int main() {
	C1 c1;
	//c1.m_A = 1; 错误

	C2 c2;
	c2.m_A = 1;

	return 0;
}
```



#### 05 成员属性设置为私有

```c++
#include<iostream>
#include<string.h>
using namespace std;

class Person5 {
public:
	void setName(string name) {
		m_Name = name;
	}

	string getName() {
		return m_Name;
	}

	void setAge(int age) {
		if (age < 0 || age>150) {
			return;
		}
		m_Age = age;
	}

	int showAge() {
		return m_Age;
	}

private:
	string m_Name;
	int m_Age;
	string m_Lover;
};

int main() {
	Person5 p1;

	p1.setName("张三");
	cout << "姓名为：" << p1.getName() << endl;

	p1.setAge(18);
	cout << "年龄为：" << p1.showAge() << endl;
	p1.setAge(1000);
	cout << "年龄为：" << p1.showAge() << endl;

	return 0;
}
```



#### 06 封装案例-立方体

```c++
#include<iostream>
using namespace std;

class Cube {
public:
	void setL(int L) {
		m_L = L;
	}
	int getL() {
		return m_L;
	}

	void setW(int W) {
		m_W = W;
	}
	int getW() {
		return m_W;
	}

	void setH(int H) {
		m_H = H;
	}
	int getH() {
		return m_H;
	}

	int caculateS() {
		return 2 * m_L * m_W + 2 * m_L * m_H + 2 * m_W * m_H;
	}

	int caculateV() {
		return m_L * m_W * m_H;
	}

	bool isSameByClass(Cube& c) {
		if (m_L == c.getL() && m_W == c.getW() && m_H == c.getH())
		{
			return true;
		}
		else
		{
			return false;
		}
	}

private:
	int m_L;
	int m_W;
	int m_H;
};

bool isSame(Cube& c1, Cube& c2) {
	if (c1.getL() == c2.getL() && c1.getW() == c2.getW() && c1.getH() == c2.getH())
	{
		return true;
	}
	else
	{
		return false;
	}
}

int main() {
	Cube c1;
	c1.setL(10);
	c1.setW(10);
	c1.setH(10);

	cout << "面积为：" << c1.caculateS() << endl;
	cout << "体积为：" << c1.caculateV() << endl;

	Cube c2;
	c2.setL(10);
	c2.setW(10);
	c2.setH(10);

	bool ret = isSame(c1, c2);
	if (ret == true)
	{
		cout << "相等" << endl;
	}
	else
	{
		cout << "不相等" << endl;
	}

	bool ret2 = c1.isSameByClass(c2);
	if (ret2 == true)
	{
		cout << "相等" << endl;
	}
	else
	{
		cout << "不相等" << endl;
	}

	return 0;
}
```



#### 07 封装案例-点和圆的关系

Point.h

```c++
#pragma once
#include<iostream>
using namespace std;

class Point {
public:
	void setX(int x);
	int getX();

	void setY(int y);
	int getY();

private:
	int m_X;
	int m_Y;
};
```

Circle.h

```c++
#pragma once
#include<iostream>
using namespace std;
#include"07 Point.h"

class Circle {
public:
	void setR(int r);
	int getR();

	void setCenter(Point center);
	Point getCenter();

private:
	int m_R;
	Point m_Center;
};
```

Point.cpp

```c++
#include"07 Point.h"

void Point::setX(int x) {
	m_X = x;
}
int Point::getX() {
	return m_X;
}

void Point::setY(int y) {
	m_Y = y;
}
int Point::getY() {
	return m_Y;
}
```

Circle.cpp

```c++
#include"07 Circle.h"
void Circle::setR(int r) {
	m_R = r;
}
int Circle::getR() {
	return m_R;
}

void Circle::setCenter(Point center) {
	m_Center = center;
}
Point Circle::getCenter() {
	return m_Center;
}
```

封装案例-点和圆的关系.cpp

```c++
#include<iostream>
using namespace std;
#include"07 Circle.h"
#include"07 Point.h"

void isInCircle(Circle& c, Point& p) {
	int distance =
		(c.getCenter().getX() - p.getX()) * (c.getCenter().getX() - p.getX()) +
		(c.getCenter().getY() - p.getY()) * (c.getCenter().getY() - p.getY());
	int rDistance = c.getR() * c.getR();

	if (distance == rDistance)
	{
		cout << "点在圆上" << endl;
	}
	else if (distance > rDistance)
	{
		cout << "点在圆外" << endl;
	}
	else
	{
		cout << "点在圆内" << endl;
	}
}

int main() {
	Circle c;
	c.setR(10);
	Point center;
	center.setX(10);
	center.setY(0);
	c.setCenter(center);

	Point p;
	p.setX(10);
	p.setY(10);
	isInCircle(c, p);

	p.setY(11);
	isInCircle(c, p);

	p.setY(9);
	isInCircle(c, p);

	return 0;
}
```



### 02 类和对象的初始化和清理

#### 01 构造函数和析构函数

```c++
#include<iostream>
using namespace std;

class Person {
public:
	Person() {
		cout << "Person构造函数的调用" << endl;
	}
	Person(int a) {
		cout << "Person(int a)构造函数的调用" << endl;
	}
	~Person() {
		cout << "Person析构函数的调用" << endl;
	}
};

void func() {
	Person p1;
	Person p2(1);
}

int main() {
	func();
	Person p3;

	return 0;
}
```



#### 02 构造函数的分类和调用

```c++
#include<iostream>
using namespace std;

class Person {
public:
	//无参构造函数（默认构造函数）
	Person() {
		cout << "Person的构造函数" << endl;
	}
	
	//有参构造函数
	Person(int a) {
		age = a;
		cout << "Person(int a)的构造函数" << endl;
	}

	//拷贝构造函数
	Person(const Person& p) {
		age = p.age;
		cout << "Person(const Person& p)的构造函数" << endl;
	}

	~Person() {
		cout << "Person的析构函数" << endl;
	}
	
private:
	int age;
};

int main() {
	//括号法
	Person p1;
	Person p2(10);
	Person p3(p2);
	
	//显示法
	Person p4 = Person(10);
	Person p5 = Person(p2);
	//不要用构造函数初始化匿名对象，编译器会认为Person(p3)===Person p3；对象声明

	//隐式转换法
	Person p6 = 10; //Person p6 = Person(10);
	Person p7 = p2; //拷贝构造

	return 0;
}
```



#### 03 拷贝构造函数调用时机

```c++
#include<iostream>
using namespace std;

class Person3 {
public:
	Person3() {
		cout << "Person默认构造函数调用" << endl;
	}

	Person3(int age) {
		cout << "Person有参构造函数" << endl;
	}

	Person3(const Person3& p) {
		cout << "Person拷贝构造函数" << endl;
		m_Age = p.m_Age;
	}

	~Person3() {
		cout << "Person析构构造函数调用" << endl;
	}

private:
	int m_Age;
};

void func3(Person3 p) {
	
}

Person3 func3_2() {
	Person3 p1;
	return p1;
}

int main() {
	//1、使用一个已经创建完毕的对象来初始化一个新对象
	Person3 p1(20);
	Person3 p2(p1);

	//2、值传递的方式给函数参数传值
	func3(p1);

	//3、值方式返回局部对象
	func3_2();

	return 0;
}
```



#### 04 构造函数的调用原则

```c++
#include<iostream>
using namespace std;

//1、编译器默认提供三种函数：无参构造函数，拷贝构造函数，析构函数
//2、当编写了有参构造，编译器就不会提供无参构造函数
//3、当编写了拷贝构造，编译器就不提供其他构造函数

class Person4 {
public:
	Person4() {
		cout << "默认构造函数" << endl;
	}
	Person4(int a) {
		age = a;
		cout << "有参构造函数" << endl;
	}
	Person4(const Person4& p) {
		age = p.age;
		cout << "拷贝构造函数" << endl;
	}
	~Person4() {
		cout << "析构函数" << endl;
	}

	int age;
};

void test4() {
	Person4 p;
	p.age = 18;

	Person4 p2(p);
	cout << "p2年龄为：" << p2.age << endl;
}

int main() {
	test4();

	return 0;
}
```



#### 05 深拷贝和浅拷贝

```c++
#include<iostream>
using namespace std;

//浅拷贝：简单的赋值
//深拷贝：重新申请内存

class Person5 {
public:
	Person5() {
		cout << "默认构造函数" << endl;
	}
	Person5(int a,int h) {
		age = a;
		height = new int(h);
		cout << "有参构造函数" << endl;
	}
	Person5(const Person5& p) {
		age = p.age;
		//height = p.height;浅拷贝，析构释放时会重复释放，出现问题
		height = new int(*p.height);//深拷贝
		cout << "拷贝构造函数" << endl;
	}
	~Person5() {
		if (height != NULL)
		{
			delete height;
			height = NULL;
		}
		cout << "析构函数" << endl;
	}

	int age;
	int *height;
};

void test5() {
	Person5 p1(18,160);
	cout << "p1的年龄：" << p1.age << "身高为：" << *p1.height << "地址：" << p1.height << endl;

	Person5 p2(p1);
	cout << "p2的年龄：" << p2.age << "身高为：" << *p2.height << "地址：" << p2.height << endl;
}

int main() {
	test5();

	return 0;
}
```



#### 06 初始化列表

```c++
#include<iostream>
using namespace std;

class Person6 {
public:
	//传统初始化操作
	Person6(int a, int b, int c) {
		m_A = a;
		m_B = b;
		m_C = c;
	}
	//Person6(int a, int b, int c) :m_A(a), m_B(b), m_C(c) {}

	//初始化列表
	Person6() :m_A(10), m_B(20), m_C(30) {
		cout << "初始化列表" << endl;
	}

	int m_A;
	int m_B;
	int m_C;
};

void test6() {
	Person6 p1(10, 20, 30);
	cout << "m_A = " << p1.m_A << endl;
	cout << "m_B = " << p1.m_B << endl;
	cout << "m_C = " << p1.m_C << endl;

	Person6 p2;
	cout << "m_A = " << p2.m_A << endl;
	cout << "m_B = " << p2.m_B << endl;
	cout << "m_C = " << p2.m_C << endl;
}

int main() {
	test6();

	return 0;
}
```



#### 07 类对象作为类成员

```c++
#include<iostream>
#include<string.h>
using namespace std;

class Phone {
public:
	Phone(string name) {
		cout << "Phone构造" << endl;
		m_Pname = name;
	}
	~Phone() {
		cout << "Phone析构函数" << endl;
	}

	string m_Pname;
};

class Person7 {
public:
	Person7(string name,string pName):m_name(name),m_phone(pName) {
		cout << "Person构造" << endl;
	}
	~Person7() {
		cout << "Person析构函数" << endl;
	}

	string m_name;
	Phone m_phone;
};

void test7() {
	Person7("张三", "苹果MAX");
}

int main() {
	test7();

	return 0;
}
```



#### 08 静态成员变量

```c++
#include<iostream>
using namespace std;

class Person8 {
public:

	//1、所有对象共享一份数据
	//2、编译阶段就分配内存
	//3、类内声明，类外初始化操作
	static int m_A;

	//静态成员变量也是有访问权限的
private:
	static int m_B;
};

int Person8::m_A = 100;
int Person8::m_B = 300;

void test8() {
	Person8 p1;
	cout << p1.m_A << endl;

	Person8 p2;
	p2.m_A = 200;

	cout << p1.m_A << endl;
}

void test8_2() {
	//静态成员变量，不属于某个对象上，所有对象共享同一份数据
	//因此静态成员变量有两种访问方式

	//1、通过对象进行访问
	Person8 p;
	cout << p.m_A << endl;

	//2、通过类名进行访问
	cout << Person8::m_A << endl;
	//cout << Person8::m_B << endl; 错误
}

int main() {
	test8();
	test8_2();
	return 0;
}
```



#### 09 静态成员函数

```c++
#include<iostream>
using namespace std;

//静态成员函数
//所有对象共享同一个函数
//静态成员函数只能访问静态成员变量

class Person9 {
public:
	static void func() {
		m_A = 100;
		//m_B = 200; 错误，m_B属于非静态成员变量
		cout << "static void func()调用" << endl;
	}

	static int m_A;
	int m_B;

	//静态成员函数也是有访问权限的
private:
	static void func2() {
		cout << "static void func2()调用" << endl;
	}
};
int Person9::m_A = 0;

void test9() {
	Person9 p;
	p.func();
	//p.func2(); 错误

	Person9::func();
}

int main() {
	test9();

	return 0;
}
```



### 03 对象模型和this指针

#### 01 成员变量和成员函数分开存储

```c++
#include<iostream>
using namespace std;

//成员变量 和 成员函数 分开存储的

class Person {
	int m_A;

	static int m_B;

	void func(){}

	static void func2(){}
};
int Person::m_B = 10;

void test01() {
	Person p;

	//空对象占用内存空间：1
	//c++编译器会给每一个空对象也分配一个字节的空间，是为了区别空对象占内存的位置
	//每个空对象也应该有一个独一无二的内存地址
	cout << "sizeof(p) = " << sizeof(p) << endl;
	//一个非静态成员变量：4
	//一个非静态成员变量 一个静态成员变量：4
	//一个非静态成员变量 一个静态成员变量 一个非静态函数：4
	//一个非静态成员变量 一个静态成员变量 一个非静态函数 一个静态函数：4
}

int main() {
	test01();

	return 0;
}
```



#### 02 this指针的使用

```c++
#include<iostream>
using namespace std;

class Person2 {
public:
	Person2(int age) {
		//this指针指向被调用的成员函数所属的对象
		this->age = age;
	}

	 Person2& PersonAddAge(Person2& p) {
		this->age += p.age;

		return *this;
	}

	int age;
};

//1、解决名称冲突
void test02() {
	Person2 p1(18);
	cout << "p1.age = " << p1.age << endl;
}

//2、返回对象本身用*this
void test02_2() {
	Person2 p1(10);
	Person2 p2(10);
	p2.PersonAddAge(p1).PersonAddAge(p1).PersonAddAge(p1);
	cout << "p2.age = " << p2.age << endl;
}

int main() {
	test02();
	test02_2();

	return 0;
}
```



#### 03 空指针访问成员函数

```c++
#include<iostream>
using namespace std;

class Person3 {
public:
	void showClassName() {
		cout << "this is Person class" << endl;
	}

	void showPersonAge() {
		cout << "age = " << m_Age << endl;
	}

	int m_Age;
};

void test03() {
	Person3* p = NULL;
	p->showClassName();
	//p->showPersonAge(); 错误
}

int main() {
	test03();

	return 0;
}
```



#### 04 const修饰成员函数

```c++
#include<iostream>
using namespace std;

class Person4 {
public:
	//在成员函数后面加const，修饰的是this指向，让指针指向的值也不可以修改

	//this指针的本质 是指针常量 指针的指向是不可以修改的
	//Person* const this;
	void showPerson() {
		this->m_A = 100;
		//this = NULL; 错误，this指针不可以修改指针的指向
	}

	//const Person* const this;
	void changePerson()const {
		//this->m_A = 100; 错误
		m_B = 100;
	}

	int m_A;
	mutable int m_B;//常函数中也可以修改这个值
};

void test04() {
	Person4 p1;
	p1.showPerson();
	p1.changePerson();
}


//常对象
void test04_2() {
	const Person4 p1;
	//p1.m_A = 100; 错误
	p1.m_B = 100;//常对象也可以修改

	//常对象只能调用常函数
	//p1.showPerson(); 错误
	p1.changePerson();
}

int main() {

	return 0;
}
```



### 04 友元

#### 01 全局函数做友元

```c++
#include<iostream>
#include<string>
using namespace std;

class Building {
	//可以访问私有权限
	friend void goodGay(Building& build);

public:
	Building() {
		m_SittingRoom = "客厅";
		m_BedRoom = "卧室";
	}

public:
	string m_SittingRoom;//客厅

private:
	string m_BedRoom;//卧室
};

void goodGay(Building& build) {
	cout << "好基友全局函数正在访问：" << build.m_SittingRoom << endl;
	cout << "好基友全局函数正在访问：" << build.m_BedRoom << endl;
}

void test01() {
	Building build;
	goodGay(build);
}

int main() {
	test01();

	return 0;
}
```



#### 02 类做友元

```c++
#include<iostream>
#include<string>
using namespace std;

class Building1;

class GoodGay {
public:
	void visit();
	GoodGay();

	Building1* building;
};

class Building1 {
	friend class GoodGay;

public:
	Building1();
public:
	string m_SittingRoom;

private:
	string m_BedRoom;
};

//类外做成员函数
Building1::Building1() {
	m_SittingRoom = "客厅";
	m_BedRoom = "卧室";
}
GoodGay::GoodGay() {
	building = new Building1;
}
void GoodGay::visit() {
	cout << "好基友正在访问：" << building->m_SittingRoom << endl;
	cout << "好基友正在访问：" << building->m_BedRoom << endl;
}

void test02() {
	GoodGay gg;
	gg.visit();
}

int main() {
	test02();

	return 0;
}
```



#### 03 成员函数做友元

```c++
#include<iostream>
#include<string>
using namespace std;

class Building3;
class GoodGay3 {
public:
	GoodGay3();
	void visit1();//可以访问Building中私有成员
	void visit2();//不可以访问Building中私有成员

	Building3* building;
};

class Building3 {
	//成员函数做友元
	friend void GoodGay3::visit1();

public:
	Building3();
public:
	string m_SittingRoom;
private:
	string m_BedRoom;
};

Building3::Building3() {
	m_SittingRoom = "客厅";
	m_BedRoom = "卧室";
}
GoodGay3::GoodGay3() {
	building = new Building3;
}
void GoodGay3::visit1() {
	cout << "visit1正在访问" << building->m_SittingRoom << endl;
	cout << "visit1正在访问" << building->m_BedRoom << endl;
}
void GoodGay3::visit2() {
	cout << "visit2正在访问" << building->m_SittingRoom << endl;
	//cout << "visit1正在访问" << building->m_BedRoom << endl; 错误
}

void test03() {
	GoodGay3 gg;
	gg.visit1();
	gg.visit2();
}

int main() {
	test03();

	return 0;
}
```



### 05 运算符重载

#### 01 加号运算符重载

```c++
#include<iostream>
using namespace std;

class Person {
public:
	//成员函数实现运算符重载
	Person operator+(Person& p) {
		Person temp;
		temp.m_A = this->m_A + p.m_A;
		temp.m_B = this->m_B + p.m_B;
		return temp;
	}

public:
	int m_A;
	int m_B;
};

class Person1 {
public:
	int m_A;
	int m_B;
};

//全局函数实现运算符重载
Person1 operator+(const Person1& p1, const Person1& p2) {
	Person1 temp;
	temp.m_A = p1.m_A + p2.m_A;
	temp.m_B = p1.m_B + p2.m_B;
	return temp;
}
//运算符重载也可以发生函数重载
Person1 operator+(const Person1& p1, const int& num) {
	Person1 temp;
	temp.m_A = p1.m_A + num;
	temp.m_B = p1.m_B + num;
	return temp;
}

void test01() {
	Person p1;
	p1.m_A = 10;
	p1.m_B = 10;
	Person p2;
	p2.m_A = 10;
	p2.m_B = 10;

	//Person p3 = p1.operator+(p2);
	Person p3 = p1 + p2;
	cout << "p3.m_A = " << p3.m_A << " p3.m_B = " << p3.m_B << endl;

	Person1 p4;
	p4.m_A = 10;
	p4.m_B = 10;
	Person1 p5;
	p5.m_A = 10;
	p5.m_B = 10;

	//Person1 p3 = operator+(p1,p2);
	Person1 p6 = p4 + p5;
	cout << "p6.m_A = " << p6.m_A << " p6.m_B = " << p6.m_B << endl;

	Person1 p7 = p4 + 10;
	cout << "p7.m_A = " << p7.m_A << " p7.m_B = " << p7.m_B << endl;
}

int main() {
	test01();

	return 0;
}
```



#### 02 左移运算符重载

```c++
#include<iostream>
using namespace std;

class Person2 {
public:
	friend ostream& operator<<(ostream& cout, Person2& p);

	Person2() {
		m_A = 10;
		m_B = 10;
	}

private:
	//不会利用成员函数重载<<运算符，因为无法实现cout在左侧
	int m_A;
	int m_B;
};

//全局函数实现左移运算符
ostream & operator<<(ostream& cout, Person2& p) {
	cout << "m_A = " << p.m_A << " m_B = " << p.m_B;
	return cout;
}

void test02() {
	Person2 p1;

	cout << p1 << endl;
}

int main() {
	test02();

	return 0;
}
```



#### 03 递增运算符重载

```c++
#include<iostream>
using namespace std;

class MyInteger {
	friend ostream& operator<<(ostream& cout, MyInteger myint);
public:
	MyInteger() {
		m_Num = 0;
	}
	
	//重载前置++运算符
	MyInteger& operator++() {
		m_Num++;
		return *this;
	}
	//重载后置++运算符 int代表占位参数，可以用于区分前置和后置
	MyInteger operator++(int) {
		MyInteger temp = *this;
		m_Num++;
		return temp;
	}

private:
	int m_Num;
};

//重载左移运算符
ostream& operator<<(ostream& cout, MyInteger myint) {
	cout << ++myint.m_Num << endl;
	cout << myint.m_Num++ << endl;
	cout << myint.m_Num << endl;

	return cout;
}

void test03() {
	MyInteger myint;
	cout << myint << endl;
}

int main() {
	test03();

	return 0;
}
```



#### 04 赋值运算符重载

```c++
#include<iostream>
using namespace std;

class Person4 {
public:
	Person4(int age) {
		m_Age = new int(age);
	}
	~Person4() {
		if (m_Age != NULL) {
			delete m_Age;
		}
	}

	//重载赋值运算符
	Person4& operator=(Person4& p) {
		//编译器提供浅拷贝——m_Age = p.m_Age;
		//应该先判断是否有属性在堆区，如果有，先释放干净，然后再深拷贝
		if (m_Age != NULL) {
			delete m_Age;
			m_Age = NULL;
		}
		m_Age = new int(*p.m_Age);

		return *this;
	}

	int* m_Age;
};

void test04() {
	Person4 p1(18);
	Person4 p2(20);
	Person4 p3(22);

	p3 = p2 = p1;

	cout << "p1的年龄为" << *p1.m_Age << endl;
	cout << "p2的年龄为" << *p2.m_Age << endl;
	cout << "p3的年龄为" << *p3.m_Age << endl;
}

int main() {
	test04();

	return 0;
}
```



#### 05 关系运算符重载

```c++
#include<iostream>
#include<string>
using namespace std;

class Person5 {
public:
	Person5(string name, int age) {
		m_Name = name;
		m_Age = age;
	}

	bool operator==(Person5& p) {
		if (this->m_Name == p.m_Name && this->m_Age == p.m_Age)
		{
			return true;
		}
		return false;
	}

	bool operator!=(Person5& p) {
		if (this->m_Name == p.m_Name && this->m_Age == p.m_Age)
		{
			return false;
		}
		return true;
	}

	string m_Name;
	int m_Age;
};

void test05() {
	Person5 p1("Tom", 18);
	Person5 p2("Tom", 18);

	if (p1 == p2)
	{
		cout << "相等" << endl;
	}
	else
	{
		cout << "不相等" << endl;
	}

	if (p1 != p2)
	{
		cout << "不相等" << endl;
	}
	else
	{
		cout << "相等" << endl;
	}
}

int main5() {
	test05();

	return 0;
}
```



#### 06 函数调用运算符重载

```c++
#include<iostream>
#include<string>
using namespace std;

class MyPrint {
public:
	//仿函数
	void operator()(string test) {
		cout << test << endl;
	}
};

void test06() {
	MyPrint myPrint;
	myPrint("Hello World");
}

class MyAdd {
public:
	int operator()(int num1,int num2) {
		return num1 + num2;
	}
};

void test06_2() {
	MyAdd myAdd;
	int ret = myAdd(100, 100);
	cout << "ret = " << ret << endl;

	//匿名对象
	cout << MyAdd()(100, 100) << endl;
}

int main() {
	test06();
	test06_2();

	return 0;
}
```



### 06 继承

#### 01 继承的基本语法

```c++
#include<iostream>
using namespace std;

class BasePage {
public:
	void header() {
		cout << "首页、公开课、登录、注册……（公共头部）" << endl;
	}
	void footer() {
		cout << "帮助中心、交流合作、站内地图……（公共底部）" << endl;
	}
	void left() {
		cout << "Java、Python、C++……（公共分类列表）" << endl;
	}
};

//继承好处：减少重复代码
//语法：class 子类 : 继承方式 父类
//子类 也称为 派生类
//父类 也称为 基类

class Java : public BasePage {
public:
	void content() {
		cout << "Java学科视频" << endl;
	}
};
class Python : public BasePage {
public:
	void content() {
		cout << "Python学科视频" << endl;
	}
};

void test01() {
	cout << "Java下载视频页面如下：" << endl;
	Java ja;
	ja.header();
	ja.footer();
	ja.left();
	ja.content();

	cout << "----------------------" << endl;

	cout << "Python下载视频页面如下：" << endl;
	Python py;
	py.header();
	py.footer();
	py.left();
	py.content();
}

int main() {
	test01();

	return 0;
}
```



#### 02 继承方法

```c++
#include<iostream>
using namespace std;

class Base2 {
public:
	int m_A;
protected:
	int m_B;
private:
	int m_C;
};
//公共继承
class Son1 : public Base2 {
public:
	void func() {
		m_A = 10;//公共权限
		m_B = 10;//保护权限
		//m_C = 10;//私有权限访问不到
	}
};
//保护继承
class Son2 : protected Base2 {
public:
	void func() {
		m_A = 10;//保护权限
		m_B = 10;//保护权限
		//m_C = 10;//私有权限访问不到
	}
};
//私有继承
class Son3 : private Base2 {
public:
	void func() {
		m_A = 10;//私有权限
		m_B = 10;//私有权限
		//m_C = 10;//私有权限访问不到
	}
};

class GrandSon3 : public Son3 {
public:
	void func() {
		//m_A = 10;//私有权限访问不到
	}
};

void test02() {
	Son1 s1;
	s1.m_A = 100;//公共权限
	//s1.m_B = 100;//保护权限
	
	Son2 s2;
	//s2.m_A = 100;//保护权限
	//s2.m_B = 100;//保护权限

	Son3 s3;
	//s2.m_A = 100;//私有权限
	//s2.m_B = 100;//私有权限
}

int main() {
	test02();

	return 0;
}
```



#### 03 继承的对象模型

```c++
#include<iostream>
using namespace std;

class Base3 {
public:
	int m_A;
protected:
	int m_B;
private:
	int m_C;
};

class Son03 :public Base3 {
public:
	int m_D;
};

void test03() {
	//父类中所有非静态成员属性都会被子类继承下去
	cout << "size of son = " << sizeof(Son03) << endl;
}

//利用开发人员命令提示工具查看对象模型
//跳转盘符	F:
//跳转文件路径	cd 具体路径下
//查看命名
//cl /dl reportSingleClassLayout类名 文件名

int main() {
	test03();

	return 0;
}
```



#### 04 继承中构造和析构顺序

```c++
#include<iostream>
using namespace std;

class Base4 {
public:
	Base4() {
		cout << "Base构造函数" << endl;
	}
	~Base4() {
		cout << "Base析构函数" << endl;
	}
};

class Son4 :public Base4 {
public:
	Son4() {
		cout << "Son构造函数" << endl;
	}
	~Son4() {
		cout << "Son析构函数" << endl;
	}
};

void test04() {
	Son4 s;
}

int main() {
	test04();

	return 0;
}
```



#### 05 继承同名成员处理

```c++
#include<iostream>
using namespace std;

class Base5{
public:
	Base5() {
		m_A = 100;
	}
	void func() {
		cout << "Base func调用" << endl;
	}
	int m_A;
};

class Son5 :public Base5 {
public:
	Son5() {
		m_A = 200;
	}
	void func() {
		cout << "Son func调用" << endl;
	}
	int m_A;
};

void test05() {
	Son5 s;
	cout << "Son m_A = " << s.m_A << endl;
	//如果通过子类访问父类同名成员，需要添加作用域
	cout << "Base m_A = " << s.Base5::m_A << endl;

	s.func();
	s.Base5::func();
}

int main() {
	test05();

	return 0;
}
```



#### 06 继承同名静态成员处理

```c++
#include<iostream>
using namespace std;

class Base6 {
public:
	static void func() {
		cout << "Base func" << endl;
	}

	static int m_A;
};
int Base6::m_A = 100;

class Son6 :public Base6 {
public:
	static void func() {
		cout << "Son func" << endl;
	}

	static int m_A;
};
int Son6::m_A = 200;

void test06() {
	//通过对象访问
	Son6 s;
	cout << "Son m_A = " << s.m_A << endl;
	cout << "Base m_A = " << s.Base6::m_A << endl;
	s.func();
	s.Base6::func();

	//通过类名访问
	cout << "Son m_A = " << Son6::m_A << endl;
	cout << "Base m_A = " << Son6::Base6::m_A << endl;
	Son6::func();
	Son6::Base6::func();
}

int main() {
	test06();

	return 0;
}
```



#### 07 多继承语法

```c++
#include<iostream>
using namespace std;

class Base7_1 {
public:
	Base7_1() {
		m_A = 100;
	}
	int m_A;
};
class Base7_2 {
public:
	Base7_2() {
		m_B = 200;
	}
	int m_B;
};

class Son7 :public Base7_1, public Base7_2 {
public:
	Son7() {
		m_C = 300;
		m_D = 400;
	}
	int m_C;
	int m_D;
};

void test07() {
	Son7 s;
	cout << "sizeof(s) = " << sizeof(s) << endl;
}

int main() {
	test07();

	return 0;
}
```



#### 08 菱形继承

```c++
#include<iostream>
using namespace std;

//动物类
class Animal {
public:
	int m_Age;
};

//利用虚继承 解决菱形继承的问题
//继承之前加上关键字 virtual 变为虚继承
//Animal类称为虚基类

//羊类
class Sheep :virtual public Animal {};

//驼类
class Tuo :virtual public Animal {};

class SheepTuo :public Sheep, public Tuo {};

void test08() {
	SheepTuo st;

	st.Sheep::m_Age = 18;
	st.Tuo::m_Age = 28;

	cout << "st.Sheep::m_Age = " << st.Sheep::m_Age << endl;
	cout << "st.Tuo::m_Age = " << st.Tuo::m_Age << endl;
	cout << "st.m_Age = " << st.m_Age << endl;
}

int main() {
	test08();

	return 0;
}
```



### 07多态

#### 01 多态基本概念

```c++
#include<iostream>
using namespace std;
//多态分为静态多态和动态多态

//静态多态：函数重载和运算符重载属于静态多态，复用函数名
//动态多态：派生类和虚函数实现运行时多态

//动态多态满足条件
//1、有继承关系
//2、子类重写父函数的虚函数

//动态多态使用
//父类的指针或者引用 执行子对象

class Animal {
public:
	//虚函数
	virtual void speak() {
		cout << "动物在说话" << endl;
	}
};

class Cat :public Animal {
public:
	//重写：函数返回值类型 函数名 参数列表 完全相同
	void speak() {
		cout << "猫在说话" << endl;
	}
};

//地址早绑定 在编译阶段确定函数地址
//地址晚绑定让小猫说话，函数前加virtual
void doSpeak(Animal& animal) {
	animal.speak();
}

void test01() {
	Cat cat;
	doSpeak(cat);
}

int main() {
	test01();

	return 0;
}
```



#### 02 多态案例-计算器实现

```c++
#include<iostream>
#include<string>
using namespace std;

//使用普通方法和多态技术实现计算器

//普通写法

class Calculatao {
public:
	int getResult(string oper) {
		if (oper == "+")
		{
			return m_Num1 + m_Num2;
		}
		else if (oper == "-")
		{
			return m_Num1 - m_Num2;
		}
		else if(oper =="*")
		{
			return m_Num1 * m_Num2;
		}
		//如果想扩展新功能，需要修改源码
		//在真实的开发中，提倡开闭原则
		//开闭原则：对扩展进行开放，对修改进行关闭
	}

	int m_Num1;
	int m_Num2;
};

void test02() {
	Calculatao c;
	c.m_Num1 = 10;
	c.m_Num2 = 20;

	cout << c.getResult("+") << endl;
	cout << c.getResult("-") << endl;
	cout << c.getResult("*") << endl;
}

//利用多态实现计算器
//多态函数优点：
//1、组织结构清晰
//2、可读性强
//3、对于前期和后期扩展以及维护性高

//实现计算器抽象类
class AbstractCalculator {
public:
	virtual int getResult() {
		return 0;
	}

	int m_Num1;
	int m_Num2;
};

//加法计算器类
class AddCalculator :public AbstractCalculator {
public:
	int getResult() {
		return m_Num1 + m_Num2;
	}
};
//减法计算器类
class SubCalculator :public AbstractCalculator {
public:
	int getResult() {
		return m_Num1 - m_Num2;
	}
};
//乘法计算器
class MulCalculator :public AbstractCalculator {
public:
	int getResult() {
		return m_Num1 * m_Num2;
	}
};

void test02_2() {
	//多态使用条件
	//父类指针或者引用指向子类对象

	//加法运算
	AbstractCalculator* abc = new AddCalculator;
	abc->m_Num1 = 10;
	abc->m_Num2 = 20;
	cout << abc->getResult() << endl;
	delete abc;

	abc = new SubCalculator;
	abc->m_Num1 = 10;
	abc->m_Num2 = 20;
	cout << abc->getResult() << endl;

	abc = new MulCalculator;
	abc->m_Num1 = 10;
	abc->m_Num2 = 20;
	cout << abc->getResult() << endl;
}

int main() {
	test02();
	cout << endl;
	test02_2();

	return 0;
}
```



#### 03 纯虚函数和抽象类

```c++
#include<iostream>
using namespace std;

class Base3 {
public:
	//纯虚函数
	//只要有一个纯虚函数，这个类称为抽象类
	//抽象类特点：
	//1、无法实例化对象
	//2、抽象类的子类 必须要重写父类中的纯虚函数，否则也属于抽象类
	virtual void func() = 0;
};

class Son3 :public Base3 {
	virtual void func() {
		cout << "func调用" << endl;
	}
};

void test03() {
	//Base3 b;
	//new Base;//抽象类是无法实例化对象

	Base3* base = new Son3;
	base->func();
}

int main() {
	test03();

	return 0;
}
```



#### 04 多态案例-制作饮品

```c++
#include<iostream>
using namespace std;

class AbstractDrinking {
public:
	//煮水
	virtual void Boil() = 0;
	//冲泡
	virtual void Brew() = 0;
	//倒入杯中
	virtual void PourInCup() = 0;
	//加入佐料
	virtual void PutSomething() = 0;
	//制作饮品
	void makeDrink() {
		Boil();
		Brew();
		PourInCup();
		PutSomething();
	}
};

//制作咖啡
class Coffee :public AbstractDrinking {
	//煮水
	virtual void Boil() {
		cout << "煮水" << endl;
	}
	//冲泡
	virtual void Brew() {
		cout << "冲泡咖啡" << endl;
	}
	//倒入杯中
	virtual void PourInCup() {
		cout << "倒入杯中" << endl;
	}
	//加入佐料
	virtual void PutSomething() {
		cout << "加入糖和牛奶" << endl;
	}
};

//制作函数
void doWork(AbstractDrinking* abs) {
	abs->makeDrink();
	delete abs;
}

void test04() {
	//制作咖啡
	doWork(new Coffee);
}

int main() {
	test04();

	return 0;
}
```



#### 05 虚析构和纯虚析构

```c++
#include<iostream>
#include<string>
using namespace std;

class Animal5 {
public:
	Animal5() {
		cout << "Animal构造函数" << endl;
	}

	//利用虚析构可以解决父类指针释放子对象时不干净的问题
	//virtual ~Animal5() {
	//	cout << "Animal析构函数" << endl;
	//}

	//纯虚析构 需要声明 需要实现
	//有了纯虚析构之后，这个类也属于抽象类，无法实例化对象
	virtual ~Animal5() = 0;

	virtual void speak() = 0;
};
//Animal纯虚析构
Animal5::~Animal5() {
	cout << "Animal析构函数" << endl;
}

class Cat5 :public Animal5 {
public:
	Cat5(string name) {
		cout << "Cat构造函数" << endl;
		m_Name = new string(name);
	}

	void speak() {
		cout << *m_Name <<"小猫说话" << endl;
	}

	~Cat5() {
		if (m_Name != NULL) {
			cout << "Cat析构函数" << endl;
			delete m_Name;
			m_Name = NULL;
		}
	}

	string* m_Name;
};

void test05() {
	Animal5* animal = new Cat5("Tom");
	animal->speak();
	delete animal;
}

int main() {
	test05();

	return 0;
}
```



#### 06 多态案例-电脑组装

```c++
#include<iostream>
using namespace std;

//零件
//CPU
class CPU {
public:
	virtual void calculate() = 0;
};
//显卡
class VideoCard {
public:
	virtual void display() = 0;
};
//内存条
class Memory {
public:
	virtual void storage() = 0;
};

//电脑
class Computer {
public:
	Computer(CPU* cpu, VideoCard* vc, Memory* mem) {
		m_cpu = cpu;
		m_vc = vc;
		m_mem = mem;
	}

	void work() {
		m_cpu->calculate();
		m_vc->display();
		m_mem->storage();
	}

	~Computer() {
		if (m_cpu != NULL) {
			delete m_cpu;
			m_cpu = NULL;
		}
		if (m_vc != NULL) {
			delete m_vc;
			m_vc = NULL;
		}
		if (m_mem != NULL) {
			delete m_mem;
			m_mem = NULL;
		}
	}

private:
	CPU* m_cpu;
	VideoCard* m_vc;
	Memory* m_mem;
};

//具体厂商
//Intel
class IntelCPU :public CPU {
public:
	void calculate() {
		cout << "IntelCPU开始工作" << endl;
	}
};
class IntelVideoCard :public VideoCard {
public:
	void display() {
		cout << "Intel显卡开始工作" << endl;
	}
};
class InterMemory :public Memory {
public:
	void storage() {
		cout << "Intel内存条开始工作" << endl;
	}
};
//Lenovo
class LenovoCPU :public CPU {
public:
	void calculate() {
		cout << "LenovoCPU开始工作" << endl;
	}
};
class LenovoVideoCard :public VideoCard {
public:
	void display() {
		cout << "Lenovo显卡开始工作" << endl;
	}
};
class LenovoMemory :public Memory {
public:
	void storage() {
		cout << "Lenovo内存条开始工作" << endl;
	}
};

void test06() {
	//创建零件
	CPU* intelCpu = new IntelCPU;
	VideoCard* intelCard = new IntelVideoCard;
	Memory* intelMem = new InterMemory;

	//组装电脑
	Computer* computer1 = new Computer(intelCpu, intelCard, intelMem);
	computer1->work();
	delete computer1;

	Computer* computer2 = new Computer(new LenovoCPU, new LenovoVideoCard, new LenovoMemory);
	computer2->work();
	delete computer2;
}

int main() {
	test06();

	return 0;
}
```



## 13 文件操作

### 01 写文件

```c++
#include<iostream>
#include<fstream>//操作文件的头文件包含
using namespace std;

//文本文件 写文件
void test01() {
	//1、包含头文件 fstream
	
	//2、创建流对象
	ofstream ofs;

	//3、指定打开方式
	ofs.open("test.txt", ios::out);

	ofs << "姓名：张三" << endl;
	ofs << "性别：男" << endl;
	ofs << "年龄：18" << endl;

	ofs.close();
}

int main() {
	test01();

	return 0;
}
```



### 02 读文件

```c++
#include<iostream>
#include<fstream>
#include<string>
using namespace std;

void test02() {
	//1、包含头文件 fstream
	
	//2、创建流对象
	ifstream ifs;

	//3、打开文件 并判断是否打开成功
	ifs.open("test.txt", ios::in);
	if (!ifs.is_open()) {
		cout << "文件打开失败" << endl;
		return;
	}

	//4、读数据
	////第一种
	//cout << "第一种" << endl;
	//char buf[1024] = { 0 };
	//while (ifs >> buf)
	//{
	//	cout << buf <<endl;
	//}

	////第二种
	//cout << "第二种" << endl;
	//char buf2[1024] = { 0 };
	//while (ifs.getline(buf2, sizeof(buf2)))
	//{
	//	cout << buf2 << endl;
	//}

	////第三种
	//string buf3;
	//while (getline(ifs,buf3))
	//{
	//	cout << buf3 << endl;
	//}

	//第四种
	char c;
	while ((c = ifs.get()) != EOF)//end of file
	{
		cout << c;
	}

	//5.关闭文件
	ifs.close();
}

int main() {
	test02();

	return 0;
}
```



### 03 二进制文件-写文件

```c++
#include<iostream>
#include<fstream>
using namespace std;

class Person {
public:
	char m_Name[64];
	int m_Age;
};

void test03() {
	//1、包含头文件 fstream

	//2、创建流对象
	ofstream ofs("person.txt", ios::out | ios::binary);

	//3、打开文件
	//ofs.open("person.txt", ios::out | ios::binary);

	//4、写文件
	Person p = { "张三",18 };
	ofs.write((const char *)&p,sizeof(Person));

	//5、关闭文件
	ofs.close();
}

int main() {
	test03();

	return 0;
}
```



### 04 二进制文件-读文件

```c++
#include<iostream>
#include<fstream>
using namespace std;

class Person {
public:
	char m_Name[64];
	int m_Age;
};

void test04() {
	//1、包含头文件 fstream
	
	//2、创建流对象
	ifstream ifs;
	
	//3、打开文件 并判断是否打开成功
	ifs.open("person.txt", ios::in | ios::binary);
	if (!ifs.is_open()) {
		cout << "打开失败" << endl;
		return;
	}

	//4、读文件
	Person p;
	ifs.read((char*)&p, sizeof(Person));

	cout << p.m_Name << " " << p.m_Age << endl;

	//5、关闭文件
	ifs.close();
}

int main() {
	test04();

	return 0;
}
```



## 14 职工管理系统

#### 头文件

##### worker.h

```c++
#pragma once
#include<iostream>
#include<string>
using namespace std;

//职工抽象类
class Worker {
public:
	virtual void showInfo() = 0;//显示个人信息
	virtual string getDeptName() = 0;//获取岗位名称

	int m_Id;
	string m_Name;
	int m_DeptId;
};
```

##### boss.h

```c++
//老板类
#pragma once
#include<iostream>
#include"worker.h"
using namespace std;

class Boss :public Worker {
public:
	Boss(int id, string name, int dId);
	void showInfo();//显示个人信息
	string getDeptName();//获取岗位名称
};
```

##### manager.h

```c++
//经理类
#pragma once
#include<iostream>
#include"worker.h"
using namespace std;

class Manager :public Worker {
public:
	Manager(int id, string name, int dId);
	void showInfo();//显示个人信息
	string getDeptName();//获取岗位名称
};
```

##### employee.h

```c++
//普通员工
#pragma once
#include<iostream>
#include"worker.h"
using namespace std;

class Employee :public Worker {
public:
	Employee(int id,string name,int dId);
	void showInfo();//显示个人信息
	string getDeptName();//获取岗位名称
};
```

##### workerManager.h

```c++
#pragma once//防止头文件重复包含
#include<iostream>//包含标准输入输出流头文件
#include<fstream>
#include"worker.h"
#include"employee.h"
#include"manager.h"
#include"boss.h"
using namespace std;//使用标准命名空间
#define FILENAME "empFile.txt"

class WorkManager {
public:
	WorkManager();
	~WorkManager();
	int get_EmpNum();//统计文件中人数
	void init_Emp();//初始化数组
	void save();//保存到文件
	void Show_Menu();//打印菜单
	void Add_Emp();//添加职工
	void Show_Emp();//显示职工
	void Del_Emp();//删除员工
	int IsExist(int id);//判断员工是否存在，如果存在返回员工所在数组位置，不存在返回-1
	void Mod_Emp();//修改职工
	void Find_Emp();//查找职工
	void Sort_Emp();//按照编号排序
	void Clean_File();//清空文件
	void ExitSystem();//退出功能
	
	bool m_FileIsEmpty;//判断文件是否为空
	int m_EmpNum;//记录职工人数
	Worker** m_EmpArray;//职工数组指针
};
```

#### 源文件

##### boss.cpp

```c++
#include"boss.h"

Boss::Boss(int id, string name, int dId) {
	this->m_Id = id;
	this->m_Name = name;
	this->m_DeptId = dId;
}

//显示个人信息
void Boss::showInfo() {
	cout << "职工编号：" << this->m_Id
		<< "\t职工姓名：" << this->m_Name
		<< "\t职工岗位：老板" << endl;
}

//获取岗位名称
string Boss::getDeptName() {
	return string("老板");
}
```

##### manager.cpp

```c++
#include"manager.h"

Manager::Manager(int id, string name, int dId) {
	this->m_Id = id;
	this->m_Name = name;
	this->m_DeptId = dId;
}

//显示个人信息
void Manager::showInfo() {
	cout << "职工编号：" << this->m_Id
		<< "\t职工姓名：" << this->m_Name
		<< "\t职工岗位：经理" << endl;
}

//获取岗位名称
string Manager::getDeptName() {
	return string("经理");
}
```

##### employee.cpp

```c++
#include"employee.h"

Employee::Employee(int id, string name, int dId) {
	this->m_Id = id;
	this->m_Name = name;
	this->m_DeptId = dId;
}

//显示个人信息
void Employee::showInfo() {
	cout << "职工编号：" << this->m_Id
		<< "\t职工姓名：" << this->m_Name
		<< "\t职工岗位：普通员工" << endl;
}

//获取岗位名称
string Employee::getDeptName() {
	return string("普通员工");
}
```

##### workerManager.cpp

```c++
#include"workerManager.h"

WorkManager::WorkManager() {
	ifstream ifs;
	ifs.open(FILENAME, ios::in);

	//1、文件不存在
	if (!ifs.is_open()) {
		cout << "文件不存在" << endl;
		this->m_EmpNum = 0;
		this->m_EmpArray = NULL;
		this->m_FileIsEmpty = true;
		return;
	}

	//2、文件存在，数据为空
	char ch;
	ifs >> ch;
	if (ifs.eof()) {
		cout << "文件为空" << endl;
		this->m_EmpNum = 0;
		this->m_EmpArray = NULL;
		this->m_FileIsEmpty = true;
		return;
	}

	//3、文件存在，并且记录数据
	int num = this->get_EmpNum();
	this->m_EmpNum = num;
	cout << "职工人数为：" << num << "人" << endl;

	this->m_EmpArray = new Worker * [this->m_EmpNum];
	this->init_Emp();//初始化数组
}

WorkManager::~WorkManager() {
	if (this->m_EmpArray != NULL) {
		delete[] this->m_EmpArray;
		this->m_EmpArray = NULL;
	}
}

//统计文件中人数
int WorkManager::get_EmpNum() {
	ifstream ifs;
	ifs.open(FILENAME, ios::in);//打开文件 读
	
	int id;
	string name;
	int dId;

	int num = 0;
	while (ifs >> id && ifs >> name && ifs >> dId)
	{
		num++;
	}

	return num;
}

//初始化数组
void WorkManager::init_Emp() {
	ifstream ifs;
	ifs.open(FILENAME, ios::in);

	int id;
	string name;
	int dId;

	int index = 0;
	while (ifs >> id && ifs >> name && ifs >> dId)
	{
		Worker* worker = NULL;
		switch (dId)
		{
		case 1:
			worker = new Employee(id, name, 1);
			break;
		case 2:
			worker = new Manager(id, name, 2);
			break;
		case 3:
			worker = new Boss(id, name, 3);
			break;
		default:
			break;
		}
		this->m_EmpArray[index] = worker;
		index++;
	}

	ifs.close();
}

//保存文件
void WorkManager::save() {
	ofstream ofs;
	ofs.open(FILENAME, ios::out);//用输出的方式打开文件--写文件

	for (int i = 0; i < this->m_EmpNum; i++) {
		ofs << this->m_EmpArray[i]->m_Id << " "
			<< this->m_EmpArray[i]->m_Name << " "
			<< this->m_EmpArray[i]->m_DeptId << endl;
	}

	ofs.close();
}

//打印菜单
void WorkManager::Show_Menu() {
	cout << "************************" << endl;
	cout << "欢迎使用职工管理系统" << endl;
	cout << "1、增加职工信息" << endl;
	cout << "2、显示职工信息" << endl;
	cout << "3、删除离职职工" << endl;
	cout << "4、修改职工信息" << endl;
	cout << "5、查找职工信息" << endl;
	cout << "6、按照编号排序" << endl;
	cout << "7、清空所有文档" << endl;
	cout << "0、退出管理程序" << endl;
	cout << "************************" << endl;
	cout << endl;
}

//添加职工
void WorkManager::Add_Emp() {
	cout << "请输入需要添加职工数量：" << endl;
	int addNum = 0;
	cin >> addNum;

	if (addNum > 0)
	{
		int newSize = this->m_EmpNum + addNum;

		//开辟新空间
		Worker** newSpace = new Worker * [newSize];

		//下载原有数据
		if (this->m_EmpArray != NULL)
		{
			for (int i = 0; i < this->m_EmpNum; i++) {
				newSpace[i] = this->m_EmpArray[i];
			}
		}

		//批量添加新数据
		for (int i = 0; i < addNum; i++) {
			int id;//职工编号
			string name;//职工姓名
			int dSelect;//部门选择

			//输入信息
			cout << "请输入第" << i + 1 << "个新职工的编号：" << endl;
			cin >> id;
			cout << "请输入第" << i + 1 << "个新职工的姓名：" << endl;
			cin >> name;
			cout << "请选择职工岗位：" << endl;
			cout << "1、普通职工" << endl;
			cout << "2、经理" << endl;
			cout << "3、老板" << endl;
			cin >> dSelect;

			//创建对象
			Worker* worker = NULL;
			switch (dSelect)
			{
			case 1:
				worker = new Employee(id, name, 1);
				break;
			case 2:
				worker = new Manager(id, name, 2);
				break;
			case 3:
				worker = new Boss(id, name, 3);
				break;
			default:
				break;
			}

			//加入数组
			newSpace[this->m_EmpNum + i] = worker;
		}

		//释放原有空间
		delete[] this->m_EmpArray;
		//指向新空间
		this->m_EmpArray = newSpace;
		//更新人数
		this->m_EmpNum = newSize;
		//文件不为空
		this->m_FileIsEmpty = false;
		//保存数据到文件中
		this->save();

		cout << "成功添加" << addNum << "名新职工" << endl;
	}
	else
	{
		cout << "输出有误" << endl;
	}
}

//显示职工
void WorkManager::Show_Emp() {
	//判断文件是否为空
	if (this->m_FileIsEmpty)
	{
		cout << "文件不存在或记录为空" << endl;
	}
	else
	{
		for (int i = 0; i < m_EmpNum; i++) {
			this->m_EmpArray[i]->showInfo();
		}
	}
	system("pause");
	system("cls");
}

//删除员工
void WorkManager::Del_Emp() {
	if (this->m_FileIsEmpty)
	{
		cout << "文件不存在或记录为空" << endl;
	}
	else
	{
		cout << "请输入需要删除职工的编号：" << endl;
		int id = -1;
		cin >> id;

		int index = this->IsExist(id);

		if (index != -1)
		{
			delete this->m_EmpArray[index];
			for (int i = index; i < this->m_EmpNum - 1; i++) {
				this->m_EmpArray[i] = this->m_EmpArray[i + 1];
			}
			this->m_EmpNum--;
			this->save();
			cout << "删除成功" << endl;
		}
		else
		{
			cout << "删除失败，未找到该员工" << endl;
		}
	}

	system("pause");
	system("cls");
}

//判断员工是否存在，如果存在返回员工所在数组位置，不存在返回-1
int WorkManager::IsExist(int id) {
	int index = -1;

	for (int i = 0; i < this->m_EmpNum; i++) {
		if (this->m_EmpArray[i]->m_Id == id) {
			return i;
		}
	}

	return index;
}

//修改职工
void WorkManager::Mod_Emp() {
	if (this->m_FileIsEmpty) 
	{
		cout << "文件不存在或文件为空" << endl;
	}
	else
	{
		cout << "请输入修改职工的编号：" << endl;
		int id;
		cin >> id;

		int ret = this->IsExist(id);
		if (ret != -1)
		{
			delete this->m_EmpArray[ret];

			int newId;
			string newName;
			int dSelect;

			cout << "查到：" << id << "号职工，请输入新职工号：" << endl;
			cin >> newId;
			cout << "请输入新姓名" << endl;
			cin >> newName;
			cout << "请输入岗位：" << endl;
			cout << "1、普通职工" << endl;
			cout << "2、经理" << endl;
			cout << "3、老板" << endl;
			cin >> dSelect;

			Worker* worker = NULL;
			switch (dSelect)
			{
			case 1:
				worker = new Employee(newId, newName, 1);
				break;
			case 2:
				worker = new Manager(newId, newName, 2);
				break;
			case 3:
				worker = new Boss(newId, newName, 3);
				break;
			default:
				break;
			}

			this->m_EmpArray[ret] = worker;
			cout << "修改成功" << endl;
			this->save();
		}
		else
		{
			cout << "查无此人" << endl;
		}
	}
	system("pause");
	system("cls");
}

//查找职工
void WorkManager::Find_Emp() {
	if (this->m_FileIsEmpty)
	{
		cout << "文件不存在或文件为空" << endl;
	}
	else {
		cout << "请输入查找的方式：" << endl;
		cout << "1、按职工编号查找" << endl;
		cout << "2、按职工姓名查找" << endl;

		int select = 0;
		cin >> select;

		if (select == 1)
		{
			int id;
			cout << "请输入查找的职工编号：" << endl;
			cin >> id;

			int ret = IsExist(id);
			if (ret != -1)
			{
				cout << "查找成功！该职工信息如下：" << endl;
				this->m_EmpArray[ret]->showInfo();
			}
			else
			{
				cout << "查无此人" << endl;
			}
		}
		else if(select == 2)
		{
			string name;
			cout << "请输入查找的职工姓名：" << endl;
			cin >> name;
			bool flag = false;

			for (int i = 0; i < this->m_EmpNum; i++) {
				if (this->m_EmpArray[i]->m_Name == name) {
					cout << "查找成功，该职工信息如下：" << endl;
					this->m_EmpArray[i]->showInfo();
					flag = true;
				}
			}
			if (!flag)
			{
				cout << "查无此人" << endl;
			}
		}
		else
		{
			cout << "输入有误" << endl;
		}
	}
	system("pause");
	system("cls");
}

//按照编号排序
void WorkManager::Sort_Emp() {
	if (this->m_FileIsEmpty)
	{
		cout << "文件不存在或文件为空" << endl;
		system("pause");
		system("cls");
	}
	else
	{
		cout << "请选择排序方式" << endl;
		cout << "1、按职工号进行升序" << endl;
		cout << "2、按职工号进行降序" << endl;

		int select = 0;
		cin >> select;
		for (int i = 0; i < this->m_EmpNum; i++) {
			int minOrMax = i;
			for (int j = i + 1; j < this->m_EmpNum; j++) {
				if (select == 1)
				{
					if (this->m_EmpArray[minOrMax]->m_Id > this->m_EmpArray[j]->m_Id)
					{
						minOrMax = j;
					}
				}
				else
				{
					if (this->m_EmpArray[minOrMax]->m_Id < this->m_EmpArray[j]->m_Id)
					{
						minOrMax = j;
					}
				}
			}
			if (i != minOrMax) {
				Worker* temp = this->m_EmpArray[i];
				this->m_EmpArray[i] = this->m_EmpArray[minOrMax];
				this->m_EmpArray[minOrMax] = temp;
			}
		}
		cout << "排序成功，结果如下:" << endl;
		this->save();
		this->Show_Emp();
	}
}

//清空文件
void WorkManager::Clean_File() {
	if (this->m_FileIsEmpty)
	{
		cout << "文件不存在或文件为空" << endl;
	}
	else
	{
		cout << "确定清空？" << endl;
		cout << "1、确定" << endl;
		cout << "2、返回" << endl;
		
		int select;
		cin >> select;

		if (select == 1)
		{
			ofstream ofs(FILENAME, ios::trunc);//删除文件后重新创建
			ofs.close();

			if (this->m_EmpArray != NULL) {
				for (int i = 0; i < this->m_EmpNum; i++) {
					delete this->m_EmpArray[i];
					this->m_EmpArray[i] = NULL;
				}

				delete[] this->m_EmpArray;
				this->m_EmpNum = 0;
				this->m_FileIsEmpty = true;
			}
			cout << "清空成功" << endl;
		}
	}
	system("pause");
	system("cls");
}

//退出系统
void WorkManager::ExitSystem() {
	cout << "欢迎下次使用" << endl;
	system("pause");
	exit(0);
}
```

##### 职工管理系统.cpp

```c++
#include<iostream>
#include"workerManager.h"
#include"worker.h"
#include"employee.h"
#include"manager.h"
#include"boss.h"
using namespace std;

int main() {
	//实例化管理者对象
	WorkManager wm;

	//用户选择选项
	int choice = 0;

	while (true)
	{
		//调用展示菜单成员函数
		wm.Show_Menu();

		cout << "请输入您的选择：" << endl;
		cin >> choice;

		switch (choice)
		{
		case 1://增加职工
			wm.Add_Emp();
			break;
		case 2://显示职工
			wm.Show_Emp();
			break;
		case 3://删除职工
			wm.Del_Emp();
			break;
		case 4://修改职工
			wm.Mod_Emp();
			break;
		case 5://查找职工
			wm.Find_Emp();
			break;
		case 6://排序职工
			wm.Sort_Emp();
			break;
		case 7://清空文档
			wm.Clean_File();
			break;
		case 0://退出系统
			wm.ExitSystem();
			break;
		default:
			system("cls");
			break;
		}
	}

	return 0;
}
```



## 15 模板

### 01 模板的模板语法

```c++
#include<iostream>
using namespace std;

//函数模板
template<typename T>

void mySwap(T& a, T& b) {
	T temp = a;
	a = b;
	b = temp;
}

int main() {
	int a = 10;
	int b = 20;

	//利用函数模板交换
	//1、自动类型推导
	mySwap(a, b);
	cout << "a = " << a << endl;
	cout << "b = " << b << endl;

	//2、显示指定类型
	mySwap<int>(a, b);
	cout << "a = " << a << endl;
	cout << "b = " << b << endl;

	return 0;
}
```



### 02 函数模板注意事项

```c++
#include<iostream>
using namespace std;

template<class T>//typename可以替换成class
void mySwap(T& a, T& b) {
	T temp = a;
	a = b;
	b = temp;
}

//函数模板注意事项
//1、自动类型推导，必须推导出一致的数据类型T才能使用
void test02() {
	int a = 10;
	int b = 20;

	mySwap(a, b);
	cout << a << " " << b << endl;

	char c = 'c';
	//mySwap(a, c); 错误，T不一致
}

//2、模板必须要确定出T的数据类型，才能使用 
template<class T>
void func() {
	cout << "func调用" << endl;
}

void test02_2() {
	func<int>();
	//func();错误
}

int main() {
	test02();
	test02_2();

	return 0;
}
```



### 03 函数模板案例-数组排序

```c++
#include<iostream>
using namespace std;

template<class T>
void mySwap(T& a, T& b) {
	T temp = a;
	a = b;
	b = temp;
}

template<class T>
void mySort(T arr[], int len) {
	for (int i = 0; i < len; i++) {
		int max = i;
		for (int j = i; j < len; j++) {
			if (arr[max] < arr[j]) {
				max = j;
			}
		}
		if (max != i) {
			mySwap(arr[max], arr[i]);
		}
	}
}

template<class T>
void printArr(T arr[], int len) {
	for (int i = 0; i < len; i++) {
		cout << arr[i] << " ";
	}
}

void test03() {
	char charArr[] = "badcfe";
	int num = sizeof(charArr) / sizeof(char);

	mySort(charArr, num);
	printArr(charArr, num);
}

void test03_2() {
	int intArr[] = { 7,4,5,2,6,3,1 };
	int num = sizeof(intArr) / sizeof(int);

	mySort(intArr, num);
	printArr(intArr, num);
}

int main() {
	test03();
	test03_2();

	return 0;
}
```



### 04 普通函数与函数模板区别

```c++
#include<iostream>
using namespace std;

//1、普通函数调用可以发生隐式转换
//2、函数模板 自动类型推导，不可以发生隐式转换
//3、函数模板 用显示指定类型，可以发生隐式转换

int myAdd(int a, int b) {
	return a + b;
}

template<class T>
T myAdd2(T a, T b) {
	return a + b;
}

void test04() {
	cout << myAdd(10, 'c') << endl;//c->99

	//cout << myAdd2(10, 'c') << endl;错误

	cout << myAdd2<int>(10, 'c') << endl;//c->99
}

int main() {
	test04();

	return 0;
}
```



### 05 普通函数和函数模板调用规则

```c++
#include<iostream>
using namespace std;

//普通函数与函数模板调用规则
//1、如果函数模板和普通函数都可以调用，优先调用普通函数
//2、可以通过空模板参数列表强制调用函数模板
//3、函数模板可以发生函数重载
//4、如果函数模板可以产生更好的匹配，优先调用函数模板

void myPrint(int a, int b) {
	cout << "普通函数" << endl;
}

template<class T>
void myPrint(T a, T b) {
	cout << "函数模板" << endl;
}

template<class T>
void myPrint(T a) {
	cout << "重载函数模板" << endl;
}

void test05() {
	int a = 10;
	int b = 20;

	myPrint(a, b);
	myPrint<>(a, b);
	myPrint(a);

	char c = 'c';
	char d = 'd';
	myPrint(c,d);
}

int main() {
	test05();

	return 0;
}
```



### 06 模板的局限性

```c++
#include<iostream>
#include<string>
using namespace std;

class Person {
public:
	Person(string name, int age) {
		m_Name = name;
		m_Age = age;
	}
	string m_Name;
	int m_Age;
};

template<class T>
bool myCompare(T& a, T& b) {
	if (a == b) {
		return true;
	}
	return false;
}

//利用具体化Person版本实现代码
template<>bool myCompare(Person& a, Person& b) {
	if (a.m_Name == b.m_Name && a.m_Age == b.m_Age) {
		return true;
	}
	return false;
}

void test06() {
	Person p1("张三", 10);
	Person p2("张三", 10);

	cout << myCompare(p1, p2) << endl;
}

int main() {
	test06();

	return 0;
}
```

