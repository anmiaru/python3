## **Python3 File(文件)方法**

### **open() 方法**  
Python open() 方法用于打开一个文件，并返回文件对象，在对文件进行处理过程都需要使用到这个函数，如果该文件无法被打开，会抛出 OSError。  
注意：使用 open() 方法一定要保证关闭文件对象，即调用 close() 方法。  
open() 函数常用形式是接收两个参数：文件名(file)和模式(mode)。
```python 
open(file, mode='r')
```

完整的语法格式为：
```python 
open(file, mode='r', buffering=-1, encoding=None, errors=None, newline=None, closefd=True, opener=None)
```
参数说明:
* file: 必需，文件路径（相对或者绝对路径）。
* mode: 可选，文件打开模式
* buffering: 设置缓冲
* encoding: 一般使用utf8
* errors: 报错级别
* newline: 区分换行符
* closefd: 传入的file参数类型
* opener:

mode 参数有：

![](/image/22-1.png)

![](/image/22-2.png)

默认为文本模式，如果要以二进制模式打开，加上 b 。

### **file 对象**  
file 对象使用 open 函数来创建，下表列出了 file 对象常用的函数：

![](/image/22-3.png)

![](/image/22-4.png)

下面对提到的这些函数进行介绍：

### **Python3 File close() 方法**
#### **描述**
close() 方法用于关闭一个已打开的文件。关闭后的文件不能再进行读写操作， 否则会触发 ValueError 错误。 close() 方法允许调用多次。

当 file 对象，被引用到操作另外一个文件时，Python 会自动关闭之前的 file 对象。 使用 close() 方法关闭文件是一个好的习惯。
#### **语法**
close() 方法语法如下：
```python
fileObject.close();
```
#### **参数**
* 无

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 close() 方法的使用：
```python 
#!/usr/bin/python3

# 打开文件
fo = open("runoob.txt", "wb")
print("文件名为: ", fo.name)

# 关闭文件
fo.close()
```
以上实例输出结果为：
```python 
文件名为:  runoob.txt
```

---


### **Python3 File flush() 方法**
#### **描述**
flush() 方法是用来刷新缓冲区的，即将缓冲区中的数据立刻写入文件，同时清空缓冲区，不需要是被动的等待输出缓冲区写入。

一般情况下，文件关闭后会自动刷新缓冲区，但有时你需要在关闭前刷新它，这时就可以使用 flush() 方法。
#### **语法**
flush() 方法语法如下：
```python
fileObject.flush();
```
#### **参数**
* 无

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 flush() 方法的使用：
```python 
#!/usr/bin/python3

# 打开文件
fo = open("runoob.txt", "wb")
print ("文件名为: ", fo.name)

# 刷新缓冲区
fo.flush()

# 关闭文件
fo.close()
```
以上实例输出结果为：
```python 
文件名为:  runoob.txt
```

---



### **Python3 File fileno() 方法**
#### **描述**
fileno() 方法返回一个整型的文件描述符(file descriptor FD 整型)，可用于底层操作系统的 I/O 操作。
#### **语法**
fileno() 方法语法如下：
```python
fileObject.fileno(); 
```
#### **参数**
* 无

#### **返回值**
返回文件描述符。

#### **实例**
以下实例演示了 fileno() 方法的使用：
```python 
#!/usr/bin/python3

# 打开文件
fo = open("runoob.txt", "wb")
print ("文件名为: ", fo.name)

fid = fo.fileno()
print ("文件描述符为: ", fid)

# 关闭文件
fo.close()
```
以上实例输出结果为：
```python 
文件名为:  runoob.txt
文件描述符为:  3
```

---


### **Python3 File isatty() 方法**
#### **描述**
isatty() 方法检测文件是否连接到一个终端设备，如果是返回 True，否则返回 False。
#### **语法**
isatty() 方法语法如下：
```python
fileObject.isatty(); 
```
#### **参数**
* 无

#### **返回值**
如果连接到一个终端设备返回 True，否则返回 False。

#### **实例**
以下实例演示了 isatty() 方法的使用：
```python 
#!/usr/bin/python3

# 打开文件
fo = open("runoob.txt", "wb")
print ("文件名为: ", fo.name)

ret = fo.isatty()
print ("返回值 : ", ret)

# 关闭文件
fo.close()
```
以上实例输出结果为：
```python 
文件名为:  runoob.txt
返回值 :  False
```

---



### **Python3 File next() 方法**
#### **描述**
Python 3 中的 File 对象不支持 next() 方法。

Python 3 的内置函数 next() 通过迭代器调用 \_\_next\_\_() 方法返回下一项。 在循环中，next()方法会在每次循环中调用，该方法返回文件的下一行，如果到达结尾(EOF),则触发 StopIteration
#### **语法**
next() 方法语法如下：
```python
next(iterator[,default])
```
#### **参数**
* 无

#### **返回值**
返回文件下一行。

#### **实例**
以下实例演示了 next() 方法的使用：

文件 runoob.txt 的内容如下：
```python 
这是第一行
这是第二行
这是第三行
这是第四行
这是第五行
```
循环读取文件的内容：
```python 
#!/usr/bin/python3

# 打开文件
fo = open("runoob.txt", "r")
print ("文件名为: ", fo.name)

for index in range(5):
    line = next(fo)
    print ("第 %d 行 - %s" % (index, line))

# 关闭文件
fo.close()
```
以上实例输出结果为：
```python 
文件名为:  runoob.txt
第 0 行 - 这是第一行

第 1 行 - 这是第二行

第 2 行 - 这是第三行

第 3 行 - 这是第四行

第 4 行 - 这是第五行
```

---



### **Python3 File read() 方法**
#### **描述**
read() 方法用于从文件读取指定的字节数，如果未给定或为负则读取所有。
#### **语法**
read() 方法语法如下：
```python
fileObject.read(); 
```
#### **参数**
* size -- 从文件中读取的字节数。

#### **返回值**
返回从字符串中读取的字节。

#### **实例**
以下实例演示了 read() 方法的使用：

文件 runoob.txt 的内容如下：
```python 
这是第一行
这是第二行
这是第三行
这是第四行
这是第五行
```
循环读取文件的内容：
```python 
#!/usr/bin/python3

# 打开文件
fo = open("runoob.txt", "r+")
print ("文件名为: ", fo.name)

line = fo.read(10)
print ("读取的字符串: %s" % (line))

# 关闭文件
fo.close()
```
以上实例输出结果为：
```python 
文件名为:  runoob.txt
读取的字符串: 这是第一行
这是第二
```
---



### **Python3 File readline() 方法**
#### **描述**
readline() 方法用于从文件读取整行，包括 "\n" 字符。如果指定了一个非负数的参数，则返回指定大小的字节数，包括 "\n" 字符。
#### **语法**
readline() 方法语法如下：
```python
fileObject.readline(); 
```
#### **参数**
* size -- 从文件中读取的字节数。

#### **返回值**
返回从字符串中读取的字节。

#### **实例**
以下实例演示了 readline() 方法的使用：

文件 runoob.txt 的内容如下：
```python 
1:www.runoob.com
2:www.runoob.com
3:www.runoob.com
4:www.runoob.com
5:www.runoob.com
```
循环读取文件的内容：
```python 
#!/usr/bin/python
# -*- coding: UTF-8 -*-

# 打开文件
fo = open("runoob.txt", "r+")
print ("文件名为: ", fo.name)

line = fo.readline()
print ("读取第一行 %s" % (line))

line = fo.readline(5)
print ("读取的字符串为: %s" % (line))

# 关闭文件
fo.close()
```
以上实例输出结果为：
```python 
文件名为:  runoob.txt
读取第一行 1:www.runoob.com

读取的字符串为: 2:www
```
---



### **Python3 File readlines() 方法**
#### **描述**
readlines() 方法用于读取所有行(直到结束符 EOF)并返回列表，该列表可以由 Python 的 for... in ... 结构进行处理。 如果碰到结束符 EOF 则返回。

#### **语法**
readlines() 方法语法如下：
```python
fileObject.readlines( );
```
#### **参数**
* 无。

#### **返回值**
返回列表，包含所有的行。

#### **实例**
以下实例演示了 readline() 方法的使用：

文件 runoob.txt 的内容如下：
```python 
1:www.runoob.com
2:www.runoob.com
3:www.runoob.com
4:www.runoob.com
5:www.runoob.com
```
循环读取文件的内容：
```python 
#!/usr/bin/python3
 
# 打开文件
fo = open("runoob.txt", "r")
print ("文件名为: ", fo.name)
 
for line in fo.readlines():                          #依次读取每行  
    line = line.strip()                             #去掉每行头尾空白  
    print ("读取的数据为: %s" % (line))
 
# 关闭文件
fo.close()
```
以上实例输出结果为：
```python 
文件名为:  runoob.txt
读取的数据为: 1:www.runoob.com
读取的数据为: 2:www.runoob.com
读取的数据为: 3:www.runoob.com
读取的数据为: 4:www.runoob.com
读取的数据为: 5:www.runoob.com
```
---



### **Python3 File seek() 方法**
#### **描述**
seek() 方法用于移动文件读取指针到指定位置。
#### **语法**
seek() 方法语法如下：
```python
fileObject.seek(offset[, whence])
```
#### **参数**
* offset -- 开始的偏移量，也就是代表需要移动偏移的字节数，如果是负数表示从倒数第几位开始。

* whence：可选，默认值为 0。给 offset 定义一个参数，表示要从哪个位置开始偏移；0 代表从文件开头开始算起，1 代表从当前位置开始算起，2 代表从文件末尾算起。

#### **返回值**
如果操作成功，则返回新的文件位置，如果操作失败，则函数返回 -1。

#### **实例**
以下实例演示了 readline() 方法的使用：
```python 
>>> f = open('workfile', 'rb+')
>>> f.write(b'0123456789abcdef')
16
>>> f.seek(5)      # 移动到文件的第六个字节
5
>>> f.read(1)
b'5'
>>> f.seek(-3, 2)  # 移动到文件倒数第三个字节
13
>>> f.read(1)
b'd'
```
文件 runoob.txt 的内容如下：
```python 
1:www.runoob.com
2:www.runoob.com
3:www.runoob.com
4:www.runoob.com
5:www.runoob.com
```
循环读取文件的内容：
```python 
#!/usr/bin/python3
 
# 打开文件
fo = open("runoob.txt", "r+")
print ("文件名为: ", fo.name)
 
line = fo.readline()
print ("读取的数据为: %s" % (line))
 
# 重新设置文件读取指针到开头
fo.seek(0, 0)
line = fo.readline()
print ("读取的数据为: %s" % (line))
 
 
# 关闭文件
fo.close()
```
以上实例输出结果为：
```python 
文件名为:  runoob.txt
读取的数据为: 1:www.runoob.com

读取的数据为: 1:www.runoob.com
```
---



### **Python3 File tell() 方法**
#### **描述**
tell() 方法返回文件的当前位置，即文件指针当前位置。
#### **语法**
tell() 方法语法如下：
```python
fileObject.tell()
```
#### **参数**
* 无

#### **返回值**
返回文件的当前位置。

#### **实例**
以下实例演示了 tell() 方法的使用：

文件 runoob.txt 的内容如下：
```python 
1:www.runoob.com
2:www.runoob.com
3:www.runoob.com
4:www.runoob.com
5:www.runoob.com
```
循环读取文件的内容：
```python 
#!/usr/bin/python3
 
# 打开文件
fo = open("runoob.txt", "r+")
print ("文件名为: ", fo.name)
 
line = fo.readline()
print ("读取的数据为: %s" % (line))
 
# 获取当前文件位置
pos = fo.tell()
print ("当前位置: %d" % (pos))
 
 
# 关闭文件
fo.close()
```
以上实例输出结果为：
```python 
文件名为:  runoob.txt
读取的数据为: 1:www.runoob.com

当前位置: 17
```

---


### **Python3 File truncate() 方法**
#### **描述**
truncate() 方法用于从文件的首行首字节开始截断，截断文件为 size 个字节，无 size 表示从当前位置截断；截断之后 V 后面的所有字节被删除，其中 Widnows 系统下的换行代表2个字节大小。
#### **语法**
truncate() 方法语法如下：
```python
fileObject.truncate( [ size ])
```
#### **参数**
* size -- 可选，如果存在则文件截断为 size 字节。

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 truncate() 方法的使用：

文件 runoob.txt 的内容如下：
```python 
1:www.runoob.com
2:www.runoob.com
3:www.runoob.com
4:www.runoob.com
5:www.runoob.com
```
循环读取文件的内容：
```python 
#!/usr/bin/python3

fo = open("runoob.txt", "r+")
print ("文件名: ", fo.name)

line = fo.readline()
print ("读取行: %s" % (line))

fo.truncate()
line = fo.readlines()
print ("读取行: %s" % (line))

# 关闭文件
fo.close()
```
以上实例输出结果为：
```python 
文件名:  runoob.txt
读取行: 1:www.runoob.com

读取行: ['2:www.runoob.com\n', '3:www.runoob.com\n', '4:www.runoob.com\n', '5:www.runoob.com\n']
```

以下实例截取 runoob.txt 文件的10个字节：
```python 
#!/usr/bin/python3

# 打开文件
fo = open("runoob.txt", "r+")
print ("文件名为: ", fo.name)

# 截取10个字节
fo.truncate(10)

str = fo.read()
print ("读取数据: %s" % (str))

# 关闭文件
fo.close()
```
以上实例输出结果为：
```python 
文件名为:  runoob.txt
读取数据: 1:www.runo
```
---


### **Python3 File write() 方法**
#### **描述**
write() 方法用于向文件中写入指定字符串。

在文件关闭前或缓冲区刷新前，字符串内容存储在缓冲区中，这时你在文件中是看不到写入的内容的。

如果文件打开模式带 b，那写入文件内容时，str (参数)要用 encode 方法转为 bytes 形式，否则报错：TypeError: a bytes-like object is required, not 'str'。
#### **语法**
write() 方法语法如下：
```python
fileObject.write( [ str ])
```
#### **参数**
* str -- 要写入文件的字符串。

#### **返回值**
返回的是写入的字符长度。

#### **实例**
文件 runoob.txt 的内容如下：
```python 
1:www.runoob.com
2:www.runoob.com
3:www.runoob.com
4:www.runoob.com
5:www.runoob.com
```
以下实例演示了 write() 方法的使用：
```python 
#!/usr/bin/python3

# 打开文件
fo = open("runoob.txt", "r+")
print ("文件名: ", fo.name)

str = "6:www.runoob.com"
# 在文件末尾写入一行
fo.seek(0, 2)
line = fo.write( str )

# 读取文件所有内容
fo.seek(0,0)
for index in range(6):
    line = next(fo)
    print ("文件行号 %d - %s" % (index, line))

# 关闭文件
fo.close()
```
以上实例输出结果为：
```python 
文件行号 0 - 1:www.runoob.com

文件行号 1 - 2:www.runoob.com

文件行号 2 - 3:www.runoob.com

文件行号 3 - 4:www.runoob.com

文件行号 4 - 5:www.runoob.com

文件行号 5 - 6:www.runoob.com
```
查看文件内容：
```python 
$ cat runoob.txt 
1:www.runoob.com
2:www.runoob.com
3:www.runoob.com
4:www.runoob.com
5:www.runoob.com
6:www.runoob.com
```

---


### **Python3 File writelines() 方法**
#### **描述**
writelines() 方法用于向文件中写入一序列的字符串。

这一序列字符串可以是由迭代对象产生的，如一个字符串列表。

换行需要制定换行符 \n。
#### **语法**
writelines() 方法语法如下：
```python
fileObject.writelines( [ str ])
```
#### **参数**
* str -- 要写入文件的字符串序列。

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 writelines() 方法的使用：
```python 
#!/usr/bin/python3

# 打开文件
fo = open("test.txt", "w")
print ("文件名为: ", fo.name)
seq = ["菜鸟教程 1\n", "菜鸟教程 2"]
fo.writelines( seq )

# 关闭文件
fo.close()
```
以上实例输出结果为：
```python 
文件名为:  test.txt
```
查看文件内容：
```python 
$ cat test.txt 
菜鸟教程 1
菜鸟教程 2
```
---











