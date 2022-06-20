Windows环境下redis重启

sqwu 2020-05-01 19:26:11  7967  收藏 9
版权
在redis安装的目录下打开cmd窗口

输入以下命令打开启动redis

redis-server redis.windows.conf
如果提示 Creating Server TCP listening socket *:6379: bind: No error，需要重启redis

重启步骤：

依次输入以下指令
1.

redis-cli -h 127.0.0.1 -p 6379 shutdown
2.如果输入上述指令，结果提示NOAUTH Authentication required.说明需要输入密码，继续输入指令：


redis-cli.exe
3.root是自己设置的redis密码

auth "root"
4.

 shutdown
5.这时redis已经成功关闭，再次输入指令启动服务

redis-server.exe redis.windows.conf
————————————————
版权声明：本文为CSDN博主「sqwu」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/qq_42345108/article/details/105881250