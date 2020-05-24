#### Linux中yum和wget的区别：

+ yum是一种安装工具。如果想安装软件，最好使用yum安装，基本上是一步完成安装软件。
+  wget是一种下载工具。可以下载网络上的资源，有点类似于迅雷。  

#### Linux安装配置maven

 1. 首先安装wget命令： yum -y install wget

 2. 使用wget命令下载压缩包：wget https://mirrors.tuna.tsinghua.edu.cn/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.tar.gz

 3. 解压压缩包：tar -zxvf apache-maven-3.6.3-bin.tar.gz

 4. 修改解压后的名字：mv apache-maven-3.6.3-bin.tar.gz maven3.6.3

 5. 将maven加入环境变量，通过cat <<EOF>>/etc/profile命令向/etc/profile文件中追加内容

    export M2_HOME=/usr/local/maven/maven3.6.3

    export PATH=$PATH:$M2_HOME/bin

    EOF

    注意=号左右不可以有空格，否则会报错

	6. 使用source /etc/profile命令使配置生效

	7. 最后通过mvn -version查看maven版本看看是否配置成功

#### Linux中设置使用VIM命令默认显示行号

1. 使用vim /etc/vimrc打开配置文件
2. 在末尾添加 set nu
3. 保存并退出

#### 使用XShelle上传文件到linux

1. 安装lrszsz：yum -y install lrzsz
2. 检查是否安装成功：rpm -qa lrzsz
3. 上传文件到linux：rz -y

#### Linux安装jenkins

1. 下载linux版本的jenkins的rpm包:
   + 官网下载，通过rz -y上传到linux
   + wget https://pkg.jenkins.io/redhat-stable/jenkins-2.222.3-1.1.noarch.rpm
2. 安装rpm包：rpm -ivh jenkins-2.222.3-1.1.noarch.rpm
3. 查看jenkins安装路径：whereis jenkins
4. 进入安装目录后，启动jenkins：service jenkins start
5. 浏览器登录：linuxip:8080访问
6. 读取密码：cat /var/lib/jenkins/secrets/initialAdminPassword

#### Linux安装git

1. 从github下载压缩包： https://github.com/git/git/releases 

   + 通过xshell上传
   + wget https://github.com/git/git/archive/v2.26.2.tar.gz

2. 解压：tar -zxvf git-2.26.2.tar.gz

3. 进入目录安装编译依赖：yum install curl-devel expat-devel gettext-devel openssl-devel zlib-devel gcc perl-ExtUtils-MakeMaker

4. 卸载安装编译依赖时安装的旧版git：yum -y remove git

5. 编译git源码：make prefix=/usr/local/git/git-2.26.2 all

6. 安装git至/usr/local/git/git-2.26.2:make prefix=/usr/local/git/git-2.26.2 install

7. 配置环境变量：在/etc/profile文件尾部添加：export PATH=$PATH:/usr/local/git/git-2.26.2/bin

8. 使配置文件生效：source /etc/profile

9. 查看Git是否安装完成：git --version

   若有此错误：expat.h: No such file or directory

   则可以使用命令：yum install expat-devel

#### Linux下解除端口占用

1. 找占用端口进程的pid：sudo lsof -i:8080
2. 终止进程：sudo kill -9 pid

#### Linux关闭防火墙命令

+ 查看防火墙状态：systemctl status firewalld；service iptables status
+ 暂时关闭防火墙：systemctl stop firewalld；service iptables stop
+ 永久关闭防火墙：systemctl disable firewalld；chkconfig iptables off
+ 重启防火墙：systemctl enable firewalld；service iptables restart
+ 永久关闭后重启：chkconfig iptables on