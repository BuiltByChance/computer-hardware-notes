# P20 · 19.查看显卡信息以及天梯图的介绍｜用 GPU-Z 查显卡，按平台读天梯图

## 在 Windows 上确认本机显卡（00:00–01:35）

1. 到 TechPowerUp 下载页，选 **Standard Version → Download**，再选一个下载镜像。课堂用的是 2.45.0。截至 2026-11-19，官网标准版为 **2.71.0**。GPU-Z 支持直接运行，个人和商业使用均免费。[GPU-Z 官方下载](https://www.techpowerup.com/download/techpowerup-gpu-z/) · [功能与授权说明](https://www.techpowerup.com/gpuz/)
2. 双击下载的程序。若出现 **Install GPU-Z?**，选 **No** 即可用独立模式启动，以后也不再询问。**Yes** 用于安装，**Not now** 会在下次启动时再问。主窗口的 **Graphics Card** 页出现显卡名称和显存数值，说明已读到设备信息。
3. 如果电脑有核显和独显，可用窗口底部的显卡下拉框选中要查的设备。先记下完整型号和后缀，再对照显存，避免把两个 GPU 的数据记在一起。

| 想知道什么 | 在哪里看 | 讲师电脑上的示例 |
|---|---|---|
| 哪一款显卡、哪家板卡厂商 | Graphics Card → Name、Subvendor | NVIDIA GeForce RTX 2070 SUPER，Gigabyte（技嘉） |
| 显存容量、类型和位宽 | Graphics Card → Memory Size、Memory Type、Bus Width | 8192 MB（8 GB）、GDDR6、256 bit |
| 核心、显存与加速频率 | Graphics Card → GPU Clock、Memory、Boost | 1605、1750、1785 MHz |
| 这一刻用了多少显存，温度和负载多高 | Sensors → Memory Used、GPU Temperature、GPU Load | 一次采样为 1533 MB、56.1 °C、16%，读数会随负载变化 |

查显卡一共有多少显存，用 **Memory Size**。想知道运行程序前后整张卡的显存占用怎样变化，看 **Memory Used**。课上的频率和温度来自讲师的显卡，当时没有运行游戏或压力测试。

## 在天梯图里定位型号（01:35–06:14）

1. 从快科技首页进入「天梯图」，按**桌面或笔记本、CPU 或显卡**选图。若打开的是带名次和分数的条形榜，可用侧栏「天梯图」切换到按代际和相对档次排列的图。[快科技天梯榜入口](https://rank.kkj.cn/)
2. 用浏览器的 **Ctrl+F** 找完整型号。桌面图按厂商和世代分列，中间箭头朝上，位置越高表示该图给出的性能档次越高。横向看同一高度，可以找到其他世代或厂商里大致同档的型号。课堂笔记本 CPU 图的左右两区是「标准电压」和「低电压」，每区都有 Intel 和 AMD。
3. 先看页头日期，再看图中有无要查的那一代。课堂打开的笔记本显卡旧图标着 **2016 年 4 月**，讲师据此停止用它判断 RTX 30 系列。相邻位置只能用于粗略比较，要估算具体游戏帧率，还需看同分辨率和画质下的实测。

| 要查的设备 | 桌面 | 笔记本 |
|---|---|---|
| CPU | [桌面 CPU 天梯图](https://www.mydrivers.com/zhuanti/tianti/cpu/index.html) | [笔记本 CPU 天梯图](https://www.mydrivers.com/zhuanti/tianti/cpum/index.html) |
| 显卡 | [桌面显卡天梯图](https://www.mydrivers.com/zhuanti/tianti/gpu/index.html) | [笔记本显卡天梯图](https://www.mydrivers.com/zhuanti/tianti/gpum/index.html) |

## 笔记本显卡要抄全型号（06:14–07:59）

早期的 **GeForce GTX 960M** 用 M 表示移动版。到了课上举例的 RTX 30 系列，**Laptop GPU** 表示笔记本型号，**Ti** 是型号的一部分。NVIDIA 同时列有 **GeForce RTX 3050 Laptop GPU** 和 **GeForce RTX 3050 Ti Laptop GPU**。查天梯图时保留这两个标记。

即使名称相同，笔记本厂商可采用不同的功耗配置。例如 NVIDIA 给 **RTX 3060 Laptop GPU** 列出的 GPU 子系统功耗范围是 **60–115 W**。比较两台具体笔记本时，核对整机规格中的 GPU 功耗，再看对应机型的实测。[NVIDIA RTX 30 系列笔记本 GPU 规格对照](https://www.nvidia.cn/geforce/laptops/compare/30-series/)
