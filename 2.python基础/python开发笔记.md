# python知识

## 认识和了解Python

#### 第一个Python程序

- 安装Python
- 配置环境变量
- 编写Python程序的方法
  - DOS下编写
  - 记事本编写
  - IDE编写

#### Python中的注释

- 作用
  - 用来给程序员看的，增强文件可读性来使用的
- 分类
  - 单行
  - 多行(文档)
- 问题
  - 支持中文，如果出现问题，可以尝试在首行加入coding = 'utf-8'解决

#### 变量以及类型

- 定义/初始化/赋值
- 使用案例

```
#实现购物小票

```

- 变量类型
  - int
  - float
  - bool
  - complex
  - str
  - list
  - tuple
  - dict
  - set
- 变量使用的注意事项：
  - 注意:定义变量的时候，而且它已经有数据的情况下，系统自动决定了它的类型
    如果想查看变量的类型，可以使用 type(变量名)进行查看

#### 标示符和关键字

- 概念
  - 开发人员在程序中自定义的一些符号和名称
    如变量名、函数名、类名
- 规则
  - 由字母(包括中文)、下划线和数字组成，且数字不能开头
    不能为系统关键字、大小写敏感
- 技巧
  - 见名知意
    - max_value
  - 驼峰命名
    - 大驼峰
      - UserName
    - 小驼峰
      - userName
    - 下划线连接
      - user_name
- 关键字
  - 关键字罗列
    - and as assert	break class continue def del elif else	except exec finally	for	from		global if in import	is	lambda not	or pass	print		raise return try whilewith		yield	
  - 关键字查询
    - import keyword
    - keyword.kwlist

#### 输出

- 普通的输出

```
print("Helloworld")
```

- 格式化输出

```
print("我今年10岁")
print("我今年11岁")
print("我今年12岁")
//格式：
age = 10
print("我今年%d岁"%age)
name="小明"
print("我的名字叫:%s,今年%d岁"%(name,age))
```

- 常见格式输出：
  - %d / %i    有符号的十进制整数
  - %u		 无符号的十进制整数
  - %o		八进制整数
  - %x		十六进制整数
  - %f		浮点数
  - %g		%f的简写

- 换行输出"\n"

```
print("我的名字叫:%s,\n今年%d岁"%(name,age))
```

- 练习
  - 完成自我介绍的输出（制表符 "\t"）

#### 输入

- raw_input()
- input()

#### 运算符

- 算术运算符

  - ‘+’	：加
  - ‘-’	：减
  - ‘*’	：乘
  - ‘/’	：除
  - ‘//’	：取整除  

  ```
  9 // 2 = 4
  9.0 // 2.0 = 4.0
  ```

  - ‘%’	：取余
  - ‘**’	：幂     

  ```
  2 ** 3 = 8
  ```

- 赋值运算符

  - 单独的赋值运算符 

    - ‘=’： 赋值			 

    ```
    a = 20,b,c = 2,3
    ```

  - 复合赋值运算符

    - ‘+=’	:	

    ```
    a += b等价于  a = a + b
    ```

    - ‘-=’	:
    - ‘*=’	:
    - ‘/=’	:
    - ‘%=’	:
    - ‘**=’	:
    - ‘//=’	:

#### 数据类型转换

- int(x,[,base])	将x转换为一个整数
- float(x)		将x转换为一个浮点数
- complex(real,[,imag])	创建一个复数
- str(x)		将x转换为字符串
- repr(x)		将对象x转换为表达式字符串
- eval(str)		用来计算在字符串中的有效python表达式，并返回一个对象
- tuple(s)		将序列s转换为一个元组
- list(s)		将序列s转换为一个列表
- hex(x)		将一个整数转换为一个十六进制的字符串
- oct(x)		将一个整数转换为一个八进制的字符串

#### 判断语句介绍 if

- 语法：

```
if 要判断的条件:
    条件成立时，要做的事情
例：如果你的年龄满18岁了，可以做点什么
```

注意：代码的缩排，可以使用tab键完成

- 练习：（import random）

```
生成一个随机值，完成骰子结果大还是小的展示
```

#### 比较、关系运算符

- ==	:检查两个操作数的值是否相等，如果相等返回True，否则返回False
- !=	:检查两个操作数的值是否相等，如果值不等，则条件为True
- ‘>=’	:
- ‘<=’	:
- ‘> ’	:
- ‘< ’	:

#### 逻辑运算符

- and	:  与     表达式1  and  表达式2  两个表达式都成立，结果为True
- or	:  或     表达式1  and  表达式2  两个有一个表达式成立，结果为True
- not	:  非	    not 表达式	与表达式的值相反

#### 推荐书籍

- 电子书

## 语句（分支循环）

#### if-else

- 语法格式：

```
if 条件：
    满足条件要做的事情1
    满足条件要做的事情2
    满足条件要做的事情3
    ...
else:
    不满足条件要做的事情1
    不满足条件要做的事情2
    不满足条件要做的事情3
    ...
```

- 案例
  - 骰子大小
  - 用户登陆

#### if-elif-else

- 使用场景：
  - 如果满足条件1时，做事情1
  - 如果满足条件2时，做事情2
  - 否则，做事情3
- 语法格式：

```
if 条件1:
    事情1
elif 条件2：
    事情2
else:
    事情3
```

- 案例练习：
  - 练习1：季节划分
  - 练习2：分数评级
- 注意事项;
  - elif不能单独使用

#### if的嵌套

- 使用场景（进地铁站）

```
if  安检合格：
    可以进入地铁站
    if 有地铁卡：
        直接刷卡进站
    else:
        购买临时卡
else ：
    接受检查
```

- 语法格式

```
if 条件1
    满足条件1做的事情
    if 条件2
        满足条件2做的事情
```

- if嵌套案例
  - 用户登陆(密码+短信验证码)

#### 猜拳游戏（石头、剪刀、布）

- 无嵌套方案1

```
result=input("石头0 剪刀1 布2\n")
computer=random.randint(0,2)
if (computer==0 and result == 2)  or (computer == 1 and result == 0) 
or (computer == 2 and result == 1):
	print("你赢了")
elif computer == result:	
	print("平局")
else:
	print("你输了")
```

- 嵌套方案2

```
# 电脑出石头的时候
if cmp == 0:
    # 如果你也出的石头
    if you == 0:
        # 平局
        print("平局，都是石头")
    # 如果你出的剪刀
    elif you == 1:
        print("很遗憾，你输了，电脑出的石头，你出的剪刀")
    # 如果你出的布
    elif you == 2:
        print("恭喜，你赢了，电脑出的石头，你出的布")
elif cmp == 1:
    if you == 0:
        print("恭喜，你赢了，电脑出的剪刀，你出的石头")
    elif you == 1:
        print("平局，都是剪刀")
    elif you == 2:
        print("很遗憾，你输了，电脑出的剪刀，你出的布")
elif cmp == 2:
    if you == 0:
        print("很遗憾，你输了，电脑出的布，你出的石头")
    elif you == 1:
        print("恭喜，你用了，电脑出的布，你出的剪刀")
    elif you == 2:
        print("平局，都是布")
```

#### 循环语句

- 使用场景

  - 四驱车
  - 排风扇
  - 樱木花道的99次表白
  - 结论: 重复的事情，一般都是用循环来解决	

- while循环

  - while循环语法

  ```
  while 条件：
      条件满足时，做的事情1
      条件满足时，做的事情2
      迭代
      ...
  ```

  - 案例

  ```
  i = 0
  while i < 5:
      print("i=%d"%i)	
      i += 1
  ```

#### while循环的使用

- 求1 + 2 + 3... + 100的和
- 求1 + 2 + 3... + 100所有偶数的和

#### while循环的嵌套以及应用

- 语法格式

```
while 条件1：
    条件1满足时，做的事情1
    条件1满足时，做的事情2
    迭代
    ...
    while 条件2：
    条件2满足时，做的事情1
    条件2满足时，做的事情2
    迭代
```

- 嵌套循环练习1

```
    打印 如下图形
    *****
    *****
    *****
```

- 嵌套循环练习2

```
    打印 如下图形
    *
    **
    ***
    ****
    *****
```

- 嵌套循环练习3  
  ![image](https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1532531716884&di=6c9c1133cd12bcfddebb85e10fad9a57&imgtype=0&src=http%3A%2F%2Fimages.cnitblog.com%2Fblog%2F636291%2F201410%2F312219071445568.png)


#### for循环

- for循环的格式

```
for 临时变量 in range(start,end,step)/Iterable:
    循环条件成立执行的代码
else:
    循环条件不成立执行的代码
```

#### 循环控制

- break：
  - 结束当前循环
- continue：
  - 跳过本次循环	
- 案例break:

```
for ch in "HelloWorld":
        print("-------------")
        if ch == 'W':
            break
        print ch
```

- 案例 continue:

```
for ch in "HelloWorld":
        print("-------------")
        if ch == 'W':
            continue
        print ch
```

- 分别对照结果，思考二者的差别

#### 课后练习

```
使用循环、分支完成以下图形的打印
图1：
   *
  ***
 *****
图2：
   *
  ***
 *****
  ***
   *
```

## 字符串，列表，元组，字典

#### 字符串

用来存储用户名、密码的数据

- 字符串格式：
  - 双引号或者单引号中的数据，就是字符串

```
    name='chenduxiu' 
    #或者
    name="zhendexiu"
```

- 字符串输出
  - 格式控制符   "%s"

```
    #例：
    name=”xiaoming“
    profession ='学生'
    address="海淀区神州科技园B座2层"
    print '-'*40
    print("姓名:%s"%name)
    print("职业：%s"%position)
    print ("地址:%s"%address)
    print ('-'*40)
```

- 字符串输入

```
输入的内容 = input("需要输入的内容")
例:通过键盘输入用户名密码
注意：python2的输入为 raw_input()
```

- 下标和切片
  - 下标索引：就是指的编号，类似超市储物柜的编号，通过编号就能找到对应的东西

```
    #例如:
    name="xiaoming"
    aaa=0
    count = len(name)
    while aaa < count:
        print(name[aaa])
        aaa+=1
```

- 切片
  - 字符串，列表，元组都支持切片操作
  - 语法

```
    [起始:结束:步长]  区间位置：左闭右开
```


```
例：
    name=‘xiaoming’
    print(name[0:2])
    打印结果   "xi"
    name='0123456789'
    print(name[0:2])
    #从第二个取到最后
    print(name[2:])
    #从头开始取，直到索引值为3的位置(不包括该元素)
    print(name[:3])
    #从索引值为2的位置开始取，直到倒数第一个(不包括倒数第一个)
    print(name[2:-1])
    #从头开始取，每两个切出一个
    print(name[0::2])
    #倒序的内容输出
    print(name[::-1])
    #倒序切出索引5到索引值1中间的数据
    print(name[5:0:-1])
```

- 字符串常见操作

  - find/rfind

  ```
  #检查str是否包含在str1中，如果是返回开始的索引值，否则返回-1
  str1.find()
  str1="good good study,day day up"
  index = str1.find("stu")
  print(index)
  ```

  - index/rindex

  ```
  跟find()方法一样，只不过目标字符串如果不在要查找的字符串中会报一个异常
  ```

  - count

  ```
  返回str在目标字符串中start-end之间出现的次数
  str1="good good study,day day up"
  print(str1.count("good"))
  ```

  - replace

  ```
  把str1中指定的字符串"good",用“222”进行替换，最多替换2次	
  str1="good good study,day day up"
  print(str1.count("good"))
  str2 = str1.replace("good","222",2)
  print(str2)
  ```

  - split

  ```
  以" "为分割符切片str1
  str1="good good study,day day up"
  array = str1.split(" ")
  print(type(array))
  print(array)
  ```

  - capitalize

  ```
  把字符串的第一个字符大写
  print(str1.capitalize())
  ```

  - title	

  ```
  把字符串中的每一个单词的首字母大写
  print(str1.title())
  ```

  - startswith

  ```
  检查字符串是否以指定字符串开头,
  是则返回True，否则返回False
  例：判断是否为有效网址
  ```

  - endswith	

  ```
  检查字符串是否以指定字符串结尾,是则返回True，否则返回False	
  例：判断是否为有效邮箱
  ```

  - lower

  ```
  转换字符串中所有的大写字符为小写
  ```

  - upper

  ```
  转换字符串中所有的小写字符为大写
  ```

  - ljust

  ```
  返回一个原字符串左对齐，并使用空格填充至长度width的新字符
  
  ```

  ```
  str1 = "hello"
  print(str1.ljust(10))
  ```

  - rjust

  ```
  返回一个原字符串右对齐，并使用空格填充至长度width的新字符
  ```

  ```
  str1 = "hello"
  print(str1.rjust(10))
  ```

  - center

  ```
  返回一个原字符串居中对齐，并使用空格填充至长度width的新字符
  str1 = "hello"
  print(str1.center(10))
  ```

  - lstrip

  ```
  删除目标字符串左边的空格
  str1 ="    hello    "
  print(str1.lstrip())
  ```

  - rstrip

  ```
  删除目标字符串右边的空格
  str1 ="    hello    "
  print(str1.rstrip())
  ```

  - strip

  ```
  删除目标字符串两边的空格
  str1 ="    hello    "
  print(str1.strip())
  ```

  - rfind

  ```
  类似于find()函数,不过是从右边开始查找
  ```

  - rindex

  ```
  类似与index()函数，不过是从右边开始查找
  ```

  - partition

  ```
  把目标字符串分割成str前，str以及str后三部分，得到一个tuple(元组)
  str1="nihaoma"
   str1.partition("hao")
   ('ni', 'hao', 'ma')
  ```

  - rpartition

  ```
  从右边开始，把目标字符串分割成str前，str以及str后三部分，得到一个tuple(元组)
  str1="nihaoma"
   str1.partition("hao")
   ('ni', 'hao', 'ma')
  ```

  - splitlines

  ```
  将目标字符串按照行进行分割,返回一个列表
  str1 = "Hello\nWorld"
  print(str1.splitlines())
  运行结果：
  ['Hello', 'World']
  ```

  - isalpha

  ```
  判断目标字符串中是否所有的字符都为字母，返回True，或者False
  str1 = "123Hello"
  print(str1.isalpha())
  ```

  - isdigit

  ```
  判断目标字符串中是否所有的字符都为数字，返回True或者False
  str1 = "123Hello"
  print(str1.isdigit())
  ```

  - isalnum

  ```
  如果字符串中都是字母或者数字则返回True，否则返回False
  str1="abc123"
  print(str1.isalnum())
  ```

  - isspace

  ```
  如果字符串中只包含空格，则返回True，否则返回False
  ```

  - join

  ```
  将字符串或者列表，元组中的每个元素(字符)使用指定字符连接起来
  li=["one","two","three"]
  str2="_"
  str2 = str2.join(li)
  print(str2)
  ```

#### 列表介绍

- 引入： 
  - 如何存储班级中所有同学的名字?

- 语法格式：

```
names=["李大钊","陈独秀","蔡元培","陈佩斯"]
#注意：比C语言中的数组功能更强大，列表中的元素可以为不同类型
list1=[10,"人",2.5,True]
```

- 访问列表中的元素

  - 设置值

  ```
  list1[0] = 100
  ```

  - 获取值

  ```
  print(list[0])
  ```

- 列表的循环遍历

  - 使用for循环进行遍历

  ```
  #例：
  list1=[10,"人",2.5,True]
  for a in  list1:
      print(a)
  ```

  - 使用while循环进行遍历

  ```
  list1=[10,"人",2.5,True]
  length = len(list1)
  i = 0
  while i < length:
          print(list1[i])
          i += 1
  ```

- 列表的常见操作

  - 增

    - append

    ```
    #通过append向指定列表添加元素
    #例：
    list2 =["one",2,"san"]
    list2.append("four")
    print(list2)
    #结果：['one', 2, 'san', 'four']
    ```

    - extend

    ```
    #通过extend可以将一个列表中的元素逐个添加到另外一个列表中
    #例：
    l1=[1,2]
    l2=[3,4]
    l1.extend(l2)
    print(l1)
    #结果：[1, 2, 3, 4]
    ```

    - insert

    ```
    #insert(index,object)在指定的位置处插入元素object
    l1=[1,2]
    l2=[3,4]
    l1.extend(l2)
    print(l1)
    #结果：[1, [3, 4], 2]
    ```

  - 查

    - in

    ```
    如果存在，则返回True，否则返回False
    l1 =[1,2,3,4,5]
    print( 1 in  l1)
    ```

     - not in

    ```
    与in相反
    l1 =[1,2,3,4,5]
    print(1 not  in l1)
    ```

    - index

    ```
    返回元素在列表中的索引值
    index(obj)
    index(obj,fromIndex,toIndex)   区间位置为前闭后开
    如果没有列表中不包含查找元素，会报错
    ```

    - count

    ```
    #返回元素在列表中出现的次数
    list1 = [1,2,3]
    print(list1.count(1))
    ```

  - 删

    - del

    ```
    #根据下标进行删除
    #例：
    l1 = [2,3,4]
    del  l1[0]
    print(l1)
    #结果：[3,4]
    ```

    - pop

    ```
    #删除最后一个元素
    #例：
    l1 = [2,3,4]
    l1.pop()
    print(l1)
    #结果:[2,3]
    ```

    - remove

    ```
    #根据元素的值进行删除
    l1 = [2,3,4]
    l1.remove(2)
    print(l1)
    #结果:[3,4]
    ```

  - 改

  ```
  直接通过下标来修改元素
  例:  
  l1=[1,2]
  l1[0] = 100
  print(l1)
  结果：[100,2]
  ```

  - 排序以及列表反转

  ```
  #sort方法将list按特定顺序进行排列，默认为由小到大，参数reverse=True可改为倒序，由大到小
  #例:
  l1 = [2,4,1,9,23]
  l1.sort()
  print(l1)
  #结果:[1,2,4,9,23]
  l1.sort(reverse=True)
  print(l1)
  #结果为:[23,9,4,2,1]
  #反转方法： reverse()
  ```

#### 列表的嵌套

- 概念

```
一个列表中的元素，又是一个列表
```

- 嵌套列表的遍历

```
l1=[[1,2],4,[5,6]]
for l in l1:
    if type(l) == list:
        for ll in l:
            print(ll)
    else:
        print(l)
    print("-"*10)
```

- 练习

```
循环录入3个学生信息(包括name,age)
使用嵌套列表完成学生信息的存储

```


#### 元组

- 元组概念

```
Python的元组与列表类似，不同之处在于元组的元素不能修改，元组使用“()”
列表使用"[]"
```

- 操作

  - 访问

  ```
  t=(1,2,3)
  print(t[0])
  修改或者删除元素的话会报错：
  t[0]= 10
  删除报错：
  t.pop()
  但是可以变向进行删除
  tuple->list(进行删除操作)->tuple
  ```

#### 字典介绍

- 字典的引入

```
#如何存储将多个国家的简称及名字完成对应的存储？
#例如:   CN:中国	JP：日本		US:美国
country = {"CN":"中国","JP":"日本"}
```

- 字典中元素的访问：

  -  直接访问

  ```
  print(country['CN'])
  打印结果:"中国"
  如果没有"CN"这个key，则会报错
  ```

  - 通过get方法访问

  ```
  value=country.get('CN')
  #这时候value的值为 "中国"
  value = country.get('SH','中国')
  #这个意思是如果有key ‘SH’则得到对应值，没有的话，得到默认值"中国"
  ```

- 字典的常见操作1

  - 修改元素

  ```
  可以直接进行修改
  student={'name':'陈独秀','age':99}
  student['age']=100
  ```

  - 添加元素

  ```
  student['address']='北京市朝阳区'
  #如果字典中没有'address'这个key，则会将这个元素条件到字典中，如果已经包含这个key
  则新值会将旧值覆盖
  ```

- 删除元素

  -  del 删除

  ```
  #例：
  #删除某个key
  del student['age']
  #删除所有的键值对，删除之后，将不能在进行访问
  ```

  - clear  

  ```
  #清空所有的键值对，清除后依旧可以进行访问
  stu.clear()
  ```


- 字典的常见操作2

  -  len()  键值对个数的获取

  ```
  stu={'name':‘xiaoming’,'age':19}
  len(stu)
  #长度为2
  ```

  -  keys()

  ```
  #返回一个字典中所有的key的列表
  allKeys= stu.keys()
  for k in allKeys:
      print(k)
      print(allKeys[k])
  ```

  - values() 

  ```
  #返回一个包含字典所有value的列表
  stu.values()
  #['xiaoming',19]
  ```

  - items() 

  ```
  #返回一个包含所有(键、值) 元组的列表
  stu.items()
  #[('name','xiaoming'),('age',18)]
  ```

- 字典的遍历

  - 所有key的遍历

  ```
  stu={'name':'xiaoming','age':19}
  for key in stu.keys():
     	print(key)
  
  ```

  - 所有value的遍历

  ```
  stu={'name':'xiaoming','age':19}
  for value in stu.values():
  	print(value)
  ```

  - 所有item的遍历

  ```
  stu={'name':'xiaoming','age':19}
  for item in  stu.items():
      print(item)
  ```

  - 所有key和value的遍历

  ```
  stu={'name':'xiaoming','age':19}
  for key,value in stu.items():
      print(type(value))
      print("%s=%s"%(key,value))
  ```

#### 公共方法

- 公共运算符

  - '+'

  ```
  作用：合并、连接
  例:str1="hello"+"world"
  结果：”helloworld“
  list1=[1,2]+[3,4]
  结果：[1, 2, 3, 4]
  例：tuple1=(1,2) + (3,4)
  结果：(1,2,3,4)
  ```

  - '*'

  ```
  作用：复制
  例:  'hello' * 2
  结果: 'hellohello'
  例: [1,2] * 2
  结果：[1,2,1,2]
  例:(1,2) * 2
  (1,2,1,2)
  ```

  - in

  ```
  作用：元素是否存在
  例：
  result = '123' in 'HelloWorld123'
  print(result)
  result= 1 in [1,2]
  print(result)
  result = 2 in (1,2)
  result = 'name' in {'name':'xxx','age':12}
  print(result)
  ```

  - not in

  ```
  作用：元素书否不存在，用法跟in 一样
  ```

- python的内置函数

  - len 

  ```
  作用：得到元素的个数
  例：len([1,2])
  len((1,2))
  获取到的为键值对个数
  len({'name':'xiaoming','age':18})
  ```

  - max(...)

  ```
  作用：获取最大值
  例:
  max(1,2,3)
  max([1,2,3,4])
  找字典中的最大键
  a =max({'a':1,'b':2,'x':3})
  ```

  - min(...)

  ```
  作用: 获取最小值(用法与max一致)
  ```

  - del

  ```
  删除元素或者删除容器
  del 元素/容器变量名
  del list1[0]
  del list1
  ```

  - 变量.del()  

  ```
  #在python3中已经不存在这种用法
  list1 = [1,2,3]
  list1.del()
  ```


- 引用的使用

  - 什么是引用

  ```
  windows中的快捷方式
  家庭地址
  ```

  - 非引用类型案例：

  ```
  a = 10
  b = a
  print(id(a))
  print(id(b))
  b=100
  print(a)
  print(b)
  print(id(a))
  print(id(b))
  ```

  - 引用类型案例:

  ```
  list1 = [1,2,3]
  list2 = list1
  print(id(list1))
  print(id(list2))
  list2[0]=100
  print(list1)
  print(list2)
  print(id(list1))
  print(id(list2))
  ```

  - 引用类型内存图分析

#### 课后练习

```
有能力的同学用函数完成
学生管理系统：
1.添加学生
2.查询学生
3.删除学生
4.修改学生
5.退出系统
```

## 函数

#### 函数介绍

- 函数概念

```
一般情况下，某段代码需要反复使用多次，
而且这段代码又具备特定的功能，
我们会把这段代码组织成为单独的功能模块，
这个功能模块就可以叫做函数
```


- 函数的定义和调用

  - 函数的定义（函数可以重复调用，不能重复定义）

  ```
  语法格式：
  def  函数名():
      代码块...
  ```

  - 函数的调用

  ```
  调用格式:
  函数名()
  ```

- 练习 封装函数打印99乘法表：  

```
# 函数的定义
def show99():
    i = 1
    while i < 10:
        j = 1
        while j <= i:
            print("%d * %d = %d\t"%(j,i,i*j),end=" ")
            j += 1
        i += 1
        print("")
        # 函数的调用，只有调用函数，函数中的代码才会被执行
show99()
```

- 函数的文档说明

```
使用help(自定义方法名) 可以查看函数的文档说明
help(show99)
显示结果：
Help on function show99 in module __main__:
show99()
    # 函数的定义: 打印99乘法表
```

#### 函数的参数

- 定义带有参数的函数

```
语法格式：
def 方法名(形参...):
    代码块(带代码中，形参可以被理解为定义好的一个变量)
```

- 带参数的函数的调用

```
方法名(实际参数)
注意：参数的个数要匹配
```

- 练习 ： 

```
定义可以完成三个数字求和的方法，求从键盘录入的三个数字的和
```


#### 函数的返回值

- 什么叫做返回值（生活实例）

```
让同桌帮你买饭回来，对你来说，饭，就是返回值
```

- 开发中的返回值

```
两个数字求和函数，有时候，调用者只是想得到这个和。
```

- 带返回值函数的案例：

```
def getSum(a,b):
    c = a + b
    return c
#简化：
def getSum(a,b):
    return a + b
#调用
result = getSum(10,20)
#这时候的result就是得到的返回值
```

#### 四种函数的类型

- 无参数，无返回值
- 无参数，有返回值
- 有参数，无返回值
- 有参数，有返回值

#### 函数的封装强化练习

- 函数的嵌套调用

```
def test2():
    print("test2")
def test1():
    #调用函数2
    test2()
test1()
```

- 封装函数练习

  - 封装函数，完成自定义个数的*组成的直线

  ```
  比如：参数为5，打印出如下内容
  
  *****
  ```

  - 封装函数，完成 自定义行数的 上题 实现的直线

  ```
  例如：参数为3，打印如下效果
  
  *****
  *****
  *****
  ```

  - 封装函数

  ```
  封装求3个数字平均数的函数
  ```

#### 局部变量

- 概念

```
在函数内部定义，用来存储临时数据的变量，称为临时变量，形参也是局部变量
```

- 注意
  - 在函数内部定义，作用域为函数内部

  - 不同函数中可以存在同名变量，互不干涉，没有关系

#### 全局变量

- 概念

  - 既能在其中一个函数中使用，又能在其他函数中使用的变量，成为全局变量

  ```
  #例：
  a = 100
  def test1():
      print(a)
  def test2():
      print(a)
  ```

- 全局变量与局部变量同名问题

  - 可以重名

  ```
  a = 100
  def test():
      a = 200
      print(a)
  test()
  #这种写法是允许的，打印出的结果为“200”，访问的为离的近的
  ```

  -  函数内部修改全局变量问题

  ```
  a = 100
  def test():
       # global a(需要手动声明a 为全局的才可以进行修改)
      a += 10
      print(a)
  ```

如果在函数内部，想修改全局变量的值，需要手动将变量前使用global进行修饰（可变类型的全局变量，不需要修饰）

```
例:
a = [1]
def test():
   a.append(10)
   print(a)	
test()
```

#### 函数应用：图书管理系统

```
def showMenu():
    print("1.添加图书")
    print("2.查询图书")
    print("3.删除图书")
    print("4.修改图书")
    print("5.退出系统")
```

#### 函数的返回值二

- 多个返回值问题

```
允许多个返回值，本质利用的是元组
def divid(a,b):
    shang = a // b
    yushu = a % b
    return shang,yushu
value1,value2=divid(10,20)
print(value1)
print(value2)
```

#### 函数的参数二

- 缺省参数

```
# 缺省参数
def test3(a,b=10):
    print(a)
    print(b)
test3(100)
```

- 可变参数

```
# 可变参数  *tu	   元组形式
def test4(*tu):
    print(a)
test4(1)
test4(1,2,3)
test4([1,2,3])
test4((1,2,3))
# 可变参数 **kw    字典形式
def test5(**kw):
    print(kw)
test5(m=1,b=2)
```

- 引用参数（可以画图讲解）

  - 基本参数

  ```
  a=100
  # 在方法中修改变量的值
  def changValue(v):
      v = 200
  changValue(a)
  # 打印发现a的值依旧为100
  print(a)
  ```

  - 引用参数

  ```
  list1=[1,2,3]
  # 在函数中修改变量的值
  def changValue(v):
      v[0] = 100
  changValue(list1)
  # 打印发现list1的值变成了[100, 2, 3]
  print(list1)
  ```

#### 递归函数

- 递归概念

```
在函数中不是调用其他而是调用自身，这种调用方式，称为递归调用
```

- 递归的使用
  - 递归求 ∑100	
  - 求 n!

#### 匿名函数

- 概念

```
用lambda关键字创建的简单的没有函数
名的函数，这种函数不用def声明
```

- 语法

```
语法格式:
lambda  参数... :  表达式
sum = lambda args1,args2: args1+args2
print(sum(1,2))
#结果为：3
```

- 注意事项：
  -  在匿名函数中，不能有return
  -  可以有0、1、多个参数
  -  表达式计算后只能返回一个值

#### 课后练习

- 完善图书管理系统其他功能
- 封装函数：判断一个数字是否为质数
- 打印1-1000之间所有的质数，两个一排
- 封装函数：判断一个数字是否为水仙花数
- 打印所有的水仙花数

## 文件处理

####文件操作介绍

- 文件的概念
- 文件的作用
  - 数据持久化

#### 文件的打开与关闭

- 生活实例（文件的操作）

  - 打开work文档
  - 修改数据
  - 保存文件
  - 关闭word

  ```
  python编程中，操作文件也一样
  打开文件/创建文件
  读写文件
  关闭文件
  ```

- 打开文件

  - 函数语法

  ```
  open(文件名,访问方式)
  f = open('123.txt','w')
  ```

  - 作用
    - 打开已经存在的文件，或者创建一个新的文件

- 常用访问方式：

```
r	：只读	指向文件头	默认方式
w	：只写	已经存在会覆盖，没有则创建新的
a	：追加	存在，指向文件为，没有则创建新的
r+	：读写	指向文件的开头
w+	：读写	已经存在会覆盖，没有创建新的
a+	：读写   文件已存在，则指向文件尾部，
进行追加内容，没有则创建新文件
```

- 关闭文件

  - 函数语法

  ```
  文件.close()
  f = open('123.txt','a+')
  f.close()
  ```

#### 文件的读写

- 写数据

  - 语法

  ```
  使用函数write('要写入的内容')
  ```

  - 案例

  ```
  f=open('123.txt','w')
  f.write('Hello World!')
  f.close()
  ```

  - 练习 

  ```
  将你最喜欢的一首古诗写入到指定文件中
  循环写
  ```


- 读数据(read)

  - read(num)

  ```
  从指定的文件中读取长度为num的数据
  如果没有给num具体值，则读取所有(以
  字符串的形式返回)
  ```

  - 案例

  ```
  def readMethod():
      f = open('125.txt','r')
      result = f.read()
      # str 类型
      print(type(result))
      print(result)
      f.close()
  ```

- 读数据(readLines)

```
def readMethod1():
    f = open('125.txt','r')
    result = f.read()
# list 类型
    print(type(result))
    print(result)
    f.close()
```

- 读数据(readLine)

```
f = open('125.txt','r')
#读取一个第一行字符串出来
result = f.readline()
# str 类型
print(type(result))
print(result)
f.close()
```

#### 自定义文件复制工具（讲解思路）

- 思路讲解
  - 打开源文件，判断源文件是否有效，有效进行后续操作
  - 新文件名字的生成   旧文件名+[复件]+.后缀（用到查找rfind,以及切片操作）
  - 开始复制文件(1. 整体复制	2.循环逐行复制)
  - 关闭文件
- 代码

```
# 复制文件方法，旧文件[附件].后缀
def copyFile2(srcFileName):
    oldFileName = srcFileName
    # 先判断文件是否存在
    f = open(oldFileName, 'r')
    print(type(f))
    # 如果存在进行后续操作
    if f:
        # 截取出文件名字
        index= oldFileName.rfind('.')
        # 截取出文件后缀
        suffix = oldFileName[index:]
        # 新文件名为
        newFileName = oldFileName[:index]+'[复件]'+suffix
        newFile = open(newFileName,'w')
        content = f.read()
        newFile.write(content)
        newFile.close()
    f.close()
copyFile2('125.txt')
```

#### 文件的定位读写

- 获取当前的位置

  - 方法

  ```
  文件名.tell()
  可以获取文件指针当前在文件中的位置
  ```

  - 用法

  ```
  f = open('125.txt','r')
  content = f.read(3)
  position = f.tell()
  print("当前的位置为:%d"%position)
  content = f.read(4)
  position = f.tell()
  print("当前的位置为:%d"%position)
  ```


- 定位到某个位置

  - 方法

  ```
  seek(offset,from)
  offset:偏移位置
  from:三个值
  0:文件头
  1:当前位置
  2:文件位
  ```

  - 用法

```
例：从文件头跳过2个字节，复制3个字节
f = open('125.txt','r')
# 从文件头开始跳过2个字节
f.seek(2,0)
# 获取当前位置
position = f.tell()
print("当前位置:%d"%position)
# 读取2个字节
content = f.read(2)
print(content)
f.close()
```

```
例：从文件尾部取2个字节（如果是从尾部进行重定位的话，需要以二进制形式打开文件）
# 从文件尾读取2个字节（尾部操作，需要使用二进制的形式打开   b）
f = open('125.txt', 'rb')
# 从尾部往前偏移2个字节
f.seek(-2, 2)
content = f.read()
print(content)
```


#### 文件的重命名与删除

OS模块中的有对文件进行重命名以及删除的方法

- 文件重命名

  - 方法  

  ```
  rename('需要修改的文件名','新的文件名')
  ```

  - 用法

  ```
  #注意：要修改的文件一定要保证没有被其他占用
  import os
  os.rename('125.txt','127.txt')
  ```

- 文件的删除

  - 方法

  ```
  remove(待删除文件的名字)
  ```

  - 用法

  ```
  import os
  remove('126.txt')
  ```

#### 文件的相关操作

同样需要导入os模块

- 创建文件夹

  - 方法

  ```
  mkdir()
  ```

  - 用法

  ```
  import os
  os.mkdir()
  ```

- 获取当前目录

  - 方法

  ```
  getcwd()
  ```

  - 用法

  ```
  import os
  os.getcwd()
  ```

- 改变默认目录

  - 方法

  ```
  chdir()
  ```

  - 用法

  ```
  import os
  os.chdir("要修改到的默认目录")
  ```

- 获取目录列表

  - 方法

  ```
  listdir('指定文件夹')
  ```

  - 用法

  ```
  import os
  os.listdir('d:/2018教学')
  ```

- 删除文件夹

  - 方法

  ```
  rmdir('文件夹路径')
  ```

  - 用法

  ```
  import os
  os.rmdir('陈独秀文件夹')
  ```

#### 代码行数统计器

- 统计某个文件中的代码行数，忽略注释

```
# 统计一个xxx.py中所有的代码
def getNumberOfCodeLines(filename):
    count = 0
# 后边的encoding='utf-8' 解决中文读取问题
    f = open(filename, 'r', encoding='utf-8')
    if f:
        # 如果文件存在,开始统计
        content = f.readline()
        while content != '':
            if not content.startswith("#"):
                count += 1
            content = f.readline()
    return count
```

- 打印一个文件夹中所有的文件名(递归解决)

```
def showAllFilesInDir(dirName):
    listfiles = os.listdir(dirName)
    for file in listfiles:
        # 文件路径为 文件夹名字+文件名
        newpath = dirpath+"/"+ file
        # 如果是文件夹
        if os.path.isdir(newpath):
            # 递归调用自己
            showAllFilesInDir(newpath)
        elif os.path.isfile(newpath):
            print(newpath)
```

#### 课后练习

 图书管理系统（数据持久化版,知识拓展）

## 面向对象1

#### 面向过程与面向对象

- 开车问题
- 吃饭问题
- 做饭问题

#### 类与对象	

- 类的概念

```
将具有共同特征以及共同行为的一组对象进行抽象，抽象出来的东西，就有一个概念：类
类就相当于制造盖楼使用的设计图
```

- 对象的概念

```
某一个具体的存在，看得见的，摸的着的
例如：望京soho（猪腰子），中央电视台总部大楼(大裤衩)
```

- 练习： 区分类与对象

```
奥迪汽车
张三停在车库的奥迪A8
雅迪
人
咱班坐在xx的xx
笔记本
thinkPad
小明的thinkPad
```

- 类的组成

```
类名
属性：（静态） 一组数据
方法：（动态）运行调用的函数
```

- 设计练习

```
封装人类：
属性：年龄、性别、年龄
行为：吃、睡、学习
封装狗类：
属性：品种、名字、颜色
行为：叫、跑、睡觉
```

- 抽象的练习
  - 王者荣耀团战图片面向对象分析
  - 绝地求生图片面向对象分析

#### 类的定义

```
语法:
class 类名:
方法列表
案例：
class Person:
# 自我介绍方法
    def introduce(self):
        print("我的名字叫:%s,今年%d岁了"%(self.name,self.age))
注意：
也有类似使用(新式类，手动指明了父类为谁)
class Person(object):
def xxxx():
....
类的命名规则：
大驼峰  Person、 Cat、Dog...
```

#### 创建对象

```
封装好类，等于是画好了图纸，下边就
可以开始根据图纸进行一座座楼房的建造了
```

- 语法格式

```
对象名 = 类名()
p = Person()
```

- 案例

```
class Person:
    # 自我介绍方法
    def introduce(self):
        print("我的名字叫:%s,今年%d岁了"%(self.name,self.age))
# p = Person('ss',12)
# 创建对象
p = Person()
# 添加属性，并给属性赋值
p.name = '陈独秀'
# 如果在这调用方法，会报错，因为在方法的调用中，访问了age属性，但是，目前对象中还没有该属性
# p.introduce()
# 添加属性，并给属性赋值
p.age = 30
# 调用对象的方法
p.introduce()
```


```
注意：
对象包含属性和方法两部分
第一次p.name 是给对象添加属性，之后再访问，则是修改属性的值
```

#### __init__方法

- __init__引入

```
每次创建对象，都需要手动添加属性，创建多个对象，这些操作要进行多次，
有没有简便的方式，创 建每一个对象，都自动包含了这些属性
答案： 有，__init__方法的使用
```

- __init__方法的使用

```
class Dog:
# 创建对象时，该方法会被默认调用（代码验证）
    def __init__(self):
        self.name='大黄'
        self.age = 2
    def showInfo(self):
        print('name:%s,age：%d'%(self.name,self.age))
# 创建对象之后，没有手动添加属性
dog = Dog()
# 调用对象方法没有报错，说明已经对象中已经包含了name跟age两个属性
dog.showInfo()
```

```
思考：
属性的值是固定的，能不能创建对象时，
直接完成赋值，答案，可以，见 5.3
```

- 自定义参数的使用

```
class Dog:
#给__init__方法增加参数，第一个self为默认参数，python解释器自动传递值
    def __init__(self,name,age):
        self.name = name
        self.age = age
    def showInfo(self):
        print('name:%s,age：%d'%(self.name,self.age))
# '大黄'与 2分别是name与age的实际参数
dog = Dog('大黄',2)
dog.showInfo()
```

- 练习： 

```
完成一个Student类的封装，包含属性：name,age,gender 方法：study()，eat()
创建对象并直接赋值(通过__init__方法完成)，调用方法测试
```

- magic方法

  ```
  在python中，有一些内置好的特定的方法，这些方法在进行特定的操作时会自动被调用，称之为魔法方法
  ```

  - 打印id

  ```
  class Dog:
      def __init__(self,name,age):
          self.name = name
          self.age = age
      def showInfo(self):
          print('name:%s,age：%d'%(self.name,self.age))
  dog = Dog('大黄',2)
  print(dog)
  打印结果：
  <__main__.Dog object at 0x0000000002839E10>
  ```

- 定义__str__()方法

```
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    def showInfo(self):
        print('name:%s,age：%d' % (self.name, self.age))
    def __str__(self):
        # 使用'+'只能拼接字符串
        message = "我的名字:" + self.name + ",我的年龄:" + str(self.age)
        return message
dog = Dog('大黄', 2)
# dog.showInfo()
# 这时候会打印__str__方法中return的数据
print(dog)
```

#### self 关键字的使用

- 表示意义：

```
可以理解为自己，类似与Java、C++中的this指针，表示对象自身
注意：
某个对象调用方法时，python解释器会把这个对象做为第一个参数，传递给self，也就是
哪个对象调用该方法，self表示的是谁
```

- 用法：

  - 添加/访问属性
  - 访问当前类中的其他方法

  ```
  见案例：
  class Dog:
      def __init__(self,name,age):
          # self作用，访问/添加属性
          self.name = name
          self.age = age
      def showInfo(self):
          print("name:%s,age:%d"%(self.name,self.age))
          # 直接访问当前类中其他方法会报错
          # shout()
          # 访问当前类中的其他对象方法
          self.shout()
      def shout(self):
          print("汪汪汪~")
  ```

  ```
  # 定义一个函数
  def printDog(dog):
      # 判断dog为Dog的类的对象(做容错处理，防止函数调用直接给一个字符串参数抛出异常)
      if isinstance(dog,Dog):
          print("是dog对象")
          # 函数中调用Dog类中的方法
          dog.showInfo()
  # 创建对象
  dog1 = Dog('大黄',2)
  dog2 = Dog('小黑',1)
  # 调用函数
  printDog(dog1)
  printDog(dog2)
  # 如果没有使用  isinstance(对象，所属类)，这行代码会导致报错
  printDog("123")
  ```

#### 隐藏数据（属性私有）

- 修改属性的方式

  - 直接修改
  - 间接修改(通过方法修改)

  ```
  class Hero:
      def __init__(self,name,gender,age):
          # self.__name = name
          self.setName(name)
          self.__gender = gender
          # self.__age 可以将属性保护起来，类的外部无法访问
          # self.__age = age
          self.setAge(age)
      def setName(self,name):
          self.__name = name
      def setAge(self,age):
          if age > 0:
              self.__age = age
          else:
              print("年龄不合理，设置默认年龄1")
              self.__age = 1
      def __str__(self):
          return  'class:Hero'+'['+self.__name+','+self.__gender+','+str(self.__age)+']'
  h1 = Hero('陈独秀','男',-100)
  # 直接修改不合理，可以给任意值
  # 属性保护之后，无法通过直接访问的方式进行访问，有利于数据安全
  h1.age = -200
  print(h1)
  ```

#### 面向对象练习之回合制小游戏

- 面向对象练习

```
类的封装： 普通攻击，跟技能攻击,
技能需要封装新的类
随机模块的使用 
import random
```

#### 工厂模式(面向对象封装练习)

- 概念

```
工厂模式是我们最常用的实例化对象模式了，是用工厂方法代替传统的直接创建对象的一种模式
```

- 用法

```
非工厂模式:
公司招聘<--------------------------->学生
工厂模式:
提需求	      满足条件
公司招聘<-------> 学校<----------->学生
class Company(object):
    def __init__(self,name):
        self.name = name
    # 公司招聘方法
    def recruitment(self,subject):
        self.subject = subject
        print(self.name+"公司需要招聘"+self.subject+"人才")
        # 通过委托学校进行招聘
        self.school = School()
        # 招聘要求为公司的要求:  subject
        stu = self.school.cultivate(self.subject)
        return  stu
class Student():
    def __init__(self):
        self.skill = None
        pass
class StudentPython(Student):
    def __init__(self):
        self.skill = 'Python'
        pass
    def __str__(self):
        return '[' + '我擅长 Python'+']'
class StudentJava(Student):
    def __init__(self):
        self.skill = 'Java'
        pass
    def __str__(self):
        return '[' + '我擅长 Java' + ']'

class School(object):
    # 工厂方法：根据需求不同，返回不同的对象
    def cultivate(self,requement):
        self.requement = requement
        if self.requement == 'python':
            return StudentPython()
        elif self.requement == 'java':
            return StudentJava()

# 招聘公司
com = Company('中科软')
# 根据科目招聘
stu = com.recruitment('python')
print(stu)
```

#### __new__方法（单例模式就会用到重写__new__方法）

- 魔法方法

```
_new__，在创建对象时候，由python解释器调用，不能手动调用
```

-  一定要有参数

```
至少要有一个参数 'cls'，代表要实例化的类，实际参数，在实例化时，由python解释器自动提供
```

-  一定要有返回值


```
如果要重写new方法时，要特别注意，可以return 父类__new__出来的实例，也可以直接return
object的__new__出来的实例
```


```
class AAA(object):
    def __init__(self):
        print("init方法")

    def __new__(cls):
        print("这是new方法")
        # return object.__new__(cls)
        return super().__new__(cls)
AAA()

执行结果：
这是new方法
init方法
```

-  init方法

```
__init__方法有一个参数self，这个就是__new__方法返回的实例，__init__作用
是给对象进行初始化操作，__init__不需要返回值
```

#### 单例模式

- 概念

```
是一种常用的软件设计模式，应用该模式的类一个类只有一个实例，即一个类只有一个对象实例。
```

- 用法

```
因为创建对象时，会默认调用__new__,以及__init__方法，所以，需要重写这两个方法完成
注意点： 对象唯一，只进行一次初始化
#  保证创建对象的唯一性，需要重写__new__方法
```


```
class SingleClass(object):
    # 用来保证对象唯一
    __single = None
    # 用来保证初始化工作只第一次有效
    __firstInit = False
    def __new__(cls,name,age):
        if not cls.__single:
            cls.__single = super().__new__(cls)
        return cls.__single
    def __init__(self,name,age):
        if not  self.__firstInit:
            self.name = name
            self.age = age
            self.__firstInit = True
a = SingleClass('aaa',12)
b = SingleClass('bbb',13)
# 分别查看a与b的地址
print(id(a))
print(id(b))
# 验证是否只有第一次初始化生效
print(a.age)
print(b.age)
# 验证对象值是否统一修改
a.age = 19
print(b.age)
```

- 作用

```
保障全局过程中，只使用一个对象
```

## 异常

#### 异常的引入

-  概念

```
异常就是不正常，当python检测到一个错误时，解释器就无法继续执行下去了，
反而出现了一些错误的提示，这就是所谓的异常。
```

#### 捕获异常

- try---except

  ```
  案例：从键盘输入被除数与除数，求商并打印
  ```

  - 传统解决方法
  - 使用异常处理的解决方法

- except 多个异常

  - 多个异常分开写(注意异常<父子>类的顺序)

  ```
  try:
  	<语句>        
  except <异常类名字>：
  	<语句>        
  except <异常类名字>:
  	<语句>        
  else:
      #如果没有异常发生
  	<语句>  
  ```

  - 多个异常写到一个元组中

  ```
  try:
      代码
  except(Exception1[,Exception2[,...ExceptionN]]]):
     	发生以上多个异常中的一个，执行这块代码
  ''''
  ```

- 获取异常信息

```
try:
    f = open('124.txt', 'r')
    f.write('HelloWorld')
#将捕获到的异常存储到到变量errMsg中
except IOError as errMsg:
    print(errMsg)
```

- 捕获所有异常

  - except 不带任何异常

  ```
  try:
      a = 2/0
  except:
      print("遇到异常")
  ```

  - except 父类Exception

  ```
  try:
      b = 3/0
  except BaseException as result:
      print(result)
  ```

- 捕获异常中else的用法

```
try:
    b = 3/1
except BaseException as result:
    print(result)
else:
    # 可以访问b的值
    print("没有遇到异常,结果为:%d"%b)
```

- try--- finally
  finally顾名思义： 最终，最后的意思

    - 用处

    ```
    确保最后一定要执行的，比如：文件关闭、数据库关闭、socket关闭，等...
    ```

    - 案例：（文件关闭问题）

    ```
    try:
        f = open('123.txt', 'r')
        # 如果遇到异常，后续代码不再执行，直接执行except模块
        f.write('HelloWorld')
        # 在这关闭文件是否合适
        f.close()
    except IOError as errMsg:
        print(errMsg)
    else:
        print("写入文件成功")
    finally:
        # 最终一定要关闭文件（打印，验证是否执行）
        f.close()
        print("finally，文件关闭")
    ```


#### 异常的传递

- 案例

  ```
  def test1():
      print("-" * 10 + "test1开始" + "-" * 10)
      print(aa)
      print("-" * 10 + "test1结束" + "-" * 10)
  def test2():
      print("-" * 10 + "test2开始" + "-" * 10)
      test1()
      print("-" * 10 + "test2结束" + "-" * 10)
  def test3():
      print("-" * 10 + "test3开始" + "-" * 10)
      try:
          test2()
      except:
          pass
      print("-" * 10 + "test3结束" + "-" * 10)
  test3()
  ```

#### 抛出自定义异常

-  自定义异常

```
通过创建一个新的异常类，程序可以命名它们自己的异常。
异常应该是典型的继承自Exception类，通过直接或间接的方式
# 自定义异常类，直接或者间接继承Exception
class GenderException(Exception):
    def __init__(self):
    super().__init__()
        # args  为BaseException的属性
        self.args = '性别只能为男或者女'
        # 也可以自定义一个属性
        self.msg = '性别只能为男或者女'
```

- 手动抛出自定义异常

```
语法： raise [Exception [, args [, traceback]]]
```


```
class Student(object):
    def __init__(self, name, gender, age):
        self.__name = name
        self.setGender(gender)
        self.__age = age
    def setGender(self, gender):
        if gender == '男' or gender == '女':
            self.__gender = gender
        else:
            # 抛出一个自定义的性别异常(也可以以列表的形式抛出多个异常)
            # raise [GenderException(), Exception()]
            raise GenderException()
try:
    stu1 = Student('大黄', '男1', 18)
except GenderException as e:
    # 打印自定义的信息
    print(e.msg)
    # 打印父类属性的信息
    print(e.args)
```

## 模块

#### 模块介绍

- 概念
  - Python 模块(Module)，是一个 Python 文件，以 .py 结尾，包含了 Python 对象定义和Python语句。
- 作用
  - 模块让你能够有逻辑地组织你的 Python 代码段。
  - 把相关的代码分配到一个模块里能让你的代码更好用，更易懂。
  - 模块能定义函数，类和变量，模块里也能包含可执行的代码。

#### 模块使用

 - 模块的引入

   - 引入语法

   ```
   import module1[, module2[,... moduleN]
   导入多个模块的话，逗号隔开就可以
   比如要引用模块random，就可以在文件最开始的地方用 import random 来引入。
   ```

   - 调用语法 

    ```
    模块名.函数名(参数)
    print(random.randint(1,6))
    ```

注意：一个模块只会被导入一次，不管你执行了多少次import

- 模块中函数，变量，类的引入

  - from…import 语句 语法

  ```
  from modname import name1[, name2[, ... nameN]]
  ```

  - from…import 语句 案例

  ```
  from MyTools import  showTenRandomNumber,showTenRandomNumber1
  #Python 的 from 语句让你从模块中导入一个指定的部分到当前命名空间中
  导入之后，被导入的方法可以直接使用方法名完成调用，不再需要模块名
  showTenRandomNumber()
  showTenRandomNumber1()
  ```


- 模块中所有内容的引入

  - from…import *  语法

  ```
  from modname import *
  ```

  - from…import *  案例

  ```
  from  MyTools import *
  # 直接通过函数名就可以完成调用
  showTenRandomNumber()
  showTenRandomNumber1()
  print(PI)
  ```


#### 自定义模块的制作

- 封装任意一个工具类()

#### 模块的测试

- 测试代码

```
在模块中，完成代码的测试
```

- 使用模块

```
导入模块，发现模块中的测试代码会先执行一次，
解决方案：给测试代码加判断条件:    
if __name__ == '__main__':
    pass
__name__ ：python解释器主动执行的代码才会为'__main__'
```

- __all__的用法（python3之后不建议使用）

  - import  不受影响
  - from 模块  import *

  ```
  使用from 模块  import *  只会导入__all__中包含的方法
  __all__ = ['showTenRandomNumber']
  ```

#### Python中的包

- 概念

```
包是一个分层次的文件目录结构，它定义了一个由模块及子包，
和子包下的子包等组成的 Python 的应用环境，包中要包含一个__init__.py模块
```

- 新的模块名

```
包名.模块名
```

- 包中模块的导入方式

```
import package1.module1
或者
from  package1 import module1
```

- 包中数据的访问方式

```
package.module1.moduleTest1()
```

- _ _ init_ _.py 的内容	

```
__init__.py 也是一个模块，可以在模块中写任意代码
首次使用包的时候,__init__.py会默认执行一次
也可以写：
from . 模块1 import *
from . 模块2 import *
这样在导入包的时候，__init__.py中的代码会默认执行

这样的好处是： 可以直接导入包
弊端，如果两个包中有同名变量，会出问题
```


#### 模块的发布

- 为什么要发布

  - 查找顺序(sys.path)
  - 安装到系统目录下

- 怎么发布？

  - 要发布的目录结构（uft-8格式）

  ```
  |----setup.py
  |----package1
        |----module1
        |----module2
  |----package2
        |----module3
        |----module4
  ```

  - 编辑setup文件

  ```
  from  distutils.core import setup
  setup(name='压缩包的名字',version='1.0',description='描述',
  author='大卫',py_modules=['package1.模块1','package1.模块2',
  'package2.模块1'])
  ```

  - 构建模块

  ```
  DOS窗口找到该文件
  python setup.py build   
  ```

  - 生成发布压缩包

  ```
  python setup.py sdist
  ```

#### 自定义模块的安装、使用

- 安装的方式
  - 找到模块的压缩包
  - 解压
- 进入文件夹
- 执行命令 python setup.py install

```
注意：如果在install的时候，
指定目录安装，可以使用
python setup.py install --prefix=安装路径
```

#### 暴力安装

- 直接将包复制到site-packages

#### 模块导入问题

- 如何导入模块：

  ```
  import sys
  如何查看该模块路径：
  print(sys.path)
  如何要导入的模块在[sys.path]中没有，则可以通过
  sys.path.append("相对路径/绝对路径")
  可以使用ipython测试，也可以使用IDE测试
  ```

- 模块重复导入

  ```
  问题：（该问题在集成IDE中不存在）
  先导入一个模块
  在导入之后，目标模块被修改
  在之前导入的地方，使用模块还是修改之前的模块没有即使更新
  ```

  - 如何解决重复导入问题：
    - 导入 imp包
    - from imp import *  导入 imp包中的所有方法
    - 调用方法reload(模块名)
  - 模块循环导入

## 核心编程

#### == 与 is的比较

- 意义	

  ```
  '=='用来比较两个值是否相等
  'is'用来表示两个变量是否同一个
  ```

- 案例验证

  ```
  a = [1,2,3]
  b = [1,2,3]
  a == b
  a is b
  #基本数据验证
  a=256
  b=256
  a is b
  a == b
  [-5 256]范围内的数字为同一个值
  ```

#### 深拷贝与浅拷贝问题

- 深浅copy概念

  ```
  嵌套列表复制时，如果为深copy,会递归复制列表
  浅copy只复制当前列表
  当列表元素为基本元素时，浅拷贝和深拷贝效果一样
  ```

- 举例验证

  ```
  a = [1,2,3]
  b  = a
  print(id(a))
  print(id(b))
  import copy
  c = copy.copy(a)  #浅拷贝  两个id不一样
  d = copy.deepcopy(a)  #深拷贝
  print(id(c))
  print(id(d))
  
  3.3 嵌套列表深copy的问题
   思考：
  a = [1,2,3]
  b = [4,5,6]
  c = [a,b]
  d = copy.deepcopy(c)
  e = c.copy()
  修改a的值
  a.append(100)
  print(c) #结果为[[1,2,3,100],[4,5,6]]
  print(d)  #结果为[[1,2,3,100],[4,5,6]]
  print(e)  #结果为[[1,2,3],[4,5,6]] 浅拷贝完成后，a的变化不会同步更新。即浅拷贝不会拷贝元素的地址。只会拷贝第一层对象
  ```

  - 画内存图分析：	

- 元组嵌套列表的复制问题

- 注意：

  - 如果是元组进行copy操作，只能得到一个指向元组的一个引用
    代码验证


#### 进制问题

- 常用进制以及进制取值范围

- 原码、反码、补码

  ```
  +1   加上  -1  和不为0的问题（以补码的形式进行计算）
  0000 0001		+1
  1000 0001		-1
  
  正数的（原码=反码=补码）
  负数的
  原码：符号位 -1表示负数
  反码：符号位不变，其他取反
  补码：反码+1
  从补码->原码的方式也是一样（符号位不变，取反+1）
  ```

- 进制转换问题

  - 十进制->其他进制

    ```
    bin(num)  #转换为二进制
    oct(num)  #转换为八进制
    hex(num)  #转换为十六进制
    ```

  - 其他进制->十进制

    ```
    int('0b10010',2)
    int('0o22',8)
    int('0x12',16)
    ```

#### 位运算

直接操作二进制，省内存，效率高

- 按位与 " & "

  - 两个操作数同为1，结果才为1，否则为0

- 按位或 " | "

  - 两个操作数，有一个为1，结果就为1，同为0的时候，为0

- 按位异或 " ^ "

  - 两个操作数相同为0，不同为1

- 按位取反 " ~ "

  ```
  1.先得到数字的补码(数字以补码的形式存在的)
  2.进行取反操作，得到取反之后的补码
  3.既然为补码，之后，需要回到人能认识的码型，因此，需要转换为原码
  4.除符号位，进行取反操作
  5.进行+1操作，得到原码
  ```


- 按位左移 " << "
  - 左移n位乘以2^n
- 按位右移 " >> "
  - 右移n位 除以2^2

#### 属性私有化问题

- xx:
  - 共有变量
- _x;
  - 单前置下划线，私有属性或者方法,from somemodule import *禁止导入，
    不同模块中导入另外一个模块（使用import导入），模块中的_x成员变量，
    可以进行访问

- __x:
  - 双前置下划线，属性，方法私有，无法继承，无法在类外访问
    不是真正意义上的私有化，只是python解释器默认给修改了名字
    这种成为名字重整
    修改规则：比如__age会被修改为_类名__age
    通过这个名字可以实现访问，但不提倡
    stu = Student(12)
    dir(stu)可以查看对象内所有属性，方法

- __ xx __:
  - 双前后置下划线，一般用于魔法方法，自定义的方法应避免
- xx_:
  - 单置后下划线，一般用于避免与变量冲突

#### property的使用1

- 私有属性合成对应的set、以及get方法

- property的引入

  - 注意先写get方法，在写set方法，只写方法名，不是方法调用

  ```
  使property升级get和set用法
  class Money():
      def __init__(self):
          self.__money = 0
      def getMoney(self):
          return self.__money
      def setMoney(self,money):
          if isinstance(money,int):
              self.__money = money
          else:
              raise Exception("金钱类型有误")
  # 手动合成
      money = property(getMoney,setMoney)
  m = Money()
  m.money = 100
  print(m.money)
  ```

- 使用property取代get和set方法	

  ```
  get方法在前，set方法在后
  学名：装饰器
  @property 
  @money.setter 
  class Money():
      def __init__(self):
          self.__money = 0
      @property
      def money(self):
          return self.__money
      @money.setter
      def money(self, money):
          if isinstance(money, int):
              self.__money = money
          else:
              raise Exception("金钱类型有误")
  m = Money()
  m.money = 100
  print(m.money)
  ```

####位运算

计算机的计算都是使用位运算，也就是转换为二进制运算
1.<<左移--------(a << n)表示a*2的n次方
print(2 << 2)-----8
原理：0000 0010 （<<2） 0000 1000=8
2.>>右移-------（a >>n）表示a/2的n次方
print(64 >> 3)----8
原理：0100 0000 （>>3）0000 1000=8
3.& 按位与
print(5 & 4)----4
原理：



#### 生成器

- 概念

  ```
  在Python中， 一边循环一边计算的机制， 称为生成器： generator 
  创建生成器: G = ( x*2 for x in range(5)) 
  可以通过 next(生成器) 函数获得生成器的下一个返回值
   没有更多的元素时， 抛出 StopIteration 的异常 
  生成器也可以使for 循环，因为生成器也是可迭代对象
  ```

- 生成器 生成的第一种方式

  ```
  list2 = [x for x in range(10)]
  print(type(list2))
  # 得到一个生成器对象
  g = (x*2 for x in range(10))
  print(type(g))
  # 打印生成器生成的第一个数字
  print(next(g))
  print(next(g))
  print(next(g))
  一共10个数字，打印超出报StopIteration异常
  ```

- 生成器应用

  - 使用循环求斐波那契的第n个数

  ```
  def feibo(items):
      a, b, n  = 1, 1, 3
      while n <= items:
          if items == 1 or items == 2:
              return 1
          else:
              a, b = b, a + b
              print(b, end=" ")
              n += 1
      return b
  print(feibo(4))
  ```

  - 生成器的第二种生成方式  yield

  ```
  def feibo(items):
      a, b, n = 1, 1, 3
      while n <= items:
          if items == 1 or items == 2:
              return 1
          else:
              a, b = b, a + b
              # 关键字yield让该函数变成生成器
              yield b
              n += 1
      return b
  # 得到的是生成器对象
  g = feibo(5)
  print(type(g))
  print(next(g))
  # 使用生成器调用__next__()方法,等价于next(g)
  print(g.__next__())
  print("--------for循环遍历结果---------")
  # 可以使用for循环遍历生成器
  for a in g:
      print(a)
  ```

  - 生成器之send()用法

  ```
  def test():
      i = 0
      while i < 5:
  #赋值运算下次会被执行  yield会使程序停住
          temp = yield i
          print(temp)
          i += 1
  g = test()
  print("-----send----")
  print(g.__next__())
  print(next(g))
  print(g.send("aaa"))
  运行结果：
  -----send----
  0
  None
  1
  aaa
  2
  ```

  - 首次调用send()异常问题

  ```
  def test():
      i = 0
      while i < 5:
          temp = yield i
          print(temp)
          i += 1
  g = test()
  print("-----send----")
  # 首次调用不传参或者传递非None参数都会导致异常
  print(g.send())
  print(g.send("aaa"))
  解决方案：
  1.首次调用使用__next__()，不使用send()
  2.或者首次使用send(None)
  ```

  - yield完成多任务

  ```
  需求： 先存钱，再取钱，两个任务交替进行
  def test1():
      while True:
          print("存钱")
          yield None
  def test2():
      while True:
          print("取钱")
          yield None
  t1 = test1()
  t2 = test2()
  while True:
      t1.__next__()
      t2.__next__()
  ```


- 好处

  ```
  需要新的数字，就生成一个新的，不同于列表，需要一下子全出来，
  更占用内存
  ```

#### 迭代器

```
迭代是访问集合元素的一种方式。 迭代器是一个可以记住遍历的位置的对象 。
迭代器只能往前不会后退
```

- 可迭代对象（Iterable）

  ```
  集合数据类型， 如 list 、 tuple 、 dict 、 set 、 str 等 
  成器和带 yield 的generator function
  这些可以直接作用于for循环的对象成为可迭代对象：Iterable
  ```

- 如何判断对象是可迭代对象（Iterable）

  ```
  可以使用isinstable()判断一个对象是否为可迭代对象
  导包:
  from collections import Iterable
  list1 = [x for x in range(5)]
  print(isinstance(list1,Iterable))
  案例：
  分别验证，列表，字典，元组，字符串，生成器是否为可迭代对象
  ```

- 迭代器（Iterator）

  ```
  可以被next()函数调⽤并不断返回下⼀个值的对象称为迭代器
  可以使用isinstance(对象,Iterator)判断对象是否为迭代器
  from collections import Iterator 
  isinstance((x for x in range(10)), Iterator) 
  案例验证： 列表，字典，字符串，元组,生成器是否为迭代器对象
  ```

- iter()函数

  ```
  分别验证将列表，字典，元组，字符串转换为迭代器，使用next()进行访问
  ```

#### 闭包1

- 什么是闭包？

  ```
  内部函数对外部函数作用域内变量的引用（非全局变量） ， 则称内部函数为闭包
  三个条件，缺一不可：
  1)必须有一个内嵌函数(函数里定义的函数）——这对应函数之间的嵌套
  2)内嵌函数必须引用一个定义在闭合范围内(外部函数里)的变量——内部函数引用外部变量
  3)外部函数必须返回内嵌函数——必须返回那个内部函数
  ```

- 案例：完成一个闭包的定义以及基本使用（nonlocal）

```
    # 定义一个外部函数
    def funcationout(num1):
        print("out start")
        # 函数内定义另外一个函数
        def funcationin(num2):
            # 并且在函数中用到了外部的变量(非全局变量)num2
            result = num1 + num2
            print("in----")
            print(result)
            return result
        print("out end")
        # 外部函数的返回值为内部函数名（内部函数的引用）
        return funcationin
    # 调用外部函数,得到一个指向内部函数的变量（闭包）
    infunc = funcationout(100)
    # 外部函数中的变量，没有随着函数的结束而释放，
    # 而是在闭包中可以随时进行调用
    infunc(200)
    infunc(1)
```

- 以上代码执行内存分析
  - 画图分析

#### 闭包2

- 闭包的作用

  ```
  闭包主要是在函数式开发过程中使用
  可以根据外部作用域的局部变量来得到不同的结果
  ```

- 闭包作用案例验证

  ```
  比如：求一个点到其他点之间的距离（不使用闭包，使用闭包分别验证）
  from math import *
  # 不使用闭包需要4个参数
  def disbtwpoint(x1,y1,x2,y2):
      return sqrt(pow(x1 - x2, 2) + pow(y1 - y2, 2))
  # 不使用闭包的调用求距离函数
  print(disbtwpoint(0,0,10,10))
  print(disbtwpoint(0,0,20,10))
  
  def disout(x1,y1):
      def disin(x2,y2):
          return sqrt(pow(x1-x2,2)+pow(y1-y2,2))
      return disin
  # 闭包getdis
  getdis = disout(0,0)
  # 获取点10,10到坐标（0,0）的距离
  print(getdis(10,10))
  # 获取点20,10到坐标（0,0）的距离
  print(getdis(20,10))
  ```


#### 装饰器1

- 装饰器简介

  ```
  装饰器本质上是一个Python函数，它可以让其他函数在
  不需要做任何代码变动的前提下增加额外功能，装饰器的返回值也是一个
  函数对象。它经常用于有以下场景，比如：插入日志、性能测试、
  事务处理、缓存、权限校验等场景。装饰器是解决这类问题的绝佳设计，
  概括的讲，装饰器的作用就是为已经存在的对象添加额外的功能
  ```

- 装饰器的解决日志问题（分三个版本）

  - v1.0版本解决

    ```
    def fun1():
        print("日志记录")
        print("使用功能1")
    
    def fun2():
        print("日志记录")
        print("使用功能2")
    ```

  - v2.0版本解决

    ```
    def writeLog():
        pass
    def fun1():
        writeLog()
        print("使用功能1")
    def fun2():
        writeLog()
        print("使用功能2")
    ```

  - v3.0版本解决

    ```
    def outfunc(func):
        def infunc():
            writeLog()
            func()
        return infunc
    def fun1():
        print("使用功能1")
    def fun2():
        print("使用功能2")
       
    # 注意名字的问题，需要分析
    fun1 = outfunc(fun1)
    # 装饰器(闭包)
    fun1()
    ```

  - v4.0版本解决 简化装饰器

    ```
    def outfunc(func):
        def infunc():
            writeLog()
            func()
        return infunc
    @outfunc
    def fun1():
        print("使用功能1")
    @outfunc
    def fun2():
        print("使用功能2")
    
    fun1()
    fun2()
    ```

#### 装饰器2

- 多个装饰器问题

  ```
  def add1(fc):
  print("add1正在装饰")
      def wrapped():
          return "《"+fc()+"》"
      return wrapped
  def add2(fc):
  print("add2正在装饰")
      def wrapped():
          return '*'+fc()+'*'
      return wrapped
  #看到这个，开始进行装饰，而不是等到调用时
  @add1
  @add2
  def test1():
      return '金陵十三钗'
  print(test1())
  打印结果：
  add2开始装饰
  add1开始装饰
  《*金陵十三钗*》
  ```

- 对有参数的函数进行装饰

  - 固定个数的参数

    ```
    def func(fn):
        print("func")
        def func_in(aa, bb):
            print("func_in1")
            fn(aa,bb)
            print("func_in2")
        return func_in
    @func
    def test(a, b):
        print("a=%d,b=%d" % (a, b))
    # 装饰器装饰之后，这不是直接调用test方法，而是调用func_in方法
    test(1,2)
    ```

  - 不固定个数的参数

    ```
    def func(fn):
        print("func")
        def func_in(*args,**kwargs):
            print("func_in1")
            # 注意参数类型，原封不动的继续使用
            fn(*args,**kwargs)
            print("func_in2")
        return func_in
    @func
    def test1(a,b,c,d):
        print("a=%d b=%d c=%d d= %d"%(a,b,c,d))
    test1(1,2, 3, 4)
    ```

#### 装饰器3

- 通用装饰器

  ```
  def func(fn):
      # 需要有参数，*args,**kwargs
      def func_in(*args,**kwargs):
          print("记录日志")
          print('访问方法:'+fn.__name__)
          # 需要有参数，*args,**kwargs
          xx = fn(*args,**kwargs)
          # 需要有返回值
          return xx
      return func_in
  
  # 待装饰函数：无参数，无返回值
  @func
  def test1():
      print("test1")
  test1()
  @func
  def test2():
      return "Hello"
  print(test2())
  @func
  def test3(a):
      print('a=%d'%a)
  test3(1)
  ```

#### python动态添加属性方法

```
动态编程语言是 高级程序设计语言 的一个类别， 在计算机科学领域已被广泛应用。
 它是指类 在 运行时可以改变其结构 的语言 ： 例如新的函数、 对象、甚至代码可以被引进，
 已有的函数可以被删除或是其他结构上的变化。
```

- 运行过程中给对象、类添加属性、添加方法

  ```
  class Person():
      def __init__(self,name,age):
          self.name = name
          self.age = age
  # 给类添加属性
  Person.score = 1000
  p1 = Person('xxx',20)
  print(p1.score)
  #单独定义一个函数 run 
  def run(self):
      print("%s在跑"%self.name)
  # 使用这种方式进行绑定
  p1.run = run
  # 在这调用直接报错
  # p1.run
  import types
  # 将run方法与对象进行绑定
  p1.run = types.MethodType(run,p1)
  # 完成调用，解决问题
  p1.run()
  ```

- types.MethonType的使用

  ```
  p1.run = types.MethodType(run,p1)
  即使换成
  xxx = types.MethodType(run,p1)
  xxx()调用一样还用
  因为之前提示缺少参数，主要是不知道self到底是谁，
  而types.MethodType(run,p1)则是告诉解释器，self指的就是p1
  ```

- 添加静态方法以及类方法

```
@staticmethod
def staticfunc():
    print("---static method---")
Person.staticfunc = staticfunc
Person.staticfunc()
@classmethod
def clsfunc(cls):
    print('---cls method---')
Person.clsfunc = clsfunc
Person.clsfunc()
```

#### __slots__的作用

```
class Person():
    # 限定Person类中，只能拥有name，跟age，如果添加新的属性，会报错
    # 注意，只能限定当前类，对子类不好使
    __slots__ = ('name','age')
代码验证
```

#### 元类

- 类也是对象(属于元类的对象)

  ```
  #打印字符串(字符串是对象)
  print("HelloWorld")
  #打印类名,类同样为一个对象
  print(Person)
  ```

- 使用动态创建类：

  - 语法：

  ```
  type(类名，由父类名称组成的元组（可以为空），包含属性的字典（名称和值）)
  ```

  ```
  案例1：使用type创建类
  Myclass = type("MyClass3",(),{})
  m1 = Myclass()
  print(type(m1))
  ```

  ```
  案例2：使用type创建带有属性(方法)的类
  def show(self):
      print("---num---%d"%self.num)
  #  使用元类(type)创建类
  Test = type("Test",(),{"show":show})
  t = Test()
  t.num = 100
  t.show()
  ```

  ```
  案例3:使用type动态创建一个继承指定类的类
  class Animal():
      def __init__(self,color="Yellow"):
          self.color = color
      def eat(self):
          print("吃死你")
  Dog = type("Dog",(Animal,),{})
  dog = Dog()
  dog.eat()
  print(dog.color)
  ```

#### 类装饰器

```
class Test(object):
    def __init__(self,func):
        print("--初始化--")
        print("func name is %s"%func.__name__)
        self.__func = func
    # 重写该方法后，对象可以直接进行调用
    def __call__(self):
        print("--装饰器中的功能--")
        self.__func()
# @Test 等价于  test = Test(test) 装饰器特性
@Test
def test():
    print('--test 函数---')
# 本身test指向函数test，但是装饰器将test指向了对象。
#  对象本身不可以被调用，但是重写__call__方法之后则会被调用
test()
执行结果：
--初始化--
func name is test
--装饰器中的功能--
--test 函数---
```

## 内存管理

#### 对象池

 什么叫做垃圾回收？
生活案例

- 小整数池

  - 系统默认创建好的，等着你使用
  - 概述
    整数在程序中的使用非常广泛，Python为了优化速度，使用了小整数对象池， 
    避免为整数频繁申请和销毁内存空间。Python 对小整数的定义是 [-5, 256] 
    这些整数对象是提前建立好的，不会被垃圾回收。在一个 Python 的程序中，
    无论这个整数处于LEGB(局部变量，闭包，全局，内建模块)中的哪个位置，
    所有位于这个范围内的整数使用的都是同一个对象。

  ```
  案例：(必须使用终端验证，pycharm每次都是所有代码都加载到内存中，
  被看成是一个整体)
  代码验证小整数
  a = 100
  print(id(a))
  del a
  b = 100
  print(id(b))
  发现删除a后，b的地址依旧是删除之前的那个地址(是否删除，小整数都常驻内存)
  ```

- 大整数池
  默认创建出来，池内为空的，创建一个就会往池中存储一个

    ```
    案例验证
    代码验证大整数
    a = 1000
    b = 1000
    print(id(a))
    print(id(b))
    #a,b的id不一样
    ```

- intern机制

  - 每个单词(字符串)，不夹杂空格或者其他符号，默认开启intern机制，共享内存，靠引用计数决定是否销毁

  ```
  案例验证:
  a = 'HelloWorld'
  b = 'HelloWorld'
  print(a is b)
  
  a = 'Hello World'
  b = 'Hello World' 
  print(a is b)
  ```


#### 垃圾收集

```
概述：
现在的高级语言如java，c#等，都采用了垃圾收集机制，
而不再是c，c++里用户自己管理维护内存的方式。自己管理内存极其自由，
可以任意申请内存，但如同一把双刃剑，为大量内存泄露，悬空指针等bug埋下隐患。
python里也同java一样采用了垃圾收集机制，不过不一样的是:
python采用的是引用计数机制为主，标记-清除和分代收集两种机制为辅的策略
```

- 引用计数

  引用计数的几种方法：

  ​		获取引用计数

  ​				sys.getrefcount(对象)---查看对象被几个东东调用

  ​		增加引用计数

  ​				将对象计入列表

  ​				将对象赋值给新的对象

  ​				将对象作为形参

  ​		减少引用计数

  ​				从列表中移除

  ​				del 对象

```
python里每一个东西都是对象，它们的核心就是一个结构体：PyObject
 typedef struct_object {
 	  	int ob_refcnt;
 		struct_typeobject *ob_type;
	} PyObject;
PyObject是每个对象必有的内容，其中ob_refcnt就是做为引用计数。
当一个对象有新的引用时，它	的ob_refcnt就会增加，当引用它的
对象被删除，它的ob_refcnt就会减少
#define Py_INCREF(op)   ((op)->ob_refcnt++) //增加计数
	#define Py_DECREF(op) \ //减少计数
    	if (--(op)->ob_refcnt != 0) \
        	; \
   	 else \
        	__Py_Dealloc((PyObject *)(op))
当引用计数为0时，该对象生命就结束了。
```

- 引用计数机制的优点：

  - 1.简单
  - 2.实时性：一旦没有引用，内存就直接释放了。不用像其他机制等到特定时机。
    实时性还带来一个好处：处理回收内存的时间分摊到了平时。

- 引用计数机制的缺点：

  - 1.维护引用计数消耗资源
  - 2.循环引用的问题无法解决（DOS窗口，查看内存tasklist，或者内存表，任务管理器）

  ```
  案例：
  import gc
  class AAA(object):
      def __init__(self):
          print ("object: born at:%s"%hex(id(self)))
      def __new__(cls, *args, **kwargs):
          print ("new")
          return super(AAA, cls).__new__(cls)
      def __del__(self):
          print ("bye bye")
  def start():
      while True: #如果关闭垃圾回收机制，无限循环下，因为引用计数不能清零，所以内存会一直不能释放。可以使用隔代回收机制处理循环问题
          a = AAA() 
          b = AAA()
          a.v = b #b对象引用计数增加
          b.v = a #a对象引用计数增加
  #无法删除 只是引用计数减1
          del a
          del b
  gc.disable() #关闭垃圾回收机制
  start()
  ```

- 隔代回收

  ```
  分代回收是用来解决交叉引用(循环引用)
  ,并增加数据回收的效率. 原理:通过对象存在
  的时间不同,采用不同的算法来 回收垃圾. 形象的比喻, 
  三个链表,零代链表上的对象(新创建的对
  象都加入到零代链表),引用数都是一,每
  增加一个指针,引用加一,随后python会检
  测列表中的互相引用的对象,根据规则减
  掉其引用计数. 
  GC算法对链表一的引用减一,引用为0的,
  清除,不为0的到链表二,链表二也执行GC
  算法,链表三一样. 
  存在时间越长的数据,越是有用的数据
  ```

  - 隔代回收触发时间？（GC阈yu值）

  ```
  随着你的程序运行，Python解释器保持对新创建的对象，
  以及因为引用计数为零而被释放掉的对象的追踪。从理论上说，
  这两个值应该保持一致，因为程序新建的每个对象都应该最终被释放掉。
  当然，事实并非如此。因为循环引用的原因，从而被分配对象的计数值
  与被释放对象的计数值之间的差异在逐渐增长。一旦这个差异累计超过某个阈值，
  则Python的收集机制就启动了，并且触发上边所说到的零代算法，
  释放“浮动的垃圾”，并且将剩下的对象移动到一代列表。
  随着时间的推移，程序所使用的对象逐渐从零代列表移动到一代列表。
  而Python对于一代列表中对象的处理遵循同样的方法，一旦被分配计数值
  与被释放计数值累计到达一定阈值，Python会将剩下的活跃对象移动到二代列表。
  通过这种方法，你的代码所长期使用的对象，那些你的代码持续访问的活跃对象，
  会从零代链表转移到一代再转移到二代。通过不同的阈值设置，Python可以在
  不同的时间间隔处理这些对象。Python处理零代最为频繁，其次是一代然后才是二代。
  ```

- 查看引用计数

  - gc模块的使用

    ```
    常用函数：
    1、gc.get_count()
    获取当前自动执行垃圾回收的计数器，返回一个长度为3的列表
    2、gc.get_threshold()
    获取gc模块中自动执行垃圾回收的频率
    3、gc.set_threshold(threshold0[,threshold1,threshold2])
    设置自动执行垃圾回收的频率
    4、gc.disable()
    python3默认开启gc机制，可以使用该方法手动关闭gc机制
    5、gc.collect()
    手动调用垃圾回收机制回收垃圾
    ```

  - 增加引用计数的条件

    - a.创建对象

      ```
      stu = Student()
      ```

    - b.将对象加入列表

      ```
      list1.append(stu)
      ```

    - c.对象被引用

      ```
      stu2 = stu
      ```

    - d.将对象作为参数，传入某个函数

      ```
      func(stu)
      ```

  - 减少对象引用计数的情况

    - a.对象被显示销毁

      ```
      del stu
      ```

    - b.对象名指向新的对象

      ```
      stu = Student()
      ```

    - c.从容器中移除，或者显示销毁列表

      ```
      list1.remove(stu)
      list1.pop(stu)
      ```

    - d.局部变量对象，作为函数参数，     

      ```
      函数结束时，引用计数-1
      ```

    - 获取某个对象的引用计数

    ```
    import sys
    obj = 'Helloworld'
    sys.getrefcount(obj)
    list1 = []
    list.append(obj)
    sys.getrefcount(obj)
    ```


## 内建属性

- 常用专有属性

  - 常用内置类属性

    ```
    __dict__:
    类的属性（包含一个字典，由类的数据属性组成）
    __doc__:
    类的文档字符串（将类中的多行注释获取到）
    __name__:
     类名
    __module__:
    类定义所在的模块
    __bases__:
    类的所有父类构成元素（包含了以个由所有父类组成的元组）
    ```

  - 属性拦截器__getattribute__

    ```
    class Test(object):
        def __init__(self,var1):
            self.var1 = var1
        #  该方法在获取对象属性的时候会被调用，
        def __getattribute__(self,obj):
            if obj == 'var2':
                print("属性var1拦截成功")
                return '123'
    s = Test("python")
    # 成员变量 var1会被以字符串的形式（'var1'）传递给__getattribute__方法的obj
    print(s.var1)  #结果为123
    # 方法的访问也可以通过属性拦截器进行拦截
    
    ```

## 内建函数

- 什么叫内建函数:

  ```
  启动python解释器后，默认加载的函数称为内建函数
  ```

- 如何查看内建函数

  ```
  两种方式：
  a. dir(__builtins__)
  b.	import builtins
  dir(builtins)
  ```

- 常用内建函数：

  - range()

    ```
    python range() 函数可创建一个整数列表，一般用在 for 循环中。
    语法：
    range(start, stop[, step])
    参数说明：
    start: 计数从 start 开始。默认是从 0 开始。例如range（5）等价于range（0， 5）;
    stop: 计数到 stop 结束，但不包括 stop。例如：range（0， 5） 是[0, 1, 2, 3, 4]没有5
    step：步长，默认为1。例如：range（0， 5） 等价于 range(0, 5, 1)
    返回：range
    案例：
    代码验证
    ```

  - map()

    ```
    map() 会根据提供的函数对指定序列做映射。
    第一个参数 function 以参数序列中的每一个元素调用 function 函数，
    返回包含每次 function 函数返回值的新列表。
    语法：
    map(function, iterable, ...)
    参数说明：
    function -- 函数
    iterable -- 一个或多个序列
    返回：
    Python 2.x 返回列表。
    Python 3.x 返回迭代器。
    案例：
    from collections import Iterable
    from collections import Iterator
    def func(x,y):
        return x*y
    # 使用匿名函数
    v = map(lambda x:x*2,[1,2,3])
    print(type(v))
    print(isinstance(v,Iterable))
    print(isinstance(v,Iterator))
    for x in v:
        print(x)
    # 两个参数
    v1 = map(func,[1,2,3],[4,5,6])
    v2 = list(v1)
    print(type(v2))
    ```

  - filter()

    ```
    filter() 函数用于过滤序列，过滤掉不符合条件的元素，返回由符合条件元素组成的新列表。
    该接收两个参数，第一个为函数，第二个为序列，
    序列的每个元素作为参数传递给函数进行判断，然后返回 True 或 False，
    最后将返回 True 的元素放到新列表中。
    语法：
    filter(function, iterable)
    参数说明：
    function -- 判断函数。
    iterable -- 可迭代对象。
    返回：
    返回迭代器。
    案例：
    def func2(x):
        return  x % 2 == 0
    # 找出1-100中的偶数
    list2 =  filter(func2,[x for x in range(1,100)])
    print(isinstance(list2,Iterator))
    for x in list2:
        print(x)
    ```

  - reduce()

    ```
    3.x后，需要先from functools import reduce
    reduce() 函数会对参数序列中元素进行累积。
    函数将一个数据集合（链表，元组等）中的所有数据进行下列操作：
    用传给reduce中的函数 function（有两个参数）先对集合中的第 1、2 个元素进行操作，
    得到的结果再与第三个数据用 function 函数运算，最后得到一个结果。
    语法：
    reduce(function, iterable[, initializer])
    参数说明：
    function -- 函数，有两个参数
    iterable -- 可迭代对象
    initializer -- 可选，初始参数
    返回：
    返回函数计算结果
    案例：求列表所有值的和 
    from functools import reduce
    v = reduce(lambda x,y:x+y,[1,2,3,4],5)
    print(v)
    v = reduce(lambda x,y:x+y,['1','2','3','4'],'5')
    print(v)
    案例: 求列表中数字所能表示的整型数
    --------------------
    def func_4(x,y):
        return x * 10 + y
    list3 = [1,2,3,4]
    value = reduce(func_4,list3)
    print(value)
    ```

  - sorted()

    ```
    sorted() 函数对所有可迭代的对象进行排序操作。
    sort 与 sorted 区别：
    sort 是应用在 list 上的方法，sorted 可以对所有可迭代的对象进行排序操作。
    list 的 sort 方法返回的是对已经存在的列表进行操作，
    而内建函数 sorted 方法返回的是一个新的 list，而不是在原来的基础上进行的操作
    语法：
    sorted(iterable[, key[, reverse]])
    参数说明：
    iterable -- 可迭代对象。
    key -- 主要是用来进行比较的元素，只有一个参数，具体的函数的参数就是取自于可迭代对象中，指定可迭代对象中的一个元素来进行排序。
    reverse -- 排序规则，reverse = True 降序 ， reverse = False 升序（默认）
    返回：
    返回重新排序的列表。
    案例：
    class Student():
        def __init__(self,name,age):
            self.name = name
            self.age = age
        def __str__(self):
            return self.name+str(self.age)
    students = [('john', 'A', 15), ('jane', 'B', 12), ('dave', 'B', 10)]
    # 根据
    students = sorted(students,key=lambda s:s[1])
    print(students)
    
    students = [Student('jj',12),Student('dd',19),Student('xx',32)]
    # 自定义对象的排序
    students1 = sorted(students,key=lambda x:x.name)
    for s in students1:
        print(s)
    ```


## 集合

- 概念

  ```
  类似于列表的一种容器，可以存储多个数据，无序，唯一
  ```

- 用法：

  - 添加、删除元素

    ```
    add()
    remove()
    ```

  - 数学运算

    ```
    a = {1,2,3}
    b = {3,4,5}
    &:
    a & b  #{3} 取交集
    |:
    a | b  # {1，2，3，4，5} 取并集
    -:
    a - b  #{1，2} 从a中抛出交集，返回a
    ^:
    a ^ b  #{1，2，4，5} 取不同时存在的元素
    ```

## 常用模块

- 常见模块列表

  ```
  builtins（内建模块）				内建函数默认加载
  os					操作系统接口
  sys					python自身运行环境
  functools				常用的工具
  json					编解码json对象
  logging				记录日志
  time					时间
  datetime				日期和时间
  calendar				日历
  multiprocessing		进程
  threading				线程
  copy					复制
  hashlib				加密
  re					正则
  socket				标准BSD  socket API
  ```

- hashlib的加密验证（账户密码验证）

  ```
  from  hashlib import *
  m = md5()
  account = '13388888888'
  pw = '123456'
  # 使用md5方式加密（md5是不可逆的）
  m.update(account.encode())
  # 打印加密后的结果
  print(m.hexdigest())
  ```

- 常用扩展库（第三方库）

  ```
  requests 使用的是 urllib3， 继承了urllib2的所有特性
  urllib 基于http的高层库
  scrapy 爬虫
  beautifulsoup4 HTML/XML的解析器
  celery 分布式任务调度模块
  redis 缓存
  Pillow(PIL) 图像处理
  xlsxwriter 仅写excle功能,支持xlsx
  xlwt 仅写excle功能,支持xls ,2013或更早版office
  xlrd 仅读excle功能
  elasticsearch 全文搜索引擎
  pymysql 数据库连接库
  mongoengine/pymongo mongodbpython接口
  matplotlib 画图
  numpy/scipy 科学计算
  django/tornado/flask web框架
  xmltodict xml 转 dict
  SimpleHTTPServer 简单地HTTP Server,不使用Web框架
  gevent 基于协程的Python网络库
  fabric 系统管理
  pandas 数据处理库
  scikit-learn 机器学习库
  python本地服务器开启
  python -m http.server 8888
  ```

## 多进程

进程》线程》携程---都是实现多任务的方式。线程存在于进程中，携程存在于线程中。

#### 多进程

1.程序:是一个指令的集合
进程:正在执行的程序；或者说：当你运行一个程序，你就启动了一个进程
编写完的代码，没有运行时，称为程序，正在运行的代码，称为进程
程序是死的(静态的)，进程是活的(动态的)

操作系统轮流让各个任务交替执⾏ ，由于CPU的执⾏速度实在是太快了， 我们感觉就像所有任务都在同时执⾏⼀样 

多进程中， 每个进程中所有数据（包括全局变量） 都各自拥有⼀份， 互不影响 。

内存分为：栈区，堆区

#### 模拟多进程

```
模拟多任务处理：一边唱歌一边跳舞（两个函数来回切换，相当于多进程。实际上这还是单进程）
from time import sleep
def sing():
    for i in range(3):
        print("正在唱歌")
        dance()
        sleep(1)

def dance():
    print("正在跳舞")
if __name__ == '__main__':
    sing()
```

#### 多进程

程序开始运行时，首先会创建一个主进程

在主进程（父进程）下，我们可以创建新的进程（子进程），子进程依赖于主进程，如果主进程结束，程序会退出

Python提供了非常好用的多进程包multiprocessing，借助这个包，可以轻松完成从单进程到并发执行的转换

multiprocessing模块提供了⼀个Process类来创建⼀个进程对象

```

from multiprocessing import Process
def run(name):
    print("子进程1运行中，name = %s"%(name))
def run1(name):
    print("子进程2运行中，name = %s"%(name))
if __name__ == "__main__":
    print("父进程启动")
    p = Process(target=run, args=('test',))--创建一个     子进程对象
    #target表示调用对象，args表示调用对象的位置参数元组
    #（注意：元组中只有一个元素时结尾要加，）
    p1 = Process(target=run, args=('test1',))
    print("子进程将要执行")
    p.start()
    p1.start()
    print(p.name)   #p.pid
    print(p1.name)
    p.join() #保证子进程结束后，主进程再结束
    print("子进程结束")
```

if __name__ == “__main__”:说明
一个python的文件有两种使用的方法，第一是直接作为程序执行，第二是import到其他的python程序中被调用（模块重用）执行。

因此if __name__ == 'main': 的作用就是控制这两种情况执行代码的过程，__name__ 是内置变量，用于表示当前模块的名字
在if __name__ == 'main': 下的代码只有在文件作为程序直接执行才会被执行，而import到其他程序中是不会被执行的

在 Windows 上，子进程会自动 import 启动它的这个文件，而在 import 的时候是会执行这些语句的。如果不加if __name__ == "__main__":的话就会无限递归创建子进程
所以必须把创建子进程的部分用那个 if 判断保护起来
import 的时候 __name__ 不是 __main__ ，就不会递归运行了

#### Process(target , name , args）

参数介绍
target表示调用对象，即子进程要执行的任务
args表示调用对象的位置参数元组，args=(1,)
name为子进程的名称

#### Process类常⽤⽅法：

p.start()：启动进程，并调用该子进程中的p.run() 
p.run():进程启动时运行的方法，正是它去调用target指定的函数，我们自定义类的类中一定要实现该方法  
p.terminate()（了解）强制终止进程p，不会进行任何清理操作
p.is_alive():如果p仍然运行，返回True.用来判断进程是否还在运行
p.join([timeout]):主进程等待p终止，timeout是可选的超时时间

#### Process类常⽤属性：

name： 当前进程实例别名， 默认为Process-N， N为从1开始递增的整数；

pid： 当前进程实例的PID值 

#### 全局变量在多个进程中不共享：进程之间的数据是独立的，默认情况下互不影响

 

```
from multiprocessing import Process
num = 1
def run1():
    global num
    num += 5
    print("子进程1运行中，num = %d"%(num))
def run2():
    global num
    num += 10
    print("子进程2运行中，num = %d"%(num))
if __name__ == "__main__":
    print("父进程启动")
    p1 = Process(target=run1)
    p2 = Process(target=run2)
    print("子进程将要执行")
    p1.start()
    p2.start()
    p1.join()
    p2.join()
    print("子进程结束")

```

创建新的进程还能够使⽤类的⽅式， 可以⾃定义⼀个类， 继承Process类， 每次实例化这个类的时候， 就等同于实例化⼀个进程对象(这种方式主要用于进程需要多次实现相同的内容)

```
import multiprocessing
import time
class ClockProcess(multiprocessing.Process):
    def run(self):
        n = 5
        while n > 0:
            print(n)
            time.sleep(1)
            n -= 1
if __name__ == '__main__':
    p = ClockProcess()
    p.start()
    p.join()
```

#### 进程池

进程池：用来创建多个进程

当需要创建的⼦进程数量不多时， 可以直接利⽤multiprocessing中的Process动态生成多个进程， 但如果是上百甚⾄上千个⽬标， ⼿动的去创建进程的⼯作量巨⼤， 此时就可以⽤到multiprocessing模块提供的Pool

初始化Pool时， 可以指定⼀个最⼤进程数， 当有新的请求提交到Pool中时，如果池还没有满， 那么就会创建⼀个新的进程⽤来执⾏该请求； 但如果池中的进程数已经达到指定的最⼤值， 那么该请求就会等待， 直到池中有进程结束， 才会创建新的进程来执⾏。

```
from multiprocessing import Pool
import random,time

def work(num):
    print(random.random()*num)
    time.sleep(3)
if __name__ == "__main__":
    po = Pool(3)        #定义一个进程池，最大进程数为3，默认大小为CPU核数
    for i in range(10):
        po.apply_async(work,(i,))      #apply_async选择要调用的目标，每次循环会用空出来的子进程去调用目标
    po.close()       #进程池关闭之后不再接收新的请求
    po.join()         #等待po中所有子进程结束，必须放在close后面

在多进程中：主进程一般用来等待，真正的任务都在子进程中执行
```

multiprocessing.Pool常⽤函数解析：
apply_async(func[, args[, kwds]]) ： 使⽤⾮阻塞⽅式调⽤func（并⾏执⾏， 堵塞⽅式必须等待上⼀个进程退出才能执⾏下⼀个进程） ， args为传递给func的参数列表， kwds为传递给func的关键字参数列表；
apply(func[, args[, kwds]])（了解即可几乎不用） 使⽤阻塞⽅式调⽤func
close()： 关闭Pool， 使其不再接受新的任务；
terminate()： 不管任务是否完成， ⽴即终⽌；
join()： 主进程阻塞， 等待⼦进程的退出， 必须在close或terminate之后使⽤； 

#### 进程间通信

```
多进程之间，默认是不共享数据的
通过Queue（队列Q）可以实现进程间的数据传递
Q本身是一个消息队列
如何添加消息（入队操作）：
from multiprocessing import Queue
q = Queue(3)      #初始化一个Queue对象，最多可接受3条消息
q.put(“消息1”)     #添加的消息数据类型不限
q.put("消息2")
q.put("消息3")
print(q.full())
```

```
可以使⽤multiprocessing模块的Queue实现多进程之间的数据传递
初始化Queue()对象时（例如： q=Queue()） ， 若括号中没有指定最⼤可接收的消息数量， 或数量为负值， 那么就代表可接受的消息数量没有上限 
Queue.qsize()： 返回当前队列包含的消息数量
Queue.empty()： 如果队列为空， 返回True， 反之False 
Queue.full()： 如果队列满了， 返回True,反之False
Queue.get([block[, timeout]])： 获取队列中的⼀条消息， 然后将其从列队中移除， block默认值为True
如果block使⽤默认值， 且没有设置timeout（单位秒） ， 消息列队如果为空， 此时程序将被阻塞（停在读取状态） ， 直到从消息列队读到消息为⽌，如果设置了timeout， 则会等待timeout秒， 若还没读取到任何消息， 则抛出"Queue.Empty"异常 
如果block值为False， 消息列队如果为空， 则会⽴刻抛出“Queue.Empty”异常
Queue.get_nowait()： 相当Queue.get(False)
Queue.put(item,[block[, timeout]])： 将item消息写⼊队列， block默认值为True
如果block使⽤默认值， 且没有设置timeout（单位秒） ， 消息列队如果已经没有空间可写⼊， 此时程序将被阻塞（停在写⼊状态） ， 直到从消息列队腾出空间为⽌， 如果设置了True和timeout， 则会等待timeout秒， 若还没空间， 则抛出"Queue.Full"异常
如果block值为False， 消息列队如果没有空间可写⼊， 则会⽴刻抛出"Queue.Full"异常
Queue.put_nowait(item)： 相当Queue.put(item, False)； 
```

例子：

```
from multiprocessing import Queue, Process
import time

def write(q):
    for value in ["a","b","c"]:
        print("开始写入：",value)
        q.put(value)
        time.sleep(1)

def read(q):
    while True:
        if not q.empty():
            print("读取到的是",q.get()) 
            time.sleep(1)
        else:
            break
if __name__ == "__main__":
    q = Queue()
    pw = Process(target=write, args=(q,))
    pr = Process(target=read, args=(q,))
    pw.start()
    pw.join()#等待接收完毕
    pr.start()
    pr.join()
    print("接收完毕！")

```

问题：
如果有两个接收方怎么办？（多任务之间配合）。

思路：

1.接受的函数在get后，再将消息put到队列中。这样后面的函数又能继续取。

2.创建两个队列来完成

注意：队列存取消息，是按照先传入的先取出，且取出后该消息就从队列中消失了



进程池创建的进程之间通信：如果要使⽤Pool创建进程， 就需要使⽤multiprocessing.Manager()中的Queue()⽽不是multiprocessing.Queue()

否则会得到⼀条如下的错误信息：RuntimeError: Queue objects should only be shared between processesthrough inheritance. 

```
from multiprocessing import Manager,Pool
import time

def writer(q):
    for i in "welcome":
        print("开始写入",i)
        q.put(i)

def reader(q):
    time.sleep(3)
    for i in range(q.qsize()):
        print("得到消息",q.get())
if __name__ == "__main__":
    print("主进程启动")
    q = Manager().Queue()
    po = Pool()
    po.apply_async(writer,(q,))
    po.apply_async(reader,(q,))
    po.close()
    po.join()
```

## 多线程

线程:实现多任务的另一种方式
一个进程中，也经常需要同时做多件事，就需要同时运行多个‘子任务’，这些子任务，就是线程
线程又被称为轻量级进程(lightweight process)，是更小的执行单元

一个进程可拥有多个并行的(concurrent)线程，当中每一个线程，共享当前进程的资源

一个进程中的线程共享相同的内存单元/内存地址空间可以访问相同的变量和对象，而且它们从同一堆中分配对象通信、数据交换、同步操作

由于线程间的通信是在同一地址空间上进行的，所以不需要额外的通信机制，这就使得通信更简便而且信息传递的速度也更快

#### 线程与进程的区别

进程是系统进⾏资源分配和调度的⼀个独⽴单位
进程在执⾏过程中拥有独⽴的内存单元， ⽽多个线程共享内存， 从⽽极⼤地提⾼了程序的运⾏效率
⼀个程序⾄少有⼀个进程,⼀个进程⾄少有⼀个线程
线程是进程的⼀个实体,是CPU调度和分派的基本单位,它是⽐进程更⼩的能独⽴运⾏的基本单位
线程⾃⼰基本上不拥有系统资源,只拥有⼀点在运⾏中必不可少的资源，但是它可与同属⼀个进程的其他的线程共享进程所拥有的全部资源 
线程的划分尺度⼩于进程(资源⽐进程少)， 使得多线程程序的并发性⾼
线程不能够独⽴执⾏， 必须依存在进程中 
线程和进程在使⽤上各有优缺点： 线程执⾏开销⼩， 但不利于资源的管理和保护； ⽽进程正相反

![image-20200726141545588](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726141545588.png)

#### 多线程是实现

python的thread模块是⽐较底层的模块，在各个操作系统中表现形式不同（低级模块）
python的threading模块是对thread做了⼀些包装的， 可以更加⽅便的被使⽤（高级模块）
thread 有一些缺点，在threading 得到了弥补，所以我们直接学习threading
import threading
if __name__ == "__main__":
    #任何进程默认会启动一个线程，这个线程称为主线程，主线程可以启动新的子线程
    #current_thread():返回当前线程的实例
    #.name ：当前线程的名称
    print('主线程%s启动' %(threading.current_thread().name))

```
import threading,time
def saySorry():
    print("子线程%s启动" %(threading.current_thread().name))
    time.sleep(1)
    print("亲爱的，我错了，我能吃饭了吗？")

if __name__ == "__main__":
    print('主线程%s启动' %(threading.current_thread().name))
    for i in range(5):
        t = threading.Thread(target=saySorry)#Thread()：创建线程，指定线程要执行的代码
        t.start()

```

```
import threading
import time

def sing():
    for i in range(3):
        print("正在唱歌...%d" %i)
        time.sleep(1)
def dance():
    for i in range(2):
        print("正在跳舞...%d" %i)
        time.sleep(1)
if __name__ == "__main__":
    print("开始：%s" %time.time())
    t1 = threading.Thread(target=sing)
    t2 = threading.Thread(target=dance)
    t1.start()
    t2.start()

    while True:
        length = len(threading.enumerate())
        #threading.enumerate():返回当前运行中的Thread对象列表
        print("当前线程数为：%d" %length)
        if length<=1:
            break
        time.sleep(1)
```

#### 创建线程的两种方式

创建线程的两种方式：
第一：通过 threading.Thread 直接在线程中运行函数；
第二：通过继承 threading.Thread 类来创建线程
这种方法只需要重载 threading.Thread 类的 run 方法，然后调用 start()开启线程就可以了

```
import threading
class MyThread(threading.Thread):
    def run(self):
        for i in range(5):
            print(i)
if __name__ == "__main__":
    t1 = MyThread()
    t2 = MyThread()
    t1.start()
    t2.start()
```

```
import threading
import time
class MyThread(threading.Thread):
    def run(self):
        for i in range(3):
            time.sleep(1)
            msq = "I`m" + self.name + "@" + str(i)
            #name属性中保存了当前线程的名字
            print(msq)
if __name__ == "__main__":
    t = MyThread()
    t.start()
```

#### 线程的五种状态

多线程程序的执⾏顺序是不确定的（操作系统决定）。 当执⾏到sleep语句时， 线程将被阻塞（Blocked） ， 到sleep结束后， 线程进⼊就绪（Runnable） 状态， 等待调度。 ⽽线程调度将⾃⾏选择⼀个线程执⾏。 代码中只能保证每个线程都运⾏完整个run函数， 但是线程的启动顺序、run函数中每次循环的执⾏顺序都不能确定

![image-20200726151543739](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726151543739.png)

1、新状态：线程对象已经创建，还没有在其上调用start()方法。
2、可运行状态：当线程有资格运行，但调度程序还没有把它选定为运行线程时线程所处的状态。当start()方法调用时，线程首先进入可运行状态。在线程运行之后或者从阻塞、等待或睡眠状态回来后，也返回到可运行状态。
3、运行状态：线程调度程序从可运行池中选择一个线程作为当前线程时线程所处的状态。这也是线程进入运行状态的唯一一种方式。
4、等待/阻塞/睡眠状态：这是线程有资格运行时它所处的状态。实际上这个三状态组合为一种，其共同点是：线程仍旧是活的（可运行的），但是当前没有条件运行。但是如果某件事件出现，他可能返回到可运行状态。
5、死亡态：当线程的run()方法完成时就认为它死去。这个线程对象也许是活的，但是，它已经不是一个单独执行的线程。线程一旦死亡，就不能复生。如果在一个死去的线程上调用start()方法，会抛出RuntimeError: threads can only be started once异常。

#### 线程共享全局变量

在⼀个进程内的所有线程共享全局变量， 多线程之间的数据共享（这点要⽐多进程要好）
缺点就是， 可能造成多个线程同时修改一个变量（即线程⾮安全），可能造成混乱

```
import threading
import time

num = 100
def work1():
    global num
    for i in range(3):
        num += 1
    print("---in work1,num is %d" %num)
def work2():
    global num
    print("---in work2,num is %d" %num)
print("---线程创建之前 num is %d" %num)
t1 = threading.Thread(target=work1)
t1.start()
time.sleep(1)
#延时一会保证线程1中的任务做完
t2 = threading.Thread(target=work2)
t2.start()
```

```
import threading
num = 0
def test1():
    global num
    for i in range(100):
	    num += 1
def test2():
    global num
    for i in range(100):
	    num += 1
p1 = threading.Thread(target=test1)
p1.start()
p2 = threading.Thread(target=test2)
p2.start()
print("---num = %d---" %num)  #结果为200正确的
```

```
import threading
import time
num = 0
def test1():
    global num
    for i in range(1000000):
	    num += 1
def test2():
    global num
    for i in range(10000000):
	    num += 1
p1 = threading.Thread(target=test1)
p1.start()
p2 = threading.Thread(target=test2)
p2.start()
time.sleep(3) #等待线程跑完
print("---num = %d---" %num)  #结果小于200000，不正确，因为两个线程在执行时会抢num这个对象，从而使某些赋值操作还没完成就被另一个线程拿走了，导致计算结果变小。
```

#### 线程同步

当多个线程⼏乎同时修改某⼀个共享数据的时候， 需要进⾏同步控制 
线程同步能够保证多个线程安全访问竞争资源， 最简单的同步机制是引⼊互斥锁 
互斥锁保证了每次只有⼀个线程进⾏写⼊操作，从⽽保证了多线程情况下数据的正确性（原子性） 
互斥锁为资源引入一个状态：锁定/非锁定。某个线程要更改共享数据时，先将其锁定，此时资源的状态为“锁定”，其他线程不能更改；直到该线程释放资源，将资源的状态变成“非锁定”，其他的线程才能再次锁定该资源。互斥锁保证了每次只有一个线程进行写入操作，从而保证了多线程情况下数据的正确性。
 threading模块中定义了Lock类， 可以⽅便的处理锁定

创建锁mutex = threading.Lock()
锁定mutex.acquire()
释放mutex.release()  #解锁 

```
import threading
import time
num = 0
def test1():
    global num
    if mutex.acquire():  #上锁，保证在调用num时，其他进程不能调用
        for i in range(1000000):
            num += 1
    mutex.release()
def test2():
    global num
    if mutex.acquire():
        for i in range(1000000):
            num += 1
    mutex.release()
mutex = threading.Lock()
p1 = threading.Thread(target=test1)
p1.start()
p2 = threading.Thread(target=test2)
p2.start()
time.sleep(3)
print(num)  #结果为2000000正确
```

#### 线程同步（死锁）

死锁（错误情况，理解即可）在线程间共享多个资源的时候， 如果两个线程分别占有⼀部分资源并且同时等待对⽅的资源， 就会造成死锁 
⼊到了死锁状态， 可以使⽤ctrl-z退出 

```
import threading
import time
class MyThread1(threading.Thread):
    def run(self):
        if mutexA.acquire():
            print(self.name + '---do1---up---')
            time.sleep(1)
            if mutexB.acquire():
                print(self.name + '---do1---down---')
                mutexB.release()
        mutexA.release()
class MyThread2(threading.Thread):
    def run(self):
	time.sleep(1) 
	if mutexB.acquire():
            		print(self.name + '---do2---up---')
            		if mutexA.acquire():
			print(self.name + '---do2---down---')
                		mutexA.release()
            	mutexB.release()

if __name__ == '__main__':
    mutexA = threading.Lock()
    mutexB = threading.Lock()
    t1 = MyThread1()
    t2 = MyThread2()
    t1.start()
    t2.start()
"""在多线程程序中，死锁问题很大一部分是由于线程同时获取多个锁造成的。如一个线程获取了第一个锁，然后在获取第二个锁的时候发生阻塞，那么这个线程就可能阻塞其他线程的执行，从而导致整个程序假死（两个人每人一根筷子）
"""
```

#### 同步和异步

同步调⽤：确定调用的顺序
按顺序购买四大名著
异步调⽤：不确定顺序
你 喊 你朋友吃饭 ， 你朋友说知道了 ， 待会忙完去找你 ，你就去做别的了 
堵塞和非堵塞

```
"""同步调用"""
import threading,time
class Task1(threading.Thread):
    def run(self):
        while True:
            if lock1.acquire():
                print('-----Task1-----')
                time.sleep(1)
                lock2.release()
class Task2(threading.Thread):
    def run(self):
        while True:
            if lock2.acquire():
                print('-----Task2-----')
                time.sleep(1)
                lock3.release()
class Task3(threading.Thread):
    def run(self):
        while True:
            if lock3.acquire():
                print('-----Task3-----')
                time.sleep(1)
                lock1.release()
lock1 = threading.Lock()
#创建另外一把锁，并且锁上
lock2 = threading.Lock()
lock2.acquire()
#再创建一把锁并锁上
lock3 = threading.Lock()
lock3.acquire()
t1 = Task1()
t2 = Task2()
t3 = Task3()
t1.start()     
t2.start()       
t3.start()
```

```
"""异步调用"""
import threading,time
num = 0
def test1():
    global num
    mutex.acquire()
    for i in range(1000000):
        num += 1
    mutex.release()
    print("1",num)
def test2():
    global num
    while True:
        if mutex.acquire(False):
            for i in range(1000000):
                num += 1
            print("2", num)
            mutex.release()
            break
        else:
            print("该干嘛干嘛")
mutex = threading.Lock()
p1 = threading.Thread(target=test1)
p2 = threading.Thread(target=test2)
p1.start()
p2.start()
```

#### ⽣产者消费者模式

⽣产者消费者模式
在线程世界⾥， ⽣产者就是⽣产数据的线程， 消费者就是消费数据的线程（做包子，吃包子） 
经常会出现生产数据的速度大于消费数据的速度，或者生产速度跟不上消费速度

⽣产者消费者模式是通过⼀个容器（缓冲区）来解决⽣产者和消费者的强耦合问题
例如两个线程共同操作一个列表，一个放数据，一个取数据

⽣产者和消费者彼此之间不直接通讯， ⽽通过阻塞队列来进⾏通讯 

Python的Queue模块：实现了3种类型的队列来实现线程同步，包括：
FIFO（先⼊先出) 队列 Queue，
LIFO（后⼊先出） 栈 LifoQueue， 
优先级队列  PriorityQueue
区别在于队列中条目检索的顺序不同
在FIFO队列中，按照先进先出的顺序检索条目
在LIFO队列中，最后添加的条目最先检索到（操作类似一个栈）
在优先级队列中，条目被保存为有序的（使用heapq模块）并且最小值的条目被最先检索
这些队列都实现了锁原语（可以理解为原⼦操作， 即要么不做， 要么就做完） ， 能够在多线程中直接使⽤ 

现阶段只要求掌握其中一种，FIFO队列

- [x] ![image-20200726160247529](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726160247529.png)

```
import threading
import time
from queue import Queue
class Pro(threading.Thread):
    def run(self):
        global queue
        count = 0
        while True:
            if queue.qsize()<1000:
                for i in range(100):
                    count = count + 1
                    msg = '生成产品' + str(count)
                    queue.put(msg)#队列中添加新产品
                    print(msg)
            time.sleep(1)
class Con(threading.Thread):
    def run(self):
        global queue
        while True:
            if queue.qsize() > 100:
                for i in range(3):
                    msg = self.name + '消费了' + queue.get()
                    print(msg)
            time.sleep(1)
if __name__ == "__main__":
    queue = Queue()
    #创建一个队列。线程中能用，进程中不能使用
    for i in range(500):#创建500个产品放到队列里
        queue.put(‘初始产品’ + str(i))#字符串放进队列
    for i in range(2):#创建了两个线程
        p = Pro()
        p.start()
    for i in range(5):#5个线程
        c = Con()
        c.start()
```

#### ThreadLocal变量

⼀个ThreadLocal变量虽然是全局变量， 但每个线程都只能读写⾃⼰线程的独⽴副本， 互不⼲扰。ThreadLocal解决了参数在⼀个线程中各个函数之间互相传递的问题 
可以理解为全局变量local_school是⼀个dict， 可以绑定其他变量 
ThreadLocal最常⽤的地⽅就是为每个线程绑定⼀个数据库连接， HTTP请求， ⽤户身份信息等， 这样⼀个线程的所有调⽤到的处理函数都可以⾮常⽅便地访问这些资源 

```
import threading
#创建一个全局的对象
local_school = threading.local()
def process_student():
    #获取当前线程关联的student
    std = local_school.student
    print("Hello %s (in %s)" %(std,threading.current_thread().name))
def process_thread(name):
    #绑定ThreadLocal的Student
    local_school.student = name
    process_student()
t1 = threading.Thread(target=process_thread,args=('zhangsan',),name='t1')
t2 = threading.Thread(target=process_thread,args=('老王',),name='t2')
t1.start()
t2.start()

```

## 网络编程

#### 网络基础

![image-20200726173601032](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726173601032.png)

![image-20200726173641239](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726173641239.png)

![image-20200726173719572](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726173719572.png)

![image-20200726173747652](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726173747652.png)

![image-20200726173816442](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726173816442.png)

![image-20200726173848102](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726173848102.png)

![image-20200726173910744](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726173910744.png)

![image-20200726173941709](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726173941709.png)

![image-20200726174007958](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726174007958.png)

![image-20200726174040737](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726174040737.png)

![image-20200726174130973](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726174130973.png)

#### Socket编程-简介

![image-20200726191006993](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726191006993.png)

![image-20200726191048268](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726191048268.png)

![image-20200726191118142](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726191118142.png)

![image-20200726191145791](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726191145791.png)

![image-20200726191209458](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726191209458.png)

#### Socket编程-udp编程

```
发送数据：为看到效果先安装“网络调试助手”
from socket import *
s = socket(AF_INET, SOCK_DGRAM) #创建套接字
addr = ('192.168.1.17', 8080) #准备接收方地址
data = input("请输入：")
s.sendto(data.encode(),addr)
#发送数据时，python3需要将字符串转成byte
#encode(‘utf-8’)# 用utf-8对数据进行编码，获得bytes类型对象
#decode（）反过来
s.close()
```

![image-20200726191348541](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726191348541.png)

接收数据

```
from socket import *
s = socket(AF_INET, SOCK_DGRAM) #创建套接字
addr = ('192.168.1.17', 8080) #准备接收方地址
data = input("请输入：")
s.sendto(data.encode(),addr)
#等待接收数据
redata = s.recvfrom(1024)
#1024表示本次接收的最大字节数
print(redata)
s.close()
```

![image-20200726191455488](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726191455488.png)

```
绑定信息：让一个进程可以使用固定的端口
一般情况下，发送方不绑定端口，接收方会绑定
from socket import *
s = socket(AF_INET, SOCK_DGRAM) #创建套接字
s.bind(('', 8788))   #绑定一个端口，ip地址和端⼝号，ip⼀般不⽤写
addr = ('192.168.1.17', 8080)   #准备接收方地址
data = input("请输入：")
s.sendto(data.encode(),addr)
redata = s.recvfrom(1024) #1024表示本次接收的最⼤字节数
print(redata)
s.close()
```

![image-20200726195751130](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726195751130.png)

```
聊天室
from socket import *
import time
#1创建套接字
udpSocket = socket(AF_INET, SOCK_DGRAM)
bindAddr = ("",7088)
udpSocket.bind(bindAddr)#绑定
while True:
    #接收对方发送的数据
    recvData = udpSocket.recvfrom(1024)
    print('【%s】 %s.%s' %(time.ctime(),recvData[1],recvData[0].decode("GB2312")))
    a = input("请输入：")
    udpSocket.sendto(a.encode('GB2312'),('192.168.1.17',8080))
#5关闭套接字
udpSocket.close()
```

![image-20200726195939222](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726195939222.png)

![image-20200726200018661](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726200018661.png)

```
#导入模块
import threading
import time
from socket import *


#实现接受消息
class Recive(threading.Thread):
    def run(self):
        udpsocket = socket(AF_INET,SOCK_DGRAM) #创建套接字
        udpsocket.bind(("",8089)) #接受方需要绑定地址,bind参数为元组
        while True:
            recivedata = udpsocket.recvfrom(1024) #接受最大为1024字节的消息
            print("{0}_{1}给你发送消息：{2}".format(recivedata[1][0],recivedata[1][1],recivedata[0].decode("GB2312")))


#实现发送消息
class Set(threading.Thread):
    def run(self):
        udpsocket = socket(AF_INET,SOCK_DGRAM)
        while True:
            a = input("请输入：")
            udpsocket.sendto(a.encode("GB2312"),("192.168.76.1",8080)) #发送消息给指定地址

if __name__ == "__main__":
    recive = Recive()
    set = Set()
    recive.start() #启动子线程1完成接受消息
    set.start() #启动子线程2来完成发送消息
```

#### 字符集

![image-20200726212916146](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726212916146.png)

#### wireshark抓包

![image-20200726213015906](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726213015906.png)

![image-20200726213040184](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726213040184.png)

![image-20200726213148960](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726213148960.png)



![image-20200726213223529](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726213223529.png)

#### TFTP协议

![image-20200726213254590](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726213254590.png)

![image-20200726213426801](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726213426801.png)

![image-20200726213448228](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726213448228.png)

![image-20200726213515762](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726213515762.png)

![image-20200726213542981](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726213542981.png)

![image-20200726213607260](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726213607260.png)

#### struct模块使用

![image-20200726213807085](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726213807085.png)

![image-20200726213843832](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726213843832.png)

![image-20200726213936560](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726213936560.png)

![image-20200726214115240](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726214115240.png)

#### udp广 播

![image-20200726214222913](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726214222913.png)

![image-20200726214252179](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200726214252179.png)

#### Packet Tracer 介绍&安装 

![image-20200727223700507](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727223700507.png)

![image-20200727223729943](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727223729943.png)

![image-20200727223816930](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727223816930.png)

![image-20200727223843442](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727223843442.png)

![image-20200727223915929](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727223915929.png)

![image-20200727223947516](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727223947516.png)

![image-20200727224038138](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727224038138.png)

![image-20200727224057214](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727224057214.png)

![image-20200727224147537](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727224147537.png)

![image-20200727224206882](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727224206882.png)

![image-20200727224229765](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727224229765.png)

![image-20200727224254857](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727224254857.png)

#### TCP

![image-20200727224356997](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727224356997.png)



![image-20200727224330638](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727224330638.png)

![image-20200727224416590](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727224416590.png)

![image-20200727224502039](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727224502039.png)

![image-20200727224518288](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727224518288.png)

![image-20200727224534170](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727224534170.png)

![image-20200727224656777](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727224656777.png)

![image-20200727224724685](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727224724685.png)

单进程服务器

```
from socket import *
serSocket = socket(AF_INET, SOCK_STREAM)
localAddr = ('',7788)
serSocket.bind(localAddr)
serSocket.listen(5)
while True:
    print("主进程等待新客户端")
    newSocket,destAddr = serSocket.accept()
    print("主进程接下来负责处理",str(destAddr))
    try:
        while True:
            recvData = newSocket.recv(1024)
            if len(recvData)>0: #如果收到的客户端数据长度为0，代表客户端已经调用close（）下线
                print("接收到", str(destAddr),recvData)
            else:
                print("%s-客户端已关闭" %str(destAddr))
                break
    finally:
        newSocket.close()
serSocket.close()
```

并发服务器

![image-20200727230839501](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727230839501.png)

多进程服务器

![image-20200727230947316](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727230947316.png)

![image-20200727231019284](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727231019284.png)

![image-20200727231040759](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727231040759.png)

#### 携程

![image-20200727232744564](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727232744564.png)

![image-20200727232805492](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727232805492.png)

![image-20200727232821744](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727232821744.png)

![image-20200727232836729](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727232836729.png)

![image-20200727232851102](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200727232851102.png)

## 数据库

#### 安装数据库

![image-20200728222439473](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728222439473.png)

![image-20200728222458150](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728222458150.png)

![image-20200728222527572](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728222527572.png)

![image-20200728222547104](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728222547104.png)

![image-20200728222613863](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728222613863.png)

![image-20200728222643750](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728222643750.png)

![image-20200728222659342](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728222659342.png)

![image-20200728222718860](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728222718860.png)

![image-20200728222738803](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728222738803.png)

![image-20200728222751670](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728222751670.png)![](

![image-20200728222819501](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728222819501.png)

![image-20200728222833878](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728222833878.png)

![image-20200728222856705](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728222856705.png)

![image-20200728222911837](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728222911837.png)

![image-20200728222930012](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728222930012.png)

#### SQL语句

![image-20200728234039830](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728234039830.png)

![image-20200728234059522](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728234059522.png)

![image-20200728234118167](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728234118167.png)

![image-20200728234135210](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728234135210.png)

![image-20200728234152309](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728234152309.png)

![image-20200728234214104](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728234214104.png)

![image-20200728234231477](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728234231477.png)![](C:\U

![image-20200728234257227](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728234257227.png)

![image-20200728234327176](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728234327176.png)

![image-20200728234417811](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728234417811.png)![image-20200728234417889](C:\Us

![image-20200728234453051](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728234453051.png)

![image-20200728234509321](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728234509321.png)

![image-20200728234542345](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200728234542345.png)![image-

![image-20200729185807046](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729185807046.png)

![image-20200729185822742](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729185822742.png)

![image-20200729185934597](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729185934597.png)

![image-20200729190949471](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729190949471.png)

![image-20200729195438531](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729195438531.png)

![image-20200729195458087](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729195458087.png)

![image-20200729195522968](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729195522968.png)

![image-20200729195552390](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729195552390.png)

![image-20200729195613006](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729195613006.png)

![image-20200729195636824](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729195636824.png)

![image-20200729195657990](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729195657990.png)

![image-20200729195714133](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729195714133.png)

![image-20200729195729312](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729195729312.png)

![image-20200729195804010](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729195804010.png)

![image-20200729195852218](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729195852218.png)

![image-20200729195937724](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729195937724.png)

![image-20200729200004508](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729200004508.png)

![image-20200729200025918](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729200025918.png)

![image-20200729200045654](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729200045654.png)

![image-20200729200106519](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729200106519.png)

![image-20200729200126771](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729200126771.png)

![image-20200729200207450](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729200207450.png)

![image-20200729200226796](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729200226796.png)

![image-20200729200245153](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729200245153.png)

![image-20200729200301669](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729200301669.png)

![image-20200729200317787](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729200317787.png)

![image-20200729200332393](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729200332393.png)

![image-20200729200354075](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729200354075.png)

![image-20200729200422079](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729200422079.png)

![image-20200729203055553](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729203055553.png)

![image-20200729203115905](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729203115905.png)

![image-20200729203134872](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729203134872.png)

![image-20200729203151580](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729203151580.png)

![image-20200729203206673](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729203206673.png)

![image-20200729203224469](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729203224469.png)

![image-20200729203240036](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729203240036.png)

![image-20200729203256451](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729203256451.png)

![image-20200729203318404](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729203318404.png)

![image-20200729203352638](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729203352638.png)

![image-20200729203429732](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729203429732.png)

![image-20200729203445685](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729203445685.png)

![image-20200729203501436](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729203501436.png)

![image-20200729203520216](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729203520216.png)

#### 事务

![image-20200729205729801](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729205729801.png)

![image-20200729205814103](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729205814103.png)

![image-20200729205850493](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729205850493.png)

![image-20200729205941474](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729205941474.png)

![image-20200729210054634](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729210054634.png)

![image-20200729210124587](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729210124587.png)

#### 关联关系的使用

![image-20200729210204175](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729210204175.png)

![image-20200729210347216](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729210347216.png)

![image-20200729210518105](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729210518105.png)

![image-20200729210612415](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729210612415.png)

#### python连接MySQL

![image-20200729210723023](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729210723023.png)

![image-20200729210752580](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729210752580.png)

![image-20200729210859481](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729210859481.png)

![image-20200729211006433](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729211006433.png)

![image-20200729211036009](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729211036009.png)

![image-20200729211147034](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729211147034.png)

![image-20200729211217319](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729211217319.png)

![image-20200729211239714](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729211239714.png)

![image-20200729211438466](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729211438466.png)

![image-20200729211502471](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729211502471.png)

![image-20200729211623930](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729211623930.png)

#### 模拟音乐播放器模拟音乐播放器

![image-20200729211820872](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729211820872.png)

![image-20200729211848920](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729211848920.png)

![image-20200729211906054](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729211906054.png)

![image-20200729212017508](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729212017508.png)

![image-20200729212053963](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729212053963.png)

## 正则表达式

#### 正则表达式概述

![image-20200729213108480](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729213108480.png)

![image-20200729213142733](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729213142733.png)

![image-20200729213200918](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729213200918.png)

![image-20200729213303806](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729213303806.png)

```
import re
line = "qwertyuiop"   #不具备通用性
s = "qwertyuiopl"
print(re.match(line, s).group())
#结果为：qwertyuiop
```

#### 表示字符

![image-20200729213609186](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729213609186.png)

![image-20200729214021030](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729214021030.png)

![image-20200729214047262](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729214047262.png)

```
import re
ret = re.match("[hH]","Hello Python")
print(ret.group())
# 结果为H
import re
ret = re.match("[0-9]","7Hello Python")
print(ret.group())
# 结果为：7
import re
ret = re.match("\d","7Hello Python")
print(ret.group())
# 结果为：7
```

#### 原始字符与转义字符

![image-20200729214533985](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729214533985.png)

![image-20200729214844812](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729214844812.png)

```
#要匹配一个\
import re
ret1 = re.match("\\\\","\\")
print(ret1.group())
# 结果为\  因为python中“\\”表示“\”,而在正则表达式中“\\”表示“\” 所以前面的匹配表达式，需要4个“\”来表示“\”
import re
ret = re.match(r"c:\\a",r"c:\a\b\c")
print(ret.group())
#结果为 c:\a  注意：r只能取消python中的转义，不能取消正则表达式中的转义
```

![image-20200729214918192](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729214918192.png)

![image-20200729215019965](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729215019965.png)

```
import re
ret = re.match("[A-Z][a-z]*","AabbBcdef")
print(ret.group())
# 结果为 Aabb

```

#### 匹配练习

![image-20200729222317397](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729222317397.png)

![image-20200729222356534](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729222356534.png)

![image-20200729230830472](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729230830472.png)

![image-20200729230851150](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729230851150.png)

![image-20200729230912074](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729230912074.png)

![image-20200729230928348](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729230928348.png)

![image-20200729230949438](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729230949438.png)

![image-20200729231010355](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729231010355.png)

![image-20200729231028904](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729231028904.png)

![image-20200729231045396](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729231045396.png)

![image-20200729231104806](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200729231104806.png)

# 前端知识

## HTML基本标签

#### HTML基本标签

1.html的作用：定义整个页面“长”什么样，相当于网站的骨架。

2.如何写html标签：安装webstorm软件。

3.html格式：

```
<!DOCTYPE html>                                 ----定义文件类型为html
<html>                            ----<html></html>之间是整个html的内容
<head lang="en">                             ---<head></head>头部标签 
    <meta charset="UTF-8">
    <title></title>             ---<title></title>标题标签，定义网页标题
</head>
<body>                          ---<body></body>身体标签，定义页面标签内容

</body>
</html>
<!---->                       ---- <!---->注释（CTRL+？）
```

2.html常用的标签：

标题标签：h1~h6。h1到h6都有自己默认的格式。字体大小等

```
2.html常用的标签：<h1>放置一级标题</h1>
<h2>放置二级标题</h2>
```

容器标签：div。定义大的模块。

段落标签：p。定义段落文字

行内标签：span。如果放置在p标签内，则它会与p标签在同一行展示。

超链接标签：a。定义超链接，点击跳转到指定路径。属性：href放置网址，target属性有self，blank值。self表示跳转后不会新建一个窗口，blank跳转后打开新窗口。

图片标签：img。用来放置图片，属性：src用来放置图片路径，可以是本地路径也可以是网络路径。alt属性，用来放置到图片加载失败时，要显示的文字

换行标签：br。用于多个行内元素在同一行时，实现换行。

分割标签：hr。显示一条分割线，属性：width定义分割线宽度。size设置分割线的高度（厚度）

#### 列表标签

- ol（有序列表）；type属性设置列表样式。使用style='list-style: none;'可以取消列表前面的标签样式

  ![image-20200730232441345](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200730232441345.png)

  ```
  <ol type='I' style='list-style: none;'>
  		<li>五个关键词助你读懂十八大以来组织工作</li>
  		<li>新华社评论员:奏响新时代的青春之歌  央视快评</li>
  		<li>梦开始的地方:学访习近平"三农"思想的浙江实践</li>
  	</ol>
  ```

  

- ul（无序列表）；列表项也是li标签，前面类型为点。

- dl（图文混排）;

  ```
  <dt>图文混排标题</dt>
  		<dd><img src="images/2.jpg" alt=""></dd>
  		<dd>图文混排内容</dd>
  ```

  


- 块级元素和行内元素：

  - 块级元素：独占一行，标签的宽是浏览器屏幕的宽度，高度由内部的内容决定，常用的块级元素：div，p，ul,li,dl

  - 行内元素：不独占一行，在同一行可以放多个元素，如果行内元素在块级元素的内部，那么会跟块级标签在同一行，行内元素的宽度和高度都是由内部的内容决定的。常见的行内元素：span，a，em，i

  - 行内块级元素：不独占一行，宽度高度可以自己设置，常见的行内块级元素：input，button，img

  - 改变元素属性的方法：

    display:block;            改变为块级元素

    display:inline;            改变为行内元素

    display:inline-block;  改变为行内块级元素

    display:none;              把元素隐藏

    ```
    <!DOCTYPE html>
    <html>
    <head lang="en">
        <meta charset="UTF-8">
        <title>我的第一个网页</title>
        <style>
            .newscontent{
                display: inline-block;
            }
        </style>
    </head>
    <body>
    <div >
        <!--使用class选择器设置display为行内元素，这样下面的两个p标签就在同一行了
        注意class定义的类需要在head标签中用style标签说明-->
        <p class='newscontent' >蔡英文要求布基纳法索:＂断交＂了 就把军备还我</p>
        <p class='newscontent' >蔡英文 防务</p>
    </div>
    </body>
    </html>
    ```

    

- 双标签和单标签：

  - 双标签：成对出现，有开始标签，有结束标签。大部分标签是双标签

  - 单标签：单个标签，写法：<br />常见的单标签：br,hr,input,img

    

#### 表格标签

5.表格table：<table></table>标签中，可以放一下标签：

<caption></caption>---放置表格标题

<tr></tr>-----行标签

<th></th>----表头标签

<td></td>----列表签

```
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title>我的第一个网页</title>
</head>
<body>
<table>
    <caption>表的标题</caption>>
    <tr>
        <th>姓名</th>
        <th>年龄</th>
        <th>手机号码</th>>
    </tr>>
    <tr>
        <td>欧毅</td>
        <td>27</td>
        <td>13118172284</td>
    </tr>
</table>>
</body>
</html>
```

#### 

- 表格的属性：（加在table标签内就对整个表格作用）
  		border:边框宽度，值为数字类型
    		cellpadding: 单元格内边距，值为数字类型
    		cellspacing：单元格外边距，值为数字类型
    		align:表格的对齐形式，
    				可选值：
    				left  左对齐
    				right  右对齐
    				center 居中

  ​		width: 设置宽度。如果在table，设置的是整个table的宽；如果在td上，设置对应列的宽

- 表格的合并属性：
  		行合并：rowspan=5  把5行合并成一行
    		列合并：colspan=3  把3列合并成一列

#### 表单标签

6.表单
	form	表单标签
		区域块：fieldset ，使用 legend 设置区域块的名称
		用户输入框： input type='text'
		单选按钮：	input type='radio'
		多选按钮：	input type='checkbox'
		下拉框：		select > option
		密码：		input type='password'
		上传文件：	input type='file'
		范围数字：	input type='range'
		提交：		input type='submit'
		重置：		input type='reset'
		按钮：		button
		文本域：		textarea

input标签属性：
		placeholder 设置提示文字
		name		设置input标签的提交数据键名，因为输入框的内容是以键值对的形式存储
		value		设置input标签的值，即给输入框一个默认值。可以删除修改。

form标签属性：
		action:	url地址，数据提交的地址
		method: 提交方式， get / post ，默认是get

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<form action="" method="get">
		<fieldset>
			<legend>区域块</legend>
			<span>普通文本</span>
		</fieldset>
		<!-- 用户输入 -->
		用户名： <input type="text" placeholder="请输入用户名或手机号" name="userName" ><br>
		<!-- 单选按钮 name必须一样，value必须设置值-->
		性别：<input type="radio" name="sex" value="1"> 男
			 <input type="radio" name="sex" value="2"> 女
			 <br>
		<!--多选按钮-->
		爱好：<input type="checkbox" name="hobby" value="1">看电影
			  <input type="checkbox" name="hobby" value="2">读书
			  <input type="checkbox" name="hobby" value="3">敲代码
			  <input type="checkbox" name="hobby" value="4">看专业书
			  <br>
		<!--下拉框-->
		住址：<select name="address">
				<option value="1">沙河</option>
				<option value="2">西三旗</option>
				<option value="3">月球</option>
				</select>
				<br>
		密码：<input type="password" name="pwd" placeholder="请输入密码"><br>
		上传文件：<input type="file" name="myfile"><br>
		数字范围：<input type="range" name="num" max="10" min="1" defaultValue='1'>	<br>
		文本域：<textarea name="content" id="" cols="300" rows="10"></textarea>
		<!-- 提交 -->
		<input type="submit">
		<!-- 重置 -->
		<input type="reset">
	</form>
</body>
</html>
```

结果如下：

![image-20200731215126652](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200731215126652.png)

## css样式

##### css样式方式

css样式作用装饰html,使页面美化。
css样式的写法有三种：
	第一种：行内样式
		把样式写在标签内部，需要在标签中添加一个属性style，在style中定义样式
	第二种：内部样式表
		在head中定义一个style标签，在这个标签中写当前页面的样式
	第三种：外部样式表
		在html文件外创建.css结尾的文件，在文件中写css样式，引入页面需要使用link标签

css样式：
	1.设置字体大小和颜色
	  font-size:12px（最下大小）;
	  color: 值可以是英文单词 red green yellow
	            还可以是rgb()	rgb(0,0,0) rgb(255,255,255)
	  	      是rgba()	带透明度的颜色值 rgba(0,255,123,0.3)---前三个值是0~255，最后一个值是0~1
	  	      是#000 



```
行内样式表
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
</head>
<body>
    <div style="font-size:30px;color:red;">行内样式表</div>
</body>
</html>
```

```
内部样式表
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
    <style>
        .box{
            font-size: 40px;
            color: rgb(0,255,0);
        }
    </style>
</head>
<body>
    <!--内部样式表,定义一个选择器，然后在head标签中使用style标签进行说明-->
    <div class="box">内部样式表</div>
</body>
</html>
```

```
外部样式表
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
    <!--使用link单标签引入css文件，rel属性默认给值stylesheet，herf标签给文件的路径-->
    <link rel="stylesheet" href="style.css">
</head>
<body>
<!--外部样式表,定义一个选择器，然后在.css文件中进行说明。需要在head标签中，使用link标签将css文件引入-->
<div class="box">外部样式表</div>
<div class="box1">外部样式表</div>
</body>
</html>
```

##### 选择器

3.选择器：
	id选择器：需要在标签上添加 id 属性，给id属性一个变量名 <div id='container'></div>
			  css中通过 #container 找到对应元素，然后可以设置样式
	类选择器：需要在标签上添加 class 属性，给class属性一个变量名 <div class='box'></div>
			  css中通过 .box 找到对应的元素，然后设置样式
	标签选择器：直接找标签的名称(div,span,a,p,input)，然后设置样式
	通用选择器：* 代表所有
	子集选择器：父级>子集
	后代选择器：父级 后代
	伪类选择器：选择器:before/:after
					 :nth-child(n)
					 :nth-of-type(n)

				<div class='box'>
					<p><a></a></p>
					<p></p>
				</div>

​			.box:before{

​			}
​			.box p:nth-child(2){
​				选中第二个p标签
​			}
注意：id选择器一次只能选中 1 元素，页面中id不能出现同名
​	 class、标签选择器每次选中的是多个，class相同类名可以出现多次
​	 nth-child/nth-of-type ：只适用于class/标签选择器,选中的是class/标签的兄弟元素

实例：

```
css文件
/*类选择器*/
.news{
    margin-left: 50px;
}
 /*id选择器*/
#list0{
    list-style: none;
}
/* /*后代选择器+id选择器*/*/
.news #list1{
    list-style: none;
}
/*后代选择器+标签选择器*/
.news #list0 li{
    border-bottom: 3px solid #000;
}
/*子集选择器*/
li>h3{
    display: inline-block;
}
/*通用选择器*/
*{
    margin: 0;
    padding: 0;
}
```

```
html文件
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
    <!--使用link单标签引入css文件，rel属性默认给值stylesheet，herf标签给文件的路径-->
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <!--写一个新闻标签-->
    <div class="news">
        <ul id="list0">
            <li>
                <h3>新闻1</h3>
                <img src="E:\尚学堂\python开发入门\03_第三阶段_web前端开发基础\02_css样式\代码\images\1.jpg" alt="图片加载失败" class="pic">
                <p>新闻1简介</p>
                <p>新华社</p>
            </li>
            <li>
                <h3>新闻1.5</h3>
                <img src="E:\尚学堂\python开发入门\03_第三阶段_web前端开发基础\02_css样式\代码\images\1.jpg" alt="图片加载失败" class="pic">
                <p>新闻1.5简介</p>
                <p>新华社</p>
            </li>
        </ul>
    </div>
    <div class="news">
        <ul id="list1">
            <li>
                <h3>新闻2</h3>
                <img src="E:\尚学堂\python开发入门\03_第三阶段_web前端开发基础\02_css样式\代码\images\2.jpg" alt="图片加载失败" class="pic">
                <p>新闻2简介</p>
                <p>新浪网</p>
            </li>
        </ul>
    </div>
</body>
</html>
```

##### 盒模型

4.盒模型（每一个标签都是盒模型）
	content : 写入内容的地方
	padding：内边距,撑开内容和边框直接的距离
	border：边框
	margin：外边距

块级元素、行内-块级元素可以设置宽高，这里设置的宽和高指的是content的宽高
padding/margin/border都是是四个方向上，四个方向上的值可以不同
四个方向：上为top 下为bottom 左为left 右为right
border由三个属性组成：宽度(border-width)、样式(border-style)、颜色(border-color)

border的简写方式：border:1px solid（实线）/dotted（点线）/dashed（虚线） #000;（三个属性没有顺序要求）
				border-bottom:3px red solid;（只设置下边框）
padding/margin的简写：
	第一种形式：只有一个值，这时四个方向都使用这个值		padding:10px;
	第二种形式：两个值，这时上和下10px,左和右是20px; 		padding:10px 20px; 
	第三种形式：三个值，这时上10，左右20px，下30px 		padding:10px 20px 30px; 
	第四种形式：四个值，上10 ，右20 ，下30，左40		padding:10px 20px 30px 40px;

```
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
    <style>
        <!--内外边距设置为0，清楚默认的设置-->
        *{
            margin: 0;
            padding: 0;
        }
        .box{
            width: 600px;
            height: 400px;
            border: 1px solid #000;
            margin: 50px auto;
        }
        .first{
            width: 200px;
            height: 100px;
            border: 2px dotted red;
            display: inline-block;
            padding: 20px;
            margin-right: 50px;
        }
        .second{
            width: 200px;
            height: 100px;
            border: 2px dashed blue;
            display: inline-block;
        }
    </style>
</head>
<body>
    <div class="box">
        <div class="first">first</div>
        <div class="second">second</div>
    </div>
</body>
</html>
```

##### 字体

5.字体
	font-family: 设置字体(宋体、微软雅黑)
	font-size:字体大小
	font-weight:字体粗细

```
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
    <style>
        <!--内外边距设置为0，清楚默认的设置-->
        *{
            margin: 0;
            padding: 0;
        }
        .box{
            width: 600px;
            height: 400px;
            border: 1px solid #000;
            margin: 50px auto;
        }
        .first{
            width: 200px;
            height: 100px;
            border: 2px dotted red;
            display: inline-block;
            padding: 20px;
            margin-right: 50px;
            font-family: '宋体';
            font-size: 30px;
            font-weight: bold;
        }
        .second{
            width: 200px;
            height: 100px;
            border: 2px dashed blue;
            display: inline-block;
        }
    </style>
</head>
<body>
    <div class="box">
        <div class="first">first</div>
        <div class="second">second</div>
    </div>
</body>
</html>
```

##### 背景

6.背景
	background
	背景颜色：比背景图片更靠近底层。background-color:
	背景图片：background-image:url('图片路径')
	背景图片大小：background-size:x轴方向 y轴方向
	背景定位：background-position:x轴方向 y轴方向（默认是从左上角开始定位）
	背景重复：background-repeat:no-repeat; repeat-x; repeat-y;

```
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
    <style>
        body{
            background-color: blue;
            height: 1000px;
        }
        .box{
            background-color: red;
            background-image: url("images/1.jpg");
            height: 300px;
            background-size: 300px 234px;
            background-repeat: no-repeat;
            background-position: 20px 30px;
        }
    </style>
</head>
<body>
    <div class="box">
        汉字
    </div>
</body>
</html>
```

##### 其他

7.其他小知识点：
	宽：width
	高：height
	行高：line-height
	文字对齐效果：text-align:center/left/right
	溢出隐藏：overflow:hidden
	垂直对齐方式：vertical-align：top
			             middle
			             bottom

##### css案例练习

```
HTML文件
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<link rel="stylesheet" href="css/style.css">
</head>
<body>
	<div id="shangou">
		<div class="container">
			<div class="head">
				<h1>小米闪购</h1>
			</div>
			<div class="content">
				<div  class='product_box shan'>
					<p class="time">18:00 场</p>
					<img src="images/flashpurchase.png" alt="" class="pic">
					<p class="txt">距离开始还有</p>
					<div class='djs'>
						<span class='hour'>01</span>
						<span class='mao'>:</span>
						<span class="hour">53</span>
						<span class="mao">:</span>
						<span class="hour">16</span>
					</div>
				</div>
				<div class='product_box carmmer'>
					<img src="images/1.jpg" alt="" class="pic1">
					<p class="product_info">米家小相机 黑色</p>
					<p class="product_td">清晰捕捉美好瞬间</p>
					<p class="price">
						<span class='now_price'>649 元</span>
						<span class='old_price'>699元</span>
					</p>
				</div>
				<div class='product_box dao'>
					<img src="images/1.jpg" alt="" class="pic1">
					<p class="product_info">米家小相机 黑色</p>
					<p class="product_td">清晰捕捉美好瞬间</p>
					<p class="price">
						<span class='now_price'>649 元</span>
						<span class='old_price'>699元</span>
					</p>
				</div>
				<div class='product_box computer'>
					<img src="images/1.jpg" alt="" class="pic1">
					<p class="product_info">米家小相机 黑色</p>
					<p class="product_td">清晰捕捉美好瞬间</p>
					<p class="price">
						<span class='now_price'>649 元</span>
						<span class='old_price'>699元</span>
					</p>
				</div>
				<div class='product_box tv'>
					<img src="images/1.jpg" alt="" class="pic1">
					<p class="product_info">米家小相机 黑色</p>
					<p class="product_td">清晰捕捉美好瞬间</p>
					<p class="price">
						<span class='now_price'>649 元</span>
						<span class='old_price'>699元</span>
					</p>
				</div>
			</div>
		</div>
	</div>
</body>
</html>
```

```
css文件
*{
	margin: 0;
	padding: 0;
}
#shangou{
	width:100%;
	padding:40px 0;
	background-color: #F5F5F5;
}
.container{
	width:1224px;
	margin:0 auto;
	height: 1000px;
}
.head{
	margin-bottom: 20px;
}
.content{
	height: 1000px;
}
.content .product_box{
	display: inline-block;
	vertical-align: top;
	width:235px;
	height: 340px;
	background-color: #fff;
	text-align: center;
	margin-right: 5px;
}
.content>div:nth-child(1){
	background-color: #F1EDED;
}

.product_box .time{
	color:#EF3A3B;
	margin-top:62px;
	font-size:20px;
	margin-bottom: 32px;
	font-weight: bold;
}
.product_box .txt{
	margin-top: 35px;
	margin-bottom: 32px;
}
.product_box .hour{
	width: 48px;
	height: 48px;
	background-color: #605751;
	color:#fff;
	font-size:24px;
	display: inline-block;
	font-weight: bold;
	text-align: center;
	line-height: 48px;
}
.product_box .mao{
	font-size:24px;
	font-weight: bold;
	color:rgba(0,0,0,0.5);
}
.product_box .djs{
	margin-bottom: 30px;
}
.shan{
	border-top:1px solid #E53935;
}
.tv{
	margin-right: 0;
}

.product_box .pic1{
	width: 160px;
	height: 160px;
	margin-top:20px;
	margin-bottom: 23px;
}
.product_box .product_info{
	font-size:14px;
	font-weight: 400;
}
.product_box .product_td{
	color:#B2B2B2;
	font-size:14px;
	margin-top:3px;
	margin-bottom: 12px;
}
.product_box .now_price{
	color:#FA721E;
}
.product_box .old_price{
	color:#ADADAD;
	text-decoration: line-through;
}
```

##### 浮动

2.浮动
	让元素脱离文档流，“漂”起来。

文档流：前端页面在浏览器中展示时是从左上角开始排练，横向从左到右依次排练行内元素或行内块元素，纵向是从上到下依次排练块级元素。

浮动关键字：float: left / right

浮动后：元素会脱离文档流，"漂"在离它最近的上一个块级元素之后，变成行内-块级元素

```
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
        <style>
            div{
                border: 1px solid #000;
            }
            .two{
                float: left;
            }
        </style>

</head>
<body>
    <div class="first">first</div>
    <div class="two">two</div>
    <div class="three">three</div>
</body>
</html>
```

结果如下：

![image-20200804214049117](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200804214049117.png)

元素浮动后一个问题：
	浮动元素后面元素会受浮动影响，使用浮动后需要清除浮动
	清除浮动方案：
		1.添加一个空标签，给空标签设置clear属性 clear:left / right / both
		2.给有浮动的元素添加一个父级元素，然后让父级元素清除浮动(overflow: hidden;)

##### 定位

3.定位
	定位关键字：position
	定位：相对定位、绝对定位、固定定位
	相对定位(relative)：是元素本身相对自己的一个偏移量，但不脱离文档流

```
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
        <style>
            *{
                margin: 0;
                padding: 0;
            }
            div{
                width: 600px;
                height: 400px;
                border: 1px solid #000;
            }
            .one{
                width: 100px;
                height: 100px;
                border: 1px dotted red;
                /*相对定位*/
                position: relative;
                top: 100px;
            }

        </style>

</head>
<body>
    <div>
        <div class="one">haha</div>
    </div>

</body>
</html>
```

结果如下：

![image-20200804220145837](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200804220145837.png)

绝对定位(absolute)：是元素相当于父级(会有一个相对定位)的一个偏移量，是脱离文档流的

```
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
        <style>
            *{
                margin: 0;
                padding: 0;
            }
            .box{
                width: 600px;
                height: 400px;
                border: 1px solid #000;

            }
            .one{
                width: 100px;
                height: 100px;
                border: 1px dotted red;
                float: left;
                /*绝对定位*/
                position: absolute;
                top: 100px;
            }
            .ck{
                width: 100px;
                height: 100px;
                border: 1px dotted red;
                float: left;
            }

        </style>

</head>
<body>
    <div class="box">
        <div class="one">haha</div>
        <div class="ck">参考盒子</div>

    </div>

</body>
</html>
```

![image-20200804221350634](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200804221350634.png)

固定定位(fixed)：相当于浏览器窗口定位，不会随页面滚动发生位置改变，也是脱离文档流的



定位有四个方向：
	top:相对顶部的偏移量
	bottom:相对顶部的偏移量
	left:相对左边的偏移量
	right:相对右边的偏移量

hover属性：鼠标放上去的效果，鼠标离开后会恢复到原来的效果
	元素:hover{

}

练习：轮播图案例

```
html文件
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<link rel="stylesheet" href="css/lbt.css">
</head>
<body>
	<!-- 轮播图布局 -->
	<div class="cousal">
		<!-- 轮播内容 -->
		<div class="slideWrapper">
			<div><img src="images/banner1.jpg" alt=""></div>
			<div><img src="images/banner2.jpg" alt=""></div>
			<div><img src="images/banner3.jpg" alt=""></div>
			<div><img src="images/banner4.jpg" alt=""></div>
			<div><img src="images/banner5.jpg" alt=""></div>
		</div>
		<!-- 左右按钮 -->
		<div class="prev"></div>
		<div class="next"></div>
		<!-- 快捷导航 -->
		<div class="cricle">
			<ul>
				<li class="active"></li>
				<li></li>
				<li></li>
				<li></li>
				<li></li>
			</ul>
		</div>
	</div>
</body>
</html>
```

```
css文件
*{
	margin: 0;
	padding: 0;
}
.cousal{
	width: 993px;
	height: 460px;
	position: relative;
	overflow: hidden;
}
.slideWrapper{
	width:4965px;
	overflow: hidden;
}
.slideWrapper>div{
	float: left;
}
.slideWrapper img{
	width: 993px;
	height: 460px;
}
.prev{
	position: absolute;
	top:195.5px;
	left:0;
	width:42px;
	height: 69px;
	background-image: url('../images/icon-slides.png');
	background-repeat: no-repeat;
	background-position: -89px 0px;
}
.prev:hover{
	background-image: url('../images/icon-slides.png')
	background-repeat: no-repeat;
	background-position: 0px 0px;
}
.next{
	position: absolute;
	top:195.5px;
	right:0;
	width:42px;
	height: 69px;
	background-image: url('../images/icon-slides.png');
	background-repeat: no-repeat;
	background-position: -126px 0px;
}
.next:hover{
	background-image: url('../images/icon-slides.png')
	background-repeat: no-repeat;
	background-position: -41px 0px;
}
.cricle{
	position: absolute;
	bottom: 25px;
	right: 35px;
}
ul{
	list-style: none;
}
.cricle li{
	width:6px;
	height: 6px;
	border: 3px solid #C6BEB8;
	float: left;
	margin-right: 10px;
	cursor: pointer;
	border-radius: 50%;
	background-color: #958C86;
}
.cricle li.active{
	background-color: #ffffff;
}
.cricle li:hover{
	background-color: #ffffff;
}
```

## js学习

### js基础

##### js基本语法

1.js基本语法
	1.js引入方式
	js是脚本语言，可以在浏览器中执行。js文件是以.js为结尾的，引入html文件中时使用script标签，这时script需要添加一个属性src，src中写js文件的路径；但是js还可以直接写在html当中，在html中需要使用<script></script>标签中写js代码

在html内部写js时，script标签可以放在head中，可以放在body中，还可以放在body后

2.js基本语法
	js执行顺序，默认是顺序结构，是从上到下，从左到右执行
	js一般一行放一条语句，语句后结束标识是 ";" ,但是结束标识不强制写
	js中换行要求：没有换行要求，最标准的缩进是一个tab。
	js中 if选择/for循环/函数function 后面的语句块都是由 {} 包裹的

3.变量和常量
	定义变量：var 变量名（全局变量） 
		let 变量名（局部变量）
	定义常量：const 常量名
	变量名的命名规范：
		1.组成：字母、数字、下划线、$
		2.首字符不能是数字
		3.不能使用关键字
		4.建议使用驼峰命名法

​	使用变量或常量：
​		1.直接访问：变量名或常量名
​		2.重新赋值：常量不能被重新赋值。变量可以重新赋值，变量中只会保存最后一次赋值。

4.注释：
	第一种：单行注释： // 注释内容
	第二种：多行注释： /* 中间注释内容 */
	第三种：多行文本注释： /** 注释内容 */

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>	
</body>
<script>
	// 定义变量
	var num = 1
	let str = 4
	// 使用变量
	// alert(str)
	// 定义常量
	const HOST = 'www.baidu.com'
	//使用常量
	alert(HOST)
	// 常量不能被重新赋值
	//HOST = 'www.sina.com'
</script>
</html>
```

5.基本数据类型
		1.数字类型(int float) : 1,2,3  3.14
		2.字符串类型(string) : 单引号或双引号引起来的字符，单引号双引号作用一样，没区别
		3.布尔类型(bealoon): true(1) 表示真  false(0) 表示假
		4.undefined类型(undefined)： 变量或对象的属性没有赋值时，默认值就是undefined
		5.null类型(null):表示空
		6.对象类型：
			数组(array): 类似python中的List，定义方式 [1,'a',true]，通过下标访问元素
			对象(object):类似python中的dict ，定义{"username":"小明","age":18}，通过键名访问
			正则表达式:同python
		检查数据类型方法：typeof 
			注意：typeof 检测对象类型时，不管是数组还是对象，返回的都是Object

6.输出方式：
	alert()：小括号中写变量或语句，窗口弹出
	console.log():在控制台输出 F12->console

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
</body>
<script>
	//定义变量,赋值
	var str = '字符串'

	let arr = [1,'a',true]

	let obj = {
		"name":"小明",
		"age":18
	}
	//通过控制台输出数据类型
	console.log(typeof str)
	console.log(typeof arr)
	console.log(typeof obj)
</script>
</html>
```

7.运算符：
		1.算数运算： + - * / %
			除法： 会运算到小数位 ，没有 // 求整
			取余： 运算到该加小数点时的余数
		2.关系运算： > >= < <= == === != !== 
			===和==区别:
				==是不判断数据类型： 1 == '1'   返回值 true
				===判断数据类型： 1 === '1'	返回值 false
		3.逻辑运算： &&(逻辑与)  ||(逻辑或)  !(逻辑非)
			没有and / or
			逻辑与、逻辑或都会存在短路运算：
				逻辑与 左边为false，右边不判断直接返回false，左边为true，返回值是右边
				逻辑或 左边为true，右边不判断直接返回 true，左边为false，返回值是右边

​	4.赋值运算： = += -= *= /= %= ++(自增) --(自建)
​		++ 、 --：
​			用法1： 变量名++ ： 本次不改变，下次使用时改变
​			用法2： ++变量名 ： 先改变后使用，当次生效

​    8.parseInt() parseFloat()
​			parseInt() ： 取小括号中整数部分
​			parseFloat() : 取小括号中整数+小数部分

##### 流程控制语句

2.流程控制语句
	1.选择结构
		if
			单分支：if(表达式){} 
			双分支：if(表达式){语句} else{语句}
			多分支：if(表达式1){} else if(表达式2){} else{}

​	switch
​		switch(表达式){
​			case 值: 语句块 ;break;
​			case 值2: 语句块； break；
​			default:语句（到前面的都匹配不到时，执行这条分支）
​		}
2.循环结构
​	for
​		普通for循环：
​			for(表达式1;表达式2;表达式3){循环体}
​			表达式1：循环条件的初始值
​			表达式2：循环条件的终止值
​			表达式3：循环条件的步长

​			for(let i=0; i<3 ; i+=1){

​			}

​		for-in循环：
​			for(let i in [1,2,3]){循环体}
​	while
​		表达式1（确定初始值）
​		while(表达式2){
​			循环体;
​			表达式3（确定步长）
​		}

3.数学方法：
	Math.random()  产生[0,1)之间的随机数 
4.获取字符串或数组的长度：
	通过.length 属性获取
	'abcd'.length
	[1,2,'a','b'].length

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
</body>
<script>
	var str = 'abcdefghijklmnopqrstuvwxyz1234567890';
	var yzm = ''
	// 生成普通四位数验证码
	for(var i=0; i<4; i++){
		//找下标
		var num = null;
		num = parseInt(Math.random() * str.length)
		yzm+=str[num]
	}
	console.log(yzm)
	// 生成不重复的验证码
	var strlen = 0
	var obj = {}
	var yzm2 = ''
	while(strlen<4){
		var num2 = null;
		num = parseInt(Math.random() * str.length)
		//保存下标，对象中没有这个下标，保存这个下标
		if(!obj[num]){
			obj[num] = 1
			strlen++
			yzm2+=str[num]
		}
	}
	console.log(yzm2)
</script>
</html>
```

##### js选择器

3.js选择器
	选择器作用：找页面中的标签
	  选择器类型：id选择器
	  				document.getElementById('id名')
	  				返回值：1个具体的标签元素
	  	     class选择器
	  			 	document.getElementsByClassName('class名');
	  			 	返回值：所有具有指定class名称的元素，是多个，以类数组形式存在，使用某一个元素时通过下标来获取
	  	     标签选择器
	  			 	document.getElmentsByTagName('标签名');
	  			 	返回值：所有指定标签的集合

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<div id="box">
		具有id的元素
	</div>
	<div class="container">
		具有class类名的元素
	</div>

	<p>p标签元素</p>
</body>
<script>
	//通过id获取元素
	var box = document.getElementById('box')
	console.log(box)
	//通过class类名获取元素
	var containers = document.getElementsByClassName('container')
	console.log(containers)
	// 通过标签获取元素
	var ps = document.getElementsByTagName('p')
	console.log(ps[0])
</script>
</html>
```

4.操作基本dom
	1.获取标签中值
	第一类：获取双标签中的值(div,span,p) 
			    .innerHTML 来获取

​	第二类：获取input标签中的值()
​			.value 来获取
​	特殊的一个标签：
​		textarea 文本域：是双标签，但是获取他的值时使用.value属性

   2.添加点击事件
    	事件：是一个具有某些功能的函数
    	点击事件：鼠标点击某个元素的时候触发的功能
    	添加点击事件方法：
    		1.找到元素
    		2.元素.onclick = function(){}

3.设置值
	第一类：设置双标签的值
		元素.innerHTML = '新值'
	第二类：设置input标签的值
		元素.value = '新值'

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<div id="box">
		id为box的div
	</div>
	用户名：<input type="text" id="username"  >
	<textarea name="" id="info" cols="30" rows="10"></textarea>
	<button id="btn">点我</button>
</body>
<script>
	//找到标签
	var box = document.getElementById('box')
	// 获取标签中的值
	var box_content = box.innerHTML
	console.log(box_content)
	// 获取Input标签
	var username = document.getElementById('username')
	var info = document.getElementById('info')
	var username_content = username.value
	console.log(username_content)
	var btn = document.getElementById('btn')
	btn.onclick = function(){
		username_content = username.value
		info_content = info.value
		console.log(username_content,info_content)
	}
	// 设置值
	box.innerHTML = 'div标签中新的值'
	username.value = 'input标签中新的值'
	info.innerHTML = 'textarea文本域标签中新的值'
</script>
</html>
```

 4.获取属性和修改属性值
    	属性有：id , class , name , src ,href , style
    	1.获取属性
    		元素.getAttribute('属性名')
    	2.设置属性值
    		元素.setAttribute('属性名','值')

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		#box{
			font-size:20px;
		}
	</style>
</head>
<body>
	<div id='box' class="content box2 box3" style='color:red'>div标签</div>
	<a href="www.baidu.com">跳转到xx</a>
	<img src="../day03/images/banner1.jpg" alt="">
</body>
<script>
	//获取属性值
	var box = document.getElementById('box')
	console.log(box.getAttribute('class'),box.getAttribute('id'))

	var Alla = document.getElementsByTagName('a')
	console.log(Alla[0].getAttribute('href'))
	
	var Allimg = document.getElementsByTagName('img')
	console.log(Allimg[0].getAttribute('src'))
	// 设置属性值
	Allimg[0].setAttribute('src','../day03/images/banner2.jpg')
</script>
</html>
```

5.获取和修改css样式
	1.获取css样式
		第一类 行内样式： 元素.style.样式名称
		第二类 内部、外部样式： window.getComputedStyle(元素)['样式名称']

​	2.设置css样式
​		元素.style.样式名 = 新值

​	注意：获取或设置 font-size 类型的样式时，需要变成驼峰命名法(fontSize)

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		#box{
			font-size:30px;
		}
	</style>
</head>
<body>
	<div id="box" style="color:red">div容器</div>
</body>
<script>
	//找元素
	var box = document.getElementById('box')
	// 获取行内样式
	console.log(box.style.color)
	console.log(box.style.fontSize)
	// 获取内部样式表，外部样式中的样式
	console.log(window.getComputedStyle(box)['fontSize'])
	console.log(window.getComputedStyle(box)['color'])
	// 设置样式
	box.style.color = 'green'
	box.style.fontSize = '60px'
</script>
</html>
```

案例：体质计算

体质指数（BMI）= 体重（kg）÷ 身高^2（m）
	当BMI指数为18.5～23.9时属正常

```
html文件
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		.container{
			width:600px;
			padding:30px 20px;
			margin:20px auto;
			border: 1px solid #000;
		}
		.container span{
			display: inline-block;
			width:200px;
			height: 30px;
			text-align: right;
		}
		.container .res{
			text-align: left;
		}
		.container input{
			width:300px;
			height: 30px;
		}
		#btn{
			width:100px;
			height: 40px;
			border:none;
			background-color: orange;
			color:#fff;
			font-size:24px;
			display: block;
			margin: 10px auto;
			cursor: pointer;
		}
		.data{
			margin-top:20px;
			border-top:1px solid #000;
			padding-top:10px;
		}
		#result{
			height: 30px;
			background-repeat: no-repeat;
			background-size: 30px 30px;
			padding-left: 35px;
		}
	</style>
</head>
<body>
	<div class="container">
		<p>
			<span>体重：</span>
			<input type="text" placeholder="请输入体重，单位kg" id="tz" >
		</p>
		<p>
			<span>身高：</span>
			<input type="text" placeholder="请输入身高，单位m" id="ht">
		</p>
		<p>
			<button id="btn">计算</button>
		</p>
		<div class="data">
			<span class="res">计算结果：</span>
			<p id="result"></p>
		</div>
	</div>
</body>
<script src="tizhi.js"></script>
</html>
```

```
js文件
// 获取按钮，身高，体重标签
var btn = document.getElementById('btn')
var ht = document.getElementById('ht')
var tz = document.getElementById('tz')

//绑定点击事件
btn.onclick = function(){
	//获取用户输入的身高和体重
	var user_height = ht.value
	var user_weight = tz.value
	var str = ''
	
	var result = document.getElementById('result')

	// 体质指数（BMI）= 体重（kg）÷ 身高^2（m）
	// 计算体质指数
	var BMI = user_weight / (user_height*user_height)

	// 判断体质指数在哪个区间  <18.5 偏瘦 18.5——23.9 正常 >23.9 偏胖
	if(BMI<18.5){
		str = '偏瘦'
		// 操作样式
		result.style.backgroundImage = "url('images/sou.jpg')"
	}else if(BMI>=18.5&&BMI<=23.9){
		str = '正常'
		result.style.backgroundImage = "url('images/zc.jpg')"
	}else{
		str = '偏胖'
		result.style.backgroundImage = "url('images/pang.jpg')"
	}
	// 把str的值设置到 id为result的p标签中
	result.innerHTML = str

}
```

### js对象的属性及方法

##### 字符串对象

1.字符串对象
	var str = 'abcd;edf;'
	属性：
		长度属性：length

```
<script>
    var str = "Hello everyone"
    console.log(str.length)
</script>
结果：14
```

​	方法：
​	indexOf('字符',start) : 检测指定字符在字符串中是否存在，如果存在返回下标，如果不存在返回-1(不是python中的反向找下标，这的意思就是没有找到)，第二个参数：指定从哪个下标开始向后查询

```
<script>
    var str = "Hello everyone;Hello world"
    console.log(str.indexOf("e"))
</script>
结果：1
```

​	slice(start,end) 、substr(start,length) 、substring(start,end):字符串截取，返回新字符串，不改变原字符串

```
<script>
    var str = "Hello everyone;Hello world"
    console.log(str.slice(15,26))
</script>
结果：Hello world
```

​	split('分割规则') : 字符串分割,分割后返回数组(列表)

```
<script>
    var str = "Hello everyone;Hello world"
    console.log(str.split(";"))
</script>
结果：["Hello everyone", "Hello world"]

```

​	replace(old,new) : 字符串替换

```
<script>
    var str = "Hello everyone;Hello world"
    console.log(str.replace("Hello","你好"))
</script>
结果：你好 everyone;Hello world-------注意，只会替换第一个
```

```
<script>
    var str = "Hello everyone;Hello world"
    console.log(str.replace(/Hello/g,"你好"))
</script>
结果：你好 everyone;你好 world------全局替换
```

​	match('字符') : 字符串匹配,返回数组

```
<script>
    var str = "Hello everyone;Hello world"
    console.log(str.match("Hello"))
</script>
结果：["Hello", index: 0, input: "Hello everyone;Hello world", groups: undefined]---返回一个列表
```

​	trim() : 去除字符串左右空白

```
<script>
    var str = " Hello everyone;Hello world "
    console.log(str.trim())
</script>
结果：Hello everyone;Hello world
```

​	toLowerCase() : 把字符串转成小写

```
<script>
    var str = " Hello everyone;Hello world "
    console.log(str.toLowerCase())
    console.log(str.toUpperCase())
</script>
结果： hello everyone;hello world 
	  HELLO EVERYONE;HELLO WORLD 
```

字符串练习

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<input type="text" id="username"><br>
	<input type="password" id="userpwd"><br>
	<button id="btn">登录</button>
</body>
<script>
	/**
	 * 1.点击登录按钮，获取用户输入信息，组成这样的字符串 
	 * 	key=value&key=value
	 *
	 * 2.找指定的cookie值 ： 查找ORIGIN对应的值
	 *  cookie字符串："BAIDUID=6848B473EF50AE27A9B71CABEFCA49B2:FG=1; BIDUPSID=6848B473EF50AE27A9B71CABEFCA49B2; PSTM=1520569296; BD_UPN=12314353; MCITY=-%3A; BDORZ=FFFB88E999055A3F8A630C64834BD6D0; FP_UID=d725dde8a25ece7393c40192702ca6ef; BD_HOME=0; ORIGIN=2; BDRCVFR[uZj3G_6bTl0]=mk3SLVN4HKm; BD_CK_SAM=1; PSINO=1; pgv_pvi=2502878208; pgv_si=s6538584064; H_PS_PSSID=26748_1436_26432_21080_26350_22158"
	 *  
	 *  3.把手机号中间4位换成*号
	 *  如：13900264678 -> 139****4678
	 */
	
	// 第一个：组成字符串 + 字符串拼接
	var btn = document.getElementById('btn')
	var username = document.getElementById('username')
	var userpwd = document.getElementById('userpwd')
	btn.onclick = function(){
		var username_val = username.value
		var userpwd_val = userpwd.value
		var str = ''
		str = 'username='+username_val+'&'+'upwd='+userpwd_val
		console.log(str)
	}
	
	// 第二题
	var cookie = "BAIDUID=6848B473EF50AE27A9B71CABEFCA49B2:FG=1; BIDUPSID=6848B473EF50AE27A9B71CABEFCA49B2; PSTM=1520569296; BD_UPN=12314353; MCITY=-%3A; BDORZ=FFFB88E999055A3F8A630C64834BD6D0; FP_UID=d725dde8a25ece7393c40192702ca6ef; BD_HOME=0; ORIGIN=fwfji0uwtgtsh; BDRCVFR[uZj3G_6bTl0]=mk3SLVN4HKm; BD_CK_SAM=1; PSINO=1; pgv_pvi=2502878208; pgv_si=s6538584064; H_PS_PSSID=26748_1436_26432_21080_26350_22158"
	// 第一种做法：字符串截取 ，需要下标：1个下标是ORIGIN后=的下标，还有1个是ORIGIN后的分号下标
	// var Oindex = cookie.indexOf('ORIGIN')
	// var firstindex = Oindex+'ORIGIN'.length+1
	// var secondindex = cookie.indexOf(';',firstindex)
	// var val = cookie.slice(firstindex,secondindex)
	// console.log(val)

	//第二种方式：字符串分割
	var arr = cookie.split(';')
	for(var i=0; i<arr.length; i++){
		var arr2 = arr[i].split('=')
		if(arr2[0].trim()=='ORIGIN'){
			console.log(arr2[1])
		}
	}
	
	//3.手机号
	var phonenumber = '13900264678'
	//第一种方法：字符串截取
	var newphonenum = phonenumber.slice(0,3)+'****'+phonenumber.slice(7)
	console.log(newphonenum)

	//第二种方法：字符串替换
	var newphonenum2 = phonenumber.replace(/^(\d{3})\d{4}(\d+)/,'$1****$2')
	console.log(newphonenum2)
</script>
</html>
```

##### 数组对象

2.数组对象(列表)
	属性：
		长度属性：length
	方法：
		头部添加：unshift() 		返回值是数组的新长度，改变原数组

```
<script>
    var list0 = [1,2,3,"s","sw"]
    var list1 = list0.unshift("naoko")
    console.log(list1)
    console.log(list0)
</script>
结果:6
    (6) ["naoko", 1, 2, 3, "s", "sw"]
```

​		尾部添加：push()		返回值是数组的新长度，改变原数组

```
<script>
    var list0 = [1,2,3,"s","sw"]
    var list1 = list0.push("naoko")
    console.log(list1)
    console.log(list0)
</script>
结果：6
	 (6) [1, 2, 3, "s", "sw", "naoko"]
```

​		头部删除：shift()		返回值是被删除的元素,改变原数组

```
<script>
    var list0 = ["one",2,3,"s","sw"]
    var list1 = list0.shift()
    console.log(list1)
    console.log(list0)
</script>
结果：
one
(4) [2, 3, "s", "sw"]
```

​		尾部删除：pop()		返回值是被删除的元素,改变原数组

```
<script>
    var list0 = ["one",2,3,"s","sw"]
    var list1 = list0.pop()
    console.log(list1)
    console.log(list0)
</script>
结果：
sw
(4) ["one", 2, 3, "s"]
```

​		修改： splice(start,len,el,el...) 	执行时分两步，第一步删除(会删除从指定位置开始的指定长度)，第二步添加功能(len后的el是添加的元素，每个元素之间用逗号隔开)

```
<script>
    var list0 = ["one",2,3,"s","sw"]
    var list1 = list0.splice(1,3,"two","three","four")
    console.log(list1)
    console.log(list0)
</script>
结果：
(3) [2, 3, "s"]
(5) ["one", "two", "three", "four", "sw"]
```

​		截取： slice(start,end)	返回新数组，不会改变原数组

```
<script>
    var list0 = ["one",2,3,"s","sw"]
    var list1 = list0.slice(1,3)
    console.log(list1)
    console.log(list0)
</script>
结果：
(2) [2, 3]
(5) ["one", 2, 3, "s", "sw"]
```

​		把数组按某种规则转成字符串：join('规则')

```
<script>
    var list0 = ["one",2,3,"s","sw"]
    var list1 = list0.join("@")
    console.log(list1)
    console.log(list0)
</script>
结果：
one@2@3@s@sw
(5) ["one", 2, 3, "s", "sw"]
```

​		检测指定字符在字符串中是否存在：indexOf()

```
<script>
    var list0 = ["one",2,3,"s","sw"]
    var list1 = list0.indexOf("sw")
    console.log(list1)
    console.log(list0)
</script>
结果：
4
(5) ["one", 2, 3, "s", "sw"]
```

数组遍历：

​	1.普通for循环
​		for(var i=0; i<arr.length; i++){
​			i 	对应下标
​			arr[i]	对应数组中的元素
​		}
​	2.for-in
​		for(var i in arr){
​			i 	对应下标
​			arr[i]	对应元素
​		}

##### 字典对象

3.对象(字典)
	定义对象： var obj = {}
	对象中的数据形式：
		{
			key:value,
			key:value
		}
	对象中的key具有唯一性，如果给已经存在的key赋值，这时是更新功能;如果对象中没有这个key，这时对象中新添加一个key:value键值对

key一定要是不可变元素

value可以是任意数据类型

常用属性：
	长度：Object.keys(对象).length

```
<script>
    var book = {
        bookname:"python入门",
        author:"xbd",
        cbs:"人民出版社",
        price:"39.9"
    }
    var iss = Object.keys(book).length
    console.log(iss)
</script>
结果：4
```

访问数据：
	1.访问某一个：对象.key  或者 对象['key'] 
		如果存在key，同时又对应的值，返回值
		如果不存在key，返回undefined

```
<script>
    var book = {
        bookname:"python入门",
        author:"xbd",
        cbs:"人民出版社",
        price:"39.9"
    }
    var iss =book["bookname"]
    console.log(iss)
</script>
结果：
python入门
```

​	2.遍历:for-in-----i对应键名

```
<script>
    var book = {
        bookname:"python入门",
        author:"xbd",
        cbs:"人民出版社",
        price:"39.9"
    }
    for(i in book){
        console.log(i)
        console.log(book[i])
    }
</script>
结果：
bookname
python入门
author
xbd
cbs
人民出版社
price
39.9
```

练习：图书管理系统

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		p{
			text-align: center;
		}
	</style>
</head>
<body>
	<h1 align="center">图书馆管理系统</h1>
<p>
	<span>书名：</span>
	<input type="text" placeholder='请输入书名' id="bookName">
	<br/>
	<span>作者：</span>
	<input type="text" placeholder='请输入作者' id="bookAuthor">
	<br/>
	<span>价格：</span>
	<input type="text" placeholder='请输入价格' id="bookPrice">
	<br/>
</p>
<p>
	<button id="selectBtn">查询所有书籍信息</button>
	<button id="insertBtn">添加新书籍信息</button>
</p>
<hr/>
<h3 align="center">删除书籍信息</h3>
<p>
	<span>要删除的书籍名称：</span>
	<input type="text" placeholder='请输入要删除的书籍名称' id="deleteBookName">
	<button id="deleteBtn">删除指定书籍信息</button>
</p>
<hr/>
</body>
<script>
	/**
	 * 一本书：
	 * 		书名
	 * 		作者
	 * 		价钱
	 * 		出版社
	 * 		简介
	 * 存储一本书最好的方式：
	 * 	使用字典
	 *
	 * 存储多本书：
	 *  用列表包含多个字典
	 *  [{},{},{}]
	 */
	var booklist = []
	// 添加图书
	var insertBtn = document.getElementById('insertBtn')
	insertBtn.onclick = function(){
		var bookName = document.getElementById('bookName').value
		var bookAuthor = document.getElementById('bookAuthor').value
		var bookPrice = document.getElementById('bookPrice').value
		var book = {}
		book.bookName = bookName
		book.bookAuthor = bookAuthor
		book.bookPrice = bookPrice
		//把字典添加到列表中
		booklist.push(book)
	}

	//查看所有图书
	var selectBtn = document.getElementById('selectBtn')
	selectBtn.onclick = function(){
		for(var i in booklist){
			console.log(booklist[i])
		}
	}


	//删除功能：找到指定书名在列表中的那个字典中，获取这个字典在列表中的下标，最后从列表中删除这个字典
	var deleteBtn = document.getElementById('deleteBtn')
	deleteBtn.onclick = function(){
		var deleteBookName = document.getElementById('deleteBookName').value
		for(var i in booklist){
			if(booklist[i]['bookName'] == deleteBookName){
				console.log('下标是：'+i)
				booklist.splice(i,1)	
			}
		}
	}
</script>
</html>
```

##### 函数

4.函数
	定义函数：
		1. function 函数名(形参列表){
				功能体
				return 可以有，也可以没有
			}
		2. var 变量名 = function(){
				功能体
			}
	调用函数：
		函数名(实参列表)

和python中不一样的：
	形参和实参个数要求：在python中少传参数报错，在js中少传参数没问题(没有参数的地方自动接收undefined)

​	js中只有简单的传参，python中的高级传参方式都没有；
​	js中可以给形参默认值
​	js函数中有一个特殊的关键字，作用是获取函数调用时传入的所有实参 arguments

##### 数学方法

1.Math数学方法
	js中数学方法都被封装在Math对象中，使用时调用Math.方法名称即可
	常用的方法：
		Math.random() 	随机数 [0,1) ,没参数

```
// 随机数 Math.random()
	function randomNumber(m,n){
		// 产生两个指定数之间的随机： Math.random()*(n-m+1) + m 
		return Math.floor(m + Math.random()*(n-m+1))
	}
```

​		Math.floor() 	向下取整	，没有参数

​		Math.ceil() 	向上取整 ，没有参数
​		Math.round()	四舍五入
​		Math.max()		最大值	，可以接收多个参数，然后判断出最大值
​		Math.min()		最小值	，可以接收多个参数，然后判断出最小值
​		Math.PI()		π 		，没参数

##### 时间

2.时间
	js时间是由 Date() 构造函数生成的，使用时需要通过 new 关键字创建
	new Date() 当前时间---括号内可以加一个时间戳，如果不加就默认是现在的时间戳

```
<script>
    var time = new Date()
    console.log(time)
</script>
结果：
Sat Aug 08 2020 19:47:22 GMT+0800 (中国标准时间)
```

​	可以通过它的方法取到里面的每一个独立项
​	获取年份：new Date().getFullYear()
​	获取月份：getMonth() 0~11
​	获取日期：getDate()  1~31
​	获取星期：getDay()   0~6
​	获取小时：getHours() 0~23
​	获取分钟：getMunites() 0~59
​	获取秒数：getSeconds() 0~59
​	时间戳：getTime()	毫秒数

世界时：toGMTString() /toUTCString()
转换本地时间：toLocalString()

##### 定时器

3.定时器
	定时器的时间是毫秒单位
	1.间隔定时器
		每隔一段时间就执行定时器的功能
		var time1 = setInterval(funciton,time)

​	关闭间隔定时器：
​		clearInterval(time1)

```
var time1 = setInterval(function(){
		console.log(new Date())
	},1000)

	var btn1 = document.getElementById('btn1')
	bnt1.onclick = function(){
		clearInterval(time1)
	}
```

2.延时定时器
	等待指定的时间，然后执行唯一一次功能
	var time2 = setTimeout(function,time)

​	关闭延时定时器：
​		clearTimeout(time2)

```
var time2 = setTimeout(function(){
		console.log('炸弹爆炸')
	},10000)

	var bnt2 = document.getElementById('bnt2')
	bnt2.onclick = function(){
		clearTimeout(time2)
	}
```

案例：秒杀倒计时

```
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        .box{
            margin: 100px auto;
            border: 3px solid red;
            width: 200px;
            clear: both;
            height: 50px;
        }
        .box2 p{
            display: inline-block;
            height: 50px;
            text-align: center;
            vertical-align: middle;
        }
        #hour{
            width: 50px;
            background-color: antiquewhite;
            border: 1px solid black;
            font-size: 30px;
        }
        .maohao{
            font-size: 30px;
        }
        #munite{
            width: 50px;
            background-color: antiquewhite;
            border: 1px solid black;
            font-size: 30px;
        }
        #second{
            width: 50px;
            background-color: antiquewhite;
            border: 1px solid black;
            font-size: 30px;
        }
        .box2{
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="box">
        <div class="box2">
            <p id="hour"></p>
            <p class="maohao">:</p>
            <p id="munite"></p>
            <p class="maohao">:</p>
            <p id="second"></p>
        </div>
    </div>
</body>
<script>
    function sjc(){
        var time1 = new Date("2020-8-9 12:00:00").getTime()
        var time2 = new Date().getTime()
        var cha = time1 - time2
        return cha
    }
    function hour0(){
        var cha = sjc()
        var hour0 = Math.floor(cha/(1000*60*60))
        return hour0
    }
    function munite0(){
        var cha = sjc()
        var munite0 = Math.floor((cha/(1000*60))%60)
        return munite0
    }
    function second0(){
        var cha = sjc()
        var second0 = Math.floor((cha/1000)%60)
        return second0
    }
    function sxian(){
        var hour = document.getElementById("hour")
        hour.innerHTML = hour0()
        var munite = document.getElementById("munite")
        munite.innerHTML = munite0()
        var second = document.getElementById("second")
        second.innerHTML = second0()
    }
    sxian()
    setInterval(sxian,1000)
</script>
</html><!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        .box{
            margin: 100px auto;
            border: 3px solid red;
            width: 200px;
            clear: both;
            height: 50px;
        }
        .box2 p{
            display: inline-block;
            height: 50px;
            text-align: center;
            vertical-align: middle;
        }
        #hour{
            width: 50px;
            background-color: antiquewhite;
            border: 1px solid black;
            font-size: 30px;
        }
        .maohao{
            font-size: 30px;
        }
        #munite{
            width: 50px;
            background-color: antiquewhite;
            border: 1px solid black;
            font-size: 30px;
        }
        #second{
            width: 50px;
            background-color: antiquewhite;
            border: 1px solid black;
            font-size: 30px;
        }
        .box2{
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="box">
        <div class="box2">
            <p id="hour"></p>
            <p class="maohao">:</p>
            <p id="munite"></p>
            <p class="maohao">:</p>
            <p id="second"></p>
        </div>
    </div>
</body>
<script>
    function sjc(){
        var time1 = new Date("2020-8-9 12:00:00").getTime()
        var time2 = new Date().getTime()
        var cha = time1 - time2
        return cha
    }
    function hour0(){
        var cha = sjc()
        var hour0 = Math.floor(cha/(1000*60*60))
        return hour0
    }
    function munite0(){
        var cha = sjc()
        var munite0 = Math.floor((cha/(1000*60))%60)
        return munite0
    }
    function second0(){
        var cha = sjc()
        var second0 = Math.floor((cha/1000)%60)
        return second0
    }
    function sxian(){
        var hour = document.getElementById("hour")
        hour.innerHTML = hour0()
        var munite = document.getElementById("munite")
        munite.innerHTML = munite0()
        var second = document.getElementById("second")
        second.innerHTML = second0()
    }
    sxian()
    setInterval(sxian,1000)
</script>
</html>
```

##### DOM增删改查

4.DOM增删改查
	DOM ： document object model ,主要操作的就是页面结构，DOM把页面当成一个结构树(tree)，结构树是由节点(标签)组成的

DOM树的根： document->document type + html 
									                                              |
							                     head                       +                                   body
							                         |			                                                      |
					              title+meta+link+script                                      div+div+div+div
操作DOM就是对DOM树中的节点(标签)进行操作

已经学过：操作单个DOM的 内容的获取和设置 ， 属性的获取和设置  ，样式的获取和设置
内容的获取和设置 ：
	获取：
	1.双标签(div) ： innerHTML
	2.input 	: value
	设置：
	1.双标签 :innerHTML = 新值
	2.input ：value = 新值
属性的获取和设置：
	获取：
		getAttribute('属性名称')
	设置：
		setAttribute('属性名称','新值');
样式的获取和设置：
	获取：
		行内：元素.style.属性名
		内部、外部样式： window.getComputedStyle('元素')['属性名']
	设置：
		元素.style.属性名 =新值

**DOM节点的增删改查**
	**增加：向DOM中添加新的标签**
		第一步：创建新标签
			1.标签节点：document.createElement('标签名')
			2.内容节点：document.createTextNode('内容')
		第二步：添加到页面
			1.添加到指定父级的最后： 父级.appendChild('新标签')
			2.添加到指定父级的指定位置: 父级.insertBefore('新标签','要插入到这个标签前')

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<div id="box">
		<span id="old">原来的标签</span>
	</div>
</body>
<script>
	//创建新标签
	var objp = document.createElement('p')
	//创建文本节点
	var objp_con = document.createTextNode('新创建的p标签中的内容')
	//把文本节点放入标签
	objp.appendChild(objp_con)
	//添加到页面
	var box = document.getElementById('box')
	// box.appendChild(objp)
	//添加到指定位置
	var old = document.getElementById('old')
	box.insertBefore(objp,old)
	//创建一个标签
	var oDiv = document.createElement('div')
	//设置id属性和class属性
	oDiv.id = 'container'
	oDiv.className = 'slide'
	//设置样式
	oDiv.style.height='400px'
	oDiv.style.width ='300px'
	oDiv.style.border = '1px solid red'
	//设置内容
	oDiv.innerHTML = '创建的div内容'
	box.appendChild(oDiv)
</script>
</html>
```

​		新创建的标签是一个完整的DOM，所以可以给新创建的标签进行属性和样式、内容操作
​		新创建标签操作：
​			内容操作：双标签的.innerHTML
​					 input.value
​			属性操作：标签.属性名=属性值
​			样式操作：标签.style.样式名称 = 值

​	增加的另外一种方案：
​		字符串方法：具体某个元素中要添加的内容，使用innerHTML形式，添加指定字符串。
​		字符串方法和创建标签法的区别：
​			1.创建标签法创建的是DOM元素 ;字符串方式创建的是普通字符串,不具备DOM操作功能
​			2.创建标签可以决定标签添加到那个位置，不删除原来的元素; 字符串方式把父级标签中所有元素删除，然后再添加字符串

**删除:**
	从DOM中删除某一个节点
	元素.removeChild('要删除的节点')

```
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
</head>
<body>
    <div id="box">
        <span>01</span>
        <span>02</span>
        <span id="three">03</span>
    </div>
</body>
<script>
    var box = document.getElementById("box")
    var three = document.getElementById("three")
    box.removeChild(three)
</script>
</html>
```

**修改(替换):**
	把原来的节点换成新节点
	父元素.replaceChild('新节点','旧节点')

```
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
</head>
<body>
    <div id="box">
        <span>01</span>
        <span>02</span>
        <span id="three">03</span>
    </div>
</body>
<script>
    var box = document.getElementById("box")
    var three = document.getElementById("three")
    //创建一个p标签
    var op = document.createElement("p")
    op.innerHTML = "新标签"
    box.replaceChild(op,three)
</script>
</html>
```

**查询：**
	前面学过id选择器、class选择器、标签选择器：他们的作用是查找到某一个或某一类标签元素
	今天学习几个快速查询节点的方式：
		查询第一个子节点：父元素.firstChild
		查询最后一个子节点：父元素.lastChild
		查询当前元素的下一个节点：元素.nextSibling
		查询当前元素的上一个节点：元素.previousSibling
		查询当前元素的父节点：元素.parentNode
		查询所有子级节点：父元素.children
		查询当前元素是否有子节点：元素.hasChildNodes()

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<div>哥哥</div>
	<div id="box">
		<ul id="list">
			<li>第一个Li</li>
			<li>第二个Li</li>
			<li>第三个Li</li>
		</ul>
		<p>普通文本</p>
	</div>
	<div id="borther">弟弟</div>
</body>
<script>
	var box = document.getElementById('box')
	var borther = document.getElementById('borther')
	//查询第一个子节点
	console.log(box.firstChild)
	//查询最后一个子节点
	console.log(box.lastChild)
	//查询上一个兄弟节点
	console.log(box.previousSibling)
	//查询下一个兄弟节点
	console.log(box.nextSibling)
	//查询所有子节点
	console.log(box.children)
	//查询父节点
	console.log(box.parentNode)
	//判断是否有子节点
	console.log(box.hasChildNodes())
	console.log(borther.hasChildNodes())
</script>
</html>
```

### js事件响应

##### 事件类型

1.事件类型
	**1.鼠标事件：**
		单击事件：click

```
<script>
    var btn = document.getElementById("btn")
    btn.onclick = function(){
        console.log("这是点击事件")
    }
</script>
```

​		双击事件：dblclick

```
<script>
    var btn = document.getElementById("btn")
    btn.ondblclick = function(){
        console.log("这是双击事件")
    }
</script>
```

​		鼠标经过事件： mouseover		会事件冒泡

```
<script>
    var btn = document.getElementById("btn")
    btn.onmouseover = function(){
        console.log("这是xx事件")
    }
</script>
```

​		鼠标离开事件： mouseout (会事件冒泡) / mouseleave (不会事件冒泡)

```
<script>
    var btn = document.getElementById("btn")
    btn.onmouseout = function(){
        console.log("这是xx事件")
    }
</script>
```

​		鼠标进入事件： mouseenter		不会事件冒泡

```
<script>
    var btn = document.getElementById("btn")
    btn.onmouseenter = function(){
        console.log("这是xx事件")
    }
</script>
```

​		hover事件：有两个过程，鼠标进入时执行鼠标进入事件，鼠标离开时执行鼠标离开事件

```

```

​		鼠标移动事件： mousemove 
​		鼠标按下事件： mousedown
​		鼠标抬起事件： mouseup

鼠标事件练习

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		#list{
			border: 1px solid red;
		}
		.more{
			display: none;
		}
		.cha_more{
			border: 1px solid #000;
		}
	</style>
</head>
<body>
	<div>
		<ul id="list">
			<li>
				<span>Java开发工程师（中、高）</span>
				<div class="cha_more">更多
				<div class="more">
					<p>技能要求：javaee、javase</p>
					<p>工作经验：5年</p>
					<p>工作地址：北京</p>
					<p>薪资：30K</p>
				</div></div>
			</li>
			<li>
				<span>Java开发工程师（中、高）</span>
				<div class="cha_more">更多
					<div class="more">
						<p>技能要求：javaee、javase</p>
						<p>工作经验：5年</p>
						<p>工作地址：北京</p>
						<p>薪资：30K</p>
					</div>
				</div>
			</li>
			<li>
				<span>Java开发工程师（中、高）</span>
				<div class="cha_more">更多
				<div class="more">
					<p>技能要求：javaee、javase</p>
					<p>工作经验：5年</p>
					<p>工作地址：北京</p>
					<p>薪资：30K</p>
				</div></div>
			</li>
		</ul>
	</div>
</body>
<script>
	var cha_more = document.getElementsByClassName('cha_more')
	var more = document.getElementsByClassName('more')
	var list = document.getElementById('list')
	
	for(let i=0; i<cha_more.length ; i++){
		cha_more[i].onmouseenter = function(){
			more[i].style.display = 'block'
		}

		cha_more[i].onmouseleave = function(){
			more[i].style.display = 'none'
		}
	}
</script>
</html>
```

**2.键盘事件：**
	键盘按下事件： keydown
	键盘抬起事件： keyup
	键盘长按事件： keypress

```
<script>
   document.onkeydown = function(){
       console.log("鼠标按下")
   }
   document.onkeyup = function(){
       console.log("鼠标抬起")
   }
   document.onkeypress = function(){
       console.log("鼠标长按")
   }
</script>
```

​	可以获取按下的案件的keyCode值
​	 回车键 13
​	 空格键 32

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<input type="text" id="search_con">
	<button id="btn">百度一下</button>
</body>
<script>
	var btn = document.getElementById('btn')
	var search_con = document.getElementById('search_con')
	btn.onclick = function(){
		var search_con_val = search_con.value
		console.log('您想要搜索的是：'+search_con_val)
	}
	//定义键盘事件,点击回车键时实现搜索功能
	search_con.onkeydown = function(e){
		var search_con_val = search_con.value
		if(e.keyCode == 13){
			console.log('这是通过回车键触发的,您想要搜索的是：'+ search_con_val)
		}
	}
</script>
</html>
```

**3.表单事件**
	获取焦点事件： focus
		元素.onfocus = function(){}	元素获取到焦点后执行的功能
		元素.focus()  让元素获取焦点

```
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
</head>
<body>
    <input type="text" id="search_con">
    <button id="btn">点我</button>
</body>
<script>
	//当页面加载完毕后执行
    window.onload = function(){   
        var search_con = document.getElementById("search_con")
        search_con.focus()
    }
</script>
</html>
```

​	失去焦点事件： blur

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<input type="text" id="search_con">
	<span class="err"></span>
	<button>点我</button>
</body>
<script>
	var search_con = document.getElementById('search_con')
	var err = document.getElementsByClassName('err')[0]
	window.onload = function(){

	}
	
	var arr = [
		{
			uname:'小明'
		},{
			uname:'小红'
		},{
			uname:'小白'
		}
	]
	// 鼠标失去焦点事件
	search_con.onblur  = function(){
		var search_con_val = search_con.value
		var srt = ''
		for(var i=0; i<arr.length ; i++){
			if(arr[i]['uname'] == search_con_val){
				str = '用户名已重复，不能使用'
				err.innerHTML = str
				break;
			}
		}
	}
</script>
</html>
```

​	提交事件： submit

**4.事件冒泡**
	事件冒泡：从当前触发元素开始，向上级触发具有相同事件类型的事件，直到document，的过程

##### 绑定事件的方法

2.绑定事件的方法
	1.DOM0级
		绑定事件：元素.on+事件类型 = function(){}
		取消事件：元素.on+事件类型 = null

​	DOM0级给同一个元素绑定相同的事件，只会执行后面定义事件的功能函数
2.DOM2级
​	绑定事件： 元素.addEventListener('事件类型',fn)
​	取消事件： 元素.removeEventListener('事件类型',fn)

​	DOM2级绑定事件：同一个元素可以绑定多个相同的事件，多个事件的功能函数都会执行
​	取消绑定时需要指定取消的功能函数，要求函数是具名函数

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<div id="box">点击我</div>
</body>
<script>
	// DOM0级
	var box = document.getElementById('box')
	box.onclick = function(){
		console.log('点击事件')
	}
	// 取消绑定的DOM0级点击事件
	box.onclick = null


	// DOM2级绑定事件
	box.addEventListener('click',function(){
		console.log('点击事件，DOM2级的')
	})
	box.addEventListener('click',otherclick)

	function otherclick(){
		console.log('DOM2级，另一个点击事件')
	}


	//取消DOM2级事件
	box.removeEventListener('click',otherclick)
</script>
</html>
```

##### 事件对象

3.事件对象
	事件在被触发时，都会生成一个事件对象，这个事件对象中保存所有和当前事件有关的信息
	event 事件对象 
	事件对象经常在事件触发函数中当形参传递到函数内部

```
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
</head>
<body>
    <div id="hhh">点我</div>
</body>
<script>
    var haha = document.getElementById("hhh")
    haha.addEventListener("click",function(event){
        console.log(event)
    })
</script>
</html>
```

比较常用的几个信息：
	target:触发元素
	type: 什么类型的触发
	keyCode: 键盘事件下的按键keyCode值
	x,y坐标信息：
		offsetX , offsetY : 相对于当前容器左上角的x,y坐标
		clientX , clientY : 相对于可视窗口左上角的x,y坐标

拖拽案例练习

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		#box{
			position: absolute;
			top:100px;
			left: 50px;
			width: 300px;
			height: 260px;
			background-color: skyblue;
			border: 1px solid #000;
		}
	</style>
</head>
<body>
	<div id="box"></div>
</body>
<script>
	var box = document.getElementById('box')

	box.onmousedown = function(e){
		var cliX = e.clientX - box.offsetLeft
		var cliY = e.clientY - box.offsetTop
		document.onmousemove = function(e){
			var newcliX = e.clientX
			var newcliY = e.clientY

			//计算鼠标移动差值
			var chaX = newcliX - cliX
			var chaY = newcliY - cliY

			box.style.top = chaY + 'px'
			box.style.left = chaX + 'px'
		}
	}
	document.onmouseup = function(){
		document.onmousemove = null
	}
</script>
</html>
```

##### 事件委托

1.事件委托
	事件委托是把事件定义在它父级或祖先级元素上，真正触发这个事件执行是我们原来想定义事件的元素。

使用事件委托的场景：页面中通过js新创建的元素，可以使用事件委托绑定事件

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<div id='box'>
		box
	</div>
</body>
<script>
	var box = document.getElementById('box')
	var str = '<p class="more">查看更多</p><span class="con">span内容</span>'
	//给class为 more 的 p标签添加事件-> 可以使用事件委托，先把事件添加到box上
	box.onclick = function(e){
		if(e.target.className == 'more'){
			console.log('查看更多')
		}
	}
	box.innerHTML = str
</script>
</html>
```

##### 滚动事件

2.滚动事件 scroll
	1.作用整个页面
		当页面发生上下滚动时，浏览器会触发一个滚动事件,发生滚动事件时可以获取到滚动高度和距离左边的滚动距离
		  滚动高度： scrollTop
		  滚动距左边距离： scrollLeft
		  这两个属性是可以读取可以设置
		  window.onscroll = function(){
		  	//获取页面滚动高度（两种方式）
		  	document.documentElement.scrollTop
		  	document.body.scrollTop

​	  

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		body{
			height: 2000px;
			width: 4000px;
		}
		#box{
			width:200px;
			height: 200px;
			border: 1px solid #000;
			overflow:scroll;
		}
		#toTop{
			position: fixed;
			bottom: 30px;
			right: 50px;
		}
	</style>
</head>
<body>
	body

	<div id='box' >滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素滚动元素</div>
	<button id="toTop">返回顶部</button>
</body>
<script>
	// 获取页面的滚动距离
	window.onscroll = function(){
		//读取高度和距左边距离
		// var sTop = document.documentElement.scrollTop || document.body.scrollTop
		// var sLeft = document.documentElement.scrollLeft || document.body.scrollLeft
		// console.log('滚动高度：'+ sTop)
		// console.log('滚动距左边距离：'+ sLeft)
		
		// 设置高度和距左边距离
		// document.documentElement.scrollTop = 300
		// document.body.scrollTop = 300
	}


	var box = document.getElementById('box')
	box.onscroll = function(){
		console.log(box.scrollTop)
	}

	var toTop = document.getElementById('toTop')
	toTop.onclick = function(){
		var nowsTop = document.documentElement.scrollTop
		var timer = setInterval(function(){
			nowsTop -= 20
			if(nowsTop<=0){
				nowsTop = 0
				clearInterval(timer)
			}
			document.documentElement.scrollTop = nowsTop
		},10)
	}
</script>
</html>
```

2.作用于某一个具体的元素
	这个元素必须设置属性 overflow:scroll，才能出现滚动条
	获取滚动距离:
		元素.scrollTop
		元素.scrollLeft

### jquery库

##### jQuery的选择器

jquery
	jQuery是js的一个类库，主要封装的是js中DOM操作部分，使用和原生js一样。
	1.需要先引入页面才能使用

	<script src='jquery.js'></script>	

2.基本用法：
	起点是从获取DOM元素开始
	 获取方法：$()
	 	小括号中写：	  

  				  id选择器 			$("#id名")
	 			   class 选择器 	  $(".class名")
	 			   元素选择 		    $("标签名")
	 			   子级选择器 		$("父级>子级")
	 			   后代选择器 		$("父级 子级")

​	jquery封装的选择器：
​		基本：
​			:even 		偶数下标，奇数行
​			:odd 		奇数下标，偶数行
​			:lt(index)  小于多少
​			:gt(index) 	大于多少
​			:eq(index) 	选择兄弟排名中的第几个

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<div id="box">
		<ul class="list">
			<li><a href=""><span>1</span></a></li>
			<li><a href=""><span>2</span></a></li>
			<li><a href=""><span>3</span></a></li>
			<li><a href=""><span>4</span></a></li>
		</ul>
		<ul class="list">
			<li><a href=""><span>1</span></a></li>
			<li><a href=""><span>2</span></a></li>
			<li><a href=""><span>3</span></a></li>
			<li><a href=""><span>4</span></a></li>
		</ul>
	</div>
</body>
<script src="libs/jquery-1.12.3.min.js"></script>
<script>
	// id选择器
	var box = $("#box")
	// console.log(box)
	// class选择器
	var lists = $(".list")
	// console.log(lists)	
	//标签选取
	var allLi = $("li:gt(2)")
	// console.log(allLi)
	// 子级选择器
	var firstListLi = $(".list:eq(0)>li:eq(3)")
	console.log(firstListLi)
	
	// 后代选择器
	var allSpan = $(".list:eq(1) span")
	// console.log(allSpan)
</script>
</html>
```

​		表单：
​			:text 		     找所有type='text' 的input标签	
​			:radio 		   type='radio' 的单选按钮
​			:checkbox 	type='chechbox' 的多选按钮
​			:checked 	  被选中的

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<input type="radio" name="sex" value="1"> 男
	<input type="radio" name="sex" value="2"> 女
	<button id='btn'>提交</button>
</body>
<script src="libs/jquery-1.12.3.min.js"></script>
<script>
	$("#btn").click(function(){
		console.log($(":radio:checked").val())
	})
</script>
</html>
```

##### jquery操作元素

3.操作元素的内容、属性、样式
	操作内容：
	  获取：
		1.双标签(div)内容 : html()
		2.input ： val()
	  设置：
	  	1.双标签 : html('新内容')
	  	2.input ： val('新内容')

​	操作属性：
​		获取： attr('属性名')
​		设置： attr('属性名','新的值')

​	样式操作：
​		获取：css('样式名')
​		设置：css('样式名','新的值')
​			  css({
​			  	"样式名1"："新的值",
​			  	"样式名2"："新的值"
​			  })

  额外封装的:
  	css类操作：
  		addClass()  :添加类名
  		removeClass() : 删除类名
  		toggleClass() : 切换类名
  	尺寸操作：
  		height() 	：高度
  		width()		:宽度
  		scrollTop() :滚动高度
  		scrollLeft() :滚动距左边距离

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<div>div的内容</div>
	<input type="text" value="input标签的值">
	<button>点我</button>
</body>
<script src="libs/jquery-1.12.3.min.js"></script>
<script>
	//获取内容
	console.log($("div:eq(0)").html())
	console.log($("input:eq(0)").val())
	//设置内容
	$('div:eq(0)').html('新的值')
	$("input:eq(0)").val('input新的值')
	//设置属性
	$("div:eq(0)").attr('id','box').attr('class','content')
	//获取属性
	console.log($("div:eq(0)").attr('id'))
	// 获取样式
	console.log($("div:eq(0)").css('fontSize'))
	// 设置样式
	$("div:eq(0)").css('color','red').css('fontSize','30px')
	$("div:eq(0)").css({
		'border':'1px solid #000',
		"background-color":'skyblue',
		"margin":"10px auto",
		"height":"400px",
		"width":300,
		"padding":"20px"
	})
	// 添加类名
	$("div:eq(0)").addClass('box2')

	//移除类名
	$("div:eq(0)").removeClass('content')

	//切换类名
	$("button").click(function(){
		$("div:eq(0)").toggleClass('box4')
	})
</script>
</html>
```

##### 绑定事件

4.绑定事件0
	$().事件名(function(){ 功能 })

​	事件名：鼠标事件、键盘事件、表单事件

​	事件委托： $().on('事件名','target',function(){ 功能 })

​	额外：
​	   one() ：绑定的事件只会执行一次

5.DOM的增删改查
	增：
		创建元素：$('标签')
			如：$("<li><div><p class='title'>"+news.title+"</p><img src="+news.url+"></div></li>")
		添加到页面:
			尾部添加：父级.append(子级)

 						 子级.appendTo(父级)
    			指定位置添加：父级.prepend(子级)
    					 子级.prependTo(父级)
    	删除：
    		empty() : 元素.empty() 删除指定元素中所有子级元素
    		remove() ： 元素.remove() 指定的元素被删除

​	改：
​		replaceWith()
​		replaceAll()

​	查：
​		父级关系： parent()
​		祖先级关系： parents(val)
​		子级关系： children()
​		后代关系： find(val) 这个里面必须有参数  
​		兄弟关系：
​			上一个兄弟： prev()
​			上面所有的兄弟：prevall()
​			下一个兄弟：next()
​			下面所有的兄弟：nextall()

​			所有兄弟：siblings()

​	   筛选：
​	   	eq()	兄弟中的第几个
​	   	first()	第一个
​	   	last()	最后一个
​	   	is() 	验证作用

   this 和 $(this)
   this是原生js中的关键字
   $(this)是jQuery的关键字
   他们的作用是一样的，作用时指向事件触发者

### jQuery动画特效

动画
1.显示隐藏
	show([speed,easing,fn])  speed:毫秒单位的时间值
	hide([speed,easing,fn]) 
 用法：元素.show() /元素.hide()

2.滑动
	slideDown([speed,easing,fn])  向下滑动，显示
	slideUp()    向上滑动，隐藏
	slideToggle() 滑动切换

3.stop()方法
	停止所有在指定元素上正在运行的动画
	stop(clearQueue,gotoEnd)
	这个两个参数可选值是布尔值
	stop(false,false) : 不清空动画队列，不立即跳到动画最后
	stop(true,true)   : 清空动画队列 , 立即跳到动画最后
	stop(false,true)  : 不清空动画队列,立即跳到动画最后
	stop(true,false)  : 清空动画队列 ,不立即跳到动画最后

4.淡入淡出
	fadeIn()    : 淡入
	fadeOut()   : 淡出
	fadeToggle(): 切换
	fadeTo(opacity)    : 淡出到指定透明度  opacity [0,1] 影响全局透明度

	淡入淡出轮播图(使用绝对定位法)

5.index()方法

6.animate()
	高级动画，animate(options,[speed,easing,fn])
	options:可以动画的属性有哪些
		不能动画：背景
		几乎带px单位的都可以动画
		接收参数时是字典形式的
		animate({
			width:40,
			height:100
		})

7.delay(speed)
	动画延时多长时间后执行

### _Ajax异步网络请求

请求数据(前后台数据交互)

1.form表单
	<form action='url' method='get/post'>
		<input type='text' />
		<input type='password' />
		<input type='radio' />
		<input type='checkbox' />
		<textarea></textarea>
		<input type='submit' />
	</form>
	点击提交(type='submit')时，form表单会自动把name属性值作为键名，value属性值作为键值，组成键值对形式，然后form表单会按指定的method方式吧数据发送到指定的url路径去

	method提交方式：
		get:
			数据会显示在地址栏，显示的形式是url?数据
			数据是键值对形式存在，多个键值对之间使用&符号连接
			? 号最多出现一次，& 可以出现多次
		post:
			数据不在地址栏中显示，可以在network监听工具中监听,在请求头中
			数据中不会出现? 和 & 符号
			正常情况下是看不到这个数据的

2.ajax
	jquery中的ajax
	$.ajax({
		url:'地址',
		type:'get/post',
		data:{},
		dataType:'json/jsonp',
		success:function(res){
			//请求成功，接收返回值
		}
	})

	注意：ajax不能跨域请求
	两个网址： 协议 、 主域名 、 端口号 完全相同时，这是两个网址是同源的
			如果 协议、主域名、端口号 有任意区别，这两个网址就是跨域的
	
	解决跨域：
		1.jsonp : 在$.ajax({dataType:'jsonp'})，需要后台支持jsonp形式
		2.cors : 需要后台配合
		3.后台设置允许所有或指定网址能直接访问


	简写形式：
		$.get(url,data,function(res){
	
		})
	
		$.post(url,data,function(res){
	
		})

2.把请求的数据添加到页面
	创建标签，把数据填充到标签中，把标签添加到页面