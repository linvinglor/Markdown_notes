# Python基础知识
tags:Python Python基础 Python笔记

----

# 编写 Python 的3种方式
1. sublime + shell
2. vi编辑器
3. pycharm

# Python 注释
- #号：表示单行注释。
- 三个双引号或三个单引号：表示多行注释。

# Python 中有中文
+ Python 中如果出现中文，不管是 Python 代码中有中文，还是 Python 注释中有中文，Python2 都需要在开头位置加上：# coding=utf-8
+ Python3 则不需要加。

# Python 的交互模式 ipython

在 Linux shell 中输入 ipython，即可进入Python的交互窗口。

在ipython中即可以输入Python命令，也可以输入Linux命令。

但是要注意：并不是所有的Linux都支持ipython命令。

# python变量和数据类型

Python是弱类型语言，变量不需要声明，可以直接使用。

如何知道变量a是什么类型的变量？

使用type()函数：type(a)

# input()

input()获取的所有数据，都当做字符串类型。

input()获取的内容，如果要和数字比较大小，需要进行类型转换，将string类型转换成int类型。

```python
age = input("请输入你的年龄：")

# 类型转换
age_num = int(age)

if age_num > 18:
    print("你的年龄大于18，已经成年了。。。")
```

# 标识符

标识符：开发人员在程序中自定义的一些符号和名称。

标识符：是开发人员自己定义的，如：变量名、函数名。

## 标识符的命名规则

- 由字母、数字、下划线组成
- 不能以数字开头
- 区分大小写
- python推荐命名方式：english_score

## 驼峰命名规则

- 小驼峰：englingScore
- 大驼峰：EnglishScore

使用驼峰法进行命名是可以的，但是推荐english_score。

## 关键字

关键字：具有特殊功能的标识符，直白来说就是：变量名。

关键字是Python已经使用的，不允许用户定义和关键字同名的变量名。

如何在Linux shell中查看Python关键字？
```python
import keyword
keyword.kwlist
```

# 运算符

```python
a=5
b=2

a+b
a-b
a*b
a/b
a//b    #取商
a%b     #取余
2**3    #2的3次方，幂
"H"*10    #10个H，"HHHHHHHHHH"
```

复合赋值运算符

- +=
- -=
- *=
- /=
- //=
- %=
- **=

注意，复合运算符有一个陷阱：
`a*=34-31+44-22`等价于`a*(34-31+44-22)`,而不是`a+34-31+44-22`

# print()

一次输出多个变量的值：

```
print("你的名字：%s" & name)
print("你的名字:%s, 年龄: %d, 性别:%s" % (name,age,sex))
```

不换行，加上`end=""`或者`end=''`：

如果`end=""`提示语法错误，请使用Python3

```python
a="Barry"
b="Allen"
print(a, end="")
print(b)
```

打印出来的结果是：`BarryAllen`
而不是：
`Barry`
`Allen`

换行，`print("")`默认就是换行。

# 判断

if...elif...else

# 循环

while

# 打印三角形

```python
# 打印三角形

i = 1
#i 第一个循环，控制行数
while i <=5:
	j = 1
	#j 第二个循环，控制列数
	while j<=i:
		print("*", end="")
		j=j+1
	print("")
	i=i+1
```

# 打印99乘法表

在打印三角形的基础上修改代码，打印99乘法表。

```python
# 打印99乘法表

i=1
while i<=9:
	j=1
	while j<=i:
		print("%d*%d=%d " %(j, i, j*i), end="")
		j+=1
	print("")
	i+=1
```

# \t

`print("a\tb")`，\t表示一个tab键（4个空格）

`print("a\nb")` ，\n表示换行。

# random 随机数

使用random随机数写的猜拳小游戏

·# Python基础知识
tags:Python Python基础 Python笔记

----

# 编写 Python 的3种方式
1. sublime + shell
2. vi编辑器
3. pycharm

# Python 注释
- #号：表示单行注释。
- 三个双引号或三个单引号：表示多行注释。

# Python 中有中文
+ Python 中如果出现中文，不管是 Python 代码中有中文，还是 Python 注释中有中文，Python2 都需要在开头位置加上：# coding=utf-8
+ Python3 则不需要加。

# Python 的交互模式 ipython

在 Linux shell 中输入 ipython，即可进入Python的交互窗口。

在ipython中即可以输入Python命令，也可以输入Linux命令。

但是要注意：并不是所有的Linux都支持ipython命令。

# python变量和数据类型

Python是弱类型语言，变量不需要声明，可以直接使用。

如何知道变量a是什么类型的变量？

使用type()函数：type(a)

# input()

input()获取的所有数据，都当做字符串类型。

input()获取的内容，如果要和数字比较大小，需要进行类型转换，将string类型转换成int类型。

```python
age = input("请输入你的年龄：")

# 类型转换
age_num = int(age)

if age_num > 18:
    print("你的年龄大于18，已经成年了。。。")
```

# 标识符

标识符：开发人员在程序中自定义的一些符号和名称。

标识符：是开发人员自己定义的，如：变量名、函数名。

## 标识符的命名规则

- 由字母、数字、下划线组成
- 不能以数字开头
- 区分大小写
- python推荐命名方式：english_score

## 驼峰命名规则

- 小驼峰：englingScore
- 大驼峰：EnglishScore

使用驼峰法进行命名是可以的，但是推荐english_score。

## 关键字

关键字：具有特殊功能的标识符，直白来说就是：变量名。

关键字是Python已经使用的，不允许用户定义和关键字同名的变量名。

如何在Linux shell中查看Python关键字？
```python
import keyword
keyword.kwlist
```

# 运算符

```python
a=5
b=2

a+b
a-b
a*b
a/b
a//b    #取商
a%b     #取余
2**3    #2的3次方，幂
"H"*10    #10个H，"HHHHHHHHHH"
```

复合赋值运算符

- +=
- -=
- *=
- /=
- //=
- %=
- **=

注意，复合运算符有一个陷阱：
`a*=34-31+44-22`等价于`a*(34-31+44-22)`,而不是`a+34-31+44-22`

# print()

一次输出多个变量的值：

```
print("你的名字：%s" & name)
print("你的名字:%s, 年龄: %d, 性别:%s" % (name,age,sex))
```

不换行，加上`end=""`或者`end=''`：

如果`end=""`提示语法错误，请使用Python3

```python
a="Barry"
b="Allen"
print(a, end="")
print(b)
```

打印出来的结果是：`BarryAllen`
而不是：
`Barry`
`Allen`

换行，`print("")`默认就是换行。

# 判断

if...elif...else

# 循环

while

# 打印三角形

```python
# 打印三角形

i = 1
#i 第一个循环，控制行数
while i <=5:
	j = 1
	#j 第二个循环，控制列数
	while j<=i:
		print("*", end="")
		j=j+1
	print("")
	i=i+1
```

# 打印99乘法表

在打印三角形的基础上修改代码，打印99乘法表。

```python
# 打印99乘法表

i=1
while i<=9:
	j=1
	while j<=i:
		print("%d*%d=%d " %(j, i, j*i), end="")
		j+=1
	print("")
	i+=1
```

# \t

`print("a\tb")`，\t表示一个tab键（4个空格）

`print("a\nb")` ，\n表示换行。

# random 随机数

使用random随机数写的猜拳小游戏

```python
#随机数random
import random

#让用户输入
player=int(input("请输入：0剪刀 1石头 2布:"))
computer=random.randint(0,2)
#比较，得出猜拳结果
if (player==0 and computer==1) or (player==1 and computer==2) or (player==1 and computer==0):
	print("哎呀，你竟然赢了，好厉害！")
elif player==computer:
	print("平局！不要走，来决战到天亮...")
else:
	print("哈哈，你输了！")

```

