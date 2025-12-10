                          LAB 263-Create Subnets and VPC 
**Overview**
In this lab, I deep dived in an environment where I learnt to create a virtual network using Virtual Private Clouds (VPCs) and subnets. The main purpose of this exercise was to fundamentally provide secure, scalable, and well-organized network architectures and manage connectivity between different parts of a network. This lab provided a practical experience on defining subnets, and understanding routing and network isolation in the cloud especially. 

                          Key Objectives
1. Get a good understanding of what a VPC is and the purpose of creating a VPC
2. Configured routing tables to allow or restrict traffic between subnets.
3. Creating multiple subnets in the VPC for varying network segments.
4. Set up internet gateways to provide external connectivity where needed.
5. Verified and validated the VPC and subnet configurations by checking IP ranges and routes.
6. Get an understanding on how network segmentation helps improve security and easier management

                          Process followed- Tasks breakdown
This lab enabled me to get an understanding of the purpose of a VPC and the process it follows when isolating network resources and setting up internet gateways to provide external connectivity when necessary. It was centered around resolving the following scenario that a customer presented which needed a resolution: 

I'm new to AWS,I need help setting up a VPC. Can you please help me through the setup process? I would like to build only the VPC part and would like to make it look something like the following picture. Can you help me ensure  I have around 15,000 private IP addresses in this VPC available?  I would also like the VPC IPv4 CIDR block to be a 192.x.x.x. I don't remember which is a private range though. Can you confirm that? I would also like to allocate at least 50 IP addresses for the public subnet. The customer provided the following diagram to further illustrate what they required:
<img width="1975" height="1376" alt="image" src="https://github.com/user-attachments/assets/0e44ac26-3abe-4025-b58d-921d4fd5e489" />

I then worked out a plan to resolve the customer's issue by working out a plan to break it down into two tasks as follows

**Task 1:Investigate the customer's needs to ensure I provide an appropriate solution**

I kicked off this task by getting a clearer understanding on VPC, subnets, route tables and internet gateway through reasearching and reading up on how each resource works. After the research it seemed logical to start with creating a new VPC and assignin it an IP address range followed by Configuring route tables to make the flow of traffic between subnets flow(or be restricted) much easier. I then set up internet gateways so that external connectivity is provided when necessary which then allowed me to verified and validate the VPC and subnet configurations by checking IP ranges and routes.

<img width="2835" height="1431" alt="image" src="https://github.com/user-attachments/assets/3ef008eb-ef0f-42a0-a350-dec64160735a" />


**Task 2:Send the response to the customer**

I wrote down a report to the cusomer detailing the solutions I came up with in task one and ensured that I simplified the terms and language as the customer did outline that they are new in AWS. 

                          Key Takeaways, difficulties encountered and how I resolved them
   
