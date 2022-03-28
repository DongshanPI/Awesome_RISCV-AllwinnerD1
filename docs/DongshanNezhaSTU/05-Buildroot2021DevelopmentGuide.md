# 使用buildroot-2021编译构建Tina-Linux最小系统

* 已实现功能
  * 支持平头哥 rv64d外部工具链。
  * 支持buildroot构建 Tina  sdk 内 Thead c910 opensbi 。
  * 支持buildroot 构建Tina  sdk 内 u-boot 2018
  * 支持buildroot构建Linux kernel 5.4自动生成Image并后续打包为boot.img
  * 自动构建并打包生成SD卡 busybox udev最小系统启动。

## 编译完整系统或者各个部分
* 我们编译使用的是ubuntu 18.04 系统，在进行如下编译之前需要先配置基本编译环境，参考下述命令来安装必须的软件包。

```shell
book@virtual-machine:~/Neza-D1/buildroot-2021$ sudo apt-get install -y which sed make binutils build-essential  gcc g++ bash patch gzip bzip2 perl  tar cpio unzip rsync file  bc wget python ncurses5  bazaar cvs git mercurial rsync scp subversion android-tools-mkbootimg
```

* 使用git命令clone源码

```shell
book@virtual-machine:~$ mkdir -p  ~/Neza-D1/ &&  cd ~/Neza-D1/
book@virtual-machine:~/Neza-D1$ git clone https://gitee.com/weidongshan/neza-d1-buildroot.git buildroot-2021
```

### 构建完整系统镜像

* 编译完整系统镜像

``` shell
book@virtual-machine:~/Neza-D1/buildroot-2021$ make  neza-d1_defconfig  //加载配置文件 
book@virtual-machine:~/Neza-D1/buildroot-2021$ make  all //完整编译系统
```

* 编译生成的系统镜像在output/image目录下，其中sdcard.img为完整的系统镜像。

``` shel
book@virtual-machine:~/Neza-D1/buildroot-2021/output/images$ ls
board.dtb         boot.img          boot_package.fex  boot.vfat      env.cfg  fw_dynamic.bin  fw_jump.bin  Image        rootfs.cpio     rootfs.ext2  rootfs.tar  sunxi.fex              uImage
boot0_sdcard.fex  boot_package.cfg  boot.scr          dragonsecboot  env.fex  fw_dynamic.elf  fw_jump.elf  ramdisk.img  rootfs.cpio.gz  rootfs.ext4  sdcard.img  u-boot-sun20iw1p1.bin
book@virtual-machine:~/Neza-D1/buildroot-2021/output/images$
```

### 单独编译各个部分

* 单独编译 opensbi阶段
``` shell
book@virtual-machine:~/Neza-D1/buildroot-2021$  make opensbi-rebuild V=1
```

* 单独编译 uboot阶段
``` shell
book@virtual-machine:~/Neza-D1/buildroot-2021$  make uboot-rebuild V=1
```

* 单独编译 kernel阶段
``` shell
book@virtual-machine:~/Neza-D1/buildroot-2021$  make linux-rebuild V=1
```

* 单独编译文件系统
  * 指定完成工具链 系统配置 需要安装的包 以及所需的格式 执行如下命令，最后生成的镜像在 output/image目录下。
``` shell
book@virtual-machine:~/Neza-D1/buildroot-2021$ make  all //完整编译系统
```

## 烧写启动

* windows下使用wind32diskimage工具烧写，Linux下直接使用dd 命令完整写入

![NezaD1wind32diskimag](https://cdn.jsdelivr.net/gh/DongshanPI/Docs-Photos@master/DongshanNezhaSTU/NezaD1wind32diskimag.png)

* 烧写成功后把卡插入开发板 开发板上电 即可自动从sd卡启动进入系统
![nezaD1startupLog](https://cdn.jsdelivr.net/gh/DongshanPI/Docs-Photos@master/DongshanNezhaSTU/nezaD1startupLog.png)