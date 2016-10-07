<center>
#DOL的配置过程 #
</center>
##1.配置一些基本的环境##
**sudo**是Linux的系统管理指令，是允许系统管理员让普通用户执行一些或者全部的root命令，如halt，reboot，su等，这样不仅减少了用户登录和管理的时间，同样也提高了安全性。
   
**apt-get**，主要用于自动从互联网的软件仓库中搜索、安装、升级、卸载软件或者操作系统。是Ubuntu,debian发行版的包管理工具，与红帽中的yum工具非常类似。
<pre>
$  sudo apt-get update 
$  sudo apt-get install ant//ant和make的用法差不多，但是比make的维护性高，生成build.xml文件，易修改
$  sudo apt-get install openjdk-7-jdk
$  sudo apt-get install unzip
</pre>


## 2.下载文件 ##
下载一些基本的额文件，也可以从主机上拷贝过去

[下载文件](http://jingyan.baidu.com/article/c33e3f48a5c153ea15cbb5b2.html)　;   
<pre>  $   sudo wget [网址2](http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz)
  $   sudo wget [网址3](http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip)</pre>

##3.解压文件##
新建dol的文件夹
<pre>  $  mkdir dol</pre>
将dolethz.zip解压到dol文件中
<pre>  $  unzip dol_ethz.zip -d dol</pre>
解压systemc
<pre>  $  tar -zxvf systemc-2.3.1.tgz</pre>
##3.编译systemc##
解压后进入systemc-2.3.1的目录下
<pre>  $  cd systemc-2.3.1</pre>
新建一个临时文件并进入，mkdir+文件名表示新建一个文件，cd+文件名表示打开文件
<pre>  $  mkdir objdir
  $  cd objdir </pre>
运行configure，即执行当前目录的脚本，主要是对即将安装的软件进行配置，检查当前环境是否满足要安装软件的以来关系，如使用什么编译器，cc还是gcc，执行configure之后会生成Makefile文件，它规定用什么编译器，编译参数等信息。
<pre>  $  ../configure CXX=g++ --disable-async-updates
</pre>
编译systemc。make install：将程序安装至系统中。如果原始码编译无误，且执行结果正确，便可以把程序安装至系统预设的可执行文件存放路径。
<pre>  $  sudo make install</pre>
记录当前工作路径
<pre>  $  pwd</pre>

##4.编译dol##
进入刚刚编译的dol文件
<pre>  $  cd ../dol </pre>
修改build_zip.xml文件里面的一段话，修改路径为上一步我们查看的路径  
编译dol
<pre>  $  ant -f build_zip.xml all </pre>
运行第一个例子
<pre>  $  cd build/bin/main
  $  ant -f runexample.xml -Dunmber=1 </pre>
成功结果如图：  
![图一](http://i.imgur.com/TjAlgEF.png)