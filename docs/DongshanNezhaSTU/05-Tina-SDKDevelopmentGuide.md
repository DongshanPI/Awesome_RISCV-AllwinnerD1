# 快速使用Tina-SDK 指南
* Tina-SDK开发HOST主机环境主要基于ubuntu-16.04及以上系统，其它系统暂未做过验证，请尽量使用 ubuntu-18.04。

## 获取源码
### 网盘获取
* 由于整个`Tina-SDK V2.0`工程比较大，所以我们单独将其分卷压缩存放至 网盘内，可以点击此 传输链接获取：https://cowtransfer.com/s/adad917a1e5f43 
1. 下载成功后，需要先拷贝到 Ubuntu系统目录下，请尽量准备足够的硬盘存储空间，建议至少保留 **100G**以上剩余空间。
2. 之后进入到 ubuntu系统目录下 执行解压缩命令` cat tina-d1-h.tar.gz.* | tar  zvx`等待解压缩完成。
3. 解压缩完成后，我们就可以开始配置HOST主机环境了
### 全志客户服务获取
* 参考 https://d1.docs.aw-ol.com/study/study_2getsdk/

## 配置主机环境
### ubuntu-16.04
安装命令：    
```shell
sudo apt-get update
sudo apt-get install build-essential subversion git-core libncurses5-dev zlib1g-dev gawk flex quilt libssl-dev xsltproc libxml-parser-perl mercurial bzr ecj cvs unzip lib32z1 lib32z1-dev lib32stdc++6 libstdc++6 -y
```
### ubuntu-18.04
安装命令：    
```shell
sudo apt-get update
sudo apt-get install build-essential subversion git-core libncurses5-dev zlib1g-dev gawk flex quilt libssl-dev xsltproc libxml-parser-perl mercurial bzr ecj cvs unzip lib32z1 lib32z1-dev lib32stdc++6 libstdc++6 -y
sudo apt-get install libc6:i386 libstdc++6:i386 lib32ncurses5 lib32z1
```
## 配置&编译
1.进入获取完成的`Tina-SDK V2.0`目录下，执行 `cd tina-d1-h/`即可进入目录内。
2. 首先执行 `source build/envsetup.sh` 命令设置环境变量等待配置完成。会提示 **Setup env done! Please run lunch next.** 此段命令。
3. 选择你要编译的目标方案配置名称，比如输入 `lunch d1-h_nezha-tina `说明指定编译d1-h tina方案，当然也可以输入 `lunch`命令显示所有的方案，在弹出的对话框中输入你要编译的方案序号。
4. 配置好方案名称后，就可以执行 `make`命令来开始编译了，整个编译过程比较漫长，可以加上 **-JN **参数来加速编译，这里**N**指的是CPU的个数一般可以以 CPU个数 x 线程数 进行指定。
5. 编译完成后，相应的文件会输出到 **/out/d1_nezha-tina/** 目录下，之后我们继续执行 `pack`打包命令，来进行打包操作。
```shell
book@virtual-machine:~$ cd tina-d1-h/
book@virtual-machine:~/tina-d1-h$ source build/envsetup.sh
Setup env done! Please run lunch next.
book@virtual-machine:~/tina-d1-h$ lunch

You're building on Linux

Lunch menu... pick a combo:
     1. d1-h_nezha_min-tina
     2. d1-h_nezha-tina
     3. d1s_nezha-tina

Which would you like?: 2
============================================
TINA_BUILD_TOP=/home/book/tina-d1-h
TINA_TARGET_ARCH=riscv
TARGET_PRODUCT=d1-h_nezha
TARGET_PLATFORM=d1-h
TARGET_BOARD=d1-h-nezha
TARGET_PLAN=nezha
TARGET_BUILD_VARIANT=tina
TARGET_BUILD_TYPE=release
TARGET_KERNEL_VERSION=5.4
TARGET_UBOOT=u-boot-2018
TARGET_CHIP=sun20iw1p1
============================================
no buildserver to clean
[1] 20070
book@virtual-machine:~/tina-d1-h$ make -j16

```
如上示例，我进入 tina-d1-h 目录 之后使用lunch命令 显示所有的支持方案，选中 第二个 d1-h_nezha-tina 之后 执行 make -j16开始编译，这里给大家提醒一下 我们的 **东山哪吒STU** 开发板支持 方案**1. d1-h_nezha_min-tina** 方案**2. d1-h_nezha-tina**。

## 打包&烧写
编译完成后，我们就可以执行 `pack`命令，将编译好的固件打包成一个 img 文件，用于后续烧写操作，固件路径在** /out/d1_nezha-tina/tina_d1-nezha_uart0.img** 以 方案名称_串口节点.img 进行命名。
最后我们就可以参考页面左侧 `快速开始` 内 烧写 全志原厂 系统的说明文档进行烧写操作啦。

