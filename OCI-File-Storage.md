# File Storage

- [File Storage](#file-storage)
  - [Overview](#overview)
    - [File Storage Concepts](#file-storage-concepts)
      - [what is Mount Target](#what-is-mount-target)
      - [what is Export](#what-is-export)
      - [Infra Chart](#infra-chart)
  - [Steps to Mount  File System](#steps-to-mount--file-system)
    - [NFS Export Options](#nfs-export-options)
      - [Example](#example)
      - [:warning:](#warning)
      - [Access Control Settings](#access-control-settings)
      - [File System Path](#file-system-path)
        - [what is Export path](#what-is-export-path)
        - [What is Mount point path](#what-is-mount-point-path)
        - [What is File System path](#what-is-file-system-path)

## Overview 

<img src="./pictures/File-storage-1.PNG" width="650" style="border-radius: 10px" />

<img src="./pictures/File-storage-2.PNG" width="650" style="border-radius: 10px" />

### File Storage Concepts

<img src="./pictures/File-storage-3.PNG" width="650" style="border-radius: 10px" />

#### what is Mount Target
<img src="./pictures/File-storage-4.PNG" width="650" style="border-radius: 10px" />

#### what is Export
<img src="./pictures/File-storage-5.PNG" width="650" style="border-radius: 10px" />

#### Infra Chart
<img src="./pictures/File-storage-6.PNG" width="650" style="border-radius: 10px" />

## Steps to Mount  File System

> :one: Check Security List and Network Security Group for access rules

> :two: Launch OCI Instance

> :three: Install nfs-units or nfs-common

> :four: create a directory

> :five: check mount targets in the OCI console

> :six: copy the mount commands and run on the client

<img src="./pictures/File-storage-7.PNG" width="300" style="border-radius: 10px" />  



### NFS Export Options

NFS Export Options enable you to create more granular access control. You can specify access levels for IP addresses or CIDR blocks, connecting to the file system through exports in a mount target. And access can be restricted so that each client's file system is inaccessible and invisible to the other so you can control access to the file system. NFS Export Options are a set of parameters within the Export that specifies the level of access granted to NFS clients when they connect to a mount target.

<img src="./pictures/File-storage-8.PNG" width="650" style="border-radius: 10px" />  

#### Example
<img src="./pictures/File-storage-9.PNG" width="650" style="border-radius: 10px" />  

:a: 

<img src="./pictures/File-storage-9-a.PNG" width="300" style="border-radius: 10px" /> 

:b:

<img src="./pictures/File-storage-9-b.PNG" width="300" style="border-radius: 10px" /> 

#### :warning:
<img src="./pictures/File-storage-10.PNG" width="650" style="border-radius: 10px" />

#### Access Control Settings
<img src="./pictures/File-storage-11.PNG" width="650" style="border-radius: 10px" />

#### File System Path
<img src="./pictures/File-storage-12.PNG" width="650" style="border-radius: 10px" />

##### what is Export path
<img src="./pictures/File-storage-13.PNG" width="650" style="border-radius: 10px" />

##### What is Mount point path
<img src="./pictures/File-storage-14.PNG" width="650" style="border-radius: 10px" />


##### What is File System path
<img src="./pictures/File-storage-15.PNG" width="650" style="border-radius: 10px" />
