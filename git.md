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
    eval $(ssh-agent -s)
# 添加私钥到ssh-agent
    ssh-add ~./ssh/github_id_rsa
~~~

## 配置
~~~
# 配置用户信息
$ git config --global user.name "your_name"
$ git config --global user.email "your_email"

# 显示当前的git配置
$ git config --list
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
