# P23 · 22-1.CPU搭配主板｜从 CPU 插槽查到主板支持列表与 BIOS 版本

台式机选板时，先用 CPU 的插槽和芯片组缩小范围，再用主板厂商的 CPU 支持列表确认具体搭配。查表时保留完整型号和后缀，例如 i9-14900K、i9-14900KF 在表里各占一行。

## 从 CPU 查插槽和芯片组

| CPU | 到哪里查 | 查到的结果 |
| --- | --- | --- |
| Core i9-14900K（01:45–08:52） | Intel 产品页 →「规格 → 封装规格 → 支持的插槽」，再点「兼容的产品」 | **FCLGA1700**，商品页通常写 **LGA1700**。700 系列列出 **B760、H770、Z790**，下方还有兼容的 600 系列。点芯片组名称，再进「兼容的产品」，可以反向核对 CPU。[Intel 插槽规格](https://www.intel.cn/content/www/cn/zh/products/sku/236773/intel-core-i9-processor-14900k-36m-cache-up-to-6-00-ghz/specifications.html) · [兼容芯片组](https://www.intel.cn/content/www/cn/zh/products/sku/236773/intel-core-i9-processor-14900k-36m-cache-up-to-6-00-ghz/compatible.html) |
| Ryzen 9 7950X3D（08:52–15:25） | AMD 产品页 →「规格」，看「CPU 平台」「支持芯片组」 | **AM5**，课堂商品标题也写作 **AM5（LGA1718）**。2024 年录屏列出 **A620、X670E、X670、B650E、B650**。当前官网还列出 **X870E、X870、B840、B850**。[AMD 7950X3D 规格](https://www.amd.com/zh-cn/products/processors/desktops/ryzen/7000-series/amd-ryzen-9-7950x3d.html) |
| Ryzen Threadripper 7980X（16:55–18:57） | 查 **7980X** 这一具体型号的 AMD 规格 | 插槽为 **sTR5**，支持的芯片组为 **TRX50**。同为 AMD 处理器，7950X3D 的 AM5 主板不能与它互换。[AMD 7980X 规格](https://www.amd.com/zh-cn/support/downloads/drivers.html/processors/ryzen-threadripper/ryzen-threadripper-7000-series/amd-ryzen-threadripper-7980x.html) |
| Core i5-12400（18:57–20:58） | 在 Intel 的「兼容的产品」中展开 600 系列 | 同为 **FCLGA1700**，**B660、Z690** 都是候选，700 系列也有兼容型号。反查时用 **Ctrl+F** 输入完整的 `i5-12400`，再看整行后缀。课堂输入 `125` 命中的是旁边的 i5-12500T。[Intel i5-12400 兼容芯片组](https://www.intel.cn/content/www/cn/zh/products/sku/134586/intel-core-i512400-processor-18m-cache-up-to-4-40-ghz/compatible.html) |

## 从芯片组查到手里这块板

1. 用芯片组名称搜索候选主板。记下品牌、完整板名和硬件修订号（如 rev. 1.0）。商品标题可以帮你找到型号，电商的「经常一起购买」也可能搭的是另一颗 CPU。
2. 在**该型号、该修订版**的厂商支持页进入 **CPU Support / CPU 支持列表**。找到与目标 CPU 完全一致的一行，读取 **Since BIOS Version** 或 **Validated since BIOS**。这列给出厂商开始验证支持该 CPU 的 BIOS 版本。
3. 把支持表的起始版本与手里主板的 BIOS 版本对照。已有可启动的电脑可在 UEFI 设置中查看版本，购买旧库存时可向卖方确认版本。如果当前 BIOS 早于表中列出的版本，按这块板的官方说明核对更新方式。

以下是按课堂出现的板名补查的例子。讲师当场查到了插槽、芯片组和商品信息，未读到这些 BIOS 版本。

| 主板及硬件版本 | CPU 支持表中的型号 | 厂商标出的起始 BIOS |
| --- | --- | --- |
| 技嘉 Z790 AORUS ELITE AX **rev. 1.0**（录屏商品标题未标修订号） | Core i9-14900K、i9-14900KF | **F9**。[技嘉 CPU 支持表](https://www.aorus.com/tw/motherboards/Z790-AORUS-ELITE-AX-rev-10/support/cpu-support) |
| 华硕 ROG STRIX B650E-E GAMING WIFI | Ryzen 9 7950X3D | **1409**。课堂偏好 X670E，这块 B650E 主板也明确列出了 7950X3D。[华硕 CPU 支持表](https://rog.asus.com/motherboards/rog-strix/rog-strix-b650e-e-gaming-wifi-model/helpdesk_cpu/) |
| 技嘉 TRX50 AERO D **rev. 1.0** | Ryzen Threadripper 7980X、7970X | 两者均为 **F1**。课堂查的是 7980X，电商搭购区显示的是 7970X。[技嘉工作站主板 CPU 支持表](https://www.aorus.com/tw/motherboards/trx50-aero-d-rev-10/support/cpu-support) |

## 在几块兼容主板之间选择

把实际要接的设备列出来，再看具体主板有几个 M.2 插槽、支持哪代 PCIe、需要的 USB 速率和接口数量是否够用。课堂打开的 AMD 平台对照表列的是芯片组**最多支持**的数量，成品板实际引出了多少接口要查板厂规格。例如要继续用已有 DDR4 内存，即使 CPU 同时支持 DDR4 和 DDR5，也要选配有 DDR4 插槽的具体板型。[AMD AM5 芯片组对照](https://www.amd.com/zh-cn/products/processors/chipsets/am5.html) · [Intel 示例处理器的内存规格](https://www.intel.cn/content/www/cn/zh/products/sku/236773/intel-core-i9-processor-14900k-36m-cache-up-to-6-00-ghz/specifications.html)

还要核对机箱能否容纳主板。课上技嘉 **X670E AORUS PRO X** 的零售标题写着 EATX，但技嘉规格表的 **Form Factor** 一栏写的是 **ATX，30.5 × 24.4 cm**。用厂商给出的板型和尺寸对照机箱规格。[技嘉 X670E AORUS PRO X 规格](https://www.gigabyte.com/Motherboard/X670E-AORUS-PRO-X/sp?lan=en)
