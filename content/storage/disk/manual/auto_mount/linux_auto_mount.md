---
title: "自动挂载 Linux 硬盘"
date: 2021-09-23T00:38:25+09:00
description: 本小节主要介绍Linux系统如何配置云硬盘的自动挂载。
draft: false
weight: 10
keyword: 云计算, 青云, QingCloud, 云硬盘, linux,自动挂载
---

## 初始化待挂载的硬盘

请参见[初始化硬盘](/storage/disk/quickstart/init/init_linux)。

## 使用磁盘UUID方式

1. 使用`blkid`命令获取磁盘的 uuid。

   ```
   # blkid /dev/sdb
   /dev/vdc: UUID="70fc59fe-d388-49ba-be56-b06cfbcc01ed" TYPE="ext4"
   ```
   > **说明：**    
   > /dev/sdb：磁盘盘符，需根据实际情况进行修改；

2. 使用以下命令，备份 fstab 配置文件。

   ```
   # cp /etc/fstab /etc/fstab.bak
   ```

3. 执行以下命令，将配置内容写入 fstab 文件。

   ```
   # echo "UUID=70fc59fe-d388-49ba-be56-b06cfbcc01ed /mnt ext4 defaults  0 0" >>/etc/fstab
   ```

   > **说明：**   
   > UUID：为步骤1查询出的磁盘uuid ，需根据实际情况进行修改；  
   > /mnt：为磁盘挂载的目录，需根据实际情况进行修改；  
   > ext4：为文件系统类型。  

   ![linux_auto_mount_1](/storage/disk/_images/linux_auto_mount_1.png)

4. 若磁盘已手动挂载，请用 `umount` 命令将挂载的磁盘卸载；再使用 mount -a 命令测试是否能自动挂载成功。

   ```
   # umount -v /dev/sdb
   # mount -a
   ```

5. 执行`df -h`命令，确认是否挂载成功。

   ```
    # df -h
   Filesystem      Size  Used Avail Use% Mounted on
   /dev/sda1        20G  859M   18G   5% /
   tmpfs           499M     0  499M   0% /dev/shm
   /dev/sdb        9.8G   23M  9.2G   1% /mnt
   ```

## 使用磁盘ID方式

1. 执行如下命令，获取磁盘设备 ID。

   ```
   # ls -l /dev/disk/by-id
   ```

   ![linux_auto_mount_2](/storage/disk/_images/linux_auto_mount_2.png)

2. 执行如下命令，备份 fstab 配置文件。

   ```
   # cp /etc/fstab /etc/fstab.bak
   ```

3. 执行以下命令，将配置内容写入 fstab 文件。

   ```
   # echo "/dev/disk/by-id/scsi-0QEMU_QEMU_HARDDISK_vol-186vl7uk  /mnt  xfs  defaults 0 0" >>/etc/fstab
   ```

   ![linux_auto_mount_3](/storage/disk/_images/linux_auto_mount_3.png)

4. 使用 `mount -a` 命令测试一下是否能自动挂载成功。

   ![linux_auto_mount_4](/storage/disk/_images/linux_auto_mount_4.png)
