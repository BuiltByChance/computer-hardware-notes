# P24 · 22-2.总结主板的知识点｜看主板布局图，分清后置接口与扩展接针

## 看主板布局图装配件

以下位置对应华硕 **ROG STRIX Z690-A GAMING WIFI D4**。查手册时保留 D4 后缀，它决定了这块板使用哪一代内存。[华硕布局图](https://rog.asus.com.cn/motherboards/rog-strix/rog-strix-z690-a-gaming-wifi-d4-model/)

| 部件 | 该插哪里，为什么 |
| --- | --- |
| CPU | ① 是 LGA1700 插槽。换 CPU 前用完整型号查[支持列表和起始 BIOS](23-cpu-motherboard-compatibility.md)。 |
| 内存 | ④ 是 CPU 右侧四条 DDR4 槽。标为 OC 的速率属于超频档，实际速率要在开机后核对。 |
| 显卡 | 优先用最靠近 CPU 的 ②，支持 PCIe 5.0 ×16。下面另一条槽外形同样长，只接了 PCIe 3.0 ×4，带宽较低。 |
| M.2 固态硬盘 | ⑤ 标出四个 M.2 位置，均支持 PCIe 4.0 ×4。若硬盘走 SATA 协议，这块板上只有 M.2_4 能用。 |

## 看后置面板和板内接针连外设

- **显示器。** 使用独显时，把线接到显卡挡板上的 HDMI 或 DisplayPort。使用主板后置视频口时，先确认所装 CPU 带核显。
- **USB-C。** 华硕图中 ⑦ 和 ⑪ 都是机箱背面能直接插的 USB-C，标称速率分别是 20 和 10 Gb/s。⑬ 位于板内，要接机箱前置 USB-C 的线。⑯ 供兼容雷电扩展卡使用，需装卡才有对应的外接端口。[华硕中文手册](https://dlcdnets.asus.com/pub/ASUS/mb/LGA1700/ROG_STRIX_Z690-A_GAMING_WIFI_D4/C19937_ROG_STRIX_Z690-A_GAMING_WIFI_D4_UM_V6_WEB.pdf)
- **网线与音频线。** ⑧ 是 2.5 GbE 有线网口。⑫ 的音频孔分输入和输出，麦克风接 Mic In，有源音箱接 Line Out。
- **USB-A。** 技嘉 Z690 AORUS MASTER rev. 1.x 的五个红色后置 USB-A 均标为 10 Gb/s。换主板时按具体型号查接口图，颜色本身不能确定速率。[技嘉后置接口规格](https://www.gigabyte.com/Motherboard/Z690-AORUS-MASTER-rev-1x/sp)
