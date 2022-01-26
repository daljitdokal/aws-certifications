# AWS cloud practitioner essentials all modules

## Module 1
### Cloud computing
The three cloud computing deployment models are cloud-based, on-premises, and hybrid. 

## Module 2
### Amazon EC2
Amazon Elastic Compute Cloud (Amazon EC2) provides secure, resizable compute capacity in the cloud as Amazon EC2 instances. By comparison, with an Amazon EC2 instance you can use a virtual server to run applications in the AWS Cloud.

Amazon EC2 Auto Scaling enables you to automatically add or remove Amazon EC2 instances in response to changing application demand. 
Within Amazon EC2 Auto Scaling, you can use two approaches: dynamic scaling and predictive scaling.

Amazon EC2 instance types: https://aws.amazon.com/ec2/instance-types/

### Elastic Load Balancing
Elastic Load Balancing is the AWS service that automatically distributes incoming application traffic across multiple resources, such as Amazon EC2 instances.

A load balancer acts as a single point of contact for all incoming web traffic to your Auto Scaling group. This means that as you add or remove Amazon EC2 instances in response to the amount of incoming traffic, these requests route to the load balancer first. Then, the requests spread across multiple resources that will handle them. For example, if you have multiple Amazon EC2 instances, Elastic Load Balancing distributes the workload across the multiple instances so that no single instance has to carry the bulk of it. 

### Messaging and queuing
#### monolithic application
Applications are made of multiple components. Suppose that you have an application with tightly coupled components. These components might include databases, servers, the user interface, business logic, and so on. This type of architecture can be considered a monolithic application. 
In this approach to application architecture, if a single component fails, other components fail, and possibly the entire application fails.

#### microservices approach
In a microservices approach, application components are loosely coupled. In this case, if a single component fails, the other components continue to work because they are communicating with each other. The loose coupling prevents the entire application from failing

#### Amazon Simple Notification Service (Amazon SNS) [payload]
Amazon Simple Notification Service (Amazon SNS) is a publish/subscribe service. Using Amazon SNS topics, a publisher publishes messages to subscribers. This is similar to the coffee shop; the cashier provides coffee orders to the barista who makes the drinks.

In Amazon SNS, subscribers can be web servers, email addresses, AWS Lambda functions, or several other options. 

### Serverless: 
All taken care for you: The term “serverless” means that your code runs on servers, but you do not need to provision or manage these servers.
Another benefit of serverless computing is the flexibility to scale serverless applications automatically. 

#### AWS Lambda
AWS Lambda is a service that lets you run code without needing to provision or manage servers. 

### Containers:
In AWS, you can also build and run containerized applications. Containers provide you with a standard way to package your application's code and dependencies into a single object. 

#### Amazon Elastic Container Service (Amazon ECS)
Amazon ECS supports Docker containers. Docker is a software platform that enables you to build, test, and deploy applications quickly.

#### Amazon Elastic Kubernetes Service (Amazon EKS)
Amazon Elastic Kubernetes Service (Amazon EKS) is a fully managed service that you can use to run Kubernetes on AWS. 

#### AWS Fargate
AWS Fargate is a serverless compute engine for containers. It works with both Amazon ECS and Amazon EKS. 

## Module 3
### AWS global infrastructure
#### Availability Zone:
An Availability Zone is a single data center or a group of data centers within a Region. Availability Zones are located tens of miles apart from each other. This is close enough to have low latency (the time between when content requested and received) between Availability Zones. However, if a disaster occurs in one part of the Region, they are distant enough to reduce the chance that multiple Availability Zones are affected.

#### Edge locations
An edge location is a site that Amazon CloudFront uses to store cached copies of your content closer to your customers for faster delivery.

#### Ways to interact with AWS services
- AWS Management Console:  web-based interface
- AWS Command Line Interface (AWS CLI): API requests
- Software development kits (SDKs): supported programming languages include C++, Java, .NET, and more.

#### AWS Elastic Beanstalk
With AWS Elastic Beanstalk, you provide code and configuration settings, and Elastic Beanstalk deploys the resources necessary to perform.

#### AWS CloudFormation
With AWS CloudFormation, you can treat your infrastructure as code. This means that you can build an environment by writing lines of code instead of using the AWS Management Console to individually provision resources.

## Module 4
### Connectivity to AWS
#### Amazon Virtual Private Cloud (Amazon VPC)
Amazon VPC enables you to provision an isolated section of the AWS Cloud. In this isolated section, you can launch resources in a virtual network that you define. Within a virtual private cloud (VPC), you can organize your resources into subnets. A subnet is a section of a VPC that can contain resources such as Amazon EC2 instances.

Internet gateway:
To allow public traffic from the internet to access your VPC, you attach an internet gateway to the VPC. An internet gateway is a connection between a VPC and the internet.

#### Virtual private gateway
To access private resources in a VPC, you can use a virtual private gateway. A virtual private gateway allows traffic into the VPC only if it is coming from an approved network.

#### AWS Direct Connect
AWS Direct Connect is a service that enables you to establish a dedicated private connection between your data center and a VPC.  


### Subnets
A subnet is a section of a VPC in which you can group resources based on security or operational needs. Subnets can be public or private. 
- Public subnets contain resources that need to be accessible by the public, such as an online store’s website.
- Private subnets contain resources that should be accessible only through your private network, such as a database that contains customers’ personal information and order histories.

### Network access control lists (ACL)
When a customer requests data from an application hosted in the AWS Cloud, this request is sent as a packet. A packet is a unit of data sent over the internet or a network. 
It enters into a VPC through an internet gateway. Before a packet can enter into a subnet or exit from a subnet, it checks for permissions. These permissions indicate who sent the packet and how the packet is trying to communicate with the resources in a subnet.
The VPC component that checks packet permissions for subnets is a network access control list (ACL).

### Domain Name System (DNS)
Translating a domain name to an IP address.

#### AWS Route 53
Amazon Route 53 is a DNS web service. It gives developers and businesses a reliable way to route end users to internet applications hosted in AWS.

## Module 5
### Instance stores and Amazon Elastic Block Store (Amazon EBS)
#### Amazon Virtual Private Cloud (Amazon VPC)
Amazon Elastic Block Store (Amazon EBS) is a service that provides block-level storage volumes that you can use with Amazon EC2 instances. If you stop or terminate an Amazon EC2 instance, all the data on the attached EBS volume remains available.

#### Amazon EBS snapshots
An EBS snapshot is an incremental backup. This means that the first backup taken of a volume copies all the data. For subsequent backups, only the blocks of data that have changed since the most recent snapshot are saved. 

Incremental backups are different from full backups, in which all the data in a storage volume copies each time a backup occurs. The full backup includes data that has not changed since the most recent backup.

### Amazon Simple Storage Service (Amazon S3)
Amazon Simple Storage Service (Amazon S3) is a service that provides object-level storage. Amazon S3 stores data as objects in buckets.

You can upload any type of file to Amazon S3, such as images, videos, text files, and so on. For example, you might use Amazon S3 to store backup files, media files for a website, or archived documents. Amazon S3 offers unlimited storage space. The maximum file size for an object in Amazon S3 is 5 TB.

When you upload a file to Amazon S3, you can set permissions to control visibility and access to it. You can also use the Amazon S3 versioning feature to track changes to your objects over time

Note:
S3: Upload file as whole, web enable and best for static web hosting, EC2 is not required.

EBS: Upload file as only updated part i.e. not re-upload 8-GB video if you just updated one part of the video. EC2 is required.

### Amazon Relational Database Service (Amazon RDS)
Amazon Relational Database Service (Amazon RDS) is a service that enables you to run relational databases in the AWS Cloud.

#### Amazon Aurora - SQL
Amazon Aurora is an enterprise-class relational database. It is compatible with MySQL and PostgreSQL relational databases. It is up to five times faster than standard MySQL databases and up to three times faster than standard PostgreSQL databases.

#### Amazon DynamoDB - NoSQL
Amazon DynamoDB is a key-value database service. It delivers single-digit millisecond performance at any scale.
- Serverless and managed
- Nonrelational databases: In a nonrelational database, you create tables. A table is a place where you can store and query data. Nonrelational databases are sometimes referred to as “NoSQL databases” because they use structures other than rows and columns to organize data. One type of structural approach for nonrelational databases is key-value pairs. With key-value pairs, data is organized into items (keys), and items have attributes (values). You can think of attributes as being different features of your data.

#### Amazon Redshift - Warehousing service
Amazon Redshift is a data warehousing service that you can use for big data analytics. It offers the ability to collect data from many sources and helps you to understand relationships and trends across your data.

#### AWS Database Migration Service (AWS DMS)
AWS Database Migration Service (AWS DMS) enables you to migrate relational databases, nonrelational databases, and other types of data stores.

## Module 6
#### The AWS shared responsibility model
Throughout this course, you have learned about a variety of resources that you can create in the AWS Cloud. These resources include Amazon EC2 instances, Amazon S3 buckets, and Amazon RDS databases. Who is responsible for keeping these resources secure: you (the customer) or AWS?

The answer is both. The reason is that you do not treat your AWS environment as a single object. Rather, you treat the environment as a collection of parts that build upon each other. AWS is responsible for some parts of your environment and you (the customer) are responsible for other parts. This concept is known as the shared responsibility model.

### User permissions and access
#### AWS Identity and Access Management (IAM)
AWS Identity and Access Management (IAM) enables you to manage access to AWS services and resources securely.   

#### AWS Organizations
Suppose that your company has multiple AWS accounts. You can use AWS Organizations to consolidate and manage multiple AWS accounts within a central location.

When you create an organization, AWS Organizations automatically creates a root, which is the parent container for all the accounts in your organization. 
In AWS Organizations, you can centrally control permissions for the accounts in your organization by using service control policies (SCPs). SCPs enable you to place restrictions on the AWS services, resources, and individual API actions that users and roles in each account can access.

#### Compliance
Depending on your company’s industry, you may need to uphold specific standards. An audit or inspection will ensure that the company has met those standards.

AWS Artifact is a service that provides on-demand access to AWS security and compliance reports and select online agreements. AWS Artifact consists of two main sections: AWS Artifact Agreements and AWS Artifact Reports.

#### Denial-of-service attacks
A denial-of-service (DoS) attack is a deliberate attempt to make a website or application unavailable to users.

AWS Shield
AWS Shield is a service that protects applications against DDoS attacks. AWS Shield provides two levels of protection: Standard and Advanced.




