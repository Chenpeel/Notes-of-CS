# Linux commands



## CentOS

###### internet 

- `ping [web] [domain]`—— 网络测试
- `ifconfig` `ipconfig` `ipaddr` ... —— 查看IP等信息
- `service network restart`—— 网络重启
- `hostname`,`hostnamectl set-hostname  name` —— hostname 设置
- `ssh root@192.168.31.1` —— ssh远程登录 （也可以使用Xshell等）

###### system

- 进程&服务（process，service）

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

    <img src="https://github.com/Chenpeel/Notes-of-CS/blob/master/pics/image-20230524132022579.png" alt="image-20230524132022579" style="zoom:25%;" />

  - `chown user` 改变所有者 

  

  
  
  ​		

###### shell basic commands

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
  -  `tail -f file`  实时跟踪文件信息，vim不会更新
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

###### zip

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













## Ubuntu

