# NAS

本文主要介绍NAS(Non-Access Stratum，非接入层)和他的协议EMM以及ESM

NAS是EPC(Evolved Packet System)的众多协议中的一个子集，下图是EPS的控制面协议，其中NAS主要用来在UE和MME之间传递non-radio signalling。从协议栈的角度看，NAS是控制面板协议中的最高层。

![control-plane](/Users/houmin/Work/503/OpenSDR/docs/img/control-plane.png)

NAS过程主要用于UE和各MME间移动性管理与会话管理过程，主要包含EMM和ESM协议：

- EMM(EPS Mobility Management)协议定义了UE的移动性控制过程
- ESM(EPS Session Management)协议定义了EPS承载上下文的管制过程，与接入层提供控制协同来完成用户面的控制。

## 基本概念

- Aggregate Maximum Bit Rate
  - 一个UE的一组非GBR承载集合的聚合比特率的最大值
- EMM Context
  - UE的Attach过程成果结束后，EMM上下文在UE与MME建得以建立
- NAS signalling connection
  - UE与MME建的对等S1连接。一个NAS信令连接由两部分串连组成：RRC连接(LTE-Uu)和S1AP连接(S1-MME)。当RRC连接成功建立时，UE就认为NAS信令连接已建立；而RRC释放时，UE认为NAS信令连接已经释放
- EMM-CONNECTED mode
  - 一旦UE和网络间建立了NAS信令连接，则UE迁到EMM-CONNECTED状态
- EMM-IDLE mode
  - UE与网络间不存在NAS信令连接，则UE处于EMM-IDLE状态
- TAI list
  - 一组TAI，UE在其指示的TA之间穿越时，不必执行TAU过程
- Initial NAS message
  - 触发NAS信令连接的建立，如：ATTACH REQUEST消息就是一个Initial NAS消息
- Last Visited Registered TAI
  - TAI列表中UE最后访问的TA所对应的TAI
- Linked Bearer Identity
  - 此ID标识附加承载资源连接于那个Default承载
- MME area
  - 一个MME所服务于TA组成的总的区域
- PDN address
  - 由PDN-GW分配给UE的一个IP地址
- TAU
  - Tracking Area Update
- 