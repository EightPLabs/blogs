# RDS on AWS -Introduction

## Introduction

- A managed database service by Amazon Web Services (AWS).
- They are designed to simplify database setup, operation, and scaling for relational databases.
- RDS supports various database engines like MySQL, PostgreSQL, SQL Server, Oracle, and MariaDB.
- It offers features like automated backups, monitoring, and high availability.
- Ideal for businesses looking for reliable, scalable, and cost-effective database solutions without the challenge of infrastructure management.

## Key Features of RDS

- **Availability**: RDS offers automated backups and user-initiated snapshots for quick database recovery and monitoring. Snapshots can be shared among multiple AWS accounts for expanded availability while ensuring data security.
- **Security**: Users create restricted passwords for database access and are assigned the Admin role by default. Encryption using KMS enhances data security.
- **Scalability**: RDS allows for automatic scaling based on transaction volume, supporting both horizontal and vertical scaling to handle increased traffic or resource demands.
- **Performance**: RDS offers SSD-backed storage options (General Purpose and Provisioned) impacting resource performance based on workload requirements.
- **Pricing**: Pay-as-you-go model with no minimum charge, allowing users to delete resources and avoid charges. Free-tier accounts have specific configurations and no bills upon resource deletion.
- **Automated Backup and Redundancy:** RDS provides automated backup mechanisms and redundancy features to ensure data integrity and availability reducing the risk of data loss.
- **Tools for Monitoring and Management:** RDS offers tools for monitoring database performance, managing configurations, and diagnosing issues enabling users to maintain optimal database operation.
- **Automatic Software Updates and Other Security Features:** RDS automatically applies software updates and patches to the database engine, enhancing security and compliance without requiring user intervention.

## Available Database Engines

- **MySQL**: Amazon RDS provides managed MySQL database instances, offering scalable, reliable, and cost-effective business solutions.
- **PostgreSQL**: Amazon RDS supports PostgreSQL, allowing users to easily deploy and manage PostgreSQL databases, ensuring high availability and compatibility.
- **Oracle**: Amazon RDS offers managed Oracle database instances, enabling businesses to run Oracle Database workloads in the cloud with features like automated backups and monitoring.
- **Microsoft SQL Server:** Amazon RDS supports Microsoft SQL Server, providing managed instances for SQL Server databases with options for easy scaling and high availability.
- **MariaDB:** Amazon RDS supports MariaDB, offering fully managed instances for MariaDB databases, allowing users to focus on application development while RDS handles database management tasks.

## Available Server Types

##### Standard

- Provides a balanced mix of computing, memory, and networking resources.
- Suitable for a wide range of workloads with moderate resource requirements.
- Offers predictable performance and cost-effective pricing.

##### Memory Optimized

- Optimized for memory-intensive workloads that require high memory-to-CPU ratios.
- Ideal for applications such as in-memory databases, caching, and analytics.
- Provides ample memory capacity to handle large datasets and high-throughput workloads efficiently.

##### Burstable performance

- Offers baseline CPU performance with the ability to burst CPU usage when needed.
- Suitable for workloads with variable CPU demands or periodic spikes in activity.
- Provides cost savings for workloads that do not require consistently high CPU utilization.

##### Optimized Read

- It is designed for read-heavy database workloads that require high throughput and low latency for read operations.
- Utilizes replicas with optimized configurations to offload read traffic from the primary database instance.
- Improves overall database performance and scalability by distributing read requests across multiple replicas.


### Should I go for it?

#### YES!

- Want to move faster
- You lack manpower/time to manage DB
- Money is not a constraint
- Want to easily get many NFRs like backup/restore, redundancy, failover etc. with the click of a button

### No!

- Well, the biggest challenge is cost -if you are short on money, then RDS can start burning your reserve sooner than expected
- You are a techie and can do a bit of hand dirty when needed
- Still in POC mode and NFR like backup/restore, and failover are not that crucial for you
- Once DB is up, your interaction with it will be minimal (Minimal usage and less data so need of tuning etc.)


Wait for the next blog to have detailed instructions on how to create an RDS DB in AWS




