



## liunx





###  1.liunx 文件

**本笔记使用的是 CentOS 7** 



​	` liunx 系统里面一切皆文件`



在centOS6中默认使用的文件格式是 ext4

在centOS7中默认使用的文件格式是xfs

电脑@名词后面

​					/ 表示在根目录上

​					~表示在/root目录下

​		[] 后面 

​						#表示管理员权限

​						$普通权限

```
[root@hadoop100 /]# cd /root
[root@hadoop100 ~]# ls
```

![image-20230321203131022](C:\Users\34912\Desktop\linux-study\imgs\image-20230321203131022.png)



- **/bin**：
  bin 是 Binaries (二进制文件) 的缩写, 这个目录存放着最经常使用的命令。

- **/boot：**
  这里存放的是启动 Linux 时使用的一些核心文件，包括一些连接文件以及镜像文件。

- **/dev ：**
  dev 是 Device(设备) 的缩写, 该目录下存放的是 Linux 的外部设备，在 Linux 中访问设备的方式和访问文件的方式是相同的。

- **/etc：**
  etc 是 Etcetera(等等) 的缩写,这个目录用来存放所有的系统管理所需要的配置文件和子目录。

- **/home**：
  用户的主目录，在 Linux 中，每个用户都有一个自己的目录，一般该目录名是以用户的账号命名的，如上图中的 alice、bob 和 eve。

- **/lib**：
  lib 是 Library(库) 的缩写这个目录里存放着系统最基本的动态连接共享库，其作用类似于 Windows 里的 DLL 文件。几乎所有的应用程序都需要用到这些共享库。

- **/lost+found**：
  这个目录一般情况下是空的，当系统非法关机后，这里就存放了一些文件。

- **/media**：
  linux 系统会自动识别一些设备，例如U盘、光驱等等，当识别后，Linux 会把识别的设备挂载到这个目录下。

- **/mnt**：
  系统提供该目录是为了让用户临时挂载别的文件系统的，我们可以将光驱挂载在 /mnt/ 上，然后进入该目录就可以查看光驱里的内容了。

- **/opt**：
  opt 是 optional(可选) 的缩写，这是给主机额外安装软件所摆放的目录。比如你安装一个ORACLE数据库则就可以放到这个目录下。默认是空的。

- **/proc**：
  proc 是 Processes(进程) 的缩写，/proc 是一种伪文件系统（也即虚拟文件系统），存储的是当前内核运行状态的一系列特殊文件，这个目录是一个虚拟的目录，它是系统内存的映射，我们可以通过直接访问这个目录来获取系统信息。
  这个目录的内容不在硬盘上而是在内存里，我们也可以直接修改里面的某些文件，比如可以通过下面的命令来屏蔽主机的ping命令，使别人无法ping你的机器：

- **/root**：
  该目录为系统管理员，也称作超级权限者的用户主目录。

- **/sbin**：
  s 就是 Super User 的意思，是 Superuser Binaries (超级用户的二进制文件) 的缩写，这里存放的是系统管理员使用的系统管理程序。

- **/selinux**：
   这个目录是 Redhat/CentOS 所特有的目录，Selinux 是一个安全机制，类似于 windows 的防火墙，但是这套机制比较复杂，这个目录就是存放selinux相关的文件的。

- **/srv**：
   该目录存放一些服务启动之后需要提取的数据。

- **/sys**：

  这是 Linux2.6 内核的一个很大的变化。该目录下安装了 2.6 内核中新出现的一个文件系统 sysfs 。

  sysfs 文件系统集成了下面3种文件系统的信息：针对进程信息的 proc 文件系统、针对设备的 devfs 文件系统以及针对伪终端的 devpts 文件系统。

  该文件系统是内核设备树的一个直观反映。

  当一个内核对象被创建的时候，对应的文件和目录也在内核对象子系统中被创建。

- **/tmp**：
  tmp 是 temporary(临时) 的缩写这个目录是用来存放一些临时文件的。

- **/usr**：
   usr 是 unix shared resources(共享资源) 的缩写，这是一个非常重要的目录，用户的很多应用程序和文件都放在这个目录下，类似于 windows 下的 program files 目录。

- **/usr/bin：**
  系统用户使用的应用程序。

- **/usr/sbin：**
  超级用户使用的比较高级的管理程序和系统守护程序。

- **/usr/src：**
  内核源代码默认的放置目录。

- **/var**：
  var 是 variable(变量) 的缩写，这个目录中存放着在不断扩充着的东西，我们习惯将那些经常被修改的目录放在这个目录下。包括各种日志文件。

- **/run**：
  是一个临时文件系统，存储系统启动以来的信息。当系统重启时，这个目录下的文件应该被删掉或清除。如果你的系统上有 /var/run 目录，应该让它指向 run。



在 Linux 系统中，有几个目录是比较重要的，平时需要注意不要误删除或者随意更改内部文件。

**/etc**： 上边也提到了，这个是系统中的配置文件，如果你更改了该目录下的某个文件可能会导致系统不能启动。

**/bin, /sbin, /usr/bin, /usr/sbin**: 这是系统预设的执行文件的放置目录，比如 **ls** 就是在 **/bin/ls** 目录下的。

值得提出的是 **/bin**、**/usr/bin** 是给系统用户使用的指令（除 root 外的通用用户），而/sbin, /usr/sbin 则是给 root 使用的指令。

**/var**： 这是一个非常重要的目录，系统上跑了很多程序，那么每个程序都会有相应的日志产生，而这些日志就被记录到这个目录下，具体在 /var/log 目录下，另外 mail 的预设放置也是在这里。





Linux常用指令

​			筛查

```
[root@hadoop111 sbin]#  ls | grep service
```



### 2. vi / vim文本编辑器



#### 2.1 什么是vi和vim

vi是Unix操作系统或者类Unix操作系统的文本编辑器

vim是编辑器是从vi发展出来的一个更强大的文本编辑器，可以主动的以字体颜色辨别语法的正确性，方便程序设计，vim和vi完全兼容



#### 2.2 模式之间的转化

一般模式：vim xxx 或者 vi xxx 进入文本 复制和粘贴

编辑模式： 先要在一般模式下 按 i 键进入编辑模式可以对文本进行编辑 按ESC可以退出

命令模式：  先要在一般模式下 输入：或者 /  进行一些对文本的命令操作 



##### 2.21进入编辑模式

|    i    | 当前光标位置之前插入数据（常用） |
| :-----: | :------------------------------: |
|    a    |   当前光标位置之后进入编辑模式   |
|    o    |     向下换行之后进入编辑模式     |
| shift+I |        在当前行头插入数据        |
| shift+A |        在当前行尾插入数据        |
| shift+O |     向上换行之后进入编辑模式     |





#### 2.3vim中常用指令

![view](C:\Users\34912\Desktop\linux-study\imgs\view.jpg)

##### 命令模式

###### ：W 

```
把缓存区的文字写入到文本中
```



###### ：q

```
退出
```



###### :wq

```
保存退出
```



###### :q!

 ```
不保存强行退出
 ```



###### / 输入查找的单词

```
n下一个单词  N上一个单词
:noh 取消高量
```



###### :set nu 显示行号

```
显示行号  关闭行号 :set nonu
```



###### 替换

​		先查找

|  :s/old/new   |    替换当前行匹配到的第一个old为new    |
| :-----------: | :------------------------------------: |
| :s/old/new/g  |         替换所有当前行old为new         |
|  :%s/old/new  | 替换文档中每一行匹配到的第一个old为new |
| :%s/old/new/g |            替换所有old为new            |



##### 一般模式

**操作区分大小写**

###### u

```
撤回操作
```



###### yy

```
复制光标的这一行
yy前面加数字可以复制几行

```

###### y+$

```
如果想复制光标后面的数据
```

###### y+^

```
复制光标前面的数据
```

###### w / b  选单词

```
通过w来选择下一个单词 选中单词的第一个字母
b选中上一个单词
```



###### d 选单词

```
选中单词的最后一个字母
```



###### y+w

```
复制当前光标后面的单词
最好通过w来选则单词
```





###### p

```
粘贴到光标对应的位置
p前面可以加数字可以复制多行
```



###### dd

```
删除当前行
dd前面加数字可以删除多行
```



###### d+w 删除一个单词

```
删除一个单词
```



###### d+方向键 删除一个字母

```
删除一个字母
```



###### x 剪贴

```
x 剪贴当前光标选中的字母 
如果下删除光标前面的字母 开启大写锁定 按X就是删除前面的
```



###### r / R可以替换

```
r选中光标并替换内容
R从光标选中一直往后替换
```



###### shift + ^ 光标跳转行头



###### shift + $ 光标跳转到行尾



###### 1 + G / gg 跳转到页头

```
1 + G注意大写G
```



###### G   跳转到页尾

```
注意大写G
```

###### 数字 +G 指定跳转行数



### 3.网络配置和系统管理操作



#### 3.1 查看IP和网关

win打开CMD

​             输入 ：ipconfig

```
C:\Users\34912> ipconfig
```

Linux

   		输入 ：ifconfig               (interfaceconfig)

```
[root@hadoop100 ~]# ifconfig
```

查看是否有网络链接

ping + IP地址

- 如果以上操作都无法ping通，需要关闭	NetworkManager服务
  - systemctl  stop  NetworkManager  关闭
  - systemctl  disable   NetworkManager   禁用



​      **VMware的三种网络链接方式**

- `桥接模式`

  ​		虚拟机直接连接外面物理网络模式，主机起到了网桥的作用，这种模式下虚拟机可以直接访问外部网络，**并且对外部网络是可见的。**



- ` NAT模式`

  ​		虚拟机和主机构建一个专用网络，并且通过虚拟网络地址转换（NAT）设备对IP进行转换。虚拟机通过共享主机IP可以访问外部网络，**但外部网络无法访问虚拟机**

  

- `仅主机模式`

  ​		虚拟机只与主机共享一个专用网络，**与外部网络无法通信**





#### 配置IP地址

```
[root@hadoop100 /]# vim /etc/sysconfig/network-scripts/ifcfg-ens33

```

打开之后：

```
SER_ONLY="no"
BOOTPROTO="dhcp"
DEFROUTE="yes"
IPV4_FAILURE_FATAL="no"
IPV6INIT="yes"
IPV6_AUTOCONF="yes"
IPV6_DEFROUTE="yes"
IPV6_FAILURE_FATAL="no"
IPV6_ADDR_GEN_MODE="stable-privacy"
NAME="ens33"
UUID="09b545b7-2b9f-473f-a204-11817fd09ad9"
DEVICE="ens33"
ONBOOT="yes"
```

变更方式

![image-20230330172437077](C:\Users\34912\Desktop\linux-study\imgs\image-20230330172437077.png)

```
YPE="Ethernet"
PROXY_METHOD="none"
BROWSER_ONLY="no"
BOOTPROTO="static"
DEFROUTE="yes"
IPV4_FAILURE_FATAL="no"
IPV6INIT="yes"
IPV6_AUTOCONF="yes"
IPV6_DEFROUTE="yes"
IPV6_FAILURE_FATAL="no"
IPV6_ADDR_GEN_MODE="stable-privacy"
NAME="ens33"
UUID="09b545b7-2b9f-473f-a204-11817fd09ad9"
DEVICE="ens33"
ONBOOT="yes"
#IP地址
IPADDR=192.168.206.100
#网关
GATEWAY=192.168.206.2
#域名解析器
DNS1=192.168.206.2
```

​	重启动网络配置

```
[root@hadoop100 /]# service network restart 
```



**怎么测试是否成功，可以去win下去ping一下**



#### 查看或者修改主机名称

##### 查看主机名称

```
oot@hadoop100 /]# hostname
```

更详细的查看

```
[root@hadoop111 ~]# hostnamectl
```



##### 修改主机名称

```
oot@hadoop100 /]# vim /etc/hostname
```

第二种修改主机名称的方式

```
doop100 /]# hostnamectl set-hostname hadoop111
```



#### 修改IP匿名信息

 		 `这个修改更像是电话薄 IP相当于电话  ，后面相当于名称`

Linux中修改IP信息

```
[root@hadoop111 ~]# vim /etc/hosts
```

打开后

​		192.168.206.100  hadoop100

​			原名   					别名

```
127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
::1         localhost localhost.localdomain localhost6 localhost6.localdomain6


192.168.206.100  hadoop100
192.168.206.100  hadoop101
192.168.206.100  hadoop102
192.168.206.100  hadoop103
192.168.206.100  hadoop104                                                                                                                                                    
```





win10中修改IP信息

​			根据下面目录打开hosts

```
C:\Windows\System32\drivers\etc
```



加入

```
192.168.206.100  hadoop100
192.168.206.100  hadoop101
192.168.206.100  hadoop102
192.168.206.100  hadoop103
192.168.206.100  hadoop104       
```



#### 远程登录

打开CMD

```
C:\Users\34912>ssh root@hadoop100

The authenticity of host 'hadoop100 (192.168.206.100)' can't be established.
ECDSA key fingerprint is SHA256:wWz/i1bI9uK5Q+fnuYWw7ga5P/pNalRLjyF8VePWHQc.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes

Warning: Permanently added 'hadoop100,192.168.206.100' (ECDSA) to the list of known hosts.
root@hadoop100's password:
Last login: Thu Mar 30 18:52:42 2023
[root@hadoop100 ~]# ls
anaconda-ks.cfg  initial-setup-ks.cfg  公共  模板  视频  图片  文档  下载  音乐  桌面
[root@hadoop100 ~]#
```



退出远程服务器

```
[root@hadoop100 ~]# exit
登出
```



#### Xshell 7 

操作基本一样

![image-20230331220735429](C:\Users\34912\Desktop\linux-study\imgs\image-20230331220735429.png)



设置简便操作



![image-20230331220828602](C:\Users\34912\Desktop\linux-study\imgs\image-20230331220828602.png)



#### Xftp 7

文件 -》当前会话-》选项 -》 编码 UTF-8

![image-20230331221352893](C:\Users\34912\Desktop\linux-study\imgs\image-20230331221352893.png)



### 4.系统管理

#### 4.1Linux的进程和服务



- 计算机中一个正在执行的程序或者命令，被叫做进程（process）。
- 启动之后一直存在，常驻在内存的进程，一般被叫做服务（service）。



#### 4.2 service服务管理

**小 tips**  **daemon（守护进程） 守护进程和服务是同一个意思  在Linux中服务后面都会加一个d**

- **CentOS 6** 的服务操作

  - 基础语法

    - service  服务名称 start / stop / restart / status

      

   	查看系统服务

```
[root@hadoop111 /]# ls /etc/init.d
functions  netconsole  network  README
```



#### 4.3systemctl （CentOS 7）

-  基础语法
  - systemctl   start / stop / restart / status   服务名称
- 经验技巧
  - 查看服务的方法 ：  /usr/lib/systemd/system

```linux
[root@hadoop100 /]# cd /usr/lib/systemd/system
[root@hadoop100 system]# pwd
/usr/lib/systemd/system
[root@hadoop100 system]# ls -al
总用量 1544
drwxr-xr-x. 27 root root 20480 3月  19 20:01 .
drwxr-xr-x. 13 root root  4096 3月  19 20:00 ..
-rw-r--r--.  1 root root   275 10月  2 2020 abrt-ccpp.service
-rw-r--r--.  1 root root   380 10月  2 2020 abrtd.service
-rw-r--r--.  1 root root   361 10月  2 2020 abrt-oops.service
-rw-r--r--.  1 root root   266 10月  2 2020 abrt-pstoreoops.service
-rw-r--r--.  1 root root   262 10月  2 2020 abrt-vmcore.service
-rw-r--r--.  1 root root   311 10月  2 2020 abrt-xorg.service
-rw-r--r--.  1 root root   729 4月   1 2020 accounts-daemon.service
-rw-r--r--.  1 root root   569 8月   6 2019 alsa-restore.service
-rw-r--r--.  1 root root   465 8月   6 2019 alsa-state.service
-rw-r--r--.  1 root root   682 10月  2 2020 anaconda-direct.service
-rw-r--r--.  1 root root   185 10月  2 2020 anaconda-nm-config.service
```



##### 服务自启动

```
[root@hadoop100 system]# setup
```



点击运行工具



![image-20230401110652039](C:\Users\34912\Desktop\linux-study\imgs\image-20230401110652039.png)



选中之后空格可以取消或者选中

![image-20230401110618130](C:\Users\34912\Desktop\linux-study\imgs\image-20230401110618130.png)



#### 4.4 系统运行级别



Linux系统有7个运行级别(runlevel)：

- 运行级别0：系统停机状态，系统默认运行级别不能设为0，否则不能正常启动
- 运行级别1：单用户工作状态，root权限，用于系统维护，禁止远程登录
- 运行级别2：多用户状态(没有NFS)
- 运行级别3：完全的多用户状态(有NFS)，登录后进入控制台命令行模式
- 运行级别4：系统未使用，保留
- 运行级别5：X11控制台，登录后进入图形GUI模式
- 运行级别6：系统正常关闭并重启，默认运行级别不能设为6，否则不能正常启动



##### CentOS 7 简化 运行级别

- multi-user.target: analogous to runlevel 3 (多用户有网，无图形界面)

- graphical.target: analogous to runlevel 5 (多用户有网，有图形界面）

  - 查看当前级别	

    ```
    [root@hadoop100 /]# systemctl get-default 
    graphical.target
    ```
    
  - 设置当前级别
  
  ```
  [root@hadoop100 /]# systemctl set-default TARGET.target (这里的TARGET 换成multi-user或者graphical)
  ```
  
  

查看运行级别文档书


```
[root@hadoop100 /]# vim /etc/inittab 
```



- 切换运行级别

  - 进入运行级别3  （大黑屏）

    - 和CTRL+ALT+F2 到 F6  一样的操作

    ```
    [root@hadoop100 /]# init 3
    ```

  - 进入运行级别5 （ui图像画界面）

    - 和CTRL+ALT+F1  一样的操作

    ```
    [root@hadoop100 /]# init 5
    ```

  

  ##### 4.5查看和管理服务级别

  可以通过 目录4.3下的服务自启动来开关

  ```
  [root@hadoop100 ~]# chkconfig --list
  
  注：该输出结果只显示 SysV 服务，并不包含
  原生 systemd 服务。SysV 配置数据
  可能被原生 systemd 配置覆盖。 
  
        要列出 systemd 服务，请执行 'systemctl list-unit-files'。
        查看在具体 target 启用的服务请执行
        'systemctl list-dependencies [target]'。
  
  netconsole     	0:关	1:关	2:关	3:关	4:关	5:关	6:关
  network        	0:关	1:关	2:开	3:开	4:开	5:开	6:关
  ```



###### 关闭或者打开所有权限



- chkconfig network off   关闭
- chkconfig network on  开启

```
[root@hadoop100 ~]# chkconfig network off
[root@hadoop100 ~]# chkconfig --list

注：该输出结果只显示 SysV 服务，并不包含
原生 systemd 服务。SysV 配置数据
可能被原生 systemd 配置覆盖。 

      要列出 systemd 服务，请执行 'systemctl list-unit-files'。
      查看在具体 target 启用的服务请执行
      'systemctl list-dependencies [target]'。

netconsole     	0:关	1:关	2:关	3:关	4:关	5:关	6:关
network        	0:关	1:关	2:关	3:关	4:关	5:关	6:关
[root@hadoop100 ~]# chkconfig network on
[root@hadoop100 ~]# chkconfig --list

注：该输出结果只显示 SysV 服务，并不包含
原生 systemd 服务。SysV 配置数据
可能被原生 systemd 配置覆盖。 

      要列出 systemd 服务，请执行 'systemctl list-unit-files'。
      查看在具体 target 启用的服务请执行
      'systemctl list-dependencies [target]'。

netconsole     	0:关	1:关	2:关	3:关	4:关	5:关	6:关
network        	0:关	1:关	2:开	3:开	4:开	5:开	6:关

```

###### 指定打开或关闭

- chkconfig --level 3 network off
- chkconfig --level 3 network on

```
[root@hadoop100 ~]# chkconfig --level 3 network off
```



###### 操作服务自启动



-  systemctl status NetworkManager
  - preset: enabled  预设开机自启动

```
[root@hadoop100 ~]# systemctl status NetworkManager
● NetworkManager.service - Network Manager
   Loaded: loaded (/usr/lib/systemd/system/NetworkManager.service; enabled; vendor preset: enabled)
   Active: active (running) since 六 2023-04-01 10:18:04 CST; 6h ago
     Docs: man:NetworkManager(8)
 Main PID: 768 (NetworkManager)
   CGroup: /system.slice/NetworkManager.service
           └─768 /usr/sbin/NetworkManager --no-daemon

```

- systemctl dsiable Network Manager   关闭开机自启动

```
[root@hadoop100 ~]# systemctl dsiable Network Manager
```





- systemctl list-unit-files     查看所有服务启动状态
  - status
    - static 静态 根据其它服务的启动来
    - disabled  开机不启动
    - enabled   开机启动

```
root@hadoop100 ~]# systemctl list-unit-files 

proc-sys-fs-binfmt_misc.mount                 static  
run-vmblock\x2dfuse.mount                     disabled
abrt-oops.service                             enabled 
```





###### 操作防火墙

- 查看防火墙状态
- Cent OS 6 的防火墙  iptables
- Cent OS 7 的防火墙  firewalld

```
[root@hadoop100 ~]# systemctl status firewalld
● firewalld.service - firewalld - dynamic firewall daemon
   Loaded: loaded (/usr/lib/systemd/system/firewalld.service; enabled; vendor preset: enabled)
   Active: active (running) since 六 2023-04-01 10:18:04 CST; 7h ago
     Docs: man:firewalld(1)
 Main PID: 730 (firewalld)
   CGroup: /system.slice/firewalld.service
           └─730 /usr/bin/python2 -Es /usr/sbin/firewalld --nofork --nopid

```



- 打开 关闭防火墙 
  -   systemctl stop firewalld
  - systemctl start firewalld

​				加不加.service 都是一样的

```
[root@hadoop100 ~]# systemctl stop firewalld.service 
[root@hadoop100 ~]# systemctl start firewalld.service 
```



- 打开 关闭 开机自启防火墙
  - systemctl disable firewalld  关闭开机自启
  - systemctl enable firewalld.service    关闭开机自启

```
[root@hadoop100 ~]# systemctl disable firewalld
[root@hadoop100 ~]# systemctl enable firewalld.service 
```



###### 关机重启

-  shutdown  关机默认一分钟后执行  
- shutdown -c 取消关机
- shutdown  now 现在关机
- shutdown  17.50 定时关机

```
[root@hadoop100 ~]# shutdown 
[root@hadoop100 ~]# shutdown -c
```



- 基本语法

1. sync														功能描述：将数据从内存同步到硬盘中
2. halt												         功能描述：停机，关系统， 但不断电
  3. poweroff										        功能描述：关机， 断电
4. reboot                                                    功能描述： 重启， 等同于 showdown -r now
  5. shutdown 【选项】  时间

| 选项 |        功能         |
| :--: | :-----------------: |
|  -h  |     相当于关机      |
|  -H  | 停机， 相当于--halt |
|  -r  |  -r = reboot  重启  |

| 时间 |               功能               |
| :--: | :------------------------------: |
| now  |             立刻关机             |
| 时间 | 等待多久关机后关机（单位是分钟） |



###  5.常用基本命令

Shell可以看作是一个命令解释器，为我们提供了交互式的文本控制台界面。我们可以通过终端控制台来输入命令，由shell进行解释并最终交给内核执行。本章就将分类介绍常用的基本shell命令。

#### 5.1 帮助命令

#####  5.1.1man获取帮助信息

- 基本语法
  - man[命令或配置文件]   						（功能描述：获得帮助信息）
  - man  man

```
[root@hadoop100 ~]# man shutdown
```



##### 5.1.2 help获取shell的内置命令的帮助信息

一部分基础功能的系统命令是直接内嵌在shell中的，系统加载启动之后会随着shell 一起加载，常驻系统内存中。这部分命令被称为“内置(built-in) 命令”;相应的其它命令被称为“外部命令”。

- 基本语法

  - help 命令											功能描述：获取shell内置命令和帮助信息
  - 命令 --help 										功能描述：获取帮助信息

- 案例实操

  - 查看cd命令的操作信息

  ```
  [root@hadoop100 ~]# help cd
  [root@hadoop100 ~]# cd --help 
  ```

或者

- 基本语法

  - type 命令                                              功能描述：判断是内嵌还是外部命令

- 案例实操

  - 查看cd的类型

  ```
  [root@hadoop100 ~]# type cd
  cd 是 shell 内嵌
  [root@hadoop100 ~]# type ls
  ls 是 `ls --color=auto' 的别名
  [root@hadoop100 ~]# 
  
  ```



##### 5.1.3查看操作历史记录

```
 [root@hadoop100 ~]# history 
```



##### 5.1.4常用快捷键

| 常用快捷键 |                   功能                    |
| :--------: | :---------------------------------------: |
|  CTRL + c  |                 停止进程                  |
|  CTRL + l  | 清屏幕， 等同于clear ，彻底清屏是： reset |
|    TAB     |         提示， 更重要的是防止敲错         |
|   上下键   |             查找执行过的命令              |
|            |                                           |
|            |                                           |



#### 5.2文件目录类

##### 5.2.1 pwd 显示工作目录的绝对路径

pwd -》 point working directory  打印工作目录

- 基本语法

  - pwd														详细信息：显示工作目录的绝对路径

- 案例实例

  - 显示工作目录的绝对路径

    ```
    [root@hadoop100 ~]# pwd
    /root
    ```

  - 相对路径     当前路径 /root/桌面

    - cd ../视频  							可以../代替/root

  - 绝对路径       绝对路径是以/根目录开始的

    - cd /root/桌面

  - cd - 来回跳转根目录和当前目录

##### 5.2.2 ls 列出目录的内容

ls -》  list   列出目录内容

- 基本语法

  - ls [选择]  [目录或者是文件]

- 选项说明

  | 选项 |                        功能                        |
  | :--: | :------------------------------------------------: |
  |  -a  |              显示全部文件包括隐藏文件              |
  |  -l  | 长数据串列出，包含文件的属性与权限等数据；等价于ll |



##### 5.2.3 创建或删除目录

- 创建目录

  - mkdir   目录名称  								无/就是在当前目录下创建
  - mkdir  /目录名称                                  根目录下创建
  - mkdir -p  /name/name                        可以创建多个目录

  ```
  [root@hadoop100 /]# mkdir -p /a/b/c
  [root@hadoop100 /]# ls /a/b/
  c
  
  ```

- 删除目录

  - rmdir    目录名称                                   如果该目录里面为空可以直接删除否则看下面
  - rmdir -p    /a/b/c                                  如果b里面和a里面没有其它目录那么直接删除a/b/c
    - 注意创建可以加上/根目录  删除不能带上根目录/

```
[root@hadoop100 /]# mkdir -p /a/b/c
[root@hadoop100 /]# ls
a  bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
[root@hadoop100 /]# rmdir -p a/b/c
[root@hadoop100 /]# ls
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var

```



##### 5.2.4 创建或删除文件

- 基本语法

  - touch   文件名称                                     可以不带后缀名称默认就是文本文件   touch（触摸）
  - 实际案例

  ```
  [root@hadoop100 wmt]# touch text.txt
  ```

  - vim    文件名称                                        也可以使用vim去创建文件 

  ```
  [root@hadoop100 wmt]# vim text.txt
  ```

  

##### 5.2.5 cp复制文件

- 基本语法

  -  cp 目标文件  路径                                     cp后面如果是目录直接复制，是文件就会覆盖
  - 实际案例

  ```
  [root@hadoop100 ~]# cp initial-setup-ks.cfg /wmt
  [root@hadoop100 /]# ls wmt
  initial-setup-ks.cfg  text.txt
  
  #覆盖
  [root@hadoop100 ~]# cp initial-setup-ks.cfg /wmt/text.txt
  cp：是否覆盖"/wmt/text.txt"？ y
  
  ```

  - 递归复制
  - cp -r 目标文件 路径                                       会复制该文件夹里面的所有的文件

  ```
  [root@hadoop100 /]# cp -r wmt /taget
  ```

  

查看别名 

```
[root@hadoop100 ~]# alias

```



##### 5.2.6 rm删除文件或目录

- 基本语法

  - rm [选择] deleteFile 
    - rm  -rf  /*      					入门到入狱
  - 选项说明白

  | 选项 |               功能               |
  | :--: | :------------------------------: |
  |  -r  |    递归删除目录里面的所有内容    |
  |  -f  | 强制删除操作，并且不提示是否删除 |
  |  -v  |           显示执行过程           |

  - 实际操作

  ```
  [root@hadoop100 /]# rm -r wmt02
  rm：是否进入目录"wmt02"? y
  rm：是否进入目录"wmt02/wmt"? y
  rm：是否删除普通文件 "wmt02/wmt/initial-setup-ks.cfg"？y
  rm：是否删除普通文件 "wmt02/wmt/text.txt"？y
  rm：是否进入目录"wmt02/wmt/wmt"? y
  rm：是否删除普通文件 "wmt02/wmt/wmt/initial-setup-ks.cfg"？y
  rm：是否删除普通文件 "wmt02/wmt/wmt/text.txt"？y
  rm：是否删除目录 "wmt02/wmt/wmt"？y
  rm：是否删除目录 "wmt02/wmt"？y
  rm：是否删除目录 "wmt02"？y
  [root@hadoop100 /]# 
  
  ```

  - rm   -f    ./*                                           ./* 解释  当前文件夹下的所有文件

  ```
  [root@hadoop100 wmt]# rm -f ./*
  ```

  



##### 5.2.7 mv移动文件与目录或重命名

- 基础操作

  - mv oldNameFlie 	newNanemFlie                                         重命名
  - mv   /temp/moveflie/targetFolder                                          移动

- 实际案例

  ```Linux
  #重命名
  [root@hadoop100 ~]# mv initial-setup-ks.cfg newNaem.cfg
  
  #移动
  [root@hadoop100 ~]# mv newNaem.cfg /wmt
  
  #移动并且重命名
  
  [root@hadoop100 ~]# mv newNaem.cfg /wmt/新的文件名
  ```



##### 5.2.8 cat查看文件内容

查看文件内容从第一行开始显示

- 基本语法

  - cat [选项]  要查看的文件

- 选项说明

  -  -n                                                          显示所有行包括空格行并且显示行号

- 案例实操

  ```
  
  [root@hadoop100 ~]# cat newNaem.cfg 
  
  [root@hadoop100 ~]# cat -n newNaem.cfg 
  
  ```



##### 5.2.9more 文件内容分屏查看器

more指令是一个基于VI编辑器的文本过滤器，它以全屏幕的方式按页显示文本文件白内容。more 指令中内置了若干快捷键，详见操作说明。



- 基本语法

  - more 要查看的文件

  - 操作说明

    |      操作       |              功能说明              |
    | :-------------: | :--------------------------------: |
    | space（空白键） |            代表向下翻页            |
    |      Enter      |            表示下翻一行            |
    |        q        | 代表立即离开more，不在显示文件内容 |
    |     CTRL+F      |            向下滚动一屏            |
    |     CTRL+B      |             返回上一屏             |
    |        =        |            输出当前行号            |
    |       :f        |        输出文件名和当前行号        |

    



##### 5.2.10 less 分屏显示文件内容

less指令用来分屏查看文件内容，它的功能与more指令类似，但是比more指令更加强大，支持各种显示终端。less 指令在显示文件内容时，并不是一次将整个文件加载之后才显示，而是根据显示需要加载内容，对于显示大型文件具有较高的效率。



- 基本语法

  - less     查看的文件
  - 操作说明

  |   操作   |              功能说明              |
  | :------: | :--------------------------------: |
  |   空格   |              向下翻页              |
  | pageDown |            向下翻动一页            |
  |  pageUp  |            向上翻动一页            |
  |  /字串   | 向下查找   n向下翻找    N向上翻找  |
  |  ？字串  | 向上查找    n向下翻找    N向上翻找 |
  |    q     |              离开less              |



##### 5.2.11 echo

echo输出内容到控制台

- 基本语法

  - echo [选项]  [输出内容]

    - 选项：

      - -e  支持反斜杠转换

| 控制字符 |        作用         |
| :------: | :-----------------: |
|   \\\    |        输出\        |
|    \n    |        换行         |
|    \t    | 制表符，也就是Tab键 |

​        

##### 5.2.12 > 输出重定向  >>追加

- 基本语法

  - ls -l    >    文件                                                              列表内容覆盖写入文件中
  - ls - al  >>    文件                                                            列表内容追加进文件中
  - cat 文件1  >    文件2                                                     把文件1覆盖掉文件2
  - echo "内容"   >>  文件                                                  把内容追加进入文件中

- 实际操作

  - 将ls -l 写入到target

  ```
  [root@hadoop100 wmt]# ls -l > target
  [root@hadoop100 wmt]# ls
  initial-setup-ks.cfg  newNaem.cfg  target  text.txt  wmt
  [root@hadoop100 wmt]# cat target
  总用量 12
  -rw-r--r--. 1 root root 1727 4月   3 11:15 initial-setup-ks.cfg
  -rw-r--r--. 1 root root 1727 3月  19 21:59 newNaem.cfg
  -rw-r--r--. 1 root root    0 4月   3 19:48 target
  -rw-r--r--. 1 root root 1727 4月   3 11:21 text.txt
  drwxr-xr-x. 2 root root  
  ```

  - 将ls - al  追加到 target

  ```
  [root@hadoop100 wmt]# ls -al >> target
  [root@hadoop100 wmt]# cat target 
  总用量 12
  -rw-r--r--. 1 root root 1727 4月   3 11:15 initial-setup-ks.cfg
  省略
  drwxr-xr-x. 2 root root    6 4月   3 17:49 wmt
  总用量 16
  drwxr-xr-x.  3 root root   94 4月   3 19:48 .
  dr-xr-xr-x. 18 root root  235 4月   3 17:42 ..
  省略
  drwxr-xr-x.  2 root root    6 4月   3 17:49 wmt
  ```

  - cat 文件1  >    文件2      

  ```
  [root@hadoop100 wmt]# cat initial-setup-ks.cfg  > target
  [root@hadoop100 wmt]# cat target
  #version=DEVEL
  # X Window System configuration information
  xconfig  --startxonboot
  # License agreement
  eula --agreed
  # System authorization information
  auth --enableshadow --passalgo=sha512
  # Use CDROM installation media
  cdrom
  
  ```

  - echo "内容"   >>  文件    

  ```
  [root@hadoop100 wmt]# echo -e "hello \n world" >> target
  [root@hadoop100 wmt]# cat target 
  hello 
   world
  
  ```



##### 5.2.13  haed 显示文件头部

haed用于显示文件开头部分内容，默认情况下的head显示文件前10行的内容

- 基本语法

  - head   文件                                           查看文件前10行内容
  - head -n 5  文件                                     查看文件前5行内容

- 实际操作

  ```
  #默认显示10行
  [root@hadoop100 wmt]# head initial-setup-ks.cfg 
  
  #显示1行
  [root@hadoop100 wmt]# head -n 1 initial-setup-ks.cfg 
  #version=DEVEL
  
  ```

  

##### tail 输出文件尾部内容

tail 用于显示文件末尾部分内容，默认情况下的head显示文件后10行的内容

- 基本语法
  - tail 文件                                           查看文件后10行内容
  - tail -n 5  文件                                   查看文件后5行内容
  - tail    -f  文件                                    实时跟踪文件所有的更新
    - tail    -f  文件  会进入一个线程   CTRL +S 是暂停    CTRL +Q是继续    CTRL +C 退出
- 选择说明



|    选项    |                功能                |
| :--------: | :--------------------------------: |
| -n  <行数> |        输出文件末尾n行内容         |
|    - f     | 显示文件最新追加内容，监视文件变化 |

- 实际操作

```
[root@hadoop100 wmt]# tail -f  target
```

