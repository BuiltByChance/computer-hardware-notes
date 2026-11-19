# P15 · 14.其他存储介质｜选择文件传递方式，读懂移动硬盘规格

## 文件放在哪里，取决于下一步怎么用

| 需求 | 介质与取舍 |
|---|---|
| 读取旧资料 | 常见 3.5 英寸高密度软盘容量为 1.44 MB，需要匹配的软驱。光盘需要支持对应格式（CD、DVD 或蓝光）的光驱。写盘还要核对刻录功能和盘片类型。[IBM 软盘简史](https://www.ibm.com/history/floppy-disk) |
| 在另一台电脑取课件，或装系统 | 能联网并有访问权限时可用网盘。离线带文件可用 U 盘。要从 U 盘安装系统，需先将它制作成可启动的安装介质。重要资料另留独立副本。 |
| 笔记本盘位已满，或要带走上百 GB 的工程文件 | USB 移动硬盘可在机外扩容。同等预算下看移动机械硬盘（HDD）能提供多大容量。频繁拷贝大文件时，看移动固态硬盘（SSD）的持续读写表现。 |

## 从商品规格估算拷贝时间

先选完整型号和容量，再查「规格与包装」里的接口、随附线缆，以及厂商标注的顺序读取、写入速度。**Gb/s 是每秒多少吉比特，MB/s 是每秒多少兆字节，8 bit = 1 byte**。USB 接口的带宽上限和硬盘的文件传输速度是两个数值。

- **西部数据 Elements SE 2 TB** 的 USB 3.2 Gen 1 接口标称 5 Gb/s。从这项规格推不出盘片读写速度，课程中约 110 MB/s 是估值。[西数规格](https://www.westerndigital.com/products/portable-drives/wd-elements-se-usb-3-0-hdd?sku=WDBEPK0020BBK-WESN)
- **三星 T7 1 TB** 标称顺序读、写最高 1050、1000 MB/s，接近该速度需要支持 USB 3.2 Gen 2（10 Gb/s）和 UASP 的主机及合适线缆。相同形状的 USB-C 口可能更慢。上一代 T5 标称最高 540 MB/s。[三星 T7 规格](https://www.samsung.com.cn/memory-storage/portable-ssd/t7-1tb-gray-external-storage-nvme-1050-mbs-mu-pc1t0t-ww/) · [三星 T5/T7 对照](https://download.semiconductor.samsung.com/resources/brochure/PSSD-T7_Series-Brochure_Web_2109_230509.pdf)
- **闪迪 E61 1 TB** 的旧商品图标 IP55、2 米跌落防护。现行黑色款 `SDSSDE61-1T00-Z25` 标 IP65、最高 3 米。买盘时按包装上的完整料号查防护条件。[闪迪规格](https://www.sandisk.com/zh-cn/products/ssd/external-ssd/portable-ssd-sandisk-extreme-usb-3-2?sku=SDSSDE61-1T00-Z25)

交付 100 GB 文件时，若实际平均速度为 100 MB/s，单次复制约需 1000 秒，即近 17 分钟。出发前写入移动盘，现场再从移动盘读出，分别受来源盘读取、连接带宽和目标盘写入限制。预留两次复制的时间，并从目标目录打开关键文件确认交付成功。
