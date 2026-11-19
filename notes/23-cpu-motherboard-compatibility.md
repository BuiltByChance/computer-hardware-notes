# P23 · 22-1.CPU搭配主板｜从 CPU 插槽查到主板支持列表与 BIOS 版本

## 换 CPU 前怎样确认主板支持

1. **用插槽和芯片组筛选。** 在 CPU 厂商规格页查插槽与兼容芯片组。例如 i9-14900K 用 LGA1700，可从 B760、Z790 等芯片组选板。Ryzen 9 7950X3D 用 AM5，Threadripper 7980X 用 sTR5，两者需要不同的主板。[Intel i9-14900K 兼容芯片组](https://www.intel.cn/content/www/cn/zh/products/sku/236773/intel-core-i9-processor-14900k-36m-cache-up-to-6-00-ghz/compatible.html) · [AMD 7950X3D 规格](https://www.amd.com/zh-cn/products/processors/desktops/ryzen/7000-series/amd-ryzen-9-7950x3d.html)
2. **用主板支持表确认具体型号。** 抄下板名和硬件修订号（如 rev. 1.0），打开对应主板的“支持 → CPU 支持列表”。按 CPU 完整型号查找，保留 K、KF、X3D 等后缀。读取这一行的“Since BIOS”或“Validated since BIOS”，得到厂商列明已验证支持该 CPU 的起始 BIOS。
3. **与板上已装的 BIOS 比较。** 现有电脑可在 UEFI 设置中查看版本，买旧库存可向卖方核实。若版本过早，先查这块板的手册，确认更新时是否需要一颗已受支持的 CPU，再安排换装。

| 主板和硬件版本 | 目标 CPU | 支持表列出的起始 BIOS |
| --- | --- | --- |
| 技嘉 Z790 AORUS ELITE AX rev. 1.0 | Core i9-14900K / 14900KF | [F9](https://www.aorus.com/tw/motherboards/Z790-AORUS-ELITE-AX-rev-10/support/cpu-support) |
| 华硕 ROG STRIX B650E-E GAMING WIFI | Ryzen 9 7950X3D | [1409](https://rog.asus.com/motherboards/rog-strix/rog-strix-b650e-e-gaming-wifi-model/helpdesk_cpu/) |
| 技嘉 TRX50 AERO D rev. 1.0 | Ryzen Threadripper 7980X | [F1](https://www.aorus.com/tw/motherboards/trx50-aero-d-rev-10/support/cpu-support) |

## 能装上 CPU 后，还要核对什么

- **旧内存能否沿用。** i9-14900K 支持 DDR4 和 DDR5，实际能插哪一种取决于主板的 DIMM 槽。要沿用 DDR4，就查具体板型的内存规格。[Intel 内存规格](https://www.intel.cn/content/www/cn/zh/products/sku/236773/intel-core-i9-processor-14900k-36m-cache-up-to-6-00-ghz/specifications.html)
- **盘和外设能否接齐。** 芯片组表列出平台上限，成品主板的规格才列出实际提供的 M.2 槽数、协议和 USB 速率。[主板接口读法](24-motherboard-slots-and-rear-io.md)
- **机箱能否容纳。** 用主板厂商的板型和尺寸对照机箱支持列表。例如课堂商品标题写 EATX，技嘉给 X670E AORUS PRO X 标的是 ATX，30.5 × 24.4 cm。[技嘉主板规格](https://www.gigabyte.com/Motherboard/X670E-AORUS-PRO-X/sp?lan=en)
