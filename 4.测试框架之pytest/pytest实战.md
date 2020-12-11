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

9. 

### （2）方法二：pytest.main()运行

格式：pytest.main('参数',‘测试用例模块路径’)

参数和终端运行时一样

### （3）自定义用例的执行顺序

我们可以所有第三方插件pytest-ordering,来自定义用例的执行顺序

1. 安装：pip install pytest-ordering

2. 使用：给用例加上@pytest.mark.run(order=1)

   ```python
   import pytest
   from python_yuan.clac import Clac
   
   class TestClac:
   
       @pytest.mark.add
       @pytest.mark.parametrize("a,b,c",[(1,1,2),(-1,2,1),(-3,-8,-11)])
       def test_jia(self,a,b,c):
           result = Clac(a,b).clac_jia()
           assert result == c
   
       @pytest.mark.run(order=2)
       @pytest.mark.parametrize("a,b,c",[(1,1,0),(-1,2,-3),(-3,-8,5)])
       def test_jian(self,a,b,c):
           result = Clac(a, b).clac_jian()
           assert result == c
   
       @pytest.mark.run(order=1)
       @pytest.mark.parametrize("a,b,c", [(1, 1, 1), (-1, 2, -2), (-3, -8, 24)])
       def test_cheng(self,a,b,c):
           print("aaa")
           result = Clac(a, b).clac_cheng()
           assert result == c
   
       @pytest.mark.parametrize("a,b,c", [(1, 1, 1), (-1, 2, -0.5), (-3, -8, -3/-8)])
       def test_chu(self,a,b,c):
           result = Clac(a, b).clac_chu()
           assert result == c
   ```

3. 执行：pytest -v test_clac.py

   ![image-20201101220830296](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201101220830296.png)

顺序原理：先安装order数字大小执行所有添加了order的测试用例，在按照用例的先后顺序执行所有没有添加order的用例

### （4）自定义pytest的匹配规则

#### pytest的默认匹配规则为：

模块：以test开头的py文件

类：以Test开头的类

方法：以test开头的方法

#### 自定义pytest的匹配规则：

1. 在当前目录下创建pytest.ini文件

   ```python
   # fulename = pytest.ini
   [pytest]
   
   # 自定义python模块匹配规则
   python_files = 'abc_*.py'
   
   # 自定义pytho类匹配规则
   python_classes = 'Abc*'
   
   # 自定义pytho方法匹配规则
   python_functions = 'abc*'
   
   # 自定义命令行，执行pytest，就相当于执行pytest -vs --alluredir ./report命令
   addopts = -vs --alluredir ./report
   ```

## 4.数据驱动

### （1）测试数据的参数化

**使用@pytest.mark.parametrize的方式给用例传递数据**

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

**使用@pytest.mark.parametrize结合yaml给用例传递数据**

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

## 6.allure

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
allure generate ./report # 会创建一个allure-report文件，里面有html格式的测试报告
```

第四步：打开测试报告

```
allure open allure-report/ #去open整个文件夹
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





