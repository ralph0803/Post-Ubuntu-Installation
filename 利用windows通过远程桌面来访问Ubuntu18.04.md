### xrdp （这种方法在18.04.2上面不行，有bug）

https://www.jianshu.com/p/f60cec98eccd

这就需要xrdp来帮助我们了。它是一个RDP服务端，可以让我们用远程桌面方式登录到Linux系统。

首先要安装xrdp。
```bash
sudo apt install xrdp
```
然后启动xrdp服务。
```bash
sudo systemctl enable xrdp
sudo systemctl start xrdp
```

现在你应该可以使用Windows自带的远程桌面工具来连接到Linux系统了。


### ssh重新开启
```bash
ps -e | grep ssh  // 看ssh服务是否开启
sudo netstat -nlp | grep :22  // 看ssh服务是否开启
sudo ufw allow 22 // 开启防火墙22端口
sudo service sshd restart //重启ssh服务
```
