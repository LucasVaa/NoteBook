# Python考点

## 题型

1. 是非题

2. 选择题

3. 填空题

4. 简答题

5. 看程序写结果

6. 两道程序题

## 注意

1. 大小写敏感，空None

2. 是否**换行**，书写格式

3. unpack斐波那契数列

4. PEP 8

   [PEP8总结](https://www.cnblogs.com/limengjie0104/p/8991430.html)

   + 每级缩进使用4个空格

   + 不可以混用空格和制表符

   + 限制所有行的最大长度为79个字符

   + 空行

     + 顶层函数和类之间使用两个空行
     + 类的方法之间使用一个空行

   + import

     + 按标准、三方、自己编写顺序排放，之间空一行
     + 不要在一行import多个库

   + 空格：避免不必要的空格

     1 各种右括号前不要加空格。
     2 逗号、冒号、分号前不要加空格。
     3 函数的左括号前不要加空格。如Func(1)。
     4 序列的左括号前不要加空格。如list[2]。
     5 操作符左右各加一个空格，不要为了对齐增加空格。
     6 函数默认参数使用的赋值符左右省略空格。
     7 不要将多句语句写在同一行，尽管使用‘；’允许。
     8 if/for/while语句中，即使执行语句只有一句，也必须另起一行。

   + 注释：英文，简明

   + 命名

5. python内置模块

   [内置模块](https://blog.csdn.net/ruanxingzi123/article/details/82787852)

6. [魔法函数](https://www.cnblogs.com/small-office/p/9337297.html)

7. 垃圾回收机制

   [垃圾回收](https://www.cnblogs.com/kumata/p/9099134.html)

8. **动态**的**解释性**语言

   [动态解释性原因](https://blog.csdn.net/kong050kong/article/details/84329142)

   动态类型语言：是指在运行期间才去做数据类型检查的语言，也就是说，在用动态类型的语言编程时，永远也不用给任何变量指定数据类型，该语言会在你第一次赋值给变量时，在内部将数据类型记录下来。

   解释性语言：只在执行程序时,才一条一条的解释成机器语言给计算机来执行,所以运行速度是不如编译后的程序运行的快的.

9. 一切皆对象

10. 编译完后.pyc

11. [LEGB](https://www.jianshu.com/p/0cd480be2d7c)

    + 局部作用域：当前函数内的作用域
    + 嵌套作用域：外部嵌套函数的作用域
    + 全局作用域：函数外部所在的命名空间
    + 内建所用于：Python内置模块的命名空间

12. [模块导入顺序](https://www.jb51.net/article/152450.htm)

    + 程序文件所在目录
    + 环境变量所设置的路径(从左至右)
    + 标准库的路径
    + .pth文件中定义的路径

13. [模块、包、库](https://blog.csdn.net/qq_37495916/article/details/79370814)

    + 模块：自我包含并且有组织的代码片段

      表现形式为：写的代码保存为文件。这个文件就是一个模块。sample.py 其中文件名smaple为模块名字。

    + 包：有层次的目录结构，它定义了由n个模块和n个子包组成的python应用程序执行环境。

      包是一个包含\_\_init\_\_.py 文件的目录，该目录下一定得有这个\_\_init\_\_.py文件和其它模块或子包。

    + 库：指python中的完成一定功能的代码集合，供用户使用的代码组合。在python中是包和模块的形式。

    + 框架： 这些框架把不同的模块集成在一起，让你更快的构架程序，而不用关注一些细节（例如socket 和协议），框架提供了需要的所有功能。

14. [异常](https://www.runoob.com/python3/python3-errors-execptions.html) 

    一个 try 语句可能包含多个except子句，分别来处理不同的特定的异常。**最多只有一个分支会被执行**

15. [深拷贝 浅拷贝](https://www.jianshu.com/p/03dce38cc97e)

16. 正则表达式

17. [time模块 时间模块](https://www.cnblogs.com/jason-lv/p/8260539.html)

    [time模块](https://docs.python.org/3/library/datetime.html)

    ```python
    import time
    
    print(time.strftime("%x %X", time.localtime()))
    print(time.strftime("%m/%d/%y %H:%M:%S", time.localtime()))
    
    # 输出
    12/29/19 20:48:01
    12/29/19 20:48:01
    ```

18. [三级菜单](https://www.jianshu.com/p/b3df65fdb5e4)

## PYthon-lxf

#### 空值

空值是Python里一个特殊的值，用`None`表示。`None`不能理解为`0`，因为`0`是有意义的，而`None`是一个特殊的空值。

执行`a = 'ABC'`，解释器创建了字符串`'ABC'`和变量`a`，并把`a`指向`'ABC'`：

![py-var-code-1](images/0-1577364497040.png)

执行`b = a`，解释器创建了变量`b`，并把`b`指向`a`指向的字符串`'ABC'`：

![py-var-code-2](images/0-1577364497075.png)

执行`a = 'XYZ'`，解释器创建了字符串'XYZ'，并把`a`的指向改为`'XYZ'`，但`b`并没有更改：

![py-var-code-3](images/0-1577364497074.png)

所以，最后打印变量`b`的结果自然是`'ABC'`了。

所以，本着节约的精神，又出现了把Unicode编码转化为“可变长编码”的**`UTF-8`编码**。UTF-8编码把一个Unicode字符根据不同的数字大小编码成1-6个字节，常用的英文字母被编码成1个字节，**汉字通常是3个字节**，只有很生僻的字符才会被编码成4-6个字节。如果你要传输的文本包含大量英文字符，用UTF-8编码就能节省空间：

| 字符 | ASCII    | Unicode           | UTF-8                      |
| :--- | :------- | :---------------- | :------------------------- |
| A    | 01000001 | 00000000 01000001 | 01000001                   |
| 中   | x        | 01001110 00101101 | 11100100 10111000 10101101 |

要计算`str`包含多少个字符，可以用`len()`函数：

```
>>> len('ABC')
3
>>> len('中文')
2
```

`len()`函数计算的是`str`的字符数，如果换成`bytes`，`len()`函数就计算字节数：

```
>>> len(b'ABC')
3
>>> len(b'\xe4\xb8\xad\xe6\x96\x87')
6
>>> len('中文'.encode('utf-8'))
6
```

**tuple**

如果要定义一个空的tuple，可以写成`()`：

```
>>> t = ()
>>> t
()
```

但是，要定义一个只有1个元素的tuple，如果你这么定义：

```
>>> t = (1)
>>> t
1
```

定义的不是tuple，是`1`这个数！这是因为括号`()`既可以表示tuple，又可以表示数学公式中的小括号，这就产生了歧义，因此，Python规定，这种情况下，按小括号进行计算，计算结果自然是`1`。

所以，只有1个元素的tuple定义时必须加一个逗号`,`，来消除歧义：

```
>>> t = (1,)
>>> t
(1,)
```

**条件判断**

`if`判断条件还可以简写，比如写：

```
if x:
    print('True')
```

只要`x`是**非零数值、非空字符串、非空list**等，就判断为`True`，否则为`False`。

**dict**

要避免key不存在的错误，有两种办法，一是通过`in`判断key是否存在：

```
>>> 'Thomas' in d
False
```

二是通过dict提供的`get()`方法，如果key不存在，可以返回`None`，或者自己指定的value：

```
>>> d.get('Thomas')
>>> d.get('Thomas', -1)
-1
```

**set**

set可以看成数学意义上的无序和无重复元素的集合，因此，两个set可以做数学意义上的交集、并集等操作：

```
>>> s1 = set([1, 2, 3])
>>> s2 = set([2, 3, 4])
>>> s1 & s2
{2, 3}
>>> s1 | s2
{1, 2, 3, 4}
```

set和dict的唯一区别仅在于没有存储对应的value，但是，set的原理和dict一样，所以，同样不可以放入可变对象，因为无法判断两个可变对象是否相等，也就无法保证set内部“不会有重复元素”。试试把list放入set，看看是否会报错。

**不可变对象**

而对于不可变对象，比如str，对str进行操作呢：

```
>>> a = 'abc'
>>> a.replace('a', 'A')
'Abc'
>>> a
'abc'
```

虽然字符串有个`replace()`方法，也确实变出了`'Abc'`，但变量`a`最后仍是`'abc'`，应该怎么理解呢？

我们先把代码改成下面这样：

```
>>> a = 'abc'
>>> b = a.replace('a', 'A')
>>> b
'Abc'
>>> a
'abc'
```

### 数据类型转换

Python内置的常用函数还包括数据类型转换函数，比如`int()`函数可以把其他数据类型转换为整数：

```
>>> int('123')
123
>>> int(12.34)
12
>>> float('12.34')
12.34
>>> str(1.23)
'1.23'
>>> str(100)
'100'
>>> bool(1)
True
>>> bool('')
False
```

**函数**

如果没有`return`语句，函数执行完毕后也会返回结果，只是结果为`None`。`return None`可以简写为`return`。

```
def my_abs(x):
    if not isinstance(x, (int, float)):
        raise TypeError('bad operand type')
    if x >= 0:
        return x
    else:
        return -x
```

**多个返回值**

原来返回值是一个tuple！但是，在语法上，返回一个tuple可以省略括号，而多个变量可以同时接收一个tuple，按位置赋给对应的值，所以，Python的函数返回多值其实就是返回一个tuple，但写起来更方便。	

**位置参数**

**默认参数**

默认参数很有用，但使用不当，也会掉坑里。默认参数有个最大的坑，演示如下：

先定义一个函数，传入一个list，添加一个`END`再返回：

```
def add_end(L=[]):
    L.append('END')
    return L
```

当你正常调用时，结果似乎不错：

```
>>> add_end([1, 2, 3])
[1, 2, 3, 'END']
>>> add_end(['x', 'y', 'z'])
['x', 'y', 'z', 'END']
```

当你使用默认参数调用时，一开始结果也是对的：

```
>>> add_end()
['END']
```

但是，再次调用`add_end()`时，结果就不对了：

```
>>> add_end()
['END', 'END']
>>> add_end()
['END', 'END', 'END']
```

很多初学者很疑惑，默认参数是`[]`，但是函数似乎每次都“记住了”上次添加了`'END'`后的list。

原因解释如下：

Python函数在定义的时候，默认参数`L`的值就被计算出来了，即`[]`，因为默认参数`L`也是一个变量，它指向对象`[]`，每次调用该函数，如果改变了`L`的内容，则下次调用时，默认参数的内容就变了，不再是函数定义时的`[]`了。

 **定义默认参数要牢记一点：默认参数必须指向不变对象！**

**命名关键字参数**

如果要限制关键字参数的名字，就可以用命名关键字参数，例如，只接收`city`和`job`作为关键字参数。这种方式定义的函数如下：

```
def person(name, age, *, city, job):
    print(name, age, city, job)
```

和关键字参数`**kw`不同，命名关键字参数需要一个特殊分隔符`*`，`*`后面的参数被视为命名关键字参数。

调用方式如下：

```
>>> person('Jack', 24, city='Beijing', job='Engineer')
Jack 24 Beijing Engineer
```

如果函数定义中已经有了一个可变参数，后面跟着的命名关键字参数就不再需要一个特殊分隔符`*`了：

```
def person(name, age, *args, city, job):
    print(name, age, args, city, job)
```

**所以，对于任意函数，都可以通过类似`func(*args, **kw)`的形式调用它，无论它的参数是如何定义的。**

**可迭代对象**

那么，如何判断一个对象是可迭代对象呢？方法是通过collections模块的Iterable类型判断：

```
>>> from collections import Iterable
>>> isinstance('abc', Iterable) # str是否可迭代
True
>>> isinstance([1,2,3], Iterable) # list是否可迭代
True
>>> isinstance(123, Iterable) # 整数是否可迭代
False
```

最后一个小问题，如果要对list实现类似Java那样的下标循环怎么办？Python内置的`enumerate`函数可以把一个list变成索引-元素对，这样就可以在`for`循环中同时迭代索引和元素本身：

```
>>> for i, value in enumerate(['A', 'B', 'C']):
...     print(i, value)
...
0 A
1 B
2 C
```

上面的`for`循环里，同时引用了两个变量，在Python里是很常见的，比如下面的代码：

```
>>> for x, y in [(1, 1), (2, 4), (3, 9)]:
...     print(x, y)
...
1 1
2 4
3 9
```

**生成器**

所以，如果列表元素可以按照某种算法推算出来，那我们是否可以在循环的过程中不断推算出后续的元素呢？这样就不必创建完整的list，从而节省大量的空间。在Python[中](https://www.liaoxuefeng.com/wiki/1016959663602400/1017323698112640)，这种一边循环一边计算的机制，称为生成器：generator。

[生成器](https://www.liaoxuefeng.com/wiki/1016959663602400/1017318207388128)

**迭代器**

[迭代器](https://www.liaoxuefeng.com/wiki/1016959663602400/1017323698112640)

`map()`函数接收两个参数，一个是函数，一个是`Iterable`，`map`将传入的函数依次作用到序列的每个元素，并把结果作为新的`Iterator`返回。

和`map()`类似，`filter()`也接收一个函数和一个序列。和`map()`不同的是，`filter()`把传入的函数依次作用于每个元素，然后根据返回值是`True`还是`False`决定保留还是丢弃该元素。

`filter()`函数返回的是一个`Iterator`

[**filter函数第一个参数为None**](https://www.cnblogs.com/xingchuxin/p/10441067.html)

**返回函数**

[返回函数](https://www.liaoxuefeng.com/wiki/1016959663602400/1017434209254976)

### 静态语言 vs 动态语言

对于静态语言（例如Java）来说，如果需要传入`Animal`类型，则传入的对象必须是`Animal`类型或者它的子类，否则，将无法调用`run()`方法。

对于Python这样的动态语言来说，则不一定需要传入`Animal`类型。我们只需要保证传入的对象有一个`run()`方法就可以了：

```
class Timer(object):
    def run(self):
        print('Start...')
```

这就是动态语言的“鸭子类型”，它并不要求严格的继承体系，一个对象只要“看起来像鸭子，走起路来像鸭子”，那它就可以被看做是鸭子。

Python的“file-like object“就是一种鸭子类型。对真正的文件对象，它有一个`read()`方法，返回其内容。但是，许多对象，只要有`read()`方法，都被视为“file-like object“。许多函数接收的参数就是“file-like object“，你不一定要传入真正的文件对象，完全可以传入任何实现了`read()`方法的对象。

**实例属性和类属性**

实例属性和类属性使用相同的名字，因为相同名称的实例属性将屏蔽掉类属性，但是当你删除实例属性后，再使用相同的名称，访问到的将是类属性。

字符串的相关操作

1. split 注意对空格的分割，以及产生空串的实例

   ```python
   a = "122223"
   a = "1 2  3"
   print(a.split())
   print(a.split(" "))
   
   # 输出
   ['1', '2', '3']
   ['1', '2', '', '3']
   
   a = "aba"
   b = a.split("a")
   print(b)
   
   # 输出
   ['', 'b', '']
   ```

2. [join](https://www.cnblogs.com/ling-yu/p/9167065.html)

3. [endswith/startswith](https://www.cnblogs.com/qianyuliang/p/7491100.html)

   ```python
   a = "hello"
   print(a.endswith("lo", 3, 5))
   print(a.endswith("lo", 3, 4))
   
   # 输出
   True
   False
   ```

**字符串编码转换**

[编码转换](https://www.cnblogs.com/liangxiyang/p/11566039.html)

[**py文件执行过程**](https://www.jianshu.com/p/1c2822669ffa)

字典方法总结

1. [zip](https://www.cnblogs.com/wdz1226/p/10181354.html)

   zip（） 返回一个zip对象，该对象的next（）方法返回一个元组，其中第i个元素来自第i个可迭代的参数。直到参数序列中最短的迭代被耗尽，然后抛出异常停止迭代，否则 next() 方法将持续返回元组。

   **重点就是这个 “zip对象” 是一个迭代器。 迭代器只能前进，不能后退。**

2. pop(key[,default])

   - key: 要删除的键值
   - default: 如果没有 key，返回 default 值；否则报错KeyError

3. popitem()

   Python 字典 popitem() 方法随机返回并删除字典中的最后一对键和值。

   如果字典已经为空，却调用了此方法，就报出KeyError异常。

   ```python
   a = {1: 2}
   print(type(a.popitem()))
   
   # 输出
   <class 'tuple'>
   ```

4. [其他常用方法](http://c.biancheng.net/view/2212.html)

**推导式**

```python
a = [(4 , 3), (1, 2), (3, 5)]
print(dict(a))
l1 = [1, 2, 3, 4]
l2 = [2, 3, 4, 5]
l3 = dict(zip(l1, l2))
print(l3)
print(zip(l1, l2))
dict1 = {i : j for i, j in a}    # 字典推导式
print(dict1)

# 输出
{4: 3, 1: 2, 3: 5}
{1: 2, 2: 3, 3: 4, 4: 5}
<zip object at 0x03A210A8>
{4: 3, 1: 2, 3: 5}
```

[**枚举**](https://www.cnblogs.com/ucos/p/5896861.html)

[**yeild**](https://blog.csdn.net/mieleizhi0522/article/details/82142856)

**else特例**：在for 或者 while 后出现的else，只有所有可迭代对象都迭代完后才执行

[**异常和错误区别**](https://www.py.cn/faq/python/11717.html)

**对象的三要素**：

1. id
2. type
3. value
4. 判断方法：https://blog.csdn.net/zhrq95/article/details/79292442

**面向对象和面向过程**

[**json**](https://www.cnblogs.com/yanwuliu/p/9593826.html)

[**类中的三种方法**](https://www.cnblogs.com/wcwnina/p/8644892.html)；[附](https://www.cnblogs.com/dushangguzhousuoli/p/11162129.html)

[**面对对象的三大特征**](https://www.cnblogs.com/peng104/p/9550305.html)

[**override**](https://blog.csdn.net/weixin_42982616/article/details/86835461)

[**super用法和mro机制**](https://www.cnblogs.com/chenhuabin/p/10058594.html#_label1)

[**组合和继承**](https://www.cnblogs.com/Yanjy-OnlyOne/p/10029970.html)

[**init和new的区别**](https://www.cnblogs.com/slhs/p/7717045.html)

[**\_\_bool\_\_和\_\_len\_\_的联系**](https://blog.csdn.net/aizhishiren2010/article/details/79031591)

[**\_\_name\_\_ = "\_\_main\_\_"**](https://www.cnblogs.com/GGGGGGZX/p/9206806.html)

[**callable()**](https://www.runoob.com/python/python-func-callable.html)

[**iterable&interator**](https://www.cnblogs.com/zf-blog/p/10613533.html)

[**闭包和装饰器**](https://blog.csdn.net/u013380694/article/details/90019571)

[**多层装饰器的执行顺序**](https://blog.csdn.net/yyb19951015/article/details/83014969)

[**evel()&evec()**](https://www.cnblogs.com/yangmingxianshen/p/7810496.html)

**os sys**

[os.path sys.path](https://www.cnblogs.com/derezzed/articles/8342208.html)

[**with**](https://www.cnblogs.com/wanglei-xiaoshitou1/p/9238275.html)

[**文件操作**](https://www.cnblogs.com/lifangzheng/p/11190765.html)

**编码方式**：encoding encode

```python
a = """one
two
three"""
print(a)
print(a.splitlines())
a = """
one
two
three
"""
print(a)
print(a.splitlines())

# 输出
one
two
three
['one', 'two', 'three']

one
two
three

['', 'one', 'two', 'three']
```

```python
a = "\na\n"
print(a)
print(a.splitlines())
a = " a "
print(a)
print(a.split())
a = " a "
print(a)
print(a.split(" "))
a = "bab"
print(a)
print(a.split("b"))

# 输出

a

['', 'a']
 a
['a']
 a
['', 'a', '']
bab
['', 'a', '']
```

```python
a = 'abc'.join(['1', '2', '3'])
print(a)
print(a.index("b"))

b = a.encode(encoding='utf-8')
print(b)
print(type(b))
print(b.decode(encoding='utf-8'))

# 输出
1abc2abc3
2
b'1abc2abc3'
<class 'bytes'>
1abc2abc3
```

```python
a = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
print(a[::-1])
print(a[2:5:2])
print(a[5:2:-1])

# 输出
[9, 8, 7, 6, 5, 4, 3, 2, 1, 0]
[2, 4]
[5, 4, 3]
```

```python
# i=[ 0,   1,   2,   3,   4,   5]
# i=[-6,  -5,  -4,  -3,  -2,  -1]
a = ['A', 'B', 'C', 'D', 'E', 'F']
print(a[0:3])
print(a[0:-3])
print(a[-6:3])
print(a[-6:-3])

# 输出
['A', 'B', 'C']
['A', 'B', 'C']
['A', 'B', 'C']
['A', 'B', 'C']
```

```python
list1 = ['a', 'b', 'c'];
list2 = [1, 2]
a = dict(zip(list1, list2))
print(a)

a = dict.fromkeys(['a', 'b', 'c'], [1, 2])
print(a)

# 输出
{'a': 1, 'b': 2}
{'a': [1, 2], 'b': [1, 2], 'c': [1, 2]}
```

```python
a = {'abc': 123, 98.6: 37}
for i in a.items():
    print(i)

a = {'abc': 123, 98.6: 37}
for k, v in a.items():
    print(k, v)
    
# 输出
('abc', 123)
(98.6, 37)
abc 123
98.6 37
```

```python
a = {x for x in 'abracadabra' if x not in 'abc'}
print(a)
a = frozenset((1, 2))
print(a)
print(type(a))

# 输出
{'d', 'r'}
frozenset({1, 2})
<class 'frozenset'>
```

```python
print(2 | 3)  # 10|11=11
print(1 ^ 3)  # 01^11=10
print(1 & 2)  # 01^10=00

# 输出
3
2
0
```

拷贝

```python
a = [1, 2, 3, [4, 5]]
b = a.copy()
print(id(a[0]))
print(id(b[0]))
b[0] = 'b'
print(id(a[0]))
print(id(b[0]))
print(a)
print(b)
print(id(a[3]))
print(id(b[3]))
b[3][0] = 'bb'
print(id(a[3]))
print(id(b[3]))
print(a)
print(b)

# 输出
2068669616
2068669616
2068669616
21351840
[1, 2, 3, [4, 5]]
['b', 2, 3, [4, 5]]
21120504
21120504
21120504
21120504
[1, 2, 3, ['bb', 5]]
['b', 2, 3, ['bb', 5]]
```

拆包

```python
a = ('str', 123, '2018-12-12', [1, 2, 3], (4, 5, 6))
b, c, d, e, f = a
print(b)
print(c)
print(d)
print(e)
print(f)
*_, aa = a;  # *_ 为通配符
print(type(_))
print(aa)
bb, *_, cc = a
print(bb)
print(cc)

# 输出
str
123
2018-12-12
[1, 2, 3]
(4, 5, 6)
<class 'list'>
(4, 5, 6)
str
(4, 5, 6)

```

```python
a = {'abc': 123, 12: 'ab', 32: 43}  # 字典拆包出来的仅是 key
b, c, d = a
print(b)
print(c)
print(d)

print(*a)  # 用*拆包
a = [1, 2, 3]
print(*a)
a = (1, 2, 3)
print(*a)
a = {1, 2, 3}
print(*a)

# 输出
abc
12
32
abc 12 32
1 2 3
1 2 3
1 2 3
```

```python
def run(a, *args):
    print(a)
    print(args)
    print(type(args))

run(1, 2, 3)

def run(**kwargs):  # 传来的 key = value 类型的实参会映射成kwargs里面的键和值
    # kwargs是一个字典，将未命名参数以键值对的形式
    print(kwargs)
    print("对kwargs拆包")
    run1(**kwargs)


def run1(a, b):  # 此处的参数名一定要和字典的键的名称一)
    print(a, b)


run(a=1, b=2)

# 输出
1
(2, 3)
<class 'tuple'>
{'a': 1, 'b': 2}
对kwargs拆包
1 2
```

总结：

1. *args作为形参时是用来接收多余的未命名参数，而**kwargs是用来接收key=value这种类型的命名参数，args是元组，kwargs是字典。*
2. 和**在函数体中除了拆包之外，并没有什么卵用。
3. 装包的含义就是把未命名参数和命名参数分别放在元组或者字典中。

关系运算，逻辑运算，位运算

- == != > < <= >=
- and or not
- & | ^ >> <<

```python
a = 20
b = 20
print(a is b)
print(id(a), id(b))
b = 30
print(a is b)
print(a is not b)

a = [1, 2, 3]
b = a
print(b is a)
print(b == a)
b = a[:]
print(b is a)
print(b == a)

# 输出
True
2068669920 2068669920
False
True
True
True
False
True
```

is 与 == 区别：is 用于判断两个变量引用对象是否为同一个， == 用于判断引用变量的值是否相等

列表生成器

```python
c = [m + n for m in 'ABC' for n in '123']
print(c)

# 输出
['A1', 'A2', 'A3', 'B1', 'B2', 'B3', 'C1', 'C2', 'C3']
```

生成器

```python
a = (x ** 2 for x in range(1, 10))
print(a)
print(a.__next__())
print(next(a))
print('-----')
for i in a:
    print(i)


def fibonacci(n):  # 生成器函数 - 斐波那契
    a, b, counter = 0, 1, 0
    while True:
        if counter >= n:
            return
        yield a
        a, b = b, a + b
        counter += 1


f = fibonacci(10)  # f 是一个迭代器，由生成器返回生成
print('fibonacci')
print(f)
print(next(f))
print(f.__next__())
print('-----')
for i in f:
    print(i)
    
# 输出
<generator object <genexpr> at 0x031F10B0>
1
4
-----
9
16
25
36
49
64
81
fibonacci
<generator object fibonacci at 0x03234FB0>
0
1
-----
1
2
3
5
8
13
21
34
```

生成器的send

```python
def average():
    s = 0
    count = 0
    avg = 0
    while True:
        num = yield avg
        s += num
        count += 1
        avg = s / count


avg_g = average()
# 第一次运行只能使用next或者send(None)
print(avg_g.__next__())
avg1 = avg_g.send(10)
print(avg1)
avg1 = avg_g.send(20)
print(avg1)
avg1 = avg_g.send(30)
print(avg1)

print('**********************************')


# 生成器的send用法 generator.send(value)
def test():
    i = 1
    while i < 5:
        temp = yield i ** 2
        print(temp)
        i += 1


t = test()
# 第一次运行只能使用next或者send(None)
print(t.__next__())
# send的作用相当于使生成器继续运行，并且传递的参数为yield的返回值(程序中即temp的值)
print(t.send("Hello World"))
print(t.__next__())  # 相当于send(None) 此时temp = None

# 输出
0
10.0
15.0
20.0
**********************************
1
Hello World
4
None
9
```

迭代器

```python
print('list_iter')
a = [1, 2, 3]
a = iter(a)
print(a)
print(next(a))
print(a.__next__())

print('str_iter')
a = '123'
a = iter(a)
print(a)
print(next(a))
print(a.__next__())

print('tuple_iter')
a = (1, 2, 3)
a = iter(a)
print(a)
print(next(a))
print(a.__next__())

print('set_iter')
a = {1, 2, 3}
a = iter(a)
print(a)
print(next(a))
print(a.__next__())

print('dict_iter')
a = {1: 'a', 2: 'b', 3: 'c'}
a = iter(a)
print(a)
print(next(a))
print(a.__next__())
print(next(a))

# 输出
list_iter
<list_iterator object at 0x03150950>
1
2
str_iter
<str_iterator object at 0x03150950>
1
2
tuple_iter
<tuple_iterator object at 0x03150950>
1
2
set_iter
<set_iterator object at 0x03184F80>
1
2
dict_iter
<dict_keyiterator object at 0x0139C030>
1
2
3
```

map

```python
def f(x):
    return x * x


a = map(f, [1, 2, 3])
print(type(a))
print(list(a))

print(list(map(str, [1, 2, 3, 4, 5, 6, 7, 8, 9])))

# 输出
<class 'map'>
[1, 4, 9]
['1', '2', '3', '4', '5', '6', '7', '8', '9']
```

reduce

```python
from functools import reduce #Reduce 在 python3 中移除，需要 import

def str2int(s):
    digits = {'0': 0, '1': 1, '2': 2, '3': 3, '4': 4, '5': 5, '6': 6, '7': 7, '8': 8, '9': 9}

    def fn(x, y):
        return x * 10 + y

    def char2num(s):
        return digits[s]

    return reduce(fn, map(char2num, s))


print(str2int('135'))

# 输出
135
```

filter

```python
def is_odd(n):
    return n % 2 == 1

a = filter(is_odd, [1, 2, 4, 5, 6, 9, 10, 15])
print(type(a))
print(list(a))

# 输出
<class 'filter'>
[1, 5, 9, 15]
```

分子筛求素数：

```python
def primes():
    it = iter(range(2, 100))  # 初始序列

    def _not_divisible(n):
        return lambda x: x % n > 0

    while True:
        n = next(it)  # 返回序列的第一个数
        yield n
        it = filter(_not_divisible(n), it)  # 构造新序列


print('primes')
for n in primes():
    if n < 50:
        print(n)
    else:
        break
```

正则表达式

```python
s = 'ABC\\-001'
s = r'ABC\-001'

import re

# span：返回一个元组包含匹配（开始，结束）的位置
print(re.match('www', 'www.runoob.com').span())  # 在起始位置匹配
print(re.match('com', 'www.runoob.com'))  # 不在起始位置匹配

line = "Cats are smarter than dogs"
# .* 表示任意匹配除换行符（\n、\r）之外的任何单个或多个字符
matchObj = re.match(r'(.*) are (.*?) .*', line)

if matchObj:
    print("matchObj.groups() : ", matchObj.groups())
    print("matchObj.group() : ", matchObj.group())
    print("matchObj.group(1) : ", matchObj.group(1))
    print("matchObj.group(2) : ", matchObj.group(2))
    print("matchObj.group(1,2) : ", matchObj.group(1, 2))
else:
    print("No match!!")
    
    
# 输出
(0, 3)
None
matchObj.groups() :  ('Cats', 'smarter')
matchObj.group() :  Cats are smarter than dogs
matchObj.group(1) :  Cats
matchObj.group(2) :  smarter
matchObj.group(1,2) :  ('Cats', 'smarter')
```

贪婪模式：

```python
import re

print(re.match(r'^(\d+)(0*)$', '102300').groups())
# ('102300', '')
print(re.match(r'^(\d+?)(0*)$', '102300').groups())
# ('1023', '00')
# 由于\d+采用贪婪匹配，直接把后面的0全部匹配了，结果0*只能匹配空字符串，加个?就可以让\d+采用非贪婪匹配；

```

```python
# 如果一个正则表达式要重复使用几千次，出于效率的考虑，我们可以预编译该正则表达式
tel = re.compile(r'^(\d{3})-(\d{3,8})$')
# 使用：
print(tel.match('010-12345').groups())
# ('010', '12345')
print(tel.match('010-8086').groups())
# ('010', '8086')
```

```python
import re

print(re.search('www', 'www.runoob.com').span())  # 在起始位置匹配
print(re.search('com', 'www.runoob.com').span())  # 不在起始位置匹配

# 输出
(0, 3)
(11, 14)
```

sub：检索和替换

```python
import re

phone = "2004-959-559 # 这是一个电话号码"

# 删除注释
num = re.sub(r'#.*$', "", phone)
print("电话号码 : ", num)

# 移除非数字的内容
num = re.sub(r'\D', "", phone)
print("电话号码 : ", num)


# 将匹配的数字乘于 2
def double(matched):
    value = int(matched.group())
    return str(value * 2)


s = 'A23G4HFD567'
print(re.sub(r'\d+', double, s))

# 输出
电话号码 :  2004-959-559
电话号码 :  2004959559
A46G8HFD1134
```

findall

```python
import re

pattern = re.compile(r'\d+')  # 查找数字
result1 = pattern.findall('runoob 123 google 456')
result2 = pattern.findall('run88oob123google456', 4, 10)  # begin and end pos

print(result1)
print(result2)

# 输出
['123', '456']
['8', '12']
```

```python
import re

it = re.finditer(r"\d+", "12a32bc43jf3")
for match in it:
    print(match.group())

print(re.split('\W+', 'runoob, runoob, runoob.'))

# 输出
12
32
43
3
['runoob', 'runoob', 'runoob', '']
```

多态
由于Python是动态语言，所以，传递给函数work_with_dog的参数dog不一定是Dog或Dog的子类型。任何数据类型的实例都可以，只要它有一个work()的方法即可：
class Book(object)：
def work()：
print('这是一本书’)
这是动态语言和静态语言（例如Java）最大的差别之一。动态语言调用实例方法，不检查类型，只要方法存在，参数正确，就可以调用。

子类可以重写父类方法，在子类中也可以调用父类的方法。

```python
class A:
    def fun(self):
        print("A")

class B(A):
    def fun(self):
        print("B")

a = B()
a.fun()
super(B, a).fun()

# 输出
B
A
```

### 考题小结

1. 运算法的使用

   ```python 
   1 + "a"
   [1, 2] + [3, 4]
   "123" * 4
   ```
    ```python
 a = 1 +"a"
   
    # error
 Traceback (most recent call last):
      File ".\test.py", line 1, in <module>
        a = 1 +"a"
    TypeError: unsupported operand type(s) for +: 'int' and 'str'
    ```
   
2. [**函数返回值**](https://blog.csdn.net/sj349781478/article/details/79399213)

3. 整数池问题？

4. sort()等返回值问题

   ```python
   a = [3 , 2, 1]
   b = reversed(a)
   c = sorted(a, reverse=True)
   print(a, b, c)
   
   # 输出
   [3, 2, 1] <list_reverseiterator object at 0x00E5DC90> [3, 2, 1]
   ```

5. [**max()函数使用**](https://www.runoob.com/python/func-number-max.html)

6. 概念描述题

   + 函数闭包的概念和特点
   + Iterable\Iterator\iter的区别
   + 深浅拷贝