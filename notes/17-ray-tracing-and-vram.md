# P17 · 16.GTX和RTX区别，以及光线追踪的用途｜辨认光追效果，读懂显存规格

## 在同一场景里辨认光追效果（00:00–04:42）

| 场景 | 比较 RTX OFF 和 RTX ON 时看哪里 |
|---|---|
| 《战地 V》街边起火 | 两张图里都有火，关闭光追时车身也有环境倒影。盯住同一扇车门和引擎盖，开启后能看到明显的橙色火光倒影。这组图展示的是**反射**。[NVIDIA 白皮书图 51](https://images.nvidia.com/aem-dam/en-zz/Solutions/design-visualization/technologies/turing-architecture/NVIDIA-Turing-Architecture-Whitepaper.pdf) |
| 《地铁：离去》室内进光 | 两张图里门口都有亮光。比较人物腿部和周围暗处怎样受光，可以看出光照到一处、再反弹到其他表面产生的**间接照明**。光追也会使原本过亮的区域变暗。[NVIDIA 关于《地铁：离去》全局光照的说明](https://www.nvidia.cn/geforce/news/geforce-gtx-ray-tracing-coming-soon/) |

GeForce RTX 从 20 系列起配有专用 **RT Core**，用于加速光线与场景的求交等计算。部分 GTX 也能通过驱动，用着色器运行基础的 DirectX 光线追踪（DXR）效果，例如 **GTX 1060 6 GB**。核对时要精确到显卡版本、游戏及其要求。分辨率、光追质量和游戏采用的效果都会影响帧率。[NVIDIA 对 GTX 与 RTX 支持范围及性能的说明](https://www.nvidia.com/en-us/geforce/news/geforce-gtx-dxr-ray-tracing-available-now/)

**自己复现《战地 V》的对照**。课堂展示的是网页截图。按官方设置方法，在游戏图形设置中启用 DirectX 12，按提示重启。在高级设置中开启 DXR，选择「DXR Reflections Quality」。复用同一机位，固定分辨率、其他画质和超分辨率设置，分别观察关闭和开启时车身或玻璃上的倒影，并记录帧率。若流畅度不足，先调低反射质量再比较。[NVIDIA《战地 V》DXR 设置说明](https://www.nvidia.com/en-us/geforce/news/battlefield-v-rtx-ray-tracing-out-now/)

## 从商品页核对显存（06:13–09:04）

显存供 GPU 存放渲染时要访问的数据，例如纹理、几何数据和渲染缓冲区。高分辨率纹理可能需要更多显存。判断游戏能否流畅运行，还要对照完整 GPU 型号、目标分辨率和画质下的实测帧率。

在商品页先选定具体版本，读标题里的**型号和容量**，再到「商品介绍」或厂商规格表找「显存容量」「显存类型」「显存位宽」。以七彩虹 **RTX 3090 Ti Vulcan OC 24G 火神**为例，**24 GB** 是容量，**GDDR6X** 是显存类型，**384 bit** 是 GPU 与显存之间的数据总线宽度。[NVIDIA 30 系列规格表](https://www.nvidia.cn/geforce/graphics-cards/30-series/)

| 课上打开的桌面显卡 | 页面显示的显存 | 复查时留意 |
|---|---:|---|
| 七彩虹 RTX 3080 Ti Vulcan OC 火神 / RTX 3090 Ti Vulcan OC 火神 | 12 GB / 24 GB | 两张卡都叫“火神”，先读全 3080 Ti 或 3090 Ti。 |
| 七彩虹 RTX 3060 Ti Vulcan OC / RTX 3060 Advanced OC、Ultra W OC | 8 GB / 12 GB | 这两款普通版 3060 的容量都大于示例 3060 Ti。容量排序无法代替性能比较。官方另列有 8 GB 的普通版 3060。[NVIDIA 3060 系列规格](https://www.nvidia.cn/geforce/graphics-cards/30-series/rtx-3060-3060ti/) |
| 微星 RTX 3050 GAMING X | 8 GB | 课上打开的是 8 GB 款。官方也列有 6 GB 桌面版，查“3050”时还要核对容量版本。[NVIDIA 30 系列规格表](https://www.nvidia.cn/geforce/graphics-cards/30-series/) |
| 磐镭 GTX 1060 | 3 GB | 商品页选中 3G，旁边另有 6G 选项。前文提到可运行基础 DXR 的 1060 特指 6 GB 款。 |
