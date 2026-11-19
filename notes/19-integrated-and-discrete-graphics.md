# P19 · 18.核显、独显的区别以及用途｜查 CPU 有没有核显，判断是否需要独显

## 先判断显示器接哪儿

| 台式机的图形配置 | GPU 和显存在哪里 | 显示器接哪里 |
|---|---|---|
| 使用核显 | GPU 集成在处理器里，通常借用系统内存 | 接主板的 HDMI 或 DisplayPort。先确认所装 CPU 有核显、主板有对应输出口。 |
| 使用独显 | GPU 位于单独的显卡上，通常配有专用显存 | 接独显挡板上的视频口。只有独显、CPU 无核显的普通台式机，接主板视频口通常无法显示。 |

笔记本可同时配备核显和独显。“独显”本身不说明性能，比较时查笔记本 GPU 的完整型号及其供电设置。[Intel 对集显和独显的说明](https://www.intel.cn/content/www/cn/zh/support/articles/000057824/graphics.html)

## 用 CPU 完整型号核对核显

在商品页切到具体配置，确认标题已经更新，再打开参数对照图，沿着**所选型号的一列**找到「核显」。厂商规格页可直接查 **GPU Specifications → GPU Name**。

| Intel 酷睿桌面 CPU | 核显 |
|---|---|
| Core i7-12700K、i7-12700 | Intel UHD Graphics 770 |
| Core i7-11700K | Intel UHD Graphics 750 |
| Core i7-12700F、i7-12700KF、i7-11700KF | 无可用核显，输出画面需要独显 |

在这组 Intel 型号中，**K 表示倍频解锁，F 表示需要独显**。12700KF 的两个后缀同时生效。[i7-12700K 官方规格](https://www.intel.cn/content/www/cn/zh/products/sku/134594/intel-core-i712700k-processor-25m-cache-up-to-5-00-ghz/specifications.html) · [Intel 后缀说明](https://www.intel.cn/content/www/cn/zh/processors/processor-numbers.html) · [Intel 对 F 后缀的说明](https://www.intel.cn/content/www/cn/zh/support/articles/000058487/processors.html)

## 按实际软件决定是否配独显

- **办公、上网、播放视频**可先考虑核显。已有独显时，保留核显也让拆下独显后仍有显示输出。
- **游戏**按目标游戏、分辨率、画质和帧率查具体核显的测试。例如 AMD 对锐龙 7 8700G 的 Radeon 780M 公布了《英雄联盟》等游戏在 1080p 低画质下的表现。[AMD 测试条件](https://www.amd.com/zh-cn/partner/articles/ryzen-8000G-series-processors.html)
- **大型游戏、影视渲染**要同时核对软件支持的 GPU 和显存需求。确认需要独显后，再比较整套机器采用 F 与非 F 处理器的成本。
