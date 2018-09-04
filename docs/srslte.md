# SoftwareRadioSystems - srsLTE

srsLTE是由SoftwareRadioSystems 实现的开源软件，起初只实现了LTE下行物理层链路功能，后来开源了其全协议栈的srsENB平台，现在srsUE终于可以和srsENB完成空口连接。

## 项目介绍

### 主要特征  

- 开源项目
- 完全按照3GPP协议实现了全协议栈UE(srsUE)和全协议栈的eNB(srsENB)
- 目前只支持Release 8
- 只支持FDD TM1和TM2传输模式, 1.4, 3, 5, 10, 15 和 20 MHz 带宽
- 项目支持USRP, bladeRF等硬件
- 产品稳定，代码优化较好，可以用作SDR开发的库

### 应用场景

- Third-party MME+ srsENB + srs UE
- Third-party MME+ Third-party ENB + srs UE
- Third-party MME+ srsENB + Third-party UE
- Third-party MME+ srsENB + 商用终端（手机、LTE数据卡）

### 相关链接 

- 官方网站 http://www.softwareradiosystems.com/ 
- 代码获取 https://github.com/srsLTE/srsUE 和 http://github.com/srsLTE/srsLTE