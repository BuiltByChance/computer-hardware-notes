# P20 · 19.查看显卡信息以及天梯图的介绍｜用 GPU-Z 查显卡，按平台读天梯图

## 用 GPU-Z 确认显卡和显存

1. 打开 TechPowerUp 下载页，选 **Standard Version → Download**，选择镜像并运行下载的程序。标准版供个人与商业用户免费使用。[GPU-Z 官方下载](https://www.techpowerup.com/download/techpowerup-gpu-z/) · [功能与授权](https://www.techpowerup.com/gpuz/)
2. 如出现 **Install GPU-Z?**，选 **No** 可直接运行，以后也不再询问。**Yes** 执行安装，**Not now** 这次跳过、下次再问。有核显和独显时，先用窗口底部的下拉框选要查的 GPU。
3. 在 **Graphics Card** 核对硬件规格，到 **Sensors** 观察当前负载。先看列名再读数字，尤其要分清显存的总容量和已用量。

| 要核对的项目 | 字段 | 示例机器读数 |
|---|---|---|
| GPU 和板卡厂商 | Graphics Card → Name、Subvendor | NVIDIA GeForce RTX 2070 SUPER，Gigabyte（技嘉） |
| 显存容量、类型、位宽 | Memory Size、Memory Type、Bus Width | 8192 MB（8 GB）、GDDR6、256 bit |
| 核心、显存、加速频率 | GPU Clock、Memory、Boost | 1605、1750、1785 MHz |
| 当前已用显存、温度、负载 | Sensors → Memory Used、GPU Temperature、GPU Load | 一帧读到 1533 MB、56.1 °C、16%。这些值随运行的程序变化。 |

## 用天梯图粗略比较型号

1. 在快科技天梯榜先选 **CPU 或显卡**，再选 **桌面或笔记本**。打开的是带分数的排行榜时，可用侧栏的「天梯图」查看相对档次。[快科技天梯榜](https://rank.kkj.cn/)
2. 检查图的更新日期和收录范围。录屏中的笔记本显卡图停在 **2016 年 4 月**，无法用它判断后来的 RTX 30 系列。用浏览器 **Ctrl+F** 搜完整型号。若图是图片，可沿图中的厂商、系列分栏查找。
3. 在同一张图内，顺箭头向上是发布者排得更高的型号，横向同一高度可粗略比较不同厂商或世代。笔记本 CPU 图还分标准电压和低电压。要估算某款游戏的帧率或项目的渲染时间，查相应负载的实测。

| 设备 | 桌面 | 笔记本 |
|---|---|---|
| CPU | [桌面 CPU 天梯图](https://www.mydrivers.com/zhuanti/tianti/cpu/index.html) | [笔记本 CPU 天梯图](https://www.mydrivers.com/zhuanti/tianti/cpum/index.html) |
| GPU | [桌面显卡天梯图](https://www.mydrivers.com/zhuanti/tianti/gpu/index.html) | [笔记本显卡天梯图](https://www.mydrivers.com/zhuanti/tianti/gpum/index.html) |

**笔记本型号保留平台和后缀。** 早期 **GTX 960M** 的 M 表示移动版。RTX 30 系列用 **Laptop GPU** 标明平台，3050 与 3050 **Ti** 都有笔记本版。同名 GPU 的供电设置也可能不同，例如 NVIDIA 为 RTX 3060 Laptop GPU 列出的 GPU 子系统功耗为 **60–115 W**。比较整机要核对厂商标出的功耗及其口径，再找对应机型的实测。[NVIDIA 笔记本 GPU 规格对照](https://www.nvidia.cn/geforce/laptops/compare/30-series/)
