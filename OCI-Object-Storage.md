# :cloud: Object Storage Basics & Advanced

- [:cloud: Object Storage Basics \& Advanced](#cloud-object-storage-basics--advanced)
  - [Overview](#overview)
  - [Object Storage Resources](#object-storage-resources)
  - [Object Storage Tiers](#object-storage-tiers)
    - [Difference Between these 3 tiers](#difference-between-these-3-tiers)
    - [Auto Tiering](#auto-tiering)
  - [Object Lifecycle Management](#object-lifecycle-management)
  - [:blossom: Object Storage Replication](#blossom-object-storage-replication)
  - [:page\_with\_curl: Object Versioning](#page_with_curl-object-versioning)
    - [Object Versioning Status](#object-versioning-status)
  - [Retention Rules](#retention-rules)
    - [To understand time-bound retention rules, examples](#to-understand-time-bound-retention-rules-examples)
  - [:train: Object Copy](#train-object-copy)
  - [:star: Loggings](#star-loggings)
  - [Pre-Authenticated Requests](#pre-authenticated-requests)
  - [Customer Managed Key](#customer-managed-key)
    - [Vault](#vault)
    - [Key](#key)
  - [Emit Object Events](#emit-object-events)
  - [Skill Checks](#skill-checks)


## Overview
> Overview of Object Storage
> 
<img src="./pictures/object-storage-1.png" width="650" style="border-radius: 10px" />

> Object Storage Use Cases
>
<img src="./pictures/object-storage-2.PNG" width="650" style="border-radius: 10px" />

## Object Storage Resources
<img src="./pictures/object-storage-3.PNG" width="650" style="border-radius: 10px" />

> Endpoint Example 
>
<img src="./pictures/object-storage-4.PNG" width="650" style="border-radius: 10px" />



## Object Storage Tiers

Storage Tiers can help with 
- maximize access performance
- Minimize storage costs

During Creation of a Bucket, you can chose 
- [x] Standard Storage Tier Bucket 
- [x] Archive Stroage Tier Bucket

`Within standard tier bucket`, you can explicitly assign storage tier to an object, the options are 
- [ ] Standard
- [ ] Infrequent Access
- [ ] Archive

### Difference Between these 3 tiers

<img src="./pictures/object-storage-5.PNG" width="650" style="border-radius: 10px" />

### Auto Tiering
> :sunny: Only between Standard tier and Infrequent Access Tier
>

<img src="./pictures/object-storage-6.PNG" width="650" style="border-radius: 10px" />

## Object Lifecycle Management

Object lifecycle management lets you manage the `lifecycle of your object storage data` through `automated archiving` and `deletion`, reducing storage costs and saving time. Object lifecycle management works by taking automated action based on the `rules` you define. 
The supported lifecycle action includes 
- [ ] :cloud: moving to infrequent access, 
- [ ] :cloud: moving to archive, 
- [ ] :fire: and delete.

> Thing to watchout
>
<img src="./pictures/object-storage-7.PNG" width="650" style="border-radius: 10px" />

> Example of a typical Object Lifecycle Management Rules
>
<img src="./pictures/object-storage-8.PNG" width="650" style="border-radius: 10px" />

`we can move standard tier objects to the archive tier 30 days after creation or last update. And then after 180 days, we can automatically delete those archived objects. And just to add, you can create another lifecycle policy rule that deletes uncommitted or failed multi-part upload after five days`

<img src="./pictures/object-storage-9.PNG" width="650" style="border-radius: 10px" />

_______________

## :blossom: Object Storage Replication 
> Replicates objects from one bucket to another in the same or different Region
> , 
>- :warning: Once a bucket becomes destination bucket, it can only be updated via the source bucket.
>- :warning: objects uploaded before replication policy  are ignored, thus not replicated 


## :page_with_curl: Object Versioning

Versioning directs object storage to automatically create an object version, each time a new object is uploaded, an existing object is overwritten, or when an object is deleted. It is enabled at the bucket level. You can enable object versioning at bucket creation time or later. You cannot disable object versioning. You can, however, suspend versioning.

It provides data protection against accidental or malicious object update, overwrite, or deletion. There is always one latest version of the object and zero or more previous versions. And you are going to be charged for all the latest object versions and previous object version. The previous object versions are retained until you explicitly delete them.

### Object Versioning Status
- Disabled
- Enabled
- Suspended
  
<img src="./pictures/object-storage-10.PNG" width="650" style="border-radius: 10px" />

<img src="./pictures/object-storage-11.PNG" width="650" style="border-radius: 10px" />


## Retention Rules

:warning: `You cannot add retention rules to versioning enabled buckets. It only works with disabled/suspended versioning status.`

Retention rules protect your data from accidental or malicious update, overwrite, or deletion. It also provides immutable WORM-compliant storage options for data return to objects storage and archive storage, and the retention rules can be locked to prevent rule modification and data deletion or modification, even by administrators. Please, note that the retention rules are configured at the bucket level.

There are two types of retention rules.

- time-bound :watch:
  - The first is time-bound, where you specify a duration during the creation of a retention rule. Object modification and deletion are prevented for the duration that you specify. 
- indefinite  :imp:
  - The second retention rule type is indefinite, where object modification and deletion are prevented, until you delete the rule.

<img src="./pictures/object-storage-12.PNG" width="650" style="border-radius: 10px" />

### To understand time-bound retention rules, examples
<img src="./pictures/object-storage-13.PNG" width="650" style="border-radius: 10px" />

`we have a time-bound retention rule of the duration of 1 year, we have two objects here 1 which was last modified 14 months ago and another 3 month ago. The retention rule will allow update/delete on Ocitest oject since the last update was 14 months ago (> 12 months) , and prevent ocidemo from updating/deletion (< 12 months)`


## :train: Object Copy 
> Almost useless if you copy with UI, it only allows single file copying....
> 
<img src="./pictures/object-storage-14.PNG" width="650" style="border-radius: 10px" />


## :star: Loggings
<img src="./pictures/object-storage-15.PNG" width="650" style="border-radius: 10px" />
<img src="./pictures/object-storage-16.PNG" width="650" style="border-radius: 10px" />

> There are two ways to create logs for Object Storage Read & Write
> - First way, via Log option in the bucket as showing above
> - The second way, is via Observability & Management >> Logggin >> Enable Servie Log
<img src="./pictures/object-storage-17.PNG" width="650" style="border-radius: 10px" />



## Pre-Authenticated Requests
> is the way to allow access to users on a private bucket
> - [ ] on Bucket level 
> - [ ] on single Oject 
> - [ ] on Prefix level
>
> The rights are `Read`,`write` and `Read & Write`
> You always need to provide an expiration time
>
> Once a pre-authenitcation link are created, the link will only show once..
<img src="./pictures/object-storage-18.PNG" width="650" style="border-radius: 10px" />


## Customer Managed Key

### Vault
Create a new Vault
### Key
create customer managed keys
THere are two types of keys , HSM(hardware) and software keys. 
<img src="./pictures/object-storage-19.PNG" width="650" style="border-radius: 10px" />
<img src="./pictures/object-storage-20.PNG" width="650" style="border-radius: 10px" />

> :warning: To use Customers Managed keys, you need to create following policy. It can be a dedicated policy which is not assigned to a group

<img src="./pictures/object-storage-21.PNG" width="650" style="border-radius: 10px" />

`After you have create your own key and assigned to a bucket, you can choose to re-rencrypt the bucket or re-encrypt a object with the new assigned key`
## Emit Object Events
 With Emit Object Events option abled, you can then go and create automation based on the state changes to objects. Along side this option, you need 2 addtional services to get it working. 
 - The first one is *Event Service*. And  (to create Rules)
 - the second one is *Notification Service*.(to create subscriptions)
here is an example of having  emit + event service + notification service to work together. What it does is that once a new oject is uploaded to bucket, event rules are triggerred and using notification service to send out emails. 

> Create Topics
> 
<img src="./pictures/object-storage-22.PNG" width="650" style="border-radius: 10px" />

> Create Subscriptiopns within topic
> 
<img src="./pictures/object-storage-23.PNG" width="650" style="border-radius: 10px" />

> Go to Observability&Management > Event Service > Rules to create a new rule
> 
<img src="./pictures/object-storage-24.PNG" width="650" style="border-radius: 10px" />

## Skill Checks

1. Which two types of object name filters are supported while configuring a lifecycle policy rule in Object Storage service?
- [x] Prefix matching
- [ ] Regex matching
- [x] Pattern matching
- [ ] Filter matching

2. You would like to store some data that is *_seldom accessed_* but requires long retention periods. Which storage tier should you use to make the solution more cost effective?
- [X] Archive
- [ ] Standard
- [ ] Reduced Redundancy
- [ ] Infrequent Access

3. You would like Object Storage service to monitor the data access pattern and help you reduce costs by automatically moving objects larger than 1 MiB out of the Standard tier into the more cost-effective Infrequent Access tier. Which feature should you enable?
- [ ] Auto-Transition
- [ ] Auto-Move
- [ ] Auto-Change
- [x] Auto-Tiering

4. Which of the following is not a valid storage tier in Object Storage service?
- [ ] Standard
- [ ] Archive
- [ ] Infrequent Access
- [x] Glacier

5. You want to upload a 2 TiB object to Object Storage. You would like to have the flexibility of pausing between the uploads of individual parts and resuming the upload when your schedule allows. Which feature should you use?
- [ ] Splitpart uploads
- [x] Multipart uploads
- [ ] Split upload
- [ ] Simultaneous upload

6. Which mechanism provides a way to let users access a bucket or an object without having their own credentials?
- [ ] Multipart Uploads
- [ ] API Keys
- [ ] Auth Tokens
- [x] Pre-Authenticated Requests

7. You have an object in a bucket. The object was last modified 4 months ago. You create a retention rule and specify a duration of 1 year. Which of these statements is correct?
- [ ] You will not be able to modify or delete the object for the next 12 months.
- [x] You will not be able to modify or delete the object for the next 8 months. (*)
- [ ] You will be able to modify or delete the object for the next 12 months.
- [ ] You will be able to modify or delete the object for the next 4 months.
  
  :star2: `It's important to understand retention duration for time-bound rules. Even though you are creating retention rules for a bucket, the duration of a rule is applied to each object in the bucket individually, and is based on the object's Last Modified timestamp.`

8. Which two of the following are valid retention rule types in Oracle Cloud Infrastructure (OCI) Object Storage?
- [ ] Duration-bound
- [ ] Unlimited
- [x] Time-bound
- [x] Indefinite

9. You would like to enable Object Storage replication. Which two statements about a replication policy are correct?
- [x] A destination bucket cannot also be a replication source.
- [ ] After the replication policy is created, the destination bucket remains in a writable state and you can upload objects directly to it.
- [ ] Replication policy creation automatically creates a destination bucket.
- [x] There can be a maximum of one replication policy per source bucket.

10. Which two of these statements about object versioning are correct?
- [ ] Object versioning does not increase your storage costs. :warning: It does increase
- [x] Object versioning is enabled at the bucket level. (*)
- [x] You cannot enable versioning on a bucket with active retention rules. :warning: 
- [ ] A bucket that is versioning-enabled can have only two versions of an object.
  
  :star:` Object versioning is enabled at the bucket level. You cannot enable versioning on a bucket with active retention rules. A bucket that is versioning-enabled can have many versions of an object. Standard Oracle Cloud Infrastructure pricing applies to each bucket that is enabled for versioning. You are charged for all latest object versions and previous object versions.`