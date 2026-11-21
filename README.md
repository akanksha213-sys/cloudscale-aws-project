
# CloudScale – Highly Available & Scalable Web Application on AWS

## Project Overview

CloudScale is an AWS-based scalable web application designed to demonstrate the implementation of highly available cloud infrastructure using core AWS services.

The project focuses on deploying a Python Flask application across multiple Availability Zones, distributing incoming traffic through an Application Load Balancer, managing compute capacity with an Auto Scaling Group, and integrating a managed MySQL database using Amazon RDS.

The objective is to understand how real-world cloud infrastructure is designed, deployed, monitored, and maintained.

## Architecture

The infrastructure is deployed in the AWS Mumbai Region (`ap-south-1`).

**Architecture components:**

- Custom Amazon VPC
- Multiple Availability Zones
- Public and Private Subnets
- Application Load Balancer (ALB)
- Amazon EC2 instances
- Auto Scaling Group (ASG)
- Amazon RDS for MySQL
- Amazon S3 for application package storage
- Security Groups for network access control

## AWS Services Used

| AWS Service | Purpose |
|---|---|
| Amazon VPC | Isolated cloud networking |
| EC2 | Hosting Flask application |
| Application Load Balancer | Distributing incoming traffic |
| Auto Scaling Group | Managing EC2 instance capacity |
| Amazon RDS | Managed MySQL database |
| Amazon S3 | Storing application deployment package |
| Security Groups | Controlling inbound and outbound traffic |
| CloudWatch | Infrastructure monitoring |

## Infrastructure Design

### 1. Networking – Amazon VPC
- Created a custom VPC.
- Configured public and private subnets across two Availability Zones.
- Configured route tables and internet connectivity.
- Used Security Groups to control application and database access.

### 2. Application Deployment – Amazon EC2
- Deployed the Python Flask application on Amazon Linux 2023.
- Installed application dependencies.
- Configured the application to run as a systemd service.
- Used an application health endpoint (`/health`) for health verification.

### 3. Load Balancing – Application Load Balancer
- Configured an Application Load Balancer.
- Created listeners and target groups.
- Configured health checks to monitor application instances.
- Distributed incoming HTTP traffic across registered targets.

### 4. Auto Scaling – Auto Scaling Group
- Configured an Auto Scaling Group.
- Integrated the group with the Application Load Balancer.
- Configured instance launch settings to support automatic replacement and capacity management.

### 5. Database Integration – Amazon RDS
- Created an Amazon RDS MySQL database.
- Configured database connectivity from the application.
- Used environment-based configuration for database credentials.
- Restricted database access through Security Groups.

### 6. Application Package Storage – Amazon S3
- Stored the application deployment ZIP package in Amazon S3.
- Used the package as an application deployment artifact.

## Technology Stack

- **Cloud Platform:** AWS
- **Operating System:** Amazon Linux 2023
- **Application:** Python, Flask
- **Database:** MySQL
- **Web Infrastructure:** Application Load Balancer, EC2, Auto Scaling
- **Networking:** VPC, Subnets, Route Tables, Security Groups
- **Storage:** Amazon S3
- **Monitoring:** Amazon CloudWatch

## Key Learning Outcomes

Through this project, I gained practical experience in:

- Designing AWS networking infrastructure.
- Deploying applications on Linux-based EC2 instances.
- Configuring load balancing and target group health checks.
- Understanding Auto Scaling and instance replacement.
- Integrating Flask applications with Amazon RDS.
- Managing application deployment packages through S3.
- Troubleshooting application health and connectivity issues.
- Understanding the relationship between networking, compute, and database services.

## Project Structure

```text
CloudScale/
│
├── README.md
├── architecture/
│   └── architecture-diagram.png
│
├── screenshots/
│   ├── vpc.png
│   ├── ec2.png
│   ├── load-balancer.png
│   ├── auto-scaling.png
│   └── rds.png
│
├── application/
│   └── CloudScale-v1.0.zip
│
└── documentation/
    ├── implementation-guide.md
    └── troubleshooting.md
```

## Future Improvements

- Implement infrastructure provisioning using Terraform.
- Introduce CI/CD automation for application deployment.
- Configure HTTPS using AWS Certificate Manager.
- Improve monitoring with CloudWatch dashboards and alarms.
- Implement stronger secrets management.
- Explore containerization using Docker.

## Author

**Akanksha Kushwaha**

B.Tech – Computer Science & Data Science

Interested in Cloud Computing, AWS Solutions Architecture, Linux Administration, and Infrastructure Engineering.

---

*This project is part of my hands-on journey toward building practical cloud infrastructure and developing real-world AWS engineering skills.*
