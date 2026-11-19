# P10 · 9.内存频率的用途｜读懂 DDR 速率、主板超频标注与笔记本扩容条件

**DDR4-3200** 表示 DDR4 内存每秒可传输 32 亿次（3200 MT/s）。DDR 在时钟的两个边沿传输，实际时钟约 **1600 MHz**。在相同总线宽度、通道数下，传输率越高，理论带宽越大。容量另算，如「DDR5-6000，16 GB × 2」为 32 GB。[金士顿对 MT/s 与 MHz 的说明](https://www.kingston.com/cn/blog/pc-performance/mts-vs-mhz)

## 主板支持多快，套条能跑多快

- **先对完整型号和内存代际。** 华硕 ROG STRIX Z690-A GAMING WIFI **D4** 用 DDR4，同名无 D4 后缀的版本用 DDR5，两代插槽的防呆缺口不同。[D4 版规格](https://rog.asus.com.cn/motherboards/rog-strix/rog-strix-z690-a-gaming-wifi-d4-model/) · [DDR5 版手册](https://dlcdnets.asus.com/pub/ASUS/mb/LGA1700/ROG_STRIX_Z690-A_GAMING_WIFI/C19960_ROG_STRIX_Z690-A_GAMING_WIFI_UM_V2_WEB.pdf)
- **再看「规格参数 → 内存」。** 「4 × DIMM，DDR5-6400（O.C.）」分别说明四个槽和主板列出的超频档。以 B660-F GAMING WIFI 为例，规格同时列有 DDR5-4800 和多个更高的 O.C. 档。实际速率还取决于 CPU、套条和设置。购前核对主板内存兼容列表，装好后读 CPU-Z「内存 → DRAM Frequency」，乘 2 核对。[华硕 B660-F 规格](https://rog.asus.com.cn/motherboards/rog-strix/rog-strix-b660-f-gaming-wifi-model/spec/)

## 笔记本扩容还要查每槽容量

拯救者 Y9000P 2022 示例标有 **16 GB 内存、512 GB SSD**。对应平台手册列出两个 DDR5-4800 SO-DIMM 插槽，商品页写最高 32 GB。若原机是 1 × 16 GB，可加一根兼容的 16 GB。若是 2 × 8 GB，两槽已满，升至 32 GB 要换 2 × 16 GB。商品页未给出这台机器的出厂分配，另列的 M.2 接口用于装硬盘。[联想平台规格，第 2 页](https://psref.lenovo.com/syspool/Sys/PDF/Legion/Lenovo_Legion_5_Pro_16IAH7H/Lenovo_Legion_5_Pro_16IAH7H_Spec.pdf#page=2)

**容量与速度可以分别验证。** 在任务管理器「进程 → 内存」观察 Chrome。课中关闭标签页后，其占用约从 1196 MB 降到 900 MB。这次测到了约 296 MB 的占用变化。要测传输率的收益，可以保持打开的项目和内存容量相同，改用另一速率后比较同一任务的耗时。
