# Data Migration

## Data Pipeline

## Database Migration Services

* A cloud service that makes it easy to migrate relational databases, data warehouses, NoSQL databases, and other types of data stores.
* If you want to migrate to a different database engine, you can use the AWS Schema Conversion Tool (AWS SCT) to translate your database schema to the new platform.
* Can be used for continuous replication (CDC)
* How to: 
    * Create a Replication Instance
        * Choose a EC2 instance from the dms instance class.
        * Allocate storage
        * Choose a VPC
        * Single or Multi-AZ if require a standby instance for HA.
    * Create source and destination Endpoints
        * Aurora, DynamoDB, SQL Server, S3, etc.
    * Create database migration Tasks.

### Performance Considerations
* Resource availability on the source.
* Available network throughput.
* Replication server capacity.
* Ability of detsination being able to process changes.
* Drop constraints and triggers befor migrating (standard practice).

## Storage Gateway

![Storage Gateway](https://d1.awsstatic.com/cloud-storage/product-page-diagram_AWS-Storage-Gateway_HIW%402x.6df96d96cdbaa61ed3ce935262431aabcfb9e52d.png)

### S3 File Gateway

![S3 File Gateway](https://docs.aws.amazon.com/filegateway/latest/files3/images/file-gateway-concepts-diagram.png)

* Network File System (NFS) and Server Message Block (SMB) interface into S3.
* Software appliance, or gateway, is deployed into your on-premises environment as a VM running on VMware ESXi, Microsoft Hyper-V, or Linux Kernel-based Virtual Machine (KVM) hypervisor.
* Low-latency access to data through transparent local caching.

### FSx File Gateway

* Windows File Server interface into Amazon FSx.

### Tape Gateway

![Tape Gateway](https://d1.awsstatic.com/cloud-storage/tape-gateway-diagram.4b6ca2b4e3f97d4df7988544400ae91424503248.png)

* Tape Gateway enables you to replace using physical tapes on premises with virtual tapes in AWS without changing existing backup workflows.
* Caches virtual tapes on premises for low-latency data access. * Compresses data and transitions virtual tapes between Amazon S3 and Amazon S3 Glacier, or Amazon S3 Glacier Deep Archive, to minimize storage costs.
* Tape gateway is deployed into your on-premises environment as a VM running on VMware ESXi, KVM, or Microsoft Hyper-V hypervisor.

### Volume Gateway

![Volume Gateway](https://d1.awsstatic.com/cloud-storage/volume-gateway-diagram.eedd58ab3fb8a5dcae088622b5c1595dac21a04b.png)

* Internet Small Computer System Interface (iSCSI) interface into S3.
* The volume gateway is deployed into your on-premises environment as a VM running on VMware ESXi, Linux KVM, or Microsoft Hyper-V hypervisor.
* Volume configurations:
    * Cached volumes
        * Data stored in S3, with frequently accessed data subsets cached locally. 
        * Substantial cost savings on primary storage.
        * Minimize the need to scale your storage on-premises. * Low-latency access to your frequently accessed data.
    * Stored volumes
        * Stores all your data locally, and asynchronously backs up point-in-time snapshots of this data to Amazon S3.

## AWS Snow
* Can be used for data transport and for running AWS compute locally.

### AWS Snowcone
* Small portable device.
* 8TB storage.
* Use cases:
    * Execute compute at edge.
    * Offline data transfer.
    * Online data transfer with AWS DataSync.

### AWS Snowball




