# P6 · 5.AMD CPU 系列详解（2024年重置版）｜查型号、读规格与区分平台

只知道“锐龙 9”还不足以判断两颗 CPU 有什么区别。先记下完整型号和使用平台，再查核心与线程、频率、三级缓存、默认 TDP，以及自己用得上的核显或商用功能。

## 在 Windows 找到本机型号，再到 AMD 查规格（00:38、07:50）

1. 在 Windows 开始菜单搜索并打开「设备管理器」，展开「处理器」。课中从文件资源管理器中「此电脑」的「管理」进入，再选「系统工具 → 设备管理器 → 处理器」。
2. 抄下任意一行的完整名称，保留末尾字母。讲师电脑显示的是 `AMD Ryzen 9 7950X3D 16-Core Processor`。同名条目对应系统识别到的逻辑处理器，不能据此数出装了几颗实体 CPU。
3. 打开 AMD 产品规格页。查锐龙、速龙或工作站型号，选「台式处理器、笔记本电脑处理器和工作站处理器规格 → 查看全部」。查 EPYC，选「服务器处理器规格 → 查看全部」。[AMD 产品规格](https://www.amd.com/zh-cn/products/specifications.html)
4. 找到与本机名称或商品标题一致的完整型号，核对平台、核心数和线程数。比较缓存时认准 L3（三级缓存），比较频率时分别看基本频率和最高加速频率。桌面版和移动版可能同属锐龙 9，但采用不同的核心配置与散热设计。[个人电脑与工作站规格表](https://www.amd.com/zh-cn/products/specifications/processors.html) · [服务器规格表](https://www.amd.com/zh-cn/products/specifications/server-processor.html)

## 读懂 Ryzen 9 7950X3D，与相近型号成对比较（02:24–13:10）

`Ryzen` 是锐龙家族，`9` 是这个家族里的产品档位，`7950X3D` 属于桌面锐龙 7000 系列。这款 CPU 采用 Zen 4 架构。系列号、架构和档位要分别查，即使都是锐龙 9，7950 和 7900 的核心数也不同。[AMD 锐龙 9 7950X3D](https://www.amd.com/zh-cn/products/processors/desktops/ryzen/7000-series/amd-ryzen-9-7950x3d.html)

| 桌面锐龙 9 | 核心 / 线程 | 基本频率 | 最高加速频率 | L3 缓存 | 默认 TDP |
| --- | --- | --- | --- | --- | --- |
| 7950X3D | 16 / 32 | 4.2 GHz | 5.7 GHz | 128 MB | 120 W |
| 7950X | 16 / 32 | 4.5 GHz | 5.7 GHz | 64 MB | 170 W |
| 7900X3D | 12 / 24 | 4.4 GHz | 5.6 GHz | 128 MB | 120 W |
| 7900X | 12 / 24 | 4.7 GHz | 5.6 GHz | 64 MB | 170 W |

横向读一行可以避免把基本频率和加速频率抄反。纵向比较前两行，7950X3D 通过 3D V-Cache 堆叠技术把 L3 增至 128 MB，核心数和最高加速频率与 7950X 相同，基本频率略低。对缓存敏感的游戏可能受益，判断具体游戏要看相同条件下的测试。默认 TDP 是散热设计指标，整机实际用电量需要测量。[AMD 四款处理器规格对照，第 9 页](https://gpuopen.com/gdc-presentations/2023/GDC-2023-AMD-Ryzen-Processor-Software-Optimization.pdf#page=9)

## 按使用场景看家族和后缀

| 场景 | 课中型号 | 查规格时看什么 |
| --- | --- | --- |
| 入门整机（00:56） | Athlon Silver 3050GE | 课中详情页标有 OEM Only（面向整机厂商），为 2 核 4 线程。判断有无盒装零售版，要核对具体型号的供货说明。 |
| 企业电脑（05:20） | Ryzen 9 PRO 7945 等 | 企业集中管理时，查看平台是否支持 AMD Memory Guard 全系统内存加密，以及基于 DASH 标准的远程管理。[AMD PRO 技术](https://www.amd.com/zh-cn/products/processors/technologies/pro-technologies.html) |
| 计划用核显的台式机（15:38） | 8700G、8600G | 8700G 是 8 核 16 线程，集成 Radeon 780M。8600G 是 6 核 12 线程，集成 Radeon 760M。只配核显时，先查显卡型号，再看目标游戏和分辨率下的表现。需要专用 AI 加速时看 NPU 一列，这两款有 NPU，同表的 8500G 和 8300G 没有。[AMD 8000G 型号对照表](https://www.amd.com/zh-cn/partner/articles/ryzen-8000G-series-processors.html) |
| 多线程工作站（17:55） | Threadripper PRO 7995WX、Threadripper 7980X | 两款分别为 96 核 192 线程、64 核 128 线程。评估渲染等并行任务时，先看软件能利用多少线程。PRO 7000 WX 系列也有面向自行装机用户的销售渠道。[AMD Threadripper 7000 发布资料](https://ir.amd.com/news-events/press-releases/detail/1162/amd-introduces-new-amd-ryzen-threadripper-7000-series-processors-and-ryzen-threadripper-pro-7000-wx-series-processors-for-the-ultimate-workstation) |
| 云服务与数据中心（22:42） | EPYC（霄龙）9004 | 9754 和 9754S 都是 128 核，前者有 256 线程，后者为 128 线程。规划并发任务时，核数和线程数要分开核对。[AMD EPYC 9004 规格](https://www.amd.com/en/products/processors/server/epyc/4th-generation-9004-and-8004-series.html) |

## 笔记本要单独查移动版（13:10、23:59）

- **先确认平台。** 课程里的 8000G 用于台式机，8040 属于笔记本系列。查到 Ryzen 9 8945HS 的处理器规格，只能确认这颗芯片的参数。确认某款笔记本是否搭载它，要看整机厂商给出的具体配置。[AMD 锐龙 9 8945HS](https://www.amd.com/zh-cn/products/processors/laptop/ryzen/8000-series/amd-ryzen-9-8945hs.html)
- **把后缀当作查找线索。** 在课中的 7000 系列笔记本里，HX 多见于高性能机型，HS 兼顾性能与机身尺寸，U 偏重能效。7945HX 的规格为 16 核 32 线程、基本频率 2.5 GHz、最高加速频率 5.4 GHz。判断持续性能和续航，还要看具体笔记本的散热、功耗设置和电池。[AMD 锐龙 9 7945HX](https://www.amd.com/en/products/processors/laptop/ryzen/7000-series/amd-ryzen-9-7945hx.html)
- **逐行读地区和频率。** 课中“仅限中国大陆”标在 7940H 这一行。7940H 与旁边的 7940HS 都是 8 核 16 线程，基本频率同为 4.0 GHz，最高加速频率同为 5.2 GHz。单看末尾多一个 S，无法给两台笔记本排性能高低。[AMD 锐龙 9 7940H](https://www.amd.com/zh-cn/products/processors/laptop/ryzen/7000-series/amd-ryzen-9-7940h.html) · [AMD 锐龙 9 7940HS](https://www.amd.com/en/products/processors/laptop/ryzen/7000-series/amd-ryzen-9-7940hs.html)
