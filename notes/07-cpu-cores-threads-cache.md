# P7 · 6.CPU 核心、线程、缓存的用途｜从商品页读懂核心数、睿频与三级缓存

看到“12 核 20 线程、最高 5.0 GHz、25 MB 三级缓存”，可以分三个问题读：工作能拆给多少个核心？少数核心忙时最高能跑到什么频率？CPU 能把多少常用数据留在三级缓存里？判断自己的软件能快多少，还需要看它能用到哪些资源。

## 从商品页抄对参数（00:00–02:58）

1. **先定型号。** 在笔记本商品页的「选择版本」切换配置，再看标题。课里的联想 ThinkBook 14p 同时列有 R7-5800H 和 R5-5600H。只记“ThinkBook 14p”，无法确定处理器。
2. **再看字段。** 课中京东 CPU 商品页的标题列出核心、线程、最高睿频和三级缓存。「规格与包装」另列主频和功率。如果那里没列核心数，可到「商品介绍」找型号对照表，沿同一行读 `Cores / Threads`。讲师用 3990X 作搜索词，实际点开并读到的是 **Threadripper PRO 3995WX，64 核 / 128 线程**。[AMD 的 3995WX 规格表](https://ir.amd.com/news-events/press-releases/detail/959/amd-announce-worlds-first-64-core-pro-workstation-the-lenovo-thinkstation-p620-the-pinnacle-of-performance-for-modern-professionals)
3. **用厂商规格页复核。** 对照完整型号，包括末尾的字母。把“主频”细分成性能核或能效核的基本频率，把“功率”细分成基础功耗或最大睿频功耗，再比较两款 CPU。

课中交替出现下面两款第 12 代桌面酷睿。两行分别对应京东商品页和讲师的记事本，基本频率等字段已按英特尔规格补全。[i7-12700K 官方规格](https://www.intel.cn/content/www/cn/zh/products/sku/134594/intel-core-i712700k-processor-25m-cache-up-to-5-00-ghz/specifications.html) · [i9-12900K 官方规格](https://www.intel.cn/content/www/cn/zh/products/sku/134599/intel-core-i912900k-processor-30m-cache-up-to-5-20-ghz/specifications.html)

| 型号 | 物理核心 | 硬件线程 | 性能核基本频率 | 能效核基本频率 | 最高睿频 | 三级缓存（L3） |
| --- | --- | --- | --- | --- | --- | --- |
| i7-12700K | 12（8 性能核 + 4 能效核） | 20 | 3.6 GHz | 2.7 GHz | 5.0 GHz | 25 MB |
| i9-12900K | 16（8 性能核 + 8 能效核） | 24 | 3.2 GHz | 2.4 GHz | 5.2 GHz | 30 MB |

## 为什么 12 核能有 20 线程（01:22–05:03）

核心是执行指令的物理单元。规格中的“线程数”指 CPU 提供给操作系统的硬件执行上下文。以 i7-12700K 为例，8 个性能核各支持 2 个硬件线程，4 个能效核各支持 1 个，所以共 **8 × 2 + 4 × 1 = 20** 个。同一核心上的两个线程会共享执行资源。

评估多核时，先问软件能不能把工作拆开。并行渲染可以把不同画块交给多个核心；必须等上一步算完才能继续的步骤，增加核心对它的用处就小得多。多开程序也能用到额外的核心，但还要看它们是否同时需要计算。

## 怎样读“主频 3.6 GHz，最高 5.0 GHz”（05:03–07:45，功耗见 09:33）

i7-12700K 商品页把 3.6 GHz 简写成“主频”，对应的是**性能核基本频率**。1 GHz 表示每秒 10 亿个时钟周期。不同架构每个周期能完成的工作量不同，跨代比较要结合具体任务的测试。[英特尔对时钟频率的说明](https://www.intel.com/content/www/us/en/gaming/resources/cpu-clock-speed.html)

**最高睿频**表示条件允许时可达到的最高频率。实际频率会随负载、活跃核心数、温度和功耗变化，空闲时可以低于基本频率。视频里“打游戏从 3.6 升到 5.0”是为了说明升频的假设场景。商品表里的 **190 W** 也有明确口径：它是这款 i7 的最大睿频功耗，基础功耗为 **125 W**。[英特尔睿频说明](https://www.intel.cn/content/www/cn/zh/support/articles/000007359/processors/intel-core-processors.html) · [i7-12700K 功耗规格](https://www.intel.cn/content/www/cn/zh/products/sku/134594/intel-core-i712700k-processor-25m-cache-up-to-5-00-ghz/specifications.html)

## 三级缓存多 5 MB，有什么用（07:45–09:33）

L3 是 CPU 缓存层级中的第三级。核心需要的数据如果没在更近的缓存中找到，但能在 L3 命中，就能省去一次访问主内存的等待。i7 的 25 MB 和 i9 的 30 MB 表示这一层能容纳多少数据，单位是容量。

例如，程序反复读取同一批数据时，如果更大的 L3 正好能把这批常用数据留住，就可能减少等待。若数据很少重复使用，额外的容量帮助就有限。两款 CPU 还同时存在核心数、频率等差异，不能根据多出的 5 MB 单独推算游戏帧率。
