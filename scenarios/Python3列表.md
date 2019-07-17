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

下面对这些函数进行详细的介绍：

## **Python3 List len()方法**
### **描述**
len() 方法返回列表元素个数。

### **语法**
len()方法语法：
```python
len(list)
```
### **参数**
* list -- 要计算元素个数的列表。

### **返回值**
返回列表元素个数。

### **实例**
以下实例展示了 len()函数的使用方法：
```python 
#!/usr/bin/python3

list1 = ['Google', 'Runoob', 'Taobao']
print (len(list1))
list2=list(range(5)) # 创建一个 0-4 的列表
print (len(list2))
```
以上实例输出结果如下：
```python 
3
5
```


## **Python3 List max()方法**
### **描述**
max() 方法返回列表元素中的最大值。

### **语法**
max()方法语法：
```python
max(list)
```
### **参数**
* list -- 要返回最大值的列表。

### **返回值**
返回列表元素中的最大值。

### **实例**
以下实例展示了 max()函数的使用方法：
```python 
#!/usr/bin/python3

list1, list2 = ['Google', 'Runoob', 'Taobao'], [456, 700, 200]

print ("list1 最大元素值 : ", max(list1))
print ("list2 最大元素值 : ", max(list2))
```
以上实例输出结果如下：
```python 
list1 最大元素值 :  Taobao
list2 最大元素值 :  700
```


## **Python3 List min()方法**
### **描述**
min() 方法返回列表元素中的最小值。

### **语法**
min()方法语法：
```python
min(list)
```
### **参数**
* list -- 要返回最小值的列表。

### **返回值**
返回列表元素中的最小值。

### **实例**
以下实例展示了 min()函数的使用方法：
```python 
#!/usr/bin/python3

list1, list2 = ['Google', 'Runoob', 'Taobao'], [456, 700, 200]

print ("list1 最小元素值 : ", min(list1))
print ("list2 最小元素值 : ", min(list2))
```
以上实例输出结果如下：
```python 
list1 最小元素值 :  Google
list2 最小元素值 :  200
```


## **Python3 List list()方法**
### **描述**
list() 方法用于将元组或字符串转换为列表。

注：元组与列表是非常类似的，区别在于元组的元素值不能修改，元组是放在括号中，列表是放于方括号中。

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



Python包含以下方法:
![](https://github.com/anmiaru/python3/raw/master/image/10-4.png)  
![](https://github.com/anmiaru/python3/raw/master/image/10-5.png)

下面对这些函数进行详细的介绍：

## **Python3 List append()方法**
### **描述**
append() 方法用于在列表末尾添加新的对象。

### **语法**
append()方法语法：
```python
list.append(obj)
```
### **参数**
* obj -- 添加到列表末尾的对象。

### **返回值**
该方法无返回值，但是会修改原来的列表。

### **实例**
以下实例展示了 append()函数的使用方法：
```python 
#!/usr/bin/python3

list1 = ['Google', 'Runoob', 'Taobao']
list1.append('Baidu')
print ("更新后的列表 : ", list1)
```
以上实例输出结果如下：
```python 
更新后的列表 :  ['Google', 'Runoob', 'Taobao', 'Baidu']
```

## **Python3 List count()方法**
### **描述**
count() 方法用于统计某个元素在列表中出现的次数。

### **语法**
count()方法语法：
```python
list.count(obj)
```
### **参数**
* obj -- 列表中统计的对象。

### **返回值**
返回元素在列表中出现的次数。

### **实例**
以下实例展示了 count()函数的使用方法：
```python 
#!/usr/bin/python3

aList = [123, 'Google', 'Runoob', 'Taobao', 123];

print ("123 元素个数 : ", aList.count(123))
print ("Runoob 元素个数 : ", aList.count('Runoob'))
```
以上实例输出结果如下：
```python 
123 元素个数 :  2
Runoob 元素个数 :  1
```

## **Python3 List extend()方法**
### **描述**
extend() 函数用于在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表）。

### **语法**
extend()方法语法：
```python
list.extend(seq)
```
### **参数**
* seq -- 元素列表，可以是列表、元组、集合、字典，若为字典,则仅会将键(key)作为元素依次添加至原列表的末尾。

### **返回值**
该方法没有返回值，但会在已存在的列表中添加新的列表内容。

### **实例**
以下实例展示了 extend()函数的使用方法：
```python 
#!/usr/bin/python3
 
list1 = ['Google', 'Runoob', 'Taobao']
list2=list(range(5)) # 创建 0-4 的列表
list1.extend(list2)  # 扩展列表
print ("扩展后的列表：", list1)
```
以上实例输出结果如下：
```python 
扩展后的列表： ['Google', 'Runoob', 'Taobao', 0, 1, 2, 3, 4]
```
不同数据类型：
```python 
#!/usr/bin/python3
 
# 语言列表
language = ['French', 'English', 'German']
 
# 元组
language_tuple = ('Spanish', 'Portuguese')
 
# 集合
language_set = {'Chinese', 'Japanese'}
 
# 添加元组元素到列表末尾
language.extend(language_tuple)
 
print('新列表: ', language)
 
# 添加集合元素到列表末尾
language.extend(language_set)
 
print('新列表: ', language)
```

```python 
新列表:  ['French', 'English', 'German', 'Spanish', 'Portuguese']
新列表:  ['French', 'English', 'German', 'Spanish', 'Portuguese', 'Japanese', 'Chinese']
```


## **Python3 List index()方法**
### **描述**
index() 函数用于从列表中找出某个值第一个匹配项的索引位置。

### **语法**
index()方法语法：
```python
list.index(x[, start[, end]])
```
### **参数**
* x-- 查找的对象。  
* start-- 可选，查找的起始位置。  
* end-- 可选，查找的结束位置。

### **返回值**
该方法返回查找对象的索引位置，如果没有找到对象则抛出异常。

### **实例**
以下实例展示了 index()函数的使用方法：
```python 
#!/usr/bin/python3

list1 = ['Google', 'Runoob', 'Taobao']
print ('Runoob 索引值为', list1.index('Runoob'))
print ('Taobao 索引值为', list1.index('Taobao'))
```
以上实例输出结果如下：
```python 
Runoob 索引值为 1
Taobao 索引值为 2
```
实例2：
```python 
#!/usr/bin/python3

list1 = ['Google', 'Runoob', 'Taobao', 'Facebook', 'QQ']
# 从指定位置开始搜索
print ('Runoob 索引值为', list1.index('Runoob',1))
```
以上实例输出结果如下：
```python 
Runoob 索引值为 1
```

## **Python3 List insert()方法**
### **描述**
insert() 函数用于将指定对象插入列表的指定位置。

### **语法**
insert()方法语法：
```python
list.insert(index, obj)
```
### **参数**
* index -- 对象obj需要插入的索引位置。
* obj -- 要插入列表中的对象。

### **返回值**
该方法没有返回值，但会在列表指定位置插入对象。

### **实例**
以下实例展示了 insert()函数的使用方法：
```python 
#!/usr/bin/python3

list1 = ['Google', 'Runoob', 'Taobao']
list1.insert(1, 'Baidu')
print ('列表插入元素后为 : ', list1)
```
以上实例输出结果如下：
```python 
列表插入元素后为 :  ['Google', 'Baidu', 'Runoob', 'Taobao']
```

## **Python3 List pop()方法**
### **描述**
pop() 函数用于移除列表中的一个元素（默认最后一个元素），并且返回该元素的值。

### **语法**
pop()方法语法：
```python
list.pop([index=-1])
```
### **参数**
* index -- 可选参数，要移除列表元素的索引值，不能超过列表总长度，默认为 index=-1，删除最后一个列表值。

### **返回值**
该方法返回从列表中移除的元素对象。

### **实例**
以下实例展示了 pop()函数的使用方法：
```python 
#!/usr/bin/python3

list1 = ['Google', 'Runoob', 'Taobao']
list1.pop()
print ("列表现在为 : ", list1)
list1.pop(1)
print ("列表现在为 : ", list1)
```
以上实例输出结果如下：
```python 
列表现在为 :  ['Google', 'Runoob']
列表现在为 :  ['Google']
```

## **Python3 List remove()方法**
### **描述**
remove() 函数用于移除列表中某个值的第一个匹配项。

### **语法**
remove()方法语法：
```python
list.remove(obj)
```
### **参数**
* obj -- 列表中要移除的对象。

### **返回值**
该方法没有返回值但是会移除列表中的某个值的第一个匹配项。

### **实例**
以下实例展示了 remove()函数的使用方法：
```python 
#!/usr/bin/python3

list1 = ['Google', 'Runoob', 'Taobao', 'Baidu']
list1.remove('Taobao')
print ("列表现在为 : ", list1)
list1.remove('Baidu')
print ("列表现在为 : ", list1)
```
以上实例输出结果如下：
```python 
列表现在为 :  ['Google', 'Runoob', 'Baidu']
列表现在为 :  ['Google', 'Runoob']
```



## **Python3 List reverse()方法**
### **描述**
reverse() 函数用于反向列表中元素。

### **语法**
reverse()方法语法：
```python
list.reverse()
```
### **参数**
* NA。

### **返回值**
该方法没有返回值，但是会对列表的元素进行反向排序。

### **实例**
以下实例展示了 reverse()函数的使用方法：
```python 
#!/usr/bin/python3

list1 = ['Google', 'Runoob', 'Taobao', 'Baidu']
list1.reverse()
print ("列表反转后: ", list1)
```
以上实例输出结果如下：
```python 
列表反转后:  ['Baidu', 'Taobao', 'Runoob', 'Google']
```



## **Python3 List sort()方法**
### **描述**
sort() 函数用于对原列表进行排序，如果指定参数，则使用比较函数指定的比较函数。

### **语法**
sort()方法语法：
```python
list.sort( key=None, reverse=False)
```
### **参数**
* key -- 主要是用来进行比较的元素，只有一个参数，具体的函数的参数就是取自于可迭代对象中，指定可迭代对象中的一个元素来进行排序。
* reverse -- 排序规则，reverse = True 降序， reverse = False 升序（默认）。

### **返回值**
该方法没有返回值，但是会对列表的对象进行排序。

### **实例**
以下实例展示了 sort() 函数的使用方法：
```python 
#!/usr/bin/python
 
aList = ['Google', 'Runoob', 'Taobao', 'Facebook']
 
aList.sort()
print ( "List : ", aList)
```
以上实例输出结果如下：
```python 
List :  ['Facebook', 'Google', 'Runoob', 'Taobao']
```
以下实例降序输出列表：
```python 
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
# 列表
vowels = ['e', 'a', 'u', 'o', 'i']
 
# 降序
vowels.sort(reverse=True)
 
# 输出结果
print ( '降序输出:', vowels )
```
以上实例输出结果如下：
```python 
降序输出: ['u', 'o', 'i', 'e', 'a']
```
以下实例演示了通过指定列表中的元素排序来输出列表：
```python 
#!/usr/bin/python
 
# 获取列表的第二个元素
def takeSecond(elem):
    return elem[1]
 
# 列表
random = [(2, 2), (3, 4), (4, 1), (1, 3)]
 
# 指定第二个元素排序
random.sort(key=takeSecond)
 
# 输出类别
print ('排序列表：', random)
```
以上实例输出结果如下：
```python 
排序列表：[(4, 1), (2, 2), (1, 3), (3, 4)]
```



## **Python3 List clear()方法**
### **描述**
clear() 函数用于清空列表，类似于 del a\[:\]。

### **语法**
clear()方法语法：
```python
list.clear()
```
### **参数**
* 无。

### **返回值**
该方法没有返回值。

### **实例**
以下实例展示了 clear()函数的使用方法：
```python 
#!/usr/bin/python3

list1 = ['Google', 'Runoob', 'Taobao', 'Baidu']
list1.clear()
print ("列表清空后 : ", list1)
```
以上实例输出结果如下：
```python 
列表清空后 :  []
```


## **Python3 List copy()方法**
### **描述**
copy() 函数用于复制列表，类似于 a\[:\]。

### **语法**
copy()方法语法：
```python
list.copy()
```
### **参数**
* 无。

### **返回值**
返回复制后的新列表。

### **实例**
以下实例展示了 copy()函数的使用方法：
```python 
#!/usr/bin/python3

list1 = ['Google', 'Runoob', 'Taobao', 'Baidu']
list2 = list1.copy()
print ("list2 列表: ", list2)
```
以上实例输出结果如下：
```python 
list2 列表:  ['Google', 'Runoob', 'Taobao', 'Baidu']
```

---
