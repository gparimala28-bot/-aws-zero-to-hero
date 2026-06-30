# AWS EC2

## What is EC2?

Amazon EC2 (Elastic Compute Cloud) is an AWS service that lets you create and manage virtual servers, called **EC2 instances**, in the cloud.

Instead of buying and maintaining physical hardware, you can launch a virtual machine whenever you need one and only pay for the resources you use.

The word **Elastic** means that you can easily increase or decrease your computing resources based on your application's needs. This flexibility allows your infrastructure to grow or shrink without purchasing additional physical hardware.

## Why do we use EC2?

EC2 is commonly used to:

- Host websites and web applications
- Run software and backend services
- Test and develop applications
- Process and store application data
- Scale computing resources based on demand

## What is an EC2 Instance?

An EC2 Instance is a virtual computer that runs in the AWS cloud.

Like a physical computer, it includes:

- CPU (processing power)
- Memory (RAM)
- Storage
- An operating system such as Linux or Windows

You can create, start, stop, restart, or terminate an instance whenever needed.

## Key Features of Amazon EC2

- **Scalable:** Increase or decrease computing resources as your application grows.
- **Multiple Instance Types:** Choose an instance based on your workload, such as general-purpose, compute-optimized, or memory-optimized.
- **Secure:** Protect your instance using Security Groups and Key Pairs.
- **Cost-Effective:** Pay only for the compute resources you use.
- **AWS Integration:** Easily connect EC2 with other AWS services like S3, IAM, RDS, and VPC.

## AWS Regions and Availability Zones

AWS has data centers located around the world.

### Region

A **Region** is a geographical location where AWS has multiple data centers.

Examples:

- us-east-1 (Northern Virginia)
- us-west-2 (Oregon)
- eu-west-1 (Ireland)

### Availability Zone (AZ)

Each Region contains multiple **Availability Zones (AZs)**.

An Availability Zone is one or more physically separate data centers designed to provide high availability and fault tolerance.

Example:

```
Region (us-east-1)

├── Availability Zone A
├── Availability Zone B
└── Availability Zone C
```
When launching an EC2 instance, you choose both the Region and the Availability Zone.

# What is a VPC?

A **VPC (Virtual Private Cloud)** is your own private network inside AWS.

Every EC2 instance runs inside a VPC.

The VPC controls:

- Networking
- IP addresses
- Subnets
- Internet access
- Security

Think of a VPC as your own private data center inside AWS.

## Main Components of EC2

### 1. AMI (Amazon Machine Image)

An AMI is a template used to create an EC2 instance.

It contains:

- Operating System
- Required software
- Configuration

Examples:

- Ubuntu
- Amazon Linux
- Windows Server

Think of an AMI as installing Windows or Ubuntu on a brand-new laptop.

### 2. Instance Type

The Instance Type determines how powerful your virtual machine is.

Examples:

- t2.micro
- t3.micro
- t2.small

It determines:

- CPU
- Memory (RAM)
- Network performance
- Other hardware resources

Choose the instance type based on your application's requirements.

### 3. Key Pair

A Key Pair is used to securely connect to your EC2 instance.

It consists of:

- Public Key (stored in AWS)
- Private Key (.pem file downloaded by you)

Never share your private key.

Without the private key, you may not be able to securely connect to your Linux EC2 instance using SSH.

### 4. Security Group

A Security Group acts like a virtual firewall for your EC2 instance.

It controls:

- Who can access your instance
- Which ports are open
- Which traffic is allowed

By default, all inbound traffic is blocked unless you explicitly allow it by creating Security Group rules.

Common ports:

| Port | Purpose |
|------|----------|
| 22 | SSH (Linux) |
| 80 | HTTP |
| 443 | HTTPS |
| 3389 | RDP (Windows) |

### 5. Storage (EBS)

**Amazon EBS (Elastic Block Store)** is the virtual hard drive attached to your EC2 instance.

It stores:

- Operating system
- Files
- Applications
- Data

Even if you stop your EC2 instance, the EBS volume usually remains attached, so your data is preserved.

### 6. Public IP Address

AWS can assign a **Public IP Address** to an EC2 instance.

A Public IP allows you to connect to your EC2 instance from the internet.

### 7. Private IP Address

Every EC2 instance also receives a **Private IP Address**.

Private IP addresses are used for communication between AWS resources inside the same VPC.

Unlike Public IPs, Private IPs cannot be accessed directly from the internet.


### 8. Elastic IP

A normal Public IP address may change when you stop and start an EC2 instance.

An **Elastic IP** is a static public IP address that you can keep and reuse.

It is useful when you need a permanent public IP address for your server.

## EC2 Launch Workflow

Launching an EC2 instance generally follows these steps:

```
Choose an AMI
        │
        ▼
Choose an Instance Type
        │
        ▼
Configure Network (VPC/Subnet)
        │
        ▼
Add Storage (EBS)
        │
        ▼
Create or Select a Key Pair
        │
        ▼
Configure Security Group
        │
        ▼
Launch EC2 Instance
        │
        ▼
Connect using SSH or RDP
```

## EC2 Instance States

```
Launch
   │
   ▼
Pending
   │
   ▼
Running
   │
 ┌─┴───────────┐
 │             │
 ▼             ▼
Reboot      Stopping
               │
               ▼
            Stopped
               │
               ▼
            Starting
               │
               ▼
            Running

Terminate
   │
   ▼
Terminated
```

The important states are:

- **Pending** – Instance is launching.
- **Running** – Instance is active.
- **Stopping** – Instance is shutting down.
- **Stopped** – Instance is powered off but can be started again.
- **Starting** – Instance is booting up.
- **Terminated** – Instance has been permanently deleted.

## Stop vs Terminate

### Stop

- Instance shuts down.
- Can be started again later.
- Data stored on the EBS volume usually remains.
- Compute charges stop, but storage charges continue.

### Terminate

- Instance is permanently deleted.
- Cannot be recovered.
- Used when the instance is no longer needed.

## EC2 Pricing (Basic Idea)

With Amazon EC2, you primarily pay for:

- Instance Usage
- Instance type
- Storage (EBS)
- Data transfer (depending on usage)
- AWS Region

When an instance is stopped:

- Compute charges stop.
- Storage charges for EBS usually continue.

AWS also offers different pricing models, including:

- On-Demand
- Reserved Instances
- Spot Instances
- Savings Plans

## Amazon EC2 Instance Types and Their Use Cases

Amazon EC2 provides different instance types to support different kinds of applications and workloads.

Each instance type is designed for a specific purpose, allowing you to choose the one that best matches your performance and resource requirements.

## 1. General Purpose Instances (M5, T3)

These instances offer a balanced combination of CPU, memory, and networking.

### Common Use Cases

- Web servers
- Small databases
- Development and testing environments

## 2. Compute-Optimized Instances (C5, C6g)

These instances are built for applications requiring high processing power.

### Common Use Cases

- High Performance Computing (HPC)
- Scientific simulations
- Batch processing
- Compute-intensive applications

## 3. Memory-Optimized Instances (R5, X1)

These instances provide a large amount of memory.

### Common Use Cases

- In-memory databases
- Big data analytics
- High-performance computing

## 4. Storage-Optimized Instances (D2, I3)

These instances are designed for applications requiring fast, high-capacity storage.

### Common Use Cases

- NoSQL databases
- Data warehousing
- Elasticsearch
- Large-scale data processing

## 5. GPU Instances (G4, P3)

These instances include powerful Graphics Processing Units (GPUs).

### Common Use Cases

- Machine learning
- Deep learning
- Video rendering
- Gaming applications
- Graphics-intensive workloads

## 6. FPGA Instances (F1)

These instances use Field Programmable Gate Arrays (FPGAs), allowing custom hardware acceleration.

### Common Use Cases

- Genomics analysis
- Financial modeling
- Real-time video processing
