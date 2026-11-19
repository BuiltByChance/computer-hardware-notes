# P17 · 16.GTX和RTX区别，以及光线追踪的用途｜辨认光追效果，读懂显存规格

## 开关光追，画面会变在哪里？

光线追踪通过计算光线与场景中物体的交点来模拟反射、间接照明等效果。GeForce RTX 从 20 系列起有专用 RT 核心加速这类计算。部分 GTX 能用着色器运行基础 DirectX 光线追踪（DXR），例如 GTX 1060 **6 GB**。能否启用还要查游戏、驱动和具体 GPU。开启后的帧率取决于场景、画质和分辨率。[NVIDIA 对 GTX 与 RTX 的 DXR 支持说明](https://www.nvidia.com/en-us/geforce/news/geforce-gtx-dxr-ray-tracing-available-now/)

| 课程对照图 | 固定位置观察 |
|---|---|
| 《战地 V》街边起火 | 关光追时车身已有环境倒影。开光追后，同一扇车门和引擎盖映出街边橙色火光，这一项是**反射**。[NVIDIA 白皮书图 51](https://images.nvidia.com/aem-dam/en-zz/Solutions/design-visualization/technologies/turing-architecture/NVIDIA-Turing-Architecture-Whitepaper.pdf) |
| 《地铁：离去》室内进光 | 比较门口附近的人物腿部和周围暗处，观察光线经其他表面反弹后怎样照亮物体，这一项是**间接照明**。有的区域开启光追后更暗。[NVIDIA 对全局光照的说明](https://www.nvidia.cn/geforce/news/geforce-gtx-ray-tracing-coming-soon/) |

要在《战地 V》中比较两种效果，在图形设置开启 DirectX 12，按提示重启游戏。进入高级设置开启 DXR，选择 **DXR Reflections Quality**。用同一机位、分辨率和画质比较车身倒影，同时记录帧率。若帧率降得过多，降低反射质量再看差别。课上的图片只展示视觉效果。[NVIDIA 游戏设置说明](https://www.nvidia.com/en-us/geforce/news/battlefield-v-rtx-ray-tracing-out-now/)

## 读显存时，把容量、类型和位宽分开

商品页选定板卡后，在规格中找以下三项。以七彩虹 **RTX 3090 Ti Vulcan OC 24G** 为例，**24 GB** 是 GPU 可存放纹理、几何数据和渲染缓冲区的容量。**GDDR6X** 是显存类型。**384 bit** 是 GPU 与显存之间的数据总线宽度。高分辨率纹理会增加显存需求，判断帧率还要看 GPU 本身。[NVIDIA 30 系列规格](https://www.nvidia.cn/geforce/graphics-cards/30-series/)

同叫“火神”的 RTX 3080 Ti 与 RTX 3090 Ti 分别是 **12 GB 和 24 GB**。课上选中的普通 RTX 3060 有 **12 GB**，RTX 3060 Ti 却是 **8 GB**。同一 GPU 名称也可能有不同容量，桌面 RTX 3060 另有 8 GB 款，GTX 1060 商品页同时列 3 GB 和 6 GB。查游戏需求时要带上显存版本。[NVIDIA RTX 3060 系列对照](https://www.nvidia.cn/geforce/graphics-cards/30-series/rtx-3060-3060ti/)
