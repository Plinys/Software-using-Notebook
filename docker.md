# Docker
## 镜像
~~~
# 导入镜像文件
$ docker load file

~~~
## 容器
~~~
# 查看当前运行容器 （显示所有容器，包括退出的,加上参数 -a）
$ docker ps
$ docker container ls

# 导入容器快照到本地镜像库
$ docker import file/URL - [REPOSITORY[:TAG]]
& 与 docker load 的差别
  ：容器快照文件将丢弃所有的历史纪录和元数据信息
  ：镜像存储文件将保存完整记录
~~~