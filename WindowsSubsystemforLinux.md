安装**Windows10内置Linux子系统**

1. 打开  控制面板\程序 启动或关闭Windows功能，勾选  
- [x] 适用于Linux的Windows子系统

根据提示重启。

2. 从Microsoft Store安装
本节适用于Windows build 16215或更高版本
下载系统，下载完成之后，点击启动即可。

例如：下载Ubuntu 


3. 启动ubuntu
在开始菜单可以看到 Ubuntu 图标，点击启动即可

启动后的内容如下：
设置用户名和密码

```bash
Installing, this may take a few minutes...
Please create a default UNIX user account. The username does not need to match your Windows username.
For more information visit: https://aka.ms/wslusers
Enter new UNIX username: dysonnnn   
Enter new UNIX password:
Retype new UNIX password:
passwd: password updated successfully
Installation successful!
To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

dysonnnn@DESKTOP-C7500B8:~$ ls
dysonnnn@DESKTOP-C7500B8:~$

```


```bash
dysonnnn@DESKTOP-C7500B8:/etc$ uname -a
Linux DESKTOP-C7500B8 4.4.0-17134-Microsoft #523-Microsoft Mon Dec 31 17:49:00 PST 2018 x86_64 x86_64 x86_64 GNU/Linux
```

修改更新源：


```bash
# 备份原来的源
sudo cp sources.list sources.list_backup
# 修改源文件
sudo vim sources.list
```
>将 http://archive.ubuntu.com/ubuntu/ 、 http://security.ubuntu.com/ubuntu/  两个地址修改为  http://mirrors.aliyun.com/ubuntu/


```bash
# See http://help.ubuntu.com/community/UpgradeNotes for how to upgrade to
# newer versions of the distribution.

## origin sources 
#deb http://archive.ubuntu.com/ubuntu/ bionic-updates main restricted
#deb http://archive.ubuntu.com/ubuntu/ bionic universe
#deb http://archive.ubuntu.com/ubuntu/ bionic-updates universe
#deb http://archive.ubuntu.com/ubuntu/ bionic multiverse
#deb http://archive.ubuntu.com/ubuntu/ bionic-updates multiverse
#deb http://archive.ubuntu.com/ubuntu/ bionic-backports main restricted universe multiverse
#deb http://security.ubuntu.com/ubuntu/ bionic-security main restricted
#deb http://security.ubuntu.com/ubuntu/ bionic-security universe
#deb http://security.ubuntu.com/ubuntu/ bionic-security multiverse

# new sources 
# http://mirrors.aliyun.com/ubuntu/
deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted
deb http://mirrors.aliyun.com/ubuntu/ bionic universe
deb http://mirrors.aliyun.com/ubuntu/ bionic-updates universe
deb http://mirrors.aliyun.com/ubuntu/ bionic multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-updates multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted
deb http://mirrors.aliyun.com/ubuntu/ bionic-security universe
deb http://mirrors.aliyun.com/ubuntu/ bionic-security multiverse

```

```
deb http://mirrors.ustc.edu.cn/ubuntu/ xenial main restricted universe multiverse
deb http://mirrors.ustc.edu.cn/ubuntu/ xenial-security main restricted universe multiverse
deb http://mirrors.ustc.edu.cn/ubuntu/ xenial-updates main restricted universe multiverse
deb http://mirrors.ustc.edu.cn/ubuntu/ xenial-proposed main restricted universe multiverse
deb http://mirrors.ustc.edu.cn/ubuntu/ xenial-backports main restricted universe multiverse
deb-src http://mirrors.ustc.edu.cn/ubuntu/ xenial main restricted universe multiverse
deb-src http://mirrors.ustc.edu.cn/ubuntu/ xenial-security main restricted universe multiverse
deb-src http://mirrors.ustc.edu.cn/ubuntu/ xenial-updates main restricted universe multiverse
deb-src http://mirrors.ustc.edu.cn/ubuntu/ xenial-proposed main restricted universe multiverse
deb-src http://mirrors.ustc.edu.cn/ubuntu/ xenial-backports main restricted universe multiverse
# --------------------- 
# 作者：Giaming 
# 来源：CSDN 
# 原文：https://blog.csdn.net/qq_33532713/article/details/86438807 
# 版权声明：本文为博主原创文章，转载请附上博文链接！
```


输入命令sudo apt-get update进行软件源更新
```
sudo apt-get update
```

安装软件
```
sudo apt-get install ssh git zsh wget 
```


- windows 系统盘 在 /mnt 目录

### 开启ssh，远程连接到电脑
[win10上使用Xshell通过ssh连接Linux](https://www.cnblogs.com/ACDIV/p/9047825.html)

1. 默认安装的ssh是缺少密钥的，如果你不想手动配置aes等几种密钥的话，最好是先删了ssh，然后再重新安装

```
sudo apt-get remove --purge openssh-server
sudo apt-get install openssh-server
```

修改配置：
```bash
$ sudo vim /etc/ssh/sshd_config
```

```bash
# filename : sshd_config
Port xxxx # 开启端口xxxx
ListenAddress 0.0.0.0 # 开启连接地址
```

查看sshd的端口情况，使用命令
```
sudo netstat -anp|grep sshd
```
[Linux系统配置ssh监听多个端口方法](https://blog.csdn.net/zhangmingcai/article/details/82895824)



重启sshd，命令为
```bash
sudo service sshd restart
# sshd: unrecognized service

# or
sudo /etc/init.d/ssh restart
```




设置zsh替换掉原有的shell 
```
chsh -s /bin/zsh 
```
[ubuntu 14.04下配置terminal为zsh默认环境](https://blog.csdn.net/zxgdll/article/details/70858857)
