

## What is S3? 

S3 is an on-demand cloud storage solution managed by AWS that can be used to store files, data, images, videos, etc. Did you notice the “on-demand” word -it means there is no limitation on the size and as per demand size will be allocated. Also, since AWS manages it, users need not worry about scalability, availability, durability, and other non-functional aspects. 


## What are the uses of S3?



* Backup and archiving
* Storage of large files like video and images
* Content sharing, S3 buckets can be shared across apps
* Static website hosting
* Bigdata processing 

There are many other use cases that can leverage S3 but above are a few.


## Advantages of using S3



* **Cost-effective**: Storage in S3 is really cheap. There are some nuances with networking cost, still, it is much cheaper than other storage options available. 
* **Auto-scaling**: The user is concerned with adding data, there is no need for any capacity planning. This is a big plus. In the traditional disk-based approach, as soon as our data grows we need to scale the infrastructure which involves capacity planning, upfront expenses, and much more complexity. 
* **High availability**: S3 does not go down, literally, the data can be accessed from anywhere and anytime. If not using S3, programmers need to take care of this aspect, and can be a big distraction.
* **Durability**:  Data in s3 is stored at multiple places, so corruption at one place does not impact the data.
* **Global access**: S3 buckets are global and can be accessed from anywhere in the world.


## How S3 storage is different

Storage is of different types, for e.g., RAID, Object Storage -S3 falls into the category of Object storage. 



* **Block storage**: operates at raw storage device level and manages data as a set of numbered fixed-size blocks
* **File storage**: Manages data as named hierarchy of files and folders.

Both of these are closely associated with the server and OS that is hosting the storage.



* **Object Storage**: Contrary to these, S3 does not expose any underlying storage mechanism, it is managed as objects which can be accessed via API using standard HTTP verbs like GET, PUT, POST, etc.


## Core concepts of S3



* **Buckets**: Buckets are the primary containers to hold data.  There is no limit on the number of objects which can be stored in the bucket. By default, the number of buckets in each account is 100 which can be increased to a max of 1000. There is no performance impact due to the number of buckets. 
* **Objects**: Objects are entities that we store in S3, e.g. files, photos, videos, etc. AWS treats objects as streams of bytes so there is no restriction as to what can be stored in the file. It can be as small as 0 bytes and as large as 5TB. Each object contains data as well as metadata. Metadata is a set of name-value pair which provides additional information about the object stored.
* **Keys**: A key is a unique identifier for the stored object. They are used to access objects in the bucket and to perform other operations. It consists of the bucket name, path, and file name. If versioning is enabled, it is also part of the key. If there is a file named “test.jpg” in bucket “My_BUCKET” under path “test1/test2”
    * The URL to access it will be [https://MY_BUCKET.s3.us-west-1.amazonaws.com/test1/test2/test.jpg](https://MY_BUCKET.s3.us-west-1.amazonaws.com/test1/test2/test.jpg)
    * The bucket name is MY_BUCKET and the key is test1/test2/test.jpg

    A common mistake, people take the “/” for folders but let’s repeat, there is no folder in S3, it’s just a convenient way to group stuff. 



## Accessing Objects



* S3 is storage on the web, so every object has to go ta unique URL. From the above example, [https://MY_BUCKET.s3.us-west-1.amazonaws.com/test1/test2/test.jpg](https://MY_BUCKET.s3.us-west-1.amazonaws.com/test1/test2/test.jpg) represents a file that can be accessed from the web depending on the permission and policies.
* S3 supports GET rest API as well as SDK through which Objects can be accessed
* A unique link of an Object can be signed and made available as a public URL for a fixed period of time


## Consistency 

S3 provides two types of consistency



* **Read-after-write consistency**: For creating and deleting existing objects, S3 provides read-after-write consistency -this means when a new object is created or existing once deleted, S3 guarantees that the latest version of the Object is available.
* **Eventual consistency**: If objects are updated, it may take some time to propagate across all of its servers. It might be possible to read an older version of the object for a while even it got updated. 


## Static hosting 

This is one of the prominent use cases, where static hosting can be enabled for a bucket and then the files inside the bucket can be used to host a static website. Typical steps would be:



* Create a bucket and enable static website hosting for it
* Add index and error files -these files are mandatory to be provided
* Create a route53 record to point to the bucket
* Create cloud-front distribution so that site is faster and more reliable 


## Versioning 

Versioning can be enabled on S3 -by default, it is disabled. Once enabled, it can be suspended but cannot be disabled. When versioning is enabled, the files never get permanently deleted -older copies are maintained by AWS. This is very handy if we want to restore to an earlier version.


## Access Control

Access policies can be used to define who can access what. 



* **Resource-based policies**
    * ACL- Each ACL Identifies resources and the permission granted. The resource here can be a bucket or just an Object. It can be used to grant read-write permissions to other AWS accounts.
    * Bucket policy- these can be applied at the bucket level and not the object level as in the case of ACL. Users or accounts can be granted access to content in a particular bucket.
* **User policies**: AWS IAM can be used to create groups, and users and then assign them permission for specific buckets and specific operations on that.
* **Signed URLs**: Presigned URLs can be created which will be public for a certain period of time and then will expire. 
* **CORS**: by default any client or website which is on a different domain, cannot access the resources of another domain. S3 allows enabling CORS for clients and domains so that its object can be cross-referenced.


## Encryption



* **Securing data in transit**
    * S3 supports SSL/TLS to encrypt data in transit when it's sent to or retrieved from S3
* **Securing data at rest**: Server side encryption with AWS managed keys (SSE-S3) is now applied by default on all the data stored in the S3 bucket. This change has been introduced on January 5, 2023, and this will not be charged separately.
    * **SSE-S3**: This is the default and simplest approach. S3 automatically encrypts data when it's stored, and decrypts it when it's retrieved. The encryption keys are managed by S3 and are rotated regularly.
    * **SSE-KMS**: Same as SSE-S3, but the Key Management Service (KMS) is used to manage the encryption keys. KMS provides a full audit trail of how the key has been used and modified over a period of time. This has additional cost implications.
    * **SSE-C**: SSE-C allows you to provide your own encryption keys, which S3 will use to encrypt and decrypt your data. This option is helpful if you have existing encryption infrastructure or if you have specific compliance or regulatory requirements.
    * **Client-side encryption**: Data uploaded to S3 is already encrypted. 


## Replication

Data in S3 is always replicated in multiple availability zones, but all zones are part of the same region. If for some reason, entire regions is unavailable, for e.g., natural disaster, political scenarios, etc. then we can lose data. Cross-region replication is a feature in S3 that can be used to replicate S3 objects in different regions. This comes at an additional price of storage, and network cost -so the pros and cost of cost vs the importance of data should be judged. 


## Event Notification

AWS S3 supports event notification which will notify registered listeners if some action happens on the object. For e.g, when an object is added/updated or deleted events will be generated which can be used to invoke lambda, send messages to SQS or SNS, integrate with event-bridge, and many more use cases.


## What are the different storage classes in S3?

Depending on the access pattern of data we can store it in different classes of storage and further optimize on cost



* **Storage class for frequently accessed Objects**: This storage class is most suitable for “hot” data, meaning this is the data on which an app or program operates frequently, is critical and needs a millisecond response.
    * **S3 standard**: This is the default, if no storage class is identified, this will be used. Its availability is 99.99% (only this storage class has 2 9’s availability) and is available in >=3 Availability zones.
    * **Reduced Redundancy**: This is intended for non-critical and reproducible data. But AWS **_does not recommend_** using it, S3 standard can have a better cost advantage.
* **Storage class for automatically optimizing data with changing or unknown access pattern**: This storage class can be used for data that can be “hot” for a few days, but as it olds, it’s relevance may decrease.
    * **S3 intelligent tiering**: This moves data to the most effective cost tier without impacting the performance impact. For e.g., if there is a news app that has videos and images, it makes sense to keep the latest data in S3 standard but move infrequently accessed data (as news grows older, the likelihood of it’s access also reduces) to cheaper storage. It’s availability is 99.9% and is available in >=3 Availability zones.
* **Storage classes for infrequently accessed objects**: This is cheaper than the S3 standard but still provides millisecond access. This is most suited for data that is long-lived, is infrequently accessed, and still needs to be retrieved in milliseconds.
    * **S3 standard-IA**: Data is stored in multiple availability zones and resilient to the loss of data in one availability zone. Its availability is 99.9% and is available in >=3 Availability zones.
    * **S3 one zone-IA**: This is even cheaper than S3 standard-IA, but data will only be stored in a single availability zone. If that crashes, data will be lost. This is suitable for data for which replication is enables or data that can be easily recreated. Its availability is 99.5%.
* **Storage classes for archiving objects**: When data is not frequently accessed and mostly will be needed on an “on-demand” basis, for example, to do some audit, or to analyze some data past. The most important aspect is, the time to retrieve data is not critical. Data in the glacier is first restored to S3 standard or S3 standard IA and then only it’s available for use.
    * **S3 Glacier instant retrieval**: Although this data is archived, it can be accessed in milliseconds. Its availability is 99.99% and is available in >=3 Availability zones.
    * **S3 Glacier flexible retrieval**: Effective when data is not accessed for at least 90 days. Retrieval can take minutes to hours. Its availability is 99.99% (after restore) and is available in >=3 Availability zones.
    * **S3 Glacier Deep Archive**: This is the cheapest storage and should be used if data is not going to be needed for at least 180 days. Data can be retrieved before that but it may be subject to an early deletion fee. It has a default retrieval time of 12 hours. Its availability is 99.99% (after restore) and is available in >=3 Availability zones.

All storage classes except RRS (which is anyway not recommended by AWS) have durability of 99.999999999% (Nine 9’s). RRS (Reduced redundancy storage) has a durability of 99.99%


## What are lifecycle rules?

Lifecycle rules can be used to transition objects from one storage class to another, delete, archive files or restore files from the glacier. For example, if we are using S3 to store application logs, we may need weekly logs for active analysis, but once they are older than 30 days we may want to archive them, and maybe after a year we no longer need them, so permanently delete the logs. These all transitions can be achieved automatically by setting transition rules.


## Wrapping Up
Thus, we have learnt about the advantages, unique features, core concepts, and different storage classes in S3. 
