# ELB-ASG
Classic Elastic Load Balancer &amp; Auto Scaling Web Servers

Using the AWS Web Console, created an Internet-facing Classic Elastic Load Balancer using Auto Scaling Group with a Launch Configuration that provision and configure Amazon Linux Apache Web Servers on t2.micro instances. 

The I.A.A.C file is attached.

## Step 1:Template Launch ## 
The Launch Configuration acts as a blueprint for creating the instances required for the Auto Scaling Group and Load Balancer setup.
This is a short configuration-
- Name
- Description
- AMI
- Instance Type
- Key pair
- Security Group
- User Data
  
All other remained in default.
![image](https://github.com/liormat401/ELB-ASG/assets/126070709/71a9a06a-06d0-4ec3-9937-c96a0b87dbd9)
*User Data from AWS Lab. could be any User Data*

![image](https://github.com/liormat401/ELB-ASG/assets/126070709/4c49dcff-dc6f-4bc6-80f8-0f0f9fe3ed49)
*Configuration Summary*










**Special Thanks:**

https://www.youtube.com/watch?v=AmQeeB4ygZc&ab_channel=SamMeech-Ward

Helped me understand the creating process.
