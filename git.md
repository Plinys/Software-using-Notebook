# Git 笔记
## 安装
**Linux**
~~~
sudo apt-get install git
~~~
**Windows**     

打开网址 [git下载](http://git-scm.com/download/win)下载安装程序，根据提示安装，     
在安装过程中建议选择默认编辑器为VScode, 此后便可以在命令行使用命令 "code filename"打开文件
## 生成密钥
先进入到 "~/.ssh" 目录，不存在则创建     
> 常用命令  
> ssh-keygen -f id_name -C "your_email"
~~~
ssh-keygen 参数说明

    -b
    创建密钥的位数。缺省值2048，最小值512，位数越多，验证速度越慢

    -C
    注释，通常填写email

    -f 
    指定文件名称
    
    -t
    指定生成密钥的算法，缺省rsa, 还有dsa, rsal
~~~
## 将ssh密钥添加到 ssh-agent

~~~
# 先在git bash 中后台启动ssh-agent
    eval "$(ssh-agent -s)"
# 添加私钥到ssh-agent
    ssh-add ~/.ssh/github_id_rsa
~~~
[如何自启动ssh-agent](https://help.github.com/cn/articles/working-with-ssh-key-passphrases)

## 验证ssh连接
    $ ssh -T git@github.com

## 配置
~~~
# 配置用户信息
$ git config --global user.name "your_name"
$ git config --global user.email "your_email"

# 显示当前的git配置
$ git config --list

# 查看某一项配置
$ git config [key]
~~~
## 增加/删除文件
~~~
# 添加制定文件到暂存区
$ git add [file1] [file2] ...

# 添加制定目录到暂存区,包括子目录
$ git add [dir]

# 添加当前所有文件到暂存区
$ git add .

# 删除工作区文件，并将这次删除放入暂存区
$ git rm [file1] [file2] ...

# 停止追踪文件，但该文件会保留在工作区
$ git rm --cached [file]

# 改名文件，并将记入暂存区
$ git mv [file-original] [file-renames]
~~~
## 代码提交
~~~
# 提交暂存区到仓库区
$ git commit -m [message]

# 提交暂存区的指定文件到仓库区
$ git commit [file1] [file2] ... -m [message]

# 提交时显示所有的diff信息
$ git commit -v
~~~
## 远程操作
~~~
# 列出所有远程主机
$ git remote

# 列出远程主机并查看网址
$ git remote -v

# 将远程仓库更新取回本地（并不合并）
$ git fetch <远程主机名> [分支名]
e: git fetch origin master

# 合并分支
$ git merge origin/master

# 将远程仓库更新取回并合并
$ git pull <远程主机名> <远程分支名>:<本地分支名>
e: git pull origin master
~~~
## 忽略文件
~~~
在仓库目录下新建 ".gitignore" 文件
.gitignore 文件规范如下
    $ 所有空行或者以 # 开头的行都会被Git忽略
    $ 可以使用标准的glob模式匹配
    $ 匹配模式可以以 "/" 开头防止递归
    $ 匹配模式可以以 "/" 结尾指定目录
    $ 要忽略指定模式以外的文件或目录，可以在模式前加上感叹号"!" 取反

glob模式
    $ 星号 "*" 匹配零个或多个任意字符
    $ [abc] 匹配任何一个在方括号内的字符
    $ "?" 问号只匹配一个任意字符
    $ 两个星号 "**" 表示匹配任意中间目录
~~~

## 版本回滚
~~~
# 回滚到上一次提交的版本
$ git reset --hard HEAD^

# 回滚到上上次提交的版本
$ git reset --hard HEAD^^

# 回滚到具体某一版本
$ git reset --hard commit-id

# 优雅查看提交历史，其中包含commit-id和提交信息
$ git log --pretty=oneline

# 查看每次提交的命令
$ git reflog
~~~
