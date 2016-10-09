# DOL安装笔记
上学期已经使用过ubuntu系统所以我直接开始环境配置
>
##1.首先安装一些必要的环境：
>
>
$	sudo apt-get update（更新我目前的ubuntu所有程序）
>
$	sudo apt-get install ant（安装ant，用于编译的工具）
>
$ sudo apt-get install openjdk-7-jdk
>
$	sudo apt-get install unzip（解压具）
>
##2.然后下载dol和systemc
>
在命令行中输入这两句话来安装
>
sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz
>
sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip
>
##3.解压文件
>
新建dol的文件夹 
>
$	mkdir dol
>
将dolethz.zip解压到 dol文件夹中
>
$	unzip dol_ethz.zip -d dol
>
解压systemc
>
$	tar -zxvf systemc-2.3.1.tgz
>
##4.编译systemc
>
解压后进入systemc-2.3.1的目录下
>
$	cd systemc-2.3.1
>
新建一个临时文件夹objdir
>
$	mkdir objdir
>
进入该文件夹objdir
>
$	cd objdir
>
运行configure(能根据系统的环境设置一下参数，用于编译)
>
$	../configure CXX=g++ --disable-async-updates
>
编译
>
$	sudo make install
>
>
