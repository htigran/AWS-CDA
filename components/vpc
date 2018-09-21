##Virtual Private Cloud - VPC
- creates a virtual network. It resembles a private datacenter or a private corporate network
- If you delete default VPC, the only way you can get it back is by contacting AWS
- default vpc is created upon instance creation. Now by default all ec2 is launched under a vpc.dfault vpc is connected to internet by default. It replaces ec2 classic functionality
- Instances in VPC behave as if they were on the same private network
- VPCs can be peered. Peering is in a star config, ie 1 central vpc
- VPC peering can be done with vpc in the same region only
- no additional charges for vpc, underlying services are charged as usual
- size of vpc between /28 (14 Ip addresses) and /16 
- to change vpc size, you have to terminate and startover
- amazon vpc does not support multicast and broadcast
- you can assign multiple ip addresses 

- instances without Elastic IP address can access internet in two ways
  * via a NAT instance. they can use EIP of nat instance. Nat allows outbound connections, but does not allow internet to initiate connection to these machines
  * for vpc with hardware vpn, via virtual private gateway to existing data center

- components of VPC
  * VPC
  * subnet
  * internet gateway
  * NAT instance: an ec2 instance that provides port address translation for non-eip instances to access internet via the gateway
  * hardware VPN
  * virtual private gateway : amazon side of a vpn connection
  * customer gateway : customer side of vpn connection
  * router to interconnect subnets and direct traffic between internet gateway , virtual private gateway, nat and subnets 

- Benefits of VPC
  * Ability to launch instances into a subnet (range of ip)
  * Ability to define custom ip address ranges inside each subnet
  * Ability to configure route tables between subnets
  * ability to configure internet gateways and attach them to subnets
  * create layered network of resources


- VPC limits
  * 5 VPC per region, more on request
  * 5 internet gateways per account, equal to VPC limit
  * 5 virtual private gateways and 5 customer gateways
  * 1 internet gateway attached to a subnet at a time
  * 1 subnet can only be in 1 availability zone
  * 50 customer gateways per region
  * 50 VPN connections per region
  * 200 route tables per region
  * 200 subnets per amazon vpc
  * 5 elastic IP addresses
  * 100 security groups
  * 50 rules per security group

- VPC via public subnet is accessible over internet. VPC via private subnet is not accessible over internet, atleast not without NAT (network address translation)
- CIDR: Classless Inter Domain routing: specifies what your continuous IP address range is
- You cannot create a VPC larger than /16
- Tenancy: Default vs dedicated. Default is shared with others, dedicated means hardware is dediacated for you. the underlying hypervisor is dedicated in dedicated tenancy
- if EC2 choose a dedicated vpc, automatically EC2 will be created as a dedicated. similar for any resouce which choosed a dedicated vpc
- You can create subnets in different availability zones for highly available architecture


- A route table is automatically provisioned when you create a VPC
- You can create a route table, and assign it to a subnet
- Each subnet can be associated with only 1 route table

- Internet Gateway
  * a gateway out to internet. 
  * You can only have 1 internet gateway per VPC
  * Internet gateway needs to be attached to a subnet
  * EC2 do not automatically get connection to internet. You need to connect the E2 via Elastic Ip or Elastic load balancer

- Steps to get internet
  * Create internet gateway
  * Attach internet gateway to vpc
  * create a new route table and attach it to a subnet
  * Edit route table and attach it to internet gateway
  * Create elastic ip or elb and attach it to ec2 created under the vpc


- under aws, you can have 251 ip addresses, opposed to industry standard 254 as they reserve a few 
- EC2 launched under a dedicated subnet will not have a public DNS or a public IP The only way to get a public IP is by creating a gateway and : assigning IP addresses manually or using ELB groups
- Even if you attach a public IP address , you still need a route to the internet to ssh in or for access over internet
- You can ssh into one EC2 and then to the other EC2 without public address from within as they are all members of same subnet. So you can connect to public instance first and then to the internal instances from within the public instance

- Each subnet can only be associated with one route table

- Access Control Layer ACL
  * ACL allows to create firewall rules that deny or allow traffic at subnet / network level. This is tighter than security group
  * ACL are stateless filtering
  * Security group sits in front of EC2 instance and allow or deny traffic at EC2 level


- NAT instance can make private machines inside vpc access internet, however the machines are not publically accesible
