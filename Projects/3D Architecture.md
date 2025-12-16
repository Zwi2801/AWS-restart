             Project 2: 3D E-Commerce Platform Architecture

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/daa833fe-7218-4d89-9bd8-374189363870" />

**Project Overview**

This was also a group project where a group of 5 members were tasked with explaining the AWS architecture designed to support a next-generation 3D e-commerce web application. The platform must be globally available, highly scalable, secure, fast, and cost-efficient while rendering 3D models to millions of users. Below is a breakdown of the AWS services selected, why they were chosen, and how the final solution meets all business and technical requirements.

Our team took on the role of Cloud Practitioners and designed an AWS architecture that meets both business needs and technical requirements. This included selecting appropriate AWS services for storage, compute, networking, security, scalability, and monitoring, and ensuring the system can handle unpredictable traffic spikes without sacrificing performance or reliability.

                                        Key Project Objectives

1. Design a highly available and fault-tolerant architecture that ensures that the platform is available 24/7
2. To learn more about AWS services that can scale automatically to handle sudden increases in global user traffic
3. Ensure that the platform will have high performance, particularly for delivering and rendering 3D content with low latency
4. Apply AWS security best practices to protect customer data and application resources
5. To put measure in place to ensure that the architecture optimizes costs by using managed services, auto scaling, and monitoring tools
6. Clearly explain architectural decisions and how each AWS service supports the system’s requirements

                                    Core AWS services selected and why we chose them for the Architecture


A. **Amazon S3 – Storage for 3D Assets**

Amazon S3 is used to store all 3D product models, textures, images, and static website assets.

The reasons for selection are as follows:

    • Highly durable (11 9’s durability)
    • Scales automatically for millions of asset requests
    • Integrates directly with CloudFront for low-latency delivery
    • Cost-effective object storage

B. **Amazon CloudFront – Global CDN for Content Delivery**

CloudFront caches 3D assets, images, and website static files across global edge locations.

The reasons for selection are as follows:

    • Reduces latency for global users
    • Protects the backend using AWS Shield and WAF integration
    • Improves performance for heavy 3D content
    • Decreases S3 and backend load

C. **EC2 Auto Scaling / AWS Lambda – Backend Compute**

The backend API can be built using either:
    
1. EC2 Auto Scaling for applications requiring long-running processes

2. AWS Lambda for event-driven API logic (serverless)

The reasons for selection are as follows:

    • Supports unpredictable spikes in traffic
    • Load adjusts automatically up or down
    • Reduces cost by only paying for what is used
    • Lambda improves scalability and removes server maintenance

D. **Amazon RDS / DynamoDB – User & Product Database**

The architecture uses:

    • RDS (MySQL/PostgreSQL) for structured data like orders, users, and transactions
    
    • DynamoDB for fast product lookups and real-time inventory access

The reasons for selection are as follows:

    • RDS provides strong consistency & relational queries
    • DynamoDB offers millisecond latency for product browsing
    • Both scale easily and integrate with Lambda/EC2

E. **Elastic Load Balancer (ELB) – Traffic Distribution**

The ALB (Application Load Balancer) distributes user requests across EC2 instances or Lambda functions.

The reasons for selection are as follows:

    • Provides health checks and fault tolerance
    • Supports path-based routing (important for API and asset endpoints)
    • Ensures high availability and automatic failover

F. **Amazon Route 53 – Domain & DNS Management**

Route 53 manages the domain and routes traffic to CloudFront or ELB.

The reasons for selection are as follows:
   
    • Highly available DNS service
    • Supports health checks and routing policies
    • Integrates well with CloudFront for global performance

G. CloudWatch & Trusted Advisor – Monitoring & Optimization

These services monitor logs, application performance, and system metrics.

The reasons for selection are as follows:

  1. CloudWatch provides real-time alerts, metrics, and dashboards
  2. Trusted Advisor helps reduce cost, improve security, and detect misconfigurations
  3.  Ensures the platform remains reliable and optimized

              Meeting Key System Requirements

1. **High Availability**

    • Route 53 + CloudFront provide multi-region distribution
   
    • ELB supports auto failover
   
    • EC2 Auto Scaling ensures instances are replaced automatically
   
    • S3 provides 99.99% availability for assets

3. **Scalability**

    • Auto Scaling handles unpredictable traffic spikes
   
    • DynamoDB offers on-demand scaling
   
    • CloudFront caches content globally, reducing backend load
   
    • Lambda automatically scales to thousands of requests per second
   

5. **Performance**

    • CloudFront drastically reduces latency for 3D models
   
    • DynamoDB provides single-digit millisecond reads
   
    • EC2 instances or Lambda functions process API requests quickly
   
    • S3 ensures fast retrieval for large 3D assets

7. **Security**

    • AWS WAF on CloudFront blocks malicious traffic
   
    • IAM roles restrict resource access
   
    • Security groups protect EC2 instances
   
    • RDS has encryption, backups, and Multi-AZ deployment
   
    • S3 supports bucket policies and encryption

9. **Cost Optimization**

    • S3 and CloudFront reduce expensive compute usage
   
    • Auto Scaling prevents over-provisioning
   
    • Lambda eliminates server idle cost
   
    • Trusted Advisor recommends savings opportunities
   
    • DynamoDB on-demand mode reduces unnecessary database cost
              




