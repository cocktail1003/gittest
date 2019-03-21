# Linux安装Redis

系统版本为Ubuntu.16.4

**一、下载Redis**

1. `Redis`中文官网地址http://www.redis.cn/下载；
2. 用命令进行下载

```shell
wget http://download.redis.io/releases/redis-5.0.0.tar.gz
```

------

**二、解压**

```shell
tar -zxvf redis-5.0.0.tar.gz 
```

解压后的源码包`redis-5.0.0`          ![1542769554774](C:\Users\ADMINI~1\AppData\Local\Temp\1542769554774.png)

------

 **三、编译**

进入`redis-5.0.0`目录下，执行

```shell
make
```

就开启了`Redis`的编译状态，在编译完成之后可以看到类似如下的信息提示： 

```shell
Hint: It's a good idea to run 'make test' ;)

make[1]: Leaving directory '/home/cocktail/download/redis-5.0.0/src'
```

- 应当运行`make test`命令

- 源码文件被移动到当前目录的`src`文件夹下面。

------

**四、安装**

进入到源码目录`src`下，输入对应的安装命令：

```shell
cd src
make test
```

安装时出现了一个错误提示如下：

```
You need tcl 8.5 or newer in order to run the Redis test
```

这时就需要安装`tcl8.5及以上`版本就可以,安装tcl:

```shell
wget http://downloads.sourceforge.net/tcl/tcl8.6.1-src.tar.gz
sudo tar xzvf tcl8.6.1-src.tar.gz  -C /usr/local/
cd  /usr/local/tcl8.6.1/unix/
sudo ./configure
sudo make
sudo make install 
```

安装好后回到`/home/cocktail/download/redis-5.0.0/src`目录下(刚刚解压的`Redis`源码包`src`目录)，再次执行安装命令：

```shell
cd src
make test
make install
```

安装完成之后的提示结果为：

```shell
Hint: It's a good idea to run 'make test' ;)

    INSTALL install
    INSTALL install
    INSTALL install
    INSTALL install
    INSTALL install
```
---------------------
