# Block Storage Basic & Adanced

- [Block Storage Basic \& Adanced](#block-storage-basic--adanced)
  - [Overview](#overview)
    - [Local NVMe](#local-nvme)
    - [Block Volume](#block-volume)
  - [Volume Attachment Types](#volume-attachment-types)
  - [Volume Access Type](#volume-access-type)
  - [Boot Volume](#boot-volume)

## Overview 
<img src="./pictures/Block-storage-1.png" width="650" style="border-radius: 10px" />

### Local NVMe 
 
 - :black_large_square: Local NVMe SSD devices are available to some compute instance shapes (such as BM.DenselO2.42) include locally attached NVMe Devices
 - :black_large_square: it has extremely low latency (since it is attached to the motherboard)
 - :black_large_square: High performance
 - :black_large_square: idea for big data, OLTP
 - :black_large_square: It is up to customer to protect and manage the durability of data

### Block Volume

<img src="./pictures/Block-storage-2.png" width="650" style="border-radius: 10px" />


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