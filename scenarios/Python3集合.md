## **Python3集合**
集合（set）是一个无序的不重复元素序列。  
可以使用大括号 { } 或者 set() 函数创建集合，注意：创建一个空集合必须用 set() 而不是 { }，因为 { } 是用来创建一个空字典。  
创建格式：
```python
parame = {value01,value02,...}
或者
set(value)
```
```python
>>>basket = {'apple', 'orange', 'apple', 'pear', 'orange', 'banana'}
>>> print(basket)                      # 这里演示的是去重功能
{'orange', 'banana', 'pear', 'apple'}
>>> 'orange' in basket                 # 快速判断元素是否在集合内
True
>>> 'crabgrass' in basket
False
 
>>> # 下面展示两个集合间的运算.
...
>>> a = set('abracadabra')
>>> b = set('alacazam')
>>> a                                  
{'a', 'r', 'b', 'c', 'd'}
>>> a - b                              # 集合a中包含而集合b中不包含的元素
{'r', 'd', 'b'}
>>> a | b                              # 集合a或b中包含的所有元素
{'a', 'c', 'r', 'd', 'b', 'm', 'z', 'l'}
>>> a & b                              # 集合a和b中都包含了的元素
{'a', 'c'}
>>> a ^ b                              # 不同时包含于a和b的元素
{'r', 'd', 'b', 'm', 'z', 'l'}
```

类似列表推导式，同样集合支持集合推导式(Set comprehension):
```python
>>>a = {x for x in 'abracadabra' if x not in 'abc'}
>>> a
{'r', 'd'}
```
---

### **集合的基本操作**
#### **1、添加元素**
语法格式如下：
```python
s.add( x )
```

将元素 x 添加到集合 s 中，如果元素已存在，则不进行任何操作。
```python
>>>thisset = set(("Google", "Runoob", "Taobao"))
>>> thisset.add("Facebook")
>>> print(thisset)
{'Taobao', 'Facebook', 'Google', 'Runoob'}
```

还有一个方法，也可以添加元素，且参数可以是列表，元组，字典等，语法格式如下：
```python
s.update( x )
```

x 可以有多个，用逗号分开。
```python
>>>thisset = set(("Google", "Runoob", "Taobao"))
>>> thisset.update({1,3})
>>> print(thisset)
{1, 3, 'Google', 'Taobao', 'Runoob'}
>>> thisset.update([1,4],[5,6])  
>>> print(thisset)
{1, 3, 4, 5, 6, 'Google', 'Taobao', 'Runoob'}
>>>
```
---

#### **2、移除元素**
语法格式如下：
```python
s.remove( x )
```

将元素 x 从集合 s 中移除，如果元素不存在，则会发生错误。
```python
>>>thisset = set(("Google", "Runoob", "Taobao"))
>>> thisset.remove("Taobao")
>>> print(thisset)
{'Google', 'Runoob'}
>>> thisset.remove("Facebook")   # 不存在会发生错误
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'Facebook'
>>>
```
此外还有一个方法也是移除集合中的元素，且如果元素不存在，不会发生错误。格式如下所示：
```python
s.discard( x )
```

```python
>>>thisset = set(("Google", "Runoob", "Taobao"))
>>> thisset.discard("Facebook")  # 不存在不会发生错误
>>> print(thisset)
{'Taobao', 'Google', 'Runoob'}
```
我们也可以设置随机删除集合中的一个元素，语法格式如下
```python
s.pop() 
```
```python
thisset = set(("Google", "Runoob", "Taobao", "Facebook"))
x = thisset.pop()
 
print(x)
```
输出结果：
```python
$ python3 test.py 
Runoob
```
多次执行测试结果都不一样。  
然而在交互模式，pop 是删除集合的第一个元素（排序后的集合的第一个元素）。  
```python
>>>thisset = set(("Google", "Runoob", "Taobao", "Facebook"))
>>> thisset.pop()
'Facebook'
>>> print(thisset)
{'Google', 'Taobao', 'Runoob'}
>>>
```
---

#### **3、计算集合元素个数**
语法格式如下：
```python
len(s)
```
计算集合 s 元素个数。
```python
>>>thisset = set(("Google", "Runoob", "Taobao"))
>>> len(thisset)
3
```
---

#### **4、清空集合**
语法格式如下：
```python
s.clear()
```
清空集合 s。
```python
>>>thisset = set(("Google", "Runoob", "Taobao"))
>>> thisset.clear()
>>> print(thisset)
set()
```
---


#### **5、判断元素是否在集合中存在**
语法格式如下：
```python
x in s
```
判断元素 x 是否在集合 s 中，存在返回 True，不存在返回 False。
```python
>>>thisset = set(("Google", "Runoob", "Taobao"))
>>> "Runoob" in thisset
True
>>> "Facebook" in thisset
False
>>>
```

**集合内置方法完整列表**
![](/image/13-1.png)

![](/image/13-2.png)


下面对上面没有提及的内置方法进行介绍：

## **Python Set copy()方法**
### **描述**
copy() 方法用于拷贝一个集合。

### **语法**
copy() 方法语法：
```python
set.copy()
```
### **参数**
* 无。

### **返回值**

无。
### **实例**
拷贝 fruits 集合：
```python 
fruits = {"apple", "banana", "cherry"}
x = fruits.copy()
print(x)
```
输出结果为：
```python 
{'cherry', 'banana', 'apple'}
```

---

## **Python Set difference() 方法**
### **描述**
difference() 方法用于返回集合的差集，即返回的集合元素包含在第一个集合中，但不包含在第二个集合(方法的参数)中。

### **语法**
difference() 方法语法：
```python
set.difference(set)
```
### **参数**
* set -- 必需，用于计算差集的集合

### **返回值**
返回一个新的集合。

### **实例**
返回一个集合，元素包含在集合 x ，但不在集合 y ：
```python 
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}
 
z = x.difference(y) 
 
print(z)
```
输出结果为：

```python 
{'cherry', 'banana'}
```

---

## **Python Set difference_update() 方法**
### **描述**
difference_update() 方法用于移除两个集合中都存在的元素。

difference_update() 方法与 difference() 方法的区别在于 difference() 方法返回一个移除相同元素的新集合，而 difference_update() 方法是直接在原来的集合中移除元素，没有返回值。

### **语法**
difference_update() 方法语法：
```python
set.difference_update(set)
```
### **参数**
* set -- 必需，用于计算差集的集合

### **返回值**
无。

### **实例**
移除两个集合都包含的元素：
```python 
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}
 
x.difference_update(y) 
 
print(x)
```
输出结果为：
```python 
{'cherry', 'banana'}
```

---

## **Python Set intersection() 方法**
### **描述**
intersection() 方法用于返回两个或更多集合中都包含的元素，即交集。

### **语法**
intersection() 方法语法：
```python
set.intersection(set1, set2 ... etc)
```
### **参数**
* set1 -- 必需，要查找相同元素的集合
* set2 -- 可选，其他要查找相同元素的集合，可以多个，多个使用逗号 , 隔开

### **返回值**

返回一个新的集合。
### **实例**
返回一个新集合，该集合的元素既包含在集合 x 又包含在集合 y 中：
```python 
x = {"apple", "banana", "cherry"}
y = {"google", "runoob", "apple"}
 
z = x.intersection(y) 
 
print(z)
```
输出结果为：
```python 
{'apple'}
```

---

## **Python Set intersection_update() 方法**
### **描述**
intersection_update() 方法用于获取两个或更多集合中都重叠的元素，即计算交集。

intersection_update() 方法不同于 intersection() 方法，因为 intersection() 方法是返回一个新的集合，而 intersection_update() 方法是在原始的集合上移除不重叠的元素。

### **语法**
intersection_update() 方法语法：
```python
set.intersection_update(set1, set2 ... etc)
```
### **参数**
* set1 -- 必需，要查找相同元素的集合
* set2 -- 可选，其他要查找相同元素的集合，可以多个，多个使用逗号 , 隔开

### **返回值**

无。
### **实例**
返回一个新集合，该集合的元素既包含在集合 x 又包含在集合 y 中：
```python 
x = {"apple", "banana", "cherry"}
y = {"google", "runoob", "apple"}
 
x.intersection_update(y) 
 
print(x)
```
输出结果为：
```python 
{'apple'}
```
计算多个集合的并集：
```python 
x = {"a", "b", "c"}
y = {"c", "d", "e"}
z = {"f", "g", "c"}
 
x.intersection_update(y, z)
 
print(x)
```
输出结果为：
```python 
{'c'}
```

---

## **Python Set isdisjoint() 方法**
### **描述**
isdisjoint() 方法用于判断两个集合是否包含相同的元素，如果没有返回 True，否则返回 False。

### **语法**
isdisjoint() 方法语法：
```python
set.isdisjoint(set)
```
### **参数**
* set -- 必需，要比较的集合

### **返回值**
返回布尔值，如果不包含返回 True，否则返回 False。

### **实例**
判断集合 y 中是否有包含 集合 x 的元素：
```python 
x = {"apple", "banana", "cherry"}
y = {"google", "runoob", "facebook"}
 
z = x.isdisjoint(y) 
 
print(z)
```
输出结果为：
```python 
True
```
如果包含返回 False：
```python 
x = {"apple", "banana", "cherry"}
y = {"google", "runoob", "apple"}
 
z = x.isdisjoint(y) 
 
print(z)
```
输出结果为：
```python 
False
```

---

## **Python Set issubset() 方法**
### **描述**
issubset() 方法用于判断集合的所有元素是否都包含在指定集合中，如果是则返回 True，否则返回 False。

### **语法**
issubset() 方法语法：
```python
set.issubset(set)
```
### **参数**
* set -- 必需，要比查找的集合

### **返回值**
返回布尔值，如果都包含返回 True，否则返回 False。

### **实例**
判断集合 x 的所有元素是否都包含在集合 y 中：
```python 
x = {"a", "b", "c"}
y = {"f", "e", "d", "c", "b", "a"}
 
z = x.issubset(y) 
 
print(z)
```
输出结果为：
```python 
True
```
如果没有全部包含返回 False：
```python 
x = {"a", "b", "c"}
y = {"f", "e", "d", "c", "b"}
 
z = x.issubset(y) 
 
print(z)
```
输出结果为：
```python 
False
```

---

## **Python Set issuperset() 方法**
### **描述**
issuperset() 方法用于判断指定集合的所有元素是否都包含在原始的集合中，如果是则返回 True，否则返回 False。

### **语法**
issuperset() 方法语法：
```python
set.issuperset(set)
```
### **参数**
* set -- 必需，要比查找的集合

### **返回值**
返回布尔值，如果都包含返回 True，否则返回 False。

### **实例**
判断集合 y 的所有元素是否都包含在集合 x 中：
```python 
x = {"f", "e", "d", "c", "b", "a"}
y = {"a", "b", "c"}
 
z = x.issuperset(y) 
 
print(z)
```
输出结果为：
```python 
True
```
如果没有全部包含返回 False：
```python 
x = {"f", "e", "d", "c", "b"}
y = {"a", "b", "c"}
 
z = x.issuperset(y) 
 
print(z)
```
输出结果为：
```python 
False
```
---

## **Python Set symmetric_difference() 方法**
### **描述**
symmetric_difference() 方法返回两个集合中不重复的元素集合，即会移除两个集合中都存在的元素。

### **语法**
symmetric_difference() 方法语法：
```python
set.symmetric_difference(set)
```
### **参数**
* set -- 集合

### **返回值**
返回一个新的集合。

### **实例**
返回两个集合组成的新集合，但会移除两个集合的重复元素：
```python 
x = {"apple", "banana", "cherry"}
y = {"google", "runoob", "apple"}
 
z = x.symmetric_difference(y) 
 
print(z)
```
输出结果为：
```python 
{'google', 'cherry', 'banana', 'runoob'}
```

---

## **Python Set symmetric_difference_update() 方法**
### **描述**
symmetric_difference_update() 方法移除当前集合中在另外一个指定集合相同的元素，并将另外一个指定集合中不同的元素插入到当前集合中。

### **语法**
symmetric_difference_update() 方法语法：
```python
set.symmetric_difference_update(set)
```
### **参数**
* set -- 要检测的集合

### **返回值**
无。

### **实例**
在原始集合 x 中移除与 y 集合中的重复元素，并将不重复的元素插入到集合 x 中：
```python 
x = {"apple", "banana", "cherry"}
y = {"google", "runoob", "apple"}
 
x.symmetric_difference_update(y) 
 
print(x)
```
输出结果为：
```python 
{'google', 'cherry', 'banana', 'runoob'}
```

---

## **Python Set union() 方法**
### **描述**
union() 方法返回两个集合的并集，即包含了所有集合的元素，重复的元素只会出现一次。

### **语法**
union() 方法语法：
```python
set.union(set1, set2...)
```
### **参数**
* set1 -- 必需，合并的目标集合
* set2 -- 可选，其他要合并的集合，可以多个，多个使用逗号 , 隔开。

### **返回值**
返回一个新集合。

### **实例**
合并两个集合，重复元素只会出现一次：
```python 
x = {"apple", "banana", "cherry"}
y = {"google", "runoob", "apple"}
 
z = x.union(y) 
 
print(z)
```
输出结果为：
```python 
{'cherry', 'runoob', 'google', 'banana', 'apple'}
```

---





