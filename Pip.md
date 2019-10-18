### 升级pip本身
  - python -m pip install --upgrade/-U pip
  - pip install --upgrage/-U pip
### 添加镜像源
  Linux   
  在“ ~/.pip/pip.conf ” 下写入如下内容（没有此文件则创建一个） 
~~~
[global]
index-url = https://pypi.tuna.tsinghua.edu.cn/simple
~~~

  Window  
  在 “C:\User\xx\pip ” 下新建 pip.ini文件，添加如下内容  
~~~
[global]
index-url = https://pypi.tuna.tsinghua.edu.cn/simple
~~~
  
### 安装包
#### 安装最新包
  - pip install package_name
#### 安装指定版本包
  - pip install package_name==1.1.1
  - pip install "package_name>=1.2"
  - pip install -r requirements.txt (批量安装列表）
### 卸载包
  - pip uninstall package_name
  - pip uninstall requirements.txt (批量卸载列表）
### 升级包
  - pip install --upgrage/-U package_name
### 查询可升级的包
  - pip list -o/--outdate
### 导出包
  - pip freeze > requiremwnts.txt
### 打包包
  - pip wheel package_name
### 遇到利用pip安装报错可尝试
  - pip install —upgrade setuptools
  - pip install ez_setup
