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
