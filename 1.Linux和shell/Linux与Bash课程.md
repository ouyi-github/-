# 一。Linux

### 0.Linux连接

- 打开Linux虚拟机（docker那台）
- 用户名/密码：root/123456
- ifup ens32（网卡）：启动网卡
- ifconfig：查看IP地址
- 使用CRT连接Linux（命令），FX（文件传输）

（1）Linux系统连接远程服务器

```
ssh -p端口号 用户名@服务器地址（host）--------ssh默认端口为22
```

（2）windows系统连接远程服务器

借助工具（xshell或者SecureCRT）

### 1。Linux目录结构

![image-20200801154159192](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801154159192.png)

常用目录介绍：

| 目录        |                                                              |
| ----------- | ------------------------------------------------------------ |
| /bin        | 存放二进制可执行文件(ls,cat,mkdir等)，常用命令一般都在这里。 |
| /etc        | 存放系统管理和配置文件                                       |
| /home       | 存放所有用户文件的根目录，是用户主目录的基点，比如用户user的主目录就是/home/user，可以用~user表示 |
| /usr        | 用于存放系统应用程序，比较重要的目录/usr/local 本地系统管理员软件安装目录（安装系统级的应用）。这是最庞大的目录，要用到的应用程序和文件几乎都在这个目录。/usr/x11r6 存放x window的目录/usr/bin 众多的应用程序 /usr/sbin 超级用户的一些管理程序 /usr/doc linux文档 /usr/include linux下开发和编译应用程序所需要的头文件 /usr/lib 常用的动态链接库和软件包的配置文件 /usr/man 帮助文档 /usr/src 源代码，linux内核的源代码就放在/usr/src/linux里 /usr/local/bin 本地增加的命令 /usr/local/lib 本地增加的库 |
| /opt        | 额外安装的可选应用程序包所放置的位置。一般情况下，我们可以把tomcat等都安装到这里。 |
| /proc       | 虚拟文件系统目录，是系统内存的映射。可直接访问这个目录来获取系统信息。 |
| /root       | 超级用户（系统管理员）的主目录（特权阶级^o^）                |
| /sbin       | 存放二进制可执行文件，只有root才能访问。这里存放的是系统管理员使用的系统级别的管理命令和程序。如ifconfig等。 |
| /dev        | 用于存放设备文件。                                           |
| /mnt        | 系统管理员安装临时文件系统的安装点，系统提供这个目录是让用户临时挂载其他的文件系统。 |
| /boot       | 存放用于系统引导时使用的各种文件                             |
| /lib        | 存放跟文件系统中的程序运行所需要的共享库及内核模块。共享库又叫动态链接共享库，作用类似windows里的.dll文件，存放了根文件系统程序运行所需的共享文件。 |
| /tmp        | 用于存放各种临时文件，是公用的临时文件存储点。               |
| /var        | 用于存放运行时需要改变数据的文件，也是某些大文件的溢出区，比方说各种服务的日志文件（系统启动日志等。）等。 |
| /lost+found | 这个目录平时是空的，系统非正常关机而留下“无家可归”的文件（windows下叫什么.chk）就在这里 |

### 2.shell基础

用户可以利用shell与Linux交互，shell有多种类别，常用的是bash

![image-20200801154837105](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801154837105.png)

如何运行shell脚本（两种方式）

![image-20200801154923295](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801154923295.png)

在linux环境下操作shell实战：

- 进入Linux系统，创建一个test.sh文件

  ```
  vi test.sh
  ```

- 在test.sh文件中，编辑shell命令

  ```
  #!/bin/bash         ------指定解析该文件使用的shell版本为bash
  echo 'hello!'       ------打印“hello！”
  ```

- 保存退出到vi命令，在linux下执行该文件

  ```
  方法一：
  chmod +x test.sh       --------赋予文件可执行权限
  ./test.sh              --------执行test.sh文件
  方法二：
  /bin/sh test.sh       ---------在外部指明解析sh文件使用的shell版本为sh
  ```

### 3.Linux常用命令：

1.文件操作

```
一。文件操作
9.ls：显示当前目录下的所有文件
(1)ls-a：显示所以文件，包括隐藏的目录和文件
(2)ls-A:显示所以文件，包括隐藏的目录和文件，但不包括“.”“..”目录
(3)ls-t：根据时间排序
(4)ls-l：显示目录和文件的完整属性
10.ls -ll：用列表的方式显示目录下文件的详细内容
11.vi:编辑文本文件（vi 文件名）
(1)按‘i’从一般模式进入到编辑模式
(2)按‘：’从一般模式进入到命令行模式，在该模式下输入‘wq’保存并退出，输入‘q！’不保存退出
(3)按esc键从编辑模式或命令行模式退出到一般模式
12.cat:查看文本文件内容
(1)cat -n连行号一起显示，包括标示空行
(2)cat -b：连行号一起显示，但不标示没有空行
13.cd：改变当前路径
14.pwd：显示当前所在的目录
15.mkdir：创建目录
(1)mkdir 文件路径 -p：当创建的目录父目录不存在时，同时创建父目录
16.rmdir：删除空目录
(1)对于非空目录只能将其底部的目录或文件删除，再用rmdir删除目录。或者用rm -fr命令循环删除非空目录
17.cp：复制文件或目录
(1)cp -r：循环复制，将目录及其子目录或者文件同时复制
①cp test1 /root/myword/010/011/test.cp表示将test1的文件复制到/root/myword/010/011目录下并改名叫test.cp
(2)cp -u：备份文件
18.rm：删除文件
(1)rm -f：强制删除，不用提示用户
(2)rm -r：循环删除目录及其底部的子目录或者文件
(3)rm -rf：强制循环删除
(4)rm -i:删除时询问
19.mv：移动文件或目录，常用于重命名工作
20.tar：打包命令/zip的用法也一样
(1)纯打包：tar -cvf 打包名 需要打包的文件1 文件2 文件3     对应的解包tar -xvf 包名
(2)打包并压缩：tar -zcvf 打包名 文件1 文件2    对应的解压缩包：tar -zxvf 包名
(3)tar -zxvf 包名 -C 目录名：解压到指定目录    
21.chmod:更改目录或文件的读写执行权限
(1)chmod 777 目录或者文件名：是将一个目录或者文件的权限放到最大
(2)ugo 法改变权限时，u 代表文件所有者，g 代表群组用户，o 代表其他用户 
(3)rwy rwx rwx 
(4)u   g   o
(5) 例如：chmod  u-x today0310 代表文件所有者去掉可执行权限 chmod -R o+x today0310 代表其他用户补上可执行权限
(6)Chmod -R:加上R参数，表示可以同时更改目录及其子目录或文件的权限
22.ln：建立连接
例如：ln -s ./test.sh ./a/test.sh----表示将./test.sh软连接到./a/test.sh
常用来把一些命令连接到/usr/bin目录下，相当于配置环境变量
23.find：查找文件
格式：find 路径 -name 表达式------在指定路径下，查找所有符合表达式的文件
例如：find / -name '*.txt'----在根目录下查找所有txt文件
24.文本查看命令
（1）cat:查看文本文件内容
	(1.1)cat -n连行号一起显示，包括标示空行
	(1.2)cat -b：连行号一起显示，但不标示没有空行
(2)less/more:分屏查看
(3)head -n 10 文件名----只查看前10行
(4)tail -n 10 文件名----只查看后10行
(5)tail -f -n 10 文件名----动态查看最后10行
25.echo---屏幕输出
26.>----重定向
例如：echo 666 > 666.txt------将屏幕输出的结果666保存到666.txt文件中
```

![image-20200801164326824](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801164326824.png)

![image-20200801164415695](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801164415695.png)

2.网络命令

```
ping 测试网络连接情况（可选参数 -c：ping的次数；-l每次ping的时间间隔）
netstat：打印Linux系统的网络状态信息（参数：-t：列出所有tcp；-u：列出所有udp；-l:只显示监听端口；-n：以数字形式显示地址和端口；-p：显示进程的pid和名字）
```

3.性能命令

```
top：持续监视系统性能
ps：查看进程信息（-aux：显示所有进程，包括用户和分组情况）
cat /proc/cpuinfo----查看cpu型号等相关信息

```

4.用户群组管理命令

```
22.su 用户名：切换用户
(1)管理员切换到普通用户不需要密码，从普通用户切换到管理员需要密码
(2)exit：切换会原来的用户
23.groupadd 群组名：用于创建一个新的群组。例：groupadd lianxi（创建一个叫lainxi的群组）------注意：此时系统会自动给群组分配群组id，从500开始按顺序排列
(1)groupadd -g 1500 lianxi（加上参数g，可以自定义群组id。这里的id指定为1500）
24.用户信息（passwd），用户密码（shadow），群组信息（group）等文件都在/etc目录下，可以用cat命令查看。
25.useradd 用户名：用来新建用户
(1)useradd -u 1600 ouyi（加上参数u可以自定义用户的id 为1600，否则系统将自动分配）
(2)useradd -g 1500（lianxi） ouyi（加上参数g，可以将新建的用户添加到群组。如果不加g参数，系统会自动创建一个与用户名相同的群组。注意，g后面可以跟群组id，也可以跟群组名）
(3)例:useradd -u 1600 -g 1500 ouyi
(4)Useradd 后面跟的参数表如下：


26.userdel 用户名:删除用户
(1)userdel -r 用户名:将该用户及其家文件和邮件同时删除,防止生产垃圾文件
27.groupdel 群组名:删除群组.(只有将群组下的用户都删除后,才能删除群组)
28.usermod 用户名:用与修改用户的id,加入群组等
(1)-u 用户id---可以指定用户id;
(2)-g 群组id(群组名)----可以指定用户加入某群组
(3)-G 群组id(群组名)---可以指定用户加入某附加群组
(4)例:usermod -u 1601 -g 1500 -G wsoy
29.id:用于产看用户的id,以及所属群组的信息
30.passwd 用户名:激活用户,也就是给用户加上密码
```

![image-20200801170217091](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801170217091.png)

5.安装包管理命令

```
1.yum  联网去下载所需要的rpm包，然后自动安装
(1)常用参数：-h：显示帮助信息；-v：显示安装细节；-y：对所有问题都回答yes
(2)yum search 软件名：查找需要安装的软件信息
(3)yum install 软件名：安装软件
(4)yum update 软件名：更新软件
(5)yum remove 软件名：卸妆软件
```

6.其他基础命令

```
1.“\”换行符：用于命令太长时换行使用。
(1)‘\’是换行符，‘/’标示根目录
2.上下键可以选择之前用过的命令
3.清屏命令：clear或ctrl+L（小写）键
4.Tab键：可以在命令忘记时，输入几个前字母，找到相关的命令或者补齐。
5.“｜”命令：将一个命令的输出作为另一个命令的输入 例： ifconfig | less（表示将ifconfig的命令输出分屏显示）
6.Shutdown：关机
7.Poweroff：直接关机
8.Reboot：重启
9.设置终端使用：
	（1）echo $LANG-----查看当前系统使用的语言
	（2）locale---------查看系统所有的语言包
	（3）yum install chinese-support-----联网下载中文语言包
	（4）LANG="zh_CN.UTF-8"-----设置语言
10.翻页
	（1）空格----一页一页向下翻
	（2）PGDN----一页一页向下翻
	（3）PGUP----一页一页向上翻 //数字键盘旁边
	（4）回车----一行一行向下翻
	（5）g------直接到第一行
	（6）G------直接到最后一行
	 (7)/------向下匹配字符串
	（8）？-----向上匹配字符串
	（9）f------显示当前浏览的行号
	（10）q-----退出查看
```

### 4.Linux三剑客与管道使用

##### 1.管道

![image-20200801170648563](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801170648563.png)

![image-20200801170713066](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801170713066.png)

##### 2.正则表达式

![image-20200801171610651](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801171610651.png)

![image-20200801171720419](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801171720419.png)

练习：

- 匹配以字母a开头的单词

  ```
  \ba\w*\b
  ```

- 匹配刚好6个字符的单词

  ```
  \b\w{6}\b
  ```

- 匹配1个或更多连续的数字

  ```
  \d+
  ```

- 匹配5到12位的QQ号

  ```
  ^[1-9]\d{4,11}$
  ```

##### 3.grep

![image-20200801171905952](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801171905952.png)

用法格式：grep + 参数 + 正则表达式+要匹配的内容

常见参数如下：

![image-20200801172023702](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801172023702.png)

![image-20200801172101972](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801172101972.png)

grep 中如果使用了扩展正则，会识别不了正则表达式。需要加上 ‘-E’参数才能正常使用

例如：

```
echo 'asdxcetccc' | grep c{3}$
这组命令并没有输出内容

echo 'asdxcetccc' | grep -E c{3}$
这组命令正确输出内容
```

![image-20201001000641716](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201001000641716.png)

![image-20200921201252265](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200921201252265.png)

##### 4.sed

grep只能对文本内容进行查找，而sed可以对文本内容进行增删改

![image-20200801172451097](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801172451097.png)

![image-20200801172547625](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801172547625.png)

![image-20200801172651300](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801172651300.png)

![image-20200801172731284](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801172731284.png)

![image-20200801173532030](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801173532030.png)



练习：

- 查看帮助文档

  ```
  方法一：
  man sed
  方法二：
  sed -h
  ```

- 在test.txt文件的第四行后添加字符串‘ouyi’

  ```
  sed -e '4 a ouyi' test.txt
  注意ouyi字符串也会独占一行，显示为第五行。
  ```

- 在在test.txt文件的第二行前添加字符串‘ouyi’

  ```
  sed -e '2 i ouyi' test.txt
  注意ouyi字符串也会独占一行，显示为第二行。
  ```

- 全局替换：将test.txt文件中的所有的‘root‘替换为‘hello’

  ```
  sed -e 's/root/hello/g' test.txt
  注意：如果不加g参数，只会替换每行中的第一个
  ```

- 修改文件内容：将test.txt文件中的所有的‘root‘替换为‘hello’

  ```
  sed -i 's/root/hello/g' test.txt
  注意，我们之前使用sed -e来对文件所做的更改，并没有修改文件本身。而使用sed -i会直接修改掉原文件
  ```

总结：sed和grep都是对文件进行操作，但grep只能对文件进行匹配查找，而sed更多是对文件进行修改后显示。

##### 5.awk

![image-20200801174507182](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801174507182.png)

![image-20200801174608498](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801174608498.png)

![image-20200801174805874](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801174805874.png)

![image-20200801174834194](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801174834194.png)

![image-20200801175010821](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801175010821.png)

![image-20200801175720833](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801175720833.png)

![image-20200801180314145](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801180314145.png)

awk打印倒数第一，倒数第二列字段

```
cat nginx.log | awk '{print $(NF),$(NF-1)}'
# $(NF)表示倒数第一行，$(NF-1)表示倒数第二行
```

awk词典进行分类汇总

![image-20201207213336341](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201207213336341.png)

```
cat test.txt | awk '{d[$1]+=$2} END{for(k in d) print k,d[k]}'
# d[$1]在这里分别对应d[a],d[b]
```

结果如下：

​	![image-20201207213853704](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201207213853704.png)

练习：

1.打印/etc/passwd文件中的包含’root‘关键字的所有内容

- 1.先cat查看相关文件内容的格式

  ![image-20200921205832243](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200921205832243.png)

- 2.通过查看文件内容我们发现，文件每行是以’:‘为分割符的，所以我们需要使用-F参数指定以”:“来对每一行进行切片

  ```
  awk -F : '/root/ {print $0}' /etc/passwd
  注意：$0表示每行切片后的整条记录，$1表示切片后的第一段内容
  ```

  ![image-20200921211338057](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200921211338057.png)

2.打印/etc/passwd文件中的包含’root‘关键字的所以记录的shell内容

- 1.通过查看文件内容，我们知道记录中的shell内容对应每行切片后的第七段内容

  

  ![image-20200921210906885](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200921210906885.png)

- 2.我们可以通过打印$7来实现只显示shell内容

- ```
  awk -F : '/root/ {print $7}' /etc/passwd
  ```

  ![image-20200921211406567](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200921211406567.png)

3..打印/etc/passwd文件的第二行的所有内容

- 1.使用参数NR来匹配需要的行数

- ```
  awk -F : 'NR==2 {print $0}' /etc/passwd
  ```

  ![image-20200921211754240](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200921211754240.png)

4.使用begin加入标题，并且打印所有记录的第一，第二片段内容

- ```
  awk -F : 'BEGIN{print "start"} {print $1,$2}' /etc/passwd
  ```

  ![image-20200921212824172](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200921212824172.png)

5.使用awk进行分段匹配

```
awk -F : '$9~/root/ {print $0}'------匹配第九段内容含root的记录
```



### 5.Linux进阶命令

##### 1.curl命令

- **curl定义：curl是向服务器发送请求的一个命令，https://curl.haxx.se/为curl官网**

- **crul用法：**

  - **sudo apt install curl--------:ubuntu中安装curl**
  - **curl -h：获取帮助信息**
  - **curl url地址-------------------：获取对应网址的文本信息**

  ```
  #获取www.baidu.com的文本信息
  curl www.baidu.com
  ```

  - **curl -i url地址-------------：获取该网址的文本信息以及协议头部信息**

  ```
  curl -i www.baidu.com
  ```

  ![image-20200924215426482](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200924215426482.png)

  - **curl -x proxy url地址---------使用代理获取网页文本信息**（可以配合代理服务器charles使用）

  ```
  #使用代理访问百度
  curl -x 127.0.0.1:8080 www.baidu.com
  ```

  - **默认的curl都是以gei请求访问网页，使用post请求：curl -X POST url地址**

  ```
  curl -X POST www.baidu.com
  ```

  - **携带参数以post方式访问网页：curl -d 参数 url地址**

  ```
  curl -d 'login=1234' https://www.baidu.com
  ```

  - **curl -o tmp.html url地址---------：获取网页文本信息，并保存在tmp.html文件中**

  ```
  curl -o tmp.html www.baidu.com
  ```

  - **curl -s url地址------------------------------：过滤掉错误和进度信息**

  ```
  curl -s www.baidu.com
  ```

- **curl实战：使用curl配合Charles实现，使用代理访问百度网址**

  - 1.安装Charles





##### 2.jq

- jq：jq是用户对json数据进行优化的命令

- jq常用命令：

  - jq '.'--------对json数据进行格式优化

  ```
  
  ```

  

![image-20200801212612831](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801212612831.png)

![image-20200801212653619](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801212653619.png)

![image-20200801212807837](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801212807837.png)

![image-20200801212847377](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801212847377.png)

### 6.bash

##### 1.变量

- 命名规则
  - 变量命名只能使用字母数字和下划线，且不能以数字开头
  - 不能使用bash的关键字
- 定义变量：变量名=值

```
your_name='ouyi'
注意;bash中严格控制空格，不能多不能少
```

- 使用变量：$变量名

```
echo $your_name
```

- 设置只读变量（不能修改删除）：readonly  变量名

```
a='cnm'
readonly a
```

- 删除变量：unset 变量名

```
unset your_name
```

- 变量类型：

  - 字符串

    - 字符串基本使用

    ```bash
    your_name='ouyi'
    ```

    - 拼接字符串：使用单引号或双引号拼接

    ```bash
    your_name='ouyi'
    echo 'hello '$your_name'!'
    结果：hello ouyi!
    ```

  - 数组

    - 定义数组变量：变量名=（value0 value1 .。。。）

    ```bash
    list_a=(1 2 3 a b c)
    注意：元素之间以空格分隔
    ```

    - 使用数组：${变量名[下标]}

    ```bash
    echo ${list_a[2]}
    注意：下标为*表示整个数组
    ```

    - 修改数组：变量名[下标]=新值

    ```
    list_a[0]='haha'
    ```

    

##### 2。控制语句

- if

  - 格式：

  ```
  if [ 条件 ];then 代码块;elif [ 条件 ];then 代码块;else 代码块;fi
  ```

  - ​	实战：

  ```bash
  a=10
  b=20
  if [ $a -eq $b ];then echo '相等';elif [ $a -gt $b ];then echo '大于';else echo '小于';fi
  ```

- ##### for 循环

  - 格式：

  ```
  for var in 元组;do 代码块;done
  ```

  - 实战1：

  ```
  list_a=(1,2,3,a,b,'c','d')
  for i in $list_a;do echo $i;done
  ```

  - 实战2：使用for循环读取文件内容，并打印到屏幕上

  ```bash
  vi test.txt
  for i in $(cat test.txt);do echo $i;done
  注意：使用cat可以读取文件内容
  ```

- ##### while循环

  - 格式

  ```
  while 条件;do 代码块；done
  ```

  - 实战1

  ```
  
  ```

  



![image-20200801203326017](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801203326017.png)

### 7.bash脚本的编写

![image-20200801203613398](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801203613398.png)

![image-20200801203729309](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801203729309.png)

![image-20200801203857381](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801203857381.png)

![image-20200801203919162](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801203919162.png)

![image-20200801204118447](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801204118447.png)

![image-20200801204146485](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801204146485.png)

![image-20200801204241073](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801204241073.png)

![image-20200801204316233](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200801204316233.png)

```
#!/bin/bash
mkdir haha
cd haha
echo "hello">hah.sh
cat hah.sh
```

- 实战：

  - read实战

  ![image-20200923210300862](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200923210300862.png)

  ![image-20200923210458691](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200923210458691.png)

  - 脚本参数传递实战

    - 先编辑sh脚本文件

    ![image-20200923211912786](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200923211912786.png)

    - 在终端运行脚本文件

    ![image-20200923212111678](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200923212111678.png)

  - shell脚本实现基本运算实战
    - 先编辑sh脚本

    ![image-20200923213437611](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200923213437611.png)

    - 在终端运行脚本

    ![image-20200923213512855](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200923213512855.png)

  - shell脚本创建目录，文件实战

    - 先编辑shell脚本

    ![image-20200923214108076](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200923214108076.png)

    - 在终端运行脚本

    ![image-20200923214145393](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200923214145393.png)

  



### 8.cgi技术

#### （1）cgi技术简介：

公共网关接口bai（Common Gateway Interface，CGI）是Web 服务器运行时外部程du序zhi的规范，按CGI 编写的程序可以扩dao展服务器功能。

CGI 应用程序能与浏览器进行交互，还可通过数据API与数据库服务器等外部数据源进行通信，从数据库服务器中获取数据。格式化为HTML文档后，发送给浏览器，也可以将从浏览器获得的数据放到数据库中。

cgi技术主要用于：当我们访问浏览器时，需要在后台执行一些脚本。这时我们就需要遵守cgi规则。

#### （2）环境搭建

- 一台linux服务器，在其上安装nginx和fcgiwrap。（浏览器和cgi交互需要借助web服务器nginx）

- 第一步：设置开源网址，因为Linux默认的源中，没有nginx和fcgiwrap。

  - ```
    查看linux版本，本次使用 7.7
    cat /etc/redhat-release
    ```

  - ```
    设置开源网址（这里使用阿里云源）
    curl -o /etc/yum.repos.d/epel.repo http://mirrors.aliyun.com/repo/epel-7.repo
    参数解析：访问http://mirrors.aliyun.com/repo/epel-7.repo网址，并将阿里云源（epel.repo）放置在/etc/yum.repos.d/epel.repo目录下。可以使用cd /etc/yum.repos.d/epel.repo查看是否成功
    ```

- 第二步：安装nginx和fcgiwrap

  - ```
    centos下安装
    yum install -y nginx fcgiwrap
    ubuntu下安装
    apt install -y nginx fcgiwrap
    ```

    

- 第三步：启动fcgiwrap服务

  - 方式一：通过访问fcgiwrap.socket文件启动（主要用于nginx fcgiwrap布置在一台服务器上时）

    - ```
      启动fcgiwrap服务
      nohup fcgiwrap -f -c 4 -s unix:/run/fcgiwrap.socket &
      参数解析：
      nohup &-----表示在后台运行服务
      -f----------表示当fcgiwrap出错时，fcgiwrap会发送对应的错误信息到对应的web服务器（nginx）
      -c----------指定启动的进程数
      -s----------指定socket文件的放置位置
      启动后我们可以使用ps -ef | grep fcgiwrap命令，查看对应进程是否启动成功
      ```

  - 方式二：通过访问指定的tcp服务来启动（主要用于nginx fcgiwrap布置在不同的服务器上时）

    - ```
      nohup fcgiwrap -f -c 4 -s tcp:ip地址：端口号 &
      ```

- 第四步：启动nginx服务器

  - 创建项目目录

    - ```
      mkdir -p /data/nginx/test_cgi/cgi/
      解析：
      /data/nginx/test_cgi/为我们的项目目录，可以自己更改
      cgi/目录名字不能改
      ```

  - 更改nginx的配置文件

    - 在/etc/nginx目录下有nginx的各种配置文件，其中 nginx.conf就是nginx的默认配置文件。我们一般不更改

    - ![image-20200928214224145](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200928214224145.png)

    - 我们在/etc/nginx/conf.d目录下新建一个nginx的配置文件

      - ```
        cd /etc/nginx/conf.d
        vi test_cgi.conf
        ```

        ![image-20200928220759627](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200928220759627.png)

  - 重启nginx服务

    - ```命令
      systemctl restart nginx
      重启后可以使用命令ps -ef | grep nginx查看对应进程是否启动
      还可以使用ss -antl命令，查看系统是否有监听8080端口
      ```

  - 使用浏览器访问：http://本地ip:8080/cgi/  来检测nginx是否配置ok

    - 第一次访问时，报502错误，因为nginx是通过/run/fcgiwrap.socket文件来于fcgiwrap交互的，所以可能是因为fcgiwrap.socket文件的权限不够，没有执行socket文件。导致报错。

      - ![image-20200928221744197](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200928221744197.png)

      - ![image-20200928222412123](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200928222412123.png)

      - 通过查看/etc/nginx/nginx.conf文件，发现nginx启动时是使用nginx用户来启动的

      - ![image-20200928222716458](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200928222716458.png)

      - 所以我们将/run/fcgiwrap.socket文件的属主更换为nginx用户

        - ```
           chown nginx:nginx /run/fcgiwrap.socket
          ```

    - 第二次访问浏览器时，会报403错误。因为我们配置nginx配置文件test_cgi.conf时，设置的当访问/cgi/地址时，会读取index.cgi文件。但我们现在还没有编写对应的文件。

  - 编写index.cgi脚本文件

    - 一般在index.cgi的文件中，我们不写具体的功能，而是用该脚本去加载其他脚本，调用其他脚本中的函数。
      - ![image-20200929215918433](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200929215918433.png)

  - 编写cgi.sh脚本，在该脚本中编写具体的功能函数

    - ![image-20200929221656722](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200929221656722.png)

  - 使用浏览器去访问，检验脚本

    - 使用curl命令去访问：

      - ```
         curl 'http://192.168.76.129:8080/cgi/' -X POST -d 'user_id=123&msg="ok!"'
         解析： 
         -X -----表示请求的方式
         -d------表示发送的内容
        ```

        ![image-20200929222237968](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200929222237968.png)

      - ```
        curl 'http://192.168.76.129:8080/cgi/?a=1' -X GET
        ```

        ![image-20200929222708676](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20200929222708676.png)

- 这样cgi+nginx服务器的环境就搭建完毕了。

### 9.Linux三剑客实战

#### （1）实战1：查找nginx.log日志文件中，404和500的报错的信息。以及报错的总行数

- 分析查看nginx.log日志文件内容，我们发现每条记录的状态码格式为数字且前后都有空格，状态码的位置按照空格作为域分隔符，位于第9段。

![image-20201001235906896](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201001235906896.png)

- 使用grep命令来实现

  - ```shell
    方法一：
    （1）查看404和500的报错信息
    grep -E '\s404\s|\s500\s' nginx.log
    参数解析：
    -E：因为grep不支持扩展正则，这里要使用带’或‘的正则表达式，所以必须加上-E参数
    （2）统计404和500报错信息的总记录数
    grep -E '\s404\s|\s500\s' nginx.log | wc -l
    参数解析：
    wc -l ： 用户输出查找到的记录总数
    方法二：
    （1）查看404和500的报错信息
    cat nginx.log | grep -E '\s404\s|\s500\s'
    （2）统计404和500报错信息的总记录数
    cat nginx.log | grep -E '\s404\s|\s500\s' | wc -l
    ```

- 所以awk命令实现

  - ```shell
    方法一：
    （1）查看404和500的报错信息
    awk '/\s404\s|\s500\s/ {print$0}' nginx.log
    解析：
    因为awk默认就是以空格作为域分隔符，所以不需要指定-F参数
    （2）统计404和500报错信息的总记录数
    awk '/\s404\s|\s500\s/ {print$0}' nginx.log | wc -l
    方法二：
    （1）查看404和500的报错信息
    cat nginx.log | awk '$9~/404|500/ {print$0}'
    参数解析：
    $9~/404|500/ ： 表示使用第九列的内容去匹配后面的正则表达式
    （2）统计404和500报错信息的总记录数
    cat nginx.log | awk '$9~/404|500/ {print$0}' | wc -l
    ```

#### (2)实战2：找出日志中出现次数最多的前三个ip

- 分析查看nginx.log日志文件内容，我们发现ip地址的位置为每条记录的开头
  
- ![image-20201001235906896](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201001235906896.png)
  
- 实现步骤一：使用awk单独提取出ip地址

  - ```shell
    awk '{print$1}' nginx.log
    ```

- 实现步骤二：进行排序

  - ```shell
    awk '{print$1}' nginx.log | sort
    参数解析：
    sort ： 排序
    ```

- 实现步骤三：相同的ip地址合并

  - ```shell
    awk '{print$1}' nginx.log | sort | uniq -c
    参数解析：
    uniq : 将相同的记录合并，加上参数’-c‘可以显示出合并前该内容出现的次数
    ```

  - ![image-20201002005053481](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201002005053481.png)

- 实现步骤四：在进行一次排序，

  - ```shell
    awk '{print$1}' nginx.log | sort | uniq -c | sort  -nr
    参数解析：
    sort  -nr ： sort排序默认是字典序且默认为升序，加上参数’-n‘表示按照数字大小排序，加上参数’-r‘表示按照降序排列
    ```

- 实现步骤四：取前三条记录

  - ```shell
    awk '{print$1}' nginx.log | sort | uniq -c | sort  -nr | head -3
    参数解析：
    head -3 ： 表示取出前三条数据
    也可以使用命令：
    awk '{print$1}' nginx.log | sort | uniq -c | sort  -nr | awk 'NR<=3 {print$0}'
    ```

#### （3）实战3：全局替换

将nginx.log日志文件中的’/topics/‘后面的数字替换为number字符串

- 分析查看nginx.log日志文件内容，我们发现/topics/后面的内容是变化的数字
  
- ![image-20201001235906896](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201001235906896.png)
  
- 使用sed实现全局替换

  - ```shell
    sed -e 's#/topics/[0-9]*#/topics/number#g' nginx.log
    参数解析：
    # ： 在sed中用于分隔替换前后字符的标识不一定是’/‘，也可以是其他符号，这里使用#
    ```

    

#### （4）实战4：ip横排

我们如果用awk提取的ip地址，是没有在同一行的，如果我们要实现把所有的ip地址放在同一行怎么实现呢？

- 我们知道，换行是因为末尾有一个换行符，那么我们把换行符换位其他字符是否就可以了呢

  - ```shell
    awk '{print$1}' nginx.log | sed 's/\n/ /g' 
    结果并没有变为一行，因为sed在处理每一行时，并没有读取到换行符
    ```

  - ![image-20201002013127632](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201002013127632.png)

- 优化代码,在sed中加入N参数，将后面一行内容追加到前一行中

  - ```shell
    awk '{print$1}' nginx.log | sed 'N;s/\n/ /g' 
    结果：只是把两行内容合并了，因为每一行中，追加操作只执行了一次
    ```

  - ![image-20201002013544234](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201002013544234.png)

- 再次优化代码：

  - ```shell
    awk '{print$1}' nginx.log | sed ':2;N;s/\n/ /g;t2' 
    结果成功了。
    解析:
    :2 ---表示创建一个标记2（可以是其他数字）
    t2 ---表示跳转到标记2
    ```

    ![image-20201002014053768](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201002014053768.png)



### 10.Linux性能统计分析

#### （1）linux常用的性能分析命令

![image-20201002023042256](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201002023042256.png)

#### （2）总体态势：uptime

uptime用于查看操作系统的总体态势：返回四个值：当前时间、系统运行了多久时间、当前登录的用户有多少，以及前 1、5 和 15 分钟系统的平均负载。

![image-20201002024327463](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201002024327463.png)

这里，第一项是当前时间，up 表示系统正在运行，5:53 是系统启动的总时间，最后是系统的负载load信息

什么叫负载load：系统负载是处于可运行runnable或不可中断uninterruptable状态的进程的平均数。可运行状态的进程要么正在使用 CPU 要么在等待使用 CPU。 不可中断状态的进程则正在等待某些 I/O 访问，例如等待磁盘 IO。负载均值的意义根据系统中 CPU 的数量不同而不同，负载为 1 对于一个只有单 CPU 的系统来说意味着负载满了，而对于一个拥有 4 CPU 的系统来说则意味着 75% 的时间里都是空闲的。

平均负载分析：一般情况下单核cpu平均负载不大于3，表示性能良好。n核cpu，平均负载不大于n*3，表示性能良好。

#### （3）操作系统日志：dmesg

应用场景：一般在系统性能发生卡顿等问题时，使用dmesg命令查看系统日志

#### （4）虚拟内存统计：vmstat

（4.1）简介

vmstat是Virtual Meomory Statistics（虚拟内存统计）的缩写，可对操作系统的虚拟内存、进程、CPU活动进行监控。是对系统的整体情况进行统计，不足之处是无法对某个进程进行深入分析。

（4.2）物理内存和虚拟内存区别

​		我们知道，直接从物理内存读写数据要比从硬盘读写数据要快的多，因此，我们希望所有数据的读取和写入都在内存完成，而内存是有限的，这样就引出了物理内存与虚拟内存的概念。

  		物理内存就是系统硬件提供的内存大小，是真正的内存，相对于物理内存，在linux下还有一个虚拟内存的概念，虚拟内存就是为了满足物理内存的不足而提出的策略，它是利用磁盘空间虚拟出的一块逻辑内存，用作虚拟内存的磁盘空间被称为交换空间（**Swap Space**）。

  		作为物理内存的扩展，linux会在物理内存不足时，使用交换分区的虚拟内存，更详细的说，就是内核会将暂时不用的内存块信息写到交换空间，这样以来，物理内存得到了释放，这块内存就可以用于其它目的，当需要用到原始的内容时，这些信息会被重新从交换空间读入物理内存。

（5）虚拟内存原理

​		在系统中运行的每个进程都需要使用到内存，但不是每个进程都需要每时每刻使用系统分配的内存空间。当系统运行所需内存超过实际的物理内存，内核会释放某些进程所占用但未使用的部分或所有物理内存，将这部分资料存储在磁盘上直到进程下一次调用，并将释放出的内存提供给有需要的进程使用。

  在Linux内存管理中，主要是通过“调页Paging”和“交换Swapping”来完成上述的内存调度。调页算法是将内存中最近不常使用的页面换到磁盘上，把活动页面保留在内存中供进程使用。交换技术是将整个进程，而不是部分页面，全部交换到磁盘上。

  分页(Page)写入磁盘的过程被称作Page-Out，分页(Page)从磁盘重新回到内存的过程被称作Page-In。当内核需要一个分页时，但发现此分页不在物理内存中(因为已经被Page-Out了)，此时就发生了分页错误（Page Fault）。

  当系统内核发现可运行内存变少时，就会通过Page-Out来释放一部分物理内存。尽管Page-Out不是经常发生，但是如果Page-out频繁不断的发生，直到当内核管理分页的时间超过运行程式的时间时，系统效能会急剧下降。这时的系统已经运行非常慢或进入暂停状态，这种状态亦被称作thrashing(颠簸)。

（6）常见命令展示

```
vmstat 5 5 【在5秒时间内进行5次采样】
```

![image-20201002032045362](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201002032045362.png)

参数解析：

Procs（进程）：

>  r: 运行队列中进程数量
>
>  b： 等待IO的进程数量

Memory（内存）：

>  swpd: 使用虚拟内存大小
>
>  free: 可用内存大小
>
>  buff: 用作缓冲的内存大小
>
>  cache: 用作缓存的内存大小

Swap：

 si: 每秒从交换区写到内存的大小（每秒进入磁盘交换器的大小）

>  so: 每秒写入交换区的内存大小（每秒从磁盘交换区出来的大小）

IO：（现在的Linux版本块的大小为1024bytes）

>  bi: 每秒读取的块数
>
>  bo: 每秒写入的块数

系统：

> in: 每秒中断数，包括时钟中断。【interrupt】（比如，当cpu满负载时，你移动鼠标，cpu会中断一些进程，来响应你的鼠标移动。）
>
> cs: 每秒上下文切换数。    【count/second】

CPU（以百分比表示）：

>  us: 用户进程执行时间占用cpu的百分比(user time)
>
>  sy: 系统进程执行时间占用cpu的百分比(system time)
>
>  id: 空闲时间(包括IO等待时间),中央处理器的空闲时间 。以百分比表示。
>
>  wa: 等待IO时间

（7）实战：编写一个bash脚本，不断创建进程。然后使用vmstat查看

- 第一步，编写bash脚本

  - ```
    vi test.sh
    ```

    ![image-20201002045053833](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201002045053833.png)

  - ```
    chmod +x ./test.sh
    ./test.sh
    ```

- 第二步：使用vmstat查看

  - ![image-20201002045233898](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201002045233898.png)

  可以看到r运行队列数一直在50以上

- 第三步：查看进程列表
  
- ![image-20201002045424949](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201002045424949.png)
  
- 第四步：杀掉相关进程

  - ```shell
    ps -ef | grep test.sh | awk 'kill_sh="kill -9 "$2;system(kill_sh)'
    参数解析：
    ps -ef | grep test.sh----先找出test.sh对应的进程
    awk 'kill_sh="kill -9 "$2;system(kill_sh)'-------使用awk执行shell命令。方法：将命令赋值给变量，然后使用system参数去执行变量
    ```

#### （5）io情况：iostat

列出磁盘io的情况

![image-20201123201642205](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201123201642205.png)

tps：该设备每秒的传输次数

kB_read/s：每秒从设备（drive expressed）读取的数据量；

kB_wrtn/s：每秒向设备（drive expressed）写入的数据量；

kB_read： 读取的总数据量；

kB_wrtn：写入的总数量数据量；

其他参数：

​		1：iostat 1--------每1秒刷新一次

​		2：iostat -c-------只查看cpu的io情况

​		3：iostat -d------只查看磁盘的io情况

#### （6）内存情况：free -m

​	free -m 查看linux内存使用情况。

![image-20201002051556457](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201002051556457.png)

一、从系统层面分析

  Mem:内存的使用情况总览表。

  totel:机器总的物理内存 单位为：M

  used：用掉的内存。

  free:空闲的物理内存。

注：物理内存(totel)=系统看到的用掉的内存(used)+系统看到空闲的内存(free)

   我们平时看内存的使用也就看这些。

二、从程序的角度分析

  shared:多个进程共享的内存总和，当前废弃不用。

  buffers：缓存内存数（写入磁盘时）。

  cached:  缓存内存数（从磁盘读取时）。

  注：程序预留的内存=buffers+cached

#### （7）进程详情：top

inux中的top命令显示系统上正在运行的进程。它是系统管理员最重要的工具之一。被广泛用于监视服务器的负载。

![image-20201002052216535](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201002052216535.png)

##### 命令详解：

（1）top命令的顶部显示与uptime命令相似的输出。

![image-20201002052335770](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201002052335770.png)

这些字段显示：

- 当前时间
- 系统已运行的时间
- 当前登录用户的数量
- 相应最近5、10和15分钟内的平均负载。

（2）任务

![image-20201002052559837](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201002052559837.png)

第二行显示的是任务或者进程的总结。进程可以处于不同的状态。这里显示了全部进程的数量。除此之外，还有正在运行、睡眠、停止、僵尸进程的数量（僵尸是一种进程的状态）。这些进程概括信息可以用’t’切换显示。

（3）cpu状态

![image-20201002052751968](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201002052751968.png)

第三行显示的是CPU状态。 这里显示了不同模式下的所占CPU时间的百分比。这些不同的CPU时间表示:

- us, user： 运行(未调整优先级的) 用户进程的CPU时间
- sy，system: 运行内核进程的CPU时间
- ni，niced：运行已调整优先级的用户进程的CPU时间
- id: 空闲时间(包括IO等待时间),中央处理器的空闲时间
- wa，IO wait: 用于等待IO完成的CPU时间
- hi：处理硬件中断的CPU时间
- si: 处理软件中断的CPU时间
- st：这个虚拟机被hypervisor偷去的CPU时间（译注：如果当前处于一个hypervisor下的vm，实际上hypervisor也是要消耗一部分CPU处理时间的）。

可以使用’t’命令切换显示。

（4）内存使用:

![image-20201002053054571](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201002053054571.png)

第四五两行显示内存使用率，有点像’free’命令。第一行是物理内存使用，第二行是虚拟内存使用(交换空间)。

物理内存显示如下:全部可用内存、已使用内存、空闲内存、缓冲内存。相似地：交换部分显示的是：全部、已使用、空闲和缓冲交换空间。

（5）字段/列

![image-20201002053244672](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201002053244672.png)

**PID**

进程ID，进程的唯一标识符

**USER**

进程所有者的实际用户名。

**PR**

进程的调度优先级。这个字段的一些值是’rt’。这意味这这些进程运行在实时态。

**NI**

进程的nice值（优先级）。越小的值意味着越高的优先级。

**VIRT**

进程使用的虚拟内存。

**RES**

驻留内存大小。驻留内存是任务使用的非交换物理内存大小。

**SHR**

SHR是进程使用的共享内存。

**S**

这个是进程的状态。它有以下不同的值:

- D – 不可中断的睡眠态。
- R – 运行态
- S – 睡眠态
- T – 被跟踪或已停止
- Z – 僵尸态

**%CPU**

自从上一次更新时到现在任务所使用的CPU时间百分比。

**%MEM**

进程使用的可用物理内存百分比。

**TIME+**

任务启动后到现在所使用的全部CPU时间，精确到百分之一秒。

**COMMAND**

运行进程所使用的命令。

还有许多在默认情况下不会显示的输出，它们可以显示进程的页错误、有效组和组ID和其他更多的信息。

##### 交互命令:

top -h：帮助信息

top -n ：获取多次cpu的执行情况 ，top –n 4 只更新4次（默认是不断更新的）

top -d ： 间隔时间，top -d 4 每隔4秒更新一次

top -p ： 获取指定pid的进程的数据，top –p 4444(PID)

##### top命令实战：

- 检测指定pid的内存20次

  - ```shell
    for i in {1..20};do top -n 1 -p 1 | grep systemd | awk '{print $11}';done
    解析：
    top -n 1 -p 1------打印pid为1的进程信息一次
    grep systemd-------取出含systemd内容的记录，也就是进程信息那一条记录
    awk '{print $11}'--打印字段11，也就是内存信息
    ```

#### （8）iftop分析网络状态

![image-20201123203210229](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201123203210229.png)

#### （9）性能分析总结

当我们遇到系统性能很差时，可以分别查看系统的CPU,内存,IO,网络流量来排查到底哪里出问题了

### 11.linux统计命令

#### （1）sort排序

![image-20201123204105648](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201123204105648.png)

练习：

![image-20201123210525281](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201123210525281.png)

![image-20201123211119471](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201123211119471.png)

#### （2）去重，uniq

![image-20201123211344545](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201123211344545.png)

注意：因为uniq只会对相邻的行进行比较，所以我们往往先使用sort排序后，再使用uniq来去重

练习：

![image-20201123212032553](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201123212032553.png)

![image-20201123212604218](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201123212604218.png)

#### （3）wc统计文本

![image-20201123213247578](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201123213247578.png)

练习：

![image-20201123213518638](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201123213518638.png)

注意：空白行也会算成一行，空格，换行符，空行会被算成一个字符

### 12.bash脚本实战：抽奖小程序

#### （1）需求：

从文件中读取名单，然后选择n名同学中奖

#### （2）前期准备：名单文件

编写一个txt文件，里面记录对应同学的姓名

![image-20201003004550341](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201003004550341.png)



#### （3）bash脚本编写

- **基本实现从txt文件中读取姓名**

  - ```
    vi lottery.sh
    ```

    ![image-20201003010347658](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201003010347658.png)

  - ```
    执行脚本检验
    chmod +x lottery.sh
    ```

    ![image-20201003010702619](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201003010702619.png)

- **实现提取的名字中含空格的bug，已经实现封装**

  - ```
    vi lottery.sh
    ```

    ![image-20201003011652256](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201003011652256.png)

  - ```
    执行脚本检验
    chmod +x lottery.sh
    ```

    ![image-20201003011730525](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201003011730525.png)

- **实现抽取一个中奖者的程序**

  - ```
    vi lottery.sh
    
    rand(){
    #从文件中读取所有人的姓名，并用‘.’代替空格
    local seeds=`while read line;do echo $line | sed -e 's/ /./g';done < tmp.txt`
    
    #从seeds中不停的删选，直到只剩一个同学为止
    local count=0
    while [[ $count != 1 ]];do
            #从seeds中选择取出一个姓名，进行猜拳操作
            seeds=`for seed in $seeds;do (($RANDOM%2)) && echo $seed;done`
            count=`echo "$seeds" | wc -l`
    done
    echo $seeds
    
    }
    rand
    ```

    ![image-20201003014918881](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201003014918881.png)

  - 循环执行脚本20次

    ![image-20201003021712875](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201003021712875.png)

  - 解决空白行的bug

  - ```
    rand(){
    #从文件中读取所有人的姓名，并用‘.’代替空格
    local seeds=`while read line;do echo $line | sed -e 's/ /./g';done < tmp.txt`
    
    #从seeds中不停的删选，直到只剩一个同学为止
    local count=0
    while [[ $count != 1 ]];do
            #从seeds中选择取出一个姓名，进行猜拳操作
            seeds=`for seed in $seeds;do (($RANDOM%2)) && echo $seed;done`
            count=`echo "$seeds" | wc -l`
    done
    
    #判断seeds是否为空白
    if [[ $seeds == '' ]];then
            rand
    else
            echo $seeds
    fi
    
    }
    rand
    ```

    ![image-20201003022328225](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201003022328225.png)

- **实现一次抽取多个中奖者**
  - ```
    rand(){
    #从文件中读取所有人的姓名，并用‘.’代替空格
    local seeds=`while read line;do echo $line | sed -e 's/ /./g';done < tmp.txt`
    
    #从seeds中不停的删选，直到只剩一个同学为止
    local count=0
    while [[ $count != 1 ]];do
            #从seeds中选择取出一个姓名，进行猜拳操作
            seeds=`for seed in $seeds;do (($RANDOM%2)) && echo $seed;done`
            count=`echo "$seeds" | wc -l`
    done
    
    #判断seeds是否为空白
    if [[ $seeds == '' ]];then
            rand
    else
            echo $seeds
    fi
    }
    
    #实现一次抽取多个中奖者
    res(){
    rgs=[]
    for((i=0;i<$1;i++));do
            rem=`rand`
            rgs[$i]=$rem
    done
    echo "${rgs[*]}"
    }
    res $1
    ```

    ![image-20201003031126177](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201003031126177.png)

  - 执行脚本文件，可以发现有重复现象。

    ![image-20201003031217591](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201003031217591.png)

- 实现中奖名单的去重

  - ```
    rand(){
    #从文件中读取所有人的姓名，并用‘.’代替空格
    local seeds=`while read line;do echo $line | sed -e 's/ /./g';done < tmp.txt`
    
    #从seeds中不停的删选，直到只剩一个同学为止
    local count=0
    while [[ $count != 1 ]];do
            #从seeds中选择取出一个姓名，进行猜拳操作
            seeds=`for seed in $seeds;do (($RANDOM%2)) && echo $seed;done`
            count=`echo "$seeds" | wc -l`
    done
    
    #判断seeds是否为空白
    if [[ $seeds == '' ]];then
            rand
    else
            echo $seeds
    fi
    
    
    
    }
    
    
    #实现一次抽取多个中奖者
    res(){
    rgs=[]
    for((i=0;i<$1;i++));do
            rem=`rand`
    
            #如果ags中已经有相同的rem，就不添加到rgs中，实现去重
            result=`echo "${rgs[*]}" | grep $rem`
            while [[ $result != '' ]];do
                    rem=`rand`
                    result=`echo "${rgs[*]}" | grep $rem`
            done
            rgs[$i]=$rem
    done
    echo "${rgs[*]}"
    }
    res $1
    ```

    ![image-20201003034047945](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201003034047945.png)

  - 再次执行脚本文件，已经没有重复项了

  ![image-20201003034205449](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201003034205449.png)

## 13.实战讲解

### 1.使用awk循环打印，获取每个字段的内容

在实际工作中，我们的每条记录可能非常复杂，使用肉眼去观察每个字段对应的内容，可能比较困难。我们可以使用awk循环打印，获取每个字段的内容

```
cat nginx.log | awk 'NR==1{for(k=1;k<=NF;k++){print k":"$k}}'
# NR==1表示只匹配第一行
# for(k=1;k<=NF;k++){print k":"$k}循环打印出每一列字段编号及内容
```

### 2.nginx日志分析实战

#### （1）取出最大的响应时间 max_response_time()

![image-20201207215317549](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201207215317549.png)

通过观察发现响应时间为倒数第二列字段

```
 max_response_time(){ cat nginx.log | awk '{print $(NF-1)}' | sort -n | tail -n 1; }
```

#### （2）取出top3的响应时间，并打印出对应的url max_response_time_and_url()

![image-20201208201738507](C:\Users\Administrator.DESKTOP-7PKNCLF\AppData\Roaming\Typora\typora-user-images\image-20201208201738507.png)

```
max_response_time_and_url(){ cat nginx.log | awk '{print $(NF-1),$7}' | sort -n | tail -n 3; }
```

#### （3）取出全部请求的平均响应时间 avg_response_time()

```
avg_response_time(){ cat nginx.log | awk  'BEGIN{sum=0}{sum+=$(NF-1)} END{print sum/NR}'; }
```

#### （4）取出所有相同url请求的平均响应时间，并且按照响应时间排序取出top 3 ,avg_response_time_by_url()

提示：使用awk词典完成分类汇总

```
avg_response_time_by_url(){ cat nginx.log | awk '{sum[$7]+=$(NF-1);count[$7]+=1} END{for(k in sum)print k,sum[k]/count[k]}'|sort -k 2 -nr | head -n 3; }

# awk '{sum[$7]+=$(NF-1);count[$7]+=1} ---sum分类汇总相同url对应的总的响应时间，count统计各url出现的次数
# END{for(k in sum)print k,sum[k]/count[k]} -----计算各url的平均响应时间
```

### 3.进程与网络实战

#### （1）每隔1s统计下aliyundun进程的cpu与mem，分类汇总下10s内的平均cpu与响应时间 

```
top -d 1 -n 10 | grep -i 'aliyundun' | awk '{sum_cpu[$13]+=$10;sum_mem[$13]+=$11;count_cpu[$13]+=1} END{for(k in sum_cpu)print k,sum_cpu[k]/count_cpu[k],sum_mem[k]/count_cpu[k]}'

# sum_cpu[$13]------分类汇总各aliyundun进程对应的cpu总和
# sum_mem[$13]------分类汇总aliyundun进程对应的mem总和
# count_cpu[$13]----统计各aliyundun进程出现的次数
```

#### （2）统计当前服务器上每个监听端口对应的网络状态的数量

```
netstat -tn | awk '{print $4}' | awk -F : '{print $2}' | sort | uniq -c
```

