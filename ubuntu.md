## 在docker中安装使用openssh-server
1. 以守护进程方式启动容器并进入容器
~~~bash
sudo docker run -d -it --net=host --name=CONTAIN_NAME IMAGE_ID bash
sudo docker exec -it CONTAIN_NAME bash
~~~

2. 修改root密码，用于后续远程登录
~~~bash
passwd
输入新密码
~~~

3. 安装openssh-server
~~~bash
apt-get update
apt-get install openssh-server
# 手动创建/var/run/sshd 目录，否则sshd启动会报错
mkdir -p /var/run/sshd
~~~

4. 更改监听端口并允许root用户用密码登录
~~~bash
vi /etc/ssh/sshd_config
修改 
Port 22
PermitRootLogin yes
~~~

5. 以守护进程方式启动 ssh-server
~~~bash
/usr/sbin/sshd -D &

如果想重启
ps -ef | grep sshd
kill -9 PID 
/usr/sbin/sshd -D &
~~~
