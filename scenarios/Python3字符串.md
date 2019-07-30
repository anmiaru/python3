## **Python3字符串**
字符串是 Python 中最常用的数据类型。我们可以使用引号( ' 或 " )来创建字符串。  
创建字符串很简单，只要为变量分配一个值即可。例如：
```python
var1 = 'Hello World!'
var2 = "Runoob"
```
---


### **Python 访问字符串中的值**
Python 不支持单字符类型，单字符在 Python 中也是作为一个字符串使用。  
Python 访问子字符串，可以使用方括号来截取字符串，如下实例：
```python
#!/usr/bin/python3
 
var1 = 'Hello World!'
var2 = "Runoob"
 
print ("var1[0]: ", var1[0])
print ("var2[1:5]: ", var2[1:5])
```
以上实例执行结果：
```python
var1[0]:  H
var2[1:5]:  unoo
```
---

### **Python 字符串更新**
你可以截取字符串的一部分并与其他字段拼接，如下实例：
```python
#!/usr/bin/python3
 
var1 = 'Hello World!'
 
print ("已更新字符串 : ", var1[:6] + 'Runoob!')
```
以上实例执行结果：
```python
已更新字符串 :  Hello Runoob!
```
---

### **Python 转义字符**
在需要在字符中使用特殊字符时，python用反斜杠(\)转义字符。如下表：
![](/image/9-1.png)

---


### **Python字符串运算符**
下表实例变量a值为字符串 "Hello"，b变量值为 "Python"：
![](/image/9-2.png)

```python
#!/usr/bin/python3
 
a = "Hello"
b = "Python"
 
print("a + b 输出结果：", a + b)
print("a * 2 输出结果：", a * 2)
print("a[1] 输出结果：", a[1])
print("a[1:4] 输出结果：", a[1:4])
 
if( "H" in a) :
    print("H 在变量 a 中")
else :
    print("H 不在变量 a 中")
 
if( "M" not in a) :
    print("M 不在变量 a 中")
else :
    print("M 在变量 a 中")
 
print (r'\n')
print (R'\n')
```
以上实例输出结果为：
```python
a + b 输出结果： HelloPython
a * 2 输出结果： HelloHello
a[1] 输出结果： e
a[1:4] 输出结果： ell
H 在变量 a 中
M 不在变量 a 中
\n
\n
```
---


### **Python字符串格式化**
Python 支持格式化字符串的输出 。尽管这样可能会用到非常复杂的表达式，但最基本的用法是将一个值插入到一个有字符串格式符 %s 的字符串中。  
在 Python 中，字符串格式化使用与 C 中 sprintf 函数一样的语法。

```python
#!/usr/bin/python3
 
print ("我叫 %s 今年 %d 岁!" % ('小明', 10))
```
以上实例输出结果：
```python
我叫 小明 今年 10 岁!
```
python字符串格式化符号:
![](/image/9-3.png)

格式化操作符辅助指令:
![](/image/9-4.png)

Python2.6 开始，新增了一种格式化字符串的函数 str.format()，它增强了字符串格式化的功能。

---


### **Python三引号**
python三引号允许一个字符串跨多行，字符串中可以包含换行符、制表符以及其他特殊字符。实例如下:

```python
#!/usr/bin/python3
 
para_str = """这是一个多行字符串的实例
多行字符串可以使用制表符
TAB ( \t )。
也可以使用换行符 [ \n ]。
"""
print (para_str)
```

以上实例执行结果为：

```python
这是一个多行字符串的实例
多行字符串可以使用制表符
TAB (    )。
也可以使用换行符 [ 
 ]。
```
三引号让程序员从引号和特殊字符串的泥潭里面解脱出来，自始至终保持一小块字符串的格式是所谓的WYSIWYG（所见即所得）格式的。  
一个典型的用例是，当你需要一块HTML或者SQL时，这时用字符串组合，特殊字符串转义将会非常的繁琐。
```python
errHTML = '''
<HTML><HEAD><TITLE>
Friends CGI Demo</TITLE></HEAD>
<BODY><H3>ERROR</H3>
<B>%s</B><P>
<FORM><INPUT TYPE=button VALUE=Back
ONCLICK="window.history.back()"></FORM>
</BODY></HTML>
'''
cursor.execute('''
CREATE TABLE users (  
login VARCHAR(8), 
uid INTEGER,
prid INTEGER)
''')
```

---

### **Unicode 字符串**
在Python2中，普通字符串是以8位ASCII码进行存储的，而Unicode字符串则存储为16位unicode字符串，这样能够表示更多的字符集。使用的语法是在字符串前面加上前缀 u。  
在Python3中，所有的字符串都是Unicode字符串。

---


### **Python 的字符串内建函数**
Python 的字符串常用内建函数如下：  
**capitalize()**  : 将字符串的第一个字符转换为大写。  
**center(width, fillchar)**  : 返回一个指定的宽度 width 居中的字符串，fillchar 为填充的字符，默认为空格。  
**count(str, beg= 0,end=len(string))**  : 返回 str 在 string 里面出现的次数，如果 beg 或者 end 指定则返回指定范围内 str 出现的次数。  
**bytes.decode(encoding="utf-8", errors="strict")**  : Python3 中没有 decode 方法，但我们可以使用 bytes 对象的 decode() 方法来解码给定的 bytes 对象，这个 bytes 对象可以由 str.encode() 来编码返回。  
**encode(encoding='UTF-8',errors='strict')**  : 以 encoding 指定的编码格式编码字符串，如果出错默认报一个ValueError 的异常，除非 errors 指定的是'ignore'或者'replace'。   
**endswith(suffix, beg=0, end=len(string))**  : 检查字符串是否以 obj 结束，如果beg 或者 end 指定则检查指定的范围内是否以 obj 结束，如果是，返回 True,否则返回 False。  
**expandtabs(tabsize=8)**  : 把字符串 string 中的 tab 符号转为空格，tab 符号默认的空格数是 8 。  
**find(str, beg=0, end=len(string))**  : 检测 str 是否包含在字符串中，如果指定范围 beg 和 end ，则检查是否包含在指定范围内，如果包含返回开始的索引值，否则返回-1。    
**index(str, beg=0, end=len(string))**  : 跟find()方法一样，只不过如果str不在字符串中会报一个异常。  
**isalnum()**  : 如果字符串至少有一个字符并且所有字符都是字母或数字则返 回 True,否则返回 False。  
**isalpha()**  : 如果字符串至少有一个字符并且所有字符都是字母则返回 True, 否则返回 False。  
**isdigit()**  : 如果字符串只包含数字则返回 True 否则返回 False。  
**islower()**  : 如果字符串中包含至少一个区分大小写的字符，并且所有这些(区分大小写的)字符都是小写，则返回 True，否则返回 False。  
**isnumeric()**  : 如果字符串中只包含数字字符，则返回 True，否则返回 False。  
**isspace()**  : 如果字符串中只包含空白，则返回 True，否则返回 False。  
**istitle()**  : 如果字符串是标题化的(见 title())则返回 True，否则返回 False。  
**isupper()**  : 如果字符串中包含至少一个区分大小写的字符，并且所有这些(区分大小写的)字符都是大写，则返回 True，否则返回 False。  
**join(seq)**  : 以指定字符串作为分隔符，将 seq 中所有的元素(的字符串表示)合并为一个新的字符串。  
**len(string)**  : 返回字符串长度。  
**ljust(width\[, fillchar\])**  : 返回一个原字符串左对齐,并使用 fillchar 填充至长度 width 的新字符串，fillchar 默认为空格。  
**lower()**  : 转换字符串中所有大写字符为小写。  
**lstrip()**  : 截掉字符串左边的空格或指定字符。
**maketrans()**  : 创建字符映射的转换表，对于接受两个参数的最简单的调用方式，第一个参数是字符串，表示需要转换的字符，第二个参数也是字符串表示转换的目标。  
**max(str)**  : 返回字符串 str 中最大的字母。  
**min(str)**  : 返回字符串 str 中最小的字母。  
**replace(old, new \[, max\])**  : 把 将字符串中的 str1 替换成 str2,如果 max 指定，则替换不超过 max 次。  
**rfind(str, beg=0,end=len(string))**  : 类似于 find()函数，不过是从右边开始查找。  
**rindex( str, beg=0, end=len(string))**  : 类似于 index()，不过是从右边开始。  
**rjust(width,\[, fillchar\])**  : 返回一个原字符串右对齐,并使用fillchar(默认空格）填充至长度 width 的新字符串。  
**rstrip()**  : 删除字符串字符串末尾的空格。  
**split(str="", num=string.count(str))**  : num=string.count(str)) 以 str 为分隔符截取字符串，如果 num 有指定值，则仅截取 num+1 个子字符串。  
**splitlines(\[keepends\])**  : 按照行('\r', '\r\n', \n')分隔，返回一个包含各行作为元素的列表，如果参数 keepends 为 False，不包含换行符，如果为 True，则保留换行符。  
**startswith(substr, beg=0,end=len(string))**  : 检查字符串是否是以指定子字符串 substr 开头，是则返回 True，否则返回 False。如果beg 和 end 指定值，则在指定范围内检查。  
**strip(\[chars\])**  : 在字符串上执行 lstrip()和 rstrip()。  
**swapcase()**  : 将字符串中大写转换为小写，小写转换为大写。  
**title()**  : 返回"标题化"的字符串,就是说所有单词都是以大写开始，其余字母均为小写(见 istitle())。  
**translate(table, deletechars="")**  : 根据 str 给出的表(包含 256 个字符)转换 string 的字符, 要过滤掉的字符放到 deletechars 参数中。  
**upper()**  : 转换字符串中的小写字母为大写。  
**zfill (width)**  : 返回长度为 width 的字符串，原字符串右对齐，前面填充0。  
**isdecimal()**  : 检查字符串是否只包含十进制字符，如果是返回 true，否则返回 false。  



---






