                      LAB 175-Using Autoscaling in AWS

**Overview**

In this lab, the AWS Command Line Interface (AWS CLI) is utilised to create an Amazon Machine Image (AMI),which in simple terms is a template that will be used to launch an Amazon Elastic Compute Cloud (EC2) instance to host a web server. The AMI is then used as the bae for launching a system that scales automatically under a variable load by using Amazon EC2 Auto Scaling. I also created an Elastic Load Balancer (ELB) to distribute the load across EC2 instances created in multiple Availability Zones. The ELB was created with the required auto scaling configuration that ensured that there would be an easy distribution of the load across EC2 instances cretaed in multiple Availability zones. Below is an illustration of the starting architecture and the desired achitecture at the end of the configuration which I achieved once I went through all of the tasks:

<img width="2357" height="1212" alt="image" src="https://github.com/user-attachments/assets/011793c5-9df7-48fb-a57c-26e610da4ad5" />

<img width="2172" height="1244" alt="image" src="https://github.com/user-attachments/assets/bb9c1d6c-0781-42d8-ab0d-7189167f3911" />

                      Key Objectives

  1. The main goal of this lab was to navigate, get accustomed and comfortable with using AWS CLI.
  2. Use an AWS CLI to create an EC2 instance.
  3. Using the AWS CLI to create a new AMI.
  4. Using the new AMI to create an Amazon EC2 template.
  5. Creating an auto scaling environment by creating an Application Load Balancer
  6. Verifying and test the auto scaling configuration
  7. Configure scaling policies by ensuring that the Auto Scaling will scale in and scale out the required number of servers based on a variable load

                   Process followed- Tasks breakdown

**Task 1: Creating a new AMI for Amazon EC2 Auto Scaling**

In task 1, I used the AWS CLI on the Command Host EC2 instance to perform all of these operations, where I launched a new EC2 instance and then created a new AMI based on that running EC2 instance. 

<img width="2864" height="1550" alt="image" src="https://github.com/user-attachments/assets/4734f6e7-e5d0-4aa9-a5bf-816af7e2dfc0" />


**Task 1.1: Connecting to the Command Host instance and configuring the AWS CLI**

Firstly, I navigated through the AWS Management Console and connected to the Command Host EC2 instance. The Command Host instance has to be running is the us-west-2 Region, so i ran the curl http command to verify and the output confirmed that it was indeed in that region so I used the region's information going forward. I then ran the "aws configure" command to update the CLI with correct credentials such as Access Key ID, AWS Secret Access Key, Default region name which I entered the us-west-2 region, and finally the Default output format which I entered json for access to run the scripts for the next tasks.

**Task 1.2: Creating a new EC2 Instance and a Custom AMI**

In this task, the main outcome was to use the AWS CLI to create a new instance that hosts a web server. I kicked off this task by inspecting the UserData.txt script that was installed as part of the Command Host instance creation, this script performs a number ofautomation and initialization tasks, including updating all installed software and eliminating the need for manual setup. I then ran a script to create a new EC2 instance which required the following information: KEYNAME, AMIID, HTTPACCESS, and SUBNETID which generated the instanceID which enabled another script to initialize a new web server.Installing the web server required about 5-10 minutes and then I moved to the last step of this task which where I used the ec2 create-image command to restart the current instance before creating the AMI to ensure the integrity of the image on the file system.

**Task 2: Creating an auto scaling environment**
Firstly I created a load balancer that pools groups of EC2 instances under a single Domain Name System (DNS) address and uses auto scaling to create EC2 instances in a dynamically scalable pool based of on the image that you created in the previous task. Finally,I enabled additional health checks on the load balancer and I created a set of alarms that scale in or out the number of instances in the load balancer group whenever the CPU performance of any machine within the group exceeds or falls below a set of specified thresholds.

**Task 2.1: Creating an Application Load Balancer and a launch template for the AutoScaling group**

In this section, I created a load balancer that can manage and balance traffic in and out of multiple EC2 instances and Availability Zones using the AWS Managemant Console. The type of ELB I created is an Application Load Balancer called WebServerELB with an attached Security and target group. The next step involved creating a launch template for my Auto Scaling group which I will create in the next task, which is a template that an Auto Scaling group uses to launch EC2 instances. I created the template on the AWS Management Console as well and i had to specify information for the instances, such as the AMI, instance type, key pair, security group, and disks.

<img width="2880" height="1447" alt="image" src="https://github.com/user-attachments/assets/f65b91f5-e972-4f01-ae9a-a202c71fca4a" />

<img width="2878" height="1374" alt="image" src="https://github.com/user-attachments/assets/26b1b707-8c00-4e14-9682-d6a9235fc42f" />



**Task 2.2: Creating an Auto Scaling group**
This is where I used the launch template I create to create an Auto Scaling group with enabled Elastic Load Balancing health checks, and for a Target value of 50 which tells the auto scaling to maintain an average CPU utilization across all instances of 50 percent. Auto scaling will automatically increase or decrease the capacity as required to keep the metric as close to the specified target value as possible. It uses a fluctuating load pattern to adjust the fluctuations in the metric.

**Task 3: Verifying and testing the auto scaling configuration**
In this final task, I started by verifying that both the auto scaling configuration and the load balancer are working both individually and together by accessing a pre-installed script on one of your servers that will consume CPU cycles, which will then invoke the scale out alarm if the traffic exceeds the target value. Lastly, I tested auto scaling functionality by allowing the web application access through the load balancer and the doing the application stress in the background which invoked the scale-up policy as a response after Amazon CloudWatch detected that the average CPU utilization of your Auto Scaling group exceeded 50 percent.

                  Key Takeaways, difficulties encountered and how I resolved them












