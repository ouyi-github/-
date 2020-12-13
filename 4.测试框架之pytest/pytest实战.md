# 一.github与pycharm的连用

1.打开pycharm，创建好项目及相关目录

![image-20201101162521751](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201101162521751.png)

2.创建一个版本库

在命令行输入git init---------需要对应已经安装了git

![image-20201101163446225](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201101163446225.png)

3.提交文件到本地仓库

![image-20201101164811393](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201101164811393.png)

4.提交到github上

（1）到github上创建对应项目

https://github.com/

![image-20201101165329661](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201101165329661.png)

（2）复制对应的ssh码

![image-20201101165929186](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201101165929186.png)

（3）将本地与github项目关联

在命令行输入 git remote add origin git@github.com:ouyi-github/cskf.git

或者在pycharm中添加对应的ssh

VCS>>GIT>>Romotes

![image-20201101171036265](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201101171036265.png)



（4）将本地项目的一些文件push到GitHub

git push origin master

（5）将github上的代码pull到本地

git pull origin master

注意：实际开发中，不会直接使用master分支

# 二.pytest实战

## 1.安装

pip install pytest

## 2.pytest case

pytest测试用例的编写方法

（1）方法一：直接编写以test开头的方法

```python
def test_a(login):
    print('需要登录的测试用例')
    assert 1
```

（2）方法二：编写以Test开头的类，在类中编写test开头的方法

```python
class TestClac:
    def test_jia(self):
        result = 1 + 2
        assert result == 3
```

## 3.pytest runner

pytest运行测试用例的方法

### （1）方法一：终端运行

格式：pytest + 参数 + 测试用例模块路径

常用的参数：

1. pytest + 测试用例模块路径---------执行对应模块下的测试用例

   ```
   pytest test_clac.py
   # 执行test_clac.py文件下的所有以test开头的方法，以及以Test开头的类，且在类中以test开头的方法。
   ```

2. pytest  -v + 测试用例模块路径-----执行对应模块下的测试用例，并且打印详细日志

   ```
   pytest -v test_clac.py
   ```

3. pytest  -s + 测试用例模块路径-----执行对应模块下的测试用例，并且打印控制台消息（及会打印用例中，print的内容）

   ```
   pytest -s test_clac.py
   ```

4. pytest  -k '正则表达式' + 测试用例模块路径-----执行对应模块下的能被正则表达式匹配到的测试用例

   ```
   pytest -v -k 'jia' test_clac.py--------执行test_clac.py文件下，用例名称含‘jia’的测试用例，并且打印详细日志
   pytest -v -k 'jia or cheng' test_clac.py----执行test_clac.py文件下，用例名称含‘jia’或者含‘cheng’的测试用例，并且打印详细日志
   pytest -v -k 'not cheng' test_clac.py------执行test_clac.py文件下，用例名称含‘cheng’以外的所有测试用例，并且打印详细日志
   ```

5. pytest test_clac.py --collect-only-----收集test_clac.py下的所有测试用例，但不执行

6. pytest -m add test_clac.py---------执行test_clac.py下的所有有add标签的测试用例

7. pytest -v test_clac.py --junit-xml=./result-----执行test_clac.py下的所有测试用例，别且生成一个xml格式的result文件保存在当前目录下

8. pytest test_clac.py::TestClac::test_jia-----执行test_clac.py下的TestClac类中的test_jia测试用例


### （2）方法二：pytest.main()运行

格式：pytest.main('参数',‘测试用例模块路径’)

参数和终端运行时一样

## 4.数据驱动

### （1）测试数据的参数化

#### 用例传递数据初始参数化

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

#### 结合yaml给用例传递数据

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

#### 读取文件数据方法封装：

我们获取yaml数据的步骤可以抽离出来，封装为一个独立的方法

```python
def get_data_from_yaml(path):
    with open(path,'r') as f:
        data = yaml.safe_load(f)
        return data

class TestCal:
    data = get_data_from_yaml
    
    @pytest.mark.parametrize('a,b',data(path='./case_data/test_calculatorcase_data.yaml'),ids=['first_case', 'two_case', 'three_case'])
    def test_add(self,a,b):
        assert True
        
# ids表示给用例取别名，每一组数据对应一条用例，对应一个别名
```

### （2）测试步骤的参数化

可以将测试步骤也以数据的形式传给用例

```python
# 测试代码文件 clac.py
class Clac:
    """创建加减乘除类"""

    def __init__(self,a,b):
        """获取数据"""
        self.a = a
        self.b = b

    def clac_jia(self):
        """加法计算方法"""
        return self.a + self.b

    def clac_jian(self):
        return self.a - self.b

    def clac_cheng(self):
        return self.a * self.b

    def clac_chu(self):
        return self.a / self.b
```

```python
# 测试代码
import pytest
from python_yuan.clac import Clac #导入待测试的代码

@pytest.mark.parametrize('step',['jia','jian','cheng','chu'])
def test_step(step):
    a = 10
    b = 20 #实际工作中，测试数据也是参数化的。这里为了方便理解，把数据写死了。
    if step == 'jia':
        result = Clac(a,b).clac_jia()
        except1 = a + b
    elif step == 'jian':
        result = Clac(a,b).clac_jian()
        except1 = a - b
    elif step == 'cheng':
        result = Clac(a,b).clac_cheng()
        except1 = a * b
    elif step == 'chu':
        result = Clac(a,b).clac_chu()
        except1 = a / b
    assert result == except1
```

## 5.pytest fixture

### 自带的fixture（setup和teardown）



![image-20201027232513577](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201027232513577.png)

-  function 定义在类外， 类外的每一个用例都执行
-  class     定义在类中，每个类执行
-  module   定义在类外，每个模块执行
-  session   定义在类外 每个session只运行一次，在自动化测试时，登录步骤可以使用该session
-  method 定义在类中，类中的每个用例都执行
-  setup/teardown  定义在类外，则类外的每个用例都执行；定义在类中，则类中的每个用例都执行

用例的执行顺序：

session级别 >module级别   >class级别>function级别。

可以给fixture（）加上参数autouse=True，这样优先级会高于同级别的fixture

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

前面讲了setup、teardown可以实现在执行用例前或结束后加入一些操作，但这种都是针对整个脚本全局生效的。
如果有以下场景：用例 1 需要先登录，用例 2 不需要登录，用例 3 需要先登录。很显然无法用 setup 和 teardown 来实现。fixture可以让我们自定义测试用例的前置条件，并且可以**跨文件**使用。

- 命名方式灵活，不局限于 setup 和teardown 这几个命名
- conftest.py 配置里可以实现数据共享，不需要 import 就能自动找到fixture
- scope=“session” 以实现多个.py **跨文件**共享

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

```python
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

之前使用@pytest.fixture(scope='module')来定义作用域，scope的参数有以下几种

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

#### 通过conftest.py文件实现共享fixture

放在conftest.py文件下的fixture可以供整个conftest.py作用域下的用例使用

> conftest.py这个文件名是固定的，不可以更改。
> 使用的时候不需要导入conftest.py，会自动寻找.

演练：

第一步：创建一个conftest.py文件

```python
# filename = conftest.py
#coding=utf-8
import pytest
@pytest.fixture()
def loginss():
    print('开始ss执行用例')
    yield
    print('执行ss用例结束')
```

第二步：在用例中使用fixture：loginss

```python
import pytest
def test_a(loginss):
     assert True
def test_b(loginss):
     assert True
def test_c():
     assert True
```

注意conftest.py文件的作用域：

1.conftest.py创建在项目目录下，则项目下的所有用例文件都可共享

2.conftest.py创建在某个带__init__.py文件的包下，则该包下的所有用例文件都可共享

#### fixture中使用参数

在fixture中使用request.param来获取传进来的参数

```python
import pytest
@pytest.fixture(params=["参数1","参数2"])
def myfixture(request):
    print("执行testPytest里的前置函数，%s" % request.param)
```

注意：参数无法从用例处，传给fixture。因为用例调用fixture只是将fixture的函数名，作为参数。

#### fixture中返回参数

```python
import pytest
@pytest.fixture(params=["参数1","参数2"])
def myfixture(request):
    return request.param

def test_print_param(myfixture):
    print("执行test_two")
    print(myfixture)
    assert 1==1
```

输出：

```python
PASSED                    [ 50%]执行test_two 
参数1
PASSED                    [100%]执行test_two
参数2
```

注意：如果是setup中返回参数，使用yield代替return

## 6.pytest常用用法：

### （1）pytest.mark.标记名

可以使用‘pytest.mark.标记名’来给用例添加标记

执行用例时使用’pytest -m 标记名‘来实现执行特殊标记的用例

```python
import pytest

@pytest.mark.demo
@pytest.mark.smoke
def test_a():
     assert True

@pytest.mark.demo
def test_b():
     assert True

@pytest.mark.smoke
def test_c():
     assert True

def test_d():
     assert True
```

执行用例：

```
pytest -vs test_code.py -m="demo" # 执行模块下含demo标记的所有用例 ,执行test_a，test_b
pytest -vs test_code.py -m="demo and smoke" # 执行模块下含demo和smoke标记的所有用例 ,执行test_a
pytest -vs test_code.py -m "demo or smoke" # 执行模块下含demo或smoke标记的所有用例 ,执行test_a，test_b，test_c
```

现在执行时，会报w'arning错误，可以在项目目录下创建一个pytest.ini文件，然后在pytest.ini文件中配置标记名，来解决该问题

![image-20201213145552374](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201213145552374.png)

### （2）pytest.mark.skip直接跳过用例的执行

我们可以给用例加上装饰器pytest.mark.skip，来跳过该用例的执行。pytest会收集该用例，但不会执行

```python
@pytest.mark.skip(reason='不想执行呢') # reason参数可以写跳过的原因，非必须参数
def test_a():
     assert True

def test_b():
     assert True

def test_c():
     assert True

def test_d():
     assert True
```

执行结果：

```
test_code.py::test_a SKIPPED
test_code.py::test_b PASSED
test_code.py::test_c PASSED
test_code.py::test_d PASSED
```

### （3）pytest.mark.skipif()满足条件时，跳过用例

```python
import pytest

@pytest.mark.skipif(1 == 1,reason='不想执行呢') # 满足条件时，跳过用例的执行
def test_a():
     assert True

def test_b():
     assert True

def test_c():
     assert True

def test_d():
     assert True
```

结果：

```python
test_code.py::test_a SKIPPED
test_code.py::test_b PASSED
test_code.py::test_c PASSED
test_code.py::test_d PASSED
```

### （4）pytest.ini添加配置

pytest.ini文件是pytest的一个配置文件，我们可以在pytest.ini文件中，添加一些常用的配置，比如自定义pytest命令，自定义pytest的匹配规则等

第一步：在项目目录下创建一个pytest.ini文件

第二步：编辑pytest.ini文件

```
[pytest]
;添加mark标记，防止运行时报wraning
markers = demo
          smoke
          
;自定义pytest添加命令参数，现在运行pytest命令= ‘pytest -sv’    
addopts = -sv

;自定义测试文件命名规则,匹配check或者test开头的文件
python_files = check* test*

;自定义测试类命名规则,匹配Check或者Test开头的类
python_classes = Check* Test*

;自定义测试方法命名规则,匹配check或者test开头的方法
python_functions = test_* check_*
```

## 7.pytest实用插件介绍

### （1）用例失败后自动重新运行：pytest-rerunfailures

安装插件：

```bash
pip install pytest-rerunfailures
```

使用方法：

```bash
pytest test_x.py --reruns=n  #--reruns=n 失败后重运行的次数
pytest -v --reruns 3 --reruns-delay 5 test_abc.py #--reruns-delay 5表示重试时间隔5秒
```

同时也可以在脚本中指定定义重跑的次数，这个时候在运行的时候，就无需加上 --reruns 这个参数

```python
@pytest.mark.flaky(reruns=6, reruns_delay=2)
    def test_example(self):
        print(3)
        assert random.choice([True, False])
```

### （2）多重校验：pytest-assume

pytest中可以用python的assert断言，也可以写多个断言，但一个失败，后面的断言将不再执行。那么如何让断言失败后，继续往下执行呢

安装插件：

```bash
pip install pytest-assume
```

使用方法：

```python
def test_simple_assume(x, y):
    pytest.assume(x == y)
    pytest.assume(True)
    pytest.assume(False)
```

### （3）分布式并发执行：pytest-xdist

pytest-xdist的出现就是为了让自动化测试用例可以分布式执行，从而节省自动化测试时间

分布式执行用例的设计原则：

1. 用例之间是独立的，用例之间没有依赖关系，用例可以完全独立运行【独立运行】
2. 用例执行没有顺序，随机顺序都能正常执行【随机执行】
3. 每个用例都能重复运行，运行结果不会影响其他用例【不影响其他用例】

安装插件：

```python
pip install pytest-xdist
```

使用方法：

多cpu并行执行用例，直接加个-n参数即可，后面num参数就是并行数量，比如num设置为3

```python
pytest -n 3
```

### （4）控制用例的执行顺序：pytest-ordering

安装插件：

```bash
pip install pytest-ordering
```

使用方法：

```python
import pytest

@pytest.mark.run(order=2)
def test_foo():
    assert True

@pytest.mark.run(order=1)
def test_bar():
    assert True
```

注意：

1.顺序原理：先安照order数字大小执行所有添加了order的测试用例，在按照用例的先后顺序执行所有没有添加order的用例

2.尽量不要让测试用例有顺序，尽量不要让测试用例有依赖！

### （5）hook（钩子）函数定制和扩展插件【了解】

官网：https://docs.pytest.org/en/latest/_modules/_pytest/hookspec.html

```
pytest_collection_modifyitems
```

Pytest在收集完所有测试用例后调用该钩子方法。我们可以定制化功能实现：

1. 自定义用例执行顺序
2. 解决编码问题（中文测试用例名称）
3. 自动添加标签

例如：
conftest.py里面：

添加：

```python
def pytest_collection_modifyitems(session, config, items):
    print(type(items)) # items是一个列表，包含所有的pytest收集到的用例
    items.reverse()
    for item in items:
        item.name = item.name.encode('utf-8').decode('unicode-escape') # 设置用例名字的编码方式
        item._nodeid = item.nodeid.encode('utf-8').decode('unicode-escape') # 设置用例ID的编码方式
		
        # 根据用例名字来自动添加mark标记
        if "add" in item._nodeid:
            item.add_marker(pytest.mark.add)
        if "div" in item._nodeid:
            item.add_marker(pytest.mark.div)
```

hook中包含很多函数，主要是用来定制特殊场景的。我们一般使用pytest_collection_modifyitems来解决编码问题

## 8.allure

### 1.安装：

linux：

方法一： sudo apt-get install allure（网络问题不一定成功）

方法二：https://repo1.maven.org/maven2/io/qameta/allure/allure-commandline/2.13.3/下载allure的zip包；

​				安装jdk：sudo apt install openjdk-8-jdk-headless

​				添加软连接（配置环境变量）：ln -s /root/allure-2.13.3/bin/allure /usr/bin/allure

windows：https://repo1.maven.org/maven2/io/qameta/allure/allure-commandline/2.13.3/下载allure的zip包，安装jdk1.8，然后配置jdk和allure环境变量即可。

总结：allure安装就是解压zip包，配置到环境变量即可。需要安装jdk

### 2.python中使用：

第一步：需要安装allure-pytest

第二步：结合allure，pytest执行测试用例：

```
pytest test_clac.py --alluredir report # 会创建一个report文件夹，里面有许多测试数据的json文件
```

第三步：读取json文件，生成测试报告

```
allure generate ./report # 会创建一个allure-report文件，里面有html格式的测试报告，可以使用-o来自己指定想要生成的文件名字
```

第四步：打开测试报告

```
allure open allure-report/ #去open整个文件夹，会在本地启动一个web服务，通过访问这个服务，可以查看测试报告
```

### 3.allure常用方法

#### （1）feature,story,step的使用

![image-20201211203201771](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201211203201771.png)



登录例子：(feature和story，step)

```python
import allure
from selenium import webdriver

@allure.feature('登录模块')
class TestLogin:
    @allure.story('登录成功')
    def test_login_success(self):
        with allure.step('输入用户名'):
            print('输入用户名')
        with allure.step('输入密码'):
            print('输入密码')
        with allure.step('点击登录'):
            print('点击登录')
        assert True

    @allure.story('用户名错误')
    def test_login_username_failed(self):
        with allure.step('输入用户名'):
            print('输入用户名')
        with allure.step('输入密码'):
            print('输入密码')
        with allure.step('点击登录'):
            print('点击登录')
        assert  True

    @allure.story('密码错误')
    def test_login_passwd_failed(self):
        with allure.step('输入用户名'):
            print('输入用户名')
        with allure.step('输入密码'):
            print('输入密码')
        with allure.step('点击登录'):
            print('点击登录')
        assert True

@allure.feature('搜索模块')
class TestSearch:
    @allure.story('精确匹配')
    def test_precise_search(self):
        assert  True

    @allure.story('模糊匹配')
    def test_dim_search(self):
        assert True
```

在终端执行代码：

```shell
1.pytest -vs test_code.py --alluredir=report/testreport2 --allure-features=登录模模块  --allure-stories=用户名错误,密码错误
# pytest -vs test_code.py》》》》执行测试用例文件
# --alluredir=report/testreport2》》》生成初始初始报告，报告位置./alluredir=report/testreport2目录
# --allure-features=登录模模块  --allure-stories=用户名错误,密码错误 》》》只执行登录模块下的‘用户名错误和密码错误’两条测试用例
2.allure generate report/testreport2 --clean
# 解析report/testreport2的初始报告文件，并生成html报告保存在allure-report目录下，如果allure-report目录下已经有之前的报告了，则需要加参数--clean将其清除掉
3.allure open allure-report
# 打开测试报告，会生成一个服务地址，使用浏览器访问即可查看报告
```

报告如下：

![image-20201211221342091](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201211221342091.png)

![image-20201211221413934](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201211221413934.png)

我们定义的feature，story，step在报告中都有展示

总结：

feature一般用来标识大的功能模块，对应class

stroy一般用来标识各个子功能，对应function

step一般用在用例步骤中，用来描述用例执行时的具体操作步骤

#### （2）sevearity来设置用例级别

![image-20201212194106490](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201212194106490.png)

severity例子：

```python
@allure.sevearity(allure.severity_level.NORMAL)
def test_a():
    assert True

@allure.severity(allure.severity_level.MINOR)
def test_b():
    assert True
    
@allure.severity(allure.severity_level.TRIVIAL)
def test_c():
    assert True
    
def test_d():
    assert True

@allure.severity(allure.severity_level.NORMAL)
class Test_h:

    @allure.severity(allure.severity_level.MINOR)
    def test_e(self):
        assert True

    @allure.severity(allure.severity_level.TRIVIAL)
    def test_f(self):
        assert True

    def test_g(self):
        assert True

class Test_i:
    def test_j(self):
        assert True
```

执行用例：

```
pytest -vs test_code.py --alluredir=report/testreport --allure-severities=normal,minor
# --allure-severities=normal,minor表示执行normal和minor级别的用例
# 执行了test_a，test_b，test_e，test_g四条用例
```

筛选规则：

1.对于类外的用例：

- 含选中级别标记的用例执行
- 含未选中级别标记或者未添加级别标记的用例不执行

2.对于含选中级别标记的类：

- 会执行类下的未添加级别标记和添加了选中的级别标记的用例

3.对于含未选中级别标记的类或者未添加标记的类：

- 会执行类下的含选中级别标记的用例
- 类下的含未选中级别标记和未添加级别标记的用例不执行

#### （3）title设置用例名称

![image-20201212211044903](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201212211044903.png)

title例子：

```python
@allure.feature('登录模块')
class TestLogin:
    @allure.title('登录成功用例')
    @allure.story('登录成功')
    def test_login_success(self):
        """
        登录成功测试用例
        :return:
        """
        assert True

    @allure.title('用户名错误用例')
    @allure.story('用户名错误')
    def test_login_username_failed(self):
        """
        登录失败》用户名错误的测试用例
        :return:
        """
        assert  True

    @allure.title('密码错误用例')
    @allure.story('密码错误')
    def test_login_passwd_failed(self):
        """
        登录失败》密码错误的测试用例
        :return:
        """
        assert True
```

执行用例：

```
pytest -vs test_code.py --alluredir=report/testreport3
allure generate report/testreport3 --clean
allure open allure-report
```

结果：

![image-20201212211846452](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201212211846452.png)

总结：allure.title只能修饰函数，及只能用来给用例取别名。对class类无效

#### （4）attach在用例中添加文字，html代码，图片，视频等

我们可以使用allure的attach来实现在用例中添加文字，html代码，图片，视频等。

attach例子：

```python
def test_text():
    try:
        assert False
    except Exception as e:
        allure.attach(body='<body>啊哦，用例执行失败了</body>',name='错误提示') # 两个参数，body是要添加的内容,name是取的别名
        allure.attach(body='这是错误日志',name="错误日志") # 两个参数，body是要添加的内容,name是取的别名
        allure.attach.file(source='C:/Users/Administrator.DESKTOP-7PKNCLF/Pictures/Saved Pictures/喵咪.jpg',
                           name="失败截图",attachment_type=allure.attachment_type.JPG)

        allure.attach.file(source='E:/测试开发/06 Python语言基础√/6 python模块.ts',name='失败视频',
                           attachment_type=allure.attachment_type.MP4)# 三个参数，source是要添加的内容,name是取的别名，attachment_type是要保存为的文件类型
        raise e
```

结果：

![image-20201212214406541](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201212214406541.png)

总结：当用例运行失败时，我们可以使用attach来添加错误日志，截图等到测试报告中

#### （5）testcase在报告中添加url连接

testcase例子：

```python
@allure.testcase('www.baidu.com')
def test_text():
     assert True
```

结果：

![image-20201212215400500](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201212215400500.png)