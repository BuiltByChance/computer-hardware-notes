# P25 · 23.苹果电脑的用途与硬件的未来｜按用途选 Mac，读懂 M1 系列性能图和屏幕规格

## 先确认工作地点和必用软件

- **需要带走电脑**时，MacBook Air 和 MacBook Pro 都自带屏幕和电池。写文档、编译项目、处理照片、剪视频是不同的负载。比较机型时，找与常用软件和任务对应的数据。
- **固定工位**先看是否需要自带屏幕。iMac 把主机和显示屏装在一起。Mac mini、Mac Studio 要另接显示器，片中的 Mac Pro 是塔式主机。Studio Display 和 Pro Display XDR 都是显示器。
- **工作依赖 Windows 软件**时，先查软件、插件和外设驱动是否支持 macOS 或 Windows 11 Arm。微软列出了在 M1 系列 Mac 上通过 Parallels Desktop 虚拟运行 Windows 11 Arm 专业版或企业版的方案，运行 Windows 需要相应许可证。苹果的“启动转换助理”适用于受支持的 Intel Mac。[微软的 Windows 11 运行选项](https://support.microsoft.com/zh-cn/windows/experience/platform-variants/options-for-using-windows-11-with-mac-computers-with-apple-m1-m2-and-m3-chips) · [Apple 启动转换说明](https://support.apple.com/zh-cn/102622)

## 对着自己的任务读性能图

M1 系列把 CPU、GPU 等集成在系统级芯片（SoC）中，两者可使用同一池统一内存。查看配置时分别读 CPU 核数、GPU 核数和内存容量。例如，2021 款 14 英寸 MacBook Pro 的两款 M1 Pro 配置分别是 8 核 CPU／14 核 GPU 和 10 核 CPU／16 核 GPU。首代 Mac Studio 另有 M1 Ultra，以 UltraFusion 连接两枚 M1 Max 晶粒，具体任务能快多少仍要看测试。[14 英寸机型规格](https://support.apple.com/zh-cn/111902) · [M1 Ultra 架构](https://www.apple.com.cn/newsroom/2022/03/apple-unveils-m1-ultra-the-worlds-most-powerful-chip-for-a-personal-computer/)

读图时先看软件和具体操作，再看测试机和对照机。下表取自视频中的 Apple 厂商测试，比较的是 **2021 款 14 英寸**与旧款 **13 英寸四核 Core i7／Iris Plus**。两台测试配置的 CPU 都是 10 核，GPU 分别是 16 核和 32 核。[Apple 当年的测试说明](https://www.apple.com.cn/newsroom/2021/10/apple-unveils-game-changing-macbook-pro/)

| 测试任务 | M1 Pro 相对旧机的速度 | M1 Max 相对旧机的速度 |
| --- | ---: | ---: |
| Xcode 构建项目 | 3.7 倍 | 3.7 倍 |
| Photoshop 的 GPU 加速滤镜和功能 | 3.3 倍 | 3.5 倍 |
| Final Cut Pro 渲染 4K 项目 | 9.2 倍 | 13.4 倍 |

同一页右栏的 16 英寸机型测的是 **8K** 渲染，对照机搭载 Radeon Pro 5600M。左右两栏换了任务和对照机，把两个倍率直接相除，算不出两款新机之间的速度差。

讲师据此预测集成 GPU 将承担更多工作。早在 2011 年，AMD Fusion 已把 CPU 和图形单元放在同一枚晶粒上。判断集成 GPU 能否承担自己的工作，可以看同一软件、同一项目在目标机型上的完成时间，再比较耗电和噪声。[AMD Fusion 发布资料](https://ir.amd.com/news-events/press-releases/detail/168/amd-fusion-apu-era-begins)

## 复查 2021 款 MacBook Pro 的规格

视频中的产品介绍页已转到现售系列。复查这堂课时，用 Apple 支持页确认年份和尺寸，再查“显示屏”“电池和电源”“充电和扩展”。[14 英寸规格](https://support.apple.com/zh-cn/111902) · [16 英寸规格](https://support.apple.com/zh-cn/111901)

- **续航和存储**　按“影片播放／无线上网”两个测试分别读。14 英寸最长为 17／11 小时，16 英寸为 21／14 小时。剪辑、编译的用电情况另计。视频旧产品页的 SSD 标注为最高读取 7.4 GB/s，写入和实际拷贝需要看相应测试。
- **清晰度、亮度和刷新率**　以 14 英寸款为例，14.2 英寸屏幕为 3024 × 1964、254 ppi。读 Liquid 视网膜 XDR 的亮度要区分 SDR（500 尼特）和 HDR（全屏持续 1000 尼特，峰值 1600 尼特）。ProMotion 表示自适应刷新率，最高 120 Hz。要在实机确认，从苹果菜单进入“系统设置 → 显示器 → 刷新率”，查看是否选中 ProMotion。[Apple 刷新率设置说明](https://support.apple.com/zh-cn/102297)
- **外设接口**　这代机身有三个雷雳 4 端口，采用 USB-C 接头，支持 USB 4，标称最高 40 Gb/s。充电还可用 MagSafe 3。接投影仪、读相机卡、插有线耳机时，分别找 HDMI、SDXC 卡槽和 3.5 毫米耳机孔。
