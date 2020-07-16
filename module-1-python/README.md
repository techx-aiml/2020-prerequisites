# 机器学习入门预习——Python 基础

## Python 的简介与安装

### Python 语言特性

- 高级语言，解释性强
- 速度快
- 模块
- 简单优雅


### 安装 Python

#### macOS
  - （推荐）前往 [Python 官网](https://www.python.org/downloads/) 下载任意 Python 3 “macOS 64 bit installer”，并按照安装程序指示安装。
  - Homebrew: 打开终端 （Terminal）并输入

```ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)" && brew install python```
  

#### Windows

前往 [Python官网](https://www.python.org/downloads/) 并根据 Windows 版本下载对应 Python 3 的 32 / 64bit 安装程序，并按照安装程序指示安装。务必记得勾选“Add Python 3.x to PATH”选项。

#### Linux

相信你已经熟悉了 Linux 并懂得如何安装，不然还是请使用 Mac 或 Windows 吧。


### 运行 Python

#### Mac

打开终端，并输入 `python3` 或 `python`（取决于你有没有安装 `python2`）并按下回车，如果安装成功你就会进入到 Python 交互式环境中，如下图所示：

![Mac Python 交互](https://i.loli.net/2020/07/07/jXs3q9NlP4ARDwn.gif)

#### Windows

请打开 CMD，输入 `python` 并按下回车，如果安装成功你就会进入到交互式环境中（图略，与上图类似）

> 至此你已经成功安装了Python，开始你的编程之旅吧！


### 第一个 Python 程序

进入你的 Python 交互式环境，在交互模式的提示符 `>>>` 下，直接输入代码，按回车，就可以立刻得到代码执行结果。

现在，试试输入 `1 + 1`，看看计算结果是不是`2`：

```python
>>> 1 + 1
2
```

是不是很简单！你也可以让 Python 任何一句话，只需要使用 `print()` 函数就可以了（不过你需要把文字用单/双引号括起来）：

```python
>>> print("hello world")
hello world
```

还有些一头雾水？不用担心，这些我们都会在后面更详细地讲解。现在我们需要退出交互环境，你只需要输入 `exit()` 并按下回车就可以了。

至此我们就完成了第一个 Python 程序，只不过它没有被存下来。当然，交互式环境也并不是为了编写代码用的，而更多是为了调试和方便初学者实验使用的。所以，后续学习和操作建议大家安装使用一个 IDE (Integrated Development Environment)，方便保存代码文件、运行和调试。常用的 IDE 有 PyCharm, VSCode 等。这么多选择，~~那挖掘机技术哪家强？~~那我们到底用哪个呢？如果没有特殊偏好我们推荐大家使用 VSCode，简单易用且跨平台。

当然，还有一种更硬核的方法：你可以在任意的文本编辑器里写好你的 `.py` 后缀的 Python 文件，并用终端运行。

比如我在 `~/TX/TX20/intro2ml/` 的文件路径下有一个名为 `helloWorld.py` 的 Python 程序想要运行，那我只需打开终端（对于 Windows 用户就是 CMD），利用 `cd` 命令跳转至该文件路径下，然后输入 `python3 helloWorld.py` 即可，如下图所示。

> 注：在终端中利用 `pwd` 可以查看当前文件路径

![Mac 终端运行 Python 文件](https://i.loli.net/2020/07/07/TLFXwG4I5mHrQxl.gif)



## 输入与输出

### 输出

就像之前说过的一样，如果我们想用 Python 在屏幕上打印字符串，只需要使用 `print()` 并在括号内加上字符串。

此外，`print` 函数也可以接受多个字符串，用逗号 `,` 隔开：

```python
>>> print("TechX", "2020:", "We choose to go to the moon")
TechX 2020: We choose to go to the moon
```

在上面的程序中，`print()` 会依次打印每个字符串，并在每两个字符串之间加上一个空格。

同时，`print()` 也能打印数字，因此也可以打印计算结果：

```python
>>> print(4 * 9 / 3)
12
```


### 输入

如果我们想让 Python 读取我们的自定义输入，我们只需要使用 `input()` 函数。比如：

```python
>>> name = input()
David # 这里指的是你在键盘上的输入
>>> name
'David' # 这里是name变量的内容
```

注意，Python 3 的 `input()` 函数接受一个标准输入数据，返回为 `str`，也就是说，即使你输入了一个数字，`input()` 的返回值仍然会是一个字符串。

那么如何输入数字呢？我们需要进行强制类型转换，例如 `num = int(input())`。这样一来，你输入的 `1` 会先经过 `input()` 变成 `'1'`，再经过转换变为 `1`。

要注意的是，如果这是你输入的是类似于 `abc` 的字符串，Python 会报错，因为无法把这些字符转化为数字。

关于类型转换我们在下面的数字类型部分也会提到。



## 基本数据类型

### 数字
Python支持两种不同的常用数值类型，分别是：

- 整数
  Python可以处理任意大小的正/负整数，和平常的写法一样，比如`2020`, `-1`, `0`等等。
  
- 浮点数
  浮点数就是小数，可以按照数学写法，比如`3.14`, `-6.6`。但对于很大或很小的浮点数，我们应该使用科学计数法，比如`6.67e-11`, `2.01e30`。

那我们如何进行数字类型的转换和运算呢？Python内置了以下几种函数来进行数字转换：

- `int(x)`将x转换为一个整数。

- `float(x)`将x转换到一个浮点数。

而Python的数字运算基本和计算器一致：
- `+`,`-`,`*`,`/`分别表示加减乘除，优先级遵守数学规则。值得注意的是`/`永远返回浮点数。
  ```python
  >>> 1 + 1
  2
  >>> 50 - 5 * 9
  5
  >>> 6 / 3
  2.0
  >>> 6 / 4
  1.5
  ```
- `//`和`%`分别表示整除和余数。
  ```python
  >>> 17 / 3
  5.666666666666667
  >>> 17 // 3
  5
  >>> 17 % 3
  2
  ```
- `**`表示幂运算
  ```python
  >>> 2 ** 2
  4
  >>> 4 ** 0.5
  2.0
  ```
- `=`表示赋值
  ```python
  >>> year = 2020
  >>> year
  2020
  ```
- `==`, `!=`, `>`, `>=`, `<`, `<=`都是比较符，分别表示等于，不等于，大于，大于等于，小于，小于等于。
- Python还内置了一些数学函数，常用的有：`sqrt(x)`, `abs(x)`, `log(x)`等。具体使用建议大家勤于去官方文档/Google查。

### 字符串
字符串是任意以`'`或`"`括起来的文本，比如`'zbc'`, `"aoligei"`等等。

如果字符串内部必须使用`'`或`"`等特殊符号，那么需要使用转义字符`\\`来标识，以防电脑误判：
```python
>>> print('I\'m \"OK\"!')
I'm "OK"!
```
这只是转义字符的其中一个用法，它还有很多其他的用途，比如`\n`表示换行，`\t`表示制表符/。

这样一来`\\`本身也需要转义，所以`\\\\`表示的就是`\\`这一字符。

### 布尔值
布尔值也是Python的数据类型之一。不同于前面的数字和字符，它只有两个取值：`True`或`False`。

布尔值描述的是真假；前面在数字运算符提到的比较符的返回值就是布尔值：

```python
>>> 1 == 2
False
>>> 1 <= 2
True
```

### 列表
列表（`list`）可以被用来有顺序地储存一系列值。举个例子：
```python
my_list = ['一段字符串', 1.618, 170001]
```
值得注意的是同一个列表中的值不需要是同一种类；它们可以是任何东西，包括但不限于数字、浮点、字符串、甚至是其他列表。

以下是一个包含其他列表的列表：
```python
nested_list = [[1, 2, 'abc'], [9, 10.2], ['niconiconi']]
```
想从一个列表中获取一个值也很容易，只用在列表变量后面加上方括号，并把目标值的位置写进去就可以：
```python
my_list = ['a', 'b', 'c']
print(my_list[1]) # b
print(my_list[2]) # c
print(my_list[0]) # a
```

列表的第一个元素的位置是0，第二个元素的位置是1，以此类推。

假设想从一个包含了其他列表的列表中获取其他列表中的值，那么需要叠加多个方括号：
```python
nested_list = [[1, 2, 'abc'], [9, 10.2], ['niconiconi']]

print(nested_list[0][2]) # abc
```

更改列表中某个位置上的值也很容易，只要用同样的方括号标出位置，并直接赋值就行：
```python
a_list = [5, 0.1, 'apple', 'banana']
a_list[3] = 32
print(a_list) # [5, 0.1, 'apple', 32]
```

列表是有“长度”的概念的。当试图访问一个位置超出列表长度的值时，程序会报错：
```python
some_list = [2, 1, 4]
some_list[6] = 'abc' # 会报错：IndexError: list index out of range
```

假设想在列表后添加一个值，则可以用`list.append`：
```python
my_list = [] # 空列表
my_list.append(900)
print(my_list) # [900]
my_list.append('abc')
print(my_list) # [900, 'abc']
```
（在使用`append`的时候，会把列表的长度增加1）

假设想删除列表里某个位置的元素，则可以使用`list.pop`：
```python
my_list = ['a', 'b', 'c']
my_list.pop(1)
print(my_list) # ['a', 'c']
```
用了`pop`之后，列表的长度会减少1。

### 字典
字典（`dict`）和列表很像，也是一种储存很多个值的方式。

不同的是列表是用数字（index）标识元素的，而字典则是用另一个元素（key）来标识元素。

创建一个字典：
```python
my_dict = {
    'a': 'apple',
    'b': 'carrot',
    3: 'number',
    'c': 'citrus'
}
```

调用字典里的值也是用方括号：
```python
print(my_dict['b']) # carrot
print(my_dict[3]) # number
```

改变一个值也和列表很像：
```python
my_dict['b'] = 42
print(my_dict) # 42
```

值得注意的是，与列表不同，假如想添加一个值，则可以直接通过改变值的方式用方括号直接赋值。

赋值的时候，用来标识的元素（key）不需要已经存在于字典的key中：
```python
some_dict = {} # 空字典
some_dict['abc'] = 100
print(some_dict['abc']) # 100
```


## 判断与循环
掌握了基本的数据和输出后，让我们来看看怎么加入控制语句吧！

控制语句的定义是任何对代码片段的执行产生作用的语句，包括判断（`if`）和循环（`for`、`while`）

### 判断
假设我们有一个`x`变量，我们想让用户知道`x`是否等于1，这时候可以使用`if`语句。
```python
if x == 1:
    print('x等于1！')
```

这个语法有几个需要注意的地方：
- 在控制语句内的代码需要缩进（4个空格或是一个Tab）
- 控制语句后面需要冒号

同时，在`if`后面加上`else`可以达成if else的逻辑：
```python
if x == 1:
    print('x等于1！')
else:
    print('x不等于1！')
```

是不是很简单？

`if`语句和其他控制语句都可以嵌套，试着回答以下的代码会打印出什么吧：
```python
a = 5
b = 4 * a
c = 9
if a + b < 50:
    if c * 3 > b:
        print('Case 1')
    else:
        print('Case 2')
else:
    if c + a < b:
        print('Case 3')
```

### 循环
循环是很重要的功能，它可以避免重复的代码，使代码的可读性增加，同时使代码更好写。

有循环的帮助，这样的代码：
```python
print('0: Hello World')
print('1: Hello World')
print('2: Hello World')
print('3: Hello World')
print('4: Hello World')
print('5: Hello World')
print('6: Hello World')
print('7: Hello World')
print('8: Hello World')
print('9: Hello World')
```

可以被写成这样：
```python
for i in range(10):
    print(str(i) + ': Hello World')
```

__`for`语句__
```python
for i in [0, 1, 2, 3, 4]:
    print(i)
```
运行结果：
```
0
1
2
3
4
```
`for`循环可以在一个指定范围内进行循环。同时，每次循环的时候会把在`for`语句中定义的变量（上面例子中的`i`）赋予对应循环次数的位置的值。

这可能听起来很复杂，我们再来看一个例子吧！
```python
my_list = [32, 100, 64, 9, 72]
for i in my_list:
    print(i)
```
运行结果：
```
32
100
64
9
72
```

以上例子中，每一次循环的时候`i`都被赋予了`my_list`中第`循环次数`位置上的值。

知道了怎么用`for`遍历一个列表后，我们来看看怎么用`for`遍历一个区间吧！

Python有个自带的`range`关键字。假设我们想遍历\[10, 20)这个区间，就可以直接把这两个值放到`range`里，然后使用`for`语句：
```python
for i in range(10, 20):
    print(i)
```

运行结果（省略了中间部分）：
```
10
11
12
...
17
18
19
```

__试试看：__ 掌握了`if`和`for`之后，试着写个打印出0-100里所有是6的倍数的数字的程序吧！

__参考答案：__ （向下翻）

|\
|\
|\
|\
|\
|\
|\
|\
|\
|\

```python
for i in range(0, 100):
    if i % 6 == 0: # 假设一个数除以N后余数是0，则那个数是N的倍数
        print(i)
```

__`while`语句__
`while`和`for`都是循环语句，但是用法却截然不同。

`while`语句会需要传入一个表达式（和`if`很像），当表达式为`True`时，`while`会一直重复执行它所包含的代码。
```python
i = 0
while i < 5:
    print(i)
    i = i + 1
```
这段代码在当`i`小于五的时候会一直循环，并每次循环给`i`加1。

再举个例子，以下代码会判断`x`是否是2^n，以及假如是的话n的值是多少：
```python
x = 128
n = 0
while x > 1:
    x = x / 2
    n = n + 1

if x < 1:
    print('x不是2^n！')
else:
    print('x是2^' + str(n))
```
## 函数
恭喜你，你已经成功掌握了基本的数据类型，判断，和循环！
下面你就可以开始更深一层次的学习了！

在这一阶段我们要掌握抽象的能力，举个栗子，我们要对1至100的数求和。
以`1 + 2 + 3 + ... + 100`这种形式来书写无疑是很麻烦的，于是数学家就发明了求和符合![](module-1-python/sigma.png?raw=true)。

这样一来我们就可以把求和记成：
![](module-1-python/equation.png?raw=true)

这种抽象逻辑无疑是很有帮助的，因为这样一来我们就不用关心底层的运算，而是考虑更高层的逻辑。
这也正是计算机编程所需要的。

在前文中，我们已经接触到了不少Python内置的函数，比如`print()`, `range()`等等。
在这里，我们要尝试编写我们的第一个函数来求出上面所说的问题，即1至100求和。

要定义（编写）一个函数，我们首先需要使用`def`语句，依次写出函数名、括号、括号中的参数和冒号。
然后，我们会在缩进块中编写函数体，并使用`return`语句返回返回值。
```python
def sum1to100():
    total = 0
    for i in range(1, 101):
        total += i
    return total

result = sum1to100()
print(result)
```
如果你运行上述的程序，你会发现结果正是5050，也就是1至100的求和。

这样一来，以后你再想1至100求和，只需调用这个函数。

但这仍然不是最普适的写法，因为我们无法求除了1至100外其他的求和。

那么我们就需要引入参数：
```python
def sumXToY(start, end):
    total = 0
    for i in range(start, end + 1):
        total += i
    return total

result = sumXToY()
print(result)
```
注意，在这两个函数里面的`return`语句是不能直接打印结果的，需要赋值到变量再打印结果。
这样一来，我们就可以求任意两数之间的和了！是不是很简单！

__试试看：__ 定义一个名为divisible的函数，接受两个参数，第一个是被除数，第二个是除数。
在这个函数中判断是否整除，如果能整除则返回True，不能则返回False。
提示：注意考虑除数是0的情况。
__参考答案：__ （向下翻）
|\
|\
|\
|\
|\
|\
|\
|\
|\
|\
```python
def divisible(dividend, divisor):
    if(divisor != 0):
        if(dividend % divisor == 0):
            return True
        else:
            return False
    else:
        raise ZeroDivisionError("division by zero") # 这里是抛出异常，并不需要掌握
                                                    # 有兴趣的可以自己搜索
print(divisible(5,3))
print(divisible(5,0)) 
```
这样你就有了一个判别能否整除的简单函数。

当然，在这种工作量的情况下，可能直接运行`x % y == 0`会更方便，
但函数的意义在于可以反复调用并能将结果继续传递下去，
而这其实是当工作量变大后十分重要的一点，所以不要嫌麻烦啦。

## 模块的安装与调用
Python的一个优点就在于有很多高质量的第三方模块(Package)。下面我们教大家如何安装需要的模块。

打开终端/CMD，输入`pip3`/`pip`(同上，取决于是否安装了Python2)，你应该会看到许多命令和解释。
我们只需要用了解install，search，list和uninstall。

比如我们需要安装numpy这个模块，我们可以先搜索，`pip3 search numpy`，
然后你就会看到第一个选项和许多带有numpy字样的其他模块：

```
pip3 search numpy
numpy (1.18.5)                            - NumPy is the fundamental package for array computing
                                            with Python.
...
```
第一个模块正是我们需要的numpy，我们只需`pip3 install numpy`就可以开始安装了。
下载其他的模块也遵循相同的步骤，只需要`pip3 install xxx`就可以安装了。

如果你需要卸载某个模块的话，只用把`install`换成`uninstall`就可以了。
而`pip3 list`可以帮你列出你当前安装的所有模块及版本。

注意，上文全部使用`pip3`是对于即安装了Python2又安装了Python3的电脑，
对于只有Python3的电脑，可以把所有`pip3`替换为`pip`。

试试自己安装pandas，matplotlib和numpy。
安装成功了？下一步，我们要学会调用它们。
- 第一种方法是`import`语句
  比如说在某个程序中，我们需要调用Python内置的模块`sys`，
  我们只需在代码的最开始写上`import sys`就可以了，
  这样Python就知道你需要`sys`模块并帮你调用。
  在此之后，如果需要某个方法，比如`platform`方法，应该这样调用：
  ```python
  import sys
  ... # 省略一些代码
  print(sys.platform) # 注意这里是sys.platform
  ...
  ```
  这样一来Python就会调用`platform`方法，并输出你的系统平台名称。
  
- 还可以使用`from ... import` 语句
  这一语句不同于上面，它会让你从模块中导入指定的部分到当前文件中，比如：
  ```python
  from sys import platform
  ...
  print(platform) # 注意这里只需要写platform就可以了
  ...
  ```
  这段代码会和上面输出同样的结果。
  
- 而`from ... import *`则帮你从模块中导入所有内容。


## 参考资料：

- [廖雪峰的Python教程](https://www.liaoxuefeng.com/wiki/1016959663602400)
- [Python3菜鸟教程](https://www.runoob.com/python3/python3-tutorial.html)
