## **Python3 日期和时间**
Python 程序能用很多方式处理日期和时间，转换日期格式是一个常见的功能。  
Python 提供了一个 time 和 calendar 模块可以用于格式化日期和时间。  
时间间隔是以秒为单位的浮点小数。  
每个时间戳都以自从1970年1月1日午夜（历元）经过了多长时间来表示。  
Python 的 time 模块下有很多函数可以转换常见日期格式。如函数time.time()用于获取当前时间戳, 如下实例:
```python
#!/usr/bin/python3

import time;  # 引入time模块

ticks = time.time()
print ("当前时间戳为:", ticks)
```
以上实例输出结果：
```python
当前时间戳为: 1459996086.7115328
```
时间戳单位最适于做日期运算。但是1970年之前的日期就无法以此表示了。太遥远的日期也不行，UNIX和Windows只支持到2038年。

---
### **什么是时间元组？**
很多Python函数用一个元组装起来的9组数字处理时间:

![](https://github.com/anmiaru/python3/raw/master/image/37-1.png)

上述也就是struct_time元组。这种结构具有如下属性：

![](https://github.com/anmiaru/python3/raw/master/image/37-2.png)

---
### **获取当前时间**
从返回浮点数的时间戳方式向时间元组转换，只要将浮点数传递给如localtime之类的函数。
```python
#!/usr/bin/python3

import time

localtime = time.localtime(time.time())
print ("本地时间为 :", localtime)
```
以上实例输出结果：
```python
本地时间为 : time.struct_time(tm_year=2016, tm_mon=4, tm_mday=7, tm_hour=10, tm_min=28, tm_sec=49, tm_wday=3, tm_yday=98, tm_isdst=0)
```

---
### **获取格式化的时间**
你可以根据需求选取各种格式，但是最简单的获取可读的时间模式的函数是asctime():

```python
#!/usr/bin/python3

import time

localtime = time.asctime( time.localtime(time.time()) )
print ("本地时间为 :", localtime)
```
以上实例输出结果：
```python
本地时间为 : Thu Apr  7 10:29:13 2016
```


---
### **格式化日期**
我们可以使用 time 模块的 strftime 方法来格式化日期：
```python
time.strftime(format[, t])
```

```python
#!/usr/bin/python3

import time

# 格式化成2016-03-20 11:45:39形式
print (time.strftime("%Y-%m-%d %H:%M:%S", time.localtime()))

# 格式化成Sat Mar 28 22:24:24 2016形式
print (time.strftime("%a %b %d %H:%M:%S %Y", time.localtime()))
  
# 将格式字符串转换为时间戳
a = "Sat Mar 28 22:24:24 2016"
print (time.mktime(time.strptime(a,"%a %b %d %H:%M:%S %Y")))
```
以上实例输出结果：
```python
2016-04-07 10:29:46
Thu Apr 07 10:29:46 2016
1459175064.0
```
python中时间日期格式化符号：

* %y 两位数的年份表示（00-99）
* %Y 四位数的年份表示（000-9999）
* %m 月份（01-12）
* %d 月内中的一天（0-31）
* %H 24小时制小时数（0-23）
* %I 12小时制小时数（01-12）
* %M 分钟数（00=59）
* %S 秒（00-59）
* %a 本地简化星期名称
* %A 本地完整星期名称
* %b 本地简化的月份名称
* %B 本地完整的月份名称
* %c 本地相应的日期表示和时间表示
* %j 年内的一天（001-366）
* %p 本地A.M.或P.M.的等价符
* %U 一年中的星期数（00-53）星期天为星期的开始
* %w 星期（0-6），星期天为星期的开始
* %W 一年中的星期数（00-53）星期一为星期的开始
* %x 本地相应的日期表示
* %X 本地相应的时间表示
* %Z 当前时区的名称
* %% %号本身

---
### **获取某月日历**
Calendar模块有很广泛的方法用来处理年历和月历，例如打印某月的月历：
```python
#!/usr/bin/python3

import calendar

cal = calendar.month(2016, 1)
print ("以下输出2016年1月份的日历:")
print (cal)
```
以上实例输出结果：
```python
以下输出2016年1月份的日历:
    January 2016
Mo Tu We Th Fr Sa Su
             1  2  3
 4  5  6  7  8  9 10
11 12 13 14 15 16 17
18 19 20 21 22 23 24
25 26 27 28 29 30 31
```

---
### **Time 模块**
Time 模块包含了以下内置函数，既有时间处理的，也有转换时间格式的：

![](https://github.com/anmiaru/python3/raw/master/image/37-3.png)

![](https://github.com/anmiaru/python3/raw/master/image/37-4.png)

![](https://github.com/anmiaru/python3/raw/master/image/37-5.png)

![](https://github.com/anmiaru/python3/raw/master/image/37-6.png)

Time模块包含了以下2个非常重要的属性：

![](https://github.com/anmiaru/python3/raw/master/image/37-7.png)

---
### **日历（Calendar）模块**
此模块的函数都是日历相关的，例如打印某月的字符月历。  
星期一是默认的每周第一天，星期天是默认的最后一天。更改设置需调用calendar.setfirstweekday()函数。模块包含了以下内置函数：

![](https://github.com/anmiaru/python3/raw/master/image/37-8.png)

![](https://github.com/anmiaru/python3/raw/master/image/37-9.png)

![](https://github.com/anmiaru/python3/raw/master/image/37-10.png)

---
### **其他相关模块和函数**
在Python中，其他处理日期和时间的模块还有：
* time 模块
* datetime模块