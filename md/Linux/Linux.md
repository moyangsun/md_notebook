

# 第一章 Linux基础

## 1.1 命令行界面

**具体信息分析**

![image-20240909182459877](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409091824917.png)

- `1`区

  - `1`
    - `d`：目录/文件
    - `l`：软链接文件
    - `-`：二进制文件
  - `2-4`
    - `u`：用户
  - `5-7`
    - `g`：组
  - `8-10`
    - `o`：其他
  - 其中数字的具体含义
    - `r`：读(用阿拉伯数字表示为`4`)
    - `w`：写(用阿拉伯数字表示为2)
    - `x`：可执行(用阿拉伯数字表示为`1`)

- `2`区：硬链接的个数

  > 硬链接和软链接从一定程度上类比`C++`中的指针和引用，当然这并不准确。**硬链接**是直接指向文件内容的链接。**软链接**是一种特殊的文件，它包含指向目标文件或目录路径的引用（类似于快捷方式）。
  >
  > <img src="https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409091849113.png" alt="image-20240909184924078" style="zoom: 67%;" Align="left"/>

- `3`区：创建者的名称

- `4`区：组名称

  > 组是`linux`中很有意思的概念，`linux`是一个是一个真实的、完整的多用户多任务操作系统，多用户多任务就是可以在系统上建立多个用户，而多个用户可以在同一时间内登录同一个系统执行各自不同的任务，而互不影响。那么对于这些用户就要进行管理，从而引生出组的概念，方便对用户进行管理。

- `5`区：文件大小
- `6`区：最后修改时间

**文件目录权限**

| 代表字符 | 权限     | 对文件的含义     | 对目录的含义               |
| -------- | -------- | ---------------- | -------------------------- |
| `r`      | 读权限   | 可以查看文件     | 可以列出目录中的内容       |
| `w`      | 写权限   | 可以修改文件内容 | 可以在目录中创建、删除文件 |
| `x`      | 执行权限 | 可以执行文件     | 可以进入目录               |



### 1.1.1 常用的基本命令


**ls**

语法：`ls [参数][File|Directory]`

参数：查看当前目录的内容

选项：

- `-a`：列出包含以`.`开始的条目。
- `-l`：显示文件具体的信息。(可以直接输入命令`ll`是一样的效果)
- `-d`：查看目录的属性

演示：

> 由于我使用的是龙溪OS是阿里开发的Linux操作系统，继承了centos8，所以会有中文出现。

![image-20240909181102076](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409091811112.png)



**cd**

语法：`cd [Directory]`

描述：更改当前目录

演示：

![image-20240909190833977](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409091908015.png)



**cp**

语法：`cp [参数] SourceFile|SourceDir TargetFile|TargetDir`

描述：拷贝文件或文件夹

参数：

- `-f`：强制复制，即若复制到的文件中有重名文件，不弹出提示，直接覆盖。
- `-i`：提示将要被覆盖的文件名
- `-r`：递归复制文件夹中的文件

演示：

![image-20240909192734473](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409091927516.png)



**rm**

语法：`rm [参数] File`

描述：删除文件

参数：

- `-i`：删除每个文件前有提示
- `-r`：递归删除文件夹中的文件
- `-f`：强制删除文件，而不再提示

演示：

![image-20240909193358752](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409091933804.png)



**mv**

语法：`mv [参数] 源文件 目标文件`

描述：移动文件，或者对文件重命名

参数：

- `-i`：移动每个文件前有提示
- `-f`：强制覆盖目标文件而不提示确认

演示：

![image-20240909194456791](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409091944841.png)



**pwd**

语法：`pwd`

描述：查看当前目录的绝对路径  

演示：

![image-20240909195006916](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409091950951.png)



**mkdir**

语法：`mkdir` [参数] 文件名

描述：创建一个目录

参数:

- `-m Mode`：设置新目录的权限模式。
- `-p`：同时创建多级目录

演示：

![image-20240909201630721](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409092016785.png)



**rmdir**

语法：`rmdir [参数] [文件名]`

描述：删除有待删除文件的父目录写权限的空目录(其实直接用`rm`就行)

参数：

- `-p`：同时删除多级目录。

演示：

![image-20240909203119088](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409092031150.png)

 

**shutdown**

语法:`shutdown`

功能描述: 关机

演示：`shutdown now`



### 1.1.2 查看文件内信息命令

**touch**

语法：`touch [参数] [文件名]`

描述：创建一个空文件，可以在创建文件时添加后缀从而确定新建文件的属性

演示：

![image-20240909205206435](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409092052492.png)





**cat**

语法：`cat [参数] [文件名]`

描述：显示文件内容，也可以用来拼接文件。

演示：

![image-20240909204600327](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409092046401.png)



**more**

语法：`more [参数] [文件名]`

描述：分页显示内容

常用命令：

- `空格键`：向下翻页（移动到下一页）。
- `Enter`：向下滚动一行。
- `b`：向上翻页（移动到上一页）。
- `q`：退出 `more`，停止查看文件。
- `/`：搜索关键字，输入 `/keyword` 然后按 `Enter`，会向下搜索文件中的 `keyword`。
- `h`：显示帮助文档。
- `=`：显示当前行号。
- `v`：在 `vi` 编辑器中打开当前文件。

演示：

![image-20240909210110689](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409092101723.png)

![image-20240909210042159](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409092100226.png)



**head**

语法：`head  -num [文件名]`

描述：显示文件中的`num`行。

演示：

![image-20240909210449479](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409092104524.png)



**tail**

语法：`tail  -num [文件名]`

描述：显示文件中的后`num`行。

演示：

![image-20240909210558502](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409092105547.png)



**less**

语法：`less [参数] [文件名]`

描述：允许用户向前或向后滚动文件内容，支持搜索功能。

常用命令：

- 空格键：向下翻一页。
- `b`：向上翻一页。
- `Enter`：向下滚动一行。
- `y`：向上滚动一行。
- `g`：跳转到文件的开头。
- `G`：跳转到文件的结尾。
- `/pattern`：向下搜索 `pattern` 字符串（按 `n` 键可以跳到下一个匹配）。
- `?pattern`：向上搜索 `pattern` 字符串（按 `n` 键可以跳到上一个匹配）。
- `n`：重复上一次的搜索（向下）。
- `N`：反向重复上一次的搜索（向上）。
- `h`：显示帮助文档，列出所有命令。
- `q`：退出 `less`。

演示：

![image-20240909211004618](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409092110659.png)

![image-20240909210944210](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409092109295.png)



### 1.1.3 用户权限设置命令

**chmod**

语法：`chmod [ugoa][+-=][rwx] [文件名]`（符号表示法）

​			`chmod [nnn] [文件名] `

描述：改变用户对文件的访问权限。

演示：

![image-20240909211655853](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409092116929.png)



**chown**

语法：`chown [用户] [文件或目录]`

描述：改变文件或目录的所有者

演示：

![image-20240909212134467](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409092121537.png)

​	

**chgrp**

语法：`chgrp [用户] [文件或目录]`

描述：改变文件或目录的所有者

演示：

![image-20240909212259166](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409092122229.png)



### 1.1.4 寻找指令

**find**

语法：find [路径] [选项] [条件] [操作]

描述：寻找文件

参数：

- 路径：要搜索的目录及其子目录。如果没有指定，默认从当前目录开始。

- 选项：控制 `find` 的行为（如是否递归等）。

- 条件：用于定义搜索的标准，比如按名称、类型、大小、时间等搜索。
  - `name`
  - `size`
  - `user`
  - ......

- 操作：对找到的文件执行特定的操作，比如删除、移动、拷贝等。

- 口诀：在哪里找，怎么找，找什么

演示：

![image-20240909212849402](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409092128445.png)



**grep**

语法:`grep` [指定字串] [源文件]

描述:在文件中搜寻字串匹配的行并输出

演示：

![image-20240917122813430](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409171228532.png)

> 管道操作符`|`:将一个命令的输出传送给另-个命令，作为另一个命令的输入。
>
> `grep`经常和管道操作符`|`搭配使用。
>
> ![image-20240917123013580](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409171230617.png)



### 1.1.5 帮助指令

**man**

语法:`man` [命令或配置文件] 

描述:获得帮助信息

演示：`man ls`



**help**

语法:`help` [命令或配置文件] 

描述:提供简明的帮助信息



**whatis**

语法:`whatis` [命令或配置文件] 

描述:简要显示命令的功能

演示：`whatis ls`

> **三者的区别：**
>
>  - **`man`**：提供详细的命令文档，适合查阅全面的手册页。
>
> - **`help`**：适用于 `shell` 内置命令，提供简明的帮助信息。
>
> - **`whatis`**：提供命令的简短描述，适合快速查看命令用途。



### 1.1.6 压缩解压命令

**tar（压缩）**

语法:`tar` 选项 [参数] [目录]

功能描述:打包目录

参数：

- `-c`:产生.`tar`打包文件
- `-x`:解包
- `-v`:显示详细信息
- `-f`:指定压缩后的文件名
- `-z`:打包同时压缩

演示：

![image-20240917125821734](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409171258777.png)

**tar（解压）**

语法:`tar` 选项 [参数] [目录]

功能描述:解压目录

参数：

- `-x`:解包
- `-v`:显示详细信息
- `-f`:指定压缩后的文件名
- `-z`:打包同时压缩

演示：

![image-20240917125938199](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409171259245.png)



### 1.1.7 网络通信命令

**ping**

语法:`ping` 选项`IP`地址

描述:测试网络连通性

![image-20240917130326657](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409171303712.png)

> 可以`ping` `ip`地址，也可以`ping`域名，事实上所谓的域名就是利用了`DNS`服务，域名的背后依然是`IP`地址，具体内容可以移步计算机网路的模块。



**ifconfig**

语法:ifconfg [选项] [网卡设备标识]

描述:查看网络设置信息

参数：`-a` 显示所有网卡信息

演示：

![image-20240917130801514](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409171308583.png)



### 1.1.8 命令总览表

| 命令       | 描述                           |
| ---------- | ------------------------------ |
| `ls`       | 查看当前目录内容               |
| `cd`       | 切换目录                       |
| `cp`       | 复制文件或文件夹               |
| `rm`       | 删除文件或文件夹               |
| `mv`       | 移动文件或文件夹               |
| `pwd`      | 查看当前目录的绝对路径         |
| `mkdir`    | 创建文件夹                     |
| `rmdir`    | 删除空的文件夹                 |
| `shutdown` | 关机                           |
| `touch`    | 创建文件                       |
| `cat`      | 查看文件                       |
| `more`     | 分页查看文件                   |
| `head`     | 查看文件的前`n`行              |
| `tail`     | 查看文件的后`n`行              |
| `less`     | 滑动查看文件                   |
| `chmod`    | 改变文件权限                   |
| `chown`    | 改变文件的所有者               |
| `chgrp`    | 改变文件所在的组               |
| `find`     | 寻找文件                       |
| `grep`     | 在文件中搜寻字串匹配的行并输出 |
| `man`      | 获得帮助信息                   |
| `help`     | 提供简明的帮助信息             |
| `whatis`   | 简要显示命令的功能             |
| `tar`      | 压缩和解压                     |
| `ping`     | 测试网络连通性                 |
| `ifconfig` | 查看网络设置信息               |

## 1.2 Linux软件包

### 1.2.1 二进制软件包之RPM

1. `RPM`软件包的一个例子:

```shell
sudo-1.7.2p1-5.el5.i386.rpm
```

其中包括软件名(sudo)，版本号(1.7.2p)，发行号(5.el5)，和硬件平台(i386)。



2. `RPM`软件包的卸载

```shell
# rpm -e sudo
# rpm -e samba
```

注意:如果其它软件包有依赖关系，卸载时会产生提示信息，可使用-nodeps强行卸载。



3. `RPM`软件包的安装

```shell
# rpm -ivh sudo-1.7.2p1-5.el5.i386.rpm
```

挂载光盘:

```shell
#mkdir /mnt/cdrom
#mount /dev/cdrom /mnt/cdrom
#ls | grep sudo
#rpm -ivh sudo-1.7.2p1-5.el5.i386.rpm
```

查询是否已经安装成功:

```shell
#rpm -q sudo
```



4. 查询软件包是否已经安装完成

```shell
#rpm -qa|grep samba
```



5. `RPM`包的管理

   1. 问题一：软件包已被安装

   ```shell
   package sudo-1.7.2p1-5.el5.i386 is already installed
   ```

   如果覆盖安装该软件包，可以在命令行上使用`--replacepkgs` 选项。

   ```shell
   #rpm -ivh --replacepkgs sudo-1.7.2p1-5.e15.i386.rpm
   ```
   2. 问题二：软件包已被安装
   
   ```shell
   conflicts with file from bark-3.2-1l sudo-1.7.2p1-5.el5.i386.rm cannot be installed
   ```
   
   要想让`RPM` 忽略该错误信息,请使用-`-replacefiles`
   
   ```shell
   #rpm -ivh -replacefiles sudo-1.7.2p1-5.e15.i386.rpm
   ```
   3. 问题三:未解决依赖关系
   
   ```shell
   failed dependencies: sudo is needed by bark-3.2-1]
   ```
   
   你必须安装完所依赖的软件包，才能解决这个问题，强制安装使用`--nodeps`选项。
   
   ```shell
   #rpm -ivh-nodeps sudo-1.7.2p1-5.e15.i386.rpm
   ```
   





## 1.3 用户和组文件

1. 用户帐号文件——`passwd`（位置:`/etc/passwd`）

   ​		用于用户登录时校验用户的经盘名、加密的口令数据项用户`ID(UID)`、默认的用户分组`ID(GID)`、用户信息用户登录子目录、登录后使用的`shell`。

   可以使用`cat`来查看用户信息。

   ![image-20240923171608308](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409231716369.png)

   > `logname`（用户的名称）: `moxiaoyang`
   >
   > `password`（用户的密码）: `x`（这里是对登入密码做了隐藏处理）
   >
   > `uid`（用户的ID）: `1000`（用户的`UID`是唯一的，`root`用户的`UID`是`0`）
   >
   > `gid`（用户的组ID）: `1000`
   >
   > `userinfo`（用户的信息）: `moxiaoyang`
   >
   > `home`（用户的`home`地址）: `/home/moxiaoyang`（`root`的用户地址是`/root`，其余都是`/home/用户名`）
   >
   > `shell`（用户使用的 `shell`模式）: `/bin/bash`

2. 用户影子文件(用户密码文件)——`shadow`(位置:`/etc/shadow`)

   ​		是一种安全机制，将加密的口令放在`shadow`文件里，该件只有`root`用户可读，而在`passwd`文件里的密文域显示个`x`，从而最大限度减少了密文泄露机会。

   可以使用`cat`来查看用户密码文件

   ![image-20240923175335602](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409231753674.png)

   > 用户登录名: `moxiaoyang`
   >
   > 用户加密口令: `$6$BrqbTh0M0k5EjHby$9EkiTPRyNEIcb5O5ERaoRieI9pvv4......`
   >
   > 从`1970年1月1日`起到上次修改口令所经历的天数: `19853`
   >
   > 需要多少天才能修改这个口令: `0`
   >
   > 该口令不过期: `99999`
   >
   > 要在口令失效前`7`天内通知用户: 7
   >
   > 发出警告禁止登录前用户还有效的天数: 未定义
   >
   > 用户被禁止的登录的时间: 未定义

3. 用户组帐号文件`group`——(位置:`/etc/group`)

   可以使用`cat`来查看用户组帐号文件
   ![image-20240923181428114](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409231814161.png)

   > 这里以第二条为例
   >
   > 用户分组名: `moxiaoyang`
   >
   > 加过密的用户分组口令: `x` （这里密码进行了隐藏）
   >
   > 用户分组`ID`号: `1000`
   >
   > 以逗号分隔的成员用户清单: `moxiaoyang`（若是组中还有其他用户用逗号隔开如`zhangsan,lisi`）

4. 用户组影子文件——`gshadow`(位置:`/etc/gshadow`)

   可以使用`cat`来查看用户组影子文件

   ![image-20240923182334818](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409231823871.png)

   > 这里以第二条为例
   >
   > 用户分组名: `moxiaoyang`
   >
   > 组密码: `!`（这里是锁定状态，具体后面会提到，还有`*`的模式表示通常表示这个组没有密码
   >
   > 管理员列表: 此字段为空，表示该组没有管理员
   >
   > 组成员列表: moxiaoyang

5. 使用`useradd`命令添加用户

   建立一个用户名为`YH`，描述信息为`moxiaoyang's roommate`，用户组为`YH`，登录`shell`为`/bin/sh`，登录主目录为`/home/YH`的用户

   ![image-20240923184530185](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409231845266.png)

   > `useradd -r YH -c "moxiaoyang's roommate" -g YH -s /bin/sh -d /home/YH`不清楚为啥这条命令为啥不行，反正`centos8`这条命令不行，不清楚红帽里能不能用。

   1. 使用`passwd`为用户添加密码

      ![image-20240923191703841](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409231917900.png)

      > 要是弹出来说太简单了，没有关系的，再输入一次就行

   2. 锁定用户密码: `passwd -l 用户名`

      ![image-20240923203001707](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409232030761.png)

   3. 解锁用户密码: `passwd -u 用户名` 

      ![image-20240923202939260](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409232029322.png)

6. 使用`usermod`命令修改用户信息

   1. 将用户`YH`的用户名改为`YHH`，其登录`shell`改为`/bin/ash`，用户描述信息改为`"YH"`

      ![image-20240923203638891](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409232036942.png)

   2. 锁定用户，使用`-L`参数

      ![image-20240923203901356](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409232039400.png)

      > 可以看到这里只有一个`!`,以作为和`password`的区分。

   3. 解锁用户，使用`-U`参数

      ![image-20240923204037271](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409232040318.png)

      > 比较有趣的一点是，若是用`passwd -l`进行上锁，可以使用输入两次`usermod -u`进行解锁

7. 使用`userdel`命令删除用户

   ![image-20240923204326122](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409232043185.png)

   > 加上`-r`删除电户的同时，一并删除该用户对应的主目录。

8. 使用`groupadd`命令创建用户组

   ![image-20240923192228412](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409231922459.png)

9. 使用`groupmod`命令修改用户组属性

   ![image-20240923192757080](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409231927134.png)





# 第二章 Samba服务器配置

## 2.1 Samba概述

**`Samba`的主要功能**

- 共享 `Linux` 的文件系统。
- 共享安装在 `Samba` 服务器上的打印机。
- 支持 `Windows` 客户使用网上邻居浏览网络。
- 使用 `Windows` 客户系统共享的文件和打印机。
- 支持 `Windows` 域控制器和 `Windows` 成员服务器使用。
- `Samba` 资源的用户进行认证。
- 支持 `WINS` 名字服务器解析及浏览。
- 支持 `SSL` 安全套接层协议。

 ## 2.2 安装Samba服务

- 查看`Samba`服务是否安装

  ```shell
  #rpm -qa | grep samba
  ```
  ![image-20240923193615717](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409231936769.png)

## 2.3 Samba服务器的基本配置

- `Samba`配置文件应存放在

  ```shell
  /etc/samba/smb.conf
  ```
  
- 先备份一下配置文件（不熟练前都在对配置文件进行操作时都尽量进行备份）

  ```shell
  #cp /etc/samba/smb.conf /etc/samba/smb.conf.bak
  ```

- `Samba`设置包括四个设置段

  - `[global]`设置全局环境选项
  - `[homes]`设置用户宿主目录选项
  - `[printers]`设置打印机共享
  - `[sharefiles]`设置文件共享

  > 需要注意是在配置文件中以`#`或者`;`开头的皆为注释内容

### 2.3.1 `smb.conf`配置文件实例详解

​		`smb.conf`包括几个段，每个段都以方括号包括。段名后面跟着若干`key/value`（键值对）。

- `[global]`（全局设置）

  - `workgroup=WGK` # 指定工作组的名称
  - `server string`=描述
  - `security`=指定安全模式
    - `share`客户端连接服务器时不需要输入用户名和密码
    - `user`(缺省设置)客户端连接服务器时需要输入用户名和密码
    - `server`客户端连接服务器时需要输入用户名和密码，但密码验证需要密码验证服务器来负责
    - `domain`采用域控制器对用户进行身份验证
    - `ads`若`samba`服务器加入到`windows`活动日录中则使用`ads`安全级别，`ads`安全级别必须指定口令服务器
  - `hosts allow`=限定主机访问
  - `log file`=指定日志文件存放的配置
  - `max log size`=指定日志文件的最大大小

- `[share]/[public]`   

  - comment = Shared Folder  # 描述信息   
  - path = /srv/samba/share  # 共享目录路径   
  - browseable = yes  # 允许在网络中浏览   
  - guest ok = yes  # 允许访客访问   
  - read only = no  # 是否只读（no 表示可写）   
  - create mask = 0755  # 设置文件创建的权限

  > 以上是最小的`sbm.conf`配置，该文件至少需要全局段和若干个共享段。全局段描述适应于整个`Samba`服务器的设置，每个共享段述一个对象的属性

- `[homes]`   

  - `comment = Home Directories`  # 描述信息   
  - `browseable = no`  # 主目录不在网络邻居中显示   
  - `writable = yes`  # 是否允许写入   
  - `valid users = %S`  # 限制为当前用户可以访问

- `[printers]`   

  - `comment = All Printers`   
  - `path = /var/spool/samba`  # 打印机的临时文件路径   
  - `browseable = no`  # 是否在网络中显示打印机   
  - `guest ok = yes`  # 是否允许访客访问打印机   
  - `writable = no`  # 打印机不允许写入（仅限打印）   
  - `printable = yes`  # 指定这是一个可打印的共享资源

- `[profiles]`   

  - `comment = User Profiles`    # 对该共享的描述，方便管理员识别   
  - `path = /var/lib/samba/profiles`  # 存放用户配置文件的目录路径   
  - `browseable = no`   # 设置为 no，避免在网络浏览器（如 Windows 的“网络邻居”）中显示该共享   
  - `guest ok = yes`   # 允许未认证的访客用户访问该共享   
  - `writable = yes`   # 允许用户对该共享目录具有写权限   
  - `create mask = 0700`   # 当创建文件时，设置默认的文件权限为 0700（文件仅对所有者可见和可写）   
  - `directory mask = 0700`   # 当创建目录时，设置默认的目录权限为 0700（目录仅对所有者可见和可写）

### 2.3.2 使用`Samba`服务

- 查看`Samba`状态

  `Samba`服务的名字为`smb`，其中包含`Smbd`和`Nmbd`两个服务，可以使用以下命令来查看`Samba`守护进程的状态。

  ```shell
  #service smb status
  #systemctl status smb.service # 新版本使用这个命令
  #systemctl status nmb.service
  ```

  ![image-20240923201010214](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409232010278.png)

- 开启`Samba`服务

  ```shell
  #service smb start
  
  #systemctl start smb.service # 新版本使用这个命令
  #systemctl start nmb.service
  ```

  ![image-20240923201142892](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409232011963.png)

- 停止`Samba`服务

  ```shell
  #service smb stop
  #systemctl stop smb.service # 新版本使用这个命令
  #systemctl stop nmb.service
  ```

  ![image-20240923201232326](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409232012395.png)

  

## 2.4 Samba客户端配置应用

1. 公司现有一个工作组`mygroup`，共享目录`/share`，共享名为`share`，此共享目录允许所有员工访问。

   1. 修改配置文件修`/etc/samba/smb.conf`

      ```shell
      #vi /etc/samba/smb.conf
      ```
      
      修改内容如下所示
   
      ```ini
      [global]
          workgroup = mygroupe    # 指定 Samba 服务器所加入的 Windows 工作组
          security = share        # 允许基于共享的访问控制
      [share]
          comment = share         # 提供对共享的描述
          path = /home/share      # 指定共享资源在文件系统中的实际路径
          public = yes            # 指示该共享是否对所有用户开放
      ```
      
      ![image-20240923205106402](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409232051470.png)
   
   
   
   2. 建立`/share`文件夹,在文件夹中建了一个测试文件`file.text`。
   
      ![image-20240923204654888](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409232046953.png)
   
   3. 重新启动`samba`服务器
   
      ```shell
      #service smb restart
      
      #systemctl restart smb.service # 新版本使用这个
      #systemctl restart nmb.service
      ```
   > 由于我的`samba`版本过新，导致无法将`security`设置为`public`，所以我采用用户登入的方式（上方为学院派，下方为实践派）。
   >
   > 首先创建一个组为`share`，创建一个用户share在组中
   >
   > ```shell
   > # groupadd share
   > # useradd -d /home/share -g share share
   > ```
   >
   > 修改配置文件修`/etc/samba/smb.conf`
   >
   > ```ini
   > # 在文件的最后加入
   > comment=name #描述信总
   > path=/home/name #共享目录
   > browseable=yes #可浏览
   > writable=yes #是否有写权限
   > available=yes #可使用 avalide
   > valid users=name #允许访问该共享的用户
   > write list=name #可写入共享的用户列表
   > ```
   >
   > ![image-20240923220417510](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409232204599.png)
   >
   > 将用户添加入samba账户中,设置好对应的密码
   >
   > ```shell
   > # smbpasswd -a share
   > ```
   >
   > 关闭防火墙
   >
   > ```shell
   > # systemctl stop firewalld.service
   > # setenforce 0
   > ```
   >
   > 重新启动`samba`服务器
   >
   > ```shell
   > #systemctl restart smb.service 
   > ```
   >
   > 在运行窗口中输入，然后输入刚刚设置的用户和密码即可登入
   >
   > ![image-20240923221544455](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409232215505.png)
   >
   > 登录入页面为
   >
   > ![image-20240923221640326](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409232216432.png)
   >
   > 若`windows`要对文件进行更改，则需要使用`chmod`来改变文件的权限。
   >
   > 还需要注意一点的是，若想用VM的网络连接方式要设置为网桥，设为网桥显示网络无法连接，可以使用下方链接。
   >
   > [解决win10系统下VMware的虚拟机桥接模式不可用问题_桥接模式不显示winr-CSDN博客](https://blog.csdn.net/qq_42549792/article/details/100592005)

2. 学校现有多个部门，因工作需要，将教学管理部的资料存放在`samba`服务器的`/jxgls`目录中集中管理，以便教学管理人浏览，并且该目录只允许教学管理部门的员工访问

   1. 添加教学管理部门的用户和组，建立文件夹`/jxgls`

      ```shell
      #groupadd jxgl
      #useradd -g jxgl jxuser1
      #useradd -g jxgl jxuser2
      #passwd jxuser1
      #passwd jxuser2
      #mkdir /jxgl
      #vi /jxgl/jx.text
      ```

      ![image-20240924152015608](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409241520689.png)

   2. 将两个帐户`jxuser1`和`jxuser2`添加到`samba`的帐户中

      ```shell
      #smbpasswd -a jxuser1
      #smbpasswd -a jxuser2
      ```

      ![image-20240924152222472](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409241522531.png)

   3. 修改`samba`配置文件`smb.conf`

      ```shell
      #vi /etc/samba/smb.conf
      ```

      ```ini
      [global]
          workgroup = mygroup
          security = user
          encrypt passwords = yes
          smb passwd file = /etc/samba/smbpasswd
      [jxgl]
      	comment = jxlgs
      	path = /jxgl
      	valid users = @jxgl
      [homes]
          comment = H
          browseable = no
          writable = yes
          valid users = %S
      ```

      ![image-20240924153148924](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409241531007.png)

   4. 关闭防火墙

      ```shell
      # systemctl stop firewalld.service
      # setenforce 0
      ```

      重新启动`samba`服务器

      ```shell
      #systemctl restart smb.service 
      ```

   5. 在运行窗口中输入，然后输入刚刚设置的用户和密码即可登入

      ![image-20240924153423228](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409241534316.png)
      
   6. 打开结果如下图所示
   
      ![image-20240924154449152](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409241544229.png)
   
   > 在登入的时候可能会出现下述情况，如你所示，不允许一个用户使用一个以上用户名与服务器或共享资源的多重连接。中断与此服务器或共享资源的所有连接，然后再试一次。所以需要在`Windows `中关闭这个服务。
   >
   > ![image-20240924154033990](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409241540041.png)
   >
   > ```bash
   > net use # 列出当前连接的共享
   > net use \\server\share /delete # 断开特定的共享
   > 
   > net use * /delete /y # 断开所有链接
   > ```
   >
   > ![image-20240924154237859](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202409241542914.png)





3. 假如公司有财务，技术，领导`3`个部门，相应的`4`个用户组为`caiwu`,`jishu`,`lingdao`;`3`个部门里各有`2`个用户分别为`caiwu01`,`caiwu02`,`jishu01`,`jishu02`,`lingdao01`,`lingdao02`架设`Samba`服务器，要求如下

   - `Samba`服务器采用用户验证的方式,每个用户可以访问自己的宿主目录,并且只有该用户能访问宿主目录,并具有完全的权限,而其他人不能看到你的宿主目录

   - 建立一个`caiwu`的文件夹,希望`caiwu`组和`lingdao`组的人能看到，`jishu02`也可以访问，但只有`caiwu01`有写的权限

   - 建立一个`lingdao`的目录,只有领导组的人可以访问并读写，还有`jishu02`也可以访问，但外人无法访问这个目录

   - 建立一个文件交换目录`jiaohuan`,所有人都能读写，包括`guest`用户，但每个人不能删除别人的文件

   - 建立一个公共的只读文件夹`public`,所有人只读这个文件的内容

   1. 添加组和用户
   
      ![image-20241007141521588](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410071415669.png)
   
      ```bash
      [root@anonymous ~]# groupadd caiwu           # 添加组
      [root@anonymous ~]# groupadd jishu
      [root@anonymous ~]# groupadd lingdao
      [root@anonymous ~]# useradd -g caiwu caiwu01   # 创建新的用户，并将其添加进对应的组中
      [root@anonymous ~]# useradd -g caiwu caiwu02
      [root@anonymous ~]# useradd -g jishu jishu01
      [root@anonymous ~]# useradd -g jishu jishu02
      [root@anonymous ~]# useradd -g lingdao lingdao01
      [root@anonymous ~]# useradd -g lingdao lingdao02
      ```
   
   2. 将`6`个帐户添加到`samba`的帐户中
   
      ![image-20241007141829041](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410071418120.png)
   
      ```bash
      [root@anonymous ~]# smbpasswd -a caiwu01        # 将用户添加进入smbpasswd中
      [root@anonymous ~]# smbpasswd -a caiwu02
      [root@anonymous ~]# smbpasswd -a jishu01
      [root@anonymous ~]# smbpasswd -a jishu02
      [root@anonymous ~]# smbpasswd -a lingdao01
      [root@anonymous ~]# smbpasswd -a lingdao02
      ```
   
   3. 建立宿主目录,交换目录及公共目录
   
      ![image-20241007142741350](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410071427414.png)
   
      ```bash
      [root@anonymous ~]# mkdir /home/samba       # 创建所需目录
      [root@anonymous ~]# mkdir /home/samba/caiwu
      [root@anonymous ~]# mkdir /home/samba/jishu
      [root@anonymous ~]# mkdir /home/samba/lingdao
      [root@anonymous ~]# mkdir /home/samba/jiaohuan
      [root@anonymous ~]# mkdir /home/samba/public
      ```
   
   4. 在相应的文件夹建立文件
   
      ![image-20241007143202506](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410071432561.png)
   
      ```bash
      [root@anonymous ~]# vi /home/samba/caiwu/cafile1
      [root@anonymous ~]# vi /home/samba/caiwu/cafile2
      [root@anonymous ~]# vi /home/samba/lingdao/lifile1
      [root@anonymous ~]# vi /home/samba/lingdao/lifile2
      [root@anonymous ~]# vi /home/samba/jiaohuan/jifile1
      [root@anonymous ~]# vi /home/samba/jiaohuan/jifile2
      [root@anonymous ~]# vi /home/samba/public/pufile1
      [root@anonymous ~]# vi /home/samba/public/pufile2
      ```
   
   5. 修改`samba`配置文件`smb.conf`
      ![image-20241007144209859](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410071442923.png)
   
      ```ini
      [global]
              workgroup = mygroup
              security = user
              encrypt passwords = yes
              smb passwd file = /etc/samba/smbpasswd
      [homes]
              comment = Home Directories
              browseable = no
              writable = yes
              valid users = %S
      [caiwu]
              comment = caiwu
              path = /home/samba/caiwu
              public = no
              vaild users = @caiwu,@lingdao,jishu02
              write list = caiwu01
      [lingdao]
              comment = lingdao
              path = /home/samba/lingdao
              public = no
              browseable = no
              valid users = @lingdao,jishu02
      [jiaohuan]
              comment = Exchange File Directory
              path = /home/samba/jiaohuan
              public = yes
              writable = yes
      [public]
              comment = Read Only Public
              path = /home/samba/public
              public = yes
              read only = yes
      ```
   
   6. 修改权限，使`/home/samba/jiaohuan`目录下的文件使所有人能读写,但不能删除别人的文件
   
      ```bash
      [root@anonymous ~]# chmod -R 1777 /home/samba/jiaohuan
      ```
   
      > **1**：粘滞位（sticky bit）。当这个位设置时，只有文件的所有者或超级用户（root）可以删除或重命名该目录中的文件。
   
   7. 重启`samba`服务器
   
      ```bash
      #systemctl restart smb.service 
      ```
   
   8. 打开结果如下
   
      使用`caiwu01`的账号打开
   
      ![image-20241007150008015](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410071500110.png)
   
      使用`jishu02`账号打开
   
      ![image-20241007151228559](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410071512647.png)
   
      > 这里需要注意由于在设置`lingdao`的时候，设置了`browseable = no`属性，所以导致共享不会出现在网络浏览器中，用户需要知道确切的路径才能访问。所以若想要访问`lingdao`文件夹，则需要输入确切的地址
      >
      > ![image-20241007151419236](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410071514321.png)



# 第三章 DHCP简介

- `DHCP`服务器利用租约机制，实现了对整个网络`IP`地址的自动统一分配和集中管理
- 当客户机向`DHCP`服务器请求分配`IP`地址时`DHCP`服务器会自动从地址池中分配一个未使用的IP地址给客户机，从而实现IP地址的动态分配。
- 在分配`IP`地址给客户机的同时也可为客户机指定默认网关、子网掩码和`DNS`服务器等

**DHCP服务的优点**

- 网络管理员可以验证IP地址和其他配置参数，而不用去检查每个主机。
- `DHCP`服务不会同时租借相同的IP地址给两台主机。
- `DHCP`管理员可以约束特定的计算机使用特定的`IP`地址。
- 可以为每个`DHCP`作用域设置很多选项。
- 客户机在不同子网移动时不需要重新配置`IP`地址。

**DHCP服务的缺点**

- `DHCP`不能发现网络上非`DHCP`客户机已经在使用的`IP`地址
- 当网络上存在多个`DHCP`服务器时，一个`DHCP`服务器不能查出被其他服务器租出去的`IP`地址;

## 3.1 DHCP工作机制

1. DHCP Discover
   - 客户端设备在网络中广播一个 `DHCP Discover` 数据包，以寻找可用的 `DHCP` 服务器。
2. DHCP Offer
   - DHCP 服务器接收到 `Discover` 请求后，回应一个 `DHCP Offer` 数据包，包含可用的 `IP` 地址、子网掩码、网关和租约时间等信息。
3. DHCP Request
   - 客户端收到一个或多个 `Offer` 后，选择其中一个并向该 `DHCP` 服务器发送 `DHCP Request` 数据包，表示接受该服务器提供的配置信息。
4. DHCP Acknowledgment (ACK)
   - `DHCP` 服务器接收到 `Request` 后，确认客户端的请求，并发送一个 `DHCP Acknowledgment（ACK）`数据包，正式将 `IP` 地址分配给客户端。
5.  `IP` 地址使用
   - 客户端收到 `ACK` 后，可以使用分配的 `IP` 地址进行网络通信。在租约期内，客户端可以使用该地址。
6. 租约续约
   - 在租约到期前，客户端可以向 `DHCP` 服务器发送请求，尝试续约以继续使用该 `IP` 地址。

## 3.2 DHCP的安装

1. 安装前的准备工作

   在不确定`Linux`系统中是否已经安装`DHCP`服务的情况下，可以在`shel`提示符输入`rpm -qa | grep dhcp`（如己经安装则不需要下述步骤）

2. `centos8`安装`DHCP`

   ```bash
   [root@anonymous ~]# sudo dnf -y install dhcp-server
   ```

   ![image-20241007155150654](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410071551755.png)

   `Red Hat Enterprise Linux5`安装`DHCP`

   ```bash
   # mount /dev/cdrom /mnt
   # cd /mnt/Server
   # rpm -ivh dhcp-3.0.5-21.el5.i386.rpm
   ```

3. 检查是否安装完成

   ![image-20241007155226062](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410071552125.png)

   ```bash
   [root@anonymous ~]# rpm -qa | grep dhcp
   ```

   

## 3.3 主配置文件dhcpd.conf

- 配置文件山参数、声明、选项组成
- 选项必须使用`option`关键字
- 除块标识(大括号)以外每行必须以分号作为行结束符。
- 以`#`开始的是注释行(在执行时将被忽略)

**常用声明**

声明(declaration)用于描述网络的布局，描述客户，提供客户的地址，或者把一组参数应用到一组声明中。

![image-20241007155830313](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410071558701.png)

**常用参数**

参数(parameter)用于表明如何执行任务，是否要执行任务，或将哪些网络配置选择项发给客户。

![image-20241007155907763](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410071559849.png)

**常用选项**

某些参数必选以 `option` 关键字开头，它们也被称为选项。是用来配置 `DHCP` 客户端的可选参数;而参数配置是必选的或者控制 `DHCP` 服务行为的值。

![image-20241007155943744](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410071559837.png)



## 3.4 书写dhcpd.conf 

首先进入`dhcpd.conf` 页面

```bash
[root@anonymous ~]# vi /etc/dhcp/dhcpd.conf 
```

书写`dhcpd.conf` 页面

```ini
ddns-update-style interim; # 指定动态 DNS 更新的方式为 interim

ignore client-updates; # 忽略来自客户端的更新请求

subnet 192.168.1.0 netmask 255.255.255.0 { # 定义子网及其子网掩码
    # --- default gateway
    option routers 192.168.1.1; # 默认网关
    option subnet-mask 255.255.255.0; # 子网掩码
    option nis-domain "domain.org"; # NIS 域名
    option domain-name "domain.org"; # 域名
    option domain-name-servers 192.168.1.1; # DNS 服务器地址
    option time-offset -18000; # 时区偏移（东部标准时间）
    # option ntpservers 192.168.1.1; # 可选的 NTP 服务器
    # option netbios-name-servers 192.168.1.1; # 可选的 NetBIOS 名称服务器

    # -- 选择点对点节点（默认是混合模式），不建议修改
    # option netbios-node-type 2; 

    range dynamic-bootp 192.168.1.128 192.168.1.254; # 动态分配的 IP 地址范围

    default-lease-time 21600; # 默认租约时间（6小时）
    max-lease-time 43200; # 最大租约时间（12小时）

    # 为特定主机提供固定地址
    host ns {
        next-server marvin.redhat.com; # 指定下一个服务器
        hardware ethernet 12:34:56:78:AB:CD; # 硬件地址（MAC 地址）
        fixed-address 207.175.42.254; # 指定固定 IP 地址
    }
}

```



# 第四章 Web服务器配置

`Web`的工作过程可以归纳为以下几个步骤:

1. 用户启动浏览器，在浏览器地址栏中指定一个`URL`，浏览器便向该`URL`所指定的`Web`服务器发出请求。
2. `Web`服务器接到浏览器的请求后，把`URL`转换成网页所在服务器上的文件路径名
3. `Web`服务器执行`Web`应用程序的服务端代码，对数据库进行操作。
4. 数据库执行的结果返回给Web服务器
5. Web服务器将服务端代码执行的结果大嵌入到客户端请求的文档中。
6. Web服务器向客户端发送页面
7. 客户端浏览显示页面。

## 4.1 Apache简介和特性

**`Apache`简介**

- `Apache`最初是由伊利诺伊大学香槟分校的国家超`4`级计算机应用中心(NCSA)开发的，此后，`Apache`被开放源代码团体的成员不断地发展和加强。
- 开始`Apache`只是`Netscape`网页服务器(现在是Sun ONE)之外的开放源代码选择，后来，它逐在功能和速度上超越了其他的基于`UNIX`的`HTTP`服务器。`1996`年`4`月以来，`Apache`一直是`Internet`上流行的`HTTP`服务器

**`Apache`的特性**

1. 支持最新的`HTTP/1.1`通信协议。
2. 简单而强有力的基于文件的配置过程。
3. 支持`PHP`、`CG1`、`Java Servlets`和`FastCGl`.
4. 支持基于`IP`和基于域名的虚拟主机。
5. 实现了动态共享对象(`DSO`)，允许在运行时动态装载模块。
6. 支持服务器端包含指令(`SSI`)
7. 支持各种方式的`HTTP`认证
8. 支持安全Socket层（SSL）。



## 4.2 所需软件的安装

### 4.2.1 Apache安装

```bash
[root@anonymous ~]# yum install httpd  # 由于我使用的是龙溪，所以可以直接使用yum
```

![image-20241014160233952](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410141602120.png)

验证是否安装成功

![image-20241014160432604](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410141604669.png)

也可以**挂载光盘**然后进行下载。

```bash
# rpm -qa | grep httpd
# mount /dev/cdrom /mnt
# cd /mnt
# cd Server

# rpm -ivh httpd-2.2.3-6.e15.i386.rpm                 # 为Apache服务的主程序包，服务器端必须安装该软件包
# rpm -ivh apr-deve1-l.2 7-11.e15_3.1.i386.rpm
# rpm -ivh httpd-devel-2.2.3-6.e15.i386.rpm			 # 为Apache开发程序包
# rpm ivh libxsit-python-l.1.17-2.e15_2.2.1386.гpm
# rpm ivh system config-hltpd-l.3.3.3-1.e15.nosrch.rpm
```



### 4.2.2 mysql的安装

第一步： 切换到`opt`目录，下载`mysql`的`rpm`包  

```bash
[root@192 opt]# cd /opt                  # 先切换到opt来存放我们的mysql的rpm包
[root@192 opt]# wget https://repo.mysql.com//mysql80-community-release-el7-1.noarch.rpm
```

注意： 如果`wget`命令不可用，我们需要安装`wget`命令  

```bash
# yum -y install wget
```

第二步：进行repo的安装

```bash
[root@192 opt]# rpm -ivh mysql80-community-release-el7-1.noarch.rpm
```

第三步：安装MySQL Server

```bash
[root@192 opt]# yum install mysql-server
```

第四步： 启动MySQL

```bash
[root@192 opt]# systemctl start mysqld.service           # 启动MySQL
[root@192 opt]# systemctl status mysqld.service			# 查看MySQL的状态
```

![image-20241014170908115](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410141709191.png)

**挂载光盘安装**

```bash
# rpm -ivh perl-DBl-1.52-2.el5.i386.rpm
# rpm -ivh mysql-5.0.77-3.e15.i386.rpm
# rpm -ivh perl-DBD-MySQL-3.0007.2.el5.i386.rpm
# rpm -ivh mysql-server-5.0.77-3.el5.i386.rpm
```



第五步：启动完成后去到`/var/log/mysqld.log`或者`/var/log/mysql/mysqld.log`中去看初始密码。

![image-20241015173603466](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410151736650.png)



第七步：进入`mysql`，并修改密码

```bash
[root@192 mysql]# mysql -u root -p
```

![image-20241015173725078](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410151737162.png)

```mysql
mysql> ALTER USER 'root'@'localhost' IDENTIFIED BY 'root';
-- exit 表示退出
mysql> exit
```

![image-20241015174901930](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410151749995.png)

重新尝试登录，成功则说明修改密码成功。



第八步：防火墙开放`3306`端口  

```bash
[root@192 opt]# firewall-cmd --permanent --add-port=3306/tcp # 开放防火墙对3306端口的权限
[root@192 opt]# firewall-cmd --reload # 重载防火墙服务
[root@192 opt]# firewall-cmd --list-ports # 查看防火墙开发的端口有哪些
3306/tcp
```

![image-20241015175248941](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410151752025.png)

> 我开的端口比较多，只要看到`3306`是开启的就行







### 4.2.3 PHP安装

```bash
[root@192 opt]# yum install -y php
```

![image-20241014171218824](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410141712416.png)

**挂载光盘安装**

```bash
# php-5.1.6-15.el5.i386.rpm
# php-cli-5.1.6-15.el5.i386.rpm
# php-common-5.1.6-15.el5.i386.rpm
# php-pdo-5.1.6-15.el5.i386.rpm
# php-mysq1-5.1.6-15.el5.i386.rpm
```



## 4.3 Apache服务器基本配置

​		`Red Hat Enterprise Linux5`中，主配置文件默认在`/etc/httpd/conf`目录中，另外在`/etc/httpd/conf.d`目录中有一些扩展配置文件。安装`Apache`后，系统会将`Apache`服务的配置文件放入固定的目录下:

| 目录              | 说明                                 |
| ----------------- | ------------------------------------ |
| /etc/httpd/conf   | 存放Apache服务器的配置文件           |
| /etc/init.d/httpd | Apache服务的启动脚本                 |
| /var/www/html     | Apache服务器默认Web站点根目录        |
| /usr/bin          | Apache软件包提供的可执行文件安装目录 |
| letc/httpd/logs   | Apache服务器的日志文件目录           |

### 4.3.1 主配置文件httpd.conf

- 整个配置文件总体上划分三个部分(section):第一部分是全局环境设置，主要用于设置`ServerRoot`、主进程号的保存文件、对进程的控制、服务器监听的IP地址和端口以及需要装载的`DSO`(Dynamic SharedObject)模块等;第二部分是服务器的`Web`站点的基本配置;第三部分是虚拟主机段。

### 4.3.2 根目录设置

- `httpd.conf`配置文件中的`ServerRoot`字段用来设置`Apache`的配置文件、错误文件和日志文件的存放目录，并且该目录是整个目录树的根节点(设置服务器的根目录)。默认情况下根路径为`/etc/httpd`，可根据需要进行修改。

```ini
# ServerRoot 目录路径
ServerRoot "/etc/httpd/conf"
```

### 4.3.3 文档目录设置

- `httpd.conf`配置文件中的`DocumentRoot`字段用来设置服务器对外发布的超文本文档存放的路径。

```ini
# DocumentRoot目录路径
DocumentRoot "/var/www/html"
```

### 4.3.4 主机名称设置

- `httpd.con`f配置文件中的`ServerName`字段设置了服务器用于辨别自己的主机名和端口号，主要用于创建转向`URL`，默认情况下是不需要设置这个参数的。

```ini
# ServerName 完整的域名[:端口号]
ServerName www.zhr.com:80
```

### 4.3.5 超时设置

- `httpd.conf`配置文件中的`Timeout`字段用于设置服务器与客户端连接的超时间隔，以秒为单位，**默认时间是`120`秒**。如果`120`秒没有收到或送出任何数据，就切断连接。

```ini
# Timeout 数值
Timeout 360
```

### 4.3.6 两次请求之间等待的最大时间设置

- `KeepAliveTimeout`用于设置持续作用中服务器在两次请求之间等待的最大时间间,以秒为单位，**默认值是`15`**。如果服务器已经完成了一次请求，但在超过了该指令设置的时间间隔后，还没有收到下一次请求，那么服务器就断开连接(两个相邻连接的时间间隔超过`15`秒，就切断连结)。

```ini
# KeepAliveTimeout 数值
KeepAliveTimeout 24
```



## 4.4 Apache的启动与停止

图形界面方式

​	在图形用户界面中，执行""系统""→"管理"→“服务”，弹出服务配置窗口。选中`httpd`复选框，然后通过该窗口上的“开始”、“停止”和“重启”来操作`Apache`服务器

命令行窗口可以输入

```bash
# service httpd start // 启动Apache服务
# service httpd status // 查看Apache是否已经启动
# service httpd stop // 停止Apache服务
```

> ![img](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410151849739.png)
> 出现这种情况，自己在对应的`testpage/index.html`下面创建一个，访问127.0.0.1。显示的就是index.html中的内容

## 4.5 Apache页面编辑实践

### 4.5.1 配置数据库

在根目录下创建一个`test`目录，里面写一个`test.txt`文件

![image-20241015181304667](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410151813743.png)

进入`mysql`输入如下指令

```mysql
-- 创建数据库
CREATE DATABASE student;

-- 切换到 student 数据库
USE student;

-- 创建表 sytable，包含 id（自动递增主键）、name（名字）、age（年龄）、addr（地址）
CREATE TABLE sytable (
    id INT(3) AUTO_INCREMENT NOT NULL PRIMARY KEY,
    name CHAR(6) NOT NULL,
    age INT(2) NOT NULL,
    addr VARCHAR(50) DEFAULT '大连市'
);

-- 插入多条数据
INSERT INTO sytable (name, age, addr) VALUES 
('张三', 20, '大连'),
('李四', 22, '北京市'),
('王五', 23, '上海市'),
('赵六', 24, '广州市');

-- 查询 sytable 表中的所有数据
SELECT * FROM sytable;
```

![image-20241015183119533](https://raw.githubusercontent.com/moyangsun/ty_assist/main/img/MatLab202410151831632.png)



### 4.5.2 编写php

**index.php**

```php
<?php
// 连接数据库
$id=mysql_connect("localhost','root','root');
$ok=mysql_select_db('student',$id);

// 检查连接是否成功
if ($ok) {
     echo "connect mysgl ok<br>";
} else {
   echo "connect mysql error";
}

// 选择数据库
$ok = mysql_select_db('student', $id);
if (!$ok) {
    die("选择数据库失败: " . mysql_error());
}

// 查询语句
$query = "SELECT * FROM sytable";
$result = mysql_query($query, $id);

// 检查查询是否成功
if (!$result) {
    die("查询失败: " . mysql_error());
}

$datanum = mysql_num_rows($result);
echo "<table border='1' align='center' width='400'>
        <tr><td>ID</td><td>Name</td><td>Age</td><td>Addr</td></tr>";

// 遍历结果集
while ($info = mysql_fetch_array($result, MYSQL_ASSOC)) {
    echo "<tr><td>" . $info['id'] . "</td>";
    echo "<td>" . $info['name'] . "</td>";
    echo "<td>" . $info['age'] . "</td>";
    echo "<td>" . $info['addr'] . "</td></tr>";
}
echo "<tr><td><a href='a.html'>插入</a></td>";
echo "<td><a href='b.html'>删除</a></td></tr>";
echo "</table>";

// 关闭数据库连接
mysql_close($id);
?>

```



**a.php**

```php
<?php
// Connect to the database
$id = mysql_connect('localhost', 'root', '123456');
$ok = mysql_select_db('student', $id);

// Check if the connection was successful
if ($ok) {
    echo "connect mysql ok";
} else {
    echo "connect mysql error";
}

// Retrieve POST data
$x = $_POST["name"];
$y = $_POST["age"];
$z = $_POST["addr"];

// Validate inputs
if ($x == "") {
    echo "<br>name is not null <a href='a.html'>return</a>";
    exit();
}
if ($y == "") {
    echo "<br>age is not null <a href='a.html'>return</a>";
    exit();
}
if ($z == "") {
    echo "<br>addr is not null <a href='a.html'>return</a>";
    exit();
}

// Insert data into the table
$query = "INSERT INTO sytable (name, age, addr) VALUES ('$x', '$y', '$z')";
$result = mysql_query($query, $id);
$error = mysql_error();

if ($error) {
    echo "Insert record error: " . $error;
}

// Close the database connection
mysql_close($id);
?>

```



**b.php**

```php
<?php
// Connect to the database
$id = mysql_connect('localhost', 'root', '123456');
$ok = mysql_select_db('student', $id);

// Check if the connection was successful
if ($ok) {
    echo "connect mysql ok";
} else {
    echo "connect mysql error";
}

// Retrieve the ID from POST data
$x = $_POST['id'];

// Validate input
if ($x == "") {
    echo "<br>ID is not null! <a href='a.html'>return</a>";
    exit();
}

// Prepare the delete query
$query = "DELETE FROM sytable WHERE id = $x";
$result = mysql_query($query, $id);
$error = mysql_error();

// Check for errors and display messages
if ($error) {
    echo "<br>Delete record error: " . $error;
} else {
    echo "<br>Delete record succeed <a href='b.html'>return</a>";
}

// Close the database connection
mysql_close($id);
?>

```

