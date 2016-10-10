# DOL frame Description
![alt text](DOL图.jpg "DOL")
# DOL安装笔记
上学期已经使用过ubuntu系统所以我直接开始环境配置
<br>
##1.首先安装一些必要的环境：
$	sudo apt-get update（更新我目前的ubuntu所有程序）
<br>
$	sudo apt-get install ant（安装ant，用于编译的工具）
<br>
$ sudo apt-get install openjdk-7-jdk
<br>
$	sudo apt-get install unzip（解压具）
<br>
##2.然后下载dol和systemc
在命令行中输入这两句话来安装
<br>
sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz
<br>
sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip
<br>
##3.解压文件
新建dol的文件夹 
<br>$	mkdir dol
<br>
将dolethz.zip解压到 dol文件夹中
<br>
$	unzip dol_ethz.zip -d dol<br>
解压systemc
<br>
$	tar -zxvf systemc-2.3.1.tgz
<br>
##4.编译systemc
解压后进入systemc-2.3.1的目录下
<br>
$	cd systemc-2.3.1
<br>新建一个临时文件夹objdir
<br>
$	mkdir objdir
<br>
进入该文件夹objdir
<br>
$	cd objdir
<br>
运行configure(能根据系统的环境设置一下参数，用于编译)
<br>
$	../configure CXX=g++ --disable-async-updates
<br>
设置结果如下：
<br>
###imghere
<br>
编译
<br>
$	sudo make install
<br>
至此就完成了编译systemc
<br>
然后可以返回上一层检查目录下有哪些文件来判断是否装好了。
<br>
$ cd ..
<br>
% ls
<br>
###imghere
<br>
记录当前的工作路径
<br>
$	pwd
<br>
###imghere
<br>
##5.编译dol
进入刚刚dol的文件夹
<br>
$	cd ../dol
<br>
然后先到文件管理器里去修改build_zip.xml文件
<br>
直接找到下面两句话（就在一开头）
<br>
###imghere
<br>
###imghere
<br>
把前面的路径改成我安装的systemc的路径，也就是上面pwd到的路径（上图已经是改好的）
<br>
然后是编译
<br>
$	ant -f build_zip.xml all
<br>
成功会显示build successful
<br>
###imghere
<br>
#至此就完成了dol的安装！
#实验感想
根据ppt一步步完成了安装了呢~markdown


