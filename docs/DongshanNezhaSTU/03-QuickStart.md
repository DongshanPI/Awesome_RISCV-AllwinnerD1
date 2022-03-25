# 快速开始使用
## 烧写固件至TF卡
* 我们提供的系统镜像有多种不同的镜像类型，主要以`全志原厂Tina-SDK`构建出来的系统，和使用`Buildroot`构建出来的两种不同类型的系统镜像。本文先以介绍`全志原厂Tina-SDK`构建出来的系统进行演示，后续在提供`Buildroot`构建出来的系统烧写步骤。
### 准备工作
1. 东山哪吒STU开发板主板 x1
2. TF卡读卡器  x1
3. 8GB以上的 micro TF卡 x1
4. `全志原厂Tina-SDK`烧写所用的烧录工具：点击下载：传输链接：https://cowtransfer.com/s/7536f3b4d23042
5. SDcard专用格式化工具：点击下载：https://cowtransfer.com/s/b0f773308c6a4f

### 烧录`Tina-SDK`镜像
1. 下载需要的镜像文件：点此传输链接：https://cowtransfer.com/s/b50be87e55ef4c 。下载任意镜像，然后参考下面步骤进行烧写。 
2. 使用 `SD Card Formatter.exe`格式化插入的 Micro TF卡。
3. 打开原厂专用烧录工具，参考下图进行烧写操作。
 打开烧录软件 PhoenixCard，选择烧录的固件，将内存卡通过读卡器插入电脑中
![](https://wiki.sipeed.com/hardware/zh/lichee/assets/RV/flash.png)

* 选择启动卡能成功启动系统
![](https://wiki.sipeed.com/hardware/zh/lichee/assets/RV/boot_cards.png)

> 并不能保证每台电脑和每个人的内存卡都是可以烧录的，烧录失败的话建议购买官方的镜像卡。
等待提示烧录结束，之后拔下卡 插入到 `东山哪吒STU`背面TF卡卡槽内，按下进去，继续进行如下步骤 启动开发板进入系统。

* 如果需要自行从头编译构建 `全志原厂Tina-SDK V2.0`系统，请移步至左侧 Tina-SDK V2.0开发指南页面。

## 上电启动系统
### 1. 连接串口线
将配套的TypeC线一段连接至开发板的串口/供电接口，另一端连接至电脑USB接口，连接成功后板载的红色电源灯会亮起。
默认情况下系统会自动安装串口设备驱动，如果没有自动安装，可以使用驱动精灵来自动安装。

* 对于Windows系统
此时Windows设备管理器 在 端口(COM和LPT) 处会多出一个串口设备，一般是以 `USB-Enhanced-SERIAL CH9102`开头，您需要留意一下后面的具体COM编号，用于后续连接使用。

![](https://cdn.jsdelivr.net/gh/codebug8/DongshanPi-Photos@master/QuickStart-01.png)
如上图，COM号是96，我们接下来连接所使用的串口号就是96。


* 对于Linux系统
可以查看是否多出一个/dev/tty<> 设备,一般情况设备节点为 /dev/ttyACM0  。
![](https://cdn.jsdelivr.net/gh/codebug8/DongshanPi-Photos@master/QuickStart-02.png)

### 2. 打开串口控制台
#### 获取串口工具
使用Putty或者MobaXterm等串口工具来开发板设备。

* 其中putty工具可以访问页面  https://www.chiark.greenend.org.uk/~sgtatham/putty/  来获取。
* MobaXterm可以通过访问页面 https://mobaxterm.mobatek.net/ 获取 (推荐使用)。


#### 使用putty登录串口
![登录截图](https://cdn.jsdelivr.net/gh/codebug8/DongshanPi-Photos@master/QuickStart-04.png)

#### 使用Mobaxterm登录串口
打开MobaXterm，点击左上角的“Session”，在弹出的界面选中“Serial”，如下图所示选择端口号（前面设备管理器显示的端口号COM21）、波特率（Speed 115200）、流控（Flow Control: none）,最后点击“OK”即可。步骤如下图所示。
**注意：流控（Flow Control）一定要选择none，否则你将无法在MobaXterm中向串口输入数据**

![连接](https://cdn.jsdelivr.net/gh/codebug8/DongshanPi-Photos@master/QuickStart-05.png)

### 3. 进入系统shell
使用串口工具成功打开串口后，可以直接按下 Enter 键 进入shell，当然您也可以按下板子上的 `Reset`复位键，来查看完整的系统信息。
![](https://cdn.jsdelivr.net/gh/codebug8/DongshanPi-Photos@master/QuickStart-06.png)
