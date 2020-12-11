# 一.selenium介绍及环境配置

## 1.selenium三大组件的介绍：

![image-20201103192807869](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201103192807869.png)

WebDriver:是selenium提供的一个API，用于操作浏览器。

IDE：是selenium提供的一个插件，可以录制用户的操作

Grid：是selenium分布式的工具，实现在多个浏览器操作

我们编写自动化主要使用WebDriver来实现。

## 2.selenium的原理

![image-20201103193454072](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201103193454072.png)

## 3.selenium的配置步骤

![image-20201103194238932](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201103194238932.png)

注意：

（1）下载driver：https://npm.taobao.org/mirrors/，选择对应的浏览器driver已经对应的版本，下载zip包。

（2）解压

（3）配置环境变量：

​			a：linux：sudo mv chromedriver /usr/bin（将驱动移动到/usr/bin目录下）

​			b：windows：将驱动chromedriver 所在的目录配置在环境变量下（path）

# 二.selenium编写自动化脚本

selenium编写测试用例的步骤：

（1）导入依赖

（2）生成driver

（3）执行测试步骤

（4）断言

## 1.生成driver

```python
from selenium import webdriver # 导入依赖
driver = webdriver.Chrome() # 使用webdriver，生成一个对应浏览器的driver。该driver提供了许多操作浏览器的API
```

## 2.driver的常用API

### （1）常见操作

#### 1.打开浏览器，进入网址

```python
driver.get('https://www.testerhome.com/')
```

#### 2.鼠标点击：定位元素后.click()

```python
driver.find_element_by_id('su').click()
```

#### 3.输入内容：定位元素后.send_keys("内容")

```python
driver.find_element_by_id('kw').send_keys('自动化测试')
```

#### 4.清空内容：定位元素后.clear()

```python
element = driver.find_element(By.ID,'kw')
element.send_keys('自动化测试')
sleep(2)
element.clear()
```

#### 5.退出浏览器

```python
driver.quit()
```



### （2）进阶操作

#### 1.简介

selenium给我们提供了两种操作浏览器控件的actions接口：

![image-20201104195034638](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201104195034638.png)

![image-20201104195502571](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201104195502571.png)

![image-20201104195544797](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201104195544797.png)

#### 2.ActionChains（web）

##### （1）.鼠标单击，双击，左键操作

```python
from selenium import webdriver
from selenium.webdriver import ActionChains
import pytest

class TestSelenium:
    def setup(self):
        self.driver = webdriver.Chrome()
        self.driver.get("http://sahitest.com/demo/clicks.htm")
        self.driver.implicitly_wait(5)

    def teardown(self):
        self.driver.close()

    def test_selenium(self):
        # 定位元素
        element_click = self.driver.find_element_by_xpath("//*[@value='click me']")
        element_double_click = self.driver.find_element_by_xpath("//*[@value='dbl click me']")
        element_right_click = self.driver.find_element_by_xpath("//*[@value='right click me']")

        # 创建一个action
        action = ActionChains(self.driver)

        # 给action添加需要执行的方法
        action.click(element_click) # 鼠标左键单击
        action.double_click(element_double_click) # 鼠标左键双击
        action.context_click(element_right_click) #鼠标右键点击

        # 执行action
        action.perform()
```

##### （2）.鼠标移动到某个元素上

```python
from selenium import webdriver
from selenium.webdriver import ActionChains
import pytest
from time import sleep

class TestSelenium:
    def setup(self):
        self.driver = webdriver.Chrome()
        self.driver.implicitly_wait(5)
        self.driver.maximize_window() #最大化窗口
    def teardown(self):
        self.driver.close()
    def test_move(self):
        self.driver.get("https://www.baidu.com/")
        # 定位元素
        ele = self.driver.find_element_by_id("s-usersetting-top")
        # 创建action
        action = ActionChains(self.driver)
        # 给action添加操作方法
        action.move_to_element(ele) # 移动到元素上,但不点击
        # 执行action
        action.perform()
```

##### （3）.拖拽一个元素到另一个元素上

方法一：

```python
from selenium import webdriver
from selenium.webdriver import ActionChains
import pytest
from time import sleep

class TestSelenium:
    def setup(self):
        self.driver = webdriver.Chrome()
        self.driver.implicitly_wait(5)
        self.driver.maximize_window() #最大化窗口

    def teardown(self):
        self.driver.close()

    def test_drag_drop(self):
        self.driver.get("http://sahitest.com/demo/dragDropMooTools.htm")
        # 定位元素
        drag_ele = self.driver.find_element_by_id("dragger")
        drop_ele = self.driver.find_element_by_xpath("/html/body/div[2]")
        # 创建action
        action = ActionChains(self.driver)
        # 给action添加操作方法
        action.drag_and_drop(drag_ele,drop_ele) # 拖拽并移动,传入两个参数，第一个为需要退拽的元素，第二个为释放位置的元素
        # 执行action
        action.perform()
```

方法二：

```python
from selenium import webdriver
from selenium.webdriver import ActionChains
import pytest
from time import sleep
class TestSelenium:
    def setup(self):
        self.driver = webdriver.Chrome()
        self.driver.implicitly_wait(5)
        self.driver.maximize_window() #最大化窗口
    def teardown(self):
        self.driver.close()
    def test_drag_drop(self):
        self.driver.get("http://sahitest.com/demo/dragDropMooTools.htm")
        # 定位元素
        drag_ele = self.driver.find_element_by_id("dragger")
        drop_ele = self.driver.find_element_by_xpath("/html/body/div[2]")
        # 创建action
        action = ActionChains(self.driver)
        # 给action添加操作方法
        action.click_and_hold(drag_ele) # 按下不放手
        action.release(drop_ele) # 释放鼠标
        # 执行action
        action.perform()
```

##### （4）.模拟键盘操作

```python
from selenium import webdriver
from selenium.webdriver import ActionChains
import pytest
from time import sleep
from selenium.webdriver.common.keys import Keys
class TestSelenium:
    def setup(self):
        self.driver = webdriver.Chrome()
        self.driver.implicitly_wait(5)
        self.driver.maximize_window() #最大化窗口
    def teardown(self):
        self.driver.close()
    def test_keys(self):
        self.driver.get("http://sahitest.com/demo/label.htm")
        # 定位元素
        ele1 = self.driver.find_element_by_xpath("/html/body/label[1]/input")
        ele2 = self.driver.find_element_by_xpath("/html/body/label[2]/table/tbody/tr/td[2]/input")
        # 创建action
        action = ActionChains(self.driver)
        # 给action添加操作方法
        ele1.click()
        action.send_keys("ouyi1") # 输入内容
        action.send_keys(Keys.SPACE) #输入空格
        action.send_keys("ouyi2") # 输入内容
        action.send_keys(Keys.CONTROL,'a') #全选
        action.send_keys(Keys.CONTROL, 'c')  # 复制
        ele2.click()
        action.send_keys(Keys.CONTROL, 'v')  # 粘贴
        # 执行action
        action.perform()
```

#### 3.TouchActions(移动端和web端)

注意：在web端使用TouchActions时，需要修改谷歌浏览器的启动options

##### （1）实现滑动

方式一：scroll_from_element----从某个元素开始滑动

```python
from selenium import webdriver
from selenium.webdriver import ActionChains,TouchActions
import pytest
from time import sleep
from selenium.webdriver.common.keys import Keys
class TestSelenium:
    def setup(self):
        # 设置谷歌的启动配置options
        option = webdriver.ChromeOptions()
        option.add_experimental_option('w3c',False) #设置谷歌启动方式不要为w3c
        self.driver = webdriver.Chrome(options=option)
        self.driver.implicitly_wait(5)
        self.driver.maximize_window() #最大化窗口
    def teardown(self):
        self.driver.quit()
    def test_touch1(self):
        self.driver.get("https://www.taobao.com/")
        # 定位元素
        ele = self.driver.find_element_by_id("J_TSearchForm")
        # 创建action
        action = TouchActions(self.driver)
        # 给action添加操作方法
        """从某个元素开始滑动。传入三个参数，第一个为开始作为滑动起点的元素，第一个为X偏移量，第三个为y偏移量"""
        action.scroll_from_element(ele,0,10000)
        # 执行action
        action.perform()
```

方式二：action.scroll(x偏移量，y偏移量)------从当前位置滑动指定的偏移量

```python
action.scroll(0,1000)
```

### （3）几种元素定位方式

#### （1）xpath定位

```python
格式：
1.driver.find_element_by_xpath('xpath路径')
2.driver.find_elements(By.XPATH,'xpath路径')
```

xpath详解：

![image-20201103215113043](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201103215113043.png)

![image-20201103215411847](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201103215411847.png)

练习：

```python
//div[@id="wraf"] #定位到id=wraf的div元素
//*[@id="wraf"] #定位到id=wraf的元素，*表示类型不限
//*[@id="wraf"]/* #定位到id=wraf的元素的所有子集元素，*表示类型不限
//*[@id="wraf"]/div #定位到id=wraf的元素的所有子集div元素
//*[@id="wraf"]//a #定位到id=wraf的元素的所有子集以及子集的子集（无论差几级）中的所有的a元素
```

#### （2）css_selector定位

```python
格式：
1.driver.find_element_by_css_selector('css路径')
2.driver.find_element(By.CSS_SELECTOR,'css路径')
```

css详解：



![image-20201103223236183](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201103223236183.png)

![image-20201103223358065](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201103223358065.png)

练习：

```python
#wraf #定位id为wraf的元素
#wraf>div #定位id为wraf的元素的子集中的所有div元素
#wraf a #定位id为wraf的元素的子子孙孙集中的所有a元素
#wraf a:nth-child(2) #定位id为wraf的元素的子子孙孙集中的所有a元素，且这些a元素属于它父级的第二个子元素。
```

#### （3）id定位

通过id属性来定位元素，定位唯一

```python
格式：
1.driver.find_element_by_id('kw')
2.element = driver.find_element(By.ID,'kw')
```

#### （4）name定位

通过 name 属性来定位元素，定位唯一

```python
driver.find_element_by_name('内容')
driver.find_element(By.NAME,'内容')
```

#### （5）class name 定位

通过元素的 class 属性来定位元素

```python
driver.find_element_by_class_name('内容')
driver.find_element(By.CLASS_NAME,'内容')
```

#### （6）link_text定位

通过链接文本信息来定位，只能用于a标签

```python
driver.find_element_by_link_text('内容')
driver.find_element(By.LINK_TEXT,'内容')
```

#### （7）partial link text 定位

对 link text 定位的补充，有些文本链接比较长，或者这些文本链接其中有一部分文本信息是动态生成的，这个时候，可以选择文本链接的一部分进行定位，只要这部分信息可以唯一的标识这个链接。

```python
driver.find_element_by_partial_link_text('内容')
driver.find_element(By.PARTIAL_LINK_TEXT,'内容')
```

#### （8）tag 定位

通过元素的标签名来定位元素

```python
driver.find_element_by_tag_name('内容')
driver.find_element(By.TAG_NAME,'内容')
```

















## 3.selenium的三种等待方式

### （1）直接等待

```python
from time import sleep
sleep(3) # 线程休眠3秒
```

### （2）隐式等待

```python
driver.implicitly_wait(5)
# 在5秒内不断检测元素是否出现，出现就结束等待，执行下一步。如果5秒内没有出现就抛出异常
# 隐式等待是作用在全局的，一般放在setup中
# 隐式等待有一个缺点：因为隐式等待是针对全局的元素而言的，而每个元素的加载时间是不一样的。所以隐式等待的等待时间是不能很好的兼容所有元素。
# 使用隐式等待会有这个bug，就是元素已经出现，但不能被点击。所以导致用例失败。这是因为浏览器加载时，会先加载DOM节点，然后再加载js等静态文件，所以会出现元素已经出现，但无法点击的问题。
```

### （3）显示等待

格式：

WebDriverWait(driver驱动,等待时间).until(方法1)：在规定的时间内不断的调用方法1，直到方法1返回True，结束等待。超时抛出异常

WebDriverWait(driver驱动,等待时间).until_not(方法1)：在规定的时间内不断的调用方法1，直到方法1返回False，结束等待。超时抛出异常

until后的方法，selenium中有许多。我们介绍几种常用的：

1.expected_conditions.presence_of_element_located----判断某个元素是否被加到了 dom 树里，并不代表该元素一定可见

```python
from selenium import webdriver # 导入依赖
from time import sleep

from selenium.webdriver.common.by import By
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.support.wait import WebDriverWait

driver = webdriver.Chrome()
driver.get('https://www.baidu.com/')

element = WebDriverWait(driver,10).until(EC.presence_of_element_located((By.ID,'kw')))
# 显式等待：直到对应的元素出现，就结束等待。并且定位到该元素

element.send_keys('selenium')
```

2.expected_conditions.visibility_of_element_located-----判断某个元素是否可见. 可见代表元素非隐藏，并且元素的宽和高都不等于 0

3.expected_conditions.presence_of_all_elements_located---判断是否至少有 1 个元素存在于 dom 树中。举个例子，如果页面上有 n 个元素的 class 都是'column-md-3'，那么只要有 1 个元素存在，这个方法就返回 True

4.expected_conditions.text_to_be_present_in_element---判断某个元素中的 text 是否 包含 了预期的字符串

5.expected_conditions.text_to_be_present_in_element_value----判断某个元素中的 value 属性是否包含 了预期的字符串

6.expected_conditions.invisibility_of_element_located----判断某个元素中是否不存在于dom树或不可见

7.expected_conditions.element_to_be_clickable---判断某个元素中是否可见并且是 enable 的，这样的话才叫 clickable

8.expected_conditions.element_to_be_selected---判断某个元素是否被选中了,一般用在下拉列表

## 4.多窗口的处理

### 4.1多窗口的识别

![image-20201104220442919](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201104220442919.png)

（1）获取当前窗口的句柄

```
driver.current_window_handle #返回当前的窗口句柄
```

（2）获取所有窗口的句柄

```
self.driver.window_handles # 返回一个包含所有窗口句柄的列表
```

### 4.2多窗口的切换

```
self.driver.switch_to_window(对应的窗口句柄) #切换到对应的窗口
```

## 5.frame处理

### 5.1frame简介

![image-20201104222123511](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201104222123511.png)

### 5.2frame的切换

![image-20201104223033421](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201104223033421.png)

![image-20201104223123668](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201104223123668.png)

![image-20201104223222498](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201104223222498.png)

## 6.selenium多浏览器的处理

我们可以将浏览器作为一个参数，传递给参数用例。来做浏览器的兼容性处理

```python
from selenium import webdriver
from selenium.webdriver import ActionChains,TouchActions
import pytest
from time import sleep
from selenium.webdriver.common.keys import Keys
import os
class TestBroswer:
    def setup(self):
        # 获取执行测试用例时传入的broswer的值，来判断使用哪个浏览器
        broswer = os.getenv('broswer')
        if broswer == 'firefox':
            self.driver = webdriver.Firefox()
        elif broswer == 'chrome':
            self.driver = webdriver.Chrome()

        self.driver.implicitly_wait(5)
        self.driver.maximize_window()  # 最大化窗口
    def teardown(self):
        self.driver.quit()
    def test_broswer(self):
        self.driver.get("https://www.baidu.com/")
        self.driver.find_element_by_id('kw').send_keys('selenium')
        self.driver.find_element_by_id('su').click()
```

这样我们在执行测试用例时，只需要传入broswer对应的值，就可以使用对应的浏览器了。

```
broswer=chrome pytest -v test_selenium.py
```

## 7.selenium执行JavaScript脚本

在自动化测试中，经常会有一些组件无法定位到。这时需要使用js来进行定位操作

### 7.1 selenium执行JavaScript命令

方式一：执行js脚本：driver.execute_script('js命令')

```python
from selenium import webdriver
from time import sleep
class TestJs:
    def setup(self):
        self.driver = webdriver.Chrome()
        self.driver.implicitly_wait(5)
        self.driver.maximize_window()
    def teardown(self):
        self.driver.quit()
    def test_js(self):
        self.driver.get("https://www.baidu.com/")
        # 使用selenium执行js脚本
        self.driver.execute_script('alert("selenium")')
        sleep(3)
```

方式二：执行js脚本，并将结果返回给selenium代码：driver.execute_script('return js命令')

```python
from selenium import webdriver
from time import sleep
class TestJs:
    def setup(self):
        self.driver = webdriver.Chrome()
        self.driver.implicitly_wait(5)
        self.driver.maximize_window()
    def teardown(self):
        self.driver.quit()
    def test_js(self):
        self.driver.get("https://www.baidu.com/")
        # 使用selenium执行js脚本
        ele1 = self.driver.execute_script('return document.getElementById("kw")')
        ele1.send_keys("selenium")
        ele2 = self.driver.execute_script('return document.getElementById("su")')
        ele2.click()
        sleep(3)
```

### 7.2使用js处理时间控件

![image-20201105230406400](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201105230406400.png)

```python
from selenium import webdriver
from time import sleep
class TestJs:
    def setup(self):
        self.driver = webdriver.Chrome()
        self.driver.implicitly_wait(5)
        self.driver.maximize_window()
    def teardown(self):
        self.driver.quit()
    def test_js(self):
        self.driver.get("https://www.12306.cn/index/")
        # 使用selenium执行js脚本
        # 定位到时间控件元素,并移除时间控件的readonly属性
        self.driver.execute_script('a = document.getElementById("train_date");a.removeAttribute("readonly")')
        self.driver.execute_script('a.value="2020-12-22"') #给时间控件的value赋值
        sleep(3)
```

## 8.selenium处理文件上传

![image-20201107203859256](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201107203859256.png)

```python
from time import sleep
from selenium import webdriver
class Test_File:
    def setup(self):
        self.driver = webdriver.Chrome()
        self.driver.implicitly_wait(5)
        self.driver.maximize_window()
    def teardown(self):
        self.driver.quit()
    def test_file(self):
        self.driver.get('https://www.baidu.com/')
        self.driver.find_element_by_xpath('//*[@id="form"]/span[1]/span[1]').click() #点击按图片搜索按钮
        ele = self.driver.find_element_by_xpath('//*[@id="form"]/div/div[2]/div[2]/input') #定位到上传文件按钮
        ele.send_keys('/home/ouyi/goods02.jpg') #上传图片
```

## 9.selenium处理弹窗

![image-20201107205630221](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201107205630221.png)

案例：

```python
from time import sleep
from selenium import webdriver
from selenium.webdriver import ActionChains
class TestAlert:
    """
    打开网页：https://www.runoob.com/try/try.php?filename=jqueryui-api-droppable
    将frame页面的元素1拖拽到元素2
    这时会有一个alert弹窗，操作接受alert弹窗
    点击界面的运行按钮
    """
    def setup(self):
        self.driver = webdriver.Chrome()
        self.driver.implicitly_wait(5)
        self.driver.maximize_window()
    def teardown(self):
        self.driver.quit()
    def test_alter(self):
        self.driver.get('https://www.runoob.com/try/try.php?filename=jqueryui-api-droppable') #打开网页
        self.driver.switch_to_frame('iframeResult') #切换到frame窗口
        drag_ele = self.driver.find_element_by_id('draggable') #定位元素1
        drop_ele = self.driver.find_element_by_id('droppable') #定位元素2
        action = ActionChains(self.driver) #创建action
        action.drag_and_drop(drag_ele,drop_ele) #添加拖拽方法
        action.perform() #执行action的方法
        sleep(2)
        alert_ele = self.driver.switch_to_alert() #获取界面弹窗对象
        alert_ele.accept() #接受弹窗
        self.driver.switch_to.parent_frame() #退出frame窗口
        self.driver.find_element_by_id('submitBTN').click() #点击运行按钮
        sleep(2)
```

## 10.selenium实现浏览器的复用

我们在selenium中如果以默认的self.driver = webdriver.Chrome()来打开一个浏览器，这种方式是打开一个全新的浏览器。我们可以给 webdriver.Chrome()传入option参数，来实现浏览器的复用。从而保存下浏览器已经有的状态和数据。

例如：我们要测试一个网站，它的许多测试点都需要登录后才能操作的。而它的登录不能实现自动化，那么我们可以启动浏览器，将其登录完成。然后在其他的测试用例中，就可以使用这个已经登录的浏览器，而不是去启动一个全新的浏览器。

以登录企业微信为例

第一步：确保chrome程序的启动文件已经配置到环境变量（usr/bin中）

第二步：在终端以端口（9222，也可以是其他未占用的端口），启动一个chrome程序。

```
google-chrome --remote-debugging-port=9222
```

然后手动打开企业微信网站：https://work.weixin.qq.com/wework_admin/frame

手动扫码登录

第三步：编写selenium自动化脚本：使用options方法，指定要打开的浏览器程序。

```python
from time import sleep
from selenium import webdriver
from selenium.webdriver.chrome.options import Options
class Testbroswer:
    def setup(self):
        option = Options() #创建一个option对象
        option.debugger_address = '127.0.0.1:9222' #option使用指定的浏览器程序
        self.driver = webdriver.Chrome(options=option) #使用指定的option生成driver
        self.driver.implicitly_wait(5)
        self.driver.maximize_window()
    def teardown(self):
        self.driver.quit()
    def test_broswer(self):
        self.driver.get("https://work.weixin.qq.com/wework_admin/frame") #此时进入企业微信网页时，就已经是登录状态了
        self.driver.find_element_by_id('menu_contacts').click() #点击通讯录按钮
        sleep(10)
```

## 11.selenium使用cookie

上面的案例，我们想要实现企业微信的跳过登录。除了可以复用浏览器外，还可以使用cookie功能。

第一步：打开浏览器，

第二步：获取cookie：self.driver.get_cookies()

```
登录企业微信。使用代码  self.driver.get_cookies()  获取页面的cookies
```

第二步：编写测试用例，在新的浏览器打开企业微信页面，使用传入cookie（）

```python
from selenium import webdriver
from time import sleep
class TestCookie:
    def setup(self):
        self.driver = webdriver.Chrome()
        self.driver.implicitly_wait(5)
        self.driver.maximize_window()
    def teardown(self):
        self.driver.quit()
    def test_cookie(self):
        # 将cookies放入变量中
        cookies = [
            {'domain': '.work.weixin.qq.com', 'httpOnly': False, 'name': 'wwrtx.vid', 'path': '/', 'secure': False,
             'value': '1688850814799304'},
            {'domain': '.work.weixin.qq.com', 'httpOnly': True, 'name': 'wwrtx.vst', 'path': '/', 'secure': False,
             'value': 't9WeHiLQAywSBmGmI12gOsE0ilqI3OJIxMS66KYmvznSI4VRY3ZxzJbFifXMg5f_QmSTOcfJ-1CesO3czeqYLiBwe7PMQttF54rA2hSBCXMNbVnb42PLJOco1ntRxj2f927lX2RRoj4sPH0gkB7QKglF-4TAAwwWXOSDXHx2j4Z7cS0yjmikvvsvb0E50u99c9t0zHJJ4AC9rsufkv-YWn_Zp7PGiLFeSP1upcN2xOSw2vP_lgJ4p4LtHvRMJK6nEXMJkliTZ7a8qwRROS8r2w'},
            {'domain': '.work.weixin.qq.com', 'httpOnly': False, 'name': 'wxpay.vid', 'path': '/', 'secure': False,
             'value': '1688850814799304'},
            {'domain': '.work.weixin.qq.com', 'httpOnly': False, 'name': 'wxpay.corpid', 'path': '/', 'secure': False,
             'value': '1970325100191509'}, {'domain': '.work.weixin.qq.com', 'expiry': 1636300223, 'httpOnly': False,
                                            'name': 'Hm_lvt_9364e629af24cb52acc78b43e8c9f77d', 'path': '/',
                                            'secure': False, 'value': '1604758667,1604758842,1604764224'},
            {'domain': '.work.weixin.qq.com', 'httpOnly': True, 'name': 'wwrtx.ref', 'path': '/', 'secure': False,
             'value': 'direct'},
            {'domain': '.work.weixin.qq.com', 'httpOnly': True, 'name': 'wwrtx.ltype', 'path': '/', 'secure': False,
             'value': '1'},
            {'domain': '.work.weixin.qq.com', 'httpOnly': False, 'name': 'wwrtx.d2st', 'path': '/', 'secure': False,
             'value': 'a8686426'},
            {'domain': '.work.weixin.qq.com', 'httpOnly': True, 'name': 'wwrtx.sid', 'path': '/', 'secure': False,
             'value': 'XpgcPt60DeBa2-FcophxYISeXtHo4nMqsljZ5C7mKq1OfUBAg0klxY7ixrRkKe2m'},
            {'domain': '.work.weixin.qq.com', 'httpOnly': True, 'name': 'wwrtx.refid', 'path': '/', 'secure': False,
             'value': '2298449271234700'},
            {'domain': '.qq.com', 'expiry': 1604851539, 'httpOnly': False, 'name': '_gid', 'path': '/', 'secure': False,
             'value': 'GA1.2.1592559454.1604758667'},
            {'domain': 'work.weixin.qq.com', 'expiry': 1604790194, 'httpOnly': True, 'name': 'ww_rtkey', 'path': '/',
             'secure': False, 'value': '1iqo9pj'},
            {'domain': '.qq.com', 'expiry': 1667837139, 'httpOnly': False, 'name': '_ga', 'path': '/', 'secure': False,
             'value': 'GA1.2.1580179371.1604758667'},
            {'domain': '.work.weixin.qq.com', 'expiry': 1636294658, 'httpOnly': False, 'name': 'wwrtx.c_gdpr',
             'path': '/', 'secure': False, 'value': '0'},
            {'domain': '.work.weixin.qq.com', 'expiry': 1607357565, 'httpOnly': False, 'name': 'wwrtx.i18n_lan',
             'path': '/', 'secure': False, 'value': 'zh'}]

        self.driver.get("https://work.weixin.qq.com/wework_admin/frame#contacts") #第一次打开网页
        # 传入cookie
        for cookie in cookies:
            self.driver.add_cookie(cookie)
        self.driver.get("https://work.weixin.qq.com/wework_admin/frame#contacts") #再次打开网页，此时变为了登录状态
        sleep(5)
```

## 12.pageObject模式

pageObject的核心思想，就是将一个页面封装成一个pageObject类。将页面上的主要元素的操作细节写成一个个方法。在写测试用例时我们就直接调用对应的pageObject类的接口，而不是在用例中去写操作细节。这样将使我们的代码维护性大大加强。

### 12.1pageObject的六大原则

1.用公共的方法去代替页面的服务（将页面主要元素的操作细节，封装成公共方法）

2.封装的方法，不要暴露太多的细节给外界。而是以接口的形式供外界调用

3.断言不要跟操作细节一起封装在pageObject中

4.页面类中的一个方法如果会跳转到一个新的页面，应该返回到这个新的页面的封装类

5.不需要对一个页面中的所有元素进行建模，而是对页面的主要元素进行建模

6.对不同的结果，封装成不同的页面类方法（失败的情况也需要考虑到）

### 12.2 pageObject实战

案例：完成对企业微信首页，企业微信登录，企业微信注册。三个页面的pageObject封装

![image-20201108195008927](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201108195008927.png)

![image-20201108195203972](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201108195203972.png)

![image-20201108195403453](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201108195403453.png)

代码文件结构如下：

![image-20201108201146644](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201108201146644.png)

首页pageObject实现：

```python
from selenium import webdriver
from selenium.webdriver.remote.webdriver import WebDriver

from web.page_workwx_login.login import Login
from web.page_workwx_login.register import Register
class Index:
    """企业微信首页pageObject"""
    def __init__(self,driver:WebDriver): #driver:WebDriver，指定参数driver的类型为WebDriver，
        # 这样在使用时可以出现相关的方法提示
        self._driver = driver

    def goto_register(self):
        """点击立即注册按钮的方法"""
        self._driver.get("https://work.weixin.qq.com/")
        self._driver.find_element_by_class_name('index_head_info_pCDownloadBtn').click() #点击立即注册
        return Register(self._driver) #返回立即注册页面的pageObject类,并且将这个driver传递给Register类

    def goto_login(self):
        """点击企业登录按钮的方法"""
        self._driver.get("https://work.weixin.qq.com/")
        self._driver.find_element_by_class_name('index_top_operation_loginBtn').click() #点击企业登录
        return Login(self._driver) #返回企业登录页面的pageObject类，并且将这个driver传递给Login类

```

登录页pageObject实现

```python
from selenium.webdriver.remote.webdriver import WebDriver
from web.page_workwx_login.register import Register
class Login:
    """企业登录页面的pageObject类"""
    def __init__(self,driver:WebDriver): #driver:WebDriver，指定参数driver的类型为WebDriver，
        # 这样在使用时可以出现相关的方法提示
        self._driver = driver #将之前pageObject类中的driver复用到这个pageObject中
    def scan_login(self):
        """扫码登录的方法"""
        pass #这个方法不好实现，所有不写
    def goto_register(self):
        """实现点击立即注册按钮的方法"""
        self._driver.find_element_by_class_name('login_registerBar_link').click() #点击立即注册
        return Register(self._driver) ##返回立即注册页面的pageObject类,并且将这个driver传递给Register类
```

注册页pageObject实现

```python
from time import sleep
from selenium.webdriver.remote.webdriver import WebDriver
class Register:
    def __init__(self,driver:WebDriver):
        self._driver = driver
    def register(self):
        """实现form表单的注册功能方法"""
        # 输入和点击等操作细节，这里我们就不写太具体。只完成两个操作示例即可
        # 数据本来应该使用参数的方式来实现，这里直接写死
        self._driver.find_element_by_id('corp_name').send_keys('华为技术有限公司') #输入公司
        self._driver.find_element_by_id('manager_name').send_keys('欧毅') #输入管理员姓名
        sleep(5)
        return True #这里应该返回注册完成后的页面
```

使用我们封装的pageObject接口，编写两条测试用例

第一个：首页点击立即注册》注册页注册

第二个：首页点击企业登录》登录页点击立即注册》注册页注册

```python
from selenium import webdriver
from web.page_workwx_login.index import Index
class TestPage:
    def setup(self):
        self._driver = webdriver.Chrome()
        self.index = Index(self._driver)
        self._driver.implicitly_wait(5)
        self._driver.maximize_window()
    def teardown(self):
        self._driver.quit()
    def test_page1(self):
        """首页点击立即注册》注册页注册"""
        self.index.goto_register().register()
    def test_page2(self):
        """首页点击企业登录》登录页点击立即注册》注册页注册"""
        self.index.goto_login().goto_register().register()
```

