#### Jenkins学习

​	 Jenkins是一个开源软件项目，旨在提供一个开放易用的软件平台，使软件的持续集成变成可能 。

​	主要功能： 将项目中重复执行的工作自动化的执行 

具体功能：

1.  软件的持续构建和测试，Jenkins提供了一个系统，使开发人员可以很容易的将改变集成到工程中。自动化的，持续的构建有利于提高开发效率。 
2.  监视job的执行，job可以实现很多的功能，Jenkins可以对这些项目进行显示，让用户更清楚的注意到这些损毁的job。 
3.  项目源代码修改的检测，jenkins能够从项目的Subversion/CVS生成最近修改的集合列表，且不会增加Subversion/CVS Repository的负载。 
4.  分布式构建，Jenkins可以将工程构建到多台机器，更好地利用硬件资源，节省时间。 

原理图：

![1589891645068](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\1589891645068.png)



```
<role rolename="manager-gui"/>
<user username="admin" password="admin" roles="manage-gui"/>
```

##### 默认未安装插件

+ Email Extension Plugin
+ Maven Integration plugin

#### 学习目标

+ 学会git、svn、maven、ftp插件
  1. 能从git和svn上拉取文件到工作区
  2. 能把工作区的文件上传到ftp服务器
  3. 会使用maven打包war包和jar包
+ 学会配置windows agent和linux agent，可以把某个任务下发到某个节点进行配置
+ 学会使用pipeline

#### 配置准备工作及简单项目配置示例

1. 进入Jenkins进行初始化
2. 进入插件管理安装maven插件和email插件以及初始化时安装失败的插件
3. 进入全局工具配置配置maven、jdk、git
4. 新建自由风格的项目后，首先进入配置里面的源码管理、选择git或者svn进行配置
5. 配置构建触发器，Build periodically：H 8 * * *每天八点构建；Poll SCM:H/5 * * * *，每五分钟进行检查源代码有没有更新决定构建
6. 在配置中的build里面设置构建方式：Root pom：路径，另一个选项是maven命令 clean test
7. 在构建后操作中设置Public JUnit test result report设置路径：target/surefire-reports/*.xml
8. 在build中选择增加构建步骤Invoke top-level Maven targets，设定maven版本和maven命令

#### Jenkins使用ftp插件上传job工作区中的文件到ftp服务器

1. 安装 Publish Over FTP 插件
2. 在系统设置中添加ftp服务器
3. name随便起，Hostname为ip地址，远程目录可不写，超时时间改成18000000
4. 在项目的配置中的构建后操作，添加Send build artifacts over FTP进行设置
5. name为系统设置里面的name，Source files为job工作区中需要上传到ftp的文件，可以使用通配符进行设置，Remove prefix为需要移除的Source files路径里面的文件夹；Remote directory为上传到ftp服务器上存储的路径，点击保存
6. 当项目构建完成后就会将Source files上传到ftp上
