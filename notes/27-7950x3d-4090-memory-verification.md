# P27 · 25.续集2_时隔5年的彻底更换，7950x3d+4090略有不满｜用 CPU-Z 核对新机配置，查清内存插槽和实际速率

## DDR5-6000 套条为什么读到 4800？

DDR5-6000 是套条的标称档位。要看实际跑多快，在系统中查当前速率，再与内存条保存的参数对照。示例机使用 Ryzen 9 7950X3D 和华硕 ROG STRIX X670E-A GAMING WIFI。[CPU-Z 官方下载](https://www.cpuid.com/softwares/cpu-z.html)

| 要查什么 | 操作与示例读数 |
| --- | --- |
| 系统识别了多少内存 | 按 `Ctrl + Shift + Esc` →“性能 → 内存”。示例显示 32 GB，四个槽用了两个，速度栏为 4800。判断容量是否够用，应在常用项目运行时查看“可用”内存。 |
| 当前实际运行多快 | CPU-Z → `Memory → DRAM Frequency` 读到 **2395.1 MHz**。DDR 每个时钟传两次数据，乘 2 约为 **4790 MT/s**，对应 DDR5-4800。跑在 DDR5-6000 时这里应接近 3000 MHz。 |
| 每条内存是什么 | CPU-Z → `SPD → Memory Slot Selection` 逐槽切换。#2 和 #4 各有一条 16 GB 芝奇，料号均为 `F5-6000J3238F16G`，JEDEC 表中有 2400 MHz。SPD 表列出条内保存的档位，实际生效值回到 Memory 页读。 |

若目标是 6000 MT/s，先按主板手册确认双条装在 **A2、B2**，再用完整套条型号查兼容列表和支持的内存配置。AMD 为 7950X3D 标出的标准最高速率为两条 DDR5-5200、四条 DDR5-3600，6000 属于超频档。到 UEFI 检查所用配置，调整后回系统复读时钟并验证负载稳定性。视频确认了约 4800 MT/s，未进入 UEFI，原因和 6000 档稳定性均未验证。[华硕手册，第 1-5 页](https://dlcdnets.asus.com/pub/ASUS/mb/SocketAM5/ROG_STRIX_X670E-A_GAMING_WIFI/C21442_ROG_STRIX_X670E-A_GAMING_WIFI_UM_V2_WEB.pdf) · [内存兼容列表](https://www.asus.com/us/supportonly/rog%20strix%20x670e-a%20gaming%20wifi/helpdesk_qvl_memory/) · [AMD 平台规格](https://www.amd.com/zh-cn/products/processors/desktops/ryzen/7000-series/amd-ryzen-9-7950x3d.html)

## 怎样验收其余配件

- **处理器。** CPU-Z 的 `CPU` 页可核对 7950X3D 的 16 核 32 线程。要量化升级幅度，在两台机器用相同版本运行 `Bench CPU`，对照单线程和多线程成绩。视频只展开参考型号，两栏没有成绩。
- **显卡与电源。** `Graphics` 页识别出技嘉 RTX 4090、24 GB GDDR6X、384 bit。NVIDIA 参考规格是显卡 450 W、建议整机电源 850 W。示例机自选 1300 W 电源，复用旧电源应按手中板卡的完整型号核对额定功率和供电线。[RTX 4090 规格](https://www.nvidia.com/en-us/geforce/graphics-cards/40-series/rtx-4090/)
- **存储。** 一块工作盘故障后，讲师未能恢复所需文件。验收备份时，从独立副本恢复一份项目并实际打开，才能检验恢复流程。
