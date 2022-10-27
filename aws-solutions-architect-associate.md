# AWS Solutions Architect (Associate)

https://explore.skillbuilder.aws/learn/lp/1044/solutions-architect-learning-plan

## VPC

The Amazon VPC IPv6 CIDR for your subnet range is /64, and the Amazon VPC CIDR range is /56. The local route is used to communicate between subnets inside your Amazon VPC. The default Amazon VPC IPv4 CIDR,172.31.0.0/16, is always the same, and is designed and configured the same too.


 - Create VPC with
	- Region
	- CIDR (i.e. 10.0.0.0/22)
 - Create Internet Gateway
   - VPC id
 - Create Subnets with (i.e. publicSubnet)
   - AZ
   - CIDR (i.e. 10.0.0.0/25)
 - Create new Route table
   - VPC id
 - Create Route (inside route table)
   - Route table id
   - CIDR (i.e. 0.0.0.0/0)
   - Internet Gateway id
 - Associtate Route table
   - Route table id
   - Subnet id

## IAM overview

- **IAM users** represent people and also applications that need access to an AWS account. 
- **IAM groups** are groups of related users, for example, your development team, sysadmins, storage engineers, and the finance team.
- **IAM roles** are used by AWS services. IAM roles can also be used to grant external access to your AWS account along with access to resources and services in the AWS account. For example, an Amazon Elastic Compute Cloud (Amazon EC2) instance inside your AWS account requires programmable access to Amazon CloudWatch, Amazon Simple Storage Service (Amazon S3), and the like.  
- **IAM policies** are used to allow or deny access to AWS services. IAM policies must be attached to an IAM user, an IAM group, or an IAM role. AWS provides preconfigured policies, AWS Managed Policies, that can be assigned as necessary. Customers can also create custom inline policies that allow or deny unique combinations of permissions that best suit the customer's AWS environment. On their own, policies just sit there, to take action they must be attached to a user, a group, or a role.  
- On a high-level overview, **IAM acts as an identity provider (IdP)**, and manages identities inside an AWS account. IAM authenticates these identities facilitating AWS account login activities to be allowed to log into the AWS account, and then authorizes those identities to access resources or deny access to resources based on the policies attached. 

### Network ACLs

Network access control lists (network ACLs) are a type of security filter like a firewall that can filter traffic attempting to enter or leave a subnet. Network ACLs are attached at the subnet level, and by default, a network ACL is created for a default Amazon VPC and is associated with all subnets in your default Amazon VPC. 

### Security groups

Security groups are the other security feature of an Amazon VPC. Unlike network ACLs, security groups are attached to AWS resources, specifically the elastic network interfaces (ENIs), not Amazon VPC subnets. 

**Note:** Security groups are not capable of explicitly blocking traffic. If you need to block a certain IP address or a block of IP addresses, you will require assistance from network ACLs.




