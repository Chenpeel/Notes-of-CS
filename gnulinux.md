##### Linux commands



## CentOS 7

##### shell basic commands

###### [bash shell](https://github.com/Chenpeel/Notes-of-CS/blob/master/shell.md)

- 常用系统环境变量：`$HOME` `$PWD` `$SHELL` `$USER` 等等
- `env`  显示所有系统环境变量
- `set` 显示所有变量

###### universal commands

- `man command` —— 解释命令信息
- `pwd` (print working directory) 
- `cd` (change directory)
- `ls`  (list)  
  - `ls -a ` (all)
  - `ls -l` (long)
  - `ls -h` (hide hided_file)
- `mkdir` `mkdir -p ~/test/test/test  ` (-parent)——递归创建
- `rmdir` `rmdir -p ~/test/test/test`
- `touch file_name` (create file)
- `cp [] source_file target_file ` (copy) `[-r]` 递归复制
- `rm [] file1 file2 ....`  `[-r -f -v]`  递归删除选项，(force) ,详细信息
- `alias` 别名和原生命令
- `cat [] filename` (catch file)  `[-n]` options 
- `head -n 10` first 10 lines
- `tail -n 12` last 12 lines
  -  `tail -f file`  实时跟踪文件信息，[vim操作](https://github.com/Chenpeel/Notes-of-CS/blob/master/vim.md)不会更新
- `more file`
- `less file` 
- `echo string` 
  - `echo  "string" > file` (replace file)
  - `echo "string" >> file`  (append to file)
  - `echo  $[] ` 
- `ln -s [source_file] [new_file]` (link)
- `history [num, -c]`,`!90`
- `date [-d "1 days ago"]  [+%Y-%m-%d-%H:%M:%S] [+%s]` `ntpdate`
- `cal 2022 -m` 日历
- `find PATH  [-name [file_name]] [-user [user_name]][-size [b c w k M G]]`
- `update db` 更新数据库 后`locate filename`
- `which file_name` 
- `whereis file_name`
- ` ls ~/ | grep [-n] test.*` -n行号
- `wc`  (word count)

##### zip

- gzip

  - `gzip file_name`
  - `gunzip file_name`

- zip

  - `zip new_name.zip old_file`
  - `zip -r new.zip old_file`
  - `unzip -d PATH file.zip` 

- tar

  - `tar [] file.tar.gz`

    | options |     functions      |
    | :-----: | :----------------: |
    |  `-z`   |    打包同时压缩    |
    |   `c`   |  产生.tar打包文件  |
    |  `-v`   |    显示详细信息    |
    |  `-f`   | 指定压缩后的文件名 |
    |  `-x`   |    解包.tar文件    |
    |  `-C`   |   解压到指定目录   |

##### internet 

- `ping [web] [domain]`—— 网络测试

- `ifconfig` `ipconfig` `ipaddr` ... —— 查看IP等信息

- `service network restart`—— 网络重启

- `hostname`,`hostnamectl set-hostname  name` —— hostname 设置

- `ssh root@192.168.31.1` —— ssh远程登录 （也可以使用Xshell等）

- `netstat [-anp]/[-nlp] | grep uid/port_id`

  | options |               functions                |
  | :-----: | :------------------------------------: |
  | ` -a `  |    显示所有正在监听和未监听的套接字    |
  | ` -n `  | 拒绝显示别名，能显示数字的全部显示数字 |
  | ` -l `  |         仅列出在监听的服务状态         |
  | ` -p `  |         表示显示哪个进程在调用         |

  - Proto（协议）
  - RECV-Q（未拷贝的字节数）
  - SEND-Q（未发送的字节数）
  - Local Address（本地地址）
  - Foreign Address （远程地址）
  - state（状态）


##### system

进程&服务（process，service）

###### service

- `systemctl start|stop|restart status service_name`

- 系统运行级别

  - `0~7`

    | levels |                   explainations                   |
    | :----: | :-----------------------------------------------: |
    |   0    |                   系统停机状态                    |
    |   1    | 但用户工作状态，root，用于系统维护，禁止远程登录  |
    |   2    |          多用户状态（无NFS），不支持网络          |
    |   3    | 完全多用户模式（NFS），登陆后进入控制台命令行模式 |
    |   4    |                     保留状态                      |
    |   5    |           X11控制台，登入后进入GUI界面            |
    |   6    |                系统正常关闭并重启                 |

  -  `multi-user.target ` 级别3

  -  ` graphicl.target` 级别5

  -  `systemctl get-default`查看运行级别

  -  `systemctl set-default TARGET.target`设置运行级别

  - `chkconfig network of|off`,`chkconfig --level num network on|off` 网络服务状态改变

- 系统管理，关机重启

  - `shutdown`,`shutdown -c` ,` shutdown time`   `-h -H -p -r now `   ——关机
  - `sync ` ——将数据有内存同步到硬盘
  - `halt`——停机，关闭系统，但不断电，内存可能还有救
  - `poweroff`——关机断电
  - `reboot`——重启

- user manage

  - `useradd user_name`

  - `useradd -g group_name user_name` 设置组

  - `passwd user_name`  设置用户名

  - `id user_name` 查看uid

  - `su user_name` 切换用户

    - `user_name ALL=(ALL) [NOPASSWD:]ALL`	sudo 权限

  - `usermod -g group_name user_name` 

  - `groupadd group_name` & `groupdel group_name`

  - `chmod 777` 文件操作权限wxr 

    <img src="https://github.com/Chenpeel/Notes-of-CS/blob/master/pics/image-20230524132022579.png" alt="image-20230524132022579" style="zoom:10%;" />

  - `chown user` 改变所有者 


###### process

- 查看进程`ps` (process status)

  - `ps [] | grep key `

    | options |                 functions                  |
    | :-----: | :----------------------------------------: |
    |    a    |        列出带有终端的所有用户的进程        |
    |    u    | 列出当前用户的所有进程，包括没有终端的进程 |
    |    x    |          面向用户的友好型风格显示          |
    |   -e    |                列出所有进程                |
    |   -u    |         列出某个用户关联的所有进程         |
    |   -f    |           显示完整格式的进程列表           |

    - uid用户名
    - pid 进程ID
    - ppid父进程ID
    - VSZ占用的虚拟内存
    - RSS占用的物理内存（LRU内存置换算法）
    - TTY使用的终端
      - pts0-255虚拟终端
      - tty1图形化终端
      - tty2-tty6本地字符界面
    - STAT状态（status）
      - R：运行状态
      - S：睡眠状态
      - T：暂停状态
      - Z：僵尸状态
      - s：包含子进程
      - l：多线程
      - +：前台显示
      - <：优先级高
      - N：优先级低

- 终止进程`kill [-9] [all][pid] ` `[-9]`force kill,`[all]` 杀疯了

- `pstree` 显示进程树

- `top[]` 实时显示进程状况 `[-d 1 ,  -i,  -p]`

- `crontab` 系统定时任务

  - `crontab [-l,-e,-r]` list , edit, remove
  - `crontab -e` --> vim
    - `***** [commands] ` min1,min2,min3/hour/day/month/weekday 、 `*/n` for how long

  

##### disk operators

- `du file/dirc` （disk usage）
  - `-h` 易阅读的方式显示
  - `-a` 不仅查看子目录大小，还要包括文件
  - `-c` 显示所有的文件和子目录大小后，显示总和
  - `-s` 只显示总和
  - `--max-depth=num` 最大深度

- `df -h` (disk free)
  - 内存和swap分区都使用tmps 
  - devtmpfs文件系统挂载
- `free -h ` 内存查看
- `lsblk -f` 查看设备挂载情况
  - sda1 | vda1 | hda1 硬盘情况
  - s表示SATA、SCSI硬盘，v表示虚拟硬盘，h表示IDE硬盘
  - a表示第一块硬盘
  - 数字表示分区

- `mount` & `umount`
- `fdisk -l` 查看硬盘情况
  - `fdisk /dev/sdb`
  - `mkfs -t xfs /dev/sdb`




##### RPM (Redhat Package Manager)

- firefox-102.10.0-1.el9.aarch64
  - `app_name - version . 硬件平台. rpm``
- `rpm -qa` (query all)  
- `rpm -qi app_name ` (query info)
- `rpm -e --nodeps app_name`  (no depandence) 卸载程序
- `rpm -ivh --nodeps app_name` install with verbose and hash\

##### yum (Yellow dog Updater Modified)

- ` yum  -y  install/update/check-update/remove/list/clean/deplist  `
- 配置yum源
  - `/etc/yum.repo.d`



## Ubuntu

##### Commands

- 其他命令基本与<a href="#CentOS 7">CentOS 7</a> 相同或相似

##### APT (Advanced Packaging Tools) 包管理

- [更改apt安装源](https://github.com/Chenpeel/Notes-of-CS/blob/master/shsh/apt_repo_change.sh)
  - 将apt_repo_change.sh复制到本地
  - terminal键入`sh apt_repo_change.sh` 即可执行（Ubuntu 20版本）
  - [其他版本(清华镜像)](http://mirrors.ustc.edu.cn)















