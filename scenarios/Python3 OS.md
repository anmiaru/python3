## **Python3 OS 文件/目录方法**
os 模块提供了非常丰富的方法用来处理文件和目录。常用的方法如下表所示：

![](/image/23-1.png)

![](/image/23-2.png)

![](/image/23-3.png)

![](/image/23-4.png)

![](/image/23-5.png)

![](/image/23-6.png)

![](/image/23-7.png)

![](/image/23-8.png)

![](/image/23-9.png)

![](/image/23-10.png)

![](/image/23-11.png)


下面对这些方法进行介绍：

### **Python3 os.access() 方法**
#### **描述**
os.access() 方法使用当前的uid/gid尝试访问路径。大部分操作使用有效的 uid/gid, 因此运行环境可以在 suid/sgid 环境尝试。
#### **语法**
access()方法语法格式如下：
```python
os.access(path, mode);
```
#### **参数**
* path \-\- 要用来检测是否有访问权限的路径。

* mode \-\- mode为F\_OK，测试存在的路径，或者它可以是包含R\_OK, W\_OK和X\_OK或者R\_OK, W\_OK和X\_OK其中之一或者更多。
   * os.F\_OK: 作为access()的mode参数，测试path是否存在。
   * os.R\_OK: 包含在access()的mode参数中 ， 测试path是否可读。
   * os.W\_OK 包含在access()的mode参数中 ， 测试path是否可写。
   * os.X\_OK 包含在access()的mode参数中 ，测试path是否可执行。

#### **返回值**
如果允许访问返回 True , 否则返回False。

#### **实例**
以下实例演示了 access() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 假定 /tmp/foo.txt 文件存在，并有读写权限

ret = os.access("/tmp/foo.txt", os.F_OK)
print ("F_OK - 返回值 %s"% ret)

ret = os.access("/tmp/foo.txt", os.R_OK)
print ("R_OK - 返回值 %s"% ret)

ret = os.access("/tmp/foo.txt", os.W_OK)
print ("W_OK - 返回值 %s"% ret)

ret = os.access("/tmp/foo.txt", os.X_OK)
print ("X_OK - 返回值 %s"% ret)
```
执行以上程序输出结果为：
```python 
F_OK - 返回值 True
R_OK - 返回值 True
W_OK - 返回值 True
X_OK - 返回值 False
```

---

### **Python3 os.chdir() 方法**
#### **描述**
os.chdir() 方法用于改变当前工作目录到指定的路径。
#### **语法**
chdir()方法语法格式如下：
```python
os.chdir(path)
```
#### **参数**
* path -- 要切换到的新路径。

#### **返回值**
如果允许访问返回 True , 否则返回False。

#### **实例**
以下实例演示了 chdir() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

path = "/tmp"

# 查看当前工作目录
retval = os.getcwd()
print ("当前工作目录为 %s" % retval)

# 修改当前工作目录
os.chdir( path )

# 查看修改后的工作目录
retval = os.getcwd()

print ("目录修改成功 %s" % retval)
```
执行以上程序输出结果为：
```python 
当前工作目录为 /www
目录修改成功 /tmp
```


---



### **Python3 os.chflags() 方法**
#### **描述**
os.chflags() 方法用于设置路径的标记为数字标记。多个标记可以使用 OR 来组合起来。

只支持在 Unix 下使用。
#### **语法**
chflags()方法语法格式如下：
```python
os.chflags(path, flags)
```
#### **参数**
* path -- 文件名路径或目录路径。
* flags -- 可以是以下值：
  * stat.UF_NODUMP: 非转储文件
  * stat.UF_APPEND: 文件只能追加内容
  * stat.UF_NOUNLINK: 文件不可删除
  * stat.UF_OPAQUE: 目录不透明，需要通过联合堆栈查看
  * stat.SF_ARCHIVED: 可存档文件(超级用户可设)
  * stat.SF_IMMUTABLE: 文件是只读的(超级用户可设)
  * stat.SF_APPEND: 文件只能追加内容(超级用户可设)
  * stat.SF_NOUNLINK: 文件不可删除(超级用户可设)
  * stat.SF_SNAPSHOT: 快照文件(超级用户可设)
#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 chflags() 方法的使用：
```python 
#!/usr/bin/python3

import os,stat

path = "/tmp/foo.txt"

# 为文件设置标记，使得它不能被重命名和删除
flags = stat.SF_NOUNLINK
retval = os.chflags( path, flags )
print ("返回值: %s" % retval)
```
执行以上程序输出结果为：
```python 
返回值: None
```


---


### **Python3 os.chmod() 方法**
#### **描述**
os.chmod() 方法用于更改文件或目录的权限。

Unix 系统可用。
#### **语法**
chmod()方法语法格式如下：
```python
os.chmod(path, mode)
```
#### **参数**
* path -- 文件名路径或目录路径。
* flags -- 可用以下选项按位或操作生成， 目录的读权限表示可以获取目录里文件名列表， ，执行权限表示可以把工作目录切换到此目录 ，删除添加目录里的文件必须同时有写和执行权限 ，文件权限以用户id->组id->其它顺序检验,最先匹配的允许或禁止权限被应用。
  * stat.S_IXOTH: 其他用户有执行权0o001
  * stat.S_IWOTH: 其他用户有写权限0o002
  * stat.S_IROTH: 其他用户有读权限0o004
  * stat.S_IRWXO: 其他用户有全部权限(权限掩码)0o007
  * stat.S_IXGRP: 组用户有执行权限0o010
  * stat.S_IWGRP: 组用户有写权限0o020
  * stat.S_IRGRP: 组用户有读权限0o040
  * stat.S_IRWXG: 组用户有全部权限(权限掩码)0o070
  * stat.S_IXUSR: 拥有者具有执行权限0o100
  * stat.S_IWUSR: 拥有者具有写权限0o200
  * stat.S_IRUSR: 拥有者具有读权限0o400
  * stat.S_IRWXU: 拥有者有全部权限(权限掩码)0o700
  * stat.S_ISVTX: 目录里文件目录只有拥有者才可删除更改0o1000
  * stat.S_ISGID: 执行此文件其进程有效组为文件所在组0o2000
  * stat.S_ISUID: 执行此文件其进程有效用户为文件所有者0o4000
  * stat.S_IREAD: windows下设为只读
  * stat.S_IWRITE: windows下取消只读
#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 chmod() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys, stat

# 假定 /tmp/foo.txt 文件存在，设置文件可以通过用户组执行

os.chmod("/tmp/foo.txt", stat.S_IXGRP)

# 设置文件可以被其他用户写入
os.chmod("/tmp/foo.txt", stat.S_IWOTH)

print ("修改成功!!")
```
执行以上程序输出结果为：
```python 
修改成功!!
```


---

### **Python3 os.chown() 方法**
#### **描述**
os.chown() 方法用于更改文件所有者，如果不修改可以设置为 -1, 你需要超级用户权限来执行权限修改操作。

只支持在 Unix 下使用。
#### **语法**
chown()方法语法格式如下：
```python
os.chown(path, uid, gid);
```
#### **参数**
* path -- 设置权限的文件路径
* uid -- 所属用户 ID
* gid -- 所属用户组 ID

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 chown() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 假定 /tmp/foo.txt 文件存在.
# 设置所有者 ID 为 100 
os.chown("/tmp/foo.txt", 100, -1)

print ("修改权限成功!!")
```
执行以上程序输出结果为：
```python 
修改权限成功!!
```


---


### **Python3 os.chroot() 方法**
#### **描述**
os.chroot() 方法用于更改当前进程的根目录为指定的目录，使用该函数需要管理员权限。

在 unix 中有效。
#### **语法**
chroot()方法语法格式如下：
```python
os.chroot(path);
```
#### **参数**
* path -- 要设置为根目录的目录。

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 chroot() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 设置根目录为 /tmp

os.chroot("/tmp")

print ("修改根目录成功!!")
```
执行以上程序输出结果为：
```python 
修改根目录成功!!
```


---


### **Python3 os.close() 方法**
#### **描述**
os.close() 方法用于关闭指定的文件描述符 fd。
#### **语法**
close()方法语法格式如下：
```python
os.close(fd);
```
#### **参数**
* fd -- 文件描述符。

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 close() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 打开文件
fd = os.open( "foo.txt", os.O_RDWR|os.O_CREAT )

#  写入字符串
os.write(fd, "This is test")

# 关闭文件
os.close( fd )

print ("关闭文件成功!!")
```
执行以上程序输出结果为：
```python 
关闭文件成功!!
```


---


### **Python3 os.closerange() 方法**
#### **描述**
os.closerange() 方法用于关闭所有文件描述符 fd，从 fd_low (包含) 到 fd_high (不包含), 错误会忽略。
#### **语法**
closerange()方法语法格式如下：
```python
os.closerange(fd_low, fd_high);
```
#### **参数**
* fd_low -- 最小文件描述符
* fd_high -- 最大文件描述符

该方法类似于：
```python 
for fd in xrange(fd_low, fd_high):
    try:
        os.close(fd)
    except OSError:
        pass
```
#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 closerange() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 打开文件
fd = os.open( "foo.txt", os.O_RDWR|os.O_CREAT )

# 写入字符串
os.write(fd, "This is test")

# 关闭文件
os.closerange( fd, fd)

print ("关闭文件成功!!")
```
执行以上程序输出结果为：
```python 
关闭文件成功!!
```


---


### **Python3 os.dup() 方法**
#### **描述**
os.dup() 方法用于复制文件描述符 fd。
#### **语法**
dup()方法语法格式如下：
```python
os.dup(fd);
```
#### **参数**
* fd -- 文件描述符

#### **返回值**
返回复制的文件描述符。

#### **实例**
以下实例演示了 dup() 方法的使用：
```python 
#!/usr/bin/python3
 
import os, sys
 
# 打开文件
fd = os.open( "foo.txt", os.O_RDWR|os.O_CREAT )
 
# 复制文件描述符
d_fd = os.dup( fd )
 
# 使用复制的文件描述符写入文件
os.write(d_fd, "This is test".encode())
 
# 关闭文件
os.closerange( fd, d_fd)
 
print ("关闭所有文件成功!!")
```
执行以上程序输出结果为：
```python 
关闭所有文件成功!!
```


---


### **Python3 os.dup2() 方法**
#### **描述**
os.dup2() 方法用于将一个文件描述符 fd 复制到另一个 fd2。

Unix, Windows 上可用。
#### **语法**
dup2()方法语法格式如下：
```python
os.dup2(fd, fd2);
```
#### **参数**
* fd -- 要被复制的文件描述符
* fd2 -- 复制的文件描述符

#### **返回值**
没有返回值。

#### **实例**
以下实例演示了 dup2() 方法的使用：
```python 
import os
 
# 打开一个文件
f=open('txt','a')
 
# 将这个文件描述符代表的文件，传递给 1 描述符指向的文件（也就是 stdout）
os.dup2(f.fileno(), 1)
 
# 关闭文件
f.close()
 
# print 输出到标准输出流，就是文件描述符1
print('runoob')
print('google')
```
执行以上程序输出结果为, 生成一个txt文件，内容是：
```python 
runoob
google
```


---


### **Python3 os.fchdir() 方法**
#### **描述**
os.fchdir() 方法通过文件描述符改变当前工作目录。

Unix 上可用。
#### **语法**
fchdir()方法语法格式如下：
```python
os.fchdir(fd);
```
#### **参数**
* fd -- 文件描述符

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 fchdir() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 首先到目录 "/var/www/html" 
os.chdir("/var/www/html" )

# 输出当前目录
print ("当前工作目录为 : %s" % os.getcwd())

# 打开新目录 "/tmp"
fd = os.open( "/tmp", os.O_RDONLY )

# 使用 os.fchdir() 方法修改到新目录
os.fchdir(fd)

# 输出当前目录
print ("当前工作目录为 : %s" % os.getcwd())

# 关闭打开的目录
os.close( fd )
```
执行以上程序输出结果为：
```python 
当前工作目录为 : /var/www/html
当前工作目录为 : /tmp
```


---


### **Python3 os.fchmod() 方法**
#### **描述**
os.fchmod() 方法用于改变一个文件的访问权限，该文件由参数fd指定，参数mode是Unix下的文件访问权限。

Unix上可用。
#### **语法**
fchmod()方法语法格式如下：
```python
os.fchmod(fd, mode);
```
#### **参数**
* fd -- 文件描述符
* mode -- 可以是以下一个或多个组成，多个使用 "|" 隔开：
  * stat.S_ISUID:设置 UID 位
  * stat.S_ISGID: 设置组 ID 位
  * stat.S_ENFMT: 系统文件锁定的执法行动
  * stat.S_ISVTX: 在执行之后保存文字和图片
  * stat.S_IREAD: 对于拥有者读的权限，Unix V7 版本中 stat.S_IRUSR 的代名词
  * stat.S_IWRITE: 对于拥有者写的权限，Unix V7 版本中 stat.S_IWUSR 的代名词
  * stat.S_IEXEC: 对于拥有者执行的权限，Unix V7 版本中 stat.S_IXUSR 的代名词
  * stat.S_IRWXU:对于拥有者读、写、执行的权限
  * stat.S_IRUSR: 对于拥有者读的权限
  * stat.S_IWUSR: 对于拥有者写的权限
  * stat.S_IXUSR: 对于拥有者执行的权限
  * stat.S_IRWXG: 对于同组的人读写执行的权限
  * stat.S_IRGRP: 对于同组读的权限
  * stat.S_IWGRP:对于同组写的权限
  * stat.S_IXGRP: 对于同组执行的权限
  * stat.S_IRWXO: 对于其他组读写执行的权限
  * stat.S_IROTH: 对于其他组读的权限
  * stat.S_IWOTH: 对于其他组写的权限
  * stat.S_IXOTH:对于其他组执行的权限
#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 fchmod() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys, stat

# 打开文件 "/tmp/foo.txt"
fd = os.open( "/tmp", os.O_RDONLY )

# 设置文件可通过组执行

os.fchmod( fd, stat.S_IXGRP)

# 设置文件可被其他用户写入
os.fchmod(fd, stat.S_IWOTH)

print ("修改权限成功!!")

# 关闭文件
os.close( fd )
```
执行以上程序输出结果为：
```python 
修改权限成功!!
```


---


### **Python3 os.fchown() 方法**
#### **描述**
os.fchown() 方法用于修改一个文件的所有权，这个函数修改一个文件的用户ID和用户组ID，该文件由文件描述符fd指定。

Unix上可用。
#### **语法**
fchown()方法语法格式如下：
```python
os.fchown(fd, uid, gid)
```
#### **参数**
* fd -- 文件描述符
* uid -- 文件所有者的用户id
* gid -- 文件所有者的用户组id

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 fchown() 方法的使用：
```python 
#!/usr/bin/python3
 
import os, sys, stat
 
# 打开文件 "/tmp/foo.txt"
fd = os.open( "/tmp", os.O_RDONLY )
 
# 设置文件的用户 id 为 100
os.fchown( fd, 100, -1)
 
# 设置文件的用户组 id 为 50
os.fchown( fd, -1, 50)
 
 
print ("修改权限成功!!")
 
# 关闭文件
os.close( fd )
```
执行以上程序输出结果为：
```python 
修改权限成功!!
```


---


### **Python3 os.fdatasync() 方法**
#### **描述**
os.fdatasync() 方法用于强制将文件写入磁盘，该文件由文件描述符fd指定，但是不强制更新文件的状态信息。如果你需要刷新缓冲区可以使用该方法。

Unix上可用。
#### **语法**
fdatasync()方法语法格式如下：
```python
os.fdatasync(fd);
```
#### **参数**
* fd -- 文件描述符

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 fdatasync() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 打开文件 "/tmp/foo.txt"
fd = os.open( "foo.txt", os.O_RDWR|os.O_CREAT )

# 写入字符串
os.write(fd, "This is test")

# 使用 fdatasync() 方法
os.fdatasync(fd)

# 读取文件
os.lseek(fd, 0, 0)
str = os.read(fd, 100)
print ("读取的字符是 : ", str)

# 关闭文件
os.close( fd )

print ("关闭文件成功!!")
```
执行以上程序输出结果为：
```python 
读取的字符是 :  This is test
关闭文件成功!!
```


---


### **Python3 os.fdopen() 方法**
#### **描述**
os.fdopen() 方法用于通过文件描述符 fd 创建一个文件对象，并返回这个文件对象。

该方法是内置函数 open() 的别名，可以接收一样的参数，唯一的区别是 fdopen() 的第一个参数必须是整型。
#### **语法**
fdopen()方法语法格式如下：
```python
os.fdopen(fd, [, mode[, bufsize]]);
```
#### **参数**
* fd -- 打开的文件的描述符，在Unix下，描述符是一个小整数。
* mode -- 可选，和 Python 内建的 open 函数一样，mode参数可以指定『r,w,a,r+,w+,a+,b』等，表示文件的是只读的还是可以读写的，以及打开文件是以二进制还是文本形式打开。这些参数和C语言中的<stdio.h>中fopen函数中指定的mode参数类似。
* bufsize -- 可选，指定返回的文件对象是否带缓冲：bufsize=0，表示没有带缓冲；bufsize=1，表示该文件对象是行缓冲的；bufsize=正数，表示使用一个指定大小的缓冲冲，单位为byte，但是这个大小不是精确的；bufsize=负数，表示使用一个系统默认大小的缓冲，对于tty字元设备一般是行缓冲，而对于其他文件则一般是全缓冲。如果这个参数没有制定，则使用系统默认的缓冲设定。

#### **返回值**
通过文件描述符返回的文件对象。

#### **实例**
以下实例演示了 fdopen() 方法的使用：
```python 
#!/usr/bin/python3
 
import os, sys
 
# 打开文件
fd = os.open( "foo.txt", os.O_RDWR|os.O_CREAT )
 
# 获取以上文件的对象
fo = os.fdopen(fd, "w+")
 
# 获取当前文章
print ("Current I/O pointer position :%d" % fo.tell())
 
# 写入字符串
fo.write( "Python is a great language.\nYeah its great!!\n");
 
# 读取内容
os.lseek(fd, 0, 0)
str = os.read(fd, 100)
print ("Read String is : ", str)
 
# 获取当前位置
print ("Current I/O pointer position :%d" % fo.tell())
 
# 关闭文件
os.close( fd )
 
print ("关闭文件成功!!")
```
执行以上程序输出结果为：
```python 
Current I/O pointer position :0
Read String is :  This is testPython is a great language.
Yeah its great!!

Current I/O pointer position :45
关闭文件成功!!
```


---


### **Python3 os.fpathconf() 方法**
#### **描述**
os.fpathconf() 方法用于返回一个打开的文件的系统配置信息。

Unix上可用。
#### **语法**
fpathconf()方法语法格式如下：
```python
os.fpathconf(fd, name)
```
#### **参数**
* fd -- 打开的文件的描述符。
* name -- 可选，和buffersize参数和Python内建的open函数一样，mode参数可以指定『r,w,a,r+,w+,a+,b』等，表示文件的是只读的还是可以读写的，以及打开文件是以二进制还是文本形式打开。这些参数和C语言中的/<stdio.h/>中fopen函数中指定的mode参数类似。

#### **返回值**
返回一个打开的文件的系统配置信息。

#### **实例**
以下实例演示了 fpathconf() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 打开文件
fd = os.open( "foo.txt", os.O_RDWR|os.O_CREAT )

print ("%s" % os.pathconf_names)

# 获取最大文件连接数
no = os.fpathconf(fd, 'PC_LINK_MAX')
print ("文件最大连接数为 :%d" % no)

# 获取文件名最大长度
no = os.fpathconf(fd, 'PC_NAME_MAX')
print ("文件名最大长度为 :%d" % no)

# 关闭文件
os.close( fd )

print ("关闭文件成功!!")
```
执行以上程序输出结果为：
```python 
{'PC_MAX_INPUT': 2, 'PC_VDISABLE': 8, 'PC_SYNC_IO': 9, 
'PC_SOCK_MAXBUF': 12, 'PC_NAME_MAX': 3, 'PC_MAX_CANON': 1, 
'PC_PRIO_IO': 11, 'PC_CHOWN_RESTRICTED': 6, 'PC_ASYNC_IO': 10, 
'PC_NO_TRUNC': 7, 'PC_FILESIZEBITS': 13, 'PC_LINK_MAX': 0, 
'PC_PIPE_BUF': 5, 'PC_PATH_MAX': 4}

文件最大连接数为 :127
文件名最大长度为 :255
Closed the file successfully!!
```


---


### **Python3 os.fstat() 方法**
#### **描述**
os.fstat() 方法用于返回文件描述符fd的状态，类似 stat()。

Unix，Windows上可用。

fstat 方法返回的结构:
* st_dev: 设备信息
* st_ino: 文件的i-node值
* st_mode: 文件信息的掩码，包含了文件的权限信息，文件的类型信息(是普通文件还是管道文件，或者是其他的文件类型)
* st_nlink: 硬连接数
* st_uid: 用户ID
* st_gid: 用户组 ID
* st_rdev: 设备 ID (如果指定文件)
* st_size: 文件大小，以byte为单位
* st_blksize: 系统 I/O 块大小
* st_blocks: 文件的是由多少个 512 byte 的块构成的
* st_atime: 文件最近的访问时间
* st_mtime: 文件最近的修改时间
* st_ctime: 文件状态信息的修改时间（不是文件内容的修改时间）

#### **语法**
fstat()方法语法格式如下：
```python
os.fstat(fd)
```
#### **参数**
* fd -- 文件的描述符。

#### **返回值**
返回文件描述符fd的状态。

#### **实例**
以下实例演示了 fstat() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 打开文件
fd = os.open( "foo.txt", os.O_RDWR|os.O_CREAT )

# 获取元组
info = os.fstat(fd)

print ("文件信息 :", info)

# 获取文件 uid
print ("文件 UID :%d" % info.st_uid)

# 获取文件 gid
print ("文件 GID  :%d" % info.st_gid)

# 关闭文件
os.close( fd)
```
执行以上程序输出结果为：
```python 
文件信息 : (33261, 3753776L, 103L, 1, 0, 0, 
            102L, 1238783197, 1238786767, 1238786767)
文件 UID :0
文件 GID :0
```

---


### **Python3 os.fstatvfs() 方法**
#### **描述**
os.fstatvfs() 方法用于返回包含文件描述符fd的文件的文件系统的信息，Python 3.3 相等于 statvfs()。。

Unix上可用。
* fstatvfs 方法返回的结构:
* f_bsize: 文件系统块大小
* f_frsize: 分栈大小
* f_blocks: 文件系统数据块总数
* f_bfree: 可用块数
* f_bavail:非超级用户可获取的块数
* f_files: 文件结点总数
* f_ffree: 可用文件结点数
* f_favail: 非超级用户的可用文件结点数
* f_fsid: 文件系统标识 ID
* f_flag: 挂载标记
* f_namemax: 最大文件长度

#### **语法**
fstatvfs()方法语法格式如下：
```python
os.fstatvfs(fd)
```
#### **参数**
* fd -- 文件的描述符。

#### **返回值**
返回包含文件描述符fd的文件的文件系统的信息。
#### **实例**
以下实例演示了 fstatvfs() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 打开文件
fd = os.open( "foo.txt", os.O_RDWR|os.O_CREAT )

# 获取元组
info = os.fstatvfs(fd)

print ("文件信息 :", info)

# 获取文件名最大长度
print ("文件名最大长度 :%d" % info.f_namemax)

# 获取可用块数
print ("可用块数 :%d" % info.f_bfree)

# 关闭文件
os.close( fd)
```
执行以上程序输出结果为：
```python 
文件信息 : (4096, 4096, 2621440L, 1113266L, 1113266L, 
             8929602L, 8764252L, 8764252L, 0, 255)
文件名最大长度 :255
可用块数 :1113266
```


---



### **Python3 os.fsync() 方法**
#### **描述**
os.fsync() 方法强制将文件描述符为fd的文件写入硬盘。在Unix, 将调用fsync()函数;在Windows, 调用 _commit()函数。

如果你准备操作一个Python文件对象f, 首先f.flush(),然后os.fsync(f.fileno()), 确保与f相关的所有内存都写入了硬盘.在unix，Windows中有效。

Unix、Windows上可用。
#### **语法**
fsync()方法语法格式如下：
```python
os.fsync(fd)
```
#### **参数**
* fd -- 文件的描述符。

#### **返回值**

该方法没有返回值。
#### **实例**
以下实例演示了 fsync() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 打开文件
fd = os.open( "foo.txt", os.O_RDWR|os.O_CREAT )

# 写入字符串
os.write(fd, "This is test")

# 使用 fsync() 方法.
os.fsync(fd)

# 读取内容
os.lseek(fd, 0, 0)
str = os.read(fd, 100)
print ("读取的字符串为 : ", str)

# 关闭文件
os.close( fd)

print ("关闭文件成功!!")
```
执行以上程序输出结果为：
```python 
读取的字符串为 :  This is test
关闭文件成功!!
```


---



### **Python3 os.ftruncate() 方法**
#### **描述**
os.ftruncate() 裁剪文件描述符fd对应的文件, 它最大不能超过文件大小。

Unix上可用。
#### **语法**
ftruncate()方法语法格式如下：
```python
os.ftruncate(fd, length)
```
#### **参数**
* fd -- 文件的描述符。
* length -- 要裁剪文件大小。

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 ftruncate() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 打开文件
fd = os.open( "foo.txt", os.O_RDWR|os.O_CREAT )

# 写入字符串
os.write(fd, "This is test - This is test")

# 使用 ftruncate() 方法
os.ftruncate(fd, 10)

# 读取内容
os.lseek(fd, 0, 0)
str = os.read(fd, 100)
print ("读取的字符串是 : ", str)

# 关闭文件
os.close( fd)

print ("关闭文件成功!!")
```
执行以上程序输出结果为：
```python 
读取的字符串是 :  This is te
关闭文件成功!!
```


---



### **Python3 os.getcwd() 方法**
#### **描述**
os.getcwd() 方法用于返回当前工作目录。
#### **语法**
getcwd()方法语法格式如下：
```python
os.getcwd()
```
#### **参数**
* 无

#### **返回值**
返回当前进程的工作目录。

#### **实例**
以下实例演示了 getcwd() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 切换到 "/var/www/html" 目录
os.chdir("/var/www/html" )

# 打印当前目录
print ("当前工作目录 : %s" % os.getcwd())

# 打开 "/tmp"
fd = os.open( "/tmp", os.O_RDONLY )

# 使用 os.fchdir() 方法修改目录
os.fchdir(fd)

# 打印当前目录
print ("当前工作目录 : %s" % os.getcwd())

# 关闭文件
os.close( fd )
```
执行以上程序输出结果为：
```python 
当前工作目录 : /var/www/html
当前工作目录 : /tmp
```


---


### **Python3 os.getcwdu() 方法**
#### **描述**
os.getcwdu() 方法用于返回一个当前工作目录的Unicode对象。

Unix, Windows 系统下可用。
#### **语法**
getcwdu()方法语法格式如下：
```python
os.getcwdu()
```
#### **参数**
* 无

#### **返回值**
返回一个当前工作目录的Unicode对象。

#### **实例**
以下实例演示了 getcwdu() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 切换到 "/var/www/html" 目录
os.chdir("/var/www/html" )

# 打印当前目录
print ("当前工作目录 : %s" % os.getcwdu())

# 打开 "/tmp"
fd = os.open( "/tmp", os.O_RDONLY )

# 使用 os.fchdir() 方法修改目录
os.fchdir(fd)

# 打印当前目录
print ("当前工作目录 : %s" % os.getcwdu())

# 关闭文件
os.close( fd )
```
执行以上程序输出结果为：
```python 
当前工作目录 : /var/www/html
当前工作目录 : /tmp
```


---


### **Python3 os.isatty() 方法**
#### **描述**
os.isatty() 方法用于判断如果文件描述符fd是打开的，同时与tty(-like)设备相连，则返回true, 否则False。
#### **语法**
isatty()方法语法格式如下：
```python
os.isatty()
```
#### **参数**
* 无

#### **返回值**
如果文件描述符fd是打开的，同时与tty(-like)设备相连，则返回true, 否则False。

#### **实例**
以下实例演示了 isatty() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 打开文件
fd = os.open( "foo.txt", os.O_RDWR|os.O_CREAT )

# 写入字符串
str = "This is runoob.com site"
os.write(fd,bytes(str, 'UTF-8'))

# 使用 isatty() 查看文件
ret = os.isatty(fd)

print ("返回值: ", ret)

# 关闭文件
os.close( fd )
```
执行以上程序输出结果为：
```python 
返回值:  False
```


---


### **Python3 os.lchflags() 方法**
#### **描述**
os.lchflags() 方法用于设置路径的标记为数字标记，类似 chflags()，但是没有软链接。

只支持在 Unix 下使用。
#### **语法**
lchflags()方法语法格式如下：
```python
os.lchflags(path, flags)
```
#### **参数**
* path -- 设置标记的文件路径
* flags -- 可以由一个或多个标记组合，多个使用"|"隔开：
  * UF_NODUMP: 非转储文件
  * UF_IMMUTABLE: 文件是只读的
  * UF_APPEND: 文件只能追加内容
  * UF_NOUNLINK: 文件不可删除
  * UF_OPAQUE: 目录不透明，需要通过联合堆栈查看
  * SF_ARCHIVED: 可存档文件(超级用户可设)
  * SF_IMMUTABLE: 文件是只读的(超级用户可设)
  * SF_APPEND: 文件只能追加内容(超级用户可设)
  * SF_NOUNLINK: 文件不可删除(超级用户可设)
  * SF_SNAPSHOT: 快照文件(超级用户可设)

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 lchflags() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 打开文件
path = "/var/www/html/foo.txt"
fd = os.open( path, os.O_RDWR|os.O_CREAT )

# 关闭文件
os.close( fd )

# 修改文件标记
ret = os.lchflags(path, os.UF_IMMUTABLE )

print ("修改文件标记成功!!")
```
执行以上程序输出结果为：
```python 
修改文件标记成功!!
```


---


### **Python3 os.lchmod() 方法**
#### **描述**
os.lchmod() 方法用于修改连接文件权限。

只支持在 Unix 下使用。
#### **语法**
lchmod()方法语法格式如下：
```python
os.lchmod(path, mode)
```
#### **参数**
* path -- 设置标记的文件路径
* mode -- 可以是以下一个或多个组成，多个使用 "|" 隔开：
  * stat.S_ISUID:设置 UID 位
  * stat.S_ISGID: 设置组 ID 位
  * stat.S_ENFMT: 系统文件锁定的执法行动
  * stat.S_ISVTX: 在执行之后保存文字和图片
  * stat.S_IREAD: 对于拥有者读的权限
  * stat.S_IWRITE: 对于拥有者写的权限
  * stat.S_IEXEC: 对于拥有者执行的权限
  * stat.S_IRWXU:对于拥有者读、写、执行的权限
  * stat.S_IRUSR: 对于拥有者读的权限
  * stat.S_IWUSR: 对于拥有者写的权限
  * stat.S_IXUSR: 对于拥有者执行的权限
  * stat.S_IRWXG: 对于同组的人读写执行的权限
  * stat.S_IRGRP: 对于同组读的权限
  * stat.S_IWGRP:对于同组写的权限
  * stat.S_IXGRP: 对于同组执行的权限
  * stat.S_IRWXO: 对于其他组读写执行的权限
  * stat.S_IROTH: 对于其他组读的权限
  * stat.S_IWOTH: 对于其他组写的权限
  * stat.S_IXOTH:对于其他组执行的权限
#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 lchmod() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 打开文件
path = "/var/www/html/foo.txt"
fd = os.open( path, os.O_RDWR|os.O_CREAT )

# 关闭文件
os.close( fd )

# 修改文件权限
# 设置文件可以通过组执行
os.lchmod( path, stat.S_IXGRP)

# 设置文件可以被其他用户写入
os.lchmod("/tmp/foo.txt", stat.S_IWOTH)

print ("修改权限成功!!")
```
执行以上程序输出结果为：
```python 
修改权限成功!!
```


---


### **Python3 os.lchown() 方法**
#### **描述**
os.lchown() 方法用于更改文件所有者，类似 chown，但是不追踪链接。

只支持在 Unix 下使用。
#### **语法**
lchown()方法语法格式如下：
```python
os.lchown(path, uid, gid)
```
#### **参数**
* path -- 设置权限的文件路径
* uid -- 所属用户 ID
* gid -- 所属用户组 ID

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 lchown() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 打开文件
path = "/var/www/html/foo.txt"
fd = os.open( path, os.O_RDWR|os.O_CREAT )

# 关闭打开的文件
os.close( fd )

# 修改文件权限
# 设置文件所属用户 ID
os.lchown( path, 500, -1)

# 设置文件所属用户组 ID
os.lchown( path, -1, 500)

print ("修改权限成功!!")
```
执行以上程序输出结果为：
```python 
修改权限成功!!
```


---


### **Python3 os.link() 方法**
#### **描述**
os.link() 方法用于创建硬链接，名为参数 dst，指向参数 src。

该方法对于创建一个已存在文件的拷贝是非常有用的。

只支持在 Unix, Windows 下使用。
#### **语法**
link()方法语法格式如下：
```python
os.link(src, dst)
```
#### **参数**
* src -- 用于创建硬连接的源地址
* dst -- 用于创建硬连接的目标地址

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 link() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 打开文件
path = "/var/www/html/foo.txt"
fd = os.open( path, os.O_RDWR|os.O_CREAT )

# 关闭文件
os.close( fd )

# 创建以上文件的拷贝
dst = "/tmp/foo.txt"
os.link( path, dst)

print ("创建硬链接成功!!")
```
执行以上程序输出结果为：
```python 
创建硬链接成功!!
```


---


### **Python3 os.listdir() 方法**
#### **描述**
os.listdir() 方法用于返回指定的文件夹包含的文件或文件夹的名字的列表。这个列表以字母顺序。 它不包括 '.' 和'..' 即使它在文件夹中。

只支持在 Unix, Windows 下使用。
#### **语法**
listdir()方法语法格式如下：
```python
os.listdir(path)
```
#### **参数**
* path -- 需要列出的目录路径

#### **返回值**
返回指定路径下的文件和文件夹列表。

#### **实例**
以下实例演示了 listdir() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 打开文件
path = "/var/www/html/"
dirs = os.listdir( path )

# 输出所有文件和文件夹
for file in dirs:
    print (file)
```
执行以上程序输出结果为：
```python 
test.htm
stamp
faq.htm
_vti_txt
robots.txt
itemlisting
resumelisting
writing_effective_resume.htm
advertisebusiness.htm
papers
resume
```


---


### **Python3 os.lseek() 方法**
#### **描述**
os.lseek() 方法用于设置文件描述符 fd 当前位置为 pos, how 方式修改。

在Unix，Windows中有效。
#### **语法**
lseek()方法语法格式如下：
```python
os.lseek(fd, pos, how)
```
#### **参数**
* fd -- 文件描述符。
* pos -- 这是相对于给定的参数 how 在文件中的位置。。
* how -- 文件内参考位置。SEEK_SET 或者 0 设置从文件开始的计算的pos; SEEK_CUR或者 1 则从当前位置计算; os.SEEK_END或者2则从文件尾部开始。

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 lseek() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 打开文件
fd = os.open( "foo.txt", os.O_RDWR|os.O_CREAT )

# 写入字符串
os.write(fd, "This is test")

# 所有 fsync() 方法
os.fsync(fd)

# 从开始位置读取字符串
os.lseek(fd, 0, 0)
str = os.read(fd, 100)
print ("Read String is : ", str)

# 关闭文件
os.close( fd )

print ("关闭文件成功!!")
```
执行以上程序输出结果为：
```python 
关闭文件成功!!
```


---


### **Python3 os.lstat() 方法**
#### **描述**
os.lstat() 方法用于类似 stat() 返回文件的信息,但是没有符号链接。在某些平台上，这是fstat的别名，例如 Windows。
#### **语法**
lstat()方法语法格式如下：
```python
os.lstat(path)
```
#### **参数**
* path -- 要返回信息的文件。

#### **返回值**
返回文件信息。

#### **实例**
以下实例演示了 lstat() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 打开文件
path = "/var/www/html/foo.txt"
fd = os.open( path, os.O_RDWR|os.O_CREAT )

# 关闭打开的文件
os.close( fd )

# 获取元组
info = os.lstat(path)

print ("文件信息 :", info)

# 获取文件 uid
print ("文件 UID  :%d" % info.st_uid)

# 获取文件 gid
print ("文件 GID :%d" % info.st_gid)
```
执行以上程序输出结果为：
```python 
文件信息 : (33261, 3450178L, 103L, 1, 500, 500, 0L, 
             1238866944, 1238866944, 1238948312)
文件 UID :500
文件 GID :500
```


---


### **Python3 os.major() 方法**
#### **描述**
os.major() 方法用于从原始的设备号中提取设备major号码 (使用stat中的st_dev或者st_rdev field)。
#### **语法**
major()方法语法格式如下：
```python
os.major(device)
```
#### **参数**
* device -- 原始的设备号中提取设备major号码 (使用stat中的st_dev或者st_rdev field)。

#### **返回值**
返回设备major号码。

#### **实例**
以下实例演示了 major() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

path = "/var/www/html/foo.txt"

# 获取元组
info = os.lstat(path)

# 获取 major 和 minor 设备号
major_dnum = os.major(info.st_dev)
minor_dnum = os.minor(info.st_dev)

print ("Major 设备号 :", major_dnum)
print ("Minor 设备号 :", minor_dnum)
```
执行以上程序输出结果为：
```python 
Major 设备号 : 0
Minor 设备号 : 103
```


---


### **Python3 os.makedev() 方法**
#### **描述**
os.makedev() 方法用于以major和minor设备号组成一个原始设备号。
#### **语法**
makedev()方法语法格式如下：
```python
os.makedev(major, minor)
```
#### **参数**
* major -- Major 设备号。
* minor -- inor 设备号。

#### **返回值**
返回设备号。

#### **实例**
以下实例演示了 makedev() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

path = "/var/www/html/foo.txt"

# 获取元组
info = os.lstat(path)

# 获取 major 和 minor 设备号
major_dnum = os.major(info.st_dev)
minor_dnum = os.minor(info.st_dev)

print ("Major 设备号 :", major_dnum)
print ("Minor 设备号 :", minor_dnum)

# 生成设备号
dev_num = os.makedev(major_dnum, minor_dnum)
print ("设备号 :", dev_num)
```
执行以上程序输出结果为：
```python 
Major 设备号 : 0
Minor 设备号 : 103
设备号 : 103
```


---


### **Python3 os.makedirs() 方法**
#### **描述**
os.makedirs() 方法用于递归创建目录。像 mkdir(), 但创建的所有intermediate-level文件夹需要包含子目录。
#### **语法**
makedirs()方法语法格式如下：
```python
os.makedirs(path, mode=0o777)
```
#### **参数**
* path -- 需要递归创建的目录。
* mode -- 权限模式。

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 makedirs() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 创建的目录
path = "/tmp/home/monthly/daily"

os.makedirs( path, 0o777 );

print ("路径被创建")
```
执行以上程序输出结果为：
```python 
路径被创建
```


---


### **Python3 os.minor() 方法**
#### **描述**
os.minor() 方法用于从原始的设备号中提取设备minor号码 (使用stat中的st_dev或者st_rdev field )。
#### **语法**
minor()方法语法格式如下：
```python
os.minor(device)
```
#### **参数**
* device -- 原始的设备(使用stat中的st_dev或者st_rdev field )

#### **返回值**
返回设备 minor 号。

#### **实例**
以下实例演示了 minor() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

path = "/var/www/html/foo.txt"

# 获取元组
info = os.lstat(path)

# 获取 major 和 minor 设备号
major_dnum = os.major(info.st_dev)
minor_dnum = os.minor(info.st_dev)

print ("Major 设备号 :", major_dnum)
print ("Minor 设备号 :", minor_dnum)
```
执行以上程序输出结果为：
```python 
Major 设备号 : 0
Minor 设备号 : 103
```


---


### **Python3 os.mkdir() 方法**
#### **描述**
os.mkdir() 方法用于以数字权限模式创建目录。默认的模式为 0777 (八进制)。
#### **语法**
mkdir()方法语法格式如下：
```python
os.mkdir(path[, mode])
```
#### **参数**
* path -- 要创建的目录
* mode -- 要为目录设置的权限数字模式

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 mkdir() 方法的使用：
```python 
#!/usr/bin/python
# -*- coding: UTF-8 -*-

import os, sys

# 创建的目录
path = "/tmp/home/monthly/daily/hourly"

os.mkdir( path, 0755 )

print ("目录已创建")
```
执行以上程序输出结果为：
```python 
目录已创建
```


---


### **Python3 os.mkfifo() 方法**
#### **描述**
os.mkfifo() 方法用于创建指令路径的管道，并设置权限模式。默认的模式为 0666 (八进制)。
#### **语法**
mkfifo()方法语法格式如下：
```python
os.mkfifo(path[, mode])
```
#### **参数**
* path -- 要创建的目录
* mode -- 要为目录设置的权限数字模式

#### **返回值**

该方法没有返回值。
#### **实例**
以下实例演示了 mkfifo() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 创建的目录
path = "/tmp/hourly"

os.mkfifo( path, 0644 )

print ("路径被创建")
```
执行以上程序输出结果为：
```python 
路径被创建
```


---


### **Python3 os.mknod() 方法**
#### **描述**
os.mknod() 方法用于创建一个指定文件名的文件系统节点（文件，设备特别文件或者命名pipe）。
#### **语法**
mknod()方法语法格式如下：
```python
os.mknod(filename[, mode=0600[, device=0]])
```
#### **参数**
* filename -- 创建的文件系统节点
* mode -- mode指定创建或使用节点的权限, 组合 (或者bitwise) stat.S_IFREG, stat.S_IFCHR, stat.S_IFBLK, 和stat.S_IFIFO (这些常数在stat模块). 对于 stat.S_IFCHR和stat.S_IFBLK, 设备定义了 最新创建的设备特殊文件 (可能使用 os.makedev()),其它都将忽略。
* device -- 可选，指定创建文件的设备

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 mknod() 方法的使用：
```python 
#!/usr/bin/python3

import os
import stat

filename = '/tmp/tmpfile'
mode = 0600|stat.S_IRUSR

# 文件系统节点指定不同模式
os.mknod(filename, mode)
```
执行以上程序输出结果为：
```python 
-rw-------. 1 root   root         0 Apr 30 02:38 tmpfile
```


---


### **Python3 os.open() 方法**
#### **描述**
os.open() 方法用于打开一个文件，并且设置需要的打开选项，模式参数mode参数是可选的，默认为 0777。
#### **语法**
open()方法语法格式如下：
```python
os.open(file, flags[, mode]);
```
#### **参数**
* file -- 要打开的文件
* flags -- 该参数可以是以下选项，多个使用 "|" 隔开：
  * os.O_RDONLY: 以只读的方式打开
  * os.O_WRONLY: 以只写的方式打开
  * os.O_RDWR : 以读写的方式打开
  * os.O_NONBLOCK: 打开时不阻塞
  * os.O_APPEND: 以追加的方式打开
  * os.O_CREAT: 创建并打开一个新文件
  * os.O_TRUNC: 打开一个文件并截断它的长度为零（必须有写权限）
  * os.O_EXCL: 如果指定的文件存在，返回错误
  * os.O_SHLOCK: 自动获取共享锁
  * os.O_EXLOCK: 自动获取独立锁
  * os.O_DIRECT: 消除或减少缓存效果
  * os.O_FSYNC : 同步写入
  * os.O_NOFOLLOW: 不追踪软链接
* mode -- 类似 chmod()。


#### **返回值**
返回新打开文件的描述符。

#### **实例**
以下实例演示了 open() 方法的使用：
```python 
#!/usr/bin/python3
  
import os, sys

# 打开文件
fd = os.open( "foo.txt", os.O_RDWR|os.O_CREAT )

# 写入字符串
os.write(fd, str.encode("This is test"))

# 关闭文件
os.close( fd )

print ("关闭文件成功!!")
```
执行以上程序输出结果为：
```python 
关闭文件成功!!
```


---


### **Python3 os.openpty() 方法**
#### **描述**
os.openpty() 方法用于打开一个新的伪终端对。返回 pty 和 tty的文件描述符。
#### **语法**
openpty()方法语法格式如下：
```python
os.openpty()
```
#### **参数**
* 无

#### **返回值**
返回文件描述符对，主从。

#### **实例**
以下实例演示了 openpty() 方法的使用：
```python 
#!/usr/bin/python3

import os

# 主 pty, 从 tty
m,s = os.openpty()

print (m)
print (s)

# 显示终端名
s = os.ttyname(s)
print (m)
print (s)
```
执行以上程序输出结果为：
```python 
3
4
3
/dev/pty0
```


---


### **Python3 os.pathconf() 方法**
#### **描述**
os.pathconf() 方法用于返回一个打开的文件的系统配置信息。

Unix 平台下可用。
#### **语法**
fpathconf()方法语法格式如下：
```python
os.fpathconf(fd, name)
```
#### **参数**
* fd -- 文件描述符
* name -- 检索的系统配置的值，它也许是一个定义系统值的字符串，这些名字在很多标准中指定（POSIX.1, Unix 95, Unix 98, 和其它）。一些平台也定义了一些额外的名字。这些名字在主操作系统上pathconf_names的字典中。对于不在pathconf_names中的配置变量，传递一个数字作为名字，也是可以接受的。

#### **返回值**
返回文件的系统信息。

#### **实例**
以下实例演示了 fpathconf() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 打开文件
fd = os.open( "foo.txt", os.O_RDWR|os.O_CREAT )

print ("%s" % os.pathconf_names)

# 获取文件最大连接数
no = os.fpathconf(fd, 'PC_LINK_MAX')
print ("Maximum number of links to the file. :%d" % no)

# 获取文件名最大长度
no = os.fpathconf(fd, 'PC_NAME_MAX')
print ("Maximum length of a filename :%d" % no)

# 关闭文件
os.close( fd)

print ("关闭文件成功!!")
```
执行以上程序输出结果为：
```python 
关闭文件成功!!
```


---


### **Python3 os.pipe() 方法**
#### **描述**
os.pipe() 方法用于创建一个管道, 返回一对文件描述符(r, w) 分别为读和写。
#### **语法**
pipe()方法语法格式如下：
```python
os.pipe()
```
#### **参数**
* 无

#### **返回值**
返回文件描述符对。

#### **实例**
以下实例演示了 pipe() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

print ("The child will write text to a pipe and ")
print ("the parent will read the text written by child...")

# 文件描述符 r, w 用于读、写
r, w = os.pipe() 

processid = os.fork()
if processid:
    # 父进程
    # 关闭文件描述符 w
    os.close(w)
    r = os.fdopen(r)
    print ("Parent reading")
    str = r.read()
    print ("text =", str)
    sys.exit(0)
else:
    # 子进程
    os.close(r)
    w = os.fdopen(w, 'w')
    print ("Child writing")
    w.write("Text written by child...")
    w.close()
    print ("Child closing")
    sys.exit(0)
```
执行以上程序输出结果为：
```python 
The child will write text to a pipe and
the parent will read the text written by child...
Parent reading
Child writing
Child closing
text = Text written by child...
```


---


### **Python3 os.popen() 方法**
#### **描述**
os.popen() 方法用于从一个命令打开一个管道。

在Unix，Windows中有效
#### **语法**
popen()方法语法格式如下：
```python
os.popen(command[, mode[, bufsize]])
```
#### **参数**
* command -- 使用的命令。
* mode -- 模式权限可以是 'r'(默认) 或 'w'。
* bufsize -- 指明了文件需要的缓冲大小：0意味着无缓冲；1意味着行缓冲；其它正值表示使用参数大小的缓冲（大概值，以字节为单位）。负的bufsize意味着使用系统的默认值，一般来说，对于tty设备，它是行缓冲；对于其它文件，它是全缓冲。如果没有改参数，使用系统的默认值。

#### **返回值**
返回一个文件描述符号为fd的打开的文件对象

#### **实例**
以下实例演示了 popen() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 使用 mkdir 命令
a = 'mkdir nwdir'

b = os.popen(a,'r',1)

print (b)
```
执行以上程序输出结果为：
```python 
open file 'mkdir nwdir', mode 'r' at 0x81614d0
```


---


### **Python3 os.read() 方法**
#### **描述**
os.read() 方法用于从文件描述符 fd 中读取最多 n 个字节，返回包含读取字节的字符串，文件描述符 fd对应文件已达到结尾, 返回一个空字符串。

在Unix，Windows中有效
#### **语法**
read()方法语法格式如下：
```python
os.read(fd,n)
```
#### **参数**
* fd -- 文件描述符。
* n -- 读取的字节。

#### **返回值**
返回包含读取字节的字符串

#### **实例**
以下实例演示了 read() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys
# 打开文件
fd = os.open("f1.txt",os.O_RDWR)
   
# 读取文本
ret = os.read(fd,12)
print (ret)

# 关闭文件
os.close(fd)
print ("关闭文件成功!!")
```
执行以上程序输出结果为：
```python 
This is test
关闭文件成功!!
```


---


### **Python3 os.readlink() 方法**
#### **描述**
os.readlink() 方法用于返回软链接所指向的文件，可能返回绝对或相对路径。

在Unix中有效
#### **语法**
readlink()方法语法格式如下：
```python
os.readlink(path)
```
#### **参数**
* path -- 要查找的软链接路径

#### **返回值**
返回软链接所指向的文件

#### **实例**
以下实例演示了 readlink() 方法的使用：
```python 
#!/usr/bin/python3

import os

src = '/usr/bin/python'
dst = '/tmp/python'

# 创建软链接
os.symlink(src, dst)

# 使用软链接显示源链接
path = os.readlink( dst )
print (path)
```
执行以上程序输出结果为：
```python 
/usr/bin/python
```


---


### **Python3 os.remove() 方法**
#### **描述**
os.remove() 方法用于删除指定路径的文件。如果指定的路径是一个目录，将抛出OSError。

在Unix, Windows中有效
#### **语法**
remove()方法语法格式如下：
```python
os.remove(path)
```
#### **参数**
* path -- 要移除的文件路径

#### **返回值**
该方法没有返回值

#### **实例**
以下实例演示了 remove() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 列出目录
print ("目录为: %s" %os.listdir(os.getcwd()))

# 移除
os.remove("aa.txt")

# 移除后列出目录
print ("移除后 : %s" %os.listdir(os.getcwd()))
```
执行以上程序输出结果为：
```python 
目录为:
[ 'a1.txt','aa.txt','resume.doc' ]
移除后 : 
[ 'a1.txt','resume.doc' ]
```


---


### **Python3 os.removedirs() 方法**
#### **描述**
os.removedirs() 方法用于递归删除目录。像rmdir(), 如果子文件夹成功删除, removedirs()才尝试它们的父文件夹,直到抛出一个error(它基本上被忽略,因为它一般意味着你文件夹不为空)。
#### **语法**
removedirs()方法语法格式如下：
```python
os.removedirs(path)
```
#### **参数**
* path -- 要移除的目录路径

#### **返回值**
该方法没有返回值

#### **实例**
以下实例演示了 removedirs() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 列出目录
print ("目录为: %s" %os.listdir(os.getcwd()))

# 移除
os.removedirs("/test")

# 列出移除后的目录
print ("移除后目录为:" %os.listdir(os.getcwd()))
```
执行以上程序输出结果为：
```python 
目录为:
[  'a1.txt','resume.doc','a3.py','test' ]
移除后目录为:
[  'a1.txt','resume.doc','a3.py' ]
```


---


### **Python3 os.rename() 方法**
#### **描述**
os.rename() 方法用于命名文件或目录，从 src 到 dst,如果dst是一个存在的目录, 将抛出OSError。
#### **语法**
rename()方法语法格式如下：
```python
os.rename(src, dst)
```
#### **参数**
* src -- 要修改的目录名
* dst -- 修改后的目录名

#### **返回值**
该方法没有返回值

#### **实例**
以下实例演示了 rename() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 列出目录
print ("目录为: %s"%os.listdir(os.getcwd()))

# 重命名
os.rename("test","test2")

print ("重命名成功。")

# 列出重命名后的目录
print ("目录为: %s" %os.listdir(os.getcwd()))
```
执行以上程序输出结果为：
```python 
目录为:
[  'a1.txt','resume.doc','a3.py','test' ]
重命名成功。
[  'a1.txt','resume.doc','a3.py','test2' ]
```


---


### **Python3 os.renames() 方法**
#### **描述**
os.renames() 方法用于递归重命名目录或文件。类似rename()。
#### **语法**
renames()方法语法格式如下：
```python
os.renames(old, new)
```
#### **参数**
* old -- 要重命名的目录
* new --文件或目录的新名字。甚至可以是包含在目录中的文件，或者完整的目录树。

#### **返回值**
该方法没有返回值

#### **实例**
以下实例演示了 renames() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys
print ("当前目录为: %s" %os.getcwd())

# 列出目录
print ("目录为: %s"%os.listdir(os.getcwd()))

# 重命名 "aa1.txt"
os.renames("aa1.txt","newdir/aanew.txt")

print ("重命名成功。")

# 列出重命名的文件 "aa1.txt"
print ("目录为: %s" %os.listdir(os.getcwd()))
```
执行以上程序输出结果为：

```python 
当前目录为: /tmp
目录为:
 [  'a1.txt','resume.doc','a3.py','aa1.txt','Administrator','newdir','amrood.admin' ]
重命名成功。
目录为:
 [  'a1.txt','resume.doc','a3.py','Administrator','newdir','amrood.admin' ]
```


---


### **Python3 os.rmdir() 方法**
#### **描述**
os.rmdir() 方法用于删除指定路径的目录。仅当这文件夹是空的才可以, 否则, 抛出OSError。
#### **语法**
rmdir()方法语法格式如下：
```python
os.rmdir(path)
```
#### **参数**
* path -- 要删除的目录路径

#### **返回值**
该方法没有返回值

#### **实例**
以下实例演示了 rmdir() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 列出目录
print ("目录为: %s"%os.listdir(os.getcwd()))

# 删除路径
os.rmdir("mydir")

# 列出重命名后的目录
print ("目录为: %s" %os.listdir(os.getcwd()))
```
执行以上程序输出结果为：
```python 
目录为:
[  'a1.txt','resume.doc','a3.py','mydir' ]
目录为:
[  'a1.txt','resume.doc','a3.py' ]
```


---


### **Python3 os.stat() 方法**
#### **描述**
os.stat() 方法用于在给定的路径上执行一个系统 stat 的调用。
#### **语法**
stat()方法语法格式如下：
```python
os.stat(path)
```
#### **参数**
* path -- 指定路径

#### **返回值**
stat 结构:
* st_mode: inode 保护模式
* st_ino: inode 节点号。
* st_dev: inode 驻留的设备。
* st_nlink: inode 的链接数。
* st_uid: 所有者的用户ID。
* st_gid: 所有者的组ID。
* st_size: 普通文件以字节为单位的大小；包含等待某些特殊文件的数据。
* st_atime: 上次访问的时间。
* st_mtime: 最后一次修改的时间。
* st_ctime: 由操作系统报告的"ctime"。在某些系统上（如Unix）是最新的元数据更改的时间，在其它系统上（如Windows）是创建时间（详细信息参见平台的文档）。

#### **实例**
以下实例演示了 stat() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 显示文件 "a2.py" 信息
statinfo = os.stat('a2.py')

print (statinfo)
```
执行以上程序输出结果为：
```python 
posix.stat_result(st_mode=33188, st_ino=3940649674337682L, st_dev=277923425L, st
_nlink=1, st_uid=400, st_gid=401, st_size=335L, st_atime=1330498089, st_mtime=13
30498089, st_ctime=1330498089)
```


---


### **Python3 os.stat_float_times() 方法**
#### **描述**
os.stat_float_times() 方法用于决定stat_result是否以float对象显示时间戳。
#### **语法**
stat_float_times()方法语法格式如下：
```python
os.stat_float_times([newvalue])
```
#### **参数**
* newvalue -- 如果为 True, 调用 stat() 返回 floats,如果 False, 调用 stat 返回 ints。如果没有该参数返回当前设置。

#### **返回值**
返回 True 或 False。

#### **实例**
以下实例演示了 stat_float_times() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# Stat 信息
statinfo = os.stat('a2.py')

print (statinfo)
statinfo = os.stat_float_times()
print (statinfo)
```
执行以上程序输出结果为：
```python 
posix.stat_result(st_mode=33188, st_ino=3940649674337682L, st_dev=277923425L, 
st_nlink=1, st_uid=400, st_gid=401, st_size=335L, st_atime=1330498089, st_mtime=13
30498089, st_ctime=1330498089)
True
```


---


### **Python3 os.statvfs() 方法**
#### **描述**
os.statvfs() 方法用于返回包含文件描述符fd的文件的文件系统的信息。
#### **语法**
statvfs()方法语法格式如下：
```python
os.statvfs([path])
```
#### **参数**
* path -- 文件路径。

#### **返回值**
返回的结构:
* f_bsize: 文件系统块大小
* f_frsize: 分栈大小
* f_blocks: 文件系统数据块总数
* f_bfree: 可用块数
* f_bavail:非超级用户可获取的块数
* f_files: 文件结点总数
* f_ffree: 可用文件结点数
* f_favail: 非超级用户的可用文件结点数
* f_fsid: 文件系统标识 ID
* f_flag: 挂载标记
* f_namemax: 最大文件长度

#### **实例**
以下实例演示了 statvfs() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 显示 "a1.py" 文件的 statvfs 信息
stinfo = os.statvfs('a1.py')

print (stinfo)
```
执行以上程序输出结果为：
```python 
posix.statvfs_result(f_bsize=4096, f_frsize=4096, f_blocks=1909350L, f_bfree=1491513L,
f_bavail=1394521L, f_files=971520L, f_ffree=883302L, f_fvail=883302L, f_flag=0,
f_namemax=255)
```


---


### **Python3 os.symlink() 方法**
#### **描述**
os.symlink() 方法用于创建一个软链接。
#### **语法**
symlink()方法语法格式如下：
```python
os.symlink(src, dst)
```
#### **参数**
* src -- 源地址。
* dst -- 目标地址。

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 symlink() 方法的使用：
```python 
#!/usr/bin/python3

import os

src = '/usr/bin/python'
dst = '/tmp/python'

# 创建软链接
os.symlink(src, dst)

print ("软链接创建成功")
```
执行以上程序输出结果为：
```python 
软链接创建成功
```


---


### **Python3 os.tcgetpgrp() 方法**
#### **描述**
os.tcgetpgrp() 方法用于回与终端fd（一个由os.open()返回的打开的文件描述符）关联的进程组。
#### **语法**
tcgetpgrp()方法语法格式如下：
```python
os.tcgetpgrp(fd)
```
#### **参数**
* fd -- 文件描述符。

#### **返回值**
该方法返回进程组。

#### **实例**
以下实例演示了 tcgetpgrp() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 显示当前目录
print ("当前目录 :%s" %os.getcwd())

# 修改目录到 /dev/tty
fd = os.open("/dev/tty",os.O_RDONLY)

f = os.tcgetpgrp(fd)

# 显示进程组
print ("相关进程组: ")
print (f)

os.close(fd)
print ("关闭文件成功!!")
```
执行以上程序输出结果为：
```python 
当前目录 :/tmp
相关进程组:
2670
关闭文件成功!!
```


---


### **Python3 os.ttyname() 方法**
#### **描述**
os.ttyname() 方法用于返回一个字符串，它表示与文件描述符fd 关联的终端设备。如果fd 没有与终端设备关联，则引发一个异常。
#### **语法**
ttyname()方法语法格式如下：
```python
os.ttyname(fd)
```
#### **参数**
* fd -- 文件描述符

#### **返回值**
返回一个字符串，它表示与文件描述符fd 关联的终端设备。

#### **实例**
以下实例演示了 ttyname() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 显示当前目录
print ("当前目录 :%s" %os.getcwd())

# 修改目录为 /dev/tty
fd = os.open("/dev/tty",os.O_RDONLY)

p = os.ttyname(fd)
print ("关联的终端为: ")
print (p)
print ("done!!")

os.close(fd)
print ("关闭文件成功!!")
```
执行以上程序输出结果为：
```python 
当前目录 :/tmp
关联的终端为:
/dev/tty
done!!
关闭文件成功!!
```


---


### **Python3 os.unlink() 方法**
#### **描述**
os.unlink() 方法用于删除文件,如果文件是一个目录则返回一个错误。
#### **语法**
unlink()方法语法格式如下：
```python
os.unlink(path)
```
#### **参数**
* path -- 删除的文件路径

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 unlink() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 列出目录
print ("目录为: %s" %os.listdir(os.getcwd()))

os.unlink("aa.txt")

# 删除后的目录
print ("删除后的目录为 : %s" %os.listdir(os.getcwd()))
```
执行以上程序输出结果为：
```python 
目录为:
 [ 'a1.txt','aa.txt','resume.doc']
删除后的目录为 : 
[ 'a1.txt','resume.doc' ]
```


---


### **Python3 os.utime() 方法**
#### **描述**
os.utime() 方法用于设置指定路径文件最后的修改和访问时间。

在Unix，Windows中有效。
#### **语法**
utime()方法语法格式如下：
```python
os.utime(path, times)
```
#### **参数**
* path -- 文件路径
* times -- 如果时间是 None, 则文件的访问和修改设为当前时间 。 否则, 时间是一个 2-tuple数字, (atime, mtime) 用来分别作为访问和修改的时间。

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 utime() 方法的使用：
```python 
#!/usr/bin/python
# -*- coding: UTF-8 -*-

import os, sys

# 显示文件的 stat 信息
stinfo = os.stat('a2.py')
print (stinfo)

# 使用 os.stat 来接收文件的访问和修改时间
print ("a2.py 的访问时间: %s" %stinfo.st_atime)
print ("a2.py 的修改时间: %s" %stinfo.st_mtime)

# 修改访问和修改时间
os.utime("a2.py",(1330712280, 1330712292))
print ("done!!")
```
执行以上程序输出结果为：
```python 
posix.stat_result(st_mode=33188, st_ino=3940649674337682L, st_dev=277923425L, st
_nlink=1, st_uid=400, st_gid=401, st_size=335L, st_atime=1330498070, st_mtime=13
30498074, st_ctime=1330498065)
a2.py 的访问时间: 1330498070
a2.py 的修改时间: 1330498074
done!!
```


---


### **Python3 os.walk() 方法**
#### **描述**
os.walk() 方法用于通过在目录树种游走输出在目录中的文件名，向上或者向下。

在Unix，Windows中有效。
#### **语法**
walk()方法语法格式如下：
```python
os.walk(top[, topdown=True[, onerror=None[, followlinks=False]]])
```
#### **参数**
* top -- 根目录下的每一个文件夹(包含它自己), 产生3-元组 (dirpath, dirnames, filenames)【文件夹路径, 文件夹名字, 文件名】。
* topdown --可选，为True或者没有指定, 一个目录的的3-元组将比它的任何子文件夹的3-元组先产生 (目录自上而下)。如果topdown为 False, 一个目录的3-元组将比它的任何子文件夹的3-元组后产生 (目录自下而上)。
* onerror -- 可选，是一个函数; 它调用时有一个参数, 一个OSError实例。报告这错误后，继续walk,或者抛出exception终止walk。
* followlinks -- 设置为 true，则通过软链接访问目录。

#### **返回值**
该方法没有返回值。

#### **实例**
以下实例演示了 walk() 方法的使用：
```python 
#!/usr/bin/python3

import os
for root, dirs, files in os.walk(".", topdown=False):
    for name in files:
        print(os.path.join(root, name))
    for name in dirs:
        print(os.path.join(root, name))
```
执行以上程序输出结果为：
```python 
./.bash_logout
./amrood.tar.gz
./.emacs
./httpd.conf
./www.tar.gz
./mysql.tar.gz
./test.py
./.bashrc
./.bash_history
./.bash_profile
./tmp
./tmp/test.py
```


---


### **Python3 os.write() 方法**
#### **描述**
os.write() 方法用于写入字符串到文件描述符 fd 中. 返回实际写入的字符串长度。

在Unix中有效。
#### **语法**
write()方法语法格式如下：
```python
os.write(fd, str)
```
#### **参数**
* fd -- 文件描述符。
* str -- 写入的字符串。

#### **返回值**
该方法返回写入的实际位数。

#### **实例**
以下实例演示了 write() 方法的使用：
```python 
#!/usr/bin/python3

import os, sys

# 打开文件
fd = os.open("f1.txt",os.O_RDWR|os.O_CREAT)

# 写入字符串
str = "This is runoob.com site"
ret = os.write(fd,bytes(str, 'UTF-8'))

# 输入返回值
print ("写入的位数为: ")
print (ret)

print ("写入成功")

# 关闭文件
os.close(fd)
print ("关闭文件成功!!")
```
执行以上程序输出结果为：
```python 
写入的位数为: 
23
写入成功
关闭文件成功!!
```


---


### **Python3 os.path() 模块**
#### **描述**
os.path 模块主要用于获取文件的属性。

以下是 os.path 模块的几种常用方法：

![](/image/23-12.png)

![](/image/23-13.png)

![](/image/23-14.png)




#### **实例**
以下实例演示了 os.path 相关方法的使用：
```python 
#!/usr/bin/python3
 
import os
 
print( os.path.basename('/root/runoob.txt') )   # 返回文件名
print( os.path.dirname('/root/runoob.txt') )    # 返回目录路径
print( os.path.split('/root/runoob.txt') )      # 分割文件名与路径
print( os.path.join('root','test','runoob.txt') )  # 将目录和文件名合成一个路径
```
执行以上程序输出结果为：
```python 
runoob.txt
/root
('/root', 'runoob.txt')
root/test/runoob.txt
```
以下实例输出文件的相关信息。
```python 
import os
import time
 
file='/root/runoob.txt' # 文件路径
 
print( os.path.getatime(file) )   # 输出最近访问时间
print( os.path.getctime(file) )   # 输出文件创建时间
print( os.path.getmtime(file) )   # 输出最近修改时间
print( time.gmtime(os.path.getmtime(file)) )  # 以struct_time形式输出最近修改时间
print( os.path.getsize(file) )   # 输出文件大小（字节为单位）
print( os.path.abspath(file) )   # 输出绝对路径
print( os.path.normpath(file) )  # 规范path字符串形式
```
执行以上程序输出结果为：
```python 
1539052805.5735736
1539052805.5775735
1539052805.5735736
time.struct_time(tm_year=2018, tm_mon=10, tm_mday=9, tm_hour=2, tm_min=40, tm_sec=5, tm_wday=1, tm_yday=282, tm_isdst=0)
7
/root/runoob.txt
/root/runoob.txt
```


---

