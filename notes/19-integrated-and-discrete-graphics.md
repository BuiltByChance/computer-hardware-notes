# P19 · 18.核显、独显的区别以及用途｜查 CPU 有没有核显，判断是否需要独显

## 核显和独显分别装在哪里

**核显**是集成在处理器里的 GPU，通常与 CPU 共用系统内存。普通办公台式机只用核显就能显示桌面、播放视频，前提是处理器有核显，主板也提供合适的视频输出接口。**独显**是独立于 CPU 的 GPU，通常有专用显存。台式机常见的是插在主板上的显卡，笔记本也可以内置独显。[Intel 对核显与独显的说明](https://www.intel.cn/content/www/cn/zh/support/articles/000057824/graphics.html)

## 用完整型号查核显（00:48–01:38、03:52–04:33）

1. 记下完整 CPU 型号，保留末尾字母。课堂在京东搜索 `intel 12代`，打开 **i7-12700K**，在商品主图下切到第二张参数对照图，鼠标移到图上放大。先对准型号所在的列，再向下读「核显」一行。
2. 在「选择平台」中依次切换到 **i7-12700F** 和 **i7-12700KF**。确认商品标题随选择更新，再打开 KF 页的对照图。两次查到的结果如下。

| 商品对照图上的 CPU 型号 | 「核显」一行 | 普通台式机怎样接显示器 |
|---|---|---|
| i7-12700K、i7-12700 | UHD 770 | 使用核显时，接主板的视频输出口 |
| i7-11700K | UHD 750 | 使用核显时，接主板的视频输出口 |
| i7-12700KF、i7-12700F、i7-11700KF | 无 | 另配独显，将显示器接到独显的视频输出口 |

复核其他型号时，在 Intel 产品规格页找 **GPU Specifications → GPU Name**。例如 i7-12700K 列出 **Intel UHD Graphics 770**。Intel 酷睿桌面型号中的 **K** 表示倍频解锁。判断有无核显时留意 **F**，带 F 或 KF 后缀的型号需要独显，官方规格页会省略处理器显卡一栏。[i7-12700K 官方规格](https://www.intel.cn/content/www/cn/zh/products/sku/134594/intel-core-i712700k-processor-25m-cache-up-to-5-00-ghz/specifications.html) · [Intel 桌面处理器后缀](https://www.intel.cn/content/www/cn/zh/processors/processor-numbers.html) · [Intel 对 F 后缀的说明](https://www.intel.cn/content/www/cn/zh/support/articles/000058487/processors.html)

## 哪些用途值得配独显（01:38–03:52、04:33–结尾）

- **办公、上网、播放视频**可以先选带核显的处理器。若打算省去独显，装机前就要核对 CPU 型号和主板显示接口。
- **玩游戏**要看具体核显在目标游戏、分辨率和画质下能否达到期望帧率。课上用 GTX 1050 作性能参照，没有实测。一个可复核的例子是 AMD 用锐龙 7 8700G 的 Radeon 780M 核显，在 1080p 低画质下测试了《英雄联盟》等游戏。[AMD 的游戏与测试条件](https://www.amd.com/zh-cn/partner/articles/ryzen-8000G-series-processors.html)
- **大型游戏或专业影像工作**先核对游戏或软件对 GPU、显存的要求。若已确定要配独显，可把 F 和非 F 版本的价格一起比较，同时考虑日后是否需要拔掉独显后仍能输出画面。
