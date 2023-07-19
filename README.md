# ELB-ASG
Classic Elastic Load Balancer &amp; Auto Scaling Web Servers

Using the AWS Web Console, created an Internet-facing Classic Elastic Load Balancer using Auto Scaling Group with a Launch Configuration that provision and configure Amazon Linux Apache Web Servers on t2.micro instances. 

The I.A.A.C file is attached.

## Step 1:Launch Templates ## 
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

## Step 2:Auto Scaling Groups ##

The ASG continuously monitors the demand on the web servers and automatically adjusts the number of instances based on predefined scaling policies. This ensures that there are enough instances available to handle increased traffic and maintain a consistent level of performance and availability. Additionally, the ASG helps with fault tolerance by replacing any unhealthy or failed instances, ensuring the web application's or website's continuous operation. By utilizing the Auto Scaling Group, we can effectively manage the scaling and availability of the infrastructure supporting the Load Balancer, providing a reliable and scalable solution for handling user requests.

The Configuration:
- Name
- Launch template (we made above)
  - version-  Each time you make changes to the launch template and save it, a new version is created. You can choose whether you want the Default, Latest or numbered version.
- Network
   - Multi subnets in multi AZ for high availability.
- Load Balancing (will create and attach later)
-  Group Size
   - How many Min, Max and Desired instances need to be running in High-Low Demand?

   ![image](https://github.com/liormat401/ELB-ASG/assets/126070709/f8993182-bd2a-4be8-9ddf-2c7dc54ae8a2)
   *Review*

   ![image](https://github.com/liormat401/ELB-ASG/assets/126070709/181a469b-8bd5-4ff6-b393-50830ad5a314)
   *Review*

   ## Step 3:Load Balancer ##
   A load balancer is essential for distributing incoming network traffic across multiple servers or instances, providing several benefits for web applications or websites.
   There is 4 types of LB:
- Classic Load Balancer (CLB):
  
   The traditional load balancer offered by AWS. It operates at the transport layer (Layer 4) and can distribute traffic between multiple servers based on network-level information such as IP addresses and ports.

- Application Load Balancer (ALB):
  
     Operates at the application layer (Layer 7) and provides advanced features such as content-based routing, request routing based on URL paths, and support for HTTP/2 and WebSockets. It allows more granular control over traffic distribution and is suitable for modern web applications.

- Network Load Balancer (NLB):
  
    A high-performance load balancer that operates at the transport layer (Layer 4). It is designed to handle extreme levels of traffic and offers features like static IP support, high throughput, and low latency. NLB is commonly used for TCP/UDP-based applications.

- Gateway Load Balancer (GWLB):
  
    A new type introduced by AWS. It is designed to distribute traffic to virtual appliances deployed in the VPC. It operates at the network layer and can route traffic based on IP protocols and ports. The Gateway Load Balancer is particularly useful for scenarios where advanced networking capabilities or third-party virtual appliances, such as firewalls or VPN concentrators, need to be integrated into your network architecture.

  
![image](https://github.com/liormat401/ELB-ASG/assets/126070709/4f93da83-724d-4c0c-9f56-a64b07256fd2)

Let's create the Target Group.

  ## Step 4:Target Group ##
  The load balancer routes requests to the targets within the target group and conducts health checks on those targets.
  Configuration:
  - Target type (this case-Instances)
  - Name
  - VPC
  - Protocol
  - Register Targets
 (Not relevant to Classic LB)

Add the target group in the Listeners and Routing section and create the LB
![image](https://github.com/liormat401/ELB-ASG/assets/126070709/860aa6da-3d62-48e2-93a3-4e705d43fb9f)

 
 ## Step 5: Attach the Load Balancer to the AutoScale Group:##
    
    ![image](https://github.com/liormat401/ELB-ASG/assets/126070709/d858cc41-c05d-4659-9ac4-17f73ee1691e)

 
  

    

  


  












**Special Thanks:**

https://www.youtube.com/watch?v=AmQeeB4ygZc&ab_channel=SamMeech-Ward

Helped me understand the creating process.
