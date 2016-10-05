参考：
http://www.ubuntukylin.com/ukylin/forum.php?mod=viewthread&tid=26148
http://askubuntu.com/questions/763202/matlab-problem-on-ubuntu-16-04
http://www.cnblogs.com/amboyna/archive/2008/03/08/1096024.html

一、前言

刚学习linux，由于必须要使用m@tl@b，所以看了很多帖子，熬了几天，终于安装好了。总结一下，以帮助需要的新人。

二、安装步骤
1、首先要下载好2Ol6@(R2Ol6@_g1nx@64.is0)及其破解文件(M@TL@B_R2Ol6@_Llnux_Cr@ck);
因为我的windows已经被干掉了，只好与ubuntu好好相处了。所以：

2.建立一个文件夹，直接挂载.iso文件。
sudo mkdir /mnt/temp，用来挂载.iso文件，就跟windows里的虚拟光驱一样;
3. cd 到iso所在的路径;
4. sudo mount -o loop R2Ol6@_g1nx@64.is0 /mnt/temp  把iso挂载到刚建的虚拟光驱中;

下两步可能会出现问题，我出现了并在百度中看见别人也出现了

5. 安装

  $ cd /mnt/temp
  sudo ./install

-----------------------------------------------------------------------------
-------------------------------无视下面的--------------------------------------
-----------------------------------------------------------------------------
（1）install .....eval......install.....,  （错误信息没记全，见谅！）不给安装。
百度后，mathwork公司的提醒是，我安装的ubuntu kylin是32位的版本，R2016a是64位版本。呵呵，我又下载了ubuntu kylin的64位的“amd”版本，进行安装。其间，学会了终端用命令行刻录光盘的方法。
安装好64位的ubuntu kylin 16.04后，再进行以上步奏，出现下一个问题：
（2）某个目录的文件“输入输出错误”，（错误信息没记全，见谅！）也没给安装。
百度后，发现有一个帖子说，R2012a版本也碰到这样的问题，没有理会，换了2009版本。仔细思考后，可能是我的文件没下载完整，于是（安装uget + aria2），在百度网盘重新下载了一遍。重复以上工作，又碰到下一个问题：
（3）“没有这个文件”，（错误信息没记全，见谅！）
ll 了一下，发现是没有执行权限，于是建立了一个 /home/m@tl@b2Ol6@/ 文件夹，用文件管理器将 /mnt/temp 中的文件全部拷贝过去。重置权限，然后就顺利安装了。

sudo mkdir /home/m@tl@b2Ol6@/
sudo chmod -R 777 /home/m@tl@b2Ol6@/

cd /home/matlab2016a/
sudo ./install
--
-----------------------------------------------------------------------------
-------------------------------无视上面的--------------------------------------
-----------------------------------------------------------------------------
4、接下来会打开matlab的安装界面(与Windows下一样)，然后输入密钥，在M@TL@B_R2Ol6@_Llnux_Cr@ck里面的FIK.txt里面。然后一直下一步，直到安装完成(大约20min～1h)。
5、进入
  cd /usr/local/M@TL@B/R20l6a/bin

新建“licenses”文件并赋予其权限
  sudo mkdir licenses
  sudo chmod 777 licenses

6、将linux破解文件夹M@tl@b_R2Ol6@_g1nx@64_cr@ck.zip下的
M@tl@b_R2Ol6@_g1nx@64.is0.lic
libmwservices.so
libcufft.so

分别拷贝到上述新建的”licenses”和”./bin/g1nxa64”下面 
  sudo cp Mat1ab_R2016a_glnxa64.lic /usr/local/M@TL@B/R2Ol6@/bin/licenses 
  sudo cp libmwservices.so /usr/local/M@TL@B/R2Ol6@/bin/g1nx@64 
  sudo cp libcufft.so /usr/local/M@TL@B/R2Ol6@/bin/g1nx@64

7、到此为止，在Ubuntu 16.04下安装M@TL@B R2Ol6@就完成了，我们只要从命令行进入m@t1@b R2Ol6@的”bin”目录，输入
  cd /usr/local/M@TL@B/R2Ol6@/bin
  sudo ./m@tl@b
然后把lic文件按指示再次导入
再次运行 sudo ./m@tl@b

即可打开m@tl@b R2Ol6@了。

为了方便，要将路径添加到系统变量中去，sudo subl /etc/profile, 添加export PATH="$PATH:/usr/local/M@TL@B/R2Ol6@/bin", 每次依然需要root极限来运行，不然会报错！！！
--
-------------------------------------------------------------------------------------------------------------------
安装中遇到的问题，绝大部分都是文件夹及文件权限问题，很容易解决。
---------------------------------------------------------------------------------------------------------------------
特别注意是：如果是安装在文件系统中，则安装的时候就要取得root权限，千万记住，要不然安装目录的时候不能创建文件夹。
----------------------------------------------------------------------------------------------
