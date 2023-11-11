# GDB

## 一、搭建环境

下载

```shell
yum install gdb
```

检查

```shell
gdb --version
```





## 二、编写及编译

c++测试程序：test.cpp

```c++
#include <iostream>

using namespace std;

int main() {
	int arr[] = {1,2,3,4,5,6,7,8,9,0};

	for (size_t i = 0; i < 10; i++)
	{
		cout << arr[i] << " ";
	}
	

	return 0;
}
```

编译

+ -g ##可调试

```shell
g++ -g test.cpp
```



## 三、执行调试

进入调试

```shell
gdb ./a.out
```

+ run/r ##立即执行代码，跑完整个代码
+ list ##查看代码
+ break/b ##打断点
  + b (function) ##在某个函数打断点
  + b (number) ##在行号处打断点
+ info (message) ##查看信息
  + info b ##查看断电信息
+ next/n ##执行下一步
+ step ##进入函数
+ print/p (expr) ##查看变量的值(可以是地址)
  + print i ##查看i变量的值
  + print &arr[0] ##查看arr[0]地址
+ quit/q ##退出gdb
+ shell (shell command) ##调用终端命令
+ set logging on ##开启日志功能



## 四、调试core文件

程序发生错误生成的core文件

查看ulimit

```shell
man ulimit
```

一般ulimit会做出限制，不生成core文件，手动开启

```shell
ulimit -c unlimit
```

ulimit -a ##查看当前所有的属性

开始调试

```shell
gdb ./a.out core.xxxx
```



## 五、调试正在运行的程序

让程序后台运行(会执行后返回一个pid)

```shell
./a.out &
```

调试正在运行的进程
-p (pid) ##调试该pid的进程

```shell
gdb -p xxxx
```

相关操作和调试二进制文件一致