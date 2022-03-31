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

EC2 purchnage options:
- **Demand**: Pay per duration used
- **Saving plans**: 1 year or 3 years term (upto 72% saving)
- **Reserved Instances**: Pedictable use then use this - 1 year or 3 years term (upto 72% saving) (3 payment options, upfron, partialy upfrond, no upfront)
- **Spot Instances**: AWS can reclaim any of these (2 minutes warning before reclaim)
- **Dedicated Instances**: Physical servers with Amazon EC2 instance capacity that is fully dedicated to your use. 
- 
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

#### Region (i.e. Sydney: ap-southeast-2)
AWS has the concept of a Region, which is a physical location around the world where we cluster data centers. We call each group of logical data centers an Availability Zone. Each AWS Region consists of multiple, isolated, and physically separate AZs within a geographic area.

#### Availability Zone (data centers):
An Availability Zone is a single data center or a group of data centers within a Region. Availability Zones are located tens of miles apart from each other. This is close enough to have low latency (the time between when content requested and received) between Availability Zones. However, if a disaster occurs in one part of the Region, they are distant enough to reduce the chance that multiple Availability Zones are affected.

**Note:**
Run across at least 2 AZ in a Region.

#### Edge locations
An edge location is a site that Amazon CloudFront uses to store cached copies of your content closer to your customers for faster delivery.

#### Ways to interact with AWS services
- AWS Management Console:  web-based interface
- AWS Command Line Interface (AWS CLI): API requests
- Software development kits (SDKs): supported programming languages include C++, Java, .NET, and more.

#### AWS CloudFormation  (Lower level service from AWS)
With AWS CloudFormation, you can treat your infrastructure as code (you have direct control to manage granular details)

#### AWS Elastic Beanstalk (Higher level service from AWS)
With AWS Elastic Beanstalk, you provide code and configuration settings, and Elastic Beanstalk deploys the resources necessary to perform. (AWS have direct control to manage granular details)


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
#### Amazon Elastic Block Store
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


## Module 6
### Amazon CloudWatch
Amazon CloudWatch is a web service that enables you to monitor and manage various metrics and configure alarm actions based on data from those metrics.

#### CloudWatch alarms
You can create alarms that automatically perform actions if the value of your metric has gone above or below a predefined threshold. 

For example, suppose that your company’s developers use Amazon EC2 instances for application development or testing purposes. If the developers occasionally forget to stop the instances, the instances will continue to run and incur charges. 

The CloudWatch dashboard feature enables you to access all the metrics for your resources from a single location. For example, you can use a CloudWatch dashboard to monitor the CPU utilization of an Amazon EC2 instance, the total number of requests made to an Amazon S3 bucket, and more. You can even customize separate dashboards for different business purposes, applications, or resources.

## Module 7
#### AWS CloudTrail
AWS CloudTrail records API calls for your account. The recorded information includes the identity of the API caller, the time of the API call, the source IP address of the API caller, and more. You can think of CloudTrail as a “trail” of breadcrumbs (or a log of actions) that someone has left behind them.

#### CloudTrail Insights
Within CloudTrail, you can also enable CloudTrail Insights. This optional feature allows CloudTrail to automatically detect unusual API activities in your AWS account. 

For example, CloudTrail Insights might detect that a higher number of Amazon EC2 instances than usual have recently launched in your account. You can then review the full event details to determine which actions you need to take next.

#### AWS Trusted Advisor
AWS Trusted Advisor is a web service that inspects your AWS environment and provides real-time recommendations in accordance with AWS best practices.

Trusted Advisor compares its findings to AWS best practices in five categories: cost optimization, performance, security, fault tolerance, and service limits. For the checks in each category, Trusted Advisor offers a list of recommended actions and additional resources to learn more about AWS best practices. 

## Module 8
#### How AWS pricing works
AWS offers a range of cloud computing services with pay-as-you-go pricing.

#### AWS Pricing Calculator
The AWS Pricing Calculator lets you explore AWS services and create an estimate for the cost of your use cases on AWS. You can organize your AWS estimates by groups that you define. A group can reflect how your company is organized, such as providing estimates by cost center.

#### Consolidated billing
In an earlier module, you learned about AWS Organizations, a service that enables you to manage multiple AWS accounts from a central location. AWS Organizations also provides the option for consolidated billing. 

The consolidated billing feature of AWS Organizations enables you to receive a single bill for all AWS accounts in your organization. By consolidating, you can easily track the combined costs of all the linked accounts in your organization. The default maximum number of accounts allowed for an organization is 4, but you can contact AWS Support to increase your quota, if needed.

#### AWS Budgets
In AWS Budgets, you can create budgets to plan your service usage, service costs, and instance reservations.
The information in AWS Budgets updates three times a day. This helps you to accurately determine how close your usage is to your budgeted amounts or to the AWS Free Tier limits.
In AWS Budgets, you can also set custom alerts when your usage exceeds (or is forecasted to exceed) the budgeted amount.

#### AWS Cost Explorer
AWS Cost Explorer is a tool that enables you to visualize, understand, and manage your AWS costs and usage over time.

#### AWS Support
AWS offers four different Support plans to help you troubleshoot issues, lower costs, and efficiently use AWS services. 

You can choose from the following Support plans to meet your company’s needs: 
Basic
Developer
Business
Enterprise

#### Technical Account Manager (TAM)
The Enterprise Support plan includes access to a Technical Account Manager (TAM).


##### AWS Marketplace
AWS Marketplace is a digital catalog that includes thousands of software listings from independent software vendors. You can use AWS Marketplace to find, test, and buy software that runs on AWS. 
For each listing in AWS Marketplace, you can access detailed information on pricing options, available support, and reviews from other AWS customers.
AWS Marketplace offers products in several categories, such as Infrastructure Products, Business Applications, Data Products, and DevOps.

## Module 9
### AWS Cloud Adoption Framework (AWS CAF)
#### 6 core perspectives of the Cloud Adoption Framework
At the highest level, the AWS Cloud Adoption Framework (AWS CAF) organizes guidance into six areas of focus, called Perspectives. Each Perspective addresses distinct responsibilities. The planning process helps the right people across the organization prepare for the changes ahead.

In general, the Business, People, and Governance Perspectives focus on business capabilities, whereas the Platform, Security, and Operations Perspectives focus on technical capabilities.

#### 6 strategies for migration
When migrating applications to the cloud, six of the most common migration strategies that you can implement are:
Rehosting
Replatforming
Refactoring/re-architecting
Repurchasing
Retaining
Retiring


#### AWS Snow Family members
The AWS Snow Family is a collection of physical devices that help to physically transport up to exabytes of data into and out of AWS. 
AWS Snow Family is composed of AWS Snowcone, AWS Snowball, and AWS Snowmobile. 

## Module 10
#### The AWS Well-Architected Framework
The AWS Well-Architected Framework helps you understand how to design and operate reliable, secure, efficient, and cost-effective systems in the AWS Cloud. It provides a way for you to consistently measure your architecture against best practices and design principles and identify areas for improvement.

The Well-Architected Framework is based on 5 pillars: 
Operational excellence
Security
Reliability
Performance efficiency
Cost optimization

#### Advantages of cloud computing
Operating in the AWS Cloud offers many benefits over computing in on-premises or hybrid environments. 
In this section, you will learn about six advantages of cloud computing:
Trade upfront expense for variable expense.
Benefit from massive economies of scale.
Stop guessing capacity.
Increase speed and agility.
Stop spending money running and maintaining data centers.
Go global in minutes.
