# P18 · 17.AMD显卡的实战分析｜区分 Radeon RX 与 PRO，比较 RX 6600 和 6600 XT

## 分清游戏卡与工作站卡

**Radeon RX** 是 AMD 面向游戏的产品线。**Radeon PRO** 面向专业工作站，型号如 WX 2100、WX 3200、W5500。选设计或建模工作站时，先在应用认证表查所用软件版本、显卡和驱动组合。选游戏卡则查目标游戏在相同分辨率、画质下的帧率。[AMD 专业显卡规格](https://www.amd.com/en/products/specifications/professional-graphics.html) · [AMD 应用与驱动认证查询](https://www.amd.com/en/search/certified-drivers.html)

## 用 RX 6600 和 6600 XT 读懂后缀

从 6700 XT 切到 6600 XT，若商品页仍显示 12 GB，重新核对所选板卡的完整型号。两种 GPU 即使共用一个商品页面，显存和计算单元也可能不同。

| 完整板卡示例 | 显存 | 计算单元 |
|---|---|---:|
| 技嘉 RX 6600 EAGLE 8G（猎鹰） | 8 GB GDDR6 | [28](https://www.amd.com/zh-cn/products/graphics/desktops/radeon/6000-series/amd-radeon-rx-6600.html) |
| 技嘉 RX 6600 XT GAMING OC 8G（魔鹰） | 8 GB GDDR6 | [32](https://www.amd.com/zh-cn/products/graphics/desktops/radeon/6000-series/amd-radeon-rx-6600-xt.html) |
| 技嘉 RX 6700 XT GAMING OC 12G | 12 GB GDDR6 | [40](https://www.amd.com/zh-cn/products/graphics/desktops/radeon/6000-series/amd-radeon-rx-6700-xt.html) |

**XT 属于 GPU 型号**，EAGLE 和 GAMING OC 是技嘉的板卡版本。6600 与 6600 XT 容量相同，XT 版有更多计算单元。计算单元增加的比例不能直接当作游戏帧率提升的比例。“旗舰”还取决于当时有哪些产品。同为 16 GB 的 RX 6800 XT、6900 XT 分别有 72、80 个计算单元，录课后 AMD 又推出了 6950 XT。[RX 6000 首发型号](https://ir.amd.com/news-events/press-releases/detail/978/amd-unveils-next-generation-pc-gaming-with-amd-radeon-rx-6000-series-bringing-leadership-4k-resolution-performance-to-aaa-gaming) · [RX 6950 XT 发布资料](https://ir.amd.com/news-events/press-releases/detail/1064/amd-announces-three-new-radeon-rx-6000-series-graphics-cards-and-first-games-adding-support-for-amd-fidelityfx-super-resolution-2-0)

**TITAN 属于 NVIDIA**，初代 GeForce GTX TITAN 面向高端游戏电脑，后来的 TITAN RTX 也用于 AI、数据科学和内容创作。[初代 GTX TITAN](https://nvidianews.nvidia.com/news/nvidia-introduces-geforce-gtx-titan-dna-of-the-world-s-fastest-supercomputer-powered-by-world-s-fastest-gpu) · [TITAN RTX](https://nvidianews.nvidia.com/news/nvidia-reveals-the-titan-of-turing-titan-rtx-6747548)
