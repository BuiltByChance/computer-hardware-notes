# P16 · 15.显卡的用途与实战分析｜定位 PCIe 显卡槽，读懂 GeForce 型号与后缀

## 从用途判断要看什么（00:00–02:40）

独立显卡上有负责图形计算的 GPU、显存和显示输出接口。台式机使用独显输出画面时，把显示器的数据线接到显卡挡板上的 HDMI 或 DisplayPort 接口。能显示桌面与能在指定画质下流畅玩游戏，是两个不同的要求。

- **玩游戏**时，先确定游戏、分辨率、画质和目标帧率，再看相同条件下的测试。提高分辨率或增加图形特效会加重 GPU 负担，CPU 也可能限制帧率。
- **做建筑制图、影视或动画**时，先确认常用软件中的哪一步能利用 GPU。例如，旋转复杂的三维模型要看视口流畅度，使用 GPU 渲染器输出成片则要看渲染时间和场景所需显存。

## 在主板图上找到显卡槽（02:40–03:14）

1. 用主板的**完整型号**打开厂商产品页或手册，找到「扩展槽」和主板布局图。课上用的是华硕 **ROG STRIX Z690-A GAMING WIFI D4**。京东「商品介绍」图里的 **②** 是扩展槽这一组的编号。
2. 沿引线找靠近 CPU 的银色加固长槽。图上标着 **PCIe 5.0 x16 SafeSlot（x16）[CPU]**，即由 CPU 直连、接通 16 条通道。这块主板装单张独显时选此槽。
3. 再对照下方长槽。它也是 x16 长度，规格却写 **PCIe 3.0 x16（x4）[芯片组]**，只接通 4 条通道。换主板时按该型号手册确认推荐槽位、通道数和所连控制器。[华硕吹雪 D4 主板布局与扩展槽](https://rog.asus.com.cn/motherboards/rog-strix/rog-strix-z690-a-gaming-wifi-d4-model/)

## 拆读 GeForce 型号（03:15–12:08）

课堂提到 AMD、NVIDIA 和 Intel Arc，展开分析的是 NVIDIA 面向玩家的 **GeForce** 产品线。以 **GeForce RTX 2080 Ti** 为例，先确认是台式显卡还是笔记本 GPU，再读 **RTX** 产品线、**20** 系列、**80** 档和 **Ti** 后缀。数字档位适合辨认同系列内的产品定位，跨系列的快慢要回到具体软件或游戏的测试。

| 课堂例子 | 从名称能确认什么 |
|---|---|
| GTX 950、960、980、980 Ti | 同属 900 系列，50、60、80 是不同档位。980 Ti 是正式型号，讲师用“假如有 GTX 960 Ti”解释后缀时举的是假设。[NVIDIA 900 系列档案](https://www.nvidia.com/en-us/geforce/900-series/) |
| GTX 1050、1050 Ti、1060、1080 Ti，以及 GTX 1660 | 前四款属于 10 系列，1660 属于 16 系列。数字系列和芯片架构要分开看。GTX 16 与 RTX 20 同为 Turing 架构，RTX 20 有专用 RT 核心与 Tensor 核心。[NVIDIA 跨系列规格对照](https://www.nvidia.cn/geforce/graphics-cards/compare/) |
| RTX 2080、2080 SUPER、2080 Ti | 这三款桌面卡的定位依次提高。官方规格依次为 **8、8、11 GB 显存**，**2944、3072、4352 个 CUDA 核心**。同属 2080 才能这样读这组三款。单凭 Ti 或 SUPER 无法推断跨型号的性能差距。[NVIDIA 20 系列规格对照](https://www.nvidia.cn/geforce/graphics-cards/compare/) |
| RTX 3050 Ti 与 RTX 3090 Ti | 课上口述 30 系列时把不同平台放在一起。NVIDIA 将 **3050 Ti** 列为笔记本电脑 GPU，**3090 Ti** 列为台式显卡。查型号时分别进入对应的平台规格表。[30 系列笔记本 GPU](https://www.nvidia.cn/geforce/laptops/compare/30-series/) · [30 系列台式显卡](https://www.nvidia.cn/geforce/graphics-cards/30-series/) |

## 从搜索结果核对到具体板卡（10:30–13:23）

先在 NVIDIA 对应系列的规格表查完整 GPU 型号，再在板卡厂商产品页核对显存、散热和尺寸。课上在京东搜“2090”搜出了鞋，改成“2080”才出现相关显卡。NVIDIA 的 20 系列清单里有 **RTX 2080、2080 SUPER、2080 Ti**。搜索框能接受一个数字，并不足以确认有这个显卡型号。[NVIDIA GeForce 规格对照](https://www.nvidia.cn/geforce/graphics-cards/compare/)

商品标题可以分层读。例如，七彩虹 **iGame GeForce RTX 3090 Ti Neptune OC 24G** 中，**RTX 3090 Ti** 是 GPU 型号，**Neptune OC（水神）**是七彩虹的一体式水冷版本，**24G** 是显存容量。旁边的 **3090 Advanced OC 24G** 少了 Ti，属于另一款 GPU。比较价格前要对齐完整型号。比较散热时还要看具体板卡，水冷版需核对机箱能否容纳冷排。[七彩虹水神产品页](https://www.colorful.cn/home/product?id=1934&mid=102)
