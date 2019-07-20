## **Python3实例**

以下实例在 Python3.4.3 版本下测试通过：
### **Python Hello World 实例**
以下实例为学习Python的第一个实例，即如何输出"Hello World!"：
```python 
# -*- coding: UTF-8 -*-

# Filename : helloworld.py

# 该实例输出 Hello World!
print('Hello World!')
```

执行以上代码输出结果为：
```python 
Hello World！
```

---


### **Python 数字求和**
以下实例为通过用户输入两个数字，并计算两个数字之和：
```python 
# -*- coding: UTF-8 -*-
 
# Filename : test.py
 
# 用户输入数字
num1 = input('输入第一个数字：')
num2 = input('输入第二个数字：')
 
# 求和
sum = float(num1) + float(num2)
 
# 显示计算结果
print('数字 {0} 和 {1} 相加结果为： {2}'.format(num1, num2, sum))
```
执行以上代码输出结果为：
```python 
输入第一个数字：1.5
输入第二个数字：2.5
数字 1.5 和 2.5 相加结果为： 4.0
```
在该实例中，我们通过用户输入两个数字来求和。使用了内置函数 input() 来获取用户的输入，input() 返回一个字符串，所以我们需要使用 float() 方法将字符串转换为数字。    
两数字运算，求和我们使用了加号 (+)运算符，除此外，还有 减号 (-), 乘号 (*), 除号 (/), 地板除 (//) 或 取余 (%)。更多数字运算可以查看我们之前学习过的Python 数字运算。    
我们还可以将以上运算，合并为一行代码：   
```python 
# -*- coding: UTF-8 -*-
 
# Filename : test.py
 
print('两数之和为 %.1f' %(float(input('输入第一个数字：'))+float(input('输入第二个数字：'))))
```

执行以上代码输出结果为：
```python 
$ python test.py 
输入第一个数字：1.5
输入第二个数字：2.5
两数之和为 4.0
```
---

### **Python 数字平方根**
平方根，又叫二次方根，表示为〔√〕，如：数学语言为：√16=4。语言描述为：根号下16=4。

以下实例为通过用户输入一个数字，并计算这个数字的平方根：
```python 
# -*- coding: UTF-8 -*-
 
# Filename : test.py
 
num = float(input('请输入一个数字： '))
num_sqrt = num ** 0.5
print(' %0.3f 的平方根为 %0.3f'%(num ,num_sqrt))
```

执行以上代码输出结果为：
```python 
$ python test.py 
请输入一个数字： 4
 4.000 的平方根为 2.000
```

在该实例中，我们通过用户输入一个数字，并使用指数运算符 ** 来计算该数的平方根。   
该程序只适用于正数。负数和复数可以使用以下的方式：
```python 
# -*- coding: UTF-8 -*-
 
# Filename : test.py
 
# 计算实数和复数平方根
# 导入复数数学模块
 
import cmath
 
num = int(input("请输入一个数字: "))
num_sqrt = cmath.sqrt(num)
print('{0} 的平方根为 {1:0.3f}+{2:0.3f}j'.format(num ,num_sqrt.real,num_sqrt.imag))
```
执行以上代码输出结果为：
```python 
$ python test.py 
请输入一个数字: -8
-8 的平方根为 0.000+2.828j
```
该实例中，我们使用了 cmath (complex math) 模块的 sqrt() 方法。

---

### **Python 二次方程**
以下实例为通过用户输入数字，并计算二次方程：
```python 
# Filename : test.py
 
# 二次方程式 ax**2 + bx + c = 0
# a、b、c 用户提供，为实数，a ≠ 0
 
# 导入 cmath(复杂数学运算) 模块
import cmath
 
a = float(input('输入 a: '))
b = float(input('输入 b: '))
c = float(input('输入 c: '))
 
# 计算
d = (b**2) - (4*a*c)
 
# 两种求解方式
sol1 = (-b-cmath.sqrt(d))/(2*a)
sol2 = (-b+cmath.sqrt(d))/(2*a)
 
print('结果为 {0} 和 {1}'.format(sol1,sol2))
```
执行以上代码输出结果为：
```python 
$ python test.py 
输入 a: 1
输入 b: 5
输入 c: 6
结果为 (-3+0j) 和 (-2+0j)
```
该实例中，我们使用了 cmath (complex math) 模块的 sqrt() 方法 来计算平方根。

---

### **Python 计算三角形的面积**
以下实例为通过用户输入三角形三边长度，并计算三角形的面积：
```python 
# -*- coding: UTF-8 -*-
 
# Filename : test.py
 
 
a = float(input('输入三角形第一边长: '))
b = float(input('输入三角形第二边长: '))
c = float(input('输入三角形第三边长: '))
 
# 计算半周长
s = (a + b + c) / 2
 
# 计算面积
area = (s*(s-a)*(s-b)*(s-c)) ** 0.5
print('三角形面积为 %0.2f' %area)
```
执行以上代码输出结果为：
```python 
$ python test.py 
输入三角形第一边长: 5
输入三角形第二边长: 6
输入三角形第三边长: 7
三角形面积为 14.70
```
---

### **Python 计算圆的面积**
圆的面积公式为 ：S=∏ r^2  
公式中 r 为圆的半径。
```python 
# 定义一个方法来计算圆的面积
def findArea(r): 
    PI = 3.142
    return PI * (r*r)
  
# 调用方法
print("圆的面积为 %.6f" % findArea(5)) 
```

以上实例输出结果为：
```python 
圆的面积为 78.550000
```
---

### **Python 随机数生成**
以下实例演示了如何生成一个随机数：
```python 
# -*- coding: UTF-8 -*-
 
# Filename : test.py
 
# 生成 0 ~ 9 之间的随机数
 
# 导入 random(随机数) 模块
import random
 
print(random.randint(0,9))
```
执行以上代码输出结果为：
```python 
4
```
以上实例我们使用了 random 模块的 randint() 函数来生成随机数，你每次执行后都返回不同的数字（0 到 9），该函数的语法为：
```python 
random.randint(a,b)
```
函数返回数字 N ，N 为 a 到 b 之间的数字（a <= N <= b），包含 a 和 b。

---

### **Python 摄氏温度转华氏温度**
以下实例演示了如何将摄氏温度转华氏温度：
```python 
# -*- coding: UTF-8 -*-
 
# Filename : test.py
 
# 用户输入摄氏温度
 
# 接收用户输入
celsius = float(input('输入摄氏温度: '))
 
# 计算华氏温度
fahrenheit = (celsius * 1.8) + 32
print('%0.1f 摄氏温度转为华氏温度为 %0.1f ' %(celsius,fahrenheit))
```
执行以上代码输出结果为：
```python 
输入摄氏温度: 38
38.0 摄氏温度转为华氏温度为 100.4 
```
以上实例中，摄氏温度转华氏温度的公式为 celsius * 1.8 = fahrenheit - 32。所以得到以下式子：
```python 
celsius = (fahrenheit - 32) / 1.8
```
---

### **Python 交换变量**

以下实例通过用户输入两个变量，并相互交换：
```python 
# -*- coding: UTF-8 -*-
 
# Filename : test.py
 
# 用户输入
 
x = input('输入 x 值: ')
y = input('输入 y 值: ')
 
# 创建临时变量，并交换
temp = x
x = y
y = temp
 
print('交换后 x 的值为: {}'.format(x))
print('交换后 y 的值为: {}'.format(y))
```
执行以上代码输出结果为：
```python 
输入 x 值: 2
输入 y 值: 3
交换后 x 的值为: 3
交换后 y 的值为: 2
```
以上实例中，我们创建了临时变量 temp ，并将 x 的值存储在 temp 变量中，接着将 y 值赋给 x，最后将 temp 赋值给 y 变量。  
#### **不使用临时变量**   
我们也可以不创建临时变量，用一个非常优雅的方式来交换变量：
```python 
x,y = y,x
```
所以以上实例就可以修改为：
```python 
# -*- coding: UTF-8 -*-
 
# Filename : test.py

# 用户输入
 
x = input('输入 x 值: ')
y = input('输入 y 值: ')
 
# 不使用临时变量
x,y = y,x
 
print('交换后 x 的值为: {}'.format(x))
print('交换后 y 的值为: {}'.format(y))
```

执行以上代码输出结果为：
```python 
输入 x 值: 1
输入 y 值: 2
交换后 x 的值为: 2
交换后 y 的值为: 1
```
---

### **Python if 语句**
以下实例通过使用 if...elif...else 语句判断数字是正数、负数或零：
```python 
# Filename : test.py
 
# 用户输入数字
 
num = float(input("输入一个数字: "))
if num > 0:
   print("正数")
elif num == 0:
   print("零")
else:
   print("负数")
```
执行以上代码输出结果为：
```python 
输入一个数字: 3
正数
```

我们也可以使用内嵌 if 语句来实现：
```python 
# Filename ：test.py
 
# 内嵌 if 语句
 
num = float(input("输入一个数字: "))
if num >= 0:
   if num == 0:
       print("零")
   else:
       print("正数")
else:
   print("负数")
```
执行以上代码输出结果为：
```python 
输入一个数字: 0
零
```
---

### **Python 判断字符串是否为数字**
以下实例通过创建自定义函数 is_number() 方法来判断字符串是否为数字：
```python 
# -*- coding: UTF-8 -*-
 
# Filename : test.py
 
def is_number(s):
    try:
        float(s)
        return True
    except ValueError:
        pass
 
    try:
        import unicodedata
        unicodedata.numeric(s)
        return True
    except (TypeError, ValueError):
        pass
 
    return False
 
# 测试字符串和数字
print(is_number('foo'))   # False
print(is_number('1'))     # True
print(is_number('1.3'))   # True
print(is_number('-1.37')) # True
print(is_number('1e3'))   # True
 
# 测试 Unicode
# 阿拉伯语 5
print(is_number('٥'))  # True
# 泰语 2
print(is_number('๒'))  # True
# 中文数字
print(is_number('四')) # True
# 版权号
print(is_number('©'))  # False
```
我们也可以使用内嵌 if 语句来实现：  
执行以上代码输出结果为：
```python 
False
True
True
True
True
True
True
True
False
```
**更多方法**  
Python isdigit() 方法检测字符串是否只由数字组成。  
Python isnumeric() 方法检测字符串是否只由数字组成。这种方法是只针对unicode对象。

---

### **Python 判断奇数偶数**
以下实例用于判断一个数字是否为奇数或偶数：
```python 
# Filename : test.py

# Python 判断奇数偶数
# 如果是偶数除于 2 余数为 0
# 如果余数为 1 则为奇数
 
num = int(input("输入一个数字: "))
if (num % 2) == 0:
   print("{0} 是偶数".format(num))
else:
   print("{0} 是奇数".format(num))
```
我们也可以使用内嵌 if 语句来实现：  
执行以上代码输出结果为：
```python 
输入一个数字: 3
3 是奇数
```
---

### **Python 判断闰年**
以下实例用于判断用户输入的年份是否为闰年：
```python 
# -*- coding: UTF-8 -*-
 
# Filename : test.py
 
year = int(input("输入一个年份: "))
if (year % 4) == 0:
   if (year % 100) == 0:
       if (year % 400) == 0:
           print("{0} 是闰年".format(year))   # 整百年能被400整除的是闰年
       else:
           print("{0} 不是闰年".format(year))
   else:
       print("{0} 是闰年".format(year))       # 非整百年能被4整除的为闰年
else:
   print("{0} 不是闰年".format(year))
```

我们也可以使用内嵌 if 语句来实现：  
执行以上代码输出结果为：
```python 
输入一个年份: 2000
2000 是闰年
```

```python 
输入一个年份: 2011
2011 不是闰年
```
---

### **Python 获取最大值函数**
以下实例中我们使用max()方法求最大值：
```python 
# -*- coding: UTF-8 -*-
 
# Filename : test.py
 
# 最简单的
print(max(1, 2))
print(max('a', 'b'))
 
# 也可以对列表和元组使用
print(max([1,2]))
print(max((1,2)))
 
# 更多实例
print("80, 100, 1000 最大值为: ", max(80, 100, 1000))
print("-20, 100, 400最大值为: ", max(-20, 100, 400))
print("-80, -20, -10最大值为: ", max(-80, -20, -10))
print("0, 100, -400最大值为:", max(0, 100, -400))
```
执行以上代码输出结果为：
```python 
2
b
2
2
80, 100, 1000 最大值为:  1000
-20, 100, 400 最大值为:  400
-80, -20, -10 最大值为:  -10
0, 100, -400 最大值为: 100
```
---

### **Python 质数判断**
一个大于1的自然数，除了1和它本身外，不能被其他自然数（质数）整除（2, 3, 5, 7等），换句话说就是该数除了1和它本身以外不再有其他的因数。
```python 
# -*- coding: UTF-8 -*-
 
# Filename : test.py
 
# Python 程序用于检测用户输入的数字是否为质数
 
# 用户输入数字
num = int(input("请输入一个数字: "))
 
# 质数大于 1
if num > 1:
   # 查看因子
   for i in range(2,num):
       if (num % i) == 0:
           print(num,"不是质数")
           print(i,"乘于",num//i,"是",num)
           break
   else:
       print(num,"是质数")
       
# 如果输入的数字小于或等于 1，不是质数
else:
   print(num,"不是质数")
```
执行以上代码输出结果为：
```python 
$ python3 test.py 
请输入一个数字: 1
1 不是质数
$ python3 test.py 
请输入一个数字: 4
4 不是质数
2 乘于 2 是 4
$ python3 test.py 
请输入一个数字: 5
5 是质数
```
---

### **Python 输出指定范围内的素数**
素数（prime number）又称质数，有无限个。除了1和它本身以外不再被其他的除数整除。  
以下实例可以输出指定范围内的素数：
```python 
#!/usr/bin/python3
 
# 输出指定范围内的素数
 
# take input from the user
lower = int(input("输入区间最小值: "))
upper = int(input("输入区间最大值: "))
 
for num in range(lower,upper + 1):
    # 素数大于 1
    if num > 1:
        for i in range(2,num):
            if (num % i) == 0:
                break
        else:
            print(num)
```

执行以上程序，输出结果为：
```python 
$ python3 test.py 
输入区间最小值: 1
输入区间最大值: 100
2
3
5
7
11
13
17
19
23
29
31
37
41
43
47
53
59
61
67
71
73
79
83
89
97
```
---

### **Python 阶乘实例**
整数的阶乘（英语：factorial）是所有小于及等于该数的正整数的积，0的阶乘为1。即：n!=1×2×3×...×n。
```python 
#!/usr/bin/python3
 
# Filename : test.py
 
# 通过用户输入数字计算阶乘
 
# 获取用户输入的数字
num = int(input("请输入一个数字: "))
factorial = 1
 
# 查看数字是负数，0 或 正数
if num < 0:
   print("抱歉，负数没有阶乘")
elif num == 0:
   print("0 的阶乘为 1")
else:
   for i in range(1,num + 1):
       factorial = factorial*i
   print("%d 的阶乘为 %d" %(num,factorial))
```
执行以上代码输出结果为：
```python 
请输入一个数字: 3
3 的阶乘为 6
```
---

### **Python 九九乘法表**
以下实例演示了如何实现九九乘法表：
```python 
# -*- coding: UTF-8 -*-
 
# Filename : test.py
 
# 九九乘法表
for i in range(1, 10):
    for j in range(1, i+1):
        print('{}x{}={}\t'.format(j, i, i*j), end='')
    print()
```

执行以上代码输出结果为：
```python 
1x1=1    
1x2=2    2x2=4    
1x3=3    2x3=6    3x3=9    
1x4=4    2x4=8    3x4=12    4x4=16    
1x5=5    2x5=10    3x5=15    4x5=20    5x5=25    
1x6=6    2x6=12    3x6=18    4x6=24    5x6=30    6x6=36    
1x7=7    2x7=14    3x7=21    4x7=28    5x7=35    6x7=42    7x7=49    
1x8=8    2x8=16    3x8=24    4x8=32    5x8=40    6x8=48    7x8=56    8x8=64    
1x9=9    2x9=18    3x9=27    4x9=36    5x9=45    6x9=54    7x9=63    8x9=72    9x9=81
```
通过指定end参数的值，可以取消在末尾输出回车符，实现不换行。

---

### **Python 斐波那契数列**
斐波那契数列指的是这样一个数列 0, 1, 1, 2, 3, 5, 8, 13,特别指出：第0项是0，第1项是第一个1。从第三项开始，每一项都等于前两项之和。  
Python 实现斐波那契数列代码如下：
```python 
# -*- coding: UTF-8 -*-
 
# Filename : test.py
 
# Python 斐波那契数列实现
 
# 获取用户输入数据
nterms = int(input("你需要几项？"))
 
# 第一和第二项
n1 = 0
n2 = 1
count = 2
 
# 判断输入的值是否合法
if nterms <= 0:
   print("请输入一个正整数。")
elif nterms == 1:
   print("斐波那契数列：")
   print(n1)
else:
   print("斐波那契数列：")
   print(n1,",",n2,end=" , ")
   while count < nterms:
       nth = n1 + n2
       print(nth,end=" , ")
       # 更新值
       n1 = n2
       n2 = nth
       count += 1
```
执行以上代码输出结果为：
```python 
你需要几项？ 10
斐波那契数列：
0 , 1 , 1 , 2 , 3 , 5 , 8 , 13 , 21 , 34 ,
```
---

### **Python 阿姆斯特朗数**
如果一个n位正整数等于其各位数字的n次方之和,则称该数为阿姆斯特朗数。 例如1^3 + 5^3 + 3^3 = 153。  
1000以内的阿姆斯特朗数： 1, 2, 3, 4, 5, 6, 7, 8, 9, 153, 370, 371, 407。  
以下代码用于检测用户输入的数字是否为阿姆斯特朗数：
```python 
# Filename : test.py
 
# Python 检测用户输入的数字是否为阿姆斯特朗数
 
# 获取用户输入的数字
num = int(input("请输入一个数字: "))
 
# 初始化变量 sum
sum = 0
# 指数
n = len(str(num))
 
# 检测
temp = num
while temp > 0:
   digit = temp % 10
   sum += digit ** n
   temp //= 10
 
# 输出结果
if num == sum:
   print(num,"是阿姆斯特朗数")
else:
   print(num,"不是阿姆斯特朗数")
```
执行以上代码输出结果为：
```python 
$ python3 test.py 
请输入一个数字: 345
345 不是阿姆斯特朗数

$ python3 test.py 
请输入一个数字: 153
153 是阿姆斯特朗数

$ python3 test.py 
请输入一个数字: 1634
1634 是阿姆斯特朗数
```
#### 获取指定期间内的阿姆斯特朗数
```python 
# Filename ：test.py
 
# 获取用户输入数字
lower = int(input("最小值: "))
upper = int(input("最大值: "))
 
for num in range(lower,upper + 1):
   # 初始化 sum
   sum = 0
   # 指数
   n = len(str(num))
 
   # 检测
   temp = num
   while temp > 0:
       digit = temp % 10
       sum += digit ** n
       temp //= 10
 
   if num == sum:
       print(num)
```
执行以上代码输出结果为：
```python 
最小值: 1
最大值: 10000
1
2
3
4
5
6
7
8
9
153
370
371
407
1634
8208
9474
```
以上实例中我们输出了 1 到 10000 之间的阿姆斯特朗数。

---

### **Python 十进制转二进制、八进制、十六进制**
以下代码用于实现十进制转二进制、八进制、十六进制：
```python 
# -*- coding: UTF-8 -*-
 
# Filename : test.py
 
# 获取用户输入十进制数
dec = int(input("输入数字："))
 
print("十进制数为：", dec)
print("转换为二进制为：", bin(dec))
print("转换为八进制为：", oct(dec))
print("转换为十六进制为：", hex(dec))
```
执行以上代码输出结果为：
```python 
python3 test.py 
输入数字：5
十进制数为：5
转换为二进制为： 0b101
转换为八进制为： 0o5
转换为十六进制为： 0x5
```


```python 
python3 test.py 
输入数字：12
十进制数为：12
转换为二进制为： 0b1100
转换为八进制为： 0o14
转换为十六进制为： 0xc
```
---

### **Python ASCII码与字符相互转换**
以下代码用于实现ASCII码与字符相互转换：
```python 
# Filename : test.py
# author by : www.runoob.com
 
# 用户输入字符
c = input("请输入一个字符: ")
 
# 用户输入ASCII码，并将输入的数字转为整型
a = int(input("请输入一个ASCII码: "))
 
 
print( c + " 的ASCII 码为", ord(c))
print( a , " 对应的字符为", chr(a))
```
执行以上代码输出结果为：

```python 
python3 test.py 
请输入一个字符: a
请输入一个ASCII码: 101
a 的ASCII 码为 97
101  对应的字符为 e
```
---

### **Python 最大公约数算法**
以下代码用于实现最大公约数算法：
```python 
# Filename : test.py
 
# 定义一个函数
def hcf(x, y):
   """该函数返回两个数的最大公约数"""
 
   # 获取最小值
   if x > y:
       smaller = y
   else:
       smaller = x
 
   for i in range(1,smaller + 1):
       if((x % i == 0) and (y % i == 0)):
           hcf = i
 
   return hcf
 
 
# 用户输入两个数字
num1 = int(input("输入第一个数字: "))
num2 = int(input("输入第二个数字: "))
 
print( num1,"和", num2,"的最大公约数为", hcf(num1, num2))
```
执行以上代码输出结果为：
```python 
输入第一个数字: 54
输入第二个数字: 24
54 和 24 的最大公约数为 6
```
---

### **Python 最小公倍数算法**
以下代码用于实现最小公倍数算法：
```python 
# Filename : test.py
 
# 定义函数
def lcm(x, y):
 
   #  获取最大的数
   if x > y:
       greater = x
   else:
       greater = y
 
   while(True):
       if((greater % x == 0) and (greater % y == 0)):
           lcm = greater
           break
       greater += 1
 
   return lcm
 
 
# 获取用户输入
num1 = int(input("输入第一个数字: "))
num2 = int(input("输入第二个数字: "))
 
print( num1,"和", num2,"的最小公倍数为", lcm(num1, num2))
```
执行以上代码输出结果为：
```python 
输入第一个数字: 54
输入第二个数字: 24
54 和 24 的最小公倍数为 216
```
---

### **Python 简单计算器实现**
以下代码用于实现简单计算器实现，包括两个数基本的加减乘除运输：
```python 
# Filename : test.py
 
# 定义函数
def add(x, y):
   """相加"""
 
   return x + y
 
def subtract(x, y):
   """相减"""
 
   return x - y
 
def multiply(x, y):
   """相乘"""
 
   return x * y
 
def divide(x, y):
   """相除"""
 
   return x / y
 
# 用户输入
print("选择运算：")
print("1、相加")
print("2、相减")
print("3、相乘")
print("4、相除")
 
choice = input("输入你的选择(1/2/3/4):")
 
num1 = int(input("输入第一个数字: "))
num2 = int(input("输入第二个数字: "))
 
if choice == '1':
   print(num1,"+",num2,"=", add(num1,num2))
 
elif choice == '2':
   print(num1,"-",num2,"=", subtract(num1,num2))
 
elif choice == '3':
   print(num1,"*",num2,"=", multiply(num1,num2))
 
elif choice == '4':
   print(num1,"/",num2,"=", divide(num1,num2))
else:
   print("非法输入")
```

执行以上代码输出结果为：
```python 
选择运算：
1、相加
2、相减
3、相乘
4、相除
输入你的选择(1/2/3/4):2
输入第一个数字: 5
输入第二个数字: 2
5 - 2 = 3
```
---

### **Python 生成日历**
以下代码用于生成指定日期的日历：
```python 
# Filename : test.py
 
# 引入日历模块
import calendar
 
# 输入指定年月
yy = int(input("输入年份: "))
mm = int(input("输入月份: "))
 
# 显示日历
print(calendar.month(yy,mm))
```
执行以上代码输出结果为：
```python 
输入年份: 2015
输入月份: 6
     June 2015
Mo Tu We Th Fr Sa Su
 1  2  3  4  5  6  7
 8  9 10 11 12 13 14
15 16 17 18 19 20 21
22 23 24 25 26 27 28
29 30
```
---

### **Python 使用递归斐波那契数列**
以下代码使用递归的方式来生成斐波那契数列：
```python 
# Filename : test.py
 
def recur_fibo(n):
   """递归函数
   输出斐波那契数列"""
   if n <= 1:
       return n
   else:
       return(recur_fibo(n-1) + recur_fibo(n-2))
 
 
# 获取用户输入
nterms = int(input("您要输出几项? "))
 
# 检查输入的数字是否正确
if nterms <= 0:
   print("输入正数")
else:
   print("斐波那契数列:")
   for i in range(nterms):
       print(recur_fibo(i))
```
执行以上代码输出结果为：

```python 
您要输出几项? 10
斐波那契数列:
0
1
1
2
3
5
8
13
21
34
```
---

### **Python 文件 IO**
以下代码演示了Python基本的文件操作，包括 open，read，write：
```python 
# Filename : test.py
 
# 写文件
with open("test.txt", "wt") as out_file:
    out_file.write("该文本会写入到文件中\n看到我了吧！")
 
# Read a file
with open("test.txt", "rt") as in_file:
    text = in_file.read()
 
print(text)
```
执行以上代码输出结果为：
```python 
该文本会写入到文件中
看到我了吧！
```

---
### **Python 字符串判断**
以下代码演示了Python字符串的判断：
```python 
# Filename : test.py

# 测试实例一
print("测试实例一")
str = "runoob.com"
print(str.isalnum()) # 判断所有字符都是数字或者字母
print(str.isalpha()) # 判断所有字符都是字母
print(str.isdigit()) # 判断所有字符都是数字
print(str.islower()) # 判断所有字符都是小写
print(str.isupper()) # 判断所有字符都是大写
print(str.istitle()) # 判断所有单词都是首字母大写，像标题
print(str.isspace()) # 判断所有字符都是空白字符、\t、\n、\r

print("------------------------")

# 测试实例二
print("测试实例二")
str = "runoob"
print(str.isalnum()) 
print(str.isalpha()) 
print(str.isdigit()) 
print(str.islower()) 
print(str.isupper()) 
print(str.istitle()) 
print(str.isspace()) 
```
执行以上代码输出结果为：
```python 
测试实例一
False
False
False
True
False
False
False
------------------------
测试实例二
True
True
False
True
False
False
```

---
### **Python 字符串大小写转换**
以下代码演示了如何将字符串转换为大写字母，或者将字符串转为小写字母等：
```python 
# Filename : test.py

str = "www.runoob.com"
print(str.upper())          # 把所有字符中的小写字母转换成大写字母
print(str.lower())          # 把所有字符中的大写字母转换成小写字母
print(str.capitalize())     # 把第一个字母转化为大写字母，其余小写
print(str.title())          # 把每个单词的第一个字母转化为大写，其余小写 
```
执行以上代码输出结果为：
```python 
WWW.RUNOOB.COM
www.runoob.com
Www.runoob.com
Www.Runoob.Com
```

---
### **Python 计算每个月天数**
以下代码通过导入 calendar 模块来计算每个月的天数：
```python 
#!/usr/bin/python3
# author by : www.runoob.com
 
import calendar
monthRange = calendar.monthrange(2016,9)
print(monthRange)
```
执行以上代码输出结果为：
```python 
(3, 30)
```
输出的是一个元组，第一个元素是所查月份的第一天对应的是星期几（0-6），第二个元素是这个月的天数。以上实例输出的意思为 2016 年 9 月份的第一天是星期四，该月总共有 30 天。

---
### **Python 获取昨天日期**
以下代码通过导入 datetime 模块来获取昨天的日期：

```python 
# Filename : test.py
 
# 引入 datetime 模块
import datetime
def getYesterday(): 
    today=datetime.date.today() 
    oneday=datetime.timedelta(days=1) 
    yesterday=today-oneday  
    return yesterday
 
# 输出
print(getYesterday())
```

执行以上代码输出结果为：
```python 
2015-06-10
```
以上实例输出的意思为昨天的日期是 2015 年 6 月 10 日。

---
### **Python list 常用操作**
### **1.list 定义**
```python 
>>> li = ["a", "b", "mpilgrim", "z", "example"]
>>> li
['a', 'b', 'mpilgrim', 'z', 'example']
>>> li[1]         
'b'
```
### **2.list 负数索引**
```python 
>>> li 
['a', 'b', 'mpilgrim', 'z', 'example']
>>> li[-1] 
'example'
>>> li[-3] 
'mpilgrim'
>>> li 
['a', 'b', 'mpilgrim', 'z', 'example']
>>> li[1:3]  
['b', 'mpilgrim'] 
>>> li[1:-1] 
['b', 'mpilgrim', 'z'] 
>>> li[0:3]  
['a', 'b', 'mpilgrim'] 
```
### **3.list 增加元素**
```python 
>>> li 
['a', 'b', 'mpilgrim', 'z', 'example']
>>> li.append("new")
>>> li 
['a', 'b', 'mpilgrim', 'z', 'example', 'new']
>>> li.insert(2, "new")
>>> li 
['a', 'b', 'new', 'mpilgrim', 'z', 'example', 'new']
>>> li.extend(["two", "elements"]) 
>>> li 
['a', 'b', 'new', 'mpilgrim', 'z', 'example', 'new', 'two', 'elements']
```

### **4.list 搜索**
```python 
>>> li 
['a', 'b', 'new', 'mpilgrim', 'z', 'example', 'new', 'two', 'elements']
>>> li.index("example")
5
>>> li.index("new")
2
>>> li.index("c")
Traceback (innermost last):
 File "<interactive input>", line 1, in ?
ValueError: list.index(x): x not in list
>>> "c" in li
False
```
### **5.list 删除元素**
```python 
>>> li 
['a', 'b', 'new', 'mpilgrim', 'z', 'example', 'new', 'two', 'elements']
>>> li.remove("z")  
>>> li 
['a', 'b', 'new', 'mpilgrim', 'example', 'new', 'two', 'elements']
>>> li.remove("new")    # 删除首次出现的一个值
>>> li 
['a', 'b', 'mpilgrim', 'example', 'new', 'two', 'elements']    # 第二个 'new' 未删除
>>> li.remove("c")     #list 中没有找到值, Python 会引发一个异常
Traceback (innermost last): 
 File "<interactive input>", line 1, in ? 
ValueError: list.remove(x): x not in list
>>> li.pop()      # pop 会做两件事: 删除 list 的最后一个元素, 然后返回删除元素的值。
'elements'
>>> li 
['a', 'b', 'mpilgrim', 'example', 'new', 'two']
```

### **6.list 运算符**
```python 
>>> li = ['a', 'b', 'mpilgrim']
>>> li = li + ['example', 'new']
>>> li 
['a', 'b', 'mpilgrim', 'example', 'new']
>>> li += ['two']         
>>> li 
['a', 'b', 'mpilgrim', 'example', 'new', 'two']
>>> li = [1, 2] * 3
>>> li 
[1, 2, 1, 2, 1, 2] 
```

### **7.使用join链接list成为字符串**
```python 
>>> params = {"server":"mpilgrim", "database":"master", "uid":"sa", "pwd":"secret"}
>>> ["%s=%s" % (k, v) for k, v in params.items()]
['server=mpilgrim', 'uid=sa', 'database=master', 'pwd=secret']
>>> ";".join(["%s=%s" % (k, v) for k, v in params.items()])
'server=mpilgrim;uid=sa;database=master;pwd=secret'
```
join 只能用于元素是字符串的 list; 它不进行任何的类型强制转换。连接一个存在一个或多个非字符串元素的 list 将引发一个异常。
### **8.list 分割字符串**
```python 
>>> li = ['server=mpilgrim', 'uid=sa', 'database=master', 'pwd=secret']
>>> s = ";".join(li)
>>> s 
'server=mpilgrim;uid=sa;database=master;pwd=secret'
>>> s.split(";")   
['server=mpilgrim', 'uid=sa', 'database=master', 'pwd=secret']
>>> s.split(";", 1) 
['server=mpilgrim', 'uid=sa;database=master;pwd=secret']
```
split 与 join 正好相反, 它将一个字符串分割成多元素 list。  
注意, 分隔符 (";") 被完全去掉了, 它没有在返回的 list 中的任意元素中出现。  
split 接受一个可选的第二个参数, 它是要分割的次数。
### **9.list 的映射解析**
```python 
>>> li = [1, 9, 8, 4] 
>>> [elem*2 for elem in li]    
[2, 18, 16, 8] 
>>> li
[1, 9, 8, 4] 
>>> li = [elem*2 for elem in li] 
>>> li 
[2, 18, 16, 8] 
```
### **10.dictionary 中的解析**
```python 
>>> params = {"server":"mpilgrim", "database":"master", "uid":"sa", "pwd":"secret"}
>>> params.keys()
dict_keys(['server', 'database', 'uid', 'pwd'])
>>> params.values()
dict_values(['mpilgrim', 'master', 'sa', 'secret'])
>>> params.items()
dict_items([('server', 'mpilgrim'), ('database', 'master'), ('uid', 'sa'), ('pwd', 'secret')])
>>> [k for k, v in params.items()]
['server', 'database', 'uid', 'pwd']
>>> [v for k, v in params.items()]
['mpilgrim', 'master', 'sa', 'secret']
>>> ["%s=%s" % (k, v) for k, v in params.items()]
['server=mpilgrim', 'database=master', 'uid=sa', 'pwd=secret']
```

### **11.list 过滤**
```python 
>>> li = ["a", "mpilgrim", "foo", "b", "c", "b", "d", "d"]
>>> [elem for elem in li if len(elem) > 1]
['mpilgrim', 'foo']
>>> [elem for elem in li if elem != "b"]
['a', 'mpilgrim', 'foo', 'c', 'd', 'd']
>>> [elem for elem in li if li.count(elem) == 1]
['a', 'mpilgrim', 'foo', 'c']
```

---
### **Python 约瑟夫生者死者小游戏**
30 个人在一条船上，超载，需要 15 人下船。  
于是人们排成一队，排队的位置即为他们的编号。  
报数，从 1 开始，数到 9 的人下船。  
如此循环，直到船上仅剩 15 人为止，问都有哪些编号的人下船了呢？
```python 
people={}
for x in range(1,31):
    people[x]=1
# print(people)
check=0
i=1
j=0
while i<=31:
    if i == 31:
        i=1
    elif j == 15:
        break
    else:
        if people[i] == 0:
            i+=1
            continue
        else:
            check+=1
            if check == 9:
                people[i]=0
                check = 0
                print("{}号下船了".format(i))
                j+=1
            else:
                i+=1
                continue
```
执行以上实例，输出结果为：

```python 
9号下船了
18号下船了
27号下船了
6号下船了
16号下船了
26号下船了
7号下船了
19号下船了
30号下船了
12号下船了
24号下船了
8号下船了
22号下船了
5号下船了
23号下船了
```

---
### **Python 实现秒表功能**
以下实例使用 time 模块来实现秒表功能：
```python 
import time
 
print('按下回车开始计时，按下 Ctrl + C 停止计时。')
while True:
    try:
        input() # 如果是 python 2.x 版本请使用 raw_input() 
        starttime = time.time()
        print('开始')
        while True:
            print('计时: ', round(time.time() - starttime, 0), '秒', end="\r")
            time.sleep(1)
    except KeyboardInterrupt:
        print('结束')
        endtime = time.time()
        print('总共的时间为:', round(endtime - starttime, 2),'secs')
        break
```
测试结果为：
```python 
按下回车开始计时，按下 Ctrl + C 停止计时。

开始
计时:  3.0 秒
计时:  5.0 秒
^C结束 6.0 秒
总共的时间为: 6.69 secs
```

---
### **Python 计算 n 个自然数的立方和**
计算公式 1^3 + 2^3 + 3^3 + 4^3 + …….+ n^3  
实现要求：  
输入 : n = 5  
输出 : 225  
公式 : 1^3 + 2^3 + 3^3 + 4^3 + 5^3 = 225    
输入 : n = 7  
输入 : 784  
公式 : 1^3 + 2^3 + 3^3 + 4^3 + 5^3 + 6^3 + 7^3 = 784  
```python 
# 定义立方和的函数
def sumOfSeries(n): 
    sum = 0
    for i in range(1, n+1): 
        sum +=i*i*i 
          
    return sum
  
   
# 调用函数
n = 5
print(sumOfSeries(n)) 
```
以上实例输出结果为：
```python 
225
```


---
### **Python 计算数组元素之和**
定义一个整型数组，并计算元素之和。  
实现要求：  
输入 : arr[] = {1, 2, 3}  
输出 : 6  
计算: 1 + 2 + 3 = 6
```python 
# 定义函数，arr 为数组，n 为数组长度，可作为备用参数，这里没有用到
def _sum(arr,n): 
      
    # 使用内置的 sum 函数计算
    return(sum(arr)) 
  
# 调用函数
arr=[] 
# 数组元素
arr = [12, 3, 4, 15] 
  
# 计算数组元素的长度
n = len(arr) 
  
ans = _sum(arr,n) 
  
# 输出结果
print ('数组元素之和为',ans) 
```
以上实例输出结果为：
```python 
数组元素之和为 34
```


---
### **Python 数组翻转指定个数的元素**
定义一个整型数组，并将指定个数的元素翻转到数组的尾部。  
例如：(arr[], d, n) 将长度为 n 的 数组 arr 的前面 d 个元素翻转到数组尾部。  
以下演示了将数组的前面两个元素放到数组后面。  
原始数组:
![](https://github.com/anmiaru/python3/raw/master/image/27-1.png)

翻转后：
![](https://github.com/anmiaru/python3/raw/master/image/27-2.png)

```python 
def leftRotate(arr, d, n): 
    for i in range(d): 
        leftRotatebyOne(arr, n) 
def leftRotatebyOne(arr, n): 
    temp = arr[0] 
    for i in range(n-1): 
        arr[i] = arr[i+1] 
    arr[n-1] = temp 
          
  
def printArray(arr,size): 
    for i in range(size): 
        print ("%d"% arr[i],end=" ") 
  

arr = [1, 2, 3, 4, 5, 6, 7] 
leftRotate(arr, 2, 7) 
printArray(arr, 7) 
```

以上实例输出结果为：
```python 
3 4 5 6 7 1 2
```

```python 
def leftRotate(arr, d, n): 
    for i in range(gcd(d,n)): 
          
        temp = arr[i] 
        j = i 
        while 1: 
            k = j + d 
            if k >= n: 
                k = k - n 
            if k == i: 
                break
            arr[j] = arr[k] 
            j = k 
        arr[j] = temp 

def printArray(arr, size): 
    for i in range(size): 
        print ("%d" % arr[i], end=" ") 

def gcd(a, b): 
    if b == 0: 
        return a; 
    else: 
        return gcd(b, a%b) 

arr = [1, 2, 3, 4, 5, 6, 7] 
leftRotate(arr, 2, 7) 
printArray(arr, 7) 
```
以上实例输出结果为：
```python 
3 4 5 6 7 1 2
```

```python 
def rverseArray(arr, start, end): 
    while (start < end): 
        temp = arr[start] 
        arr[start] = arr[end] 
        arr[end] = temp 
        start += 1
        end = end-1
  
def leftRotate(arr, d): 
    n = len(arr) 
    rverseArray(arr, 0, d-1) 
    rverseArray(arr, d, n-1) 
    rverseArray(arr, 0, n-1) 
  
def printArray(arr): 
    for i in range(0, len(arr)): 
        print (arr[i], end=' ') 
  
arr = [1, 2, 3, 4, 5, 6, 7] 
leftRotate(arr, 2) 
printArray(arr) 
```

以上实例输出结果为：
```python 
3 4 5 6 7 1 2
```


---
### **Python 将列表中的头尾两个元素对调**
定义一个列表，并将列表中的头尾两个元素对调。  
例如：
```python 
对调前 : [1, 2, 3]
对调后 : [3, 2, 1]
```


```python 
def swapList(newList): 
    size = len(newList) 
      
    temp = newList[0] 
    newList[0] = newList[size - 1] 
    newList[size - 1] = temp 
      
    return newList 

newList = [1, 2, 3] 
  
print(swapList(newList)) 
```

以上实例输出结果为：
```python 
[3, 2, 1]
```

```python 
def swapList(newList): 
      
    newList[0], newList[-1] = newList[-1], newList[0] 
  
    return newList 
      
newList = [1, 2, 3] 
print(swapList(newList)) 
```
以上实例输出结果为：
```python 
[3, 2, 1]
```

```python 
def swapList(list): 
      
    get = list[-1], list[0] 
      
    list[0], list[-1] = get 
      
    return list
      
newList = [1, 2, 3] 
print(swapList(newList)) 
```

以上实例输出结果为：
```python 
[3, 2, 1]
```


---
### **Python 将列表中的指定位置的两个元素对调**
定义一个列表，并将列表中的指定位置的两个元素对调。  
例如，对调第一个和第三个元素：
```python 
对调前 : List = [23, 65, 19, 90], pos1 = 1, pos2 = 3
对调后 : [19, 65, 23, 90]
```

```python 
def swapPositions(list, pos1, pos2): 
      
    list[pos1], list[pos2] = list[pos2], list[pos1] 
    return list
  
List = [23, 65, 19, 90] 
pos1, pos2  = 1, 3
  
print(swapPositions(List, pos1-1, pos2-1)) 
```

以上实例输出结果为：
```python 
[19, 65, 23, 90]
```

```python 
def swapPositions(list, pos1, pos2): 
      
    first_ele = list.pop(pos1)    
    second_ele = list.pop(pos2-1) 
     
    list.insert(pos1, second_ele)   
    list.insert(pos2, first_ele)   
      
    return list
  
List = [23, 65, 19, 90] 
pos1, pos2  = 1, 3
  
print(swapPositions(List, pos1-1, pos2-1)) 
```
以上实例输出结果为：
```python 
[19, 65, 23, 90]
```

```python 
def swapPositions(list, pos1, pos2): 
  
    get = list[pos1], list[pos2] 
       
    list[pos2], list[pos1] = get 
       
    return list
  
List = [23, 65, 19, 90] 
  
pos1, pos2  = 1, 3
print(swapPositions(List, pos1-1, pos2-1)) 
```

以上实例输出结果为：
```python 
[19, 65, 23, 90]
```


---
### **Python 翻转列表**
定义一个列表，并将它翻转。  
例如，对调第一个和第三个元素：
```python 
翻转前 : list = [10, 11, 12, 13, 14, 15]
翻转后 : [15, 14, 13, 12, 11, 10]
```

```python 
def Reverse(lst): 
    return [ele for ele in reversed(lst)] 
      
lst = [10, 11, 12, 13, 14, 15] 
print(Reverse(lst)) 
```

以上实例输出结果为：
```python 
[15, 14, 13, 12, 11, 10]
```

```python 
def Reverse(lst): 
    lst.reverse() 
    return lst 
      
lst = [10, 11, 12, 13, 14, 15] 
print(Reverse(lst)) 
```
以上实例输出结果为：
```python 
[15, 14, 13, 12, 11, 10]
```

```python 
def Reverse(lst): 
    new_lst = lst[::-1] 
    return new_lst 
      
lst = [10, 11, 12, 13, 14, 15] 
print(Reverse(lst)) 
```

以上实例输出结果为：
```python 
[15, 14, 13, 12, 11, 10]
```


---
### **Python 判断元素是否在列表中存在**
定义一个列表，并判断元素是否在列表中。
```python 
test_list = [ 1, 6, 3, 5, 3, 4 ] 
  
print("查看 4 是否在列表中 ( 使用循环 ) : ") 
  
for i in test_list: 
    if(i == 4) : 
        print ("存在") 
  
print("查看 4 是否在列表中 ( 使用 in 关键字 ) : ") 

if (4 in test_list): 
    print ("存在") 
```
以上实例输出结果为：
```python 
查看 4 是否在列表中 ( 使用循环 ) : 
存在
查看 4 是否在列表中 ( 使用 in 关键字 ) : 
存在
```


```python 
from bisect import bisect_left  
  
# 初始化列表
test_list_set = [ 1, 6, 3, 5, 3, 4 ] 
test_list_bisect = [ 1, 6, 3, 5, 3, 4 ] 
  
print("查看 4 是否在列表中 ( 使用 set() + in) : ") 
  
test_list_set = set(test_list_set) 
if 4 in test_list_set : 
    print ("存在") 
  
print("查看 4 是否在列表中 ( 使用 sort() + bisect_left() ) : ") 
  
test_list_bisect.sort() 
if bisect_left(test_list_bisect, 4): 
    print ("存在") 
```
以上实例输出结果为：
```python 
查看 4 是否在列表中 ( 使用 set() + in) : 
存在
查看 4 是否在列表中 ( 使用 sort() + bisect_left() ) : 
存在
```


---
### **Python 清空列表**
定义一个列表，并清空列表，可以使用 clear() 方法实现。
```python 
RUNOOB = [6, 0, 4, 1] 
print('清空前:', RUNOOB)  
  
RUNOOB.clear()
print('清空后:', RUNOOB)  
```
以上实例输出结果为：
```python 
清空前: [6, 0, 4, 1]
清空后: []
```


---
### **Python 复制列表**
定义一个列表，并将该列表元素复制到另外一个列表上。  
实例 1
```python 
def clone_runoob(li1): 
    li_copy = li1[:] 
    return li_copy 
  
li1 = [4, 8, 2, 10, 15, 18] 
li2 = clone_runoob(li1) 
print("原始列表:", li1) 
print("复制后列表:", li2) 
```
以上实例输出结果为：
```python 
原始列表: [4, 8, 2, 10, 15, 18]
复制后列表: [4, 8, 2, 10, 15, 18]
```
实例 2: 使用 extend() 方法
```python 
def clone_runoob(li1): 
    li_copy = [] 
    li_copy.extend(li1) 
    return li_copy 
  
li1 = [4, 8, 2, 10, 15, 18] 
li2 = clone_runoob(li1) 
print("原始列表:", li1) 
print("复制后列表:", li2) 
```

以上实例输出结果为：
```python 
原始列表: [4, 8, 2, 10, 15, 18]
复制后列表: [4, 8, 2, 10, 15, 18]
```
实例 3: 使用 list() 方法
```python 
def clone_runoob(li1): 
    li_copy = list(li1) 
    return li_copy 
  
li1 = [4, 8, 2, 10, 15, 18] 
li2 = clone_runoob(li1) 
print("原始列表:", li1) 
print("复制后列表:", li2) 
```
以上实例输出结果为：
```python 
原始列表: [4, 8, 2, 10, 15, 18]
复制后列表: [4, 8, 2, 10, 15, 18]
```


---
### **Python 计算元素在列表中出现的次数**
定义一个列表，并计算某个元素在列表中出现的次数。  
例如：
```python 
输入 : lst = [15, 6, 7, 10, 12, 20, 10, 28, 10]
       x = 10
输出 : 3 
```

实例 1
```python 
def countX(lst, x): 
    count = 0
    for ele in lst: 
        if (ele == x): 
            count = count + 1
    return count 
  
lst = [8, 6, 8, 10, 8, 20, 10, 8, 8] 
x = 8
print(countX(lst, x)) 
```
以上实例输出结果为：
```python 
5
```
实例 2: 使用 count() 方法
```python 
def countX(lst, x): 
    return lst.count(x) 
  
lst = [8, 6, 8, 10, 8, 20, 10, 8, 8] 
x = 8
print(countX(lst, x)) 
```

以上实例输出结果为：
```python 
5
```


---
### **Python 计算列表元素之和**
定义一个数字列表，并计算列表元素之和。  
例如： 输入 : \[12, 15, 3, 10\] 输出 : 40  
实例 1
```python 
total = 0
  
list1 = [11, 5, 17, 18, 23]  
  
for ele in range(0, len(list1)): 
    total = total + list1[ele] 
  
print("列表元素之和为: ", total) 
```
以上实例输出结果为：
```python 
列表元素之和为:  74
```
实例 2: 使用 while() 循环
```python 
total = 0
ele = 0
  
list1 = [11, 5, 17, 18, 23]  
  
while(ele < len(list1)): 
    total = total + list1[ele] 
    ele += 1
      
print("列表元素之和为: ", total) 
```

以上实例输出结果为：
```python 
列表元素之和为:  74
```
实例 3: 使用递归
```python 
list1 = [11, 5, 17, 18, 23] 

def sumOfList(list, size): 
   if (size == 0): 
     return 0
   else: 
     return list[size - 1] + sumOfList(list, size - 1) 
      
total = sumOfList(list1, len(list1)) 

print("列表元素之和为: ", total) 
```
以上实例输出结果为：
```python 
列表元素之和为:  74
```


---
### **Python 计算列表元素之积**
定义一个数字列表，并计算列表元素之积。  
例如：
```python 
输入 : list1 = [1, 2, 3] 
输出 : 6 
计算：1 * 2 * 3  
```
```python 
def multiplyList(myList) : 
      
    result = 1
    for x in myList: 
         result = result * x  
    return result  
      
list1 = [1, 2, 3]  
list2 = [3, 2, 4] 
print(multiplyList(list1)) 
print(multiplyList(list2)) 
```
以上实例输出结果为：
```python 
6
24
```

---
### **Python 查找列表中最小元素**
定义一个数字列表，并查找列表中的最小元素。  
例如：
```python 
输入 : list1 = [10, 20, 4]
输出 : 4 
```

实例 1
```python 
list1 = [10, 20, 4, 45, 99] 
  
list1.sort() 
  
print("最小元素为:", *list1[:1]) 
```
以上实例输出结果为：
```python 
最小元素为: 4
```
实例 2：使用 min() 方法
```python 
list1 = [10, 20, 1, 45, 99] 
  
print("最小元素为:", min(list1)) 
```
以上实例输出结果为：

```python 
最小元素为: 1
```

---
### **Python 查找列表中最大元素**
定义一个数字列表，并查找列表中的最大元素。  
例如：
```python 
输入 : list1 = [10, 20, 4]
输出 : 20 
```
实例 1
```python 
list1 = [10, 20, 4, 45, 99] 
  
list1.sort() 
  
print("最大元素为:", list1[-1]) 
```
以上实例输出结果为：
```python 
最大元素为: 99
```

实例 2：使用 max() 方法
```python 
list1 = [10, 20, 1, 45, 99] 
  
print("最大元素为:", max(list1)) 
```
以上实例输出结果为：
```python 
最大元素为: 99
```

---
### **Python 移除字符串中的指定位置字符**
给定一个字符串，然后移除制定位置的字符：
```python 
test_str = "Runoob"
  
# Printing original string  
print ("原始字符串为 : " + test_str) 
  
# 移除第三个字符 n
new_str = "" 
  
for i in range(0, len(test_str)): 
    if i != 2: 
        new_str = new_str + test_str[i] 

print ("字符串移除后为 : " + new_str) 
```
执行以上代码，输出结果为：

```python 
原始字符串为 : Runoob
字符串移除后为 : Ruoob
```

---
### **Python 判断字符串是否存在子字符串**
给定一个字符串，然后判断指定的子字符串是否存在于改字符串中。
```python 
def check(string, sub_str): 
    if (string.find(sub_str) == -1): 
        print("不存在！") 
    else: 
        print("存在！") 
 
string = "www.runoob.com"
sub_str ="runoob"
check(string, sub_str)
```
执行以上代码输出结果为：
```python 
存在！
```

---
### **Python 判断字符串长度**
给定一个字符串，然后判断改字符串的长度。  
实例 1：使用内置方法 len()
```python 
str = "runoob"
print(len(str))
```

执行以上代码输出结果为：
```python 
6
```
实例 2：使用循环计算
```python 
def findLen(str): 
    counter = 0
    while str[counter:]: 
        counter += 1
    return counter 
  
str = "runoob"
print(findLen(str))
```
执行以上代码输出结果为：
```python 
6
```

---
### **Python 使用正则表达式提取字符串中的 URL**
给定一个字符串，里面包含 URL 地址，需要我们使用正则表达式来获取字符串的 URL。
```python 
import re 
  
def Find(string): 
    # findall() 查找匹配正则表达式的字符串
    url = re.findall('https?://(?:[-\w.]|(?:%[\da-fA-F]{2}))+', string)
    return url 
      
 
string = 'Runoob 的网页地址为：https://www.runoob.com，Google 的网页地址为：https://www.google.com'
print("Urls: ", Find(string))
```
执行以上代码输出结果为：
```python 
Urls:  ['https://www.runoob.com', 'https://www.google.com']
```

---
### **Python 将字符串作为代码执行**
给定一个字符串代码，然后使用 exec() 来执行字符串代码。  
实例 1：使用内置方法 len()
```python 
def exec_code(): 
    LOC = """ 
def factorial(num): 
    fact=1 
    for i in range(1,num+1): 
        fact = fact*i 
    return fact 
print(factorial(5)) 
"""
    exec(LOC) 
 
exec_code()
```
执行以上代码输出结果为：
```python 
120
```

---
### **Python 字符串翻转**
给定一个字符串，然后将其翻转，逆序输出。
实例 1：使用字符串切片
```python 
str='Runoob'
print(str[::-1])
```
执行以上代码输出结果为：
```python 
boonuR
```
实例 2：使用 reversed()
```python 
str='Runoob'
print(''.join(reversed(str)))
```

执行以上代码输出结果为：
```python 
boonuR
```

---
### **Python 对字符串切片及翻转**
给定一个字符串，从头部或尾部截取指定数量的字符串，然后将其翻转拼接。
```python 
def rotate(input,d): 
  
    Lfirst = input[0 : d] 
    Lsecond = input[d :] 
    Rfirst = input[0 : len(input)-d] 
    Rsecond = input[len(input)-d : ] 
  
    print( "头部切片翻转 : ", (Lsecond + Lfirst) )
    print( "尾部切片翻转 : ", (Rsecond + Rfirst) )
 
if __name__ == "__main__": 
    input = 'Runoob'
    d=2  # 截取两个字符
    rotate(input,d)
```
执行以上代码输出结果为：
```python 
头部切片翻转 :  noobRu
尾部切片翻转 :  obRuno
```

---
### **Python 按键(key)或值(value)对字典进行排序**
给定一个字典，然后按键(key)或值(value)对字典进行排序。
实例1：按键(key)排序
```python 
def dictionairy():  
  
    # 声明字典
    key_value ={}     
 
    # 初始化
    key_value[2] = 56       
    key_value[1] = 2 
    key_value[5] = 12 
    key_value[4] = 24
    key_value[6] = 18      
    key_value[3] = 323 
 
    print ("按键(key)排序:")   
 
    # sorted(key_value) 返回一个迭代器
    # 字典按键排序
    for i in sorted (key_value) : 
        print ((i, key_value[i]), end =" ") 
  
def main(): 
    # 调用函数
    dictionairy()              
      
# 主函数
if __name__=="__main__":      
    main()
```

执行以上代码输出结果为：
```python 
按键(key)排序:
(1, 2) (2, 56) (3, 323) (4, 24) (5, 12) (6, 18) 
```
实例2：按值(value)排序
```python 
def dictionairy():  
 
    # 声明字典
    key_value ={}     
 
    # 初始化
    key_value[2] = 56       
    key_value[1] = 2 
    key_value[5] = 12 
    key_value[4] = 24
    key_value[6] = 18      
    key_value[3] = 323 
 
 
    print ("按值(value)排序:")   
    print(sorted(key_value.items(), key = lambda kv:(kv[1], kv[0])))     
   
def main(): 
    dictionairy()             
      
if __name__=="__main__":       
    main()
```
执行以上代码输出结果为：
```python 
按值(value)排序:
[(1, 2), (5, 12), (6, 18), (4, 24), (2, 56), (3, 323)]
```

实例 3 : 字典列表排序
```python 
lis = [{ "name" : "Taobao", "age" : 100},  
{ "name" : "Runoob", "age" : 7 }, 
{ "name" : "Google", "age" : 100 }, 
{ "name" : "Wiki" , "age" : 200 }] 
  
# 通过 age 升序排序
print ("列表通过 age 升序排序: ")
print (sorted(lis, key = lambda i: i['age']) )
  
print ("\r") 
  
# 先按 age 排序，再按 name 排序
print ("列表通过 age 和 name 排序: ")
print (sorted(lis, key = lambda i: (i['age'], i['name'])) )
  
print ("\r") 
  
# 按 age 降序排序
print ("列表通过 age 降序排序: ")
print (sorted(lis, key = lambda i: i['age'],reverse=True) )
```
执行以上代码输出结果为：
```python 
列表通过 age 升序排序: 
[{'name': 'Runoob', 'age': 7}, {'name': 'Taobao', 'age': 100}, {'name': 'Google', 'age': 100}, {'name': 'Wiki', 'age': 200}]

列表通过 age 和 name 排序: 
[{'name': 'Runoob', 'age': 7}, {'name': 'Google', 'age': 100}, {'name': 'Taobao', 'age': 100}, {'name': 'Wiki', 'age': 200}]

列表通过 age 降序排序: 
[{'name': 'Wiki', 'age': 200}, {'name': 'Taobao', 'age': 100}, {'name': 'Google', 'age': 100}, {'name': 'Runoob', 'age': 7}]
```

---
### **Python 计算字典值之和**
给定一个字典，然后计算它们所有数字值的和。
```python 
def returnSum(myDict): 
      
    sum = 0
    for i in myDict: 
        sum = sum + myDict[i] 
      
    return sum
  
dict = {'a': 100, 'b':200, 'c':300} 
print("Sum :", returnSum(dict))
```
执行以上代码输出结果为：
```python 
Sum : 600
```

---
### **Python 移除字典点键值(key/value)对**
给定一个字典，然后计算它们所有数字值的和。  
实例 1 : 使用 del 移除
```python 
test_dict = {"Runoob" : 1, "Google" : 2, "Taobao" : 3, "Zhihu" : 4} 
  
# 输出原始的字典
print ("字典移除前 : " + str(test_dict)) 
  
# 使用 del 移除 Zhihu
del test_dict['Zhihu'] 
  
# 输出移除后的字典
print ("字典移除后 : " + str(test_dict)) 
  
# 移除没有的 key 会报错
#del test_dict['Baidu']
```
执行以上代码输出结果为：
```python 
字典移除前 : {'Runoob': 1, 'Google': 2, 'Taobao': 3, 'Zhihu': 4}
字典移除后 : {'Runoob': 1, 'Google': 2, 'Taobao': 3}
```
实例 2 : 使用 pop() 移除
```python 
test_dict = {"Runoob" : 1, "Google" : 2, "Taobao" : 3, "Zhihu" : 4} 
  
# 输出原始的字典
print ("字典移除前 : " + str(test_dict)) 
  
# 使用 pop 移除 Zhihu
removed_value = test_dict.pop('Zhihu') 
  
# 输出移除后的字典
print ("字典移除后 : " + str(test_dict)) 
  
print ("移除的 key 对应的 value 为 : " + str(removed_value)) 
  
print ('\r') 
  
# 使用 pop() 移除没有的 key 不会发生异常，我们可以自定义提示信息
removed_value = test_dict.pop('Baidu', '没有该键(key)') 
  
# 输出移除后的字典
print ("字典移除后 : " + str(test_dict)) 
print ("移除的值为 : " + str(removed_value))
```

执行以上代码输出结果为：
```python 
字典移除前 : {'Runoob': 1, 'Google': 2, 'Taobao': 3, 'Zhihu': 4}
字典移除后 : {'Runoob': 1, 'Google': 2, 'Taobao': 3}
移除的 key 对应的 value 为 : 4

字典移除后 : {'Runoob': 1, 'Google': 2, 'Taobao': 3}
移除的值为 : 没有该键(key)
```
实例 3 : 使用 items() 移除
```python 
test_dict = {"Runoob" : 1, "Google" : 2, "Taobao" : 3, "Zhihu" : 4} 
  
# 输出原始的字典
print ("字典移除前 : " + str(test_dict)) 
  
# 使用 pop 移除 Zhihu
new_dict = {key:val for key, val in test_dict.items() if key != 'Zhihu'} 
  
  
# 输出移除后的字典
print ("字典移除后 : " + str(new_dict))
```
执行以上代码输出结果为：
```python 
字典移除前 : {'Runoob': 1, 'Google': 2, 'Taobao': 3, 'Zhihu': 4}
字典移除后 : {'Runoob': 1, 'Google': 2, 'Taobao': 3}
```

---
### **Python 合并字典**
给定一个字典，然后计算它们所有数字值的和。
实例 1 : 使用 update() 方法，第二个参数合并第一个参数
```python 
def Merge(dict1, dict2): 
    return(dict2.update(dict1)) 
      
# 两个字典
dict1 = {'a': 10, 'b': 8} 
dict2 = {'d': 6, 'c': 4} 
  
# 返回  None 
print(Merge(dict1, dict2)) 
  
# dict2 合并了 dict1
print(dict2)
```

执行以上代码输出结果为：
```python 
None
{'d': 6, 'c': 4, 'a': 10, 'b': 8}
```
实例 2 : 使用 **，函数将参数以字典的形式导入
```python 
def Merge(dict1, dict2): 
    res = {**dict1, **dict2} 
    return res 
      
# 两个字典
dict1 = {'a': 10, 'b': 8} 
dict2 = {'d': 6, 'c': 4} 
dict3 = Merge(dict1, dict2) 
print(dict3)
```
执行以上代码输出结果为：
```python 
{'a': 10, 'b': 8, 'd': 6, 'c': 4}
```

---
### **Python 将字符串的时间转换为时间戳**
给定一个字符串的时间，将其转换为时间戳。
```python 
import time
 
a1 = "2019-5-10 23:40:00"
# 先转换为时间数组
timeArray = time.strptime(a1, "%Y-%m-%d %H:%M:%S")
 
# 转换为时间戳
timeStamp = int(time.mktime(timeArray))
print(timeStamp)
 
 
# 格式转换 - 转为 /
a2 = "2019/5/10 23:40:00"
# 先转换为时间数组,然后转换为其他格式
timeArray = time.strptime(a2, "%Y-%m-%d %H:%M:%S")
otherStyleTime = time.strftime("%Y/%m/%d %H:%M:%S", timeArray)
print(otherStyleTime)
```
执行以上代码输出结果为：
```python 
1557502800
```

---
### **Python 获取几天前的时间**
计算几天前并转换为指定格式。
```python 
import time
import datetime
 
# 先获得时间数组格式的日期
threeDayAgo = (datetime.datetime.now() - datetime.timedelta(days = 3))
# 转换为时间戳
timeStamp = int(time.mktime(threeDayAgo.timetuple()))
# 转换为其他字符串格式
otherStyleTime = threeDayAgo.strftime("%Y-%m-%d %H:%M:%S")
print(otherStyleTime)
```
执行以上代码输出结果为：
```python 
2019-05-18 18:06:08
```


```python 
import time
import datetime
 
#给定时间戳
timeStamp = 1557502800
dateArray = datetime.datetime.utcfromtimestamp(timeStamp)
threeDayAgo = dateArray - datetime.timedelta(days = 3)
print(threeDayAgo)
```
执行以上代码输出结果为：
```python 
2019-05-07 15:40:00
```

---
### **Python 将时间戳转换为指定格式日期**
给定一个时间戳，将其转换为指定格式的时间。  
**注意时区的设置。**
#### **当前时间**
```python 
import time
 
# 获得当前时间时间戳
now = int(time.time())
#转换为其他日期格式,如:"%Y-%m-%d %H:%M:%S"
timeArray = time.localtime(now)
otherStyleTime = time.strftime("%Y-%m-%d %H:%M:%S", timeArray)
print(otherStyleTime)
```

执行以上代码输出结果为：
```python 
2019-05-21 18:02:49
```

```python 
import datetime
 
# 获得当前时间
now = datetime.datetime.now()
# 转换为指定的格式
otherStyleTime = now.strftime("%Y-%m-%d %H:%M:%S")
print(otherStyleTime)
```
执行以上代码输出结果为：
```python 
2019-05-21 18:03:48
```
#### **指定时间戳**
```python 
import time
 
timeStamp = 1557502800
timeArray = time.localtime(timeStamp)
otherStyleTime = time.strftime("%Y-%m-%d %H:%M:%S", timeArray)
print(otherStyleTime)
```

执行以上代码输出结果为：
```python 
2019-05-10 23:40:00
```

```python 
import datetime
 
timeStamp = 1557502800
dateArray = datetime.datetime.utcfromtimestamp(timeStamp)
otherStyleTime = dateArray.strftime("%Y-%m-%d %H:%M:%S")
print(otherStyleTime)
```
执行以上代码输出结果为：
```python 
2019-05-10 23:40:00
```

---
### **Python 打印自己设计的字体**
通过对 26 个字母的设定，设置自己要输出的字体。
```python 
name = "RUNOOB"
  
# 接收用户输入
# name = input("输入你的名字: \n\n") 
  
lngth = len(name) 
l = "" 
  
for x in range(0, lngth): 
    c = name[x] 
    c = c.upper() 
      
    if (c == "A"): 
        print("..######..\n..#....#..\n..######..", end = " ") 
        print("\n..#....#..\n..#....#..\n\n") 
          
    elif (c == "B"): 
        print("..######..\n..#....#..\n..#####...", end = " ") 
        print("\n..#....#..\n..######..\n\n") 
          
    elif (c == "C"): 
        print("..######..\n..#.......\n..#.......", end = " ") 
        print("\n..#.......\n..######..\n\n") 
          
    elif (c == "D"): 
        print("..#####...\n..#....#..\n..#....#..", end = " ") 
        print("\n..#....#..\n..#####...\n\n") 
          
    elif (c == "E"): 
        print("..######..\n..#.......\n..#####...", end = " ") 
        print("\n..#.......\n..######..\n\n") 
          
    elif (c == "F"): 
        print("..######..\n..#.......\n..#####...", end = " ") 
        print("\n..#.......\n..#.......\n\n") 
          
    elif (c == "G"): 
        print("..######..\n..#.......\n..#.####..", end = " ") 
        print("\n..#....#..\n..#####...\n\n") 
          
    elif (c == "H"): 
        print("..#....#..\n..#....#..\n..######..", end = " ") 
        print("\n..#....#..\n..#....#..\n\n") 
          
    elif (c == "I"): 
        print("..######..\n....##....\n....##....", end = " ") 
        print("\n....##....\n..######..\n\n") 
          
    elif (c == "J"): 
        print("..######..\n....##....\n....##....", end = " ") 
        print("\n..#.##....\n..####....\n\n") 
          
    elif (c == "K"): 
        print("..#...#...\n..#..#....\n..##......", end = " ") 
        print("\n..#..#....\n..#...#...\n\n") 
          
    elif (c == "L"): 
        print("..#.......\n..#.......\n..#.......", end = " ") 
        print("\n..#.......\n..######..\n\n") 
          
    elif (c == "M"): 
        print("..#....#..\n..##..##..\n..#.##.#..", end = " ") 
        print("\n..#....#..\n..#....#..\n\n") 
          
    elif (c == "N"): 
        print("..#....#..\n..##...#..\n..#.#..#..", end = " ") 
        print("\n..#..#.#..\n..#...##..\n\n") 
          
    elif (c == "O"): 
        print("..######..\n..#....#..\n..#....#..", end = " ") 
        print("\n..#....#..\n..######..\n\n") 
          
    elif (c == "P"): 
        print("..######..\n..#....#..\n..######..", end = " ") 
        print("\n..#.......\n..#.......\n\n") 
          
    elif (c == "Q"): 
        print("..######..\n..#....#..\n..#.#..#..", end = " ") 
        print("\n..#..#.#..\n..######..\n\n") 
          
    elif (c == "R"): 
        print("..######..\n..#....#..\n..#.##...", end = " ") 
        print("\n..#...#...\n..#....#..\n\n") 
          
    elif (c == "S"): 
        print("..######..\n..#.......\n..######..", end = " ") 
        print("\n.......#..\n..######..\n\n") 
          
    elif (c == "T"): 
        print("..######..\n....##....\n....##....", end = " ") 
        print("\n....##....\n....##....\n\n") 
          
    elif (c == "U"): 
        print("..#....#..\n..#....#..\n..#....#..", end = " ") 
        print("\n..#....#..\n..######..\n\n") 
          
    elif (c == "V"): 
        print("..#....#..\n..#....#..\n..#....#..", end = " ") 
        print("\n...#..#...\n....##....\n\n") 
          
    elif (c == "W"): 
        print("..#....#..\n..#....#..\n..#.##.#..", end = " ") 
        print("\n..##..##..\n..#....#..\n\n") 
          
    elif (c == "X"): 
        print("..#....#..\n...#..#...\n....##....", end = " ") 
        print("\n...#..#...\n..#....#..\n\n") 
          
    elif (c == "Y"): 
        print("..#....#..\n...#..#...\n....##....", end = " ") 
        print("\n....##....\n....##....\n\n") 
          
    elif (c == "Z"): 
        print("..######..\n......#...\n.....#....", end = " ") 
        print("\n....#.....\n..######..\n\n") 
          
    elif (c == " "): 
        print("..........\n..........\n..........", end = " ") 
        print("\n..........\n\n") 
          
    elif (c == "."): 
        print("----..----\n\n")
```
执行以上代码输出结果为：
```python 
..######..
..#....#..
..#.##... 
..#...#...
..#....#..


..#....#..
..#....#..
..#....#.. 
..#....#..
..######..


..#....#..
..##...#..
..#.#..#.. 
..#..#.#..
..#...##..


..######..
..#....#..
..#....#.. 
..#....#..
..######..


..######..
..#....#..
..#....#.. 
..#....#..
..######..


..######..
..#....#..
..#####... 
..#....#..
..######..
```

---
### **Python 二分查找**
二分搜索是一种在有序数组中查找某一特定元素的搜索算法。搜索过程从数组的中间元素开始，如果中间元素正好是要查找的元素，则搜索过程结束；如果某一特定元素大于或者小于中间元素，则在数组大于或小于中间元素的那一半中查找，而且跟开始一样从中间元素开始比较。如果在某一步骤数组为空，则代表找不到。这种搜索算法每一次比较都使搜索范围缩小一半。

![](https://github.com/anmiaru/python3/raw/master/image/27-3.png)

```python 
# 返回 x 在 arr 中的索引，如果不存在返回 -1
def binarySearch (arr, l, r, x): 
  
    # 基本判断
    if r >= l: 
  
        mid = int(l + (r - l)/2)
  
        # 元素整好的中间位置
        if arr[mid] == x: 
            return mid 
          
        # 元素小于中间位置的元素，只需要再比较左边的元素
        elif arr[mid] > x: 
            return binarySearch(arr, l, mid-1, x) 
  
        # 元素大于中间位置的元素，只需要再比较右边的元素
        else: 
            return binarySearch(arr, mid+1, r, x) 
  
    else: 
        # 不存在
        return -1
  
# 测试数组
arr = [ 2, 3, 4, 10, 40 ] 
x = 10
  
# 函数调用
result = binarySearch(arr, 0, len(arr)-1, x) 
  
if result != -1: 
    print ("元素在数组中的索引为 %d" % result )
else: 
    print ("元素不在数组中")
```
执行以上代码输出结果为：
```python 
元素在数组中的索引为 3
```

---
### **Python 线性查找**
线性查找指按一定的顺序检查数组中每一个元素，直到找到所要寻找的特定值为止。

![](https://github.com/anmiaru/python3/raw/master/image/27-4.png)


```python 
def search(arr, n, x): 
  
    for i in range (0, n): 
        if (arr[i] == x): 
            return i; 
    return -1; 
  
# 在数组 arr 中查找字符 D
arr = [ 'A', 'B', 'C', 'D', 'E' ]; 
x = 'D'; 
n = len(arr); 
result = search(arr, n, x) 
if(result == -1): 
    print("元素不在数组中") 
else: 
    print("元素在数组中的索引为", result);
```
执行以上代码输出结果为：
```python 
元素在数组中的索引为 3
```

---
### **Python 插入排序**
插入排序（英语：Insertion Sort）是一种简单直观的排序算法。它的工作原理是通过构建有序序列，对于未排序数据，在已排序序列中从后向前扫描，找到相应位置并插入。

![](https://github.com/anmiaru/python3/raw/master/image/27-5.gif)


```python 
def insertionSort(arr): 
  
    for i in range(1, len(arr)): 
  
        key = arr[i] 
  
        j = i-1
        while j >=0 and key < arr[j] : 
                arr[j+1] = arr[j] 
                j -= 1
        arr[j+1] = key 
  
  
arr = [12, 11, 13, 5, 6] 
insertionSort(arr) 
print ("排序后的数组:") 
for i in range(len(arr)): 
    print ("%d" %arr[i])
```

执行以上代码输出结果为：
```python 
排序后的数组:
5
6
11
12
13
```

---
### **Python 快速排序**
快速排序使用分治法（Divide and conquer）策略来把一个序列（list）分为较小和较大的2个子序列，然后递归地排序两个子序列。  
步骤为：  
* 挑选基准值：从数列中挑出一个元素，称为"基准"（pivot）;
* 分割：重新排序数列，所有比基准值小的元素摆放在基准前面，所有比基准值大的元素摆在基准后面（与基准值相等的数可以到任何一边）。在这个分割结束之后，对基准值的排序就已经完成;
* 递归排序子序列：递归地将小于基准值元素的子序列和大于基准值元素的子序列排序。
递归到最底部的判断条件是数列的大小是零或一，此时该数列显然已经有序。

选取基准值有数种具体方法，此选取方法对排序的时间性能有决定性影响。

![](https://github.com/anmiaru/python3/raw/master/image/27-6.gif)

```python 
def partition(arr,low,high): 
    i = ( low-1 )         # 最小元素索引
    pivot = arr[high]     
  
    for j in range(low , high): 
  
        # 当前元素小于或等于 pivot 
        if   arr[j] <= pivot: 
          
            i = i+1 
            arr[i],arr[j] = arr[j],arr[i] 
  
    arr[i+1],arr[high] = arr[high],arr[i+1] 
    return ( i+1 ) 
  
 
# arr[] --> 排序数组
# low  --> 起始索引
# high  --> 结束索引
  
# 快速排序函数
def quickSort(arr,low,high): 
    if low < high: 
  
        pi = partition(arr,low,high) 
  
        quickSort(arr, low, pi-1) 
        quickSort(arr, pi+1, high) 
  
arr = [10, 7, 8, 9, 1, 5] 
n = len(arr) 
quickSort(arr,0,n-1) 
print ("排序后的数组:") 
for i in range(n): 
    print ("%d" %arr[i]),
```
执行以上代码输出结果为：
```python 
排序后的数组:
1
5
7
8
9
10
```

---
### **Python 选择排序**
选择排序（Selection sort）是一种简单直观的排序算法。它的工作原理如下。首先在未排序序列中找到最小（大）元素，存放到排序序列的起始位置，然后，再从剩余未排序元素中继续寻找最小（大）元素，然后放到已排序序列的末尾。以此类推，直到所有元素均排序完毕。

![](https://github.com/anmiaru/python3/raw/master/image/27-7.gif)

```python 
import sys 
A = [64, 25, 12, 22, 11] 
  
for i in range(len(A)): 
      
   
    min_idx = i 
    for j in range(i+1, len(A)): 
        if A[min_idx] > A[j]: 
            min_idx = j 
                
    A[i], A[min_idx] = A[min_idx], A[i] 
  
print ("排序后的数组：") 
for i in range(len(A)): 
    print("%d" %A[i]),
```

执行以上代码输出结果为：
```python 
排序后的数组：
11
12
22
25
64
```

---
### **Python 冒泡排序**
冒泡排序（Bubble Sort）也是一种简单直观的排序算法。它重复地走访过要排序的数列，一次比较两个元素，如果他们的顺序错误就把他们交换过来。走访数列的工作是重复地进行直到没有再需要交换，也就是说该数列已经排序完成。这个算法的名字由来是因为越小的元素会经由交换慢慢"浮"到数列的顶端。

![](https://github.com/anmiaru/python3/raw/master/image/27-8.gif)

```python 
def bubbleSort(arr):
    n = len(arr)
 
    # 遍历所有数组元素
    for i in range(n):
 
        # Last i elements are already in place
        for j in range(0, n-i-1):
 
            if arr[j] > arr[j+1] :
                arr[j], arr[j+1] = arr[j+1], arr[j]
 
arr = [64, 34, 25, 12, 22, 11, 90]
 
bubbleSort(arr)
 
print ("排序后的数组:")
for i in range(len(arr)):
    print ("%d" %arr[i]),
```
执行以上代码输出结果为：
```python 
排序后的数组:
11
12
22
25
34
64
90
```

---
### **Python 归并排序**
归并排序（英语：Merge sort，或mergesort），是创建在归并操作上的一种有效的排序算法。该算法是采用分治法（Divide and Conquer）的一个非常典型的应用。

分治法:
* 分割：递归地把当前序列平均分割成两半。
* 集成：在保持元素顺序的同时将上一步得到的子序列集成到一起（归并）。

![](https://github.com/anmiaru/python3/raw/master/image/27-9.gif)

```python 
def merge(arr, l, m, r): 
    n1 = m - l + 1
    n2 = r- m 
  
    # 创建临时数组
    L = [0] * (n1)
    R = [0] * (n2)
  
    # 拷贝数据到临时数组 arrays L[] 和 R[] 
    for i in range(0 , n1): 
        L[i] = arr[l + i] 
  
    for j in range(0 , n2): 
        R[j] = arr[m + 1 + j] 
  
    # 归并临时数组到 arr[l..r] 
    i = 0     # 初始化第一个子数组的索引
    j = 0     # 初始化第二个子数组的索引
    k = l     # 初始归并子数组的索引
  
    while i < n1 and j < n2 : 
        if L[i] <= R[j]: 
            arr[k] = L[i] 
            i += 1
        else: 
            arr[k] = R[j] 
            j += 1
        k += 1
  
    # 拷贝 L[] 的保留元素
    while i < n1: 
        arr[k] = L[i] 
        i += 1
        k += 1
  
    # 拷贝 R[] 的保留元素
    while j < n2: 
        arr[k] = R[j] 
        j += 1
        k += 1
  
def mergeSort(arr,l,r): 
    if l < r: 
  
        
        m = int((l+(r-1))/2)
  
       
        mergeSort(arr, l, m) 
        mergeSort(arr, m+1, r) 
        merge(arr, l, m, r) 
  
  
arr = [12, 11, 13, 5, 6, 7] 
n = len(arr) 
print ("给定的数组") 
for i in range(n): 
    print ("%d" %arr[i]), 
  
mergeSort(arr,0,n-1) 
print ("\n\n排序后的数组") 
for i in range(n): 
    print ("%d" %arr[i]),
```
执行以上代码输出结果为：
```python 
给定的数组
12
11
13
5
6
7


排序后的数组
5
6
7
11
12
13
```

---
### **Python 堆排序**
堆排序（Heapsort）是指利用堆这种数据结构所设计的一种排序算法。堆积是一个近似完全二叉树的结构，并同时满足堆积的性质：即子结点的键值或索引总是小于（或者大于）它的父节点。堆排序可以说是一种利用堆的概念来排序的选择排序。

![](https://github.com/anmiaru/python3/raw/master/image/27-10.gif)

```python 
def heapify(arr, n, i): 
    largest = i  
    l = 2 * i + 1     # left = 2*i + 1 
    r = 2 * i + 2     # right = 2*i + 2 
  
    if l < n and arr[i] < arr[l]: 
        largest = l 
  
    if r < n and arr[largest] < arr[r]: 
        largest = r 
  
    if largest != i: 
        arr[i],arr[largest] = arr[largest],arr[i]  # 交换
  
        heapify(arr, n, largest) 
  
def heapSort(arr): 
    n = len(arr) 
  
    # Build a maxheap. 
    for i in range(n, -1, -1): 
        heapify(arr, n, i) 
  
    # 一个个交换元素
    for i in range(n-1, 0, -1): 
        arr[i], arr[0] = arr[0], arr[i]   # 交换
        heapify(arr, i, 0) 
  
arr = [ 12, 11, 13, 5, 6, 7] 
heapSort(arr) 
n = len(arr) 
print ("排序后") 
for i in range(n): 
    print ("%d" %arr[i]),
```
执行以上代码输出结果为：
```python 
排序后
5
6
7
11
12
13
```

---
### **Python 计数排序**
计数排序的核心在于将输入的数据值转化为键存储在额外开辟的数组空间中。作为一种线性时间复杂度的排序，计数排序要求输入的数据必须是有确定范围的整数。

![](https://github.com/anmiaru/python3/raw/master/image/27-11.gif)

```python 
def countSort(arr): 
  
    output = [0 for i in range(256)] 
  
    count = [0 for i in range(256)] 
  
    ans = ["" for _ in arr] 
  
    for i in arr: 
        count[ord(i)] += 1
  
    for i in range(256): 
        count[i] += count[i-1] 
  
    for i in range(len(arr)): 
        output[count[ord(arr[i])]-1] = arr[i] 
        count[ord(arr[i])] -= 1
  
    for i in range(len(arr)): 
        ans[i] = output[i] 
    return ans  
  
arr = "wwwrunoobcom"
ans = countSort(arr) 
print ( "字符数组排序 %s"  %("".join(ans)) )
```
执行以上代码输出结果为：
```python 
符数组排序 bcmnoooruwww
```

---
### **Python 希尔排序**
希尔排序，也称递减增量排序算法，是插入排序的一种更高效的改进版本。但希尔排序是非稳定排序算法。  
希尔排序的基本思想是：先将整个待排序的记录序列分割成为若干子序列分别进行直接插入排序，待整个序列中的记录"基本有序"时，再对全体记录进行依次直接插入排序。

![](https://github.com/anmiaru/python3/raw/master/image/27-12.gif)

```python 
def shellSort(arr): 
  
    n = len(arr)
    gap = int(n/2)
  
    while gap > 0: 
  
        for i in range(gap,n): 
  
            temp = arr[i] 
            j = i 
            while  j >= gap and arr[j-gap] >temp: 
                arr[j] = arr[j-gap] 
                j -= gap 
            arr[j] = temp 
        gap = int(gap/2)
  
arr = [ 12, 34, 54, 2, 3] 
  
n = len(arr) 
print ("排序前:") 
for i in range(n): 
    print(arr[i]), 
  
shellSort(arr) 
  
print ("\n排序后:") 
for i in range(n): 
    print(arr[i]),
```

执行以上代码输出结果为：
```python 
排序前:
12
34
54
2
3

排序后:
2
3
12
34
54
```

---
### **Python 拓扑排序**
对一个有向无环图(Directed Acyclic Graph简称DAG)G进行拓扑排序，是将G中所有顶点排成一个线性序列，使得图中任意一对顶点u和v，若边(u,v)∈E(G)，则u在线性序列中出现在v之前。通常，这样的线性序列称为满足拓扑次序(Topological Order)的序列，简称拓扑序列。简单的说，由某个集合上的一个偏序得到该集合上的一个全序，这个操作称之为拓扑排序。  
在图论中，由一个有向无环图的顶点组成的序列，当且仅当满足下列条件时，称为该图的一个拓扑排序（英语：Topological sorting）：  
* 每个顶点出现且只出现一次；
* 若A在序列中排在B的前面，则在图中不存在从B到A的路径。

![](https://github.com/anmiaru/python3/raw/master/image/27-13.png)

```python 
from collections import defaultdict 
 
class Graph: 
    def __init__(self,vertices): 
        self.graph = defaultdict(list) 
        self.V = vertices
  
    def addEdge(self,u,v): 
        self.graph[u].append(v) 
  
    def topologicalSortUtil(self,v,visited,stack): 
  
        visited[v] = True
  
        for i in self.graph[v]: 
            if visited[i] == False: 
                self.topologicalSortUtil(i,visited,stack) 
  
        stack.insert(0,v) 
  
    def topologicalSort(self): 
        visited = [False]*self.V 
        stack =[] 
  
        for i in range(self.V): 
            if visited[i] == False: 
                self.topologicalSortUtil(i,visited,stack) 
  
        print (stack) 
  
g= Graph(6) 
g.addEdge(5, 2); 
g.addEdge(5, 0); 
g.addEdge(4, 0); 
g.addEdge(4, 1); 
g.addEdge(2, 3); 
g.addEdge(3, 1); 
  
print ("拓扑排序结果：")
g.topologicalSort()
```
执行以上代码输出结果为：
```python 
拓扑排序结果：
[5, 4, 2, 3, 1, 0]
```
