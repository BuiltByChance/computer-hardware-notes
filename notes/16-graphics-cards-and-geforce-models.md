# P16 · 15.显卡的用途与实战分析｜定位 PCIe 显卡槽，读懂 GeForce 型号与后缀

## 先确定 GPU 要完成的任务

显卡上的 GPU 负责图形计算，显存保存纹理和渲染所需的数据。台式机使用独显输出时，把显示器接到显卡挡板上的 HDMI 或 DisplayPort。

- **游戏**关心目标分辨率和画质下能达到多少帧。比较显卡时固定游戏、场景和设置。若场景受 CPU 限制，更换显卡的收益也会受限。
- **建筑制图、动画和影视**要看软件在哪一步调用 GPU。旋转复杂模型看视口是否流畅，导出成片看指定渲染器的耗时，同时核对显存是否足够容纳场景。

## 在主板手册上找独显的安装位置

以华硕 ROG STRIX Z690-A GAMING WIFI D4 为例，在产品页的主板布局图找到「扩展槽」。图中 ②、靠近 CPU 的银色长槽标为 **PCIe 5.0 x16（x16）[CPU]**，由 CPU 直连，单卡优先用它。下方长槽也能插下 x16 卡，标注却是 **PCIe 3.0 x16（x4）[芯片组]**。前一个 x16 表示槽的物理尺寸，括号内的 x4 表示实际接通的通道。换主板要重新查手册。[华硕主板布局与扩展槽](https://rog.asus.com.cn/motherboards/rog-strix/rog-strix-z690-a-gaming-wifi-d4-model/)

## 从商品标题分清 GPU 型号和板卡版本

NVIDIA 的消费级显卡品牌是 **GeForce**，AMD 有 Radeon，Intel 有 Arc。以桌面 **GeForce RTX 2080 Ti** 为例，RTX 是产品线，20 是系列，80 表示该系列内的档位，Ti 属于完整型号。

| 例子 | 能从名字判断什么 |
|---|---|
| GTX 960、GTX 980 Ti、GTX 1060、GTX 1660 | 分别属于 900、900、10、16 系列。GTX 16 和 RTX 20 同属 Turing 架构，RTX 20 增加了专用光追核心。跨代快慢要查具体应用或游戏的成绩。[900 系列](https://www.nvidia.com/en-us/geforce/900-series/) · [GeForce 规格对照](https://www.nvidia.cn/geforce/graphics-cards/compare/) |
| RTX 2080、2080 SUPER、2080 Ti | 同一代同一档的这三款定位依次提高。前两款都是 8 GB，Ti 是 11 GB。显存相同也可能是不同 GPU。[GeForce 规格对照](https://www.nvidia.cn/geforce/graphics-cards/compare/) |
| RTX 3050 Ti Laptop GPU、RTX 3090 Ti | 前者是笔记本 GPU，后者是桌面卡。先核对平台，再比较数字和后缀。[30 系列笔记本 GPU](https://www.nvidia.cn/geforce/laptops/compare/30-series/) · [30 系列桌面卡](https://www.nvidia.cn/geforce/graphics-cards/30-series/) |

读完整板卡名 **七彩虹 iGame GeForce RTX 3090 Ti Neptune OC 24G** 时，GPU 型号止于 **RTX 3090 Ti**，**Neptune OC（水神）**指七彩虹的一体式水冷版本，**24G** 指显存容量。比较报价先对齐 GPU 和板卡版本，再查卡长、厚度和冷排安装空间。[七彩虹水神规格](https://www.colorful.cn/home/product?id=1934&mid=102)
