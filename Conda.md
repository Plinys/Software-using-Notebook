## 环境管理
### 查看环境管理所有命令帮助
  - conda env -h
### 创建环境
  - conda create --name env_name python=3.6
### 列举当前所有环境
  - conda env list
### 进入某个环境
  - activate env_name
### 退出当前环境
  - deactivate
### 复制某个环境
  - conda create --name new_env_name --clone old_env_name
### 删除某个环境
conda remove --name env_name --all
### 分享某个环境
  - conda env export > environment.yml
  - conda env create -f environment.yml
## 包管理
### 列出环境下所有包
  - conda list
### 安装包
  - conda install package_name
### 更新包
  - conda update paackage_name
  - conda update --all
### 删除包
  - conda remove package_name
### 移除无用的安装失败的包及缓存
  - conda clean --all
