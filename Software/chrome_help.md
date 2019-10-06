[禁用software_reporter_tool.exe 解决CPU高占用率的问题](https://as32.net/blog/9196)

今天开机后，从几分钟到半个小时之间，感觉机器反应有些慢，发现CPU占用80-90%。查看任务管理器，

有一个 software_reporter_tool.exe 的程序占用了一半的CPU使用率。 转到文件所在文件夹查看，发现是 Google Chrome 使用的一个文件。

查询该文件，发现 software_reporter_tool.exe  会扫描系统，类似 
Chrome 的一个计划任务，每周启动扫描 一次，运行大约20-25分钟。它会扫描 
Google Chrome 浏览器 未能正常运行的程序问题，比如多次未正常关闭 
Chrome ，或某些恶意软件或应用程序导致Chrome浏览器运行中出现错误，它就会扫面检查问题通知你并删除该受感染程序。

简单来说，Software Reporter Tool 是 Chrome 清理报告工具 ，  帮助维持Google Chrome正常运行。但是效率上的低下，让我感觉到系统延迟，要想办法让他以后停止执行。

文件位置：  C：\ Users \ {您的用户名} \ AppData \ Local \ Google \ Chrome \用户数据\ SwReporter \ {版本号}\ software_reporter_tool.exe 

网上看到方法是，修改 Chrome 设置，“ 将使用情况统计信息和崩溃报告自动发送给 Google ”的选项关闭，我看了我的设置本身就是关闭的。解决无效，然后自己找到了用最简单的方法， 
C:\Users\Administrator\AppData\Local\Google\Chrome\User Data\SwReporter\36.184.200 下编辑 manifest.json文件：

“allow-reporter-logs”: true 修改为 “allow-reporter-logs”: false

这样它会自己停止运行，并且下次不再启动。


