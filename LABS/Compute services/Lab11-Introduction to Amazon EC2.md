                  LAB 11- Introduction to Amazon EC2

**Overview**

This lab provided in-depth and practicel experience with Amazon Elastic Compute Cloud (Amazon EC2), a core AWS service used to create and manage virtual servers in the cloud. Amazon EC2 allows users to quickly launch computing resources without friction, adjust capacity as needed, monitor performance, and only pay for what they use.

Throughout the lab, I launched an EC2 instance configured as a simple web server, monitored its health and performance, adjusted security settings to allow web traffic to flow freely., I then resized the instance and storage to demonstrate scalability, tested termination protection, and finally terminated the instance. This lab demonstrated how EC2 supports flexibility, scalability, and secure cloud-based computing.

<img width="772" height="629" alt="image" src="https://github.com/user-attachments/assets/5d8a16e3-4bb7-4158-833c-c2d0eb72126a" />

                  Key Objectives

1. Launch an Amazon EC2 instance enabled with termination protection 
2. Deploy a basic web server using a user data script
3. Monitor the EC2 instance using status checks and CloudWatch metrics
4. Modify a security group to allow HTTP access
5. Resize the EC2 instance and its EBS storage volume
6. Test and understand termination protection
7. Safely terminate an EC2 instance

          Process followed- Tasks breakdown

   **Task1- Launching your EC2 instance**

I used the AWS Management Console to create the EC2 instance, so I kicked off this lab by navigating to the Services menu on the console, then clicked on EC2 and opened the EC2 Dashboard. I selected Launch instance and I named the instance Web Server, creating a Name tag for easy identification.

Some of the Key configuration choices in addition to the Instance name included:

1. **AMI:** Amazon Linux 2023 (default)
2. **Instance Type:** t3.micro
3. **Key Pair:** Proceeded without a key pair (not required for this lab
4. **VPC:** Lab VPC
5. **Security Group:** Custom security group with no inbound rules initially
6. **Termination Protection:** Enabled

<img width="1128" height="495" alt="image" src="https://github.com/user-attachments/assets/4cb84fad-d563-4959-83b9-8474284b4d50" />


**Task 2- Monitor Your Instance**

With the EC2 running and in the available state, I reviewed the following:

1. **Status Checks:** - I checked the status of the instance using the Status Checks tab to confirm system and instance reachability.
2. **Monitoring:** - I explored the Monitoring tab to view Amazon CloudWatch metrics.
3. **Get Instance Screenshot** - I used Get Instance Screenshot to view the instance console output.

**Task 3: Updating the Security Group and Accessing the Web Server**

I attempted to access the web server by copying the instance’s Public IPv4 address on a web browser, but I couldnt access it because I confirmed access failed because HTTP traffic was not allowed, specifically inbound HTTP traffic (port 80) was not permitted by the security group.

The steps I followed for the resolution are: I updated the security group inbound rules to allow:
Type: HTTP (Port 80)
Source: Anywhere-IPv4

I refreshed the browser and successfully viewed the web page after saving the rule, and it showed the message below:

<img width="1138" height="236" alt="image" src="https://github.com/user-attachments/assets/be7f4aa6-7390-4cf1-8999-05134ab52b5b" />

**Task 4- Resize Your Instance: Instance Type and EBS Volume**

In this task, i followed the following steps to resize my instance:

1. Stopping the Instance- I stopped the EC2 instance to allow configuration changes.
2. Changing the Instance Type- I changed the instance type from t3.micro to t3.small, doubling the available memory.
3. Resizing the EBS Volume- I increased the root EBS volume size from 8 GiB to 10 GiB.
4. Restarting the Instance- I restarted the instance to apply the new configuration.

<img width="1328" height="730" alt="image" src="https://github.com/user-attachments/assets/c87c6ef8-8baf-4f9b-a065-191f4330a238" />

**Task 5- Test Termination Protection**

It is possible to delete your instance when you no longer need it which is referred to as terminating your instance. You cannot connect to or restart an instance after it has been terminated. I initially attempted to terminate the instance, but the termination failed, confirming that termination protection was working correctly. I then disabled termination protection in the instance settings then I successfully terminated the instance only after I disabled the termination protection. The instance was permanently deleted together with ts associated resources.
<img width="1359" height="731" alt="image" src="https://github.com/user-attachments/assets/bc732813-304b-4065-86d9-b4c41a834805" />





















