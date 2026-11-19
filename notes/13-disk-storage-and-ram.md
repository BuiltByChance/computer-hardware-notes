# P13 · 12.硬盘的用途｜区分磁盘空间与运行内存，确认文件已复制

打开一张保存在硬盘上的图片时，图片文件留在磁盘，查看器会把显示它所需的数据读入 RAM。关闭查看器可以释放它占用的内存。再打开同一路径，仍能读到保存好的图片。机械硬盘（HDD）和固态硬盘（SSD）都能在断电后保留已写入的数据。只存在 RAM 中、尚未保存的修改会随断电丢失。

## 两种“还剩多少空间”，分别去哪看（04:26–05:56）

| 要回答的问题 | Windows 操作 | 讲师虚拟机里的读数 |
|---|---|---|
| 目标盘还能存多少文件？ | 按 `Win + E` 打开文件资源管理器，点左侧「此电脑」，在「设备和驱动器」下看目标盘的可用空间和总容量。 | 本地磁盘 C: **76.3 GB 可用，共 119 GB**。下载或复制文件到 C: 时看前一个数。 |
| 正在运行的程序用了多少内存？ | 右键「开始」→「任务管理器」→「性能」→「内存」。要看各个程序，再切到「进程」，查看「内存」列。 | RAM 共 **8.0 GB**，画面当时显示 **3.9 GB（49%）** 正在使用，可用 **4.1 GB**。读数会随应用的运行而变化。 |

盘符是 Windows 访问驱动器的入口。课堂画面里的 D: 标为「DVD 驱动器 (D:) VMware Tools」，对应虚拟光盘。同一块硬盘也可以分出多个带盘符的卷。想查 C:、D: 各在什么设备上，可右键「开始」→「磁盘管理」，对照下半窗格的设备和卷。[微软：查看可用磁盘空间](https://support.microsoft.com/zh-cn/windows/experience/storage-filemanagement/free-up-drive-space-in-windows) · [微软：磁盘管理](https://support.microsoft.com/zh-cn/windows/experience/storage-filemanagement/disk-management-in-windows)

## 查一个文件夹实际占多少磁盘空间（06:45–07:03）

在资源管理器中右键目标文件夹 →「属性」→「常规」。**大小**是其中各文件的内容大小之和，**占用空间**是文件系统实际为它们分配的磁盘空间，两项可能不同。

讲师查看 `C:\Program Files (x86)\Microsoft Visual Studio`，显示大小 **69.8 MB**、占用空间 **70.6 MB**，包含 476 个文件和 86 个文件夹。这个数只覆盖选中的目录。要看软件运行时占了多少 RAM，则去任务管理器找相应进程。

## 复制图片并确认结果（07:03–07:29）

1. 在资源管理器选一张已有的图片，按 `Ctrl + C`。打开目标文件夹，按 `Ctrl + V`。练习可选自己有写入权限的文件夹，例如「图片」里的子文件夹。[微软文件资源管理器指南](https://support.microsoft.com/zh-cn/windows/experience/fileexplorer/file-explorer-in-windows)
2. 讲师从桌面复制到 `C:\` 根目录。Windows 提示需要管理员权限，点击「继续」后出现复制进度。这个权限提示与所选目标目录有关。
3. **核对副本。** 到目标路径检查文件名、类型和大小，再回到源目录核对原件。视频中 C 盘根目录出现了 `Frank的店铺.png`，类型为 PNG，大小列显示 **11 KB**，桌面原件仍保留。画面验证到复制完成，课堂没有重启电脑。

## 从机械硬盘商品标题认出容量（07:36–08:18）

课堂展示的希捷酷鱼 `ST4000DM004` 标为 **4 TB、256 MB、5400 RPM、SATA**。这四项依次表示存储容量、硬盘缓存、盘片转速和接口。西部数据蓝盘 `WD10EZEX` 则是 **1 TB、64 MB、7200 RPM**。要判断能存多少文件，看容量。要知道眼前这块盘还剩多少空间，回到「此电脑」读可用值。[希捷酷鱼 3.5 英寸硬盘规格表](https://www.seagate.com/content/dam/seagate/zh_cn/content-fragments/products/datasheets/barracuda-3-5-hdd/barracuda-3-5-hdd-DS17-2-2603US-zh_CN.pdf) · [西部数据蓝盘规格表](https://documents.westerndigital.com/content/dam/doc-library/zh_cn/assets/public/western-digital/product/internal-drives/wd-blue-hdd/product-brief-western-digital-wd-blue-pc-hdd.pdf)
