# 一.pytest测试框架

## 1.概念

pytest是一个非常成熟的全功能的Python测试框架，主要有以下几个特点：

- 简单灵活，容易上手
- 支持参数化
- 能够支持简单的单元测试和复杂的功能测试，还可以用来做selenium/appnium等自动化测试、接口自动化测试（pytest+requests）
- pytest具有很多第三方插件，并且可以自定义扩展，比较好用的如pytest-selenium（集成selenium）、pytest-html（完美html测试报告生成）、pytest-rerunfailures（失败case重复执行）、pytest-xdist（多CPU分发）等
- 测试用例的skip和xfail处理
- 可以很好的和jenkins集成
- report框架----allure 也支持了pytest

## 2.安装

### (1)安装pytest

```python
pip install pytest #安装
pytest --version #验证
```

### (2)安装pytest的插件

```bash
pip install pytest-sugar #对运行的过程进行美化
pip install pytest-rerunfailures #重新运行失败的测试用例
pip install pytest-xdist #实现并发执行测试用例
pip install pytest-assume #当出现失败的测试用例后，继续执行接下来的测试用例
pip install pytest-html #生成测试报告
```

## 3.pytest框架中的命令约束

所有的单测文件名都需要满足test_*.py格式或*_test.py格式。
在单测文件中，测试类以Test开头，并且不能带有 **init** 方法(注意：定义class时，需要以T开头，不然pytest是不会去运行该class的)
在单测类中，可以包含一个或多个test_开头的函数。
此时，在执行pytest命令时，会自动从当前目录及子目录中寻找符合上述约束的测试函数来执行。

## 4.用法详解

### （1）创建测试用例方法（函数）

格式：以test开头

```python
import pytest #导入pytest

def test_a():
    """以test开头的测试函数"""
    print("----->test_a")
    assert 1 #断言成功
    
def test_b():
    print('----->test_b')
    assert 0 #断言失败
```

### （2）运行pytest中的测试用例

#### 方法一：终端运行

格式：pytest + 被测文件路径

```shell
pytest test_abc.py
```

![image-20201027222835482](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201027222835482.png)

#### 方法二.在python脚本中运行

pytest.main(["参数1",“参数2”,"用例模块路径"])-------可以传多个参数，但是用例模块路径必须放在最后传递

```python
if __name__ == "__main__":
    pytest.main(["-s",'-v',"test_abc.py"])
```

参数和终端运行时一致

#### 特殊执行场景

1.测试用例执行失败后，重试3次

```python
pip install pytest-rerunfailures #安装相关的扩展包pytest-rerunfailures
pytest -v --reruns 3 test_abc.py #-v表示打印详细日志；--reruns 3表示失败后重试3次
```

结果：

![image-20201027224959910](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201027224959910.png)

2.测试用例执行失败后，重试3次，每次间隔时间5秒

```python
pytest -v --reruns 3 --reruns-delay 5 test_abc.py #--reruns-delay 5表示重试时间隔5秒
```

3.一条测试用例中，往往有多个断言，当一个断言失败时。后面的断言也就不再执行了。那么如何让断言失败后，继续往下执行呢

```
第一步：pip install pytest-assume #安装相关扩展包pytest-assume
第二步：在测试用例方法中，使用pytest.assume()来添加断言
```

实例：

```python
#测试用例
def test_d():
    pytest.assume('e' in 'et')
    pytest.assume(1==2)
    print('666')
    pytest.assume(True)
```

```
pytest -v -s test_abc.py::test_d #执行测试用例
```

结果：

![image-20201027231133765](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201027231133765.png)

## 5.pytest框架的fixture

### 自带的fixture（setup和teardown）



![image-20201027232513577](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201027232513577.png)

-  function 定义在类外， 类外的每一个用例都执行
-  class     定义在类中，每个类执行
-  module   定义在类外，每个模块执行
-  session   定义在类外 每个session只运行一次，在自动化测试时，登录步骤可以使用该session
-  method 定义在类中，类中的每个用例都执行
-  setup/teardown  定义在类外，则类外的每个用例都执行；定义在类中，则类中的每个用例都执行

例子：

```python
import pytest #导入pytest

def setup_module():
    """在整个模块用例测试开始前执行"""
    print("----->setup_module")

def teardown_module():
    """在整个模块用例测试结束后执行"""
    print("----->teardown_module")

def setup_function():
    """在每一个外部的用例测试开始前执行"""
    print("----->setup_function")

def teardown_function():
    """在每一个外部的用例测试结束后执行"""
    print("----->teardown_function")

def test_a():
    """以test开头的测试函数"""
    print("----->test_a")
    assert 1 #断言成功

def test_b():
    print('----->test_b')
    assert 'e' in 'et'

class Test_hh:
    def setup_class(self):
        """在整个类中用例测试开始前执行"""
        print("----->setup_class")

    def teardown_class(self):
        """在整个类中用例测试结束后执行"""
        print("----->teardown_class")

    def setup_method(self):
        """在每一个类中的用例测试开始前执行"""
        print("----->setup_method")

    def teardown_method(self):
        """在每一个类中的用例测试结束后执行"""
        print("----->teardown_method")

    def test_c(self):
        print('----->test_c')
        assert 'e' in 'et'

    def test_d(self):
        print('----->test_d')
        assert 'e' in 'et'


if __name__ == "__main__":
    pytest.main(["-s",'-v',"test_abc.py"])
```

### 自定义fixture

场景：

![image-20201028195820327](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201028195820327.png)

#### **实现自定义setup**

```python
# filename：test_login.py
import pytest #导入pytest

@pytest.fixture()
def login():
    """
    给对应的方法添加装饰器@pytest.fixture()，
    然后在需要调用的测试用例方法中传入该方法，即可。
    """
    print("登录方法")

def test_a(login):
    print('需要登录的测试用例')
    assert 1

def test_b():
    print('不需要登录的测试用例')
    assert 1

def test_c(login):
    print('需要登录的测试用例')
    assert 1

if __name__ == "__main__":
    pytest.main(['-v','-s','test_login.py'])
```

#### **实现自定义teardown**

在前面我们定义的fixture方法，只能实现在每个用例开始执行前执行（setup），那么怎么实现每个用例执行完成后执行呢（teardown）

方法：在定义的fixture方法中，可以使用yield进行区分，在yield前面的操作是setup，在yield后面的操作是teardown

```
import pytest #导入pytest

@pytest.fixture()
def login():
    """
    给对应的方法添加装饰器@pytest.fixture()，
    然后在需要调用的测试用例方法中传入该方法，即可。
    """
    print("登录方法") #setup
    yield

    print('退出登录方法') #teardown


def test_a(login):
    print('需要登录的测试用例')
    assert 1

def test_b():
    print('不需要登录的测试用例')
    assert 1

def test_c(login):
    print('需要登录的测试用例')
    assert 1

if __name__ == "__main__":
    pytest.main(['-v','-s','test_login.py'])
```

#### 自定义fixture的作用域

之前使用@pytest.fixture(scope='module')来定义框架，scope的参数有以下几种

-  function  每一个用例都执行，不论是否在类中。自定义的方法作为参数传递给用例方法
-  class     每个类执行
-  module   每个模块执行(函数形式的用例)
-  session   每个session只运行一次，在自动化测试时，登录步骤可以使用该session

```python
import pytest #导入pytest

@pytest.fixture(scope='class')
def login():
    """
    给对应的方法添加装饰器@pytest.fixture()，
    然后在需要调用的测试用例方法中传入该方法，即可。
    """
    print("登录方法") #setup
    yield

    print('退出登录方法') #teardown

class Test_login():

    def test_a(self,login):
        print('test_a')
        assert 1

    def test_b(self,login):
        print('test_b')
        assert 1

    def test_c(self,login):
        print('test_c')
        assert 1

if __name__ == "__main__":
    pytest.main(['-v','-s','test_login.py'])
```

#### 给测试用例传递数据

我们可以使用@pytest.mark.parametrize()来给用例传递数据

格式：@pytest.mark.parametrize("测试用例中的变量",[(数据1,数据2,数据3])---------数据和变量的位置要对应

​	ids可以给每一组数据对应的用例取一个别名，如果不设置ids默认以test_num1,test_num2,test_num3来给用例命名

```python
import pytest

@pytest.mark.parametrize("a,b",[(1,1),(2,2),(3,5)]，ids=['one','two','three'])
def test_num(a,b):
    print("test_num")
    assert a == b

if __name__ == "__main__":
    pytest.main() #虽然只有一条测试用例，但因为有3组数据。所有执行了3条测试用例
```

还可以参数组合传递

```python
import pytest

@pytest.mark.parametrize("a",[(1),(2),(3)])
@pytest.mark.parametrize("b",[(1),(2)])                   #---------形成了6组数据
def test_num(a,b):
    print("test_num")
    assert a == b

if __name__ == "__main__":
    pytest.main() #虽然只有一条测试用例，但因为有6组数据。所有执行了6条测试用例
```

#### 给测试用例传递方法和数据

```python
import pytest

@pytest.fixture()
def sum(a,b):
    """求和方法"""
    return a + b


@pytest.mark.parametrize("sum",[(1,2),(2,3)],indirect=True)
def test_sum(sum):
    print("test_sum")
    c = sum
    assert c == 5

if __name__ == "__main__":
    pytest.main()
```

#### 跳过某条测试用例不执行

```python
@pytest.mark.skip(1 == 1,reason='不想执行呢')
    def test_c(self,login):
        print('test_c')
        assert 1
```

#### 某条测试用例不执行，直接标注为Xpass

```python
@pytest.mark.xfail()
    def test_c(self,login):
        print('test_c')
        assert 1
```

#### 将用例标记为某个模块

格式：

在用例前加上@pytest.mark.模块名------将该用例标记到对应的模块下

执行用例时，在最后加上‘-m=模块名’----------执行指定模块下的测试用例

```python
import pytest #导入pytest

@pytest.fixture(scope='class')
def login():
    """
    给对应的方法添加装饰器@pytest.fixture()，
    然后在需要调用的测试用例方法中传入该方法，即可。
    """
    print("登录方法") #setup
    yield

    print('退出登录方法') #teardown

class Test_login():

    @pytest.mark.module1
    def test_a(self,login):
        print('test_a')
        assert 1

    @pytest.mark.module1
    def test_b(self,login):
        print('test_b')
        assert 1

    @pytest.mark.module2
    def test_c(self,login):
        print('test_c')
        assert 1

    @pytest.mark.module2
    def test_d(self,login):
        print("test_d")
        assert 1

if __name__ == "__main__":
    pytest.main(['-v','-s','test_login.py','-m=module1'])
```



### 公共模块conftest

在实际工作中，对于自定义的fixture方法，往往会集中放在一个地方。

pytest给我们提供了一种方法：将公共的fixture方法放置在conftest.py文件中，这样我们在执行测试用例时，会自动去该文件下找对应的方法

```python
# filename：conftest.py
import pytest

@pytest.fixture()
def login():
    """
    给对应的方法添加装饰器@pytest.fixture()，
    然后在需要调用的测试用例方法中传入该方法，即可。
    """
    print("登录方法")
```

```python
# filename：test_login.py
import pytest #导入pytest

def test_a(login):
    print('需要登录的测试用例')
    assert 1

def test_b():
    print('不需要登录的测试用例')
    assert 1

def test_c(login):
    print('需要登录的测试用例')
    assert 1

if __name__ == "__main__":
    pytest.main(['-v','-s','test_login.py'])
```

在测试用例文件中，不需要导入conftest

![image-20201028201930325](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201028201930325.png)

## 6.多线程执行测试用例

（1）安装

```
pip install pytest-xdist
```

（2）使用

```
pytest test_login.py -n 3 #'-n 3'表示使用3个线程来执行
```

## 7.HTML报告

（1）安装

```
pip install pytest-html
```

（2）使用

```
pytest test_login.py --html=report.html
```

# 二.参数化用例

## 1.pytest数据参数化（使用@pytest.mark.parametrize）

![image-20201029214427008](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201029214427008.png)

举例：

```python
# filename:test_data.py
import pytest

# 方式一：使用string传参
class TestData1():
    @pytest.mark.parametrize("a,b",[(10,20),(30,40),(50,60)])
    def test_data1(self,a,b):
        print(a + b)

# 方式二：使用元组传参
class TestData2():
    @pytest.mark.parametrize(("a","b"),[(10,20),(30,40),(50,60)])
    def test_data2(self,a,b):
        print(a + b)

# 方式三：使用列表传参
class TestData3():
    @pytest.mark.parametrize(["a","b"],[(10,20),(30,40),(50,60)])
    def test_data3(self,a,b):
        print(a + b)

if __name__ == "__main__":
    pytest.main(['-v','-s','test_data.py'])
```

这样我们只写了3条测试方法，但执行了9条测试用例。所以使用数据参数化可以大大减小代码量

## 2.使用yaml实现数据参数化

方法：

1.将数据写在yaml文件中

2.在测试用例代码中使用yaml

例子：

```yaml
# filename:data.yaml
-
  - 10
  - 20
-
  - 30
  - 40
-
  - 50
  - 60
```

```python
# filename:test_data.py
import pytest
import yaml

# 方式一：使用string传参
class TestData1():
    @pytest.mark.parametrize("a,b",yaml.safe_load(open('./data.yaml')))
    def test_data1(self,a,b):
        print(a + b)

# 方式二：使用元组传参
class TestData2():
    @pytest.mark.parametrize(("a","b"),yaml.safe_load(open('./data.yaml')))
    def test_data2(self,a,b):
        print(a + b)

# 方式三：使用列表传参
class TestData3():
    @pytest.mark.parametrize(["a","b"],yaml.safe_load(open('./data.yaml')))
    def test_data3(self,a,b):
        print(a + b)

if __name__ == "__main__":
    pytest.main(['-v','-s','test_data.py'])
```

# 三.数据驱动

![image-20201029221847453](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201029221847453.png)

![image-20201029222044568](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201029222044568.png)

# 四.测试报告的美化与定制

## 1.allure介绍

![image-20201029223110626](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201029223110626.png)

## 2.allure安装

![image-20201029223316667](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201029223316667.png)

命令行安装：

linux：sudo  apt-get install allure

mac:    brew install  allure

windows:   scoop install allure

举例：windows下安装allure

第一步：安装jdk

第二步：在https://github.com/allure-framework/allure2/releases下下载allure安装包（）

第三步：

## 3.pytest与allure的交互

# 五.pycharm设置pytest解释器

pycharm可以将解释器设置为pytest

第一步：设置单元测试解释器为pytest（默认为unittest）

![image-20201211193035191](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201211193035191.png)

第二步：设置pycharm执行的解释器为pytest

![image-20201211193526326](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201211193526326.png)

![image-20201211193301316](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201211193301316.png)

如果要切换会python解释器，做法一样，先清楚所有解释器，再选择python解释器，再选择需要执行的py文件

