Linux下 新增硬盘 && 挂载分区
=================

### 所用到的命令

- ##### `mount DEVICE-BOOT` 挂载一个磁盘[文件系统 | file system]
e.g. `mount /dev/sdb1`

- ##### `umount DEVICE-BOOT` [扩展] 取消挂载一个磁盘[文件系统 | file system]
e.g. `umount /dev/sdb1`

- ##### `df -h`
    在 `man` 中， 此命令的`NAME`为 **`df - report file system disk space usage`**

        df -h // 使用此命令可以查看到已可用的文件系统使用情况 (已分区, 已格式化)

- ##### `fdisk`    manipulate disk partition table
        fdisk -l // 查看所有的磁盘分区表
        fdisk -m // 列出所有命令项
        fdisk -n // 更新一个硬盘的分区表

- ##### `mkfs` 格式化磁盘
`mkfs.ext4 /dev/sdb` or `mkfs -t ext4 /dev/sdb`

### 名词解释

##### 挂载分区
之前一直对挂载分区的概念有着模糊不清的认识， 以为只要是使一个磁盘能够作为文件夹正常操作就为挂载。
其实不然， 挂载是将一个磁盘系统挂载到某个目录|`POINT`下，使其可以被访问到即为挂载，不涉及其他的操作。


### 文件及文件夹
`IDE` 设备以`hd`命名
`SATA` 设备以`sd`命名

- `/dev`:  设备驱动
- `/dev/sdL`:  `L` letter 字母为硬盘设备号
- `/dev/sdLN`: `N` number 数字为硬盘下划分的磁盘驱动号
- `/etc/fstab`:
    `Ubuntu Server`下对此文件的解释： `static file system information.`
    静态文件系统信息。 挂载的位置 文件系统类型
    开机会自动挂载