# AWS: Ping google.com from private subnet through Jumb Box

## Objective:  
Create 2 subnets, private and public, in the same VPC.   
Connect private subnet through Jumb box in public subnet  
then  ping google.com from instance in private subnet through NAT instance instance in public subnet.

![](Images/AWS.png)

## Step Overview:
1. Create VPC
2. Create 2 subnets, private and public  
3. Create Internet Gateways 
4. Create 2 Route Tables  
   * One for Private subnet  
   * One for Public subnet
5. Create 3 Security Groups for each instances
6. Create 3 Instances  
   * Place 2 instances in public subnet. Name them as Jumb Box and NAT Instance. 
   * Place 1 instance in private subnet with the name Final Instance.  
7. Associate Elastic IPs to instances in public subnet    
8. Test connection (Using Putty and Pageant)
   * Connect to Jump Box  
   * From Jump Box connect to Final Instance in private subnet  
   * ping google.com from Final Instance (through NAT Instance)

## Step 1: Create VPC  
1. Go to AWS Management Console  
2. Find Services/ VPC  
3. Your VPCs/ Create VPC by using IPv4 CIDR block  (e.g. 10.0.0.0/16 ) 

![](Images/CIDR_BLOCK_16.png)

## Step 2: Create 2 subnets, private and public  
1. Go to Subnets/ Create subnet
2. Choose VPC that was created from the previous step
3. Set 2 differents IPv4 CIDR block for each subnets  (e.g. 10.0.0.0/24 and 10.0.1.0/24 ) 

![](Images/SubNet1.png)
![](Images/SubNet2.png)



