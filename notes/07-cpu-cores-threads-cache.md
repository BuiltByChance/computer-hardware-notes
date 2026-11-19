# P7 · 6.CPU 核心、线程、缓存的用途｜从商品页读懂核心数、睿频与三级缓存

## 核心与线程怎样参与并行计算

核心是执行指令的物理单元，规格表的线程数表示系统可调度的硬件线程数。i7-12700K 的 8 个性能核各支持 2 个线程，4 个能效核各支持 1 个，合计 **12 核、20 线程**。同一核心上的线程共享执行资源。

多个核心适合能拆开的工作，例如把一帧画面分成多个区域并行渲染，或让几个程序同时计算。若某一步必须等待上一步的结果，多加核心带来的加速就有限。

## 基本频率、睿频和功耗

| 型号 | 核心 / 线程 | 性能核 / 能效核基本频率 | 最高睿频 | 三级缓存 |
| --- | --- | --- | --- | --- |
| i7-12700K | 12 / 20 | 3.6 / 2.7 GHz | 5.0 GHz | 25 MB |
| i9-12900K | 16 / 24 | 3.2 / 2.4 GHz | 5.2 GHz | 30 MB |

1 GHz 表示每秒 10 亿个时钟周期。每个周期完成的工作量因架构和任务而异。以表中的 i7 为例，3.6 GHz 指性能核基本频率，5.0 GHz 是条件允许时的最高睿频。实际频率随负载、活跃核心数、温度和功耗变化，空闲时还会降频。它的基础功耗为 125 W，最大睿频功耗为 190 W。[i7-12700K 规格](https://www.intel.cn/content/www/cn/zh/products/sku/134594/intel-core-i712700k-processor-25m-cache-up-to-5-00-ghz/specifications.html) · [i9-12900K 规格](https://www.intel.cn/content/www/cn/zh/products/sku/134599/intel-core-i912900k-processor-30m-cache-up-to-5-20-ghz/specifications.html)

## 三级缓存能减少哪些等待

更靠近核心的缓存没找到数据时，如果能在三级缓存（L3）中读到，就省去一次访问主内存的等待。程序反复读取同一批数据时，较大的 L3 有机会把更多数据留下。上表两款相差 5 MB，游戏帧率还受核心、频率和游戏本身影响。

Threadripper PRO 3995WX 的 64 核可提供 128 个硬件线程。对渲染这类并行任务，不能把 128 个线程按 128 个物理核心估算。[AMD 3995WX 规格表](https://ir.amd.com/news-events/press-releases/detail/959/amd-announce-worlds-first-64-core-pro-workstation-the-lenovo-thinkstation-p620-the-pinnacle-of-performance-for-modern-professionals)
