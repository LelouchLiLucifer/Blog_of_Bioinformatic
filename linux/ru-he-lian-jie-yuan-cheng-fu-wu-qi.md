# 如何连接远程服务器

在做生信项目的时候，我们通常不会在自己的个人PC上运行程序,因为处理生信项目所需要的消耗的CPU计算量和PC内存量往往过于庞大，以个人PC的水平去运行如此消耗计算机性能的程序是不太现实的。举一个俺踩过的坑:俺在初学的时候曾在自己的个人PC上运行过一个相对来说不算很大的生信项目，然后这玩意连续运行了接近三天，却只完成了不到10%，然而把同样的项目交给老板提供的专门用来跑生信项目的远程服务器上运行时，不到1h就得出想要的全部结果了...\
所以说"专业的事情，还是交给专业的'人'去做，这样才更有效率"。在一般情况下，项目的负责人会提供专用的远程服务器给项目组的组员用来跑项目。服务器运维的技术活有专门的运维人员负责处理，我们只需要能够连接上远程服务器，并且配置好运行该项目需要的工作环境，就可以开始~~搬砖~~工作啦。\
于是乎，最重要的一步就是：如何连接上远程服务器？\
我们需要准备的东西包括:一台电脑、远程连接软件、远程服务器相关信息(用户名、IP、端口、密码or私钥)~~&脑子~~\
①电脑的话，由于windows系统的使用率最高，所以我们主要以目前最新的Windows 11系统为例进行讲解，其他系统的操作方式可以自行百度、bing~~或者Google~~\
②远程连接软件的话，常用的有Xshell、putty、Final Shell & windows terminal(终端)\
③远程服务器的相关信息，通常情况下负责人给的格式为:\


```
用户名@服务器的IP地址:端口号   #默认情况下，如果不特殊说明，认为端口号为22
服务器的密码 or 私钥文件
举个例子：
demo@192.168.123.21:5244   
passw20230415
#这里的demo是用户名，192.168.123.21是服务器的IP地址，5244是服务器的远程连接端口号，服务器密码是passw20230415
```

之后分别介绍一下使用Xshell、putty、Final Shell以及windows terminal(终端)连接远程服务器的方法\


### **使用Xshell连接远程服务器的方式**

①下载Xshell软件\
官方网址为[https://www.xshell.com/zh/xshell/](https://www.xshell.com/zh/xshell/)，该软件默认是可以试用一段时间后需要购买许可证才能继续使用的，对于非商业用途的项目来说，我们可以在官方的[这个页面](https://www.xshell.com/zh/free-for-home-school/)申请免费版许可证来使用该软件。\
②软件的安装 这个软件的安装没有什么需要特别注意的地方，小白的话只需要一路无脑下一步(Next)即可\
③服务器的连接 Xshell连接远程服务器的方式，目前互联网上已经有较为详细的教程了，这里提供一个笔者认为比较简单易懂的教程[点击这里](https://www.jianshu.com/p/ed0f00c95c89)

### **使用putty连接远程服务器的方式**

### **使用Final Shell连接远程服务器的方式**

### **使用windows terminal(终端)连接远程服务器的方式**

使用windows terminal(终端)连接远程服务器相对来说比较麻烦，虽然有可视化的图形界面，但又好像宛如没有，因为实际上还是需要自己写ssh命令来进行连接，所以这个不建议小白第一次就尝试使用，但如果你就是想挑战难一点的、看着更加高级一点的方法，那么就请跟俺来看看这个软件的使用方法吧\
①下载windows terminal(终端)软件（以下简称"终端"） 如果你使用的是Windows 11系统，那么这个软件是预装在系统里的；如果你是Windows 11之前系统的用户则需要自己去下载安装该软件，"终端"的下载方式有两种<1>[通过Microsoft Store进行安装](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701?hl=en-us\&gl=us)<2>[通过github下载](https://github.com/microsoft/terminal/releases)\
更加详细的说明可以参考微软官方的文档[https://learn.microsoft.com/zh-cn/windows/terminal/install](https://learn.microsoft.com/zh-cn/windows/terminal/install)\
②配置"终端"软件:\
首先给"终端"添加配置文件 ![配置terminal-1.png](https://s2.loli.net/2023/04/16/YIQnCWteiqbJcoX.png)\
然后点击新建配置文件 ![配置terminal-2.png](https://s2.loli.net/2023/04/17/6AJVWleBw28iszm.png)\
之后修改命令行 ![配置terminal-3.png](https://s2.loli.net/2023/04/17/zpEnZ2W4bFhyVdL.png)\
最基本的命令行写法为

```
#使用账号密码登录服务器
ssh 用户名@服务器的IP地址:端口号 
#使用密钥文件登录服务器
ssh -i 密钥文件路径 用户名@服务器IP地址:端口号
```