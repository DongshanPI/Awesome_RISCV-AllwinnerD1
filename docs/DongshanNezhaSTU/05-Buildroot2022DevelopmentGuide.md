# 使用buildroot-2022编译构建Linux主线最小系统
支持的组件

 - 支持单独编译SPL。
 - 支持Opensbi V0.9版本
 - 支持uClibc库，Glibc库等
 - 支持u-boot-2021.10 版本
 - 支持LinuxKernel  5.14.0-rc4 版本

## 配置环境
* 我们编译使用的是ubuntu 18.04 系统，在进行如下编译之前需要先配置基本编译环境，参考下述命令来安装必须的软件包。
```shell
book@100ask:~$ sudo apt-get install -y which sed make binutils build-essential  gcc g++ bash patch gzip bzip2 perl  tar cpio unzip rsync file  bc wget python ncurses5  bazaar cvs git mercurial rsync scp subversion 
```

## 获取源码
注意：社区版本和百问网提供的版本本质上没有区别，我们只是将其整合增加了更多的软件包配置，并提供整个工程。

### 获取社区版本
* 使用git命令clone源码
```shell
book@100ask:~$ git clone https://git.buildroot.net/buildroot buildroot-2022
book@100ask:~$ cd buildroot-2022 && git checkout buildroot-2022.02

```

* 使用wget下载
```shell
book@100ask:~$ wget https://buildroot.org/downloads/buildroot-2022.02.tar.gz
book@100ask:~$ tar -xvf buildroot-2022.02.tar.gz
```
### 使用百问网提供的版本
* 完整压缩版本
传输链接：https://dongshanpi.cowtransfer.com/s/6cbc58bbc68045
下载后拷贝到 ubuntu系统内，执行 `tar -xvf buildroot-2022.02.tar.gz`解压缩。
解压完成以后，就可以继续参考下面步骤进行编译系统。
* git仓库版本


## 编译系统
1.进入解压缩的 buildroot-2022.02目录下。
``` shell
book@100ask:~$ cd buildroot-2022.02
```
2.执行 make nezha_defconfig 指定配置文件
``` shell
book@100ask:~/buildroot-2022.02$ make nezha_defconfig
```

3. 执行 make 命令开始编译。
``` shell
book@100ask:~/buildroot-2022.02$ make V=1
```
等待编译完成会有类似如下输出信息。
![Buildroot-2022_MakeCompile_output_001](https://cdn.jsdelivr.net/gh/DongshanPI/Docs-Photos@master/DongshanNezhaSTU/Buildroot-2022_MakeCompile_output_001.png)
之后继续参考如下命令执行烧写操作。
## 烧写启动
* windows下使用wind32diskimage工具烧写，Linux下直接使用dd 命令完整写入
![NezaD1wind32diskimag](https://cdn.jsdelivr.net/gh/DongshanPI/Docs-Photos@master/DongshanNezhaSTU/NezaD1wind32diskimag.png)
* 烧写成功后把卡插入开发板 开发板上电 即可自动从sd卡启动进入系统
``` shell
[36]HELLO! BOOT0 is starting!
[39]BOOT0 commit :
[41]set pll start
[43]periph0 has been enabled
[46]set pll end
[47]board init ok
[49]DRAM only have internal ZQ!!
[52]get_pmu_exist() = -1
[54]ddr_efuse_type: 0x0
[57][AUTO DEBUG] single rank and full DQ!
[61]ddr_efuse_type: 0x0
[64][AUTO DEBUG] rank 0 row = 15
[67][AUTO DEBUG] rank 0 bank = 8
[70][AUTO DEBUG] rank 0 page size = 2 KB
[74]DRAM BOOT DRIVE INFO: V0.24
[77]DRAM CLK = 792 MHz
[79]DRAM Type = 3 (2:DDR2,3:DDR3)
[82]DRAMC ZQ value: 0x7b7bfb
[85]DRAM ODT value: 0x42.
[88]ddr_efuse_type: 0x0
[91]DRAM SIZE =512 M
[94]DRAM simple test OK.
[96]dram size =512
[98]card no is 0
[100]sdcard 0 line count 4
[102][mmc]: mmc driver ver 2021-04-2 16:45
[111][mmc]: Wrong media type 0x0
[114][mmc]: ***Try SD card 0***
[133][mmc]: HSSDR52/SDR25 4 bit
[136][mmc]: 50000000 Hz
[138][mmc]: 30436 MB
[140][mmc]: ***SD/MMC 0 init OK!!!***
[178]Loading boot-pkg Succeed(index=0).
[182]Entry_name        = opensbi
[185]Entry_name        = dtb
[188]Entry_name        = u-boot
[191]Jump to second Boot.

OpenSBI v0.9
   ____                    _____ ____ _____
  / __ \                  / ____|  _ \_   _|
 | |  | |_ __   ___ _ __ | (___ | |_) || |
 | |  | | '_ \ / _ \ '_ \ \___ \|  _ < | |
 | |__| | |_) |  __/ | | |____) | |_) || |_
  \____/| .__/ \___|_| |_|_____/|____/_____|
        | |
        |_|

Platform Name             : Allwinner D1 NeZha
Platform Features         : medeleg
Platform HART Count       : 1
Platform IPI Device       : aclint-mswi
Platform Timer Device     : aclint-mtimer @ 24000000Hz
Platform Console Device   : uart8250
Platform HSM Device       : ---
Platform Reboot Device    : sunxi-wdt-reset
Platform Shutdown Device  : ---
Firmware Base             : 0x40000000
Firmware Size             : 248 KB
Runtime SBI Version       : 0.3

Domain0 Name              : root
Domain0 Boot HART         : 0
Domain0 HARTs             : 0*
Domain0 Region00          : 0x0000000014008000-0x000000001400bfff (I)
Domain0 Region01          : 0x0000000014000000-0x0000000014007fff (I)
Domain0 Region02          : 0x0000000040000000-0x000000004003ffff ()
Domain0 Region03          : 0x0000000000000000-0xffffffffffffffff (R,W,X)
Domain0 Next Address      : 0x000000004a000000
Domain0 Next Arg1         : 0x0000000044000000
Domain0 Next Mode         : S-mode
Domain0 SysReset          : yes

Boot HART ID              : 0
Boot HART Domain          : root
Boot HART ISA             : rv64imafdcvsux
Boot HART Features        : scounteren,mcounteren,mcountinhibit,time
Boot HART PMP Count       : 16
Boot HART PMP Granularity : 2048
Boot HART PMP Address Bits: 38
Boot HART MHPM Count      : 0
Boot HART MIDELEG         : 0x0000000000000222
Boot HART MEDELEG         : 0x000000000000b109


U-Boot 2021.10 (Mar 24 2022 - 11:08:02 +0000)

DRAM:  512 MiB
WDT:   Started watchdog@6011000 with servicing (16s timeout)
MMC:   mmc@4020000: 0, mmc@4021000: 1
Loading Environment from nowhere... OK
In:    serial@2500000
Out:   serial@2500000
Err:   serial@2500000
Net:
Warning: ethernet@4500000 (eth0) using random MAC address - a6:72:3c:ad:2f:47
eth0: ethernet@4500000
Hit any key to stop autoboot:  0
switch to partitions #0, OK
mmc0 is current device
Scanning mmc 0:1...
Found /boot/extlinux/extlinux.conf
Retrieving file: /boot/extlinux/extlinux.conf
134 bytes read in 2 ms (65.4 KiB/s)
1:      linux
Retrieving file: /boot/Image
15509024 bytes read in 1330 ms (11.1 MiB/s)
append: console=ttyS0,115200 root=/dev/mmcblk0p1 ro rootwait
Retrieving file: /boot/sun20i-d1-nezha.dtb
24602 bytes read in 6 ms (3.9 MiB/s)
## Flattened Device Tree blob at 4fa00000
   Booting using the fdt blob at 0x4fa00000
   Loading Device Tree to 0000000049ff6000, end 0000000049fff019 ... OK

Starting kernel ...

[    0.000000] Linux version 5.14.0-rc4 (book@100ask) (riscv64-buildroot-linux-uclibc-gcc.br_real (Buildroot 2022.02) 10.3.0, GNU ld (GNU Binutils) 2.36.1) #1 PREEMPT Thu Mar 24 11:08:54 UTC 2022

```