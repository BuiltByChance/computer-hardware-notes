# P14 · 13.硬盘的分类以及接口｜读懂硬盘速度，核对 M.2 插槽兼容性

给电脑加硬盘，先查硬盘完整型号和容量，再查主板或笔记本对应插槽的规格。这样可以判断盘能否装下、主板能否识别，以及这个位置能提供多大带宽。

## 读懂机械硬盘上的四个参数（00:00–05:13）

课堂打开的希捷酷鱼 `ST2000DM008` 标有 **2 TB、256 MB、7200 RPM、SATA**。2 TB 是存储容量，按十进制是 2000 GB，换成二进制约 1863 GiB。256 MB 是硬盘缓存。7200 RPM 是盘片每分钟转 7200 圈。SATA 是它与主机传输数据的接口。台式机中，这款 3.5 英寸硬盘固定在机箱硬盘位，SATA 数据线接主板，另一组 SATA 电源线接电源。

**转速和传输速度要分开读。** 希捷为这款盘标出的外圈最大持续读取速度是 **220 MB/s**。讲师写的“机械硬盘读写 ≤110 MB/s”不能用来判断这款盘的上限。外圈持续读取也不能代表随机读写或整盘写入的表现。[希捷酷鱼官方规格表](https://www.seagate.com/content/dam/seagate/zh_cn/content-fragments/products/datasheets/barracuda-3-5-hdd/barracuda-3-5-hdd-DS17-2-2603US-zh_CN.pdf)

## 认出 SSD 的外形和连接方式（05:13–07:39、13:14–20:15）

HDD 用旋转盘片和磁头读写，SSD（solid-state drive，固态硬盘）用闪存存储。SSD 有多种外形和连接方式。

| 看到的标注 | 安装前查什么 |
|---|---|
| 2.5 英寸 SATA SSD | 查 2.5 英寸盘位和 SATA 接口。台式机通常要接数据线和电源线。笔记本还要核对盘位厚度，以及原机是否需要排线或托架。 |
| mSATA | 一种小卡式 SATA SSD，多见于较老设备。查设备手册有没有专用的 mSATA 插槽。它和 M.2 的接头不同。 |
| PCIe 插卡式 SSD（AIC） | 像扩展卡一样插在主板长槽。核对物理长度、实际接通的通道数，以及显卡是否挡住位置。课堂的 WD_BLACK AN1500 使用 PCIe 3.0 ×8。[AN1500 官方规格](https://documents.sandisk.com/content/dam/asset-library/en_us/assets/public/western-digital/product/internal-drives/wd-black-ssd/data-sheet-wd-black-an1500-nvme-ssd.pdf) |
| U.2 | 常见于企业存储。核对硬盘、线缆或服务器背板是否明确支持 U.2。同为 2.5 英寸外形也可能使用不同接口。 |
| M.2 SATA / M.2 PCIe NVMe | **M.2** 描述卡和连接器的规格，**SATA / PCIe** 表示传输接口，**NVMe** 是 PCIe SSD 常用的存储协议。标签上的 **2280** 表示宽 22 mm、长 80 mm。卡能放进去，还要核对槽支持哪一种接口。[金士顿 M.2、SATA 与 NVMe 问答](https://www.kingston.com/cn/ssd/ssd-faq) |

## 从规格页和跑分截图读出速度（07:39–13:14、15:30–23:24）

先读清型号、容量和测试项目。**顺序读取 / 写入**分别反映连续读出、写入大块数据的速度，通常以 MB/s 标注。商品页的“最高”值是在指定条件下测得的。开机、加载游戏和解压还涉及小文件访问、CPU 等因素，不能直接用两块盘的顺序读速之比换算等待时间。

| 课堂示例 | 顺序读 / 写（MB/s） | 数值出处 |
|---|---:|---|
| WD Green SATA 1 TB，`WDS100T3G0A` | 545 / 未列 | 商品页只有读速，评论也没有找到同型号的写速。[WD Green 官方规格](https://documents.sandisk.com/content/dam/asset-library/en_us/assets/public/western-digital/product/internal-drives/wd-green-ssd/product-brief-wd-green-sata-ssd.pdf) |
| WD Green SATA 240 GB，`WDS240G1G0A` | 504.68 / 432.82 | 讲师放大的第三方 AS SSD Benchmark 截图，读的是第一行“连续读写”。评测正文另外转述了 540 / 405。两组数值都来自这篇 240 GB 评测。 |
| 三星 870 EVO 1 TB，2.5 英寸 SATA | 560 / 530 | 商品图和厂商的最高顺序值。SATA 6 Gb/s 的接口带宽与某款盘的读写值是两项指标。[三星 870 EVO 规格表](https://image.semiconductor.samsung.com/resources/data-sheet/Samsung_SSD_870_EVO_Data_Sheet_Rev1.1.pdf) |
| 三星 970 EVO Plus 1 TB、980 PRO 2 TB | 3500 / 3300、7000 / 5100 | 两款均为 M.2 NVMe，分别使用 PCIe 3.0 ×4、4.0 ×4。对比前要认准容量版本。[970 EVO Plus 规格](https://semiconductor.samsung.com/news-events/news/samsung-electronics-sets-new-performance-levels-for-consumer-nvme-ssds-with-970-evo-plus/) · [980 PRO 2 TB 规格](https://www.samsung.com.cn/memory-storage/nvme-ssd/980-pro-2tb-nvme-pcie-gen-4-mz-v8p2t0bw/) |

需要复核跑分时，看截图左上角的硬盘型号、容量，再分别读顺序和 4K 各行。课堂只查看了 **1.6.4194.30305** 的汉化版截图。作者站可下载的 ZIP 中，程序版本为 **2.0.7316.34247**。[AS SSD Benchmark 作者站下载（ZIP）](https://www.alex-is.de/progs/AS%20SSD%20Benchmark.zip)

## 按主板上的具体槽位判断兼容性（24:18–30:08）

1. **查对型号和槽号。** 在主板厂商页面打开「规格参数」→「存储 / Storage」，对照布局图找到 `M.2_1`、`M.2_2` 等标号。显卡长槽列在「扩展插槽」栏，要与 M.2 存储槽分开看。笔记本用完整机型查维护手册，确认剩余盘位和固定螺柱的位置。
2. **逐槽匹配尺寸和接口。** 华硕 ROG STRIX Z690-A GAMING WIFI（DDR5 吹雪）的布局图中，编号 **6** 是四个带散热片的 M.2 槽。四槽均支持 PCIe 4.0 ×4，只有 `M.2_4` 还支持 SATA。手里若是一块 M.2 SATA 2280 SSD，应选兼容 SATA 的那个槽。[华硕吹雪布局与规格](https://rog.asus.com.cn/motherboards/rog-strix/rog-strix-z690-a-gaming-wifi-model/)
3. **读懂代际和通道数。** `PCIe 4.0 ×4` 指第 4 代、4 条通道。兼容的 Gen4 NVMe 盘装入 Gen3 NVMe 槽，会按双方支持的链路工作，达不到 Gen4 标称峰值。若槽只支持 SATA，NVMe 盘可能根本无法识别。微星 PRO Z690-P DDR4 写的 `2 × Gen4 ×4` 指两个 Gen4 ×4 存储槽。[微星逐槽规格](https://www.msi.cn/Motherboard/PRO-Z690-P-DDR4/Specification) · [金士顿兼容性问答](https://www.kingston.com/cn/ssd/ssd-faq)
4. **商品图标得含糊时，查手册里的槽号。** 课堂把七彩虹 CVN Z690M GAMING FROZEN V20 商品图上的“PCIe 4.0/3.0”解读成两个槽各支持一代。原厂手册第 15 页逐槽列明，**M2_1、M2_2 都支持 PCIe 4.0 ×4，M2_2 还支持 SATA**。铭瑄 MS-iCraft Z690 WIFI 的规格则把四个 Gen4 ×4 M.2 槽与一个 Gen3 ×4 全长扩展槽分开列出。看图时要沿引线找到具体插槽。[七彩虹手册第 15 页](https://download.colorful.cn/EnDownload/MotherBroard/2022/Intel%20600/Manual/CVN%20Z690M.pdf?v=1#page=15) · [铭瑄布局图与存储规格](https://www.maxsun.com.cn/2021/1103/5619.html)
5. **核对散热片空间。** 有些盘自带散热片，有些主板已在槽上覆盖散热片，要按主板和 SSD 手册检查高度及安装方式。课中的 PS5 扩容盘就是一例。索尼要求兼容的 PCIe Gen4 ×4 M.2 NVMe SSD 配有效散热结构，并建议连续读取至少 5500 MB/s。[PlayStation 官方扩容规格](https://www.playstation.com/zh-hans-cn/support/hardware/ps5-install-m2-ssd/)
