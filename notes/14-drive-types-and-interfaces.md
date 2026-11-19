# P14 · 13.硬盘的分类以及接口｜读懂硬盘速度，核对 M.2 插槽兼容性

## 先看硬盘怎么接

| 类型 | 安装前核对什么 |
| --- | --- |
| 3.5 英寸 SATA 机械硬盘、2.5 英寸 SATA SSD | 台式机要有相应盘位、主板 SATA 数据接口和电源线。笔记本还要查厚度、排线和托架。 |
| mSATA、U.2 | mSATA 是较老的小卡式 SATA 接口，不能直接插 M.2。U.2 常用于企业存储，需匹配线缆或背板。 |
| PCIe 插卡式 SSD | 占用主板扩展槽。核对可用位置与实际通道数，例如 WD_BLACK AN1500 需要 PCIe 3.0 ×8 才能达到标称带宽。[AN1500 规格表](https://documents.sandisk.com/content/dam/asset-library/en_us/assets/public/western-digital/product/internal-drives/wd-black-ssd/data-sheet-wd-black-an1500-nvme-ssd.pdf) |
| M.2 SSD | **M.2** 是外形和连接器规格，**2280** 表示宽 22 mm、长 80 mm。M.2 盘可以走 SATA 或 PCIe，NVMe 是 PCIe SSD 常用的存储协议。[金士顿 SSD 问答](https://www.kingston.com/cn/ssd/ssd-faq) |

## 按具体 M.2 槽位选盘

1. 在主板官网「规格参数 → 存储设备」及手册布局图中找到具体槽号，逐项核对**尺寸、SATA 或 PCIe 支持、PCIe 代际和通道数**。显卡所在的全长扩展槽另列在「扩展槽」。
2. 例一，华硕 ROG STRIX Z690-A GAMING WIFI（DDR5）有四个 PCIe 4.0 ×4 M.2 槽，只有 **M.2_4** 兼容 SATA。M.2 SATA 2280 盘应装在这个槽。例二，七彩虹 CVN Z690M GAMING FROZEN V20 的 **M2_1、M2_2** 都支持 PCIe 4.0 ×4，只有 **M2_2** 还支持 SATA。选槽以手册逐槽说明为准。[华硕布局与规格](https://rog.asus.com.cn/motherboards/rog-strix/rog-strix-z690-a-gaming-wifi-model/) · [七彩虹手册第 15 页](https://download.colorful.cn/EnDownload/MotherBroard/2022/Intel%20600/Manual/CVN%20Z690M.pdf?v=1#page=15)
3. **PCIe 4.0 ×4** 表示第 4 代、4 条通道。Gen4 NVMe 盘装到兼容的 Gen3 槽，速率受 Gen3 限制。再查固定螺柱位置和散热片高度。PS5 扩容另有明确要求，包括 Gen4 ×4 NVMe、有效散热结构，建议顺序读取至少 5500 MB/s。[PlayStation 扩容规格](https://www.playstation.com/zh-hans-cn/support/hardware/ps5-install-m2-ssd/)

## 读速度先看测试项目

机械盘用旋转盘片和磁头读写，SSD 用闪存。希捷酷鱼 `ST2000DM008` 标的 7200 RPM 是转速，外圈最大持续读取为 **220 MB/s**。估算连续拷贝时间要查具体型号的 MB/s，单靠转速算不出传输速度。[希捷酷鱼规格表](https://www.seagate.com/content/dam/seagate/zh_cn/content-fragments/products/datasheets/barracuda-3-5-hdd/barracuda-3-5-hdd-DS17-2-2603US-zh_CN.pdf)

| 示例 | 顺序读／写（MB/s） | 怎样比较 |
| --- | ---: | --- |
| WD Green SATA 1 TB 与 240 GB | 1 TB 商品页只列读 545，240 GB 跑分为 504.68／432.82 | 后者是课堂展示的第三方 AS SSD 截图。看左上角型号和容量，再读第一行连续读写，不能借另一容量的成绩补写 1 TB 写速。[WD Green 规格](https://documents.sandisk.com/content/dam/asset-library/en_us/assets/public/western-digital/product/internal-drives/wd-green-ssd/product-brief-wd-green-sata-ssd.pdf) · [AS SSD 作者下载](https://www.alex-is.de/progs/AS%20SSD%20Benchmark.zip) |
| 三星 870 EVO 1 TB（SATA） | 560／530 | 厂商给出的最高顺序值。SATA 6 Gb/s 是接口带宽，单位不同。[870 EVO 规格表](https://image.semiconductor.samsung.com/resources/data-sheet/Samsung_SSD_870_EVO_Data_Sheet_Rev1.1.pdf) |
| 三星 970 EVO Plus 1 TB、980 PRO 2 TB | 3500／3300、7000／5100 | 两者均为 M.2 NVMe，分别使用 PCIe 3.0 ×4、4.0 ×4。顺序读写适合比较连续大文件，小文件访问要另看随机读写。[970 EVO Plus 规格](https://semiconductor.samsung.com/news-events/news/samsung-electronics-sets-new-performance-levels-for-consumer-nvme-ssds-with-970-evo-plus/) · [980 PRO 规格](https://www.samsung.com.cn/memory-storage/nvme-ssd/980-pro-2tb-nvme-pcie-gen-4-mz-v8p2t0bw/) |
