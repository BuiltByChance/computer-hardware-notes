# P13 · 12.硬盘的用途｜区分磁盘空间与运行内存，确认文件已复制

HDD 和 SSD 能在断电后保留已写入的文件。打开图片时，文件留在盘上，查看器把所需数据读入 RAM。关闭查看器会释放相应内存。尚未保存到磁盘的修改会随断电丢失。

## 在 Windows 分清三种用量

| 要查什么 | 操作 | 读数示例 |
| --- | --- | --- |
| 磁盘还装得下多少文件 | `Win + E` →「此电脑」→「设备和驱动器」 | C: 共 119 GB，**可用 76.3 GB**。虚拟机里的 D: 是 VMware Tools 虚拟光盘。要查盘符属于哪块物理磁盘，右键「开始」→「磁盘管理」看设备与卷的对应关系。[微软磁盘管理说明](https://support.microsoft.com/zh-cn/windows/experience/storage-filemanagement/disk-management-in-windows) |
| 文件夹占多少磁盘空间 | 右键文件夹 →「属性 → 常规」 | 示例目录「大小」69.8 MB 是文件内容总量，「占用空间」70.6 MB 是文件系统分配量。 |
| 运行中的程序占多少 RAM | 任务管理器 →「性能 → 内存」看整机，「进程 → 内存」看各程序 | 示例虚拟机共 8 GB RAM，已用 3.9 GB，可用 4.1 GB。 |

## 复制后怎样检查

在资源管理器选中源文件，按 `Ctrl + C`，打开目标文件夹后按 `Ctrl + V`。等进度结束，在目标位置核对文件名和大小，再确认原件仍在源目录。课堂把桌面 PNG 复制到 `C:\`，点「继续」通过管理员权限提示后，根目录出现了 **11 KB** 的副本。练习时也可选自己有写入权限的文件夹。[微软文件资源管理器指南](https://support.microsoft.com/zh-cn/windows/experience/fileexplorer/file-explorer-in-windows)

看硬盘商品时同样要分清容量与缓存。希捷酷鱼 `ST4000DM004` 的 **4 TB** 是存储容量，**256 MB** 是硬盘缓存，**5400 RPM** 是盘片转速，**SATA** 是接口。[希捷酷鱼 3.5 英寸硬盘规格表](https://www.seagate.com/content/dam/seagate/zh_cn/content-fragments/products/datasheets/barracuda-3-5-hdd/barracuda-3-5-hdd-DS17-2-2603US-zh_CN.pdf)
