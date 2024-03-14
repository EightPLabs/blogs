# Amazon Elastic Block Store - Introduction


## Definition and purpose



* Elastic Block Store is an AWS service providing block-level storage volumes.
* These volumes serve as raw, unformatted block devices that can be attached to EC2 instances.
* Its volumes offer persistent storage that remains intact even if the associated EC2 instance is terminated.
* The main goal of Amazon EBS is to provide scalable and durable storage solutions for different workloads on AWS infrastructure.

    

### Role in AWS infrastructure



* Amazon EBS is crucial in the AWS infrastructure by providing reliable and flexible storage solutions for EC2 instances.
* It provides persistent block-level storage for EC2 instances.
* Data stored on EBS volumes remains even if the associated EC2 instance is terminated.
* EBS supports various use cases, including database storage, boot volumes, and temporary storage.


## Key Features of EBS

AWS EBS offers various features, and here are some of the important ones


### Block storage basics



* EBS offers block-level storage, allowing for precise data management at the block level.
* Users can create multiple volumes and attach them to EC2 instances as needed.
* Each volume acts as a physical hard drive and everything can be formatted and partitioned accordingly.
* EBS volumes have an independent lifecycle from attached EC2 instances and ensure durability.
* Block storage has high-performance storage which is perfect for a lot of different applications and workloads.


### Elasticity and scalability



* EBS volumes can be resized smoothly to meet changing storage needs.
* Storage capacity adjustments can be made flexibly without interrupting operations or affecting data availability.
* This scalability enables users to scale storage resources up or down based on workload demands.
* Users can increase volume size to meet growing data requirements or decrease it to optimize costs.
* Elasticity and scalability ensure that storage resources closely align with the evolving needs of applications and workloads.


## Understanding EBS Volume Types

Two main types of storage devices are Solid state drives and Hard disk drives. SDD uses flash memory for faster performance but comes at a higher cost. HDD offers larger capacities at a lower cost but with slower speeds due to spinning magnetic disks.


### Solid State Drives Subtypes:



* **General Purpose gp2:** Balances cost and performance. It is also applicable to workloads such as boot volumes, medium-sized databases, and sample virtual desktops.
* **Provisioned IOPS:** Designed for high-performance requirements allowing for customizable IOPS and throughput, ideal for demanding applications.


### Hard Disk Drives Subtypes:



* **Throughput Optimized (st1):** Prioritizes high throughput for large and sequential data access, suitable for frequently accessed storage needs.
* **Cold HDD** Cost-effective option for storage with less frequent access prioritizing throughput over IOPS.
* **Magnetic (standard)** Older-generation volumes offering lower performance that is suitable for infrequently accessed data at a lower cost


## Use Cases for Different Volume Types


### Matching workloads to volume types



* General Purpose suits various workloads such as boot volumes, medium-sized databases, and development environments.
* Provisioned IOPS Ideal for I/O-intensive workloads such as databases, ERP systems, and critical business applications that require consistent performance.
* Throughput Optimized is suitable for large and sequential workloads like data warehousing, log processing, and big data analytics.
* Cold HDD is best for infrequently accessed, large, and sequential data sets such as data archiving, backups, and log storage.
* Magnetic is a basic storage option for low-performance workloads like non-critical applications, testing, and development.


### Performance considerations



* **General Purpose** provides balanced performance for various workloads with periodic capabilities suitable for applications with moderate I/O requirements and varying workloads.
* **Provisioned IOPS** offers consistent and predictable performance with customizable IOPS which makes it best for sensible applications to delay and require high performance.
* **Throughput Optimized** is for high throughput and delivering reliable performance for data-intensive tasks like large-scale data processing, analytics, and batch processing.
* **Cold HDD** provides cost-effective storage for infrequently accessed data with predictable throughput making it suitable for scenarios where performance is less critical.
* **Magnetic** offers basic storage capabilities at a lower cost, making it suitable for non-critical workloads with low I/O requirements.


## Common Use Cases for EBS


### Database Storage



* Offers durable block-level storage which has consistent low-latency performance.
* compatible with MySQL, PostgreSQL, Oracle, or SQL Server databases.
* Offers durable block-level storage which has consistent low-latency performance.


### Boot Volumes



* Frequently used as boot volumes for Amazon EC2 instances.
* Contains the operating system and application files necessary to start the instance.
* Enables fast and reliable instance launches, with easy backup and restoration using snapshots.


### Temporary Storage



* Used for storing temporary data during application processing.
* Suitable for temporary files, caches, logs, or intermediate data generated by applications.
* Provides flexible and scalable storage options for temporary data needs.


## References

[https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AmazonEBS.html#ebs-features](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AmazonEBS.html#ebs-features)

[https://www.scaler.com/topics/aws/ebs-volume-types/](https://www.scaler.com/topics/aws/ebs-volume-types/)

[https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-creating-volume.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-creating-volume.html)

[https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volume-types.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volume-types.html)

[https://kloudle.com/academy/create-attach-and-detach-ebs-volumes/](https://kloudle.com/academy/create-attach-and-detach-ebs-volumes/)

[https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSSnapshots.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSSnapshots.html)
