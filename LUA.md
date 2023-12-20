# LUA

老牛逼的脚本语言，轻量化的脚本语言，嵌入式开发特别合适

## 环境



## print

打印输出

```lua
print('hello world')
```

echo

```
hello world
```



## 注释

```lua
--单行注释
--[[
多行注释
--]]
```



## 数据类型

| 数据类型 | 描述                                                         |
| :------- | :----------------------------------------------------------- |
| nil      | 这个最简单，只有值nil属于该类，表示一个无效值（在条件表达式中相当于false）。 |
| boolean  | 包含两个值：false和true。                                    |
| number   | 表示双精度类型的实浮点数                                     |
| string   | 字符串由一对双引号或单引号来表示                             |
| function | 由 C 或 Lua 编写的函数                                       |
| userdata | 表示任意存储在变量中的C数据结构                              |
| thread   | 表示执行的独立线路，用于执行协同程序                         |
| table    | Lua 中的表（table）其实是一个"关联数组"（associative arrays），数组的索引可以是数字、字符串或表类型。在 Lua 里，table 的创建是通过"构造表达式"来完成，最简单构造表达式是{}，用来创建一个空表。 |

```lua
print(type(1))
print(type(1.23))
print(type("ashbdu"))
print(type(print))
print(type(type))
print(type(nil))
```

echo

```
number
number  
string  
function
function
nil     
```



### nil

nil变量表示为空（null）

一个变量为定义也能使用，内容为nil，给一个数据赋值为nil，相当于回收了该数据的内存

```lua
tab1 = {k1 = 'k1',k2 = 'k2'}
tab1.k1 = nil --释放k1
tab1 = nil --释放tab1
```



### boolean

boolean类型有true和false，nil为false



### number

正数和浮点数都存为number

可以使用科学计数法biaoshi

```lua
print(1)
print(1.2)
print(1e4+9)
print(1e-3+2)
```

echo

```
1
1.2    
10009.0
2.001
```





### string

定义使用单引号和双引号都可以

多行字符串使用``[[]]``

`..` ：字符串加法运算

`+-*/` ：数字运算运算，字符串会转换成number

`#` ：获取字符串长度

```lua
str1 = '1111'
str2 = "2222"
str3 = 
[[
3333
3333
]]

print(str1)
print(str2)
print(str3)
print(str1..str2)
print('1' + '3')
print(1 .. 3)
print(#'hhhh')
```

echo

```
1111
2222
3333
3333

11112222
4
13
4
```



### table

`{}` ：table构造表达式

table可做字典`{key1=value1,key2=value2}`

table可做数组`{value1,value2}` 索引从1开始

```lua
tab1 = {}
tab2 = {key1 = 'hhhh',key2 = 1000}

print(tab1)
print(tab2.key1)
print(tab2['key2'])

tab3 = {'111','222','333','abcd'}
print(tab3[2])

tab3[1] = '1234'
tab3[10] = '9999'
for key, value in pairs(tab3) do
    print(key..' '..value)
end
```

echo

```
table: 0000016863BB2DB0
hhhh  
1000  
222   
1 1234
2 222 
3 333 
4 abcd
10 9999
```



### function

```lua
function func(n)
    if n == 1 then
        return n
    else
        return n*func(n-1)
    end
end

print(type(func))
print(func(3))

func2 = func

print(func2(5))
```

echo

```
function
6  
120
```



### thread



### userdata



## 变量

`local` ：局部变量声明

局部变量在生命周期直接掉用覆盖全局变量

变量赋值可以多个变量同时赋值，右值个数多余左值个数时，默认取前面的值

`a,b = b,a` ：swap

```lua
a = 5
print(type(a))
a = 'hello'
print(type(a))

do
    b = 5
    local c = 5
end

print(b)
print(c)

do
    local a = 10
    print(a)
end

print(a)
a,b = b,a
print(a,b)
```

echo

```
number
string       
5
nil
10
hello        
5       hello
```



## 循环

### while

```lua
while condition do
	statment
end
```

```lua
a = 1
while a < 5 do
    print(a)
    a = a + 1
end
```

echo

```
1
2
3
4
```



### for

数值for

```lua
for var=start,end[,step] do
	statement
end
```

```lua
for i = 10, 5, -1 do
    print(i)
end
```

echo

```
10
9
8
7
6
5
```

泛型for

```lua
tab = {1,2,3,4,5}
for key, value in pairs(tab) do
    print(value)
end
```

echo

```lua
1
2
3
4
5
```



### repeat until（do-while）

```lua
repeat
    steatment
until (state) == true
```



```lua
a = 5
repeat
    print(a)
    a = a - 1
until a < 3
```

echo

```
5
4
3
```



## 分支

```lua
if control1 then
    statement1
elseif control2 then
    statement2
else
    statement3
end
```



```lua
if true then
    print(1)
end

if false then
    print(0)
end

if true then
    print(1)
else
    print(0)
end

if false then
    print(0)
else
    print(1)
end

if 10 < 1 then
    print('10 < 1')
elseif 10 > 5 then
    print('10 > 5')
else
    print('over')
end
```



## function妙用

```lua
--[[
    [local] function functionName(arg1,arg2...)
        functionBody
        [return value1,value2...]
    end
--]]
```

```lua
local function max(num1,num2)
    if num1 > num2 then
        return num1
    else
        return num2
    end
end

print(max(10,20))

myFunc = function (param)
    print(param)
end

myFunc(100)

--多参数
local function test(...)
    local arg = {...}
    for key, value in pairs(arg) do
        print(key..value)
    end
end
test()
test(1,2,3,4)
```

echo

```
20
100
11
22
33
44
```



## 运算符

算数运算符

| 操作符 | 描述                 | 实例                |
| :----- | :------------------- | :------------------ |
| +      | 加法                 | A + B 输出结果 30   |
| -      | 减法                 | A - B 输出结果 -10  |
| *      | 乘法                 | A * B 输出结果 200  |
| /      | 除法                 | B / A 输出结果 2    |
| %      | 取余                 | B % A 输出结果 0    |
| ^      | 乘幂                 | A^2 输出结果 100    |
| -      | 负号                 | -A 输出结果 -10     |
| //     | 整除运算符(>=lua5.3) | **5//2** 输出结果 2 |

关系运算符

| 操作符 | 描述                                                         | 实例                  |
| :----- | :----------------------------------------------------------- | :-------------------- |
| ==     | 等于，检测两个值是否相等，相等返回 true，否则返回 false      | (A == B) 为 false。   |
| ~=     | 不等于，检测两个值是否相等，不相等返回 true，否则返回 false  | (A ~= B) 为 true。    |
| >      | 大于，如果左边的值大于右边的值，返回 true，否则返回 false    | (A > B) 为 false。    |
| <      | 小于，如果左边的值大于右边的值，返回 false，否则返回 true    | (A < B) 为 true。     |
| >=     | 大于等于，如果左边的值大于等于右边的值，返回 true，否则返回 false | (A >= B) 返回 false。 |
| <=     | 小于等于， 如果左边的值小于等于右边的值，返回 true，否则返回 false | (A <= B) 返回 true。  |

逻辑运算符

| 操作符 | 描述                                                         | 实例                   |
| :----- | :----------------------------------------------------------- | :--------------------- |
| and    | 逻辑与操作符。 若 A 为 false，则返回 A，否则返回 B。         | (A and B) 为 false。   |
| or     | 逻辑或操作符。 若 A 为 true，则返回 A，否则返回 B。          | (A or B) 为 true。     |
| not    | 逻辑非操作符。与逻辑运算结果相反，如果条件为 true，逻辑非为 false。 | not(A and B) 为 true。 |

其他运算符

| 操作符 | 描述                               | 实例                                                         |
| :----- | :--------------------------------- | :----------------------------------------------------------- |
| ..     | 连接两个字符串                     | a..b ，其中 a 为 "Hello " ， b 为 "World", 输出结果为 "Hello World"。 |
| #      | 一元运算符，返回字符串或表的长度。 | #"Hello" 返回 5                                              |



## 字符串

转义字符用于表示不能直接显示的字符，比如后退键，回车键等，如在字符串转换双引号可以使用 **\**。

所有的转义字符和所对应的意义：

| 转义字符 | 意义                                | ASCII码值（十进制） |
| -------- | ----------------------------------- | ------------------- |
| \a       | 响铃(BEL)                           | 007                 |
| \b       | 退格(BS) ，将当前位置移到前一列     | 008                 |
| \f       | 换页(FF)，将当前位置移到下页开头    | 012                 |
| \n       | 换行(LF) ，将当前位置移到下一行开头 | 010                 |
| \r       | 回车(CR) ，将当前位置移到本行开头   | 013                 |
| \t       | 水平制表(HT) （跳到下一个TAB位置）  | 009                 |
| \v       | 垂直制表(VT)                        | 011                 |
| \\       | 代表一个反斜线字符''\'              | 092                 |
| \'       | 代表一个单引号（撇号）字符          | 039                 |
| \"       | 代表一个双引号字符                  | 034                 |
| \0       | 空字符(NULL)                        | 000                 |
| \ddd     | 1到3位八进制数所代表的任意字符      | 三位八进制          |
| \xhh     | 1到2位十六进制所代表的任意字符      | 二位十六进制        |

Lua 提供了很多的方法来支持字符串的操作：

| 序号 | 方法 & 用途                                                  |
| :--- | :----------------------------------------------------------- |
| 1    | **string.upper(argument):** 字符串全部转为大写字母。         |
| 2    | **string.lower(argument):** 字符串全部转为小写字母。         |
| 3    | **string.gsub(mainString,findString,replaceString,num)**在字符串中替换。mainString 为要操作的字符串， findString 为被替换的字符，replaceString 要替换的字符，num 替换次数（可以忽略，则全部替换），如：`> string.gsub("aaaa","a","z",3); zzza  3` |
| 4    | **string.find (str, substr, [init, [plain]])** 在一个指定的目标字符串 str 中搜索指定的内容 substr，如果找到了一个匹配的子串，就会返回这个子串的起始索引和结束索引，不存在则返回 nil。**init** 指定了搜索的起始位置，默认为 1，可以一个负数，表示从后往前数的字符个数。**plain** 表示是否使用简单模式，默认为 false，true 只做简单的查找子串的操作，false 表示使用使用正则模式匹配。以下实例查找字符串 "Lua" 的起始索引和结束索引位置：`> string.find("Hello Lua user", "Lua", 1)  7  9` |
| 5    | **string.reverse(arg)** 字符串反转`> string.reverse("Lua") auL` |
| 6    | **string.format(...)** 返回一个类似printf的格式化字符串`> string.format("the value is:%d",4) the value is:4` |
| 7    | **string.char(arg) 和 string.byte(arg[,int])** char 将整型数字转成字符并连接， byte 转换字符为整数值(可以指定某个字符，默认第一个字符)。`> string.char(97,98,99,100) abcd > string.byte("ABCD",4) 68 > string.byte("ABCD") 65 >` |
| 8    | **string.len(arg)** 计算字符串长度。`string.len("abc") 3`    |
| 9    | **string.rep(string, n)** 返回字符串string的n个拷贝`> string.rep("abcd",2) abcdabcd` |
| 10   | **..** 链接两个字符串`> print("www.runoob.".."com") www.runoob.com` |
| 11   | **string.gmatch(str, pattern)** 返回一个迭代器函数，每一次调用这个函数，返回一个在字符串 str 找到的下一个符合 pattern 描述的子串。如果参数 pattern 描述的字符串没有找到，迭代函数返回nil。`> for word in string.gmatch("Hello Lua user", "%a+") do print(word) end Hello Lua user` |
| 12   | **string.match(str, pattern, init)** string.match()只寻找源字串str中的第一个配对. 参数init可选, 指定搜寻过程的起点, 默认为1。 在成功配对时, 函数将返回配对表达式中的所有捕获结果; 如果没有设置捕获标记, 则返回整个配对字符串. 当没有成功的配对时, 返回nil。`> = string.match("I have 2 questions for you.", "%d+ %a+") 2 questions > = string.format("%d, %q", string.match("I have 2 questions for you.", "(%d+) (%a+)")) 2, "questions"` |
