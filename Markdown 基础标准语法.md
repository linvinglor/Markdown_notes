# Markdown 基础标准语法

可以查看这里：[Markdown 基础标准语法](http://note.youdao.com/noteshare?id=40988983718ff8590bbdceb2d576e2c2&sub=6D1E4A19AFE34B90BE55BB82DD397738)

# \# 标题

标题：# + 空格。

通过 # 号的个数表示几级标题。（一共只有1~6级标题，1级标题字体最大）

例如：
```
# 这是一级标题
## 这是二级标题
### 这是三级标题
#### 这是四级标题
##### 这是五级标题
###### 这是六级标题
```
效果如下：
# 这是一级标题
## 这是二级标题
### 这是三级标题
#### 这是四级标题
##### 这是五级标题
###### 这是六级标题

# 表格 |\-\-\-|
表格的对齐方式：
1. 居左：  :---
2. 居中：  :---:
3. 居右：  ---:
例如：
```
|标题1|标题2|标题3|标题4|
|:---|:---:|:---:|---:|
|居左对齐|居中对齐|居中对齐|居右对齐|
|吃饭|睡觉|玩游戏|打豆豆|
|苹果|橘子|香蕉|芒果|
```

效果如下：
|标题1|标题2|标题3|标题4|
|:---|:---:|:---:|---:|
|居左对齐|居中对齐|居中对齐|居右对齐|
|吃饭|睡觉|玩游戏|打豆豆|
|苹果|橘子|香蕉|芒果|


## 无序列表
无需列表使用 -/+/* + 空格。例如：
```
- 无序列表1
- 无需列表2
- 无序列表3

* 无序列表4
* 无序列表5
* 无序列表6

+ 无序列表7
+ 无序列表8
+ 无序列表9
```
效果如下：

- 无序列表1
- 无需列表2
- 无序列表3

* 无序列表4
* 无序列表5
* 无序列表6

+ 无序列表7
+ 无序列表8
+ 无序列表9

## 有序列表
有序列表：数字 + 英文符号 . + 空格。例如：
```
1. 有序列表01
2. 有序列表02
3. 有序列表03
```
效果如下：
1. 有序列表01
2. 有序列表02
3. 有序列表03
***

# 引用(注释)
引用：大于号 > + 空格。例如：
```
> 这是引用

> 这段内容是引用的格式，接下来让我们看一下引用的格式是什么样子。首先，字体是灰色的，然后与正常字体的大小是一样的，而且每行字的最前面有一个竖线。

> 原来，MarkDown中空一行就代表换行，就像下面这样

> 看，是不是换行了。

> 当 > 和文字之间添加 5个blank（空格）时，块注释的文字会有变化。

>     下面这段文字会显示在一个引用框里面。
>     换行的时候要重新使用大于号和5个空格。
```

效果如下：

> 这是引用

> 这段内容是引用的格式，接下来让我们看一下引用的格式是什么样子。首先，字体是灰色的，然后与正常字体的大小是一样的，而且每行字的最前面有一个竖线。

> 原来，MarkDown中空一行就代表换行，就像下面这样

> 看，是不是换行了。

> 当 > 和文字之间添加 5个blank（空格）时，块注释的文字会有变化。

>     下面这段文字会显示在一个引用框里面。
>     换行的时候要重新使用大于号和5个空格。

# 图片、链接

### 图片
```
图片：![图片文本](图片url)
```
其中，图片文本可以忽略不写。
### 链接（Link）
Markdown有两种方式实现链接：内联方式 和 引用方式

```
内联方式：[链接文本](链接url)
```

例如：
```
- [搜狗](http://www.sogou.com)
- [百度](http://www.baidu.com)
- [Markdown入门语法](http://www.jianshu.com/p/1e402922ee32/)
```

效果如下：

- [搜狗](http://www.sogou.com)
- [百度](http://www.baidu.com)
- [Markdown入门语法](http://www.jianshu.com/p/1e402922ee32/)

### 链接——引用方式：
例如：
```
I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

[1]: http://google.com/        "Google"
[2]: http://search.yahoo.com/  "Yahoo Search"
[3]: http://search.msn.com/    "MSN Search"
```

效果如下：

I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

[1]: http://google.com/        "Google"
[2]: http://search.yahoo.com/  "Yahoo Search"
[3]: http://search.msn.com/    "MSN Search"

# 粗体、斜体

### 粗体
粗体：两个 * 号。例如：
```
**这一段文字是以粗体显示的。**
```

效果如下：

**这一段文字是以粗体显示的。**

### 斜体

斜体：一个 * 号。例如：

```
*这一段文字是以斜体显示的。*
```

效果如下：

*这一段文字是以斜体显示的。*

# 分隔线

使用三个 * 、 - 、 _ 表示横线


三个星号标识分隔线

***

三个中划线标识分隔线

---

三个下划线标识分隔线

___

# 代码
代码分为：行内代码、代码块

### 行内代码

行内代码：使用 \`代码\` 表示，可以嵌入文字中。例如：

```
这是行内代码`HttpURLConnection con = (HttpURLConnection) url.openConnection()`可以嵌入文字中
```
效果如下：

这是行内代码`HttpURLConnection con = (HttpURLConnection) url.openConnection()`可以嵌入文字中

### 代码块

代码块：三个```。例如：

```
var myObject = {
    firstName:"John",
    lastName: "Doe",
    fullName: function () {
        return this.firstName + " " + this.lastName;
    }
}
myObject.fullName();         // 返回 "John Doe"
```

### 代码块高亮

代码块高亮：在三个```后加上代码语言名称。

例如：```java

```java
var myObject = {
    firstName:"John",
    lastName: "Doe",
    fullName: function () {
        return this.firstName + " " + this.lastName;
    }
}
myObject.fullName();         // 返回 "John Doe"
```

# Markdown换行

- 软换行：空格+空格+回车
- 硬换行
- 两段文字之间空出一行，即：回车+回车
- 使用HTML标签`<br/>`

# 设置字体、字体大小和颜色

Markdown可以使用HTML标签设置字体、字体大小和颜色。例如：

```
<font face="微软雅黑" color="red" size="6">字体及字体颜色和大小</font>
<font color="#0000ff">字体颜色</font>
```

效果如下：

<font face="微软雅黑" color="red" size="6">字体及字体颜色和大小</font>
<font color="#0000ff">字体颜色</font>

# 文本对齐方式

```
<p align="left">内容左对齐<p>
<p align="center">内容居中<p>
<p align="right">内容右对齐<p>
```

效果如下：

<p align="left">内容左对齐<p>
<p align="center">内容居中<p>
<p align="right">内容右对齐<p>

# 下划线
```
<u>需要加下划线的文本</u>
```

效果如下：

<u>需要加下划线的文本</u>

#### 注意：并不是支持Markdown就一定支持HTML标签，具体还要灵活使用。