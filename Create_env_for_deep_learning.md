# Create A Environment for Deep Learning (In Linux)

## 1.Download and Install Miniconda
    # Download Miniconda use TsingHua mirrors
    $ wget https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/Miniconda3-latest-Linux-x86_64.sh
    
    # Install Miniconda 
    $ bash Miniconda3-latest-Linux-x86_64.sh
    $ source ~/.bashrc

## 2.Config mirror channels for conda and pip
    # For conda
    $ conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
    $ conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
    
    # For pip
      create file '~/.pip/pip.conf' if not exists and write the following:
      "
      [global]
      index-url = https://pypi.tuna.tsinghua.edu.cn/simple
      "

## 3.Creating a python environment and activate it
    # Create environment
    $ conda create --name [env_name] python=3.7
    
    # Activate environment
    $ conda activate [env_name]

## 4.Install pytorch
    详见[pytorch官网](https://pytorch.org/get-started/locally/)     
    # Cheack CUDA's version     
    (1) $ nvcc -V       
    (2) $ cat /usr/local/cuda/version.txt       
    
    # Install pytorch use conda     
    $ conda install pytorch torchvision cudatoolkit=[CUDA's version]
    
## 5.Install other packages
    # OpenCV
    $ pip install opencv-python
    $ pip install opencv-contrib-python
    
    # scikit-image
    $ pip install scikit-image
    
    # pillow 
    $ pip install pillow
    
    # tqdm
    $ pip install tqdm
    
    # faiss (unofficial)
    $ pip install faiss-gpu
    $ pip install faiss-cpu
    
    # flask 
    $ pip install flask
    
    # pymysql
    $ pip install pymysql
    
    # pika
    $ pip install pika
    
    
    
    