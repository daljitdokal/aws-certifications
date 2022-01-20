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








