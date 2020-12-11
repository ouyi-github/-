# 一.pip依赖管理

pip是python中管理安装包的工具

## 1.pip常用命令

pip help----------帮助文档

pip install 包名==版本号（不加版本号，默认安装最新的）--------安装其他包

pip uninstall 包名------------删除安装包

pip list---------------查看已经安装的所有包



## 2.pip源更换

![image-20201020221439128](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201020221439128.png)

pip install 包名 -i pip镜像云地址-----------使用指定的镜像云安装包

# 二.python基本数据类型

## 1.变量

### 定义：![image-20201021191401466](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201021191401466.png)

### 命名规则：

![image-20201021191540695](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201021191540695.png)

## 2.数字

### 数字的三种类型：

![image-20201021191839855](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201021191839855.png)

```python
a = 1
b = 1.2
c = 2j
```

## 3.字符串

### 定义：

```python
d = 'string'
```

### 打印转义字符

方法一：在转义字符前加反斜杠

```python
d = 'string\\n'
```

方法二：在字符串前加上r

```python
d = r'string\n'
```

### 多个字符串的连接

使用加号（+）连接多个字符串

```python
a = 'aaaaa'
b = 'bbbbb'
print(a+b)
结果：aaaaabbbbb
```

### 字符串内的引用

方法一：使用f加上{}，引用

```python
a = 'aaaaa'
b = 'bbbbb'
print(f'{a}{b}cccc')
结果：aaaaabbbbbcccc
```

方法二：使用{}加上format

```python
a = 'aaaaa'
b = 'bbbbb'
print('{}{}cccc'.format(a,b))
结果：aaaaabbbbbcccc
```

## 4.列表

### 概念：

![image-20201022214244570](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201022214244570.png)

### 定义：

方法一：使用[]定义

```python
list_a = [1,52,'ad']
```

方法二：使用list方法定义，将其他类型的数据转化为字符串

```python
list_a = list('python')
print(list_a)
结果：['p', 'y', 't', 'h', 'o', 'n']
```

### 索引

下标从0开始，-1表示最后一位

```python
list_a = [1,2,3,4]
print(list_a[0])
```

### 切片

方法：list[开始下标:结束下标:步长]，注意：结束下标是开区间，开始下标是闭区间

```python
list_a = [1,2,3,4,5,6,7,8,9,10]
print(list_a[0:8:2])
结果：[1, 3, 5, 7]
```

### 方法

（1）list.append()---------在列表的末尾添加一个元素

```python
list_a = [1,2,3]
list_a.append('A')
print(list_a)
结果：[1, 2, 3, 'A']
```

（2）list.insert(下标，内容)---------在列表的指定位置添加一个元素

```python
list_a = [1,2,3]
list_a.insert(1,'A')
print(list_a)
结果：[1, 'A', 2, 3]
```

（3）list.remove(内容)------------删除列表中指定的内容。注意，如果该内容重复出现，只会删除最前面的那一个。

```python
list_a = [1,2,3,1]
list_a.remove(1)
print(list_a)
结果：[2, 3, 1]
```

（4）list.pop(下标)-------删除指定下标对应的内容，并返回删除的值。如果pop后没有参数，默认是删除并返回最后一个值

```python
list_a = [1,2,'A',3,1]
y = list_a.pop(2)
print(list_a)
print(y)
结果：
[1, 2, 3, 1]
A
```

（5）list.sort()-------对列表内容进行排序，可以自定义规则

```python
list_a = [1,2,5,6,3,7]
list_a.sort() #默认升序
print(list_a)
list_a.sort(reverse=True) #降序
print(list_a)
结果：
[1, 2, 3, 5, 6, 7]
[7, 6, 5, 3, 2, 1]
```

（6）list.reverse()------将列表的内容反转

```python
list_a = [1,2,5,6,3,7]
list_a.reverse()
print(list_a)
结果：
[7, 3, 6, 5, 2, 1]
```

(7)列表推导式

```python
list_a = [i**2 for i in range(1,11)]
print(list_a)
结果：
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

## 5.元组

元组与列表类似，只是元组是不可改变的。所以列表中所有改变的方法都不可用。

### 定义

方法一：使用（）定义元组

```python
tuple_a = (1,2,'a')
print(tuple_a)
结果：(1, 2, 'a')
```

方法二：使用tuple方法，将其他类型的数据变为元组

```python
list_a = [1,2,'a']
tuple_a = tuple(list_a)
print(tuple_a)
结果：
(1, 2, 'a')
```

### 方法

（1）tuple.count(内容)--------查看指定内容在元组中出现的次数

```python
tuple_a = (1,2,'a','a')
count = tuple_a.count('a')
print(count)
结果：2
```

（2）tuple.index(内容)------查看指定内容在元组中对应的下标，注意，如果是重复内容，只会返回第一次出现时的下标

```python
tuple_a = (1,2,'a','a')
count = tuple_a.index('a')
print(count)
结果：2
```

## 6.集合

![image-20201022222816873](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201022222816873.png)

### 定义

方法一：使用{}定义

```python
set_a = {1,2,'a','a'}
print(set_a)
结果：{1, 2, 'a'}
```

方法二：使用set方法，将其他数据类型转化为集合

```python
set_a = set((1,2,'a','a'))
print(set_a)
结果：{1, 2, 'a'}
```

### 方法

集合的大部分方法与列表一样

（1）set1.union(set2)--------返回两个集合的并集

```python
a = {1,2,'a'}
b = {3,4,'a'}
print(a.union(b))
结果：
{1, 2, 3, 4, 'a'}
```

（2）set1.intersection(set2)------返回两个集合的交集

```python
a = {1,2,'a'}
b = {3,4,'a'}
print(a.intersection(b))
结果：
{'a'}
```

（3）set1.difference(set2)-------返回集合1中有，集合2中没有的数据

```python
a = {1,2,'a'}
b = {3,4,'a'}
print(a.difference(b))
结果：{1, 2}
```

## 7.字典

![image-20201022224223186](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201022224223186.png)

### 定义

方法一：使用{key:value}定义

```python
dict_a = {"name":"ouyi","age":18}
print(dict_a)
结果：
{'name': 'ouyi', 'age': 18}
```

方法二：使用dict(key=value)来定义

```python
dict_a = dict(name="ouyi",age=18)
print(dict_a)
结果：
{'name': 'ouyi', 'age': 18}
```

### 方法

（1）dict.keys()-------返回字典中所有的key

```python
dict_a = {"name":"ouyi","age":18}
print(dict_a.keys())
结果：
dict_keys(['name', 'age'])
```

（2）dict.values()--------返回字典中所有的value

```python
dict_a = {"name":"ouyi","age":18}
print(dict_a.values())
结果：dict_values(['ouyi', 18])
```

（3）dict.items()-------返回字典中所有的key，value

```python
dict_a = {"name":"ouyi","age":18}
print(dict_a.items())
结果：dict_items([('name', 'ouyi'), ('age', 18)])
```

（4）dict[key1]-------返回key1对应的值

```python
dict_a = {"name":"ouyi","age":18}
print(dict_a['name'])
结果：
ouyi
```

（5）dict.pop(key)----删除并返回key对应的键值对

```
dict_a = {"name":"ouyi","age":18}
print(dict_a.pop('name'))
print(dict_a)
结果：
ouyi
{'age': 18}
```

（6）dict.popitem()----随机删除并返回一个键值对

```
dict_a = {"name":"ouyi","age":18}
print(dict_a.popitem())
print(dict_a)
结果：
('age', 18)
{'name': 'ouyi'}
```



# 三.python的控制流语法

## 1.分支结构

![image-20201021200058917](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201021200058917.png)

```python
a = 1
if a == 0:
    print('a等于0')
elif a == 1:
    print('a等于1')
else:
    print('a不等于0，1')
```

## 2.循环结构

![image-20201021201101403](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201021201101403.png)



### for in循环

![image-20201021201212097](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201021201212097.png)

```python
for i in range(101):
    print(i)
```

### while循环

![image-20201021201940016](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201021201940016.png)



```python
a =0
while a <= 10:
    print(a)
    a+=1
```

## 3.break和continue

![image-20201021202323152](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201021202323152.png)



# 四.函数

## 1.定义：

def 函数名（参数):

​	"""函数说明"""

​	代码块

​	return xxx

```python
def sum_a(a,b):
    """求和函数"""
    c = a + b
    return c
```

## 2.函数的调用

函数名（参数）

```python
def func1(a,b,c):
    """
    函数的作用
    :param a: 参数a的介绍
    :param b: 参数b的介绍
    :param c: 参数c的介绍
    :return: 返回值的介绍
    """
    代码块
    return xxx
func1(a,b,c)
```

## 3.函数的参数

### 形参

函数定义时的参数，为形参

### 实参

函数调用时参入的参数，为实参

### 位置参数

```python
def sum_a(a,b):
    """求和函数"""
    c = a + b
    return c
print(sum_a(5,8))
调用时，按照位置将实参与形参一一对应。5对应a，8对应b
```

### 关键字参数

```python
def sum_a(a,b):
    """求和函数"""
    c = a + b
    return c
print(sum_a(b=5,a=8))
调用函数时，使用关键字将实参与形参一一对应。这样参入参数时的位置可以颠倒
```

### 默认值参数

```python
def sum_a(a,b=3):
    """求和函数"""
    c = a + b
    return c
print(sum_a(1))
在定义形参时，可以给参数设置一个默认值。注意，默认值参数必须在最后面。sum_a(a=3,b)这样是错误的写法。当实参没有给默认值参数传值时，会使用默认值
```

### 形参的*args,**kwargs

*args表示元组传参，**kwargs表示字典传参

```python
def sum_a(*args):
    c = args
    return c
print(sum_a(1,2))
结果：(1, 2)
```

```python
def sum_a(**kwargs):
    """求和函数"""
    c = kwargs
    return c
print(sum_a(a=1,b=2,c=3))
结果：{'a': 1, 'b': 2, 'c': 3}
```

一般形参设置为(*args,**kwargs)后，可以接受任何形式的实参

## 4.lambda匿名函数

格式：lambda 参数:表达式

```python
a = lambda y:y*2
print(a(2))
```

lambda 只适用于封装一些简单的表达式

# 五.模块

![image-20201023192841695](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201023192841695.png)

![image-20201023192957463](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201023192957463.png)

![image-20201023193100728](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201023193100728.png)

![image-20201023194204408](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201023194204408.png)

**dir()函数**

```
import time
print(dir(time))---------返回time模块内的所有方法
print(dir())-------------返回当前文件下的所有方法，包括导入进来的
```

# 六.输入与输出

## 1.输出

### （1）print()

print(内容)------------将内容输出打印到屏幕

#### 字符串的拼接：

1.格式化输出：使用%拼接

```python
print('我是%s,今年%d岁'%('欧毅',18))
```

注意：%S表示字符串；%d表示10进制整数；

2.format()方法

```python
print('我是{},今年{}岁'.format('欧毅',18))
print('我是{a},今年{b}岁'.format(b = 18,a = '欧毅'))
```

3.f(变量名)方法

```python
name = '欧毅'
age = 18
print(f'我是{name},今年{age}岁')
```

### （2）文件读取IO操作

![image-20201023200444648](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201023200444648.png)

#### 打开文件

方法一：open(文件路径,打开方式)，返回一个可操作对象。可以进行读写

```python
f = open('./index.txt','w')
```

常见的文件打开方式：

![image-20201023201840433](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201023201840433.png)

方法二：with open(文件路径，打开方式) as 变量名

使用这种方式打开，程序会自动关闭文件

```python
with open('./index.txt','r+') as file:
    print(file.read())
```



#### 操作文件

（1）read()---------读取文件中的所有内容

```python
f = open('./index.txt','r+')
result = f.read()
print(result)
f.close()
```

（2）readable()-------查看该文件是否可读，返回True或者False

```
f = open('./index.txt','r+')
result = f.readable()
print(result)
f.close()
```

（3）readline()------打印一行数据，并且指针会停留在下一行

```python
f = open('./index.txt','r+')
result1 = f.readline() #打印第一行数据
print(result1)
result2 = f.readline() #打印第二行数据
print(result2)
f.close()
```

（4）readlines()-----打印所有内容，并且返回一个列表。每一行的内容为一个元素

```python
f = open('./index.txt','r+')
result1 = f.readlines()
print(result1)
f.close()
```

（5）write()------在文件中写入数据

```python
f = open('./index.txt','r+')
f.write('hello\nmy name is ouyi\ni am 18 years old')
f.close()
```

（6）close()--------关闭文件。注意使用open方式打开的文件，必须在最后使用close()来关闭掉

### （3）json格式转换

![image-20201023204917443](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201023204917443.png)

#### 方法

（1）json.dumps()----------字典，列表转化为字符串流。这种字符串流可以用于与其他语言进行数据交换

```python
import json

data1 = {
    'name':'ouyi',
    'age':18,
    'gender':'男'
}
data2 = ['ouyi',18,'男']
js1 = json.dumps(data1)
print(js1)
print(type(js1))
js2 = json.dumps(data2)
print(js2)
print(type(js2))
结果：
{"name": "ouyi", "age": 18, "gender": "\u7537"}
<class 'str'>
["ouyi", 18, "\u7537"]
<class 'str'>
```

（2）json.loads()------将字符串流转化为字典，列表

```python
import json

data1 = {
    'name':'ouyi',
    'age':18,
    'gender':'男'
}
data2 = ['ouyi',18,'男']
js1 = json.dumps(data1) #将json（字典）转化为字符串流
print(js1)
print(type(js1))
js2 = json.dumps(data2) #将json（列表）转化为字符串流
print(js2)
print(type(js2))
js3 = json.loads(js1) #将字符串流转化为json（字典）
print(js3)
print(type(js3))
js4 = json.loads(js2) #将字符串流转化为json（列表）
print(js4)
print(type(js4))
结果：
{"name": "ouyi", "age": 18, "gender": "\u7537"}
<class 'str'>
["ouyi", 18, "\u7537"]
<class 'str'>
{'name': 'ouyi', 'age': 18, 'gender': '男'}
<class 'dict'>
['ouyi', 18, '男']
<class 'list'>
```

（3）json.dump()--------将字典，列表转化为字符串流，并保存到文件中

```python
import json

data1 = {
    'name':'ouyi',
    'age':18,
    'gender':'男'
}
json.dump(data1,open('./index.txt','w'))
```

（4）json.load()-------打开一个文件，并把文件中的字符串流转化为字典，列表

```python
import json
data1 = json.load(open('./index.txt','r'))
print(data1)
print(type(data1))
结果：
{'name': 'ouyi', 'age': 18, 'gender': '男'}
<class 'dict'>
```

# 七.python的错误与异常

![image-20201023221037140](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201023221037140.png)

## try

格式：如果代码块1没有出现异常，会执行代码块3和代码块4。如果代码块1出现异常，那么会执行代码块2和代码块4

```
try:

​		代码块1

except:

​		代码块2（代码块1出错时，执行）

else:

​		代码块3（代码块1没有出错时，执行）

finally:

​		代码块4（代码块1不论是否出错，都执行）
```

except后面可以加上异常名字，这样会只捕捉指定的异常。如果不加会捕捉所有异常

```python
try:
    a = int(input('请输入一个整数'))
    b = int(input('请输入一个整数'))
    print(a/b)
except Exception as e:
    print('出现异常',e)
else:
    print('程序没有异常')
finally:
    print('程序结束')
```

## 自定义异常

（1）所有raise自定义抛出异常。

```python
a = int(input('请输入一个数字5-10的数字'))
if a < 5 or a > 10:
    raise Exception('数字必须在5-10之间')
```

（2）自定义异常类

```python
class ErrorNumber(Exception):
    """自定义异常类"""
    def __init__(self):
        pass
    def __str__(self):
        return '数字必须在5-10之间'

a = int(input('请输入一个数字5-10的数字'))
if a < 5 or a > 10:
    raise ErrorNumber()
```

# 八.面向对象

## 1.什么是面向对象

![image-20201024195403791](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201024195403791.png)

![image-20201024195547972](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201024195547972.png)

## 2.类，类方法，类变量

![image-20201024195824211](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201024195824211.png)

```python
# 定义类
class SayName():
    # 定义类变量
    haha = 'haha'

    # 定义类方法
    def __init__(self,name): # 类中内置的一种方法，完成对类的初始化操作
        self.name = name

    def sayname(self): # 自定义类方法
        return 'Hello,my name is {}'.format(self.name)

    def __str__(self): # 类中内置的一种方法，当我们实例化调用该类时，返回的就是这个方法的返回值
        return '调用SayName成功'


#调用类
print(SayName('OUYI').haha) #调用类变量
print(SayName('OUYI').sayname()) #调用类方法
print(SayName('OUYI')) #实例化调用类

结果：
haha
Hello,my name is OUYI
调用SayName成功
```

# 九.python中常用的标准库

## 1.操作系统相关：os

### os.mkdir(文件目录路径)--------创建文件目录

```python
import os
os.mkdir('testdir')
```

### os.listdir(目录路径)------列出所有的文件和目录（相当于ls）

```python
print(os.listdir('./'))
注意：返回的是一个列表
```

### os.removedirs(目录路径)-----删除文件目录

```python
os.removedirs('./testdir')
```

### os.getcwd()---------获取当前路径（相当于pwd）

```python
print(os.getcwd())
```

### os.path.join(路径1，路径2)--------将两个路径拼接起来

```python
os.path.join('test1','test2')
```

### os.path.exists(路径)-------判断指定的文件或文件夹是否存在，返回True或者False

```python
print(os.path.exists('test'))
```

## 2.时间相关：time

![image-20201024204733931](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201024204733931.png)

### time.asctime()-----获取国外格式的时间

```python
import time
print(time.asctime())
```

### time.time()-------获取当前时间戳，以秒为单位

```python
import time
print(time.time())
```

### time.sleep(数字)-----等待多少秒

```python
import time
time.sleep(5)
```

### time.localtime(时间戳)---------将时间戳，转化成时间元组。默认是当前的时间戳

```python
import time
print(time.localtime())
结果：
time.struct_time(tm_year=2020, tm_mon=10, tm_mday=24, tm_hour=20, tm_min=52, tm_sec=23, tm_wday=5, tm_yday=298, tm_isdst=0)
```

### time.strftime(“%Y-%m-%d %H-%M-%S”,time.localtime())--将时间元组，转化成自定义的格式

```python
print(time.strftime('%Y-%m-%d %H-%M-%S', time.localtime()))
结果：
2020-10-24 20-55-28
```

# 十.多线程

## 1.概念

![image-20201024220134927](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201024220134927.png)

![image-20201024220532835](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201024220532835.png)

![image-20201024220844302](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201024220844302.png)

![image-20201024221017310](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201024221017310.png)

## 2.代码实现

### （1）单线程模式

```python
import time
import logging

#实例化一个日志输出对象
logging.basicConfig(level=logging.INFO) #输出info级别的日志

# 获取当前时间
def local_time():
    return time.strftime('%Y-%m-%d %H-%M-%S',time.localtime())

#任务1
def loop1():
    logging.info('start loop1 at ' + local_time())
    time.sleep(5)
    logging.info('end loop1 at ' + local_time())

#任务2
def loop2():
    logging.info('start loop2 at ' + local_time())
    time.sleep(5)
    logging.info('end loop2 at ' + local_time())

if __name__ == "__main__":
    loop1()
    loop2()
    
结果：
INFO:root:start loop1 at 2020-10-24 22-30-23
INFO:root:end loop1 at 2020-10-24 22-30-28
INFO:root:start loop2 at 2020-10-24 22-30-28
INFO:root:end loop2 at 2020-10-24 22-30-33
```

我们可以发现，使用单线程时，是任务1执行完后，再执行任务2。耗时较长

### （2）多线程

查看其他资料（哈哈）

#### 使用threading模块创建子线程

方法一：通过 threading.Thread 直接在线程中运行函数；

```python
import time
import logging
import threading

#实例化一个日志输出对象
logging.basicConfig(level=logging.INFO) #输出info级别的日志

# 获取当前时间
def local_time():
    return time.strftime('%Y-%m-%d %H-%M-%S',time.localtime())

#任务
def loop(i):
    logging.info('start loop'+str(i)+' at '  + local_time())
    time.sleep(5)
    logging.info('end loop'+str(i)+' at '  + local_time())

if __name__ == "__main__":
    # 创建一个列表，用来存放线程
    threads = []
    # 创建子线程，并放置到线程列表中
    for i in range(0,2):
        t = threading.Thread(target=loop,args=(i,))
        threads.append(t)
    # 启动子线程，执行任务
    for i in range(0,2):
        threads[i].start()
    # 检测每一个子线程是否释放，确保所有子线程都释放后，主线程才结束
    for i in range(0,2):
        threads[i].join()
```

常用的命令：

threading.Thread(target=任务函数,args=(函数的参数))------------常见一个子线程，返回一个线程对象

线程对象.start()-------------启动该线程

线程对象.join()--------------等待线程对象结束，常用于主线程等待子线程释放后，再结束。

#### 通过继承 threading.Thread 类来创建子线程

这种方法只需要重载 threading.Thread 类的 run 方法，然后调用 start()开启线程就可以了

```python
import time
import logging
import threading

#实例化一个日志输出对象
logging.basicConfig(level=logging.INFO) #输出info级别的日志

class LoopThread(threading.Thread):
    def __init__(self,i):
        threading.Thread.__init__(self)
        self.i = i

    # 获取当前时间
    def local_time(self):
        return time.strftime('%Y-%m-%d %H-%M-%S', time.localtime())

    # 任务
    def run(self):
        logging.info('start loop' + str(self.i) + ' at ' + self.local_time())
        time.sleep(5)
        logging.info('end loop' + str(self.i) + ' at ' + self.local_time())

if __name__ == "__main__":
    # 创建一个列表，用来存放线程
    threads = []
    # 创建子线程，并放置到线程列表中
    for i in range(0,2):
        t = LoopThread(i)
        threads.append(t)
    # 启动子线程，执行任务
    for i in range(0,2):
        threads[i].start()
    # 检测每一个子线程是否释放，确保所有子线程都释放后，主线程才结束
    for i in range(0,2):
        threads[i].join()
```

# 十一.python外部源文件处理

## 1.常用的外部数据源

![image-20201025214618096](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201025214618096.png)

## 2.yaml的读写

需要pip install PyYAML

### （1）yaml文件格式

基本格式：

- 大小写敏感
- 使用缩进表示层级关系
- 缩进时不允许使用Tab键，只允许使用空格。
- 缩进的空格数目不重要，只要相同层级的元素左侧对齐即可

数据类型

- 字典

  

  ![image-20201025233055442](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201025233055442.png)

- 列表

  - 在yaml中的格式：

  ![image-20201025234038326](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201025234038326.png)

  - 在python中对应格式：

  ```
  [['group1', 'group2', 'group3'], ['group4', 'group5']]
  ```

- 描点和引用

  - 在yaml'文件中：

  ![image-20201101231339813](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201101231339813.png)

  - 在python中：

  ```
  {
  'coment':{
  'host':'localhost',
  'port':3306,
  'company':'HW'
  },
  'development':{
  'host':'localhost',
  'port':3306,
  'company':'HW',
  'database':'myapp_dev'
  },
  'test':{
  'host':'localhost',
  'port':3306,
  'company':'HW',
  'database':'myapp_test'
  }
  }
  ```

### （2）yaml.load()

从yaml中读取内容，并转化为python对应的数据格式

```python
import yaml
result = yaml.safe_load(open('./sss.yml'))
print(result)
```

### （3）yaml.dump()

将python格式的数据，保存到yaml中

```python
import yaml
with open('./hhh.yml','w') as f:
    yaml.safe_dump(data={'a':[1,2]},stream=f)
```

结果：

![image-20201025234723790](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201025234723790.png)

## 3.json的读写

参考第六节：输入与输出

## 4.excel的读写

### （1）安装

```python
pip install openpyxl
```

### （2）使用

### 创建对象（工作簿）

场景1：创建一个新的Excel文档

```python
from openpyxl import Workbook

# 实例化一个workbook对象，用于创建，打开excel
wb = Workbook()
wb.save('test1.xlsx')
```

场景2：打开一个已有的excel文档

```python
from openpyxl import Workbook,load_workbook

# 实例化一个workbook对象，用于创建，打开excel
wb =load_workbook('test1.xlsx')
```

### Workbook对象属性（工作簿操作）

写excel内容：

1.打开一个新的工作簿-------Workbook()

2.创建一个execl表单页----Workbook().create_sheet(sheet名字，位置)-------不指定位置的话，默认在最后一页

3.添加或者修改sheet页的内容：

- ​		方法1：sheet页[编号 例如：'A3'] = 内容

```python
from openpyxl import Workbook,load_workbook
wb =Workbook() # 实例化一个workbook对象，用于创建，打开excel
wb1 = wb.create_sheet('ouyi') # 创建一个sheet页
wb1['A1'] = 'OUYI' #添加内容到excel
wb1['B2'] = 'haha' #添加内容到excel
wb.save('test2.xlsx') #保存工作薄
```

- ​		方法2：sheet页.cell(row=6,column=3,value=88888888)：添加修改-----row表示行；column列表示

```python
from openpyxl import Workbook,load_workbook
wb =Workbook() # 实例化一个workbook对象，用于创建，打开excel
wb1 = wb.create_sheet('ouyi2') # 创建一个sheet页
for lie in range(1,11): # 写入excel内容
    for hang in range(1,11):
        wb1.cell(row=hang,column=lie,value='ouyi')
wb.save('test2.xlsx') #保存工作薄
```

- ​		方法3：sheet页.append(['X','Y','Z',...])-----------在末尾一行添加内容

```python
from openpyxl import Workbook,load_workbook
wb =Workbook() # 实例化一个workbook对象，用于创建，打开excel
wb1 = wb.create_sheet('ouyi2') # 创建一个sheet页
wb1.append(['ouyi','ojbk','afa'])
wb.save('test2.xlsx') #保存工作薄
```

读取excel内容

1.wb.sheetnames  输出表单页名称，返回列表

```python
from openpyxl import Workbook,load_workbook
wb =load_workbook('test2.xlsx') # 实例化一个workbook对象，用于创建，打开excel
print(wb.sheetnames)
结果：
['Sheet', 'ouyi2']
```

2.wb【sheet页名称】【单元格】.value---------获取对应单元格的内容

```python
from openpyxl import Workbook,load_workbook
wb =load_workbook('test2.xlsx') # 实例化一个workbook对象，用于创建，打开excel
result = wb['ouyi2']['A1'].value
print(result)、
结果：
ouyi
```

# 十二.python虚拟环境

## 1.linux环境下配置虚拟环境

### **（1）安装虚拟环境相关的包**

1）sudo pip install virtualenv #安装虚拟环境

2）sudo pip install virtualenvwrapper #安装虚拟环境扩展包

3）编辑家目录下面的.bashrc文件，添加下面两行。

***\*export WORKON_HOME=$HOME/.virtualenvs\****

***\*source /usr/local/bin/virtualenvwrapper.sh\****

4）使用source .bashrc使其生效一下。

### **（2）创建使用虚拟环境**

1）创建虚拟环境命令：

​	mkvirtualenv 虚拟环境名

2）创建python3虚拟环境：

mkvirtualenv -p python3 bj11_py3

3）进入虚拟环境工作：

​	workon 虚拟环境名

4）查看机器上有多少个虚拟环境：

​	workon 空格 + 两个tab键

5）退出虚拟环境：

​	deactivate

6）删除虚拟环境：

​	rmvirtualenv 虚拟环境名

## 2.Windows环境下配置虚拟环境

### （1）安装虚拟环境相关的包

1）pip install virtualenv #安装virtualenv 模块

###   (2)创建使用虚拟环境

1）virtualenv 虚拟环境名 #创建虚拟环境

2） virtualenv  -p C:\Users\Administrator\AppData\Local\Programs\Python\Python35\python.exe 虚拟环境名 #创建指定python解释器的虚拟环境

3）激活虚拟环境：

```shell
 cd 虚拟环境目录
 cd Scripts
 activate.bat
```

4）退出虚拟环境

```css
deactivate.bat
```