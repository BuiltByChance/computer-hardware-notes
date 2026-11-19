# P6 · 5.AMD CPU 系列详解（2024年重置版）｜查型号、读规格与区分平台

**先确认本机型号。** Windows 中打开「设备管理器 → 处理器」，抄下一行完整名称，例如 `Ryzen 9 7950X3D`。多行同名条目对应逻辑处理器。查锐龙、速龙或线程撕裂者，进入个人电脑与工作站规格表。查霄龙（EPYC），进入服务器规格表。[AMD 个人电脑与工作站规格](https://www.amd.com/zh-cn/products/specifications/processors.html) · [AMD 服务器规格](https://www.amd.com/zh-cn/products/specifications/server-processor.html)

## 桌面锐龙 9 怎么比较

`Ryzen 9` 表示家族和档位，`7950X3D` 才是具体型号。下列四款都属于采用 Zen 4 架构的桌面锐龙 7000 系列。

| 型号 | 核心 / 线程 | 基本 / 最高加速频率 | 三级缓存 | 默认 TDP |
| --- | --- | --- | --- | --- |
| 7950X3D | 16 / 32 | 4.2 / 5.7 GHz | 128 MB | 120 W |
| 7950X | 16 / 32 | 4.5 / 5.7 GHz | 64 MB | 170 W |
| 7900X3D | 12 / 24 | 4.4 / 5.6 GHz | 128 MB | 120 W |
| 7900X | 12 / 24 | 4.7 / 5.6 GHz | 64 MB | 170 W |

同样是 16 核，7950X3D 通过 3D V-Cache 增大三级缓存，基本频率比 7950X 略低。选游戏 CPU 时，看目标游戏能从更大缓存获益多少。TDP 描述散热设计，整机实际耗电量需测量。[AMD 四款型号对照，第 9 页](https://gpuopen.com/gdc-presentations/2023/GDC-2023-AMD-Ryzen-Processor-Software-Optimization.pdf#page=9)

## 按平台和用途筛选

| 用途 | 选型要点 |
| --- | --- |
| 入门或商用整机 | 速龙 Silver 3050GE 为 2 核 4 线程，面向整机厂商（OEM）。企业若需全系统内存加密，看整机是否支持 AMD Memory Guard。需要远程管理时查 DASH 管理标准的支持情况。[AMD PRO 技术](https://www.amd.com/zh-cn/products/processors/technologies/pro-technologies.html) |
| 靠核显运行游戏 | 桌面 8700G 配 Radeon 780M，8600G 配 760M。按分辨率查目标游戏测试。若软件会用到神经网络处理器（NPU），8700G、8600G 配有 NPU，8500G 和 8300G 没有。[AMD 8000G 对照](https://www.amd.com/zh-cn/partner/articles/ryzen-8000G-series-processors.html) |
| 笔记本 | 8040 是移动系列，8000G 是桌面系列。移动锐龙 7000 的 HX 偏高性能，HS 兼顾性能与机身尺寸，U 偏能效。7940H 与 7940HS 都是 8 核 16 线程、基本 4.0 GHz、最高 5.2 GHz。判断持续性能要看具体整机的散热和功耗设置。 |
| 并行工作站 | 线程撕裂者（Threadripper）7980X 有 64 核 128 线程，PRO 7995WX 有 96 核 192 线程。先确认渲染等任务能同时利用多少线程。 |
| 服务器 | EPYC 9754 与 9754S 都有 128 核，前者有 256 线程，后者有 128 线程。估算并发能力时要分别核对核心和线程。[EPYC 9004 规格](https://www.amd.com/en/products/processors/server/epyc/9004-series.html) |
