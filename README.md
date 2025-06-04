# AWS-VPC-NAT-EC2-HandsOn
Use NAT Gateway to enable internet access for instances in a private subnet within Amazon Web Services (AWS)

## **Project Overview**
This hands-on lab demonstrates AWS networking fundamentals:
- ✅ **VPC Creation** (10.0.0.0/16)
- ✅ **Public Subnet** (10.0.0.0/24) with auto-assign public IP
- ✅ **Private Subnet** (10.0.1.0/24) with no direct internet access
- ✅ **Internet Gateway** for public subnet
- ✅ **NAT Gateway** for private subnet internet access
- ✅ **EC2 Instances** in both subnets (public & private)
- ✅ **SSH Verification** of internet access
  
## **Steps Executed**

### **1. VPC & Subnet Setup**
- Created VPC (`10.0.0.0/16`)
- Public Subnet (`10.0.0.0/24`) with auto-assign public IPv4
- Private Subnet (`10.0.1.0/24`)

### **2. Internet Gateway & Routing**
- Attached an **Internet Gateway (IGW)** to the VPC
- Created a **public route table** with a route to `0.0.0.0/0` via IGW
- Associated the public subnet with this route table

### **3. EC2 Instances**
- Launched a **public EC2 instance** (auto-assign public IP enabled)
- Launched a **private EC2 instance** (no public IP)
- Used the same **key pair** and **security group** for both

### **4. NAT Gateway Setup**
- Created a **NAT Gateway** in the public subnet
- Allocated an **Elastic IP** for NAT
- Updated the **private route table** to route `0.0.0.0/0` via NAT Gateway

### **5. Verification**
- **Public Instance**: Had internet access (`yum update` worked)
- **Private Instance**: Initially no internet, but worked after NAT Gateway

