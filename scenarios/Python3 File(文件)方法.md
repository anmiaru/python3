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

![](https://github.com/anmiaru/python3/raw/master/image/22-1.png)

![](https://github.com/anmiaru/python3/raw/master/image/22-2.png)

默认为文本模式，如果要以二进制模式打开，加上 b 。

### **file 对象**  
file 对象使用 open 函数来创建，下表列出了 file 对象常用的函数：

![](https://github.com/anmiaru/python3/raw/master/image/22-3.png)

![](https://github.com/anmiaru/python3/raw/master/image/22-4.png)












