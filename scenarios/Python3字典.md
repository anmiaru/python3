## **Python3字典**
字典是另一种可变容器模型，且可存储任意类型对象。  
字典的每个键值(key=>value)对用冒号(:)分割，每个对之间用逗号(,)分割，整个字典包括在花括号({})中 ,格式如下所示：
```python
d = {key1 : value1, key2 : value2 }
```

键必须是唯一的，但值则不必。  
值可以取任何数据类型，但键必须是不可变的，如字符串，数字或元组。  
一个简单的字典实例：
```python
dict = {'Alice': '2341', 'Beth': '9102', 'Cecil': '3258'}
```
也可如此创建字典：
```python
dict1 = { 'abc': 456 }
dict2 = { 'abc': 123, 98.6: 37 }
```
---

### **访问字典里的值**
把相应的键放入到方括号中，如下实例:
```python
#!/usr/bin/python3
 
dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
 
print ("dict['Name']: ", dict['Name'])
print ("dict['Age']: ", dict['Age'])
```

以上实例输出结果：
```python
dict['Name']:  Runoob
dict['Age']:  7
```

如果用字典里没有的键访问数据，会输出错误如下：
```python
#!/usr/bin/python3
 
dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
 
print ("dict['Alice']: ", dict['Alice'])
```

以上实例输出结果：
```python
Traceback (most recent call last):
  File "test.py", line 5, in <module>
    print ("dict['Alice']: ", dict['Alice'])
KeyError: 'Alice'
```


---

### **修改字典**
向字典添加新内容的方法是增加新的键/值对，修改或删除已有键/值对如下实例:
```python
#!/usr/bin/python3
 
dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
 
dict['Age'] = 8               # 更新 Age
dict['School'] = "菜鸟教程"  # 添加信息
 
 
print ("dict['Age']: ", dict['Age'])
print ("dict['School']: ", dict['School'])
```

以上实例输出结果：
```python
dict['Age']:  8
dict['School']:  菜鸟教程
```


---

### **删除字典元素**
能删单一的元素也能清空字典，清空只需一项操作。  
显示删除一个字典用del命令，如下实例：
```python
#!/usr/bin/python3
 
dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
 
del dict['Name'] # 删除键 'Name'
dict.clear()     # 清空字典
del dict         # 删除字典
 
print ("dict['Age']: ", dict['Age'])
print ("dict['School']: ", dict['School'])
```

但这会引发一个异常，因为用执行 del 操作后字典不再存在：
```python
Traceback (most recent call last):
  File "test.py", line 9, in <module>
    print ("dict['Age']: ", dict['Age'])
TypeError: 'type' object is not subscriptable
```
**注**：del() 方法后面也会讨论。

---

### **字典键的特性**
字典值可以是任何的 python 对象，既可以是标准的对象，也可以是用户定义的，但键不行。   
两个重要的点需要记住：  
1）不允许同一个键出现两次。创建时如果同一个键被赋值两次，后一个值会被记住，如下实例：
```python
#!/usr/bin/python3
 
dict = {'Name': 'Runoob', 'Age': 7, 'Name': '小菜鸟'}
 
print ("dict['Name']: ", dict['Name'])
```

以上实例输出结果：
```python
dict['Name']:  小菜鸟
```

2）键必须不可变，所以可以用数字，字符串或元组充当，而用列表就不行，如下实例：
```python
#!/usr/bin/python3
 
dict = {['Name']: 'Runoob', 'Age': 7}
 
print ("dict['Name']: ", dict['Name'])
```

以上实例输出结果：
```python
Traceback (most recent call last):
  File "test.py", line 3, in <module>
    dict = {['Name']: 'Runoob', 'Age': 7}
TypeError: unhashable type: 'list'
```

---


### **字典内置函数&方法**
Python字典包含了以下内置函数：

![](/image/12-1.png)

Python字典包含了以下内置方法：

![](/image/12-2.png)
![](/image/12-3.png)

下面对这些内置方法进行详细介绍：

## **Python3 字典 clear()方法**
### **描述**
Python 字典 clear() 函数用于删除字典内所有元素。

### **语法**
clear()方法语法：
```python
dict.clear()
```
### **参数**
* NA。

### **返回值**
该函数没有任何返回值。

### **实例**
以下实例展示了 clear()函数的使用方法：
```python 
#!/usr/bin/python3

dict = {'Name': 'Zara', 'Age': 7}

print ("字典长度 : %d" %  len(dict))
dict.clear()
print ("字典删除后长度 : %d" %  len(dict))
```
以上实例输出结果为：
```python 
字典长度 : 2
字典删除后长度 : 0
```

---

## **Python3 字典 copy()方法**
### **描述**
Python 字典 copy() 函数返回一个字典的浅复制。

### **语法**
copy()方法语法：
```python
dict.copy()
```
### **参数**
* NA。

### **返回值**
返回一个字典的浅复制。

### **实例**
以下实例展示了 copy()函数的使用方法：
```python 
#!/usr/bin/python3
 
dict1 = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
 
dict2 = dict1.copy()
print ("新复制的字典为 : ",dict2)
```
以上实例输出结果为：
```python 
新复制的字典为 :  {'Age': 7, 'Name': 'Runoob', 'Class': 'First'}
```
### **直接赋值和 copy 的区别**
可以通过以下实例说明：
```python 
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
dict1 =  {'user':'runoob','num':[1,2,3]}
 
dict2 = dict1          # 浅拷贝: 引用对象
dict3 = dict1.copy()   # 浅拷贝：深拷贝父对象（一级目录），子对象（二级目录）不拷贝，还是引用
 
# 修改 data 数据
dict1['user']='root'
dict1['num'].remove(1)
 
# 输出结果
print(dict1)
print(dict2)
print(dict3)
```
实例中 dict2 其实是 dict1 的引用（别名），所以输出结果都是一致的，dict3 父对象进行了深拷贝，不会随dict1 修改而修改，子对象是浅拷贝所以随 dict1 的修改而修改。
```python 
{'user': 'root', 'num': [2, 3]}
{'user': 'root', 'num': [2, 3]}
{'user': 'runoob', 'num': [2, 3]}
```

---

## **Python3 字典 fromkeys() 方法**
### **描述**
Python 字典 fromkeys() 函数用于创建一个新字典，以序列 seq 中元素做字典的键，value 为字典所有键对应的初始值。

### **语法**
fromkeys() 方法语法：
```python
dict.fromkeys(seq[, value])
```
### **参数**
* seq -- 字典键值列表。
* value -- 可选参数, 设置键序列（seq）对应的值，默认为 None。

### **返回值**
该方法返回一个新字典。

### **实例**
以下实例展示了 fromkeys()函数的使用方法：
```python 
#!/usr/bin/python3
 
seq = ('name', 'age', 'sex')
 
dict = dict.fromkeys(seq)
print ("新的字典为 : %s" %  str(dict))
 
dict = dict.fromkeys(seq, 10)
print ("新的字典为 : %s" %  str(dict))
```
以上实例输出结果为：
```python 
新的字典为 : {'age': None, 'name': None, 'sex': None}
新的字典为 : {'age': 10, 'name': 10, 'sex': 10}
```
---

## **Python3 字典 get() 方法**
### **描述**
Python 字典 get() 函数返回指定键的值，如果值不在字典中返回默认值。

### **语法**
get()方法语法：
```python
dict.get(key, default=None)
```
### **参数**
* key -- 字典中要查找的键。
* default -- 如果指定键的值不存在时，返回该默认值值。

### **返回值**
返回指定键的值，如果值不在字典中返回默认值 None。

### **实例**
以下实例展示了 get()函数的使用方法：
```python 
#!/usr/bin/python3 

dict = {'Name': 'Runoob', 'Age': 27}

print ("Age 值为 : %s" %  dict.get('Age'))
print ("Sex 值为 : %s" %  dict.get('Sex', "NA"))
```

```python 
Age 值为 : 27
Sex 值为 : NA
```
---

## **Python3 字典 in 操作符**
### **描述**
Python 字典 in 操作符用于判断键是否存在于字典中，如果键在字典 dict 里返回 true，否则返回 false。

而 not in 操作符刚好相反，如果键在字典 dict 里返回 false，否则返回 true。

### **语法**
in 操作符语法：
```python
key in dict
```
### **参数**
* key -- 要在字典中查找的键。

### **返回值**
如果键在字典里返回true，否则返回false。

### **实例**
以下实例展示了 in 操作符在字典中的使用方法：
```python 
#!/usr/bin/python3
 
dict = {'Name': 'Runoob', 'Age': 7}
 
# 检测键 Age 是否存在
if  'Age' in dict:
    print("键 Age 存在")
else :
    print("键 Age 不存在")
 
# 检测键 Sex 是否存在
if  'Sex' in dict:
    print("键 Sex 存在")
else :
    print("键 Sex 不存在")
 
 
# not in
 
# 检测键 Age 是否存在
if  'Age' not in dict:
    print("键 Age 不存在")
else :
    print("键 Age 存在")
```
以上实例输出结果为：
```python 
键 Age 存在
键 Sex 不存在
键 Age 存在
```
---
## **Python3 字典 items() 方法**
### **描述**
Python 字典 items() 方法以列表返回可遍历的(键, 值) 元组数组。

### **语法**
items()方法语法：
```python
dict.items()
```
### **参数**
* NA。

### **返回值**
返回可遍历的(键, 值) 元组数组。

### **实例**
以下实例展示了 items() 方法的使用方法：
```python 
#!/usr/bin/python3
 
dict = {'Name': 'Runoob', 'Age': 7}
 
print ("Value : %s" %  dict.items())
```
以上实例输出结果为：
```python 
Value : dict_items([('Age', 7), ('Name', 'Runoob')])
```
---
## **Python3 字典 keys() 方法**
### **描述**
Python3 字典 keys() 方法返回一个可迭代对象，可以使用 list() 来转换为列表。

注意：Python2.x 是直接返回列表

### **语法**
keys()方法语法：
```python
dict.keys()
```
### **参数**
* NA。

### **返回值**
返回一个迭代器。

### **实例**
以下实例展示了 keys() 方法的使用方法：
```python 
>>> dict = {'Name': 'Runoob', 'Age': 7}
>>> dict.keys()
dict_keys(['Name', 'Age'])
>>> list(dict.keys())             # 转换为列表
['Name', 'Age']
>>> 
```
以上实例输出结果为：
```python 
字典所有的键为 : dict_keys(['Age', 'Name'])
```
---
## **Python3 字典 setdefault() 方法**
### **描述**
Python 字典 setdefault() 方法和 get()方法 类似, 如果键不已经存在于字典中，将会添加键并将值设为默认值。

### **语法**
setdefault()方法语法：
```python
dict.setdefault(key, default=None)
```
### **参数**
* key -- 查找的键值。
* default -- 键不存在时，设置的默认键值。

### **返回值**
如果 key 在 字典中，返回对应的值。如果不在字典中，则插入 key 及设置的默认值 default，并返回 default ，default 默认值为 None。

### **实例**
以下实例展示了 setdefault() 方法的使用方法：
```python 
#!/usr/bin/python3
 
dict = {'Name': 'Runoob', 'Age': 7}
 
print ("Age 键的值为 : %s" %  dict.setdefault('Age', None))
print ("Sex 键的值为 : %s" %  dict.setdefault('Sex', None))
print ("新字典为：", dict)
```
以上实例输出结果为：
```python 
Age 键的值为 : 7
Sex 键的值为 : None
新字典为： {'Age': 7, 'Name': 'Runoob', 'Sex': None}
```
---

## **Python3 字典 update() 方法**
### **描述**
Python 字典 update() 函数把字典参数 dict2 的 key/value(键/值) 对更新到字典 dict 里。

### **语法**
update() 方法语法：
```python
dict.update(dict2)
```
### **参数**
* dict2 -- 添加到指定字典dict里的字典。

### **返回值**
该方法没有任何返回值。

### **实例**
以下实例展示了 update()函数的使用方法：
```python 
#!/usr/bin/python3
 
dict = {'Name': 'Runoob', 'Age': 7}
dict2 = {'Sex': 'female' }
 
dict.update(dict2)
print ("更新字典 dict : ", dict)
```
以上实例输出结果为：
```python 
更新字典 dict :  {'Name': 'Runoob', 'Age': 7, 'Sex': 'female'}
```
---

## **Python3 字典 values() 方法**
### **描述**
Python 字典 values() 方法返回一个迭代器，可以使用 list() 来转换为列表，列表为字典中的所有值。

### **语法**
values()方法语法：
```python
dict.values()
```
### **参数**
* NA。

### **返回值**
返回迭代器。

### **实例**
以下实例展示了 values() 方法的使用方法：
```python 
#!/usr/bin/python3
 
dict = {'Sex': 'female', 'Age': 7, 'Name': 'Zara'}
 
print ("字典所有值为 : ",  list(dict.values()))
```
以上实例输出结果为：
```python 
字典所有值为 :  ['female', 7, 'Zara']
```
---

## **Python3 字典 pop() 方法**
### **描述**
Python 字典 pop() 方法删除字典给定键 key 所对应的值，返回值为被删除的值。key值必须给出。 否则，返回default值。

### **语法**
pop()方法语法：
```python
pop(key[,default])
```
### **参数**
* key: 要删除的键值
* default: 如果没有 key，返回 default 值

### **返回值**
返回被删除的值。

### **实例**
以下实例展示了 pop() 方法的使用方法：
```python 
>>> site= {'name': '菜鸟教程', 'alexa': 10000, 'url': 'www.runoob.com'}
>>> pop_obj=site.pop('name')
>>> print(pop_obj)
菜鸟教程
```

---
## **Python3 字典 popitem() 方法**
### **描述**
Python 字典 popitem() 方法随机返回并删除字典中的一对键和值(一般删除末尾对)。

如果字典已经为空，却调用了此方法，就报出KeyError异常。

### **语法**
popitem()方法语法：
```python
popitem()
```
### **参数**
* 无

### **返回值**
返回一个键值对(key,value)形式。

### **实例**
以下实例展示了 popitem() 方法的使用方法：
```python 
#!/usr/bin/python3

site= {'name': '菜鸟教程', 'alexa': 10000, 'url': 'www.runoob.com'}
pop_obj=site.popitem()
print(pop_obj)   
print(site)
```
输出结果为：
```python 
('url', 'www.runoob.com')
{'name': '菜鸟教程', 'alexa': 10000}
```


---

