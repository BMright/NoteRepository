#### Git命令练习

1. 创建版本库：git init

2. 将文件添加到暂存区：git add readme.txt   添加全部：git add .

3. 查看是否有文件未提交：git status

4. 查看未提交文件修改内容：git diff readme.txt

5. 将暂存区的文件提交到到版本库：git commit -m "message"

6. 将未进入暂存区的文件一并提交到版本库：git commit -am "message" 但是不能提交未被跟踪过的文件，即没有加入版本库的文件

7. 设置邮箱：git config --global user.email "1361585641@qq.com"

8. 设置用户名：git config --global user.name "BMright"

9. 查看历史记录：git log

10. 版本回退：

    + git reset --hard HEAD~1
    + git reset --hard 版本号
    + 获取版本号：git reflog

11. 查看文件内容：cat ./test/test1.txt

12. 撤销操作：

    + 撤销未加入暂存区的操作：

      + git checkout -- file  注意：-- 表示撤销命令，如果没有则变成创建分支命令
      + git restore file

    + 撤销加入暂存区的操作：

      ‘git restore --staged file

13. 删除操作

    1. 从本地移除文件：rm file  删除文件夹加上 -r：rm -r directory
    2. 提交删除

#### Git连接远程仓库

1. 生成密钥（SSH key）：$ ssh-keygen -t rsa -C "1361585641@qq.com" 

2. 添加密钥： 将生成的密钥即.ssh/id_rsa.pub中内容全部复制，在github的 Settings-->SSH and GPG keys-->New SSH key，key中粘贴复制的内容(Title自定义)。

3. 验证密钥是否添加成功：

   +  github：ssh -T git@github.com
   + 码云：ssh -T git@gitee.com

4. 连接远程仓库：git remote add origin git@github.com:yourName/repositoryname.git

5. 上传文件到远程仓库：git push origin master

6. 从远程仓库拉取文件：git pull origin master

7. 查看远程连接：git remote -v

8. 删除远程连接：git remote rm origin

9. 从远程仓库克隆项目到本地：git clone https://github.com/BMright/RemoteTest.git

10. 第一次连接本地和远程仓库时报错，可以通过命令强行使两段不相干的代码合并：

     git pull origin master --allow-unrelated-histories 