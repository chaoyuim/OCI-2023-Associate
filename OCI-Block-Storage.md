# Block Storage Basic & Adanced

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

<img src="./pictures/Block-storage-3.png" width="400" style="border-radius: 10px" />

>Paravirtualized

<img src="./pictures/Block-storage-4.png" width="400" style="border-radius: 10px" />