# Creating a Virtual Private Cloud (VPC)

> Creating a Virtual Private Cloud (VPC) with public and private subnets, 
> an internet gateway for public subnets, and a NAT gateway for private subnets
> involves several steps. Below are the detailed steps to achieve this
> on a cloud platform like Amazon Web Services (AWS):

![image](https://github.com/iasman312/vpc_repo/assets/31188447/17828c92-fc6d-4d7e-8169-53ec88162b7b)

#### Navigate to VPC Dashboard: 
Once logged in, navigate to the VPC Dashboard.

#### Create a VPC:
1. Click on "Create VPC".
2. Enter a name for the VPC.
3. Enter the desired CIDR block for your VPC (e.g., 10.0.0.0/16).
4. Configure any additional settings as needed (e.g., IPv6 CIDR block).
5. Click "Create VPC".

#### Create Subnets:
1. After creating the VPC, navigate to the "Subnets" section.
2. Click on "Create subnet".
3. Enter a name for the subnet and select the VPC you created earlier.
4. Choose the availability zone for the subnet.
5. Enter the CIDR block for the subnet (e.g., 10.0.1.0/24 for public, 10.0.16.0/24 for private).
6. Repeat this step to create both public and private subnets.

#### Create an Internet Gateway (IGW):
1. Navigate to the "Internet Gateways" section.
2. Click on "Create internet gateway".
3. Give the internet gateway a name.
4. Select the newly created internet gateway and attach it to your VPC.

#### Create Route Tables:
1. Navigate to the "Route Tables" section.
2. Create two route tables, one for public and one for private.
3. Select the public subnet for the public route table and the private subnet for the private route table.
4. Select the public route table and add a route with destination 0.0.0.0/0 and target as the internet gateway created earlier.
5. Select the private route table and leave it empty for now.

#### Create a NAT Gateway:
1. Navigate to the "NAT Gateways" section.
2. Click on "Create NAT gateway".
3. Select the public subnet and create an Elastic IP address.
4. Create the NAT gateway.
   
#### Update Private Route Table:
1. Go back to the "Route Tables" section.
2. Edit the private route table.
3. Add a route with destination 0.0.0.0/0 and target as the NAT gateway created earlier.


