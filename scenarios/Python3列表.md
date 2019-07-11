## **Python3列表**

序列是Python中最基本的数据结构。序列中的每个元素都分配一个数字 - 它的位置，或索引，第一个索引是0，第二个索引是1，依此类推。  
Python有6个序列的内置类型，但最常见的是列表和元组。  
序列都可以进行的操作包括索引，切片，加，乘，检查成员。  
此外，Python已经内置确定序列的长度以及确定最大和最小的元素的方法。  
列表是最常用的Python数据类型，它可以作为一个方括号内的逗号分隔值出现。  
列表的数据项不需要具有相同的类型  
创建一个列表，只要把逗号分隔的不同的数据项使用方括号括起来即可。如下所示：
```python
list1 = ['Google', 'Runoob', 1997, 2000];
list2 = [1, 2, 3, 4, 5 ];
list3 = ["a", "b", "c", "d"];
```
与字符串的索引一样，列表索引从0开始。列表可以进行截取、组合等。

---

### **访问列表中的值**

使用下标索引来访问列表中的值，同样你也可以使用方括号的形式截取字符，如下所示：
```python
#!/usr/bin/python3
 
list1 = ['Google', 'Runoob', 1997, 2000];
list2 = [1, 2, 3, 4, 5, 6, 7 ];
 
print ("list1[0]: ", list1[0])
print ("list2[1:5]: ", list2[1:5])
```
以上实例输出结果：
```python
list1[0]:  Google
list2[1:5]:  [2, 3, 4, 5]
```

---


### **更新列表**

你可以对列表的数据项进行修改或更新，你也可以使用append()方法来添加列表项，如下所示：
```python
#!/usr/bin/python3
 
list = ['Google', 'Runoob', 1997, 2000]
 
print ("第三个元素为 : ", list[2])
list[2] = 2001
print ("更新后的第三个元素为 : ", list[2])
```
**注意**：我们会在接下来的章节讨论append()方法的使用  

以上实例输出结果：
```python
第三个元素为 :  1997
更新后的第三个元素为 :  2001
```

---


### **删除列表元素**

可以使用 del 语句来删除列表的的元素，如下实例：
```python
#!/usr/bin/python3
 
list = ['Google', 'Runoob', 1997, 2000]
 
print ("原始列表 : ", list)
del list[2]
print ("删除第三个元素 : ", list)
```
以上实例输出结果：
```python
原始列表 :  ['Google', 'Runoob', 1997, 2000]
删除第三个元素 :  ['Google', 'Runoob', 2000]
```
**注意**：我们会在接下来的章节讨论 remove() 方法的使用

---

### **Python列表脚本操作符**

列表对 + 和 * 的操作符与字符串相似。+ 号用于组合列表，* 号用于重复列表。

如下所示：

![](https://github.com/anmiaru/python3/raw/master/image/10-1.png)

---


### **Python列表截取与拼接**

Python的列表截取与字符串操作类型，如下所示：
```python 
L=['Google', 'Runoob', 'Taobao']
```
操作：
![](https://github.com/anmiaru/python3/raw/master/image/10-2.png)
```python 
>>>L=['Google', 'Runoob', 'Taobao']
>>> L[2]
'Taobao'
>>> L[-2]
'Runoob'
>>> L[1:]
['Runoob', 'Taobao']
>>>
```
列表还支持拼接操作：
```python 
>>>squares = [1, 4, 9, 16, 25]
>>> squares += [36, 49, 64, 81, 100]
>>> squares
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
>>>
```

---

### **嵌套列表**
使用嵌套列表即在列表里创建其它列表，例如：
```python 
>>>a = ['a', 'b', 'c']
>>> n = [1, 2, 3]
>>> x = [a, n]
>>> x
[['a', 'b', 'c'], [1, 2, 3]]
>>> x[0]
['a', 'b', 'c']
>>> x[0][1]
'b'
```
---

### **Python列表函数&方法**
Python包含以下函数:
![](https://github.com/anmiaru/python3/raw/master/image/10-3.png)

Python包含以下方法:
![](https://github.com/anmiaru/python3/raw/master/image/10-4.png)  
![](https://github.com/anmiaru/python3/raw/master/image/10-5.png)


---
