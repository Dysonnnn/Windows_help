mysql8.0.11

log
管理员模式开启powershell
```
Windows PowerShell
版权所有 (C) Microsoft Corporation。保留所有权利。

PS C:\Windows\system32> mysqld --initialize --console
2019-04-24T09:06:00.812468Z 0 [System] [MY-013169] [Server] C:\Program Files\mysql-8.0.11-winx64\bin\mysqld.exe (mysqld 8.0.11) initializing of server in progress as process 27112
2019-04-24T09:06:04.453544Z 5 [Note] [MY-010454] [Server] A temporary password is generated for root@localhost: tT;=D2lIOa)X
2019-04-24T09:06:06.112289Z 0 [System] [MY-013170] [Server] C:\Program Files\mysql-8.0.11-winx64\bin\mysqld.exe (mysqld 8.0.11) initializing of server has completed
PS C:\Windows\system32>
PS C:\Windows\system32> mysqld --install mysql
Service successfully installed.
PS C:\Windows\system32> net start mysql
mysql 服务正在启动 ..
mysql 服务已经启动成功。

PS C:\Windows\system32> mysql -uroot -p
Enter password: ************
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 8
Server version: 8.0.11

Copyright (c) 2000, 2018, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> alter user 'root'@'localhost' identified by 'mysql';
Query OK, 0 rows affected (0.01 sec)

mysql> net stop mysql
    -> ;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'net stop mysql' at line 1
mysql>
```