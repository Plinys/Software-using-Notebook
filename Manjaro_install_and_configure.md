# Manjaro-deepin 的安装与相应配置
## 到官网下载相应版本
  - 发行版本 [下载地址](https://manjaro.org/get-manjaro/)
  -    发行版本又分为 XFCE,KDE,GNOME 三个版本，[区别](https://www.manjaro.cn/153)
  - 社区版本 [下载地址](https://manjaro.org/community-editions/)
  -    社区版本个人喜欢deepin版本，界面清新
## 制作启动盘（windows上制作为例）
  - 烧录工具及制作步骤具体可见 [here](https://wiki.manjaro.org/index.php?title=Burn_an_ISO_File#Burning_to_a_CD.2FDVD_in_Windows)
  - 个人推荐使用 [refus](https://rufus.ie/en_IE.html)
  - 制作方式选择DD
## 开机或重启进入bios 选择利用USB启动进入安装界面
  - 各个电脑进入BIOS 方式可能不同，google it
  - 安装界面下设置好时区，键盘，语言，驱动（driver)建议此处选择non-free非开源，non-free下系统会根据本机安装相应驱动
  - 光标移到boot选项，按下回车进入live系统
## 在live系统按照提示进行相应配置
  - 配置完后开始安装。。。等待。。
## 配置中国镜像源，让速度起飞
  - sudo pacman-mirroes -i -c China -m rank 
  - 手动勾选需要的镜像源
## 升级系统
  - sudo pacman -Syyu
## 添加Arch中科大源，可以下载更多arch系软件
  - 编辑配置文件
  - sudo nano /etc/pacman.conf  
  - 在末尾添加以下三行代码
  - [archlinuxcn]
  - SigLevel=Optional TrustedOnly
  - Server = https://mirrors.ustc.edu.cn/archlinuxcn/$arch
  - 之后导入 GPG Key
  - sudo pacman -S archlinuxcn-keyring
## 安装搜狗拼音
  - sudo pacman -S fcitx-im
  - sudo pacman -S fcitx-configtool
  - sudo pacman -S fcitx-sogoupinyin
  - 需要配置输入法配置文件，重启后生效
  - sudo nano ~/.xprofile
  - 在此文件下写入以下内容
  - export GTK_IM_MODULE=fcitx
  - export QT_IM_MODULE=fcitx
  - export XMODIFIERS="@im=fcitx"
 ## 安装软件
  - sudo pacman -S google-chrome
  - sudo pacman -S netease-cloud-music
