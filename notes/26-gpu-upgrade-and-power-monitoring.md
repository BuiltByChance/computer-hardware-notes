# P26 · 24.续集：时隔4年的硬件更新，显卡2070s换到了4070｜换显卡前核对电源，用 HWMonitor 看实际功耗

## 换显卡前，先查两种功率

显卡功率描述卡本身的用电规格，厂商建议的电源瓦数针对整台电脑。下表取自 NVIDIA 公版或参考设计。查自己的卡时，核对完整型号、显存版本和板卡厂商。

| 显卡 | 显卡功率 | 建议整机电源 | 官方规格 |
| --- | ---: | ---: | --- |
| GeForce RTX 2070 SUPER | 215 W | 650 W | [NVIDIA 2070 SUPER](https://www.nvidia.com/en-gb/geforce/graphics-cards/rtx-2070-super/) |
| GeForce RTX 3080 | 10 GB 版 320 W，12 GB 版 350 W | 750 W | [NVIDIA 3080 系列](https://www.nvidia.com/en-us/geforce/graphics-cards/30-series/rtx-3080-3080ti/) |
| GeForce RTX 4070（普通版） | 200 W | 650 W | [NVIDIA 4070 系列](https://www.nvidia.com/en-us/geforce/graphics-cards/40-series/rtx-4070-family/) |

讲师从 2070 SUPER 换到 4070 Founders Edition，沿用了原来的 650 W 电源。他曾为 3080 计划配 850 W 电源。复用自己的电源时，应同时核对 CPU 等部件的用电和显卡所需的供电线，再查卡长、槽位和电源线所需的机箱空间。以 4070 FE 为例，可以用两根 PCIe 8-pin 线连接随卡转接器，也可以使用额定至少 300 W 的兼容 PCIe Gen 5 供电线。[NVIDIA 公版安装前检查](https://www.nvidia.com/en-us/geforce/graphics-cards/40-series/rtx-4070-family/)

## 在 Windows 上核对一次负载

1. **认准显卡。** 在 GPU-Z 的 `Graphics Card` 页核对型号、显存容量和类型。讲师的 4070 显示 12288 MB GDDR6X，HWiNFO 系统摘要进一步识别为 Founders Edition。[GPU-Z 官方下载](https://www.techpowerup.com/download/techpowerup-gpu-z/)
2. **确认正在做什么。** 按 `Ctrl + Shift + Esc`，进入“任务管理器 → 性能”，选择名称与实机相符的 GPU。录屏时对照 `Video Encode` 曲线、GPU 利用率和专用显存。15:45 的画面中，利用率约 27%，专用显存占用 1.5/12.0 GB，GPU 温度 49 °C。利用率本身不能换算成瓦数。
3. **选对传感器。** 打开 HWMonitor，展开显卡型号，读 `Powers → GPU` 的瓦数、`Temperatures → GPU` 的核心温度和 `Fans` 的转速。温度下另列显存和热点。若要显示摄氏度，进入 `Tools → Options → Display Temperatures in`，选 `Celsius` 并点 `OK`，回到传感器表确认单位为 °C。[HWMonitor 官方下载](https://www.cpuid.com/softwares/hwmonitor.html)
4. **给每项读数标上负载和时段。** `Value` 是当前值，`Min`、`Max` 是这一段监控捕捉到的极值。想比较录屏与游戏，分别在任务开始前重新打开监控，结束后记录同一行的 `Max`。想知道整机从插座取多少电，需要测整机输入功率。

**录屏读数示例。** 讲师用 Bandicam 录制桌面，片尾的编码器设置为 HEVC（H.265）、NVIDIA NVENC。16:43 时，`Powers → GPU` 的当前／最低／最高分别为 **10.27／9.99／26.70 W**，核心 49 °C，两个风扇均为 0 RPM。到片尾，同一行的最高值更新到 **27.18 W**。约 180 W 是讲师回忆的游戏或工作负载峰值。4070 FE 的两把风扇分居卡的正反两面，网页单面图只能看到其中一把。[4070 FE 正反面实拍](https://www.tomshardware.com/reviews/nvidia-geforce-rtx-4070-review/2)

## 按用途找工具

- **查详细配置和传感器**可用 HWiNFO。先看系统摘要，再点“传感器”。示例机实际识别为 Core i9-9900KF、技嘉 Z390 GAMING X-CF、32 GB 双通道 DDR4。约 1500 MHz 的内存时钟对应约 3000 MT/s。HWiNFO64 提供安装版和便携版，非商业使用免费。[HWiNFO 官方下载与许可入口](https://www.hwinfo.com/download/)
- **在游戏中看监控数据**可用 MSI Afterburner。这节只展示了快捷方式，未配置游戏内叠加显示。[MSI Afterburner 官方下载](https://www.msi.com/Landing/afterburner/graphics-cards)
- **比较升级前后的性能**可用 3DMark。固定测试项目、版本和设置，同时记录 CPU、GPU 与成绩。课堂只提及过去的跑分，未展示成绩页。UL 指定的免费 Demo 下载入口是 Steam。[UL 的 3DMark 下载说明](https://benchmarks.ul.com/download)
