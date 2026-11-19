# P12 · 11.电源的用途｜读懂额定功率，按显卡型号核对整机电源要求

台式机电源（PSU）把插座提供的交流电转换成主板、CPU、显卡和硬盘等部件使用的直流电。笔记本通常由厂商配好外置电源适配器。自己组装台式机时，需要核对整机需要多大功率，以及电源能否给各部件提供合适的接口。

## 先看清瓦数写在哪里（03:18–06:14）

| 在哪里看 | 课堂示例 | 这个数回答什么问题 |
|---|---|---|
| 电源铭牌或商品规格的「额定功率」「持续输出功率」 | 京东长城 X7 标注 **750 W** | 这台电源在规定条件下能持续输出多大功率？ |
| 显卡厂商规格的「显卡功率」「TDP 功耗」 | 七彩虹 iGame GeForce RTX 3090 Ti Vulcan OC 官网标注 **510 W** | 厂商为这张显卡标出的功耗是多少？ |
| 同一张显卡规格里的「建议电源」「推荐系统功率」 | 七彩虹为该型号标注 **1000 W 及以上** | 给装有这张卡的整台电脑配电源，应从多大额定功率考虑？ |

视频里，讲师在京东显卡页点「规格与包装」，看到的是“建议电源 700W以上”，随后按自己的判断去找 1000 W 电源。复查时，在七彩虹的同型号产品页点 **「规格参数」**，可以同时找到「TDP功耗」「建议电源」「外接供电」三项。长城 X7 只用于辨认电源额定值。[七彩虹 Vulcan OC 产品页](https://www.colorful.cn/home/product?id=1935&mid=102)

## 给自己的配置核对电源（04:46–06:38、07:24–08:14）

1. **记下显卡完整型号和 CPU 型号。** 搜“显卡完整型号 + 建议电源”，打开这张卡的厂商规格页。保留品牌、系列和 `Ti`、`OC` 等后缀。以 RTX 3090 Ti 为例，NVIDIA 创始人版列出显卡功率 450 W、推荐系统功率 850 W，七彩虹 Vulcan OC 列出的两项数值都更高。[NVIDIA 创始人版规格](https://www.nvidia.cn/geforce/graphics-cards/30-series/rtx-3090-3090ti/) · [七彩虹 Vulcan OC 规格](https://www.colorful.cn/home/product?id=1935&mid=102)
2. **用整机建议值核对电源的额定输出。** “建议电源”已经针对整机，直接与电源的持续输出功率比较。再核对自己的 CPU、超频设置和其他硬件。换 CPU 或显卡后，按新组合重新查。[华硕整机电源功率估算工具](https://rog.asus.com/event/psu/asus-power-supply-calculator/us/index.html)
3. **核对供电接口和线材。** 比较显卡的「外接供电」与电源说明书列出的线材规格和数量。例如，七彩虹这张卡标注 **1 个 16 针接口**。额定输出达到整机建议值，且线材能按显卡和电源说明书接齐，才算完成纸面匹配。[七彩虹 Vulcan OC 规格](https://www.colorful.cn/home/product?id=1935&mid=102)

## 从 1000 W、金牌、全模组分别能知道什么（06:15–07:24）

视频展示的是海盗船 **RM1000x（2021 款）**。官网分别列出持续输出 1000 W、80 PLUS Gold、全模组和风扇停转模式，可逐项核对。[海盗船 RM1000x 产品规格](https://www.corsair.com/us/en/p/psu/cp-9020201-na/rmx-series-rm1000x-1000-watt-80-plus-gold-fully-modular-atx-psu-cp-9020201-na)

- **1000 W** 表示额定输出能力。要估算插座取电功率，用「硬件此刻所需的直流输出功率 ÷ 此时电源的转换效率」。例如，输出 450 W、效率 90% 时，插座端约为 **500 W**。这是换算示例，视频没有测量功耗。
- **80 PLUS 金牌** 表示电源在规定输入电压和负载条件下达到相应的转换效率。想了解散热或噪声，应另查风扇规格、停转条件或噪声曲线。[80 PLUS 官方效率等级表](https://www.clearesult.com/80plus/80plus-psu-ratings-explained) · [海盗船 RMx 2021 系列手册](https://assets.corsair.com/image/upload/corsairmedia/sys_master/productcontent/WW_RMx_Series_2021_QSG_Web_AD.pdf)
- **全模组** 表示电源侧的输出线可以按需插拔。装机时按本型号的线材兼容说明选线，用到哪些接口就接哪些线。[海盗船 RM1000x 产品规格](https://www.corsair.com/us/en/p/psu/cp-9020201-na/rmx-series-rm1000x-1000-watt-80-plus-gold-fully-modular-atx-psu-cp-9020201-na)
