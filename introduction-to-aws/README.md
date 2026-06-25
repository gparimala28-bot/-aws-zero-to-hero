# AWS Fundamentals

## What is AWS?

Amazon Web Services (AWS) is Amazon's cloud computing platform that offers a wide range of on-demand services, including:

* Compute resources
* Storage solutions
* Databases
* Networking services
* Security tools
* Monitoring and management services

## Why AWS?

AWS is one of the world's leading cloud platforms, trusted by startups, enterprises, and government organizations. It enables businesses to build, deploy, and scale applications quickly without investing in physical infrastructure.

### Key Advantages

- Pay only for what you use.
- Scale resources up or down based on demand.
- Access a global network of data centers.
- Benefit from enterprise-grade security and compliance.
- Eliminate upfront hardware and maintenance costs.

# Core AWS Services

AWS services are categorized into three cloud service models based on the level of management provided by AWS: **Infrastructure as a Service (IaaS), Platform as a Service (PaaS), and Software as a Service (SaaS).**

## Infrastructure as a Service (IaaS)

IaaS provides the core infrastructure required to build cloud applications. AWS manages the physical hardware, while users are responsible for configuring operating systems, applications, networking, and storage.

### Compute Services

#### Amazon EC2 (Elastic Compute Cloud)

* Launch scalable virtual machines in the cloud.
* Suitable for hosting websites, applications, databases, and enterprise workloads.

#### Amazon EC2 Auto Scaling
* Automatically adjusts the number of EC2 instances based on traffic or workload.
* Helps maintain application availability while optimizing infrastructure costs.

#### Elastic Load Balancing (ELB)
* Distributes incoming application traffic across multiple EC2 instances.
* Improves fault tolerance, scalability, and application availability.

### Storage Services

#### Amazon S3 (Simple Storage Service)

* Scalable object storage designed for storing files, backups, images, videos, and application data.
* Provides high durability, availability, versioning, lifecycle management, and secure access.

#### Amazon EBS (Elastic Block Store)

* Persistent block storage designed specifically for EC2 instances.
* Ideal for operating systems, databases, and applications requiring fast, low-latency disk performance.

#### Amazon EFS (Elastic File System)

* Fully managed shared file storage that can be mounted across multiple EC2 instances.
* Automatically expands and shrinks as storage requirements change.

#### Amazon S3 Glacier

* Low-cost archival storage for long-term data retention.
* Best suited for backups, compliance records, and infrequently accessed data.

### Networking Services

#### Amazon VPC (Virtual Private Cloud)

* Create isolated virtual networks within AWS.
* Configure subnets, routing tables, internet gateways, and security groups to control network traffic.

#### AWS Direct Connect

* Establishes a dedicated private connection between on-premises infrastructure and AWS.
* Delivers lower latency, higher bandwidth, and more reliable connectivity than public internet connections.


### Security & Identity Services

#### AWS IAM (Identity and Access Management)

* Securely manage users, groups, roles, and permissions.
* Control access to AWS resources using fine-grained security policies.

#### AWS KMS (Key Management Service)

* Create and manage encryption keys for protecting sensitive information.
* Integrates seamlessly with many AWS services to simplify data encryption.

## Platform as a Service (PaaS)

PaaS provides a managed platform for building, deploying, and scaling applications without managing the underlying infrastructure.

### Compute Services

#### AWS Lambda

* Execute code without provisioning or managing servers.
* Automatically scales based on incoming requests and follows a pay-per-use pricing model.

#### AWS Elastic Beanstalk

* Deploy web applications quickly without managing infrastructure.
* Automatically provisions resources, performs scaling, monitors application health, and handles updates.

### Container Services

#### Amazon Elastic Container Service (ECS)

* Fully managed container orchestration service for Docker applications.
* Simplifies deploying, managing, and scaling containerized workloads.

### Database Services

#### Amazon RDS (Relational Database Service)

* Managed relational database service supporting MySQL, PostgreSQL, MariaDB, Oracle, and SQL Server.
* Automates backups, software patching, scaling, and high availability.

#### Amazon DynamoDB

* Fully managed NoSQL database designed for high performance and low latency.
* Automatically scales to support applications with unpredictable workloads.

#### Amazon ElastiCache

* In-memory caching service supporting Redis and Memcached.
* Improves application speed by reducing database queries and delivering faster response times.

#### Amazon Redshift

* Fully managed cloud data warehouse built for analytics and business intelligence.
* Enables fast querying of large datasets using standard SQL.

### Networking Services

#### Amazon Route 53

* Highly available Domain Name System (DNS) and domain registration service.
* Routes user requests efficiently while supporting health checks and intelligent traffic routing.

#### Amazon CloudFront

* Global Content Delivery Network (CDN) that distributes websites, APIs, videos, and static content with low latency.
* Uses AWS edge locations to cache content closer to users for improved performance.

### Security Services

#### AWS WAF (Web Application Firewall)

* Protect web applications against common attacks such as SQL injection and cross-site scripting (XSS).
* Filters malicious requests before they reach applications.

#### AWS Shield

* Managed Distributed Denial-of-Service (DDoS) protection service.
* Helps safeguard applications against network and application-layer attacks.

### Monitoring & Management Services

#### Amazon CloudWatch

* Collects logs, metrics, and performance data from AWS resources.
* Supports monitoring, alerting, dashboards, and automated responses.

#### AWS CloudTrail

* Records API activity and account events for auditing and compliance.
* Helps monitor user actions and investigate security incidents.

#### AWS CloudFormation

* Automates infrastructure deployment using Infrastructure as Code (IaC).
* Creates and manages AWS resources through reusable templates.

#### AWS Systems Manager

* Centralized management service for AWS resources.
* Simplifies patching, automation, configuration management, and remote administration.

## Software as a Service (SaaS)

SaaS delivers fully managed software applications that users can access through a web browser or client application without managing the underlying infrastructure.

### Business Productivity Services

#### Amazon WorkSpaces

* Cloud-based Desktop-as-a-Service (DaaS) solution.
* Allows organizations to provision secure Windows or Linux virtual desktops on demand.

#### Amazon WorkDocs

* Secure document storage and collaboration platform.
* Enables teams to create, edit, share, and manage files from anywhere.

#### Amazon WorkMail

* Managed business email and calendaring service.
* Works with popular email clients while providing enterprise-grade security.

#### Amazon Chime

* Communication and collaboration platform for meetings, messaging, voice calls, and video conferencing.
* Supports secure collaboration across desktop and mobile devices.

## AWS Global Infrastructure

### Regions

Regions are geographically separated AWS locations where services are hosted.

**Benefits:**

* Reduced latency
* Regulatory compliance
* Regional redundancy
* Disaster recovery planning

### Availability Zones (AZs)

Availability Zones are isolated data centers within a region.

**Benefits:**

* High availability
* Fault tolerance
* Business continuity
* Reliable application deployment

### Edge Locations

Edge Locations cache content closer to end users.

**Benefits:**

* Faster content delivery
* Reduced latency
* Improved application performance
* Enhanced security protection

## AWS Partitions

AWS infrastructure is divided into independent partitions:

| Partition    | Purpose                                 |
| ------------ | --------------------------------------- |
| AWS Standard | Global commercial workloads             |
| AWS China    | Compliance with Chinese regulations     |
| AWS GovCloud | U.S. government and regulated workloads |

Each partition operates independently with separate resources, credentials, and compliance requirements.

## Getting Started with AWS

### AWS Free Tier

The AWS Free Tier allows new users to explore cloud services at no cost within defined usage limits.

Common Free Tier offerings include:

* EC2 virtual machines
* S3 object storage
* RDS databases
* DynamoDB storage

### Account Creation Steps

1. Create an AWS account.
2. Verify identity and payment details.
3. Select the Basic Support Plan.
4. Access the AWS Management Console.

## AWS CLI Setup

AWS Command Line Interface (CLI) enables management of AWS resources directly from your local machine.

### Prerequisites

* AWS account
* Internet connection
* Administrative system access

### Installation

AWS CLI is available for:

* Windows
* macOS
* Linux

### Configuration

Configure the CLI using:

```bash
aws configure
```
Provide:

* Access Key ID
* Secret Access Key
* Default Region
* Output Format

Verify installation:

```bash
aws sts get-caller-identity
```

## Multiple Account Management

AWS CLI supports named profiles for managing multiple AWS accounts.

Example:

```bash
aws configure --profile work
aws configure --profile personal
```
Use a specific profile:

```bash
aws s3 ls --profile work
```
## Best Practices

* Deploy applications across multiple Availability Zones.
* Select regions based on performance, compliance, and cost.
* Secure credentials and never expose access keys.
* Implement monitoring and logging for operational visibility.
* Use Edge Locations for global content delivery.

## Key Takeaways

* AWS provides a scalable and secure cloud platform.
* Regions, Availability Zones, and Edge Locations form the foundation of AWS infrastructure.
* Core services span compute, storage, networking, databases, and security.
* AWS CLI simplifies cloud resource management from local environments.
* Understanding AWS architecture is essential for building resilient cloud solutions.
