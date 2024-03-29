# EBS

* High performance, low latency, per instance block storage.
* For data that must be quickly accessible and requires long-term persistence.
* Can only be attached to EC2 instances in the same AZ.
* To make avaialble in another AZ:
    * Take a snapshot, (copy to new region if required), and restore snapshot to a new volume.
* Volumes can be encypted volumes:
    * Data stored at rest on the volume, disk I/O, and snapshots created from the volume are all encrypted. 
* EBS Multi-Attach:
    * Enables you to attach a single Provisioned IOPS SSD (io1 or io2) volume to multiple instances that are in the same Availability Zone. 
* Recommended for:
    * data that must be quickly accessible and requires long-term persistence. 
    * particularly well-suited for use as the primary storage for file systems, databases, or for any applications that require fine granular updates and access to raw, unformatted, block-level storage. 


## EBS Volume Types

* General Purpose SSD (gp2 and gp3):
    * Balance price and performance.
    * Ideal for boot volumes, medium-size single instance databases, and development and test environments.
    * Max IOPs/volume = 16,000
* Provisioned IOPS SSD (io1 ans io2):
    * I/O-intensive workloads that are sensitive to storage performance and consistency.
    * Provide a consistent IOPS rate that you specify when you create the volume.
    * High volume durability.
    * Max IOPs/volume = 64,000
* Throughput Optimized HDD (st1):
    * Low-cost magnetic storage that defines performance in terms of throughput rather than IOPS. 
    * Ideal for large, sequential workloads such as Amazon EMR, ETL, data warehouses, and log processing. 
* Cold HDD volumes (sc1): 
    * Low-cost magnetic storage that defines performance in terms of throughput rather than IOPS. 
    * I deal for large, sequential, cold-data workloads. 
    * If you require infrequent access to your data and are looking to save costs, these volumes provides inexpensive block storage.  

## EBS Snapshots

* Snapshots are incremental backups to S3.
* Snapshot Encryption:
    * Snapshots taken from encrypted volumes are automatically encrypted.
    * Volumes created from an encrypted snapshot are also automatically encrypted.
    * When you copy a snapshot, you can encrypt the copy or you can specify a KMS key that is different than the original.
* Amazon Data Lifecycle Manager
    * Automate the creation, retention, and deletion of EBS snapshots and EBS-backed AMIs.

## RAID on EBS

* RAID is an OS concept. Create and attcah multiple EBS volumes, then configure RAID on the OS.
* RAID 0
    * Disk striping. Spit across disks.
    * Provide greater read and write performance.
* RAID 1
    * Mirroring
    * Offers redundancy and fault tolerance.
    * Offers slower write speeds but could offer the same read performance as RAID 0 if the RAID controller uses multiplexing to read data from disks. 

### Instance storage
* Temporary block-level storage.
* Physically attached to host computer.
* Data is lost when instance terminates, but preserved during a reboot.
* Instance store backed instances cannot be stopped or hibernated.
* 
