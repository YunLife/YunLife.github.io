后台启动jar包
nohup java -jar ***.jar &
查看java进程
ps -ef | grep java
杀掉进程
kill -9 [pid]

linux下如果不能使用rz sz命令，就需要安装rz sz命令，安装命令为：
yum install lrzsz -y

java设置启动参数
java -Xms128m -Xmx256m -jar xxx.jar --server.port =8080
-Xms128m 设置jvm堆最小内存128m
 -Xmx256m  设置jvm堆最大内存256m


linux下安装jdk
首先下载jdk，上传至Linux服务器
解压命令如下
tar -zxv -f jdk-8u201-linux-x64.tar.gz
解压完成后，配置环境变量在 /etc/profile文件中添加如下配置
JAVA_HOME={jdk目录}
PATH=$JAVA_HOME/bin:$PATH
CLASSPATH=$JAVA_HOME/jre/lib/ext:$JAVA_HOME/lib/tools.jar
export PATH JAVA_HOME CLASSPATH
配置完成后，用命令是配置重新生效
source /etc/profile
然后查看java安装是否成功，java -version

linux下tomcat的启动

Linux下tomcat服务的启动、关闭与错误跟踪，使用PuTTy远程连接到服务器以后，通常通过以下几种方式启动关闭tomcat服务：
切换到tomcat主目录下的bin目录（cd usr/local/tomcat/bin）
1，启动tomcat服务
方式一：直接启动 ./startup.sh
方式二：作为服务启动 nohup ./startup.sh &
方式三：控制台动态输出方式启动 ./catalina.sh run 动态地显示tomcat后台的控制台输出信息,Ctrl+C后退出并关闭服务
解释：
通过方式一、方式三启动的tomcat有个弊端，当客户端连接断开的时候，tomcat服务也会立即停止，通过方式二可以作为linux服务一直运行
通过方式一、方式二方式启动的tomcat，其日志会写到相应的日志文件中，而不能动态地查看tomcat控制台的输出信息与错误情况，通过方式三可以以控制台模式启动tomcat服务，
直接看到程序运行时后台的控制台输出信息，不必每次都要很麻烦的打开catalina.out日志文件进行查看，这样便于跟踪查阅后台输出信息。tomcat控制台信息包括log4j和System.out.println()等输出的信息。
2，关闭tomcat服务
./shutdown.sh

Linux解压命令
linux下提供了zip和unzip程序，zip是压缩程序，unzip是解压程序。它们的参数选项很多，可用命令zip -help和unzip -help查看，这里只做简单介绍，举例说明一下其用法：

# zip test.zip test.jpg test.png
这条命令是将test.jpg和test.png压缩成一个zip包
# zip test.zip *.jpg
这条命令是将所有.jpg的文件压缩成一个zip包
# zip -r test.zip test
这条命令是将文件夹test压缩成一个zip包
# unzip test.zip
这条命令是将test.zip中的所有文件解压出来

Linux下安装mysql
下载mysql
wget http://repo.mysql.com/mysql-community-release-el7-5.noarch.rpm
解压mysql
rpm -ivh mysql-community-release-el7-5.noarch.rpm
yum update
yum install mysql-server