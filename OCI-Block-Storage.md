# Block Storage Basic & Adanced

- [Block Storage Basic \& Adanced](#block-storage-basic--adanced)
  - [Overview](#overview)
    - [Local NVMe](#local-nvme)
    - [Block Volume](#block-volume)
  - [Volume Attachment Types](#volume-attachment-types)
  - [Volume Access Type](#volume-access-type)
  - [Boot Volume](#boot-volume)
    - [Boot Volume performance](#boot-volume-performance)
    - [Boot Volume Dynamic Performance Scalling](#boot-volume-dynamic-performance-scalling)
  - [Resize a Volume](#resize-a-volume)
  - [Skill Checks](#skill-checks)

## Overview 
<img src="./pictures/Block-storage-1.PNG" width="650" style="border-radius: 10px" />

### Local NVMe 
 
 - :black_large_square: Local NVMe SSD devices are available to some compute instance shapes (such as BM.DenselO2.42) include locally attached NVMe Devices
 - :black_large_square: it has extremely low latency (since it is attached to the motherboard)
 - :black_large_square: High performance
 - :black_large_square: idea for big data, OLTP
 - :black_large_square: It is up to customer to protect and manage the durability of data

### Block Volume

<img src="./pictures/Block-storage-2.PNG" width="650" style="border-radius: 10px" />


## Volume Attachment Types
When you attach a block volume to an instance, you have the following ways
>iSCSI

<img src="./pictures/Block-storage-3.PNG" width="400" style="border-radius: 10px" />

>Paravirtualized

<img src="./pictures/Block-storage-4.PNG" width="400" style="border-radius: 10px" />

<img src="./pictures/Block-storage-5.PNG" width="650" style="border-radius: 10px" />

## Volume Access Type

<img src="./pictures/Block-storage-6.PNG" width="650" style="border-radius: 10px" />

<img src="./pictures/Block-storage-7.PNG" width="650" style="border-radius: 10px" />

## Boot Volume
<img src="./pictures/Block-storage-8.PNG" width="650" style="border-radius: 10px" />

### Boot Volume performance 

<img src="./pictures/Block-storage-9.PNG" width="650" style="border-radius: 10px" />

--------------------------

> There are 4 performance levels
>
- [ ] Lower Costs - :warning: `Only available for block volumes, not for  BOOT volume`
- [x] Balanced - `Default`
- [ ] Higher Performance 
- [ ] Ultra High Performance :warning: `Only available for block volumes`

### Boot Volume Dynamic Performance Scalling

> there are 2 type of dynamic performance scalling with autotuning

- [x] Performance Based Autotuning `Use needs to define the default(min) and Max performance VPUs`
- [x] Detached  Volume Autotuning  :zzz: `Once volume detached, volume performance level is set to Lower Cost`

:sparkles: These two settings can be enabled at the same time. 



## Resize a Volume 
> :warning: One can `only increasing` a Volume Size, `NOT` decrease

> :star: One can choose `online  resizing ` or  `Offline Resizing`
> 

<img src="./pictures/Block-storage-10.PNG" width="650" style="border-radius: 10px" />






## Skill Checks

1. Which of the following is NOT a block volume performance level?

    :white_large_square: Higher Performance

   :white_check_mark: Optimized (*)

    :white_large_square: Lower Cost

    :white_large_square: Ultra High Performance

2. What happens when the detached volume autotuning feature is enabled and the volume is detached from the instance?
   
    :white_check_mark: The Block Volume service adjusts the performance level to Lower Cost. (*)

    :white_large_square: The Block Volume service adjusts the performance level to Ultra High Performance.

    :white_large_square: The Block Volume service adjusts the performance level to Higher Performance.

    :white_large_square: The Block Volume service adjusts the performance level to Balanced.

3. Which two are options for attachment type when you attach a block volume to a VM instance?

    :white_large_square: SMB

    :white_check_mark: iSCSI (*)

    :white_check_mark: Paravirtualized (*)

    :white_large_square: NFS    

4. You want to attach a block volume to a VM instance and one of your requirements is to get a better IOPS performance. Which volume attachment type would you use?
   
    :white_large_square: NFS

    :white_large_square: Paravirtualized

    :white_large_square: SMB

    :white_check_mark: iSCSI (*)    

5. Which three of the following are options for access type when you attach a block volume to an instance?

    :white_large_square: Read/Execute

    :white_check_mark: Read-only-Shareable (*)

    :white_check_mark: Read/Write-Shareable (*)

    :white_check_mark: Read/Write (*)

    :white_large_square: Write/Execute    