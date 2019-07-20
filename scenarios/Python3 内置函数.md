# **Python3 内置函数**

![](https://github.com/anmiaru/python3/raw/master/image/38-1.png)

## **Python3 abs() 函数**
### **描述**
abs() 函数返回数字的绝对值。
### **语法**
以下是 abs() 方法的语法:
```python
abs( x )
```
### **参数**
* x -- 数值表达式，可以是整数，浮点数，复数。

### **返回值**
函数返回 x（数字）的绝对值，如果参数是一个复数，则返回它的大小。

### **实例**
以下展示了使用 abs() 方法的实例：
```python
#!/usr/bin/python3

print ("abs(-40) : ", abs(-40))
print ("abs(100.10) : ", abs(100.10))
```
以上实例运行后输出结果为：
```python
abs(-40) :  40
abs(100.10) :  100.1
```
---


## **Python all() 函数**
### **描述**
all() 函数用于判断给定的可迭代参数 iterable 中的所有元素是否都为 TRUE，如果是返回 True，否则返回 False。  
元素除了是 0、空、None、False 外都算 True。  
函数等价于：
```python
def all(iterable):
    for element in iterable:
        if not element:
            return False
    return True
```
Python 2.5 以上版本可用。
### **语法**
以下是 all() 方法的语法:

```python
all(iterable)
```
### **参数**
* iterable -- 元组或列表。

### **返回值**
如果iterable的所有元素不为0、''、False或者iterable为空，all(iterable)返回True，否则返回False；  
**注意**：空元组、空列表返回值为True，这里要特别注意。

### **实例**
以下展示了使用 all() 方法的实例：
```python
>>> all(['a', 'b', 'c', 'd'])  # 列表list，元素都不为空或0
True
>>> all(['a', 'b', '', 'd'])   # 列表list，存在一个为空的元素
False
>>> all([0, 1，2, 3])          # 列表list，存在一个为0的元素
False
   
>>> all(('a', 'b', 'c', 'd'))  # 元组tuple，元素都不为空或0
True
>>> all(('a', 'b', '', 'd'))   # 元组tuple，存在一个为空的元素
False
>>> all((0, 1, 2, 3))          # 元组tuple，存在一个为0的元素
False
   
>>> all([])             # 空列表
True
>>> all(())             # 空元组
True
```

---
## **Python any() 函数**
### **描述**
any() 函数用于判断给定的可迭代参数 iterable 是否全部为 False，则返回 False，如果有一个为 True，则返回 True。  
元素除了是 0、空、FALSE 外都算 TRUE。  
函数等价于：
```python
def any(iterable):
    for element in iterable:
        if element:
            return True
    return False
```
Python 2.5 以上版本可用。
### **语法**
以下是 any() 方法的语法:
```python
any(iterable)
```
### **参数**
* iterable -- 元组或列表。

### **返回值**
如果都为空、0、false，则返回false，如果不都为空、0、false，则返回true。

### **实例**
以下展示了使用 any() 方法的实例：
```python
>>>any(['a', 'b', 'c', 'd'])  # 列表list，元素都不为空或0
True
 
>>> any(['a', 'b', '', 'd'])   # 列表list，存在一个为空的元素
True
 
>>> any([0, '', False])        # 列表list,元素全为0,'',false
False
 
>>> any(('a', 'b', 'c', 'd'))  # 元组tuple，元素都不为空或0
True
 
>>> any(('a', 'b', '', 'd'))   # 元组tuple，存在一个为空的元素
True
 
>>> any((0, '', False))        # 元组tuple，元素全为0,'',false
False
  
>>> any([]) # 空列表
False
 
>>> any(()) # 空元组
False
```
 
---
## **Python3 ascii() 函数**
### **描述**
ascii() 函数类似 repr() 函数, 返回一个表示对象的字符串, 但是对于字符串中的非 ASCII 字符则返回通过 repr() 函数使用 \x, \u 或 \U 编码的字符。 生成字符串类似 Python2 版本中 repr() 函数的返回值。

### **语法**
以下是 ascii() 方法的语法:
```python
ascii(object)
```
### **参数**
* object -- 对象。

### **返回值**
返回字符串。

### **实例**
以下展示了使用 ascii() 方法的实例：
```python
>>> ascii('runoob')
"'runoob'"
```
---
## **Python bin() 函数**
### **描述**
bin() 返回一个整数 int 或者长整数 long int 的二进制表示。

### **语法**
以下是 bin() 方法的语法:
```python
bin(x)
```

### **参数**
* x -- int 或者 long int 数字

### **返回值**
字符串。

### **实例**
以下展示了使用 bin 函数的实例：
```python
>>>bin(10)
'0b1010'
>>> bin(20)
'0b10100'
```
---
## **Python bool() 函数**
### **描述**
bool() 函数用于将给定参数转换为布尔类型，如果没有参数，返回 False。  
bool 是 int 的子类。

### **语法**
以下是 bool() 方法的语法:
```python
class bool([x])
```
### **参数**
* x -- 要进行转换的参数。
### **返回值**
返回 Ture 或 False。
### **实例**
以下展示了使用 bool 函数的实例：
```python
>>>bool()
False
>>> bool(0)
False
>>> bool(1)
True
>>> bool(2)
True
>>> issubclass(bool, int)  # bool 是 int 子类
True
```
---
## **Python bytearray() 函数**
### **描述**
bytearray() 方法返回一个新字节数组。这个数组里的元素是可变的，并且每个元素的值范围: 0 <= x < 256。
### **语法**
bytearray()方法语法：
```python
class bytearray([source[, encoding[, errors]]])
```

### **参数**
* 如果 source 为整数，则返回一个长度为 source 的初始化数组；
* 如果 source 为字符串，则按照指定的 encoding 将字符串转换为字节序列；
* 如果 source 为可迭代类型，则元素必须为\[0 ,255\] 中的整数；
* 如果 source 为与 buffer 接口一致的对象，则此对象也可以被用于初始化 bytearray。
* 如果没有输入任何参数，默认就是初始化数组为0个元素。

### **返回值**
返回新字节数组。
### **实例**
以下实例展示了 bytearray() 的使用方法：

```python
>>>bytearray()
bytearray(b'')
>>> bytearray([1,2,3])
bytearray(b'\x01\x02\x03')
>>> bytearray('runoob', 'utf-8')
bytearray(b'runoob')
>>>
```
---
## **Python3 bytes 函数**
### **描述**
bytes 函数返回一个新的 bytes 对象，该对象是一个 0 <= x < 256 区间内的整数不可变序列。它是 bytearray 的不可变版本。
### **语法**
以下是 bytes 的语法:
```python
class bytes([source[, encoding[, errors]]])
```
### **参数**
* 如果 source 为整数，则返回一个长度为 source 的初始化数组；
* 如果 source 为字符串，则按照指定的 encoding 将字符串转换为字节序列；
* 如果 source 为可迭代类型，则元素必须为\[0 ,255\] 中的整数；
* 如果 source 为与 buffer 接口一致的对象，则此对象也可以被用于初始化 bytearray。
* 如果没有输入任何参数，默认就是初始化数组为0个元素。
### **返回值**
返回一个新的 bytes 对象。
### **实例**
以下展示了使用 bytes 的实例：
```python
>>>a = bytes([1,2,3,4])
>>> a
b'\x01\x02\x03\x04'
>>> type(a)
<class 'bytes'>
>>>
>>> a = bytes('hello','ascii')
>>>
>>> a
b'hello'
>>> type(a)
<class 'bytes'>
>>>
```
---
## **Python callable() 函数**
### **描述**
**callable()** 函数用于检查一个对象是否是可调用的。如果返回 True，object 仍然可能调用失败；但如果返回 False，调用对象 object 绝对不会成功。  
对于函数、方法、lambda 函式、 类以及实现了 \_\_call__ 方法的类实例, 它都返回 True。
### **语法**
callable()方法语法：
```python
callable(object)
```
### **参数**
* object -- 对象

### **返回值**
可调用返回 True，否则返回 False。
### **实例**
以下实例展示了 callable() 的使用方法：
```python
>>>callable(0)
False
>>> callable("runoob")
False
 
>>> def add(a, b):
...     return a + b
... 
>>> callable(add)             # 函数返回 True
True
>>> class A:                  # 类
...     def method(self):
...             return 0
... 
>>> callable(A)               # 类返回 True
True
>>> a = A()
>>> callable(a)               # 没有实现 __call__, 返回 False
False
>>> class B:
...     def __call__(self):
...             return 0
... 
>>> callable(B)
True
>>> b = B()
>>> callable(b)               # 实现 __call__, 返回 True
True
```
---
## **Python3 chr() 函数**
### **描述**
chr() 用一个整数作参数，返回一个对应的字符。
### **语法**
以下是 chr() 方法的语法:
```python
chr(i)
```
### **参数**
* i -- 可以是 10 进制也可以是 16 进制的形式的数字，数字范围为 0 到 1,114,111 (16 进制为0x10FFFF)。

### **返回值**
返回值是当前整数对应的 ASCII 字符。

### **实例**
以下展示了使用 chr() 方法的实例：
```python
>>>chr(0x30)
'0'
>>> chr(97) 
'a'
>>> chr(8364)
'€'
```
---
## **Python classmethod 修饰符**
### **描述**
classmethod 修饰符对应的函数不需要实例化，不需要 self 参数，但第一个参数需要是表示自身类的 cls 参数，可以来调用类的属性，类的方法，实例化对象等。
### **语法**
classmethod 语法：
```python
classmethod
```
### **参数**
* 无。

### **返回值**
返回函数的类方法。
### **实例**
以下实例展示了 classmethod 的使用方法：
```python
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
class A(object):
    bar = 1
    def func1(self):  
        print ('foo') 
    @classmethod
    def func2(cls):
        print ('func2')
        print (cls.bar)
        cls().func1()   # 调用 foo 方法
 
A.func2()               # 不需要实例化
```
输出结果为：
```python
func2
1
foo
```
---
## **Python compile() 函数**
### **描述**
compile() 函数将一个字符串编译为字节代码。
### **语法**
以下是 compile() 方法的语法:
```python
compile(source, filename, mode[, flags[, dont_inherit]])
```
### **参数**
* source -- 字符串或者AST（Abstract Syntax Trees）对象。。
* filename -- 代码文件名称，如果不是从文件读取代码则传递一些可辨认的值。
* mode -- 指定编译代码的种类。可以指定为 exec, eval, single。
* flags -- 变量作用域，局部命名空间，如果被提供，可以是任何映射对象。。
* flags和dont_inherit是用来控制编译源码时的标志

### **返回值**
返回表达式执行结果。
### **实例**
以下展示了使用 compile 函数的实例：
```python
>>>str = "for i in range(0,10): print(i)" 
>>> c = compile(str,'','exec')   # 编译为字节代码对象 
>>> c
<code object <module> at 0x10141e0b0, file "", line 1>
>>> exec(c)
0
1
2
3
4
5
6
7
8
9
>>> str = "3 * 4 + 5"
>>> a = compile(str,'','eval')
>>> eval(a)
17
```
---
## **Python complex() 函数**
### **描述**
complex() 函数用于创建一个值为 real + imag * j 的复数或者转化一个字符串或数为复数。如果第一个参数为字符串，则不需要指定第二个参数。
### **语法**
complex 语法：
```python
class complex([real[, imag]])
```
### **参数**
* real -- int, long, float或字符串；
* imag -- int, long, float；

### **返回值**
返回一个复数。

### **实例**
以下实例展示了 complex 的使用方法：
```python
>>>complex(1, 2)
(1 + 2j)
 
>>> complex(1)    # 数字
(1 + 0j)
 
>>> complex("1")  # 当做字符串处理
(1 + 0j)
 
# 注意：这个地方在"+"号两边不能有空格，也就是不能写成"1 + 2j"，应该是"1+2j"，否则会报错
>>> complex("1+2j")
(1 + 2j)
```
---
## **Python delattr() 函数**
### **描述**
**delattr** 函数用于删除属性。   
**delattr(x, 'foobar')** 相等于 **del x.foobar**。
### **语法**
delattr 语法：
```python
delattr(object, name)
```
### **参数**
* object -- 对象。
* name -- 必须是对象的属性。

### **返回值**
无。
### **实例**
以下实例展示了 delattr 的使用方法：
```python
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
class Coordinate:
    x = 10
    y = -5
    z = 0
 
point1 = Coordinate() 
 
print('x = ',point1.x)
print('y = ',point1.y)
print('z = ',point1.z)
 
delattr(Coordinate, 'z')
 
print('--删除 z 属性后--')
print('x = ',point1.x)
print('y = ',point1.y)
 
# 触发错误
print('z = ',point1.z)
```
输出结果：
```python
('x = ', 10)
('y = ', -5)
('z = ', 0)
--删除 z 属性后--
('x = ', 10)
('y = ', -5)
Traceback (most recent call last):
  File "test.py", line 22, in <module>
    print('z = ',point1.z)
AttributeError: Coordinate instance has no attribute 'z'
```
---
## **Python dict() 函数**
### **描述**
dict() 函数用于创建一个字典。
### **语法**
dict 语法：
```python
class dict(**kwarg)
class dict(mapping, **kwarg)
class dict(iterable, **kwarg)
```
### **参数**
* **kwargs -- 关键字
* mapping -- 元素的容器。
* iterable -- 可迭代对象。

### **返回值**
返回一个字典。

### **实例**
以下实例展示了 dict 的使用方法：
```python 
>>>dict()                        # 创建空字典
{}
>>> dict(a='a', b='b', t='t')     # 传入关键字
{'a': 'a', 'b': 'b', 't': 't'}
>>> dict(zip(['one', 'two', 'three'], [1, 2, 3]))   # 映射函数方式来构造字典
{'three': 3, 'two': 2, 'one': 1} 
>>> dict([('one', 1), ('two', 2), ('three', 3)])    # 可迭代对象方式来构造字典
{'three': 3, 'two': 2, 'one': 1}
>>>
```
---
## **Python dir() 函数**
### **描述**
dir() 函数不带参数时，返回当前范围内的变量、方法和定义的类型列表；带参数时，返回参数的属性、方法列表。如果参数包含方法\_\_dir\_\_()，该方法将被调用。如果参数不包含\_\_dir\_\_()，该方法将最大限度地收集参数信息。
### **语法**
dir 语法：
```python
dir([object])
```
### **参数**
* object -- 对象、变量、类型。

### **返回值**
返回模块的属性列表。

### **实例**
以下实例展示了 dir 的使用方法：
```python 
>>>dir()   #  获得当前模块的属性列表
['__builtins__', '__doc__', '__name__', '__package__', 'arr', 'myslice']
>>> dir([ ])    # 查看列表的方法
['__add__', '__class__', '__contains__', '__delattr__', '__delitem__', '__delslice__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getslice__', '__gt__', '__hash__', '__iadd__', '__imul__', '__init__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__reversed__', '__rmul__', '__setattr__', '__setitem__', '__setslice__', '__sizeof__', '__str__', '__subclasshook__', 'append', 'count', 'extend', 'index', 'insert', 'pop', 'remove', 'reverse', 'sort']
>>>
```
---
## **Python3 divmod() 函数**
### **描述**
Python divmod() 函数接收两个数字类型（非复数）参数，返回一个包含商和余数的元组(a // b, a % b)。

在 python 3.x 版本该函数不支持复数。
### **语法**

```python
divmod(a, b)
```
### **参数**
* a: 数字，非复数。
* b: 数字，非复数。

如果参数 a 与 参数 b 都是整数，函数返回的结果相当于 (a // b, a % b)。  
如果其中一个参数为浮点数时，函数返回的结果相当于 (q, a % b)，q 通常是 math.floor(a / b)，但也有可能是 1 ，比小，不过 q * b + a % b 的值会非常接近 a。  
如果 a % b 的求余结果不为 0 ，则余数的正负符号跟参数 b 是一样的，若 b 是正数，余数为正数，若 b 为负数，余数也为负数，并且 0 <= abs(a % b) < abs(b)。
### **实例**

```python 
>>> divmod(7, 2)
(3, 1)
>>> divmod(8, 2)
(4, 0)
>>> divmod(8, -2)
(-4, 0)
>>> divmod(3, 1.3)
(2.0, 0.3999999999999999)
```
---
## **Python3 enumerate() 函数**
### **描述**
enumerate() 函数用于将一个可遍历的数据对象(如列表、元组或字符串)组合为一个索引序列，同时列出数据和数据下标，一般用在 for 循环当中。
### **语法**
以下是 enumerate() 方法的语法:
```python
enumerate(sequence, [start=0])
```
### **参数**
* sequence -- 一个序列、迭代器或其他支持迭代对象。
* start -- 下标起始位置。

### **返回值**
返回 enumerate(枚举) 对象。

### **实例**
以下展示了使用 enumerate() 方法的实例：
```python 
>>>seasons = ['Spring', 'Summer', 'Fall', 'Winter']
>>>list(enumerate(seasons))
[(0, 'Spring'), (1, 'Summer'), (2, 'Fall'), (3, 'Winter')]
>>>list(enumerate(seasons, start=1))       # 小标从 1 开始
[(1, 'Spring'), (2, 'Summer'), (3, 'Fall'), (4, 'Winter')]
```

普通的 for 循环
```python 
>>>i = 0
>>>seq = ['one', 'two', 'three']
>>>for element in seq:
...    print(i, seq[i])
...    i += 1
... 
0 one
1 two
2 three
```

for 循环使用 enumerate
```python 
>>>seq = ['one', 'two', 'three']
>>>for i, element in enumerate(seq):
...    print(i, seq[i])
... 
0 one
1 two
2 three
>>>
```
---
## **Python eval() 函数**
### **描述**
eval() 函数用来执行一个字符串表达式，并返回表达式的值。
### **语法**
以下是 eval() 方法的语法:
```python
eval(expression[, globals[, locals]])
```
### **参数**
* expression -- 表达式。
* globals -- 变量作用域，全局命名空间，如果被提供，则必须是一个字典对象。
* locals -- 变量作用域，局部命名空间，如果被提供，可以是任何映射对象。

### **返回值**
返回表达式计算结果。

### **实例**
以下展示了使用 eval() 方法的实例：
```python 
>>>x = 7
>>> eval( '3 * x' )
21
>>> eval('pow(2,2)')
4
>>> eval('2 + 2')
4
>>> n=81
>>> eval("n + 4")
85
```
---
## **Python3 exec 函数**
### **描述**
exec 执行储存在字符串或文件中的 Python 语句，相比于 eval，exec可以执行更复杂的 Python 代码。
### **语法**
以下是 exec 的语法:
```python
exec(object[, globals[, locals]])
```
### **参数**
* object：必选参数，表示需要被指定的Python代码。它必须是字符串或code对象。如果object是一个字符串，该字符串会先被解析为一组Python语句，然后在执行（除非发生语法错误）。如果object是一个code对象，那么它只是被简单的执行。
* globals：可选参数，表示全局命名空间（存放全局变量），如果被提供，则必须是一个字典对象。
* locals：可选参数，表示当前局部命名空间（存放局部变量），如果被提供，可以是任何映射对象。如果该参数被忽略，那么它将会取与globals相同的值。

### **返回值**
exec 返回值永远为 None。

### **实例**
以下展示了使用 exec 的实例：
```python 
>>>exec('print("Hello World")')
Hello World
# 单行语句字符串
>>> exec("print ('runoob.com')")
runoob.com
 
#  多行语句字符串
>>> exec ("""for i in range(5):
...     print ("iter time: %d" % i)
... """)
iter time: 0
iter time: 1
iter time: 2
iter time: 3
iter time: 4
```


```python 
x = 10
expr = """
z = 30
sum = x + y + z
print(sum)
"""
def func():
    y = 20
    exec(expr)
    exec(expr, {'x': 1, 'y': 2})
    exec(expr, {'x': 1, 'y': 2}, {'y': 3, 'z': 4})
    
func()
```

输出结果：
```python 
60
33
34
```
---
## **Python3 filter() 函数**
### **描述**
**filter()** 函数用于过滤序列，过滤掉不符合条件的元素，返回一个迭代器对象，如果要转换为列表，可以使用 **list()** 来转换。  

该接收两个参数，第一个为函数，第二个为序列，序列的每个元素作为参数传递给函数进行判，然后返回 True 或 False，最后将返回 True 的元素放到新列表中。
### **语法**
以下是 filter() 方法的语法:
```python
filter(function, iterable)
```
### **参数**
* function -- 判断函数。
* iterable -- 可迭代对象。

### **返回值**
返回一个迭代器对象

### **实例**
以下展示了使用 filter 函数的实例：
```python 
#!/usr/bin/python3
 
def is_odd(n):
    return n % 2 == 1
 
tmplist = filter(is_odd, [1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
newlist = list(tmplist)
print(newlist)
```

输出结果 ：
```python 
[1, 3, 5, 7, 9]
```

过滤出1~100中平方根是整数的数：
```python 
#!/usr/bin/python3
 
import math
def is_sqr(x):
    return math.sqrt(x) % 1 == 0
 
tmplist = filter(is_sqr, range(1, 101))
newlist = list(tmplist)
print(newlist)
```

输出结果 ：
```python 
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```
---
## **Python float() 函数**
### **描述**
float() 函数用于将整数和字符串转换成浮点数。
### **语法**
float()方法语法：
```python
class float([x])
```
### **参数**
* x -- 整数或字符串

### **返回值**
返回浮点数。

### **实例**
以下实例展示了 float() 的使用方法：
```python 
>>>float(1)
1.0
>>> float(112)
112.0
>>> float(-123.6)
-123.6
>>> float('123')     # 字符串
123.0
```
---
## **Python format 格式化函数**
### **描述**
Python2.6 开始，新增了一种格式化字符串的函数 **str.format()**，它增强了字符串格式化的功能。

基本语法是通过 {} 和 : 来代替以前的 % 。

format 函数可以接受不限个参数，位置可以不按顺序。
### **实例**

```python 
>>>"{} {}".format("hello", "world")    # 不设置指定位置，按默认顺序
'hello world'
 
>>> "{0} {1}".format("hello", "world")  # 设置指定位置
'hello world'
 
>>> "{1} {0} {1}".format("hello", "world")  # 设置指定位置
'world hello world'
```

也可以设置参数：
```python 
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
print("网站名：{name}, 地址 {url}".format(name="菜鸟教程", url="www.runoob.com"))
 
# 通过字典设置参数
site = {"name": "菜鸟教程", "url": "www.runoob.com"}
print("网站名：{name}, 地址 {url}".format(**site))
 
# 通过列表索引设置参数
my_list = ['菜鸟教程', 'www.runoob.com']
print("网站名：{0[0]}, 地址 {0[1]}".format(my_list))  # "0" 是必须的
```

输出结果为：
```python 
网站名：菜鸟教程, 地址 www.runoob.com
网站名：菜鸟教程, 地址 www.runoob.com
网站名：菜鸟教程, 地址 www.runoob.com
```

也可以向 str.format() 传入对象：
```python 
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
class AssignValue(object):
    def __init__(self, value):
        self.value = value
my_value = AssignValue(6)
print('value 为: {0.value}'.format(my_value))  # "0" 是可选的
```

输出结果为：
```python 
value 为: 6
```

#### **数字格式化**
下表展示了 str.format() 格式化数字的多种方法：
```python 
>>> print("{:.2f}".format(3.1415926));
3.14
```

![](https://github.com/anmiaru/python3/raw/master/image/38-2.png)

![](https://github.com/anmiaru/python3/raw/master/image/38-3.png)

^, <, > 分别是居中、左对齐、右对齐，后面带宽度， : 号后面带填充的字符，只能是一个字符，不指定则默认是用空格填充。   
\+ 表示在正数前显示 +，负数前显示 -；  （空格）表示在正数前加空格。  
b、d、o、x 分别是二进制、十进制、八进制、十六进制。  
此外我们可以使用大括号 {} 来转义大括号，如下实例：

```python 
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
print ("{} 对应的位置是 {{0}}".format("runoob"))
```
输出结果为：

```python 
runoob 对应的位置是 {0}
```
---
## **Python frozenset() 函数**
### **描述**
frozenset() 返回一个冻结的集合，冻结后集合不能再添加或删除任何元素。
### **语法**
frozenset() 函数语法：
```python
class frozenset([iterable])
```
### **参数**
* iterable -- 可迭代的对象，比如列表、字典、元组等等。

### **返回值**
返回新的 frozenset 对象，如果不提供任何参数，默认会生成空集合。

### **实例**
以下实例展示了 frozenset() 的使用方法：
```python 
>>>a = frozenset(range(10))     # 生成一个新的不可变集合
>>> a
frozenset([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
>>> b = frozenset('runoob') 
>>> b
frozenset(['b', 'r', 'u', 'o', 'n'])   # 创建不可变集合
>>>
```
---
## **Python getattr() 函数**
### **描述**
getattr() 函数用于返回一个对象属性值。
### **语法**
getattr 语法：
```python
getattr(object, name[, default])
```
### **参数**
* object -- 对象。
* name -- 字符串，对象属性。
* default -- 默认返回值，如果不提供该参数，在没有对应属性时，将触发 AttributeError。

### **返回值**
返回对象属性值。

### **实例**
以下实例展示了 getattr 的使用方法：
```python 
>>>class A(object):
...     bar = 1
... 
>>> a = A()
>>> getattr(a, 'bar')        # 获取属性 bar 值
1
>>> getattr(a, 'bar2')       # 属性 bar2 不存在，触发异常
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'A' object has no attribute 'bar2'
>>> getattr(a, 'bar2', 3)    # 属性 bar2 不存在，但设置了默认值
3
>>>
```
---
## **Python globals() 函数**
### **描述**
globals() 函数会以字典类型返回当前位置的全部全局变量。
### **语法**
globals() 函数语法：
```python
globals()
```
### **参数**
* 无

### **返回值**
返回全局变量的字典。

### **实例**
以下实例展示了 globals() 的使用方法：
```python 
>>>a='runoob'
>>> print(globals()) # globals 函数返回一个全局变量的字典，包括所有导入的变量。
{'__builtins__': <module '__builtin__' (built-in)>, '__name__': '__main__', '__doc__': None, 'a': 'runoob', '__package__': None}
```
---
## **Python hasattr() 函数**
### **描述**
hasattr() 函数用于判断对象是否包含对应的属性。
### **语法**
hasattr 语法：
```python
hasattr(object, name)
```
### **参数**
* object -- 对象。
* name -- 字符串，属性名。

### **返回值**
如果对象有该属性返回 True，否则返回 False。

### **实例**
以下实例展示了 hasattr 的使用方法：
```python 
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
class Coordinate:
    x = 10
    y = -5
    z = 0
 
point1 = Coordinate() 
print(hasattr(point1, 'x'))
print(hasattr(point1, 'y'))
print(hasattr(point1, 'z'))
print(hasattr(point1, 'no'))  # 没有该属性
```

输出结果：
```python 
True
True
True
False
```
---
## **Python hash() 函数**
### **描述**
hash() 用于获取取一个对象（字符串或者数值等）的哈希值。
### **语法**
hash 语法：
```python
hash(object)
```
### **参数**
* object -- 对象

### **返回值**
返回对象的哈希值。

### **实例**
以下实例展示了 hash 的使用方法：
```python 
>>>hash('test')            # 字符串
2314058222102390712
>>> hash(1)                 # 数字
1
>>> hash(str([1,2,3]))      # 集合
1335416675971793195
>>> hash(str(sorted({'1':1}))) # 字典
7666464346782421378
>>>
```
---
## **Python help() 函数**
### **描述**
help() 函数用于查看函数或模块用途的详细说明。
### **语法**
help 语法：
```python
help([object])
```
### **参数**
* object -- 对象

### **返回值**
返回对象帮助信息。

### **实例**
以下实例展示了 help 的使用方法：
```python 
>>>help('sys')             # 查看 sys 模块的帮助
……显示帮助信息……
 
>>>help('str')             # 查看 str 数据类型的帮助
……显示帮助信息……
 
>>>a = [1,2,3]
>>>help(a)                 # 查看列表 list 帮助信息
……显示帮助信息……
 
>>>help(a.append)          # 显示list的append方法的帮助
……显示帮助信息……
```
---
## **Python3 hex() 函数**
### **描述**
hex() 函数用于将一个指定数字转换为 16 进制数。
### **语法**
hex 语法：
```python
hex(x)
```
### **参数**
* x -- 一个整数

### **返回值**
返回一个字符串，以 0x 开头。

### **实例**
以下实例展示了 hex 的使用方法：
```python 
>>>hex(255)
'0xff'
>>> hex(-42)
'-0x2a'
>>> hex(12)
'0xc'
>>> type(hex(12))
<class 'str'>      # 字符串
```
---
## **Python id() 函数**
### **描述**
id() 函数用于获取对象的内存地址。
### **语法**
id 语法：
```python
id([object])
```
### **参数**
* object -- 对象

### **返回值**
返回对象的内存地址。

### **实例**
以下实例展示了 id 的使用方法：
```python 
>>>a = 'runoob'
>>> id(a)
4531887632
>>> b = 1
>>> id(b)
140588731085608
```
---
## **Python3 input() 函数**
### **描述**
Python3.x 中 input() 函数接受一个标准输入数据，返回为 string 类型。   

*注意：在 Python3.x 中 raw_input() 和 input() 进行了整合，去除了 raw_input( )，仅保留了input( )函数，其接收任意任性输入，将所有输入默认为字符串处理，并返回字符串类型。*
### **语法**

```python
input([prompt])
```
### **参数**
* prompt: 提示信息

### **实例**

```python 
>>>a = input("input:")
input:123                  # 输入整数
>>> type(a)
<class 'str'>              # 字符串
>>> a = input("input:")    
input:runoob              # 正确，字符串表达式
>>> type(a)
<class 'str'>             # 字符串
```
---
## **Python int() 函数**
### **描述**
int() 函数用于将一个字符串或数字转换为整型。
### **语法**
以下是 int() 方法的语法:
```python
class int(x, base=10)
```
### **参数**
* x -- 字符串或数字。
* base -- 进制数，默认十进制。

### **返回值**
返回整型数据。

### **实例**
以下展示了使用 int() 方法的实例：
```python 
>>>int()               # 不传入参数时，得到结果0
0
>>> int(3)
3
>>> int(3.6)
3
>>> int('12',16)        # 如果是带参数base的话，12要以字符串的形式进行输入，12 为 16进制
18
>>> int('0xa',16)  
10  
>>> int('10',8)  
8
```
---
## **Python isinstance() 函数**
### **描述**
isinstance() 函数来判断一个对象是否是一个已知的类型，类似 type()。

*isinstance() 与 type() 区别：*
* *type() 不会认为子类是一种父类类型，不考虑继承关系。*
* *isinstance() 会认为子类是一种父类类型，考虑继承关系。
如果要判断两个类型是否相同推荐使用 isinstance()。*

### **语法**
以下是 isinstance() 方法的语法:
```python
isinstance(object, classinfo)
```
### **参数**
* object -- 实例对象。
* classinfo -- 可以是直接或间接类名、基本类型或者由它们组成的元组。

### **返回值**
如果对象的类型与参数二的类型（classinfo）相同则返回 True，否则返回 False。

### **实例**
以下展示了使用 isinstance 函数的实例：
```python 
>>>a = 2
>>> isinstance (a,int)
True
>>> isinstance (a,str)
False
>>> isinstance (a,(str,int,list))    # 是元组中的一个返回 True
True
```

type() 与 isinstance()区别：
```python 
class A:
    pass
 
class B(A):
    pass
 
isinstance(A(), A)    # returns True
type(A()) == A        # returns True
isinstance(B(), A)    # returns True
type(B()) == A        # returns False
```
---
## **Python issubclass() 函数**
### **描述**
issubclass() 方法用于判断参数 class 是否是类型参数 classinfo 的子类。
### **语法**
以下是 issubclass() 方法的语法:
```python
issubclass(class, classinfo)
```
### **参数**
* class -- 类。
* classinfo -- 类。

### **返回值**
如果 class 是 classinfo 的子类返回 True，否则返回 False。

### **实例**
以下展示了使用 issubclass 函数的实例：
```python 
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
class A:
    pass
class B(A):
    pass
    
print(issubclass(B,A))    # 返回 True
```
---
## **Python iter() 函数**
### **描述**
iter() 函数用来生成迭代器。
### **语法**
以下是 iter() 方法的语法:
```python
iter(object[, sentinel])
```
### **参数**
* object -- 支持迭代的集合对象。
* sentinel -- 如果传递了第二个参数，则参数 object 必须是一个可调用的对象（如，函数），此时，iter 创建了一个迭代器对象，每次调用这个迭代器对象的\_\_next\_\_()方法时，都会调用 object。

### **返回值**
迭代器对象。

### **实例**

```python 
>>>lst = [1, 2, 3]
>>> for i in iter(lst):
...     print(i)
... 
1
2
3
```
---
## **Python3 len()方法**
### **描述**
Python len() 方法返回对象（字符、列表、元组等）长度或项目个数。
### **语法**
len()方法语法：
```python
len( s )
```
### **参数**
* s -- 对象。

### **返回值**
返回对象长度。

### **实例**
以下实例展示了 len() 的使用方法：
```python 
>>>str = "runoob"
>>> len(str)             # 字符串长度
6
>>> l = [1,2,3,4,5]
>>> len(l)               # 列表元素个数
5
```
---
## **Python3 List list()方法**
### **描述**
list() 方法用于将元组或字符串转换为列表。

**注**：元组与列表是非常类似的，区别在于元组的元素值不能修改，元组是放在括号中，列表是放于方括号中。
### **语法**
list()方法语法：
```python
list( seq )
```
### **参数**
* seq -- 要转换为列表的元组或字符串。

### **返回值**
返回列表。

### **实例**
以下实例展示了 list()函数的使用方法：
```python 
#!/usr/bin/python3

aTuple = (123, 'Google', 'Runoob', 'Taobao')
list1 = list(aTuple)
print ("列表元素 : ", list1)

str="Hello World"
list2=list(str)
print ("列表元素 : ", list2)
```
以上实例输出结果如下：

```python 
列表元素 :  [123, 'Google', 'Runoob', 'Taobao']
列表元素 :  ['H', 'e', 'l', 'l', 'o', ' ', 'W', 'o', 'r', 'l', 'd']
```
---
## **Python locals() 函数**
### **描述**
locals() 函数会以字典类型返回当前位置的全部局部变量。

对于函数, 方法, lambda 函式, 类, 以及实现了 \_\_call__ 方法的类实例, 它都返回 True。
### **语法**
locals() 函数语法：
```python
locals()
```
### **参数**
* 无

### **返回值**
返回字典类型的局部变量。

### **实例**
以下实例展示了 locals() 的使用方法：
```python 
>>>def runoob(arg):    # 两个局部变量：arg、z
...     z = 1
...     print (locals())
... 
>>> runoob(4)
{'z': 1, 'arg': 4}      # 返回一个名字/值对的字典
>>>
```
---
## **Python map() 函数**
### **描述**
map() 会根据提供的函数对指定序列做映射。

第一个参数 function 以参数序列中的每一个元素调用 function 函数，返回包含每次 function 函数返回值的新列表。
### **语法**
map() 函数语法：
```python
map(function, iterable, ...)
```
### **参数**
* function -- 函数
* iterable -- 一个或多个序列

### **返回值**
Python 2.x 返回列表。  
Python 3.x 返回迭代器。

### **实例**
以下实例展示了 map() 的使用方法：
```python 
>>>def square(x) :            # 计算平方数
...     return x ** 2
... 
>>> map(square, [1,2,3,4,5])   # 计算列表各个元素的平方
[1, 4, 9, 16, 25]
>>> map(lambda x: x ** 2, [1, 2, 3, 4, 5])  # 使用 lambda 匿名函数
[1, 4, 9, 16, 25]
 
# 提供了两个列表，对相同位置的列表数据进行相加
>>> map(lambda x, y: x + y, [1, 3, 5, 7, 9], [2, 4, 6, 8, 10])
[3, 7, 11, 15, 19]
```
---
## **Python3 max() 函数**
### **描述**
max() 方法返回给定参数的最大值，参数可以为序列。
### **语法**
以下是 max() 方法的语法:
```python
max( x, y, z, .... )
```
### **参数**
* x -- 数值表达式。
* y -- 数值表达式。
* z -- 数值表达式。

### **返回值**
返回给定参数的最大值。

### **实例**
以下展示了使用 max() 方法的实例：
```python 
#!/usr/bin/python3

print ("max(80, 100, 1000) : ", max(80, 100, 1000))
print ("max(-20, 100, 400) : ", max(-20, 100, 400))
print ("max(-80, -20, -10) : ", max(-80, -20, -10))
print ("max(0, 100, -400) : ", max(0, 100, -400))
```

以上实例运行后输出结果为：
```python 
max(80, 100, 1000) :  1000
max(-20, 100, 400) :  400
max(-80, -20, -10) :  -10
max(0, 100, -400) :  100
```
---
## **Python memoryview() 函数**
### **描述**
**memoryview()** 函数返回给定参数的内存查看对象(Momory view)。

所谓内存查看对象，是指对支持缓冲区协议的数据进行包装，在不需要复制对象基础上允许Python代码访问。
### **语法**
memoryview 语法：
```python
memoryview(obj)
```
### **参数**
* obj -- 对象

### **返回值**
返回元组列表。

### **实例**
以下实例展示了 memoryview 的使用方法：
```python 
>>>v = memoryview(bytearray("abcefg", 'utf-8'))
>>> print(v[1])
98
>>> print(v[-1])
103
>>> print(v[1:4])
<memory at 0x10f543a08>
>>> print(v[1:4].tobytes())
b'bce'
>>>
```
---
## **Python3 min() 函数**
### **描述**
min() 方法返回给定参数的最小值，参数可以为序列。
### **语法**
以下是 min() 方法的语法:
```python
min( x, y, z, .... )
```
### **参数**
* x -- 数值表达式。
* y -- 数值表达式。
* z -- 数值表达式。

### **返回值**
返回给定参数的最小值。

### **实例**
以下展示了使用 min() 方法的实例：
```python 
#!/usr/bin/python3

print ("min(80, 100, 1000) : ", min(80, 100, 1000))
print ("min(-20, 100, 400) : ", min(-20, 100, 400))
print ("min(-80, -20, -10) : ", min(-80, -20, -10))
print ("min(0, 100, -400) : ", min(0, 100, -400))
```

以上实例运行后输出结果为：
```python 
min(80, 100, 1000) :  80
min(-20, 100, 400) :  -20
min(-80, -20, -10) :  -80
min(0, 100, -400) :  -400
```
---
## **Python next() 函数**
### **描述**
next() 返回迭代器的下一个项目。
### **语法**
next 语法：
```python
next(iterator[, default])
```
### **参数**
* iterator -- 可迭代对象
* default -- 可选，用于设置在没有下一个元素时返回该默认值，如果不设置，又没有下一个元素则会触发 StopIteration 异常。

### **返回值**
返回对象帮助信息。

### **实例**
以下实例展示了 next 的使用方法：
```python 
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
# 首先获得Iterator对象:
it = iter([1, 2, 3, 4, 5])
# 循环:
while True:
    try:
        # 获得下一个值:
        x = next(it)
        print(x)
    except StopIteration:
        # 遇到StopIteration就退出循环
        break
```

输出结果为：
```python 
1
2
3
4
5
```
---
## **Python oct() 函数**
### **描述**
oct() 函数将一个整数转换成8进制字符串。
### **语法**
oct 语法：
```python
oct(x)
```
### **参数**
* x -- 整数。

### **返回值**
返回8进制字符串。

### **实例**
以下实例展示了 oct 的使用方法：
```python 
>>>oct(10)
'012'
>>> oct(20)
'024'
>>> oct(15)
'017'
>>>
```
---
## **Python3 open() 函数**
### **描述**
Python open() 函数用于打开一个文件，并返回文件对象，在对文件进行处理过程都需要使用到这个函数，如果该文件无法被打开，会抛出 OSError。

**注意**：使用 open() 函数一定要保证关闭文件对象，即调用 close() 函数。  

### **语法**
open() 函数常用形式是接收两个参数：文件名(file)和模式(mode)。
```python
open(file, mode='r')
```
完整的语法格式为：
```python
open(file, mode='r', buffering=-1, encoding=None, errors=None, newline=None, closefd=True, opener=None)
```

### **参数**
* file: 必需，文件路径（相对或者绝对路径）。
* mode: 可选，文件打开模式
* buffering: 设置缓冲
* encoding: 一般使用utf8
* errors: 报错级别
* newline: 区分换行符
* closefd: 传入的file参数类型
* opener:

mode 参数有：

![](https://github.com/anmiaru/python3/raw/master/image/39-12.png)

![](https://github.com/anmiaru/python3/raw/master/image/39-13.png)

默认为文本模式，如果要以二进制模式打开，加上 b 。

### **实例**
测试文件 test.txt，内容如下：
```python 
RUNOOB1
RUNOOB2
```


```python 
>>>f = open('test.txt')
>>> f.read()
'RUNOOB1\nRUNOOB2\n'
```
---
## **Python3 ord() 函数**
### **描述**
ord() 函数是 chr() 函数（对于 8 位的 ASCII 字符串）的配对函数，它以一个字符串（Unicode 字符）作为参数，返回对应的 ASCII 数值，或者 Unicode 数值。
### **语法**
以下是 ord() 方法的语法:
```python
ord(c)
```
### **参数**
* c -- 字符。

### **返回值**
返回值是对应的十进制整数。

### **实例**
以下展示了使用 ord() 方法的实例：
```python 
>>>ord('a')
97
>>> ord('€')
8364
>>>
```
---
## **Python3 pow() 函数**
### **描述**
pow() 方法返回 x^y（x的y次方） 的值。
### **语法**
以下是 math 模块 pow() 方法的语法:
```python
import math

math.pow( x, y )
```
内置的 pow() 方法
```python
pow(x, y[, z])
```
函数是计算x的y次方，如果z在存在，则再对结果进行取模，其结果等效于pow(x,y) %z

**注意：**pow() 通过内置的方法直接调用，内置方法会把参数作为整型，而 math 模块则会把参数转换为 float。
### **参数**
* x -- 数值表达式。
* y -- 数值表达式。
* z -- 数值表达式。

### **返回值**
返回 x^y（x的y次方） 的值。

### **实例**
以下展示了使用 pow() 方法的实例：
```python 
#!/usr/bin/python3
import math   # 导入 math 模块

print ("math.pow(100, 2) : ", math.pow(100, 2))
# 使用内置，查看输出结果区别
print ("pow(100, 2) : ", pow(100, 2))
print ("math.pow(100, -2) : ", math.pow(100, -2))
print ("math.pow(2, 4) : ", math.pow(2, 4))
print ("math.pow(3, 0) : ", math.pow(3, 0))
```

以上实例运行后输出结果为：
```python 
math.pow(100, 2) :  10000.0
pow(100, 2) :  10000
math.pow(100, -2) :  0.0001
math.pow(2, 4) :  16.0
math.pow(3, 0) :  1.0
```
---
## **Python print() 函数**
### **描述**
print() 方法用于打印输出，最常见的一个函数。  

*print 在 Python3.x 是一个函数，但在 Python2.x 版本不是一个函数，只是一个关键字。*
### **语法**
以下是 print() 方法的语法:
```python
print(*objects, sep=' ', end='\n', file=sys.stdout)
```
### **参数**
* objects -- 复数，表示可以一次输出多个对象。输出多个对象时，需要用 , 分隔。
* sep -- 用来间隔多个对象，默认值是一个空格。
* end -- 用来设定以什么结尾。默认值是换行符 \n，我们可以换成其他字符串。
* file -- 要写入的文件对象。

### **返回值**
无。

### **实例**
以下展示了使用 print 函数的实例：
```python 
>>>print(1)  
1  
>>> print("Hello World")  
Hello World  
 
>>> a = 1
>>> b = 'runoob'
>>> print(a,b)
1 runoob
 
>>> print("aaa""bbb")
aaabbb
>>> print("aaa","bbb")
aaa bbb
>>> 
 
>>> print("www","runoob","com",sep=".")  # 设置间隔符
www.runoob.com
```
---
## **Python property() 函数**
### **描述**
property() 函数的作用是在新式类中返回属性值。
### **语法**
以下是 property() 方法的语法:
```python
class property([fget[, fset[, fdel[, doc]]]])
```
### **参数**
* fget -- 获取属性值的函数
* fset -- 设置属性值的函数
* fdel -- 删除属性值函数
* doc -- 属性描述信息

### **返回值**
返回新式类属性。

### **实例**
定义一个可控属性值 x
```python 
class C(object):
    def __init__(self):
        self._x = None
 
    def getx(self):
        return self._x
 
    def setx(self, value):
        self._x = value
 
    def delx(self):
        del self._x
 
    x = property(getx, setx, delx, "I'm the 'x' property.")
```

如果 c 是 C 的实例化, c.x 将触发 getter,c.x = value 将触发 setter ， del c.x 触发 deleter。

如果给定 doc 参数，其将成为这个属性值的 docstring，否则 property 函数就会复制 fget 函数的 docstring（如果有的话）。

将 property 函数用作装饰器可以很方便的创建只读属性：
```python 
class Parrot(object):
    def __init__(self):
        self._voltage = 100000
 
    @property
    def voltage(self):
        """Get the current voltage."""
        return self._voltage
```
上面的代码将 voltage() 方法转化成同名只读属性的 getter 方法。

property 的 getter,setter 和 deleter 方法同样可以用作装饰器：

```python 
class C(object):
    def __init__(self):
        self._x = None
 
    @property
    def x(self):
        """I'm the 'x' property."""
        return self._x
 
    @x.setter
    def x(self, value):
        self._x = value
 
    @x.deleter
    def x(self):
        del self._x
```
这个代码和第一个例子完全相同，但要注意这些额外函数的名字和 property 下的一样，例如这里的 x。

---
## **Python3 range() 函数用法**
### **描述**
Python3 range() 函数返回的是一个可迭代对象（类型是对象），而不是列表类型， 所以打印的时候不会打印列表。

Python3 list() 函数是对象迭代器，可以把range()返回的可迭代对象转为一个列表，返回的变量类型为列表。

Python2 range() 函数返回的是列表。
### **语法**

```python
range(stop)
range(start, stop[, step])
```
### **参数**
* start: 计数从 start 开始。默认是从 0 开始。例如range（5）等价于range（0， 5）;
* stop: 计数到 stop 结束，但不包括 stop。例如：range（0， 5） 是[0, 1, 2, 3, 4]没有5
* step：步长，默认为1。例如：range（0， 5） 等价于 range(0, 5, 1)

### **实例**

```python 
>>>range(5)
range(0, 5)
>>> for i in range(5):
...     print(i)
... 
0
1
2
3
4
>>> list(range(5))
[0, 1, 2, 3, 4]
>>> list(range(0))
[]
>>>
```

有两个参数或三个参数的情况（第二种构造方法）：:
```python 
>>>list(range(0, 30, 5))
[0, 5, 10, 15, 20, 25]
>>> list(range(0, 10, 2))
[0, 2, 4, 6, 8]
>>> list(range(0, -10, -1))
[0, -1, -2, -3, -4, -5, -6, -7, -8, -9]
>>> list(range(1, 0))
[]
>>>
>>>
```
---
## **Python repr() 函数**
### **描述**
repr() 函数将对象转化为供解释器读取的形式。
### **语法**
以下是 repr() 方法的语法:
```python
repr(object)
```
### **参数**
* object -- 对象。

### **返回值**
返回一个对象的 string 格式。

### **实例**
以下展示了使用 repr() 方法的实例：
```python 
>>>s = 'RUNOOB'
>>> repr(s)
"'RUNOOB'"
>>> dict = {'runoob': 'runoob.com', 'google': 'google.com'};
>>> repr(dict)
"{'google': 'google.com', 'runoob': 'runoob.com'}"
>>>
```
---
## **Python3 reversed 函数**
### **描述**
reversed 函数返回一个反转的迭代器。
### **语法**
以下是 reversed 的语法:
```python
reversed(seq)
```
### **参数**
* seq -- 要转换的序列，可以是 tuple, string, list 或 range。

### **返回值**
返回一个反转的迭代器。

### **实例**
以下展示了使用 tuple 的实例：
```python 
#!/usr/bin/env python3
 
# 字符串
seqString = 'Runoob'
print(list(reversed(seqString)))
 
# 元组
seqTuple = ('R', 'u', 'n', 'o', 'o', 'b')
print(list(reversed(seqTuple)))
 
# range
seqRange = range(5, 9)
print(list(reversed(seqRange)))
 
# 列表
seqList = [1, 2, 4, 3, 5]
print(list(reversed(seqList)))
```

以上实例输出结果为：
```python 
['b', 'o', 'o', 'n', 'u', 'R']
['b', 'o', 'o', 'n', 'u', 'R']
[8, 7, 6, 5]
[5, 3, 4, 2, 1]
```
---
## **Python3 round() 函数**
### **描述**
round() 方法返回浮点数x的四舍五入值。
### **语法**
以下是 round() 方法的语法:
```python
round( x [, n]  )
```
### **参数**
* x -- 数字表达式。
* n -- 表示从小数点位数，其中 x 需要四舍五入，默认值为 0。

### **返回值**
返回浮点数x的四舍五入值。

### **实例**
以下展示了使用 round() 方法的实例：
```python 
#!/usr/bin/python3

print ("round(70.23456) : ", round(70.23456))
print ("round(56.659,1) : ", round(56.659,1))
print ("round(80.264, 2) : ", round(80.264, 2))
print ("round(100.000056, 3) : ", round(100.000056, 3))
print ("round(-100.000056, 3) : ", round(-100.000056, 3))
```

以上实例运行后输出结果为：
```python 
round(70.23456) :  70
round(56.659,1) :  56.7
round(80.264, 2) :  80.26
round(100.000056, 3) :  100.0
round(-100.000056, 3) :  -100.0
```
---
## **Python set() 函数**
### **描述**
set() 函数创建一个无序不重复元素集，可进行关系测试，删除重复数据，还可以计算交集、差集、并集等。
### **语法**
set 语法：
```python
class set([iterable])
```
### **参数**
* iterable -- 可迭代对象对象；

### **返回值**
返回新的集合对象。

### **实例**
以下实例展示了 set 的使用方法：
```python 
>>>x = set('runoob')
>>> y = set('google')
>>> x, y
(set(['b', 'r', 'u', 'o', 'n']), set(['e', 'o', 'g', 'l']))   # 重复的被删除
>>> x & y         # 交集
set(['o'])
>>> x | y         # 并集
set(['b', 'e', 'g', 'l', 'o', 'n', 'r', 'u'])
>>> x - y         # 差集
set(['r', 'b', 'u', 'n'])
>>>
```
---
## **Python setattr() 函数**
### **描述**
setattr() 函数对应函数 getattr()，用于设置属性值，该属性不一定是存在的。
### **语法**
setattr() 语法：
```python
setattr(object, name, value)
```
### **参数**
* object -- 对象。
* name -- 字符串，对象属性。
* value -- 属性值。

### **返回值**
无。

### **实例**
以下实例展示了 setattr() 函数的使用方法：

对已存在的属性进行赋值：
```python 
>>>class A(object):
...     bar = 1
... 
>>> a = A()
>>> getattr(a, 'bar')          # 获取属性 bar 值
1
>>> setattr(a, 'bar', 5)       # 设置属性 bar 值
>>> a.bar
5
```

如果属性不存在会创建一个新的对象属性，并对属性赋值：
```python 
>>>class A():
...     name = "runoob"
... 
>>> a = A()
>>> setattr(a, "age", 28)
>>> print(a.age)
28
>>>
```
---
## **Python slice() 函数**
### **描述**
slice() 函数实现切片对象，主要用在切片操作函数里的参数传递。
### **语法**
slice 语法：
```python
class slice(stop)
class slice(start, stop[, step])
```
### **参数**
* start -- 起始位置
* stop -- 结束位置
* step -- 间距

### **返回值**
返回一个切片对象。

### **实例**
以下实例展示了 slice 的使用方法：
```python 
>>>myslice = slice(5)    # 设置截取5个元素的切片
>>> myslice
slice(None, 5, None)
>>> arr = range(10)
>>> arr
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
>>> arr[myslice]         # 截取 5 个元素
[0, 1, 2, 3, 4]
>>>
```
---
## **Python3 sorted() 函数**
### **描述**
sorted() 函数对所有可迭代的对象进行排序操作。

*sort 与 sorted 区别：*  
*sort 是应用在 list 上的方法，sorted 可以对所有可迭代的对象进行排序操作。*  
*list 的 sort 方法返回的是对已经存在的列表进行操作，而内建函数 sorted 方法返回的是一个新的 list，而不是在原来的基础上进行的操作。*

### **语法**
sorted 语法：
```python
sorted(iterable, key=None, reverse=False)  
```
### **参数**
* iterable -- 可迭代对象。
* key -- 主要是用来进行比较的元素，只有一个参数，具体的函数的参数就是取自于可迭代对象中，指定可迭代对象中的一个元素来进行排序。
* reverse -- 排序规则，reverse = True 降序 ， reverse = False 升序（默认）。

### **返回值**
返回重新排序的列表。

### **实例**
以下实例展示了 sorted 的最简单的使用方法：
```python 
>>>sorted([5, 2, 3, 1, 4])
[1, 2, 3, 4, 5]                      # 默认为升序
```

你也可以使用 list 的 list.sort() 方法。这个方法会修改原始的 list（返回值为None）。通常这个方法不如sorted()方便-如果你不需要原始的 list，list.sort()方法效率会稍微高一些。
```python 
>>>a=[5,2,3,1,4]
>>> a.sort()
>>> a
[1,2,3,4,5]
```

另一个区别在于list.sort() 方法只为 list 定义。而 sorted() 函数可以接收任何的 iterable。
```python 
>>>sorted({1: 'D', 2: 'B', 3: 'B', 4: 'E', 5: 'A'})
[1, 2, 3, 4, 5]
```

利用key进行倒序排序
```python 
>>>example_list = [5, 0, 6, 1, 2, 7, 3, 4]
>>> result_list = sorted(example_list, key=lambda x: x*-1)
>>> print(result_list)
[7, 6, 5, 4, 3, 2, 1, 0]
>>>
```

要进行反向排序，也通过传入第三个参数 reverse=True：
```python 
>>>example_list = [5, 0, 6, 1, 2, 7, 3, 4]
>>> sorted(example_list, reverse=True)
[7, 6, 5, 4, 3, 2, 1, 0]
```
---
## **Python staticmethod() 函数**
### **描述**
python staticmethod 返回函数的静态方法。

该方法不强制要求传递参数，如下声明一个静态方法：
```python
class C(object):
    @staticmethod
    def f(arg1, arg2, ...):
        ...
```
以上实例声明了静态方法 f，从而可以实现实例化使用 C().f()，当然也可以不实例化调用该方法 C.f()。
### **语法**

```python
staticmethod(function)
```
### **参数**
* 无


### **实例**

```python 
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
class C(object):
    @staticmethod
    def f():
        print('runoob');
 
C.f();          # 静态方法无需实例化
cobj = C()
cobj.f()        # 也可以实例化后调用
```

以上实例输出结果为：
```python 
runoob
runoob
```
---
## **Python str() 函数**
### **描述**
str() 函数将对象转化为适于人阅读的形式。
### **语法**
以下是 str() 方法的语法:
```python
class str(object='')
```
### **参数**
* object -- 对象。

### **返回值**
返回一个对象的string格式。

### **实例**
以下展示了使用 str() 方法的实例：
```python 
>>>s = 'RUNOOB'
>>> str(s)
'RUNOOB'
>>> dict = {'runoob': 'runoob.com', 'google': 'google.com'};
>>> str(dict)
"{'google': 'google.com', 'runoob': 'runoob.com'}"
>>>
```
---
## **Python sum() 函数**
### **描述**
sum() 方法对系列进行求和计算。
### **语法**
以下是 sum() 方法的语法:
```python
sum(iterable[, start])
```
### **参数**
* iterable -- 可迭代对象，如：列表、元组、集合。
* start -- 指定相加的参数，如果没有设置这个值，默认为0。

### **返回值**
返回计算结果。

### **实例**
以下展示了使用 sum 函数的实例：
```python 
>>>sum([0,1,2])  
3  
>>> sum((2, 3, 4), 1)        # 元组计算总和后再加 1
10
>>> sum([0,1,2,3,4], 2)      # 列表计算总和后再加 2
12
```
---
## **Python super() 函数**
### **描述**
**super()** 函数是用于调用父类(超类)的一个方法。

super 是用来解决多重继承问题的，直接用类名调用父类方法在使用单继承的时候没问题，但是如果使用多继承，会涉及到查找顺序（MRO）、重复调用（钻石继承）等种种问题。

MRO 就是类的方法解析顺序表, 其实也就是继承父类方法时的顺序表。
### **语法**
以下是 super() 方法的语法:
```python
super(type[, object-or-type])
```
### **参数**
* type -- 类。
* object-or-type -- 类，一般是 self
Python3.x 和 Python2.x 的一个区别是: Python 3 可以使用直接使用 super().xxx 代替 super(Class, self).xxx :

Python3.x 实例：
```python 
class A:
     def add(self, x):
         y = x+1
         print(y)
class B(A):
    def add(self, x):
        super().add(x)
b = B()
b.add(2)  # 3
```
### **返回值**
无。

### **实例**
以下展示了使用 super 函数的实例：
```python 
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
class FooParent(object):
    def __init__(self):
        self.parent = 'I\'m the parent.'
        print ('Parent')
    
    def bar(self,message):
        print ("%s from Parent" % message)
 
class FooChild(FooParent):
    def __init__(self):
        # super(FooChild,self) 首先找到 FooChild 的父类（就是类 FooParent），然后把类 FooChild 的对象转换为类 FooParent 的对象
        super(FooChild,self).__init__()    
        print ('Child')
        
    def bar(self,message):
        super(FooChild, self).bar(message)
        print ('Child bar fuction')
        print (self.parent)
 
if __name__ == '__main__':
    fooChild = FooChild()
    fooChild.bar('HelloWorld')
```


执行结果：
```python 
Parent
Child
HelloWorld from Parent
Child bar fuction
I'm the parent.
```
---
## **Python3 tuple 函数**
### **描述**
tuple 函数将列表转换为元组。
### **语法**
以下是 tuple 的语法:
```python
tuple( seq )
```
### **参数**
* seq -- 要转换为元组的序列。

### **返回值**
返回元组。

### **实例**
以下展示了使用 tuple 的实例：
```python 
>>>list1= ['Google', 'Taobao', 'Runoob', 'Baidu']
>>> tuple1=tuple(list1)
>>> tuple1
('Google', 'Taobao', 'Runoob', 'Baidu')
```
---
## **Python type() 函数**
### **描述**
type() 函数如果你只有第一个参数则返回对象的类型，三个参数返回新的类型对象。

*isinstance() 与 type() 区别：*  
* *type() 不会认为子类是一种父类类型，不考虑继承关系。*
* *isinstance() 会认为子类是一种父类类型，考虑继承关系。
如果要判断两个类型是否相同推荐使用 isinstance()。*

### **语法**
以下是 type() 方法的语法:
```python
type(object)
type(name, bases, dict)
```
### **参数**
* name -- 类的名称。
* bases -- 基类的元组。
* dict -- 字典，类内定义的命名空间变量。

### **返回值**
一个参数返回对象类型, 三个参数，返回新的类型对象。

### **实例**
以下展示了使用 type 函数的实例：
```python 
# 一个参数实例
>>> type(1)
<type 'int'>
>>> type('runoob')
<type 'str'>
>>> type([2])
<type 'list'>
>>> type({0:'zero'})
<type 'dict'>
>>> x = 1          
>>> type( x ) == int    # 判断类型是否相等
True
 
# 三个参数
>>> class X(object):
...     a = 1
...
>>> X = type('X', (object,), dict(a=1))  # 产生一个新的类型 X
>>> X
<class '__main__.X'>
```

type() 与 isinstance()区别：
```python 
class A:
    pass
 
class B(A):
    pass
 
isinstance(A(), A)    # returns True
type(A()) == A        # returns True
isinstance(B(), A)    # returns True
type(B()) == A        # returns False
```
---
## **Python vars() 函数**
### **描述**
**vars()** 函数返回对象object的属性和属性值的字典对象。
### **语法**
vars() 函数语法：
```python
vars([object])
```
### **参数**
* object -- 对象

### **返回值**
返回对象object的属性和属性值的字典对象，如果没有参数，就打印当前调用位置的属性和属性值 类似 locals()。

### **实例**
以下实例展示了 vars() 的使用方法：
```python 
>>>print(vars())
{'__builtins__': <module '__builtin__' (built-in)>, '__name__': '__main__', '__doc__': None, '__package__': None}
>>> class Runoob:
...     a = 1
... 
>>> print(vars(Runoob))
{'a': 1, '__module__': '__main__', '__doc__': None}
>>> runoob = Runoob()
>>> print(vars(runoob))
{}
```
---
## **Python3 zip() 函数**
### **描述**
**zip()** 函数用于将可迭代的对象作为参数，将对象中对应的元素打包成一个个元组，然后返回由这些元组组成的对象，这样做的好处是节约了不少的内存。

我们可以使用 list() 转换来输出列表。

如果各个迭代器的元素个数不一致，则返回列表长度与最短的对象相同，利用 * 号操作符，可以将元组解压为列表。

*zip 方法在 Python 2 和 Python 3 中的不同：在 Python 2.x zip() 返回的是一个列表。*  

### **语法**
zip 语法：
```python
zip([iterable, ...])
```
### **参数**
* iterabl -- 一个或多个迭代器;

### **返回值**
返回一个对象。

### **实例**
以下实例展示了 zip 的使用方法：
```python 
>>>a = [1,2,3]
>>> b = [4,5,6]
>>> c = [4,5,6,7,8]
>>> zipped = zip(a,b)     # 返回一个对象
>>> zipped
<zip object at 0x103abc288>
>>> list(zipped)  # list() 转换为列表
[(1, 4), (2, 5), (3, 6)]
>>> list(zip(a,c))              # 元素个数与最短的列表一致
[(1, 4), (2, 5), (3, 6)]
 
>>> a1, a2 = zip(*zip(a,b))          # 与 zip 相反，zip(*) 可理解为解压，返回二维矩阵式
>>> list(a1)
[1, 2, 3]
>>> list(a2)
[4, 5, 6]
>>>
```
---
## **Python \_\_import__() 函数**
### **描述**
\_\_import__() 函数用于动态加载类和函数 。

如果一个模块经常变化就可以使用 \_\_import__() 来动态载入。
### **语法**
\_\_import__ 语法：
```python
__import__(name[, globals[, locals[, fromlist[, level]]]])
```
### **参数**
* name -- 模块名

### **返回值**
返回元组列表。

### **实例**
以下实例展示了 \_\_import__ 的使用方法：
a.py 文件代码：
```python 
#!/usr/bin/env python    
#encoding: utf-8  
 
import os  
 
print ('在 a.py 文件中 %s' % id(os))
```


test.py 文件代码：
```python 
#!/usr/bin/env python    
#encoding: utf-8  
 
import sys  
__import__('a')        # 导入 a.py 模块
```

执行 test.py 文件，输出结果为：
```python 
在 a.py 文件中 4394716136
```




