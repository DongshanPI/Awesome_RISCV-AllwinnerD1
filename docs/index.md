---
title: Overview DongshanNezhaSTU.
description: Overview DongshanNezhaSTU RISCV D1 some Boards.
last_updated: Thur May 02 12:00:00 2022 UTC
---
<p class="text-center">
    <a href="https://www.aw-ol.com/">
        <img src="https://d1.docs.aw-ol.com/assets/img/%E5%85%A8%E7%90%83%E9%A6%96%E9%A2%97.png" width="auto" height="auto" alt="D1-H">
    </a>
    <br>
    <strong>D1-H 是全志科技首款基于RISC-V指令集的芯片，集成了阿里平头哥64位C906核心，支持RVV，1GHz+主频，可支持Linux、RTOS等系统。同时支持最高4K的H.265/H.264解码，内置一颗HiFi4 DSP，最高可外接2GB DDR3，可以应用于智慧城市、智能汽车、智能商显、智能家电、智能办公和科研教育等多个领域。</strong>
</p>

此网站是关于 RISCV64 Linux开发板相关资源汇总页面，主要以使用全志D1/D1s芯片系列开发板作为主要介绍，主要包含如下内容。

- **支持的开发板**:支持`东山哪吒STU` `Nezha` `MQ-Pro`,此站点主要以 `东山哪吒STU`开发作为示例。
- **支持的SDK**:配套的D1/D1s支持了 `Tina-SDK` `Buildroot` `RTOS` 以及多个 Linux `发行版系统`。
- **已知的文档**:
    -  `Tina-SDK`开发资料：包含 'SDK模块开发指南' '基础组件开发指南'。
    -  SOC开发手册：包含 D1/D1s SOC数据手册 芯片手册
    -  硬件设计参考资源：公版原理图 设计参考文件 以及一些开源PI文件。
- **应用开发及项目示例**:
    -  Debian系列发行版系统构建教程。
    -  Tina-sdk构建开发教程。
    -  Buildroot构建开发教程。
    -  RT-Smart系统开发教程
    -  xboot开发教程。
    -  平头哥社区的一些系统支持。
- **配套其它资源**：
    - 东山哪吒STU交流社区板块：https://forums.100ask.net/c/rv64/
    - AW-OL交流社区板块：https://bbs.aw-ol.com/
    - whycan交流社区板块：https://whycan.com/forumlist.php
- **参与页面维护**: 此页面全都托管在GitHub 仓库中，可以点击页面的右上角 🖊 图标进行编辑。

---

## 整站资料索引
### 硬件
#### 东山哪吒STU
 - 原理图文件: [存放位置](https://github.com/DongshanPI/Awesome_RISCV-AllwinnerD1/tree/master/DongshanNezhaSTU)
    - DongshanNezhaSTU-Core-Bottom.jpg
    - DongshanNezhaSTU_CORE_SCH_V1.0.pdf
    - DongshanNezhaSTU-Core-TOP.jpg
    - DongshanNezhaSTU_DIY-BASE_SCH_V1.0.pdf
    - DongshanNezhaSTU-DIY-BASE_v1.0.zip
#### 哪吒
 - 硬件设计：[存放位置](https://github.com/DongshanPI/Awesome_RISCV-AllwinnerD1/tree/master/Tina-SDK/Hardware%E7%A1%AC%E4%BB%B6%E7%B1%BB%E6%96%87%E6%A1%A3/%E7%A1%AC%E4%BB%B6%E8%AE%BE%E8%AE%A1)
    - D1-H_DEV_DDR3_16X2_V1_2.brd
    - D1-H_package.zip
    - D1-H_SCHEMATIC_NEZA_V1_2.DSN
    - D1-H_SCHEMATIC_NEZA_V1_2.pdf
#### MQ-Pro

### 手册&文档
#### Tina-SDK软件类文档
 - SDK模块开发指南：[存放位置](https://github.com/DongshanPI/Awesome_RISCV-AllwinnerD1/tree/master/Tina-SDK/Software%E8%BD%AF%E4%BB%B6%E7%B1%BB%E6%96%87%E6%A1%A3/SDK%E6%A8%A1%E5%9D%97%E5%BC%80%E5%8F%91%E6%8C%87%E5%8D%97)
	- D1-H_Linux_AUDIOCODEC_开发指南.pdf
	- D1-H_Linux_CCU_开发指南.pdf
	- D1-H_Linux_CE开发指南.pdf
	- D1-H_Linux_CPUFREQ_开发指南.pdf
	- D1-H_Linux_Display_开发指南.pdf
	- D1-H_Linux_DMAC_开发指南.pdf
	- D1-H_Linux_DMIC_开发指南.pdf
	- D1-H_Linux_EMAC_开发指南.pdf
	- D1-H_Linux_G2D_开发指南.pdf
	- D1-H_Linux_GPADC_开发指南.pdf
	- D1-H_Linux_GPIO_开发指南.pdf
	- D1-H_Linux_HDMI20_开发指南.pdf
	- D1-H_Linux_I2S_开发指南.pdf
	- D1-H_Linux_IR-RX_开发指南.pdf
	- D1-H_Linux_IR-TX_开发指南.pdf
	- D1-H_Linux_LCD_开发指南.pdf
	- D1-H_Linux_LRADC_开发指南.pdf
	- D1-H_Linux_Media_开发指南.pdf
	- D1-H_Linux_RTC_开发指南.pdf
	- D1-H_Linux_SID_开发指南.pdf
	- D1-H_Linux_SPDIF_开发指南.pdf
	- D1-H_Linux_SPI-NAND_开发指南.pdf
	- D1-H_Linux_SPI_开发指南.pdf
	- D1-H_Linux_Standby_开发指南.pdf
	- D1-H_Linux_Thermal_开发指南.pdf
	- D1-H_Linux_TWI_开发指南.pdf
	- D1-H_Linux_UART_开发指南.pdf
	- D1-H_Linux_USB_开发指南.pdf
	- D1-H_Linux_离线烧录_开发指南.pdf
 - 基础组件开发指南：[存放位置](https://github.com/DongshanPI/Awesome_RISCV-AllwinnerD1/tree/master/Tina-SDK/Software%E8%BD%AF%E4%BB%B6%E7%B1%BB%E6%96%87%E6%A1%A3/%E5%9F%BA%E7%A1%80%E7%BB%84%E4%BB%B6%E5%BC%80%E5%8F%91%E6%8C%87%E5%8D%97)
	- D1-H_Tina_Linux_Camera_开发指南.pdf
	- D1-H_Tina_Linux_Display_开发指南.pdf
	- D1-H_Tina_Linux_Key_快速配置_使用指南.pdf
	- D1-H_Tina_Linux_LCD_调试指南.pdf
	- D1-H_Tina_Linux_LEDC_开发指南.pdf
	- D1-H_Tina_Linux_OTA_开发指南.pdf
	- D1-H_Tina_Linux_PWM_开发指南.pdf
	- D1-H_Tina_Linux_SDK_发布说明.pdf
	- D1-H_Tina_Linux_SPI_LCD_调试指南.pdf
	- D1-H_Tina_Linux_syslog_使用指南.pdf
	- D1-H_Tina_Linux_Tinatest测试_使用指南.pdf
	- D1-H_Tina_Linux_U-Boot_开发指南.pdf
	- D1-H_Tina_Linux_USB_开发指南.pdf
	- D1-H_Tina_Linux_WiFi_RF测试_使用指南.pdf
	- D1-H_Tina_Linux_Wi-Fi_开发指南.pdf
	- D1-H_Tina_Linux_以太网_开发指南.pdf
	- D1-H_Tina_Linux_内存优化_开发指南.pdf
	- D1-H_Tina_Linux_功耗管理_开发指南.pdf
	- D1-H_Tina_Linux_各平台多媒体格式_支持列表.pdf
	- D1-H_Tina_Linux_启动优化_开发指南.pdf
	- D1-H_Tina_Linux_图形系统_开发指南.pdf
	- D1-H_Tina_Linux_多媒体编码_开发指南.pdf
	- D1-H_Tina_Linux_多媒体解码_开发指南.pdf
	- D1-H_Tina_Linux_存储_开发指南.pdf
	- D1-H_Tina_Linux_存储性能_参考指南.pdf
	- D1-H_Tina_Linux_安全_开发指南.pdf
	- D1-H_Tina_Linux_打包流程_说明指南.pdf
	- D1-H_Tina_Linux_扩展IO_开发指南.pdf
	- D1-H_Tina_Linux_温度控制_使用指南.pdf
	- D1-H_Tina_Linux_系统裁剪_开发指南.pdf
	- D1-H_Tina_Linux_系统调试_使用指南.pdf
	- D1-H_Tina_Linux_系统软件_开发指南.pdf
	- D1-H_Tina_Linux_红外_开发指南.pdf
	- D1-H_Tina_Linux_网络性能_参考指南.pdf
	- D1-H_Tina_Linux_蓝牙_开发指南.pdf
	- D1-H_Tina_Linux_配网_开发指南.pdf
	- D1-H_Tina_Linux_配置_开发指南.pdf
	- D1-H_Tina_Linux_量产测试_使用指南.pdf
	- D1-H_Tina_Linux_音频_开发指南.pdf

#### D1/D1s芯片手册
 - SOC芯片数据&开发手册: [存放位置](https://github.com/DongshanPI/Awesome_RISCV-AllwinnerD1/tree/master/Tina-SDK/   Hardware%E7%A1%AC%E4%BB%B6%E7%B1%BB%E6%96%87%E6%A1%A3/%E8%8A%AF%E7%89%87%E6%89%8B%E5%86%8C)
	- D1-H Brief_V1.4.pdf
	- D1-H_Datasheet_V1.0.pdf
	- D1-H_User Manual_V1.0.pdf
	- D1s_Brief_V1.0.pdf
	- D1s_Datasheet_V1.0.pdf
	- D1s_User Manual_V1.0.pdf

### 系统&组件
#### Tina-SDK系统
- 源码仓库地址: https://gitlab.com/weidongshan/tina-d1-h.git
- 使用介绍: 
#### Buildroot-SDK
- 源码仓库地址: https://gitee.com/weidongshan/neza-d1-buildroot
- 使用介绍： https://gitee.com/weidongshan/neza-d1-buildroot/blob/master/README.md

### 开发工具
#### 系统烧写工具

