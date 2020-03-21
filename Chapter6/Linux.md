# Linux

## Linux 远程控制管理

传统的网络服务程序，FTP、POP、telnet 本质上都是不安全的，因为它们在网络上通过明文传送口令和数据，这些数据非常容易被截获。SSH 叫做 `Secure Shell`。通过 SSH，可以把传输数据进行加密，预防攻击，传输的数据进行了压缩，可以加快传输速度。

## OpenSSH

SSH 是芬兰一家公司开发。但是受到版权和加密算法限制，现在很多人都使用 `OpenSSH`。`OpenSSH` 是 SSH 的替代软件，免费。

`OpenSSH` 由客户端和服务端组成。

- 基于口令的安全验证：知道服务器的帐号密码即可远程登录，口令和数据在传输过程中都会被加密。
- 基于密钥的安全验证：此时需要在创建一对密钥，把公有密钥放到远程服务器上自己的宿主目录中，而私有密钥则由自己保存。

注意:在`SSH`客户端中不是使用`Ctrl + C` 来复制, 而是使用`Ctrl + Insert`来进行复制,也不是使用`Ctrl + V`来粘贴,而是使用`Shift + Insert`进行粘贴

### 检查软件是否安装

```
apt-cache policy openssh-client openssh-server
```

### 安装服务端

```
apt-get install openssh-server
```

### 安装客户端

```
apt-get install openssh-client
```

OpenSSH 服务器的主要配置文件为 `/etc/ssh/sshd\_config`，几乎所有的配置信息都在此文件中。

## XShell

`XShell` 是一个强大的安全终端模拟软件，它支持 `SSH1`, `SSH2`, 以及 `Microsoft Windows` 平台的 TELNET 协议。`XShell` 通过互联网到远程主机的安全连接以及它创新性的设计和特色帮助用户在复杂的网络环境中工作。

`XShell` 可以在 Windows 界面下用来访问远端不同系统下的服务器，从而比较好的达到远程控制终端的目的。



## Linux 目录结构

![1584794134330](../img/1584794134330.png)

| 目录 | 说明                                                         |
| :--- | :----------------------------------------------------------- |
| bin  | 存放二进制可执行文件(ls,cat,mkdir等)                         |
| boot | 存放用于系统引导时使用的各种文件                             |
| dev  | 用于存放设备文件                                             |
| etc  | 存放系统配置文件                                             |
| home | 存放所有用户文件的根目录                                     |
| lib  | 存放跟文件系统中的程序运行所需要的共享库及内核模块           |
| mnt  | 系统管理员安装临时文件系统的安装点                           |
| opt  | 额外安装的可选应用程序包所放置的位置                         |
| proc | 虚拟文件系统，存放当前内存的映射                             |
| root | 超级用户目录                                                 |
| sbin | 存放二进制可执行文件，只有root才能访问                       |
| tmp  | 用于存放各种临时文件                                         |
| usr  | 用于存放系统应用程序，比较重要的目录/usr/local 本地管理员软件安装目录 |
| var  | 用于存放运行时需要改变数据的文件                             |

## 操作文件目录

| 命令  | 说明                               | 语法                                            | 参数  | 参数说明                           |
| :---- | :--------------------------------- | :---------------------------------------------- | :---- | :--------------------------------- |
| ls    | 显示文件和目录列表                 | ls [-alrtAFR] [name...]                         |       |                                    |
|       |                                    |                                                 | -l    | 列出文件的详细信息                 |
|       |                                    |                                                 | -a    | 列出当前目录所有文件，包含隐藏文件 |
| mkdir | 创建目录                           | mkdir [-p] dirName                              |       |                                    |
|       |                                    |                                                 | -p    | 父目录不存在情况下先生成父目录     |
| cd    | 切换目录                           | cd [dirName]                                    |       |                                    |
| touch | 生成一个空文件                     |                                                 |       |                                    |
| echo  | 生成一个带内容文件                 | echo abcd > 1.txt，echo 1234 >> 1.txt           |       | >  添加, >> 为追加                 |
| cat   | 显示文本文件内容                   | cat [-AbeEnstTuv] [--help] [--version] fileName |       |                                    |
| cp    | 复制文件或目录                     | cp [options] source dest                        |       |                                    |
| rm    | 删除文件                           | rm [options] name...                            |       |                                    |
|       |                                    |                                                 | -f    | 强制删除文件或目录                 |
|       |                                    |                                                 | -r    | 同时删除该目录下的所有文件         |
| mv    | 移动文件或目录                     | mv [options] source dest                        |       |                                    |
| find  | 在文件系统中查找指定的文件         |                                                 |       |                                    |
|       |                                    | find -name  '*abcd.txt'                         | -name | 文件名                             |
| grep  | 在指定的文本文件中查找指定的字符串 |                                                 |       |                                    |
| tree  | 用于以树状图列出目录的内容         |                                                 |       |                                    |
| pwd   | 显示当前工作目录                   |                                                 |       |                                    |
| ln    | 建立软链接                         |                                                 |       |                                    |
| more  | 分页显示文本文件内容               |                                                 |       |                                    |
| head  | 显示文件开头内容                   |                                                 |       |                                    |
| tail  | 显示文件结尾内容                   |                                                 |       |                                    |
|       |                                    |                                                 | -f    | 跟踪输出                           |

## 系统管理命令

| 命令     | 说明                                                         |
| :------- | :----------------------------------------------------------- |
| stat     | 显示指定文件的相关信息,比ls命令显示内容更多                  |
| who      | 显示在线登录用户                                             |
| hostname | 显示主机名称                                                 |
| uname    | 显示系统信息                                                 |
| top      | 显示当前系统中耗费资源最多的进程                             |
| ps       | 显示瞬间的进程状态, `ps -ef|grep xxx`:查看某进程详情         |
| du       | 显示指定的文件（目录）已使用的磁盘空间的总量,加参数 `-h` 可查看更详细信息 |
| df       | 显示文件系统磁盘空间的使用情况, `-h` 可查看更详细信息        |
| free     | 显示当前内存和交换空间的使用情况, `-h` 可查看更详细信息      |
| ifconfig | 显示网络接口信息                                             |
| ping     | 测试网络的连通性                                             |
| netstat  | 显示网络状态信息                                             |
| clear    | 清屏                                                         |
| kill     | 杀死一个进程, `kill -9 进程号`:绝对杀死某一进程              |

## 开关机命令

> shutdown 命令可以用来进行关机程序，并且在关机以前传送讯息给所有使用者正在执行的程序，shutdown 也可以用来重开机。

| 命令     | 语法                                            | 参数       | 参数说明                                                     |
| :------- | :---------------------------------------------- | :--------- | :----------------------------------------------------------- |
| shutdown | shutdown [-t seconds] [-rkhncfF] time [message] |            |                                                              |
|          |                                                 | -t seconds | 设定在几秒钟之后进行关机程序                                 |
|          |                                                 | -k         | 并不会真的关机，只是将警告讯息传送给所有只用者               |
|          |                                                 | -r         | 关机后重新开机（重启）                                       |
|          |                                                 | -h         | 关机后停机                                                   |
|          |                                                 | -n         | 不采用正常程序来关机，用强迫的方式杀掉所有执行中的程序后自行关机 |
|          |                                                 | -c         | 取消目前已经进行中的关机动作                                 |
|          |                                                 | -f         | 关机时，不做 fcsk 动作(检查 Linux 档系统)                    |
|          |                                                 | -F         | 关机时，强迫进行 fsck 动作                                   |
|          |                                                 | time       | 设定关机的时间                                               |
|          |                                                 | message    | 传送给所有使用者的警告讯息                                   |

### 重启

- reboot,没有权限时,使用`sudo reboot`
- shutdown -r now

### 关机

- shutdown -h now

## 压缩命令

### tar

| 命令 | 语法                                        | 参数 | 参数说明                        |
| :--- | :------------------------------------------ | :--- | :------------------------------ |
| tar  | tar [-cxzjvf] 压缩打包文档的名称 欲打包目录 |      |                                 |
|      |                                             | -c   | 建立一个归档文件的参数指令      |
|      |                                             | -x   | 解开一个归档文件的参数指令      |
|      |                                             | -z   | 是否需要用 gzip 压缩            |
|      |                                             | -j   | 是否需要用 bzip2 压缩           |
|      |                                             | -v   | 压缩的过程中显示文件            |
|      |                                             | -f   | 使用档名，在 f 之后要立即接档名 |
|      |                                             | -tf  | 查看归档文件里面的文件          |

**例子：**

- 压缩文件夹：`tar -zcvf test.tar.gz test\`
- 解压文件夹：`tar -zxvf test.tar.gz`

### gzip

| 命令 | 语法                               | 参数 | 参数说明                                                     |
| :--- | :--------------------------------- | :--- | :----------------------------------------------------------- |
| gzip | gzip [选项] 压缩（解压缩）的文件名 |      |                                                              |
|      |                                    | -d   | 解压缩                                                       |
|      |                                    | -l   | 对每个压缩文件，显示压缩文件的大小，未压缩文件的大小，压缩比，未压缩文件的名字 |
|      |                                    | -v   | 对每一个压缩和解压的文件，显示文件名和压缩比                 |
|      |                                    | -num | 用指定的数字num调整压缩的速度，-1或--fast表示最快压缩方法（低压缩比），-9或--best表示最慢压缩方法（高压缩比）。系统缺省值为6 |

说明：压缩文件后缀为 gz

### bzip2

| 命令  | 语法         | 参数 | 参数说明                                                     |
| :---- | :----------- | :--- | :----------------------------------------------------------- |
| bzip2 | bzip2 [-cdz] |      |                                                              |
|       |              | -d   | 解压缩                                                       |
|       |              | -z   | 压缩参数                                                     |
|       |              | -num | 用指定的数字num调整压缩的速度，-1或--fast表示最快压缩方法（低压缩比），-9或--best表示最慢压缩方法（高压缩比）。系统缺省值为6 |

说明：压缩文件后缀为 bz2

## Linux 编辑器

### vim

#### 运行模式

编辑模式：输入`vim 某文件`进行编辑模式,等待编辑命令输入, 

插入模式：编辑模式下，输入 `i` 进入插入模式，插入文本信息

命令模式：在编辑模式下，按`ESC`键退出插入模式,输入 `:` 进行命令模式

说明:在编辑模式下,连续两次按下`D`,可快速删除选中行.

#### 命令

`:q` 直接退出vi

`:wq` 保存后退出vi ，并可以新建文件

`:q!` 强制退出

`:w file` 将当前内容保存成某个文件

`:set number` 在编辑文件显示行号

`:set nonumber` 在编辑文件不显示行号

### nano

nano 是一个字符终端的文本编辑器，有点像 DOS 下的 editor 程序。它比 vi/vim 要简单得多，比较适合 Linux 初学者使用。某些 Linux 发行版的默认编辑器就是 nano。

#### 命令

- 保存：`ctrl + o`
- 搜索：`ctrl + w`
- 上一页：`ctrl + y`
- 下一页：`ctrl + v`
- 退出：`ctrl + x`

## Linux 软件包管理

>  APT(Advanced Packaging Tool) 是 Debian/Ubuntu 类 Linux 系统中的软件包管理程序, 使用它可以找到想要的软件包, 而且安装、卸载、更新都很简便；也可以用来对 Ubuntu 进行升级; APT 的源文件为 `/etc/apt/` 目录下的 `sources.list` 文件。
>
> 由于国内的网络环境问题，我们需要将 Ubuntu 的数据源修改为国内数据源，操作步骤如下：

### 修改数据源

#### 查看系统版本

```
lsb_release -a
```

输出结果为

```
No LSB modules are available.
Distributor ID:    Ubuntu
Description:    Ubuntu 18.04 LTS
Release:    18.04
Codename:    bionic
```

**注意：** Codename 为 `bionic`，该名称为 Ubuntu 系统的名称，修改数据源需要用到该名称

#### 编辑数据源

```
vi /etc/apt/sources.list
```

删除全部内容并修改为

```
deb http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
```

#### 更新数据源

```
apt-get update
```

### 常用 APT 命令

#### 安装软件包

```
apt-get install packagename
```

#### 删除软件包

```
apt-get remove packagename
```

#### 更新软件包列表

```
apt-get update
```

#### 升级有可用更新的系统（慎用）

```
apt-get upgrade
```

#### 其它 APT 命令

##### 搜索

```
apt-cache search package
```

##### 获取包信息

```
apt-cache show package
```

##### 删除包及配置文件

```
apt-get remove package --purge
```

##### 了解使用依赖

```
apt-cache depends package
```

##### 查看被哪些包依赖

```
apt-cache rdepends package
```

##### 安装相关的编译环境

```
apt-get build-dep package
```

##### 下载源代码

```
apt-get source package
```

##### 清理无用的包

```
apt-get clean && apt-get autoclean
```

##### 检查是否有损坏的依赖

```
apt-get check
```