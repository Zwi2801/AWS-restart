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
