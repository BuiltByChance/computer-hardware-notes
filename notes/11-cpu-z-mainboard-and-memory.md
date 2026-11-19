# P11 · 10.主板和内存条搭配以及如何查看自己电脑的内存与主板信息｜用 CPU-Z 查主板、内存速率和各槽模组

## CPU-Z 的三页分别看什么

解压 CPU-Z 后，在 x64 Windows 上运行 `cpuz_x64.exe`。下面的读数来自一台使用技嘉 Z390 主板的电脑。[CPU-Z 官方下载](https://www.cpuid.com/softwares/cpu-z.html)

| 页面 | 读取与判断 |
| --- | --- |
| **主板（Mainboard）** | 记录制造商和完整型号。示例为 Gigabyte、`Z390 GAMING X-CF`，修订栏只写 `x.x`。选官网规格页时，再对照主板或包装上的 `REV` 标记。 |
| **内存（Memory）** | 查总容量、通道数和「时序 → DRAM Frequency」。示例为 DDR4、32 GB、双通道，时钟约 1499.6 MHz，乘 2 得约 **3000 MT/s**。乘 2 来自 DDR 每周期传输两次，和通道数无关。 |
| **SPD** | 在「内存插槽选择」逐槽查看容量、模组厂商、颗粒厂商和料号。示例四槽各 8 GB，共 32 GB，仍以双通道运行。Galaxy Microsystems 是模组厂商，Micron 是颗粒厂商。料号为空时可查内存条标签。 |

SPD 的「最大带宽」和时序表描述内存条保存的参数。例如 XMP-3002 列里的 **1501 MHz、16-18-18-38、1.350 V** 是一组预设。确认当前速率要回「内存」页读 DRAM Frequency。[英特尔 XMP 说明](https://www.intel.cn/content/www/cn/zh/gaming/extreme-memory-profile-xmp.html)

## 用主板规格确认能装什么

在厂商页面打开对应型号与修订版的「规格 → 内存」，查 DDR 代际、槽数、容量与速率。标有 **O.C.** 的是超频档。再按候选套条的料号，在「支持 → 内存兼容列表」（QVL）里核对测试过的容量和插条数量。

技嘉 **Z390 GAMING X rev. 1.0** 有四个 DDR4 槽，3000、4000、4266 均列为 O.C.。本机实际约为 DDR4-3000，换 DDR4-4000 是设想。另一款 **Z690 AORUS ELITE rev. 1.x** 的 DDR5 版列有 DDR5-6000（O.C.），不能把这组规格套到 Z390。混装两套标称速率相同的内存，仍需核对整组兼容性。[技嘉 Z390 规格](https://www.gigabyte.com/Motherboard/Z390-GAMING-X-rev-10/sp) · [技嘉 Z690 规格](https://www.gigabyte.com/Motherboard/Z690-AORUS-ELITE-rev-1x/sp)
