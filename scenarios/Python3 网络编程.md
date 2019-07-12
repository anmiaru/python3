## **Python3 网络编程**
Python 提供了两个级别访问的网络服务。：

* 低级别的网络服务支持基本的 Socket，它提供了标准的 BSD Sockets API，可以访问底层操作系统Socket接口的全部方法。
* 高级别的网络服务模块 SocketServer， 它提供了服务器中心类，可以简化网络服务器的开发。

---
### **什么是 Socket?**
Socket又称"套接字"，应用程序通常通过"套接字"向网络发出请求或者应答网络请求，使主机间或者一台计算机上的进程间可以通讯。

---
### **socket()函数**

Python 中，我们用 socket（）函数来创建套接字，语法格式如下：
```python
socket.socket([family[, type[, proto]]])
```
#### **参数**
* family: 套接字家族可以使AF_UNIX或者AF_INET
* type: 套接字类型可以根据是面向连接的还是非连接分为SOCK_STREAM或SOCK_DGRAM
* protocol: 一般不填默认为0.

#### **Socket 对象(内建)方法**

![](https://github.com/anmiaru/python3/raw/master/image/32-1.png)

![](https://github.com/anmiaru/python3/raw/master/image/32-2.png)

---
### **简单实例**

#### **服务端**
我们使用 socket 模块的 **socket** 函数来创建一个 socket 对象。socket 对象可以通过调用其他函数来设置一个 socket 服务。  
现在我们可以通过调用 **bind(hostname, port)** 函数来指定服务的 port(端口)。  
接着，我们调用 socket 对象的 accept 方法。该方法等待客户端的连接，并返回 connection 对象，表示已连接到客户端。

完整代码如下：
```python
#!/usr/bin/python3
# 文件名：server.py

# 导入 socket、sys 模块
import socket
import sys

# 创建 socket 对象
serversocket = socket.socket(
            socket.AF_INET, socket.SOCK_STREAM) 

# 获取本地主机名
host = socket.gethostname()

port = 9999

# 绑定端口号
serversocket.bind((host, port))

# 设置最大连接数，超过后排队
serversocket.listen(5)

while True:
    # 建立客户端连接
    clientsocket,addr = serversocket.accept()      

    print("连接地址: %s" % str(addr))
    
    msg='欢迎访问菜鸟教程！'+ "\r\n"
    clientsocket.send(msg.encode('utf-8'))
    clientsocket.close()
```
### **客户端**
接下来我们写一个简单的客户端实例连接到以上创建的服务。端口号为 9999。  
**socket.connect(hosname, port )** 方法打开一个 TCP 连接到主机为 hostname 端口为 port 的服务商。连接后我们就可以从服务端获取数据，记住，操作完成后需要关闭连接。

完整代码如下：
```python
#!/usr/bin/python3
# 文件名：client.py

# 导入 socket、sys 模块
import socket
import sys

# 创建 socket 对象
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM) 

# 获取本地主机名
host = socket.gethostname() 

# 设置端口号
port = 9999

# 连接服务，指定主机和端口
s.connect((host, port))

# 接收小于 1024 字节的数据
msg = s.recv(1024)

s.close()

print (msg.decode('utf-8'))
```
现在我们打开两个终端，第一个终端执行 server.py 文件：
```python
$ python3 server.py
```
第二个终端执行 client.py 文件：
```python
$ python3 client.py 
欢迎访问菜鸟教程！
```
这时我们再打开第一个终端，就会看到有以下信息输出：
```python
连接地址： ('192.168.0.118', 33397)
```
---

### **Python Internet 模块**
以下列出了 Python 网络编程的一些重要模块：

![](https://github.com/anmiaru/python3/raw/master/image/32-3.png)

更多内容可以参阅官网的[Python Socket Library and Modules](https://docs.python.org/3.0/library/socket.html)
