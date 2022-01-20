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














