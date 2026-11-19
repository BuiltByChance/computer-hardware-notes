# P21 · 20.笔记本选择实战，游戏配置信息表｜读懂游戏本商品页，对照 Steam 系统需求

## 读游戏本商品页，先锁定具体配置

同一系列里，标题或按钮上的一个选择可能同时改变显卡、显存和硬盘。打开商品页后，记下**机型编号**，再分别抄出 CPU、笔记本 GPU、显存、系统内存和 SSD。惠普暗影精灵 8 的两种配置展示了为什么要这样读。

| 机型编号 | CPU（商品标题） | 独显与显存 | 系统内存 | SSD |
|---|---|---|---|---|
| 16-b1011TX | 第 12 代酷睿 i7 | RTX 3070 Ti Laptop，8 GB | 16 GB DDR5 | 1 TB |
| 16-b1005TX | 酷睿 i7-12700H | RTX 3050 Ti Laptop，4 GB | 16 GB DDR5 | 512 GB |

在这两款之间切换「选择存储」，请用更新后的机型编号确认所选配置。比较其他游戏本还要查屏幕和显卡的供电设置。例如宏碁新暗影骑士·擎的商品图标 **RTX 3060、140 W、2.5K、165 Hz**。165 Hz 表示屏幕的刷新上限，要判断能否跑满它，应看这款整机在目标分辨率下的游戏帧率。

## 用 Steam 系统需求对照自己的机器

1. 在 Steam 商店搜索游戏，核对**游戏名与版本**，往下找到「系统需求」。原版、重制版和资料片可能有独立的配置表。[Steam 商店](https://store.steampowered.com/)
2. 对照最低与推荐两栏，分别检查操作系统、CPU、系统内存、GPU 及其显存、磁盘**可用空间**。系统内存对应笔记本的「16 GB DDR5」，显存对应「RTX 3050 Ti 4 GB」。两个容量不能相加或相互补足。
3. 阅读推荐栏的画质、分辨率和帧率附注。不同游戏的「推荐」目标可能不同。换成笔记本 GPU 时，还要核对对应机型的表现。

| 游戏及版本 | 推荐 CPU（Intel / AMD） | 系统内存（最低 → 推荐） | 推荐 GPU 与显存（NVIDIA / AMD） | 可用空间 |
|---|---|---|---|---|
| [荒野大镖客：救赎 2](https://store.steampowered.com/app/1174180/Red_Dead_Redemption_2/?l=schinese) | i7-4770K / Ryzen 5 1500X | 8 → 12 GB | GTX 1060 6 GB / RX 480 4 GB | 150 GB |
| [艾尔登法环，本体](https://store.steampowered.com/app/1245620/ELDEN_RING/?l=schinese) | i7-8700K / Ryzen 5 3600X | 12 → 16 GB | GTX 1070 8 GB / RX Vega 56 8 GB | 60 GB |
| [地平线 零之曙光，2020 Complete Edition](https://store.steampowered.com/app/1151640/Horizon_Zero_Dawn_Complete_Edition/?l=schinese) | i7-4770K / Ryzen 5 1500X | 8 → 16 GB | GTX 1060 6 GB / RX 580 8 GB | 100 GB |

第二款暗影精灵的 16 GB 系统内存达到《艾尔登法环》推荐值，但 4 GB 显存低于推荐栏两款显卡的 8 GB。Steam 简体中文推荐栏给出的估计是 **1080p、高画质、60 fps**。能否达到该目标，应查这款游戏在 RTX 3050 Ti 笔记本上的实测。安装《荒野大镖客：救赎 2》则要看安装盘能否腾出 150 GB，只知道 SSD 标称 512 GB 仍不足以判断。

《荒野大镖客：救赎 2》的最低系统已从录屏中的 Windows 7 SP1 更新为 **Windows 10 64 位**。[Rockstar 当前配置](https://support.rockstargames.com/articles/1LqwiYbHeiSyo3dtcVyS1N/red-dead-redemption-2-pc-system-requirements)
