
# AWS Global Infrastructure

As a leading cloud service provider, Amazon Web Services (AWS) has established a global network to run and manage cloud services and support worldwide. Currently, there are 33 AWS regions with 105 available zones and it continues to expand with an announced plan of 4 additional zones with 12 new available zones across the globe.


![alt_text](images/image1.png "image_tooltip")


 This blog will explore the fundamental components of AWS Global infrastructure like Data centers, regions, and Availability Zones (AZs). 


## AWS Data Centers and their Facilities



* Data centers are the foundation of AWS cloud infrastructure.
* They are physical locations for storing servers, routers, firewalls, storage systems, and switches.
* Distributed across multiple regions for redundancy and availability.
* They are connected through high-speed networking for communication between Availability Zones and global regions.


## AWS Regions



* AWS operates in 33 regions globally.
* Each region is isolated, ensuring data remains within the chosen region.
* Regions consist of multiple data centers with high-speed private networking.
* Various cloud services are available in each region, including computing, storage, databases, and networking.
![alt_text](images/image2.png "image_tooltip")

* These services are designed to be durable, redundant, and capable of failing over to backup services within the same region in the event of a disaster. 


### Characteristics of AWS Regions



* AWS regions provide geographic diversity, allowing users to choose the location closest to their audience for reduced latency.
* AWS Regions enable resource scaling based on demand and support efficient handling of increased workloads.
* Combined with CDN (Content Delivery Network) services, AWS regions support global content delivery, enhancing content distribution's speed and efficiency.
* AWS regions provide security isolation containing the impact of security incidents within specific geographic boundaries.


![alt_text](images/image3.png "image_tooltip")


Depending on the application scope and requirements of the user, they may choose to operate in one or more regions at a time. Using multiple regions for the application deployment will improve its reliability and availability. AWS offers services like Route 53 for geographically load-balancing application stacks hosted in different regions.


## AWS Availability Zones



* Each region has at least two or more availability zones.
* Availability Zones represent isolated data centers within a geographical region.
* They are connected through a private fiber network to enable data transfers.
* The purpose is to enhance application and service availability and reliability.


![alt_text](images/image4.png "image_tooltip")



### AZ Balancing and Distribution of Resources


![alt_text](images/image5.png "image_tooltip")




* Data center failure within AZ doesn't affect AWS-managed services in the region
* Services like S3, and Elastic Load Balancing are designed to run independently
* Availability Zones distributed across different physical regions within the region
* AWS balances and distributes resources across Availability Zones
* Dynamic allocation of physical data center locations for subnets
* Subnets may be stored in different data centers within the same AZ


### Multiple Availability Zones



* Applications are designed to operate across multiple Availability Zones for high availability.

    
![alt_text](images/image6.png "image_tooltip")


* Key infrastructure services like VPC (Virtual Private Cloud), ELB, EC2, and Auto Scaling are deployed across multiple Availability Zones.


### Failover and High Availability



* Designing for multiple Availability Zones is crucial for application failover and database replication.
* Applications are designed to automatically failover between Availability Zones to ensure availability.


## Selecting a Region for Workloads


### Factors influencing region selection

When choosing a specific zone for workloads involves considering certain factors. They are



* Compliance Rules
* Latency Issues
* Service offered
* Pricing Realities 


#### Compliance Rules



* Compliance rules determine the measures that AWS regions must follow to meet the needs and expectations of customers operating in the specific regions.
* Compliance rules ensure the integrity, security, and reliability of cloud services and improve the trust of the organizations to utilize the cloud for their business.


#### Latency Issues



* latency issues arise due to the physical distance between users and the servers hosting cloud services
* Higher latency causes slower response times and user dissatisfaction with cloud services


#### Service offered



* Review the availability of essential AWS services in the selected region.
* Ensure that computing, storage, databases, and networking services meet the workload needs.


#### Pricing Realities 



* Pricing realities include the actual costs and fees associated with utilizing cloud services across AWS regions
* It involves understanding the pricing structures for various services, such as computing, storage, and data transfer.
* Factors like service usage, data storage volumes, and additional features can affect pricing


### Regional service availability

AWS services may not be uniformly accessible across all AWS regions with variations in availability based on geographic location. Organizations assess regional service availability when selecting AWS regions for deployment to ensure that required services are accessible. These are some of the core infrastructure services in all AWS regions.

 


![alt_text](images/image7.png "image_tooltip")



#### 1. Compute service
* AWS EC2
* AWS Lambda
#### 2. Storing service
* AWS S3 (Simple Storage Service)
* AWS EBS (Elastic Block Service)
* AWS Glacier
#### 3. Database service
* Amazon RDS (Relational Database Service)
* Amazon DynamicDB
#### 4. Networking service
* Elastic load balancing


## AWS Edge Locations


### 
![alt_text](images/image8.png "image_tooltip")



### Definition and purpose



* AWS Edge locations are distributed data centers forming part of Amazon's CloudFront content delivery network (CDN).
* Edge Locations are positioned globally to ensure low latency and high data transfer speeds for users accessing content hosted on AWS.
* Store frequently accessed data near end-users to enable faster delivery of content.
* It is essential for optimizing performance and enhancing user experience by reducing latency and improving data delivery efficiency

The Services offered at each edge are 



* Route 53
*  AWS Shield
* Web Application Firewall
* CloudFront. 


### Global content delivery



* AWS Global Content Delivery utilizes a network of edge locations distributed worldwide to efficiently deliver digital content to users irrespective of their geographic location
* AWS Global Content Delivery benefits users by improving performance and reliability when accessing content, even during peak demand or traffic spikes
* AWS global content distribution at edge locations near end-users diminishes the time required for users to access content, resulting in quicker load times and enhanced responsiveness of web applications.


## Amazon CloudFront



* CloudFront is a content delivery network service.
* Its primary goal is to reduce latency and provide fast access to content.

    
![alt_text](images/image9.png "image_tooltip")


* Efficiently delivers web pages, images, videos, and other static or dynamic assets globally.
* Its infrastructure is designed to provide high transfer speeds, enhancing the user experience


### Key features and benefits



* CloudFront has a great network of edge locations distributed across the world that helps in delivering content to end users closer to minimize latency and enhance user experience.
* Provides fast and prompt delivery of content during peak traffic periods.
* It is integrated with other AWS services to offer enhanced security features like DDoS protection, SSL/TLS encryption, and field-level encryption.


### CloudFront Use Cases



* CloudFront helps to improve the speed of delivering static content for websites and increases the performance and user experience of a website.
* It offers high-definition video content to viewers with low latency and high reliability.
* It enables the distribution of software packages and patches for faster downloads and smooth software deployment.


## Security in AWS Global Infrastructure



* AWS Key Management Service delivers a key management service to encrypt data that’s saved on services such as S3, EBS, and RDS, among others, as well as SSL/TLS encryption to secure data transmission through networks.
* AWS aligns with numerous compliance standards and certifications like SOC, PCI DSS, HIPAA, and GDPR ensuring that customers can meet their regulatory requirements.
* Virtual Private Cloud enables users to build isolated virtual networks, and it also provides the capability to define security groups and network access control list options to control both inbound and outbound traffic.
* Web Application Firewall and AWS Shield protect against DDoS attacks and web application vulnerabilities.


## Best Practices for Global Deployments



* **Multi-region Architecture:** Enhances fault tolerance and disaster recovery by spreading resources across diverse regions. Amazon Route 53 and AWS Global Accelerator optimize traffic management by directing users to the nearest AWS region. 
* **Auto Scaling:** Utilize AWS Auto Scaling to dynamically adjust resource capacity based on changes in demand. Design scalable architectures utilizing services like AWS Elastic Load Balancing (ELB) to evenly distribute incoming traffic across multiple instances and Availability Zones.
* **High Availability:** Develop load balancing, database replication, and data synchronization mechanisms that ensure that services are always available during failure.
* **Performance Optimization:** Optimize performance by leveraging AWS services like Amazon CloudFront for content delivery, Amazon Aurora for databases with high performance, and AWS Global Accelerator for improving application responsiveness and reducing latency.


## Cost Optimization Strategies



* For storage cost optimization, use AWS S3 storage classes such as S3 Standard, S3 Intelligent-Tiering, S3 Glacier, and S3 Glacier Deep Archive depending on the data access patterns and retrieval needs.
* Use AWS Cost Explorer, AWS Budgets, and AWS Cost Anomaly Detection to monitor cost trends, analyze cost drivers, and implement measures to reduce costs on time.
* For optimizing resources use AWS Trusted Advisor and AWS Cost Explorer to review the metrics of resource utilization and discover unused resources. 
