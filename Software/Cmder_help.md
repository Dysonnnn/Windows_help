## [cmder GitHub](https://github.com/cmderdev/cmder)

## 为何使用它
Cmder的主要优点是可移植性。它设计为完全独立，没有外部依赖性，这使其非常适合USB Sticks或云存储。因此，您可以随身携带控制台，别名和二进制文件（如wget，curl和git）。

Cmder的用户界面也设计得更加赏心悦目，您可以在这里比较Cmder和ConEmu之间的主要区别。

##安装
### 单用户便携式配置
1. 下载最新版本
2. 提取存档。注意：此路径不应该是C:\Program Files其他任何需要管理员访问权限才能修改配置文件的路径
3. （可选）将您自己的可执行文件放入%cmder_root%\bin要注入PATH 的文件夹中。
4. 跑 Cmder.exe

### 使用非便携式个人用户配置安装共享Cmder
下载最新版本
将存档解压缩到共享位置。
（可选）将您自己的可执行文件放入%cmder_root%\bin要注入PATH 的文件夹中。
（可选）创建%userprofile%\cmder_config\bin要注入单个用户PATH的文件夹。默认是在第一次运行时自动创建它。
（可选）将您自己的可执行文件放入%userprofile%\cmder_config\bin要注入PATH 的文件夹中。
Cmder.exe使用/C命令行参数运行。例：cmder.exe /C %userprofile%\cmder_config
如果缺少，将创建以下目录结构。

c:\users\[username]\cmder_config
├───bin
└───config
    └───profile.d
共享安装和单个用户配置位置都可以包含一整套init和profile.d脚本，从而实现具有用户覆盖的共享配置。见下文。

## Cmder.exe Command Line Arguments
|Argument	|Description|
|---|----|
| /C [user_root_path]	|Individual user Cmder root folder. Example: %userprofile%\cmder_config|
| /M	|Use conemu-%computername%.xml for ConEmu settings storage instead of user_conemu.xml|
| /REGISTER [ALL, USER]	|Register a Windows Shell Menu shortcut.注册Windows Shell菜单快捷方式。|
| /UNREGISTER |[ALL, USER]	Un-register a Windows Shell Menu shortcut. 取消注册Windows Shell菜单快捷方式。|
| /SINGLE	Start Cmder in single mode.|
| /START [start_path]	|Folder path to start in.|
| /TASK [task_name]|	Task to start after launch.|

example :
```
Cmder.exe /REGISTER ALL
```



#### 在所选文件夹中打开Cmder的快捷方式
1. 以管理员身份打开终端
2. 导航到您放置Cmder的目录
3. 执行.\cmder.exe /REGISTER ALL 如果收到“拒绝访问”消息，请确保在管理员提示符下执行该命令。
在文件资源管理器窗口中，右键单击目录或在目录上，在上下文菜单中查看“Cmder Here”。



**注意：**只有完整版的Cmder附带预先安装的bash，使用的是安装的git-for-windows安装。如果没有其他配置，预配置的Bash选项卡可能无法在Cmder mini版本上运行。

但是，您可以选择使用bash的外部安装，例如Microsoft的Linux子系统（称为WSL）或在Windows上提供POSIX支持的Cygwin项目。


---



[Cmder中文显示不正常解决办法](https://blog.csdn.net/xiangxianghehe/article/details/78103954)
右键->setting->startup->Enviroment，然后加入：

set LANG=zh_CN.UTF8 


[cmder中文乱码、文字重叠等问题](http://www.cnblogs.com/wenber/p/3740948.html)

中文乱码：

将下面的4行命令添加到cmder/config/aliases文件末尾
```
l=ls --show-control-chars 
la=ls -aF --show-control-chars 
ll=ls -alF --show-control-chars 
ls=ls --show-control-chars -F
```

通过快捷键win+alt+p:打开设置面板，去掉Monospace前面的勾选


[Cmder光标错位的问题&VSCode终端光标错位问题](https://www.cnblogs.com/wenqiangit/p/9920953.html)

前面的 λ 或者> 导致的，换成# :
在 Cmder 下的 verndor 目录里，修改 clink.lua 文件大约40和46行，把符号 λ 改为 # 保存即可

光标的样式怎么从竖线改成方块：
settings->Features-Text_cursor->Active_console_Text_cursor 选择Block就可以了
FIGHTING---EVEREY BOD