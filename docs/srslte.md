# SoftwareRadioSystems - srsLTE

srsLTE是由SoftwareRadioSystems 实现的开源软件，起初只实现了LTE下行物理层链路功能，后来开源了其全协议栈的srsENB平台，现在srsUE终于可以和srsENB完成空口连接。

## 项目介绍

### 包含模块

- srsUE - a complete SDR LTE UE application featuring all layers from PHY to IP
- srsENB - a complete SDR LTE eNodeB application
- srsEPC - a light-weight LTE core network implementation with MME, HSS and S/P-GW
- a highly modular set of common libraries for PHY, MAC, RLC, PDCP, RRC, NAS, S1AP and GW layers.



### 主要特征  

- LTE Release 8 compliant (with selected features of Release 9)
- FDD configuration
- Tested bandwidths: 1.4, 3, 5, 10, 15 and 20 MHz
- Transmission mode 1 (single antenna), 2 (transmit diversity), 3 (CCD) and 4 (closed-loop spatial multiplexing)
- Frequency-based ZF and MMSE equalizer
- Evolved multimedia broadcast and multicast service (eMBMS)
- Highly optimized Turbo Decoder available in Intel SSE4.1/AVX2 (+100 Mbps) and standard C (+25 Mbps)
- MAC, RLC, PDCP, RRC, NAS, S1AP and GW layers
- Detailed log system with per-layer log levels and hex dumps
- MAC layer wireshark packet capture
- Command-line trace metrics
- Detailed input configuration files



### srsUE特征

- Cell search and synchronization procedure for the UE
- Soft USIM supporting Milenage and XOR authentication
- Hard USIM support using PCSC framework
- Virtual network interface *tun_srsue* created upon network attach
- 150 Mbps DL in 20 MHz MIMO TM3/TM4 configuration in i7 Quad-Core CPU.
- 75 Mbps DL in 20 MHz SISO configuration in i7 Quad-Core CPU.
- 36 Mbps DL in 10 MHz SISO configuration in i5 Dual-Core CPU.

srsUE has been fully tested and validated with the following network equipment:

- Amarisoft LTE100 eNodeB and EPC
- Nokia FlexiRadio family FSMF system module with 1800MHz FHED radio module and TravelHawk EPC simulator
- Huawei DBS3900
- Octasic Flexicell LTE-FDD NIB

### srsENB特征

- Round Robin MAC scheduler with FAPI-like C++ API
- SR support
- Periodic and Aperiodic CQI feedback support
- Standard S1AP and GTP-U interfaces to the Core Network
- 150 Mbps DL in 20 MHz MIMO TM3/TM4 with commercial UEs
- 75 Mbps DL in SISO configuration with commercial UEs
- 50 Mbps UL in 20 MHz with commercial UEs

srsENB has been tested and validated with the following handsets:

- LG Nexus 5 and 4
- Motorola Moto G4 plus and G5
- Huawei P9/P9lite, P10/P10lite, P20/P20lite
- Huawei dongles: E3276 and E398

## 

### srsEPC特征

- Single binary, light-weight LTE EPC implementation with:
  - MME (Mobility Management Entity) with standard S1AP and GTP-U interface to eNB
  - S/P-GW with standard SGi exposed as virtual network interface (TUN device)
  - HSS (Home Subscriber Server) with configurable user database in CSV format

## 

### 应用场景

- Third-party MME+ srsENB + srs UE
- Third-party MME+ Third-party ENB + srs UE
- Third-party MME+ srsENB + Third-party UE
- Third-party MME+ srsENB + 商用终端（手机、LTE数据卡）

### 支持硬件

本项目库支持Ettus Universal Hardware Driver (UHD) 和bladeRF的驱动。所以，只要是UHD和bladeRF支持的硬件都可以使用。但是，现在的库不支持采样率转换，所以硬件必须支持30.72MHz的时钟，这样才能按LTE的采样频率正常工作并且从LTE基站解码信号。

已经测试过的硬件入下：

- USRP B210
- USRP B205mini
- USRP X300
- limeSDR
- bladeRF

### 相关链接 

- 官方网站 http://www.softwareradiosystems.com/ 
- 代码获取 https://github.com/srsLTE/srsUE 和 http://github.com/srsLTE/srsLTE