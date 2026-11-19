# P27 · 25.续集2_时隔5年的彻底更换，7950x3d+4090略有不满｜用 CPU-Z 核对新机配置，查清内存插槽和实际速率

## 装好新机，先核对系统识别到了什么

讲师的示例机使用 Ryzen 9 7950X3D、华硕 ROG STRIX X670E-A GAMING WIFI、两条 16 GB DDR5 和技嘉 RTX 4090。打开 CPU-Z 即可按下表核对自己的机器。CPUID 官网提供 Windows 安装版、ZIP 便携版，也保留了片中使用的 ASUS ROG 外观。[CPU-Z 官方下载](https://www.cpuid.com/softwares/cpu-z.html)

| 要确认的问题 | 入口 | 示例机的读数及用途 |
| --- | --- | --- |
| CPU 和主板是什么型号？ | CPU-Z → CPU、Mainboard | CPU 为 16 核 32 线程的 7950X3D。记下主板完整型号，才能查对内存插槽图和兼容列表。 |
| 显卡由谁制造，显存有多大？ | CPU-Z → Graphics | GPU 是 RTX 4090，板卡厂商为 GIGABYTE，显存 23.99 GB GDDR6X，位宽 384 bit。查电源、卡长和散热规格时，还要从卡身或包装确认技嘉的具体型号。 |
| 新 CPU 究竟快了多少？ | CPU-Z → Bench | 用相同版本和设置，在新旧机分别运行 Bench CPU，记录单线程和多线程成绩。Reference 只提供参考型号。课堂仅展开列表，两项成绩都为空。 |

## 套条标称 6000，为什么系统只显示 4800？

1. **查系统当前速率。** 按 `Ctrl + Shift + Esc`，进入“任务管理器 → 性能 → 内存”。示例机识别到 32.0 GB，四槽用了两个，`Speed` 显示 4800（该版 Windows 界面标作 MHz）。此时“使用中”约 9.6 GB，“可用”约 21.2 GB。判断是否要加内存，应在常用项目运行时再看可用容量。
2. **用实时时钟复核。** 打开 CPU-Z → `Memory`，读 `DRAM Frequency`。DDR 每个时钟传输两次，所以 **2395.1 MHz × 2 ≈ 4790 MT/s**，对应 **DDR5-4800**。如果已运行在 DDR5-6000，预期看到的时钟约为 3000 MHz。
3. **逐槽读内存条资料。** 打开 `SPD → Memory Slot Selection`。示例机的 `Slot #2` 和 `Slot #4` 各显示一条 16 GB G.Skill，料号都是 `F5-6000J3238F16G`，JEDEC 表含 2400 MHz。SPD 描述模块保存的参数，当前频率到 Memory 页读。这块华硕主板的手册第 1-5 页建议两条装在 **DIMM_A2、DIMM_B2**。其他主板按各自手册的双条插法核对。[华硕中文主板手册](https://dlcdnets.asus.com/pub/ASUS/mb/SocketAM5/ROG_STRIX_X670E-A_GAMING_WIFI/C21442_ROG_STRIX_X670E-A_GAMING_WIFI_UM_V2_WEB.pdf)
4. **区分标称档位与平台规格。** AMD 给 7950X3D 列出的标准最高速率为两条 DDR5-5200、四条 DDR5-3600。想使用套条的 6000 档，应先查完整套条型号、主板兼容列表，再到 UEFI 核对实际选用的内存配置。若调整了配置，回系统按前两步复读，并验证常用负载稳定。视频只查到了当前约 4800 MT/s，未检查 UEFI，也未验证 6000 档。[AMD 7950X3D 规格](https://www.amd.com/zh-cn/products/processors/desktops/ryzen/7000-series/amd-ryzen-9-7950x3d.html) · [华硕内存兼容列表](https://www.asus.com/us/supportonly/rog%20strix%20x670e-a%20gaming%20wifi/helpdesk_qvl_memory/)

## 其余配件按自己的负载核对

- **电源和散热。** 讲师为静音和升级余量选了 1300 W 电源，CPU 搭配 be quiet! 360 mm 水冷。NVIDIA 对参考设计 RTX 4090 列出显卡总功率 450 W、整机电源 850 W。复用电源时应以具体板卡的要求、整机配置和供电线为准。若要比较两张卡的噪声和温度，应固定负载、环境和测量位置。[NVIDIA RTX 4090 规格](https://www.nvidia.com/en-us/geforce/graphics-cards/40-series/rtx-4090/)
- **存储与数据。** 讲师的一块 970 EVO 使用多年，另一块西数 SSD 故障后，他花约八小时抢救仍未恢复所需数据。工作文件应另存一份独立备份，并试着恢复、打开其中一份文件。选新盘时查主板 M.2 插槽支持的 PCIe 代际。片中提到的 990 PRO 之后，三星已推出 PCIe 5.0 的 9100 PRO。[三星 9100 PRO 发布资料](https://news.samsung.com/us/samsung-announces-9100-pro-series-ssds-with-breakthrough-pcie-5-0-performance/)
