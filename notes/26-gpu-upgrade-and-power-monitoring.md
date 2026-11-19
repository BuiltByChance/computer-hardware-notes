# P26 · 24.续集：时隔4年的硬件更新，显卡2070s换到了4070｜换显卡前核对电源，用 HWMonitor 看实际功耗

## 旧电源能否带动新显卡

先查**显卡本身的功率**和**建议整机电源**。以下为 NVIDIA 参考规格，非公版卡另查板卡厂商的要求。

| 显卡 | 显卡功率 | 建议整机电源 |
| --- | ---: | ---: |
| [RTX 2070 SUPER](https://www.nvidia.com/en-gb/geforce/graphics-cards/rtx-2070-super/) | 215 W | 650 W |
| [RTX 3080](https://www.nvidia.com/en-us/geforce/graphics-cards/30-series/rtx-3080-3080ti/) | 10 GB 版 320 W，12 GB 版 350 W | 750 W |
| [RTX 4070 普通版](https://www.nvidia.com/en-us/geforce/graphics-cards/40-series/rtx-4070-family/) | 200 W | 650 W |

从 2070 SUPER 换到 4070 Founders Edition 的示例机沿用了 650 W 电源。照着升级前，查自己的电源额定功率、CPU 等部件的用电、机箱容得下的卡长和供电线空间。4070 FE 可用两根 PCIe 8-pin 线接随卡转接器，也可用额定至少 300 W 的兼容 PCIe Gen 5 供电线。[NVIDIA 安装要求](https://www.nvidia.com/en-us/geforce/graphics-cards/40-series/rtx-4070-family/)

## 测一次显卡功耗

1. **认显卡和负载。** 在 GPU-Z 的 `Graphics Card` 页确认显卡型号与显存。按 `Ctrl + Shift + Esc` 打开“任务管理器 → 性能 → GPU”。用硬件编码录屏时看 `Video Encode` 曲线确认编码引擎在工作，GPU 利用率只表示忙碌程度。[GPU-Z 下载](https://www.techpowerup.com/download/techpowerup-gpu-z/)
2. **读对传感器。** 在 HWMonitor 展开同名显卡，`Powers → GPU` 读瓦数，`Temperatures → GPU` 读核心温度，`Fans` 读转速。`Value` 是当前值，`Max` 是本次监控捕捉到的最高值。分别在录屏与游戏开始前重开监控，可单独记录各项任务的峰值。测整机从插座取的功率要用外接功率计。[HWMonitor 下载](https://www.cpuid.com/softwares/hwmonitor.html)
3. **把读数和工况记在一起。** 示例机用 NVENC 编码 H.265 桌面录像时，4070 FE 的瞬时读数为 **10.27 W、49 °C、两把风扇均为 0 RPM**，到片尾监控记录的峰值为 **27.18 W**。约 180 W 来自讲师对其他负载的回忆，这次录屏只测到了桌面编码。

查整机配置可用 HWiNFO 的系统摘要，查温度和风扇转速用其“传感器”窗口。比较升级前后的图形性能，可在两张卡上运行同一版本、同一设置的 3DMark 项目，记录图形分数。课堂没有展示可对照的跑分。[HWiNFO 官方下载](https://www.hwinfo.com/download/) · [3DMark 官方下载说明](https://benchmarks.ul.com/download)
