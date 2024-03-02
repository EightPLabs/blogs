# Amazon Elastic Block Store

* Elastic Block Store is an AWS service providing block-level storage volumes.
* The main goal of Amazon EBS is to provide scalable and durable storage solutions for different workloads on AWS infrastructure.

    
![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-000.png?raw=true)



In this blog, let us understand EBS and also explore the AWS console for creating and managing EBS volumes and screenshots.


# EBS Volume



* Amazon Elastic Block Store (EBS) provides scalable block-level storage volumes that can be attached to Amazon EC2 instances. These volumes offer flexibility in terms of size, performance, and configuration options to meet the specific needs of applications.
* EBS volumes deliver consistent and low-latency performance, making them suitable for various workloads like transactional databases, high-performance computing, and I/O-intensive applications.
* These volumes serve as raw, unformatted block devices that can be attached to EC2 instances.
* They are replicated within their Availability Zone (AZ) to ensure data durability and availability. Additionally, snapshots can be created to back up EBS volumes that provide point-in-time recovery and disaster recovery capabilities.


## Prerequisites:

These are the prerequisites for creating EBS volume and snapshots in the AWS console



* Sign in to the AWS Console to access EC2 resources.
* Choose a region. For this tutorial, we are choosing the Mumbai region. 


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-001.png?raw=true)



## Creating EBS Volume Through AWS Console


### **Step 1: Navigate to EC2 Dashboard**

Go to the EC2 service dashboard, locate the **_Volumes_** option under the **_Elastic Block Store_** category in the navigation pane, and click on it.


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-002.png?raw=true)



### **Step 2: Create Volume**

Click on the **_Create Volume_** button to initiate the process of creating a new EBS volume.


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-003.png?raw=true)



### **Step 3: Select Volume Type** 

Choose the appropriate volume type based on your requirements, such as


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-004.png?raw=true)



##### **General Purpose SSD (gp3)**



* It offers balanced performance and cost-effectiveness with the ability to adjust IOPS and throughput independently, making it suitable for various workloads.


##### **General Purpose SSD (gp2)**



* It provides baseline performance with burst capabilities, ideal for general-purpose applications and boot volumes that require consistent performance at a lower cost.


##### **Provisioned IOPS SSD (io1)**



* It is designed for I/O-intensive applications demanding predictable performance, allowing users to specify desired IOPS and capacity levels.


##### **Provisioned IOPS SSD (io2)**



* It offers enhanced durability and consistent performance for critical production workloads, ensuring low-latency and high-throughput storage operations.


##### **Throughput Optimized HDD (st1)**



* Optimized for large, sequential I/O workloads at a low cost, making it suitable for data warehouses, log processing, and analytics.


##### **Cold HDD**



* Designed for infrequent access workloads with large datasets, providing cost-effective storage for scenarios like data archiving and backups.


##### **Magnetic**



* Legacy storage option with low-cost magnetic hard disk drives (HDDs), suitable for low-performance requirements and cost-sensitive applications.

For this tutorial, let us choose **_General purpose SSD (gp3)_**


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-005.png?raw=true)



### **Step 4: Specify Size**

Enter the desired size for the volume in gigabytes (GB). Ensure it meets the storage needs of your application. 

For this tutorial let's choose **_100GiB._**


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-006.png?raw=true)



### **Step 5:  Specify IOPS**

Specify the required number of IOPS to ensure predictable performance for I/O-intensive applications.

We can choose the default **_3000 IOPS_** for the tutorial.


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-007.png?raw=true)



### **Step 6:  Specify Throughput**

Define the desired throughput capacity to optimize data transfer rates and support sequential I/O operations efficiently.

We can define it as the default **_125 MiB/s_**. You can specify based on your requirements. 


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-008.png?raw=true)



### **Step 7:  Choose Availability Zone**


### Choose the Availability Zone from your region


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-009.png?raw=true)


We can choose **_ap-south-1a_** AZ.


### **Step 8: Snapshot ID**

Choose whether to create the volume from an existing snapshot. If not selected, a new volume will be created without using a snapshot as a source.


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-010.png?raw=true)


We will see more about EBS snapshots in upcoming sections.


### **Step 9: Configure Additional Settings**

Optionally configure additional settings such as encryption and tags.


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-011.png?raw=true)



### **Step 10: Review and Create**

Review the configuration details of the EBS volume to ensure accuracy. Click on the **_Create Volume_** button to finalize the creation process.


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-012.png?raw=true)



## Attaching, Detaching, and Deleting EBS Volume



* Attaching and detaching volumes in AWS is essential for managing storage resources efficiently. 
* This process involves associating volumes with EC2 instances to provide additional storage or detaching volumes for maintenance. 
* Efficient execution of these actions ensures smooth operation and optimal resource utilization within the AWS environment.
* When you no longer require your EBS volume delete the resources.


### Attaching the EBS Volume



* Locate the volume you want to attach and select it.
* Click on the **_Actions_** and choose **_Attach Volume_**.


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-013.png?raw=true)




* Select the EC2 instance to which you want to attach the volume.
* Specify the device name (e.g., /dev/sdf) for the attached volume.


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-014.png?raw=true)




* Confirm the attachment and the volume will be accessible from the specified EC2 instance.


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-015.png?raw=true)



### Detaching the EBS Volume



* Locate the volume you want to detach and select it.
* Click on the **_Actions_** on the menu and choose **_Detach Volume_**.
* Confirm the detachment and the volume will be disconnected from the EC2 instance.


### Deleting the EBS Volume



* Locate the volume you want to delete and select it.
* Click on the **_Actions_** and choose **_Delete Volume_**.


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-016.png?raw=true)




* Confirm the deletion and the volume will be permanently removed from your AWS account.


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-017.png?raw=true)



![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-018.png?raw=true)



# EBS Snapshots



* EBS snapshots are ideal for data recovery in Amazon EBS volumes.
* Point-in-time recovery allows restoration to specific points in case of data issues.
* Incremental backups record changes since the last snapshot, reducing backup time and storage costs.
* Through snapshot generation, you can provide business resilience and perform disaster recovery as the loss of data of business is prevented.
* EBS snapshots are incremental and reside changes in data concerning the last EBS snapshot. This reduces the time of backing up and reduces the cost of storage.

    
![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-019.png?raw=true)




## Creating EBS Snapshots Through AWS Console


### **Step 1: Navigate to EC2 Dashboard**

Go to the EC2 service dashboard, locate the **_Snapshots _**option under the **_Elastic Block Store_** category in the navigation pane, and click on it.


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-020.png?raw=true)



### **Step 2: Create Snapshots**

Click on the **_Create Snapshot_** button to initiate the process of creating a new EBS volume.


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-021.png?raw=true)



### **Step 3: Resource type**

Choose the resource type based on your requirements. There are two types of resources available. They are


#### **Volume**



* Create a snapshot from a specific volume.


#### **Instance**



* Create multi-volume snapshots from an instance

For this let us choose the **_volume_**.


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-022.png?raw=true)



### **Step 4: Choose the Volume ID**

Select the ID of the desired volume. Let’s choose the ID of the volume that we have created before. 


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-023.png?raw=true)



### **Step 5: Configure Additional Settings**

Optionally configure additional settings such as encryption and tags.


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-024.png?raw=true)



### **Step 6: Review and Create**

Review the configuration details of the EBS Snapshot. Click on the **_Create Snapshot_** button to finalize the creation process.


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-025.png?raw=true)



## **Managing Snapshot**


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-026.png?raw=true)



### **Create Volume from Snapshot** 



* Generate a new EBS volume based on the selected snapshot for use with EC2 instances.


### **Create an Image from Snapshot**



* Create an Image from the selected snapshot, allowing you to launch EC2 instances with the same configuration.


### **Copy Snapshot**

Duplicate the selected snapshot to another region for backup or disaster recovery purposes.


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-027.png?raw=true)



### **Delete Snapshot**



* Permanently remove the selected snapshot from your AWS account.


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-028.png?raw=true)



![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-029.png?raw=true)



### **Manage Tags**



* Add, edit, or remove tags to organize and categorize snapshots for easier management.


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-030.png?raw=true)



### **Snapshot Settings**


#### **Modify Permissions**



* Adjust permissions to control who can access or manage the snapshot.

    
![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-031.png?raw=true)




#### **Manage Snapshot Locks**



* Apply or remove locks on snapshots to prevent accidental deletion.

    
![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-032.png?raw=true)




#### **Manage Fast Snapshot Restore** 



* Enable or disable fast snapshot restore to improve performance when restoring snapshots.


![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-033.png?raw=true)



### **Archiving**


#### **Restore Snapshot from Archive**



* Retrieve a snapshot from a long-term storage archive for recovery or access.

    
![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-034.png?raw=true)




#### **Change Restore Period**



* Adjust the duration for which a snapshot is kept in archive storage before deletion.


#### **Archive Snapshot**



* Move snapshots to archive storage for long-term retention and cost savings

    
![alt_text](https://github.com/EightPLabs/blogs/blob/main/EBS%20-%20Images/image-035.png?raw=true)

