# Unbuntu Applications


<!--more-->



# Ubuntu 18.04 系统

## Windows10 & Ubuntu18.04 双系统制作





## Programming

### Java Language:

#### Environment

two file: dont forget!

```
source /etc/profile
```

```
souce ~/.bashrc
```





## Tool:

### git:

```linux
# update default package
sudo apt udpate

# install git
sudo apt install git

# check
git --version

# settings
# method 1
git config --global user.name "Your Name"
git config --global user.email "youremail@domain.com"

# method 2
sudo gedit ~/.gitconfig
```



### Maven:

reference:

```
https://blog.csdn.net/Once_Pluto/article/details/83385054
```

### Tomcat:

An error between Idea intellij and Tomcat

```
	Error running 'Tomcat 9': Error copying configuration files from /opt/apache-tomcat-9.0.30/conf to /home/bryce/.IntelliJIdea2019.3/system/tomcat/Unnamed_PersonalBlog/conf: Directory is invalid /opt/apache-tomcat-9.0.30/conf/Catalina
```

analyse:

Idea can't aceess the Tomcat file, give the tomcat high priority then the problem slove

solution:

```
sudo chmod -R 777 Tomcat
```



## Software

### make notes:

#### **WPS**:

1、remove libreoffice

```
sudo apt-get remove libreoffice-common

# Terminal show
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following packages will be REMOVED:
  libreoffice-avmedia-backend-gstreamer libreoffice-base-core libreoffice-calc
  libreoffice-common libreoffice-core libreoffice-draw libreoffice-gnome
  libreoffice-gtk3 libreoffice-help-en-gb libreoffice-help-en-us
  libreoffice-help-zh-cn libreoffice-impress libreoffice-l10n-en-gb
  libreoffice-l10n-en-za libreoffice-l10n-zh-cn libreoffice-math
  libreoffice-ogltrans libreoffice-pdfimport libreoffice-style-breeze
  libreoffice-style-galaxy libreoffice-style-tango libreoffice-writer
  python3-uno
0 upgraded, 0 newly installed, 23 to remove and 247 not upgraded.
After this operation, 400 MB disk space will be freed.
Do you want to continue? [Y/n] y
(Reading database ... 210013 files and directories currently installed.)
Removing libreoffice-avmedia-backend-gstreamer (1:6.0.7-0ubuntu0.18.04.10) ...
Removing libreoffice-calc (1:6.0.7-0ubuntu0.18.04.10) ...
Removing libreoffice-help-zh-cn (1:6.0.7-0ubuntu0.18.04.10) ...
Removing python3-uno (1:6.0.7-0ubuntu0.18.04.10) ...
Removing libreoffice-pdfimport (1:6.0.7-0ubuntu0.18.04.10) ...
Removing libreoffice-help-en-us (1:6.0.7-0ubuntu0.18.04.10) ...
Removing libreoffice-ogltrans (1:6.0.7-0ubuntu0.18.04.10) ...
Removing libreoffice-impress (1:6.0.7-0ubuntu0.18.04.10) ...
Removing libreoffice-draw (1:6.0.7-0ubuntu0.18.04.10) ...
Removing libreoffice-gnome (1:6.0.7-0ubuntu0.18.04.10) ...
Removing libreoffice-gtk3 (1:6.0.7-0ubuntu0.18.04.10) ...
Removing libreoffice-help-en-gb (1:6.0.7-0ubuntu0.18.04.10) ...
Removing libreoffice-l10n-en-gb (1:6.0.7-0ubuntu0.18.04.10) ...
Removing libreoffice-l10n-en-za (1:6.0.7-0ubuntu0.18.04.10) ...
Removing libreoffice-l10n-zh-cn (1:6.0.7-0ubuntu0.18.04.10) ...
Removing libreoffice-math (1:6.0.7-0ubuntu0.18.04.10) ...
Removing libreoffice-style-breeze (1:6.0.7-0ubuntu0.18.04.10) ...
Removing libreoffice-writer (1:6.0.7-0ubuntu0.18.04.10) ...
Removing libreoffice-base-core (1:6.0.7-0ubuntu0.18.04.10) ...
Removing libreoffice-core (1:6.0.7-0ubuntu0.18.04.10) ...
Removing libreoffice-common (1:6.0.7-0ubuntu0.18.04.10) ...
rmdir: failed to remove '/var/lib/libreoffice/share/prereg/': No such file or directory
rmdir: failed to remove '/var/lib/libreoffice/share/': No such file or directory
rmdir: failed to remove '/var/lib/libreoffice/program/': No such file or directory
rmdir: failed to remove '/var/lib/libreoffice': No such file or directory
rmdir: failed to remove '/var/lib/libreoffice': No such file or directory
Removing libreoffice-style-tango (1:6.0.7-0ubuntu0.18.04.10) ...
Removing libreoffice-style-galaxy (1:6.0.7-0ubuntu0.18.04.10) ...
Processing triggers for mime-support (3.60ubuntu1) ...
Processing triggers for desktop-file-utils (0.23-1ubuntu3.18.04.2) ...
Processing triggers for gnome-icon-theme (3.12.0-3) ...
Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
Processing triggers for shared-mime-info (1.9-2) ...
Processing triggers for gnome-menus (3.13.3-11ubuntu1.1) ...
Processing triggers for hicolor-icon-theme (0.17-2) ...
```

if want to re-install libreoffice:

```
sudo apt-get install libreoffice
```

2、download WPS 

①official website: [recommend]

> https://linux.wps.com/

I use unbutu 18.04, so download the .deb version

② Terminal

```lunux
wget http://ftp.cn.debian.org/debian/pool/main/libp/libpng/libpng12-0_1.2.49-1+deb7u2
```

use this kind of way, you have to find the up-to-date version of WPS from time to time, so I am not recommended.

The link I provide is wps version in 2018, it works in ubuntu18.04

3、install wps

```
sudo dpkg -i wps-office_11.1.0.9080.XA_amd64.deb 
```

if error occur "to install libpng12-0"

```
# run the commend
sudo apt install-f

# then re-install
```

4、font support

① download font 

In china:

```
link: https://pan.baidu.com/s/1fNqgrfjWJS2G3lUIiIxcoA  
password: i362
```

out china:[not now]

② unzip

```
# There are several file in the zip
mkdir font

unzip -d font wps_symbol_fonts.zip
```

③ copy the aimed location:

```
sudo mv font/\* /usr/share/font
```

note: in my ubuntu18.04, the file"font" has not -s, not like "fonts", change the location as your owns

④ generate font index information:

```
sudo mkfontscale

sudo mkfontdir
```

⑤ update font cache

```
sudo fc-cache
```



#### Wiznote:

download:

> https://www.wiz.cn/wiznote-linux.html

install:

```
sudo dpkg -i wiznote_2.3.2.4_amd64.deb
```

#### Foxit Reader:

> https://www.foxitsoftware.com/downloads/

click the free version



#### Typora:

> https://support.typora.io/Typora-on-Linux/

### Brower:

#### chrome :

official site:

> https://www.google.com/intl/zh-CN/chrome/

use firefox to download:

![image-20200227220136313](/home/bryce/.config/Typora/typora-user-images/image-20200227220136313.png)

note: click software install!

free-connection: SwitchyOmega

download:

```
link: https://pan.baidu.com/s/1pHn5FnSO0UZSe1NerAk7tQ  
password: kcg3
```

open chrome: click  menu -> more tools -> extension 

turn on the "develop mode", and click "Load unpacked"

settings:
![image-20200227223234542](/home/bryce/.config/Typora/typora-user-images/image-20200227223234542.png)

- The protocol must be SOCKS5
- The server and the port is depend on your computer settings

### download

#### uget

```
 sudo add-apt-repository ppa:plushuang-tw/uget-stable
    sudo apt update
    sudo apt install uget
```

### others:

#### Nutstore:

install dependency:

```
sudo apt-get install default-jre-headless gvfs-bin python-notify
```

download

method 1:

```
wget http://www.jianguoyun.com/static/exe/installer/nutstore_linux_dist_x64.tar.gz -O /tmp/nutstore_bin.tar.gz
```

method 2:

```
https://www.jianguoyun.com/s/downloads/linux
```

unzip:

```
tar -zxvf nutstore_bin.tar.gz
```

install pic & menu

```
~/.nutstore/dist/bin/install_core.sh
```

problems:
if nutstore doesn't work

1、 restart

```
sudo reboot
```

2、restart the desk

```
sudo service xrdp restart
```

#### copyq:

add PPA:

```
sudo add-apt-repository ppa:hluk/copyq
```

install:

```
 sudo apt-get update

sudo apt-get install copyq
```



#### albert:

website:

> https://software.opensuse.org/download.html?project=home:manuelschneid3r&package=albert

download

```
sudo apt-get install albert
```

how to use: 

https://mos86.com/54972.html

### Programming:

#### vs code:

download:

> https://code.visualstudio.com/Download

install:

```
sudo dpkg -i code_1.24.1-1528912196_amd64.deb
```

run:[ignore]

```
sudo /usr/share/code/code --unity-launch
```

note: check the python version whether is 2 or 3 
