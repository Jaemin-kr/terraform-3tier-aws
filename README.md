# Terraform Project: 3-Tier Architecture on AWS

This project provides Terraform configurations to deploy a 3-tier architecture in an AWS environment. The architecture includes separate tiers for Web, Application (WAS), and Database, each residing in its own subnet. Below are the details of the infrastructure components and their configurations.


## Architecture Overview

The infrastructure is organized into three primary tiers:
1. **Web Tier**: Contains the web servers (EC2 instances) and associated networking components.
2. **Application (WAS) Tier**: Hosts the application servers (EC2 instances).
3. **Database Tier**: Manages the database resources (RDS instances).

### VPC and Subnets

A single VPC with CIDR `10.0.0.0/16` is used, and the tiers are segregated into individual subnets:

| Tier               | Subnet Name         | CIDR Block        |
|--------------------|---------------------|-------------------|
| **VPC**            | `dev-vpc`           | `10.0.0.0/16`     |
| **Web-Subnet-01**  | `dev-web-subnet01`  | `10.0.10.0/24`    |
| **WAS-Subnet-01**  | `dev-was-subnet01`  | `10.0.20.0/24`    |
| **DB-Subnet-01**   | `dev-db-subnet01`   | `10.0.30.0/24`    |
| **DB-Subnet-01**   | `dev-db-subnet02`   | `10.0.31.0/24`    |


### Routing Tables

Each tier has its own dedicated routing table for traffic control:

| Tier          | Routing Table Name  |
|---------------|---------------------|
| **Web Tier**  | `dev-web-rtb`       |
| **WAS Tier**  | `dev-was-rtb`       |
| **DB Tier**   | `dev-db-rtb`        |


### Security Groups

Security groups are defined to control access between the tiers and the external world:

| Security Group Name | Purpose                           |
|----------------------|-----------------------------------|
| `dev-web-sg`         | Web tier access control          |
| `dev-was-sg`         | Application tier access control  |
| `dev-db-sg`          | Database tier access control     |


### Servers and Resources

The infrastructure includes the following servers:

| Server Name | Description                   | Instance Type / Resource |
|-------------|-------------------------------|--------------------------|
| `dev-web`   | Web server (EC2 instance)     | EC2                      |
| `dev-was`   | Application server (EC2)      | EC2                      |
| `dev-db`    | Database server (RDS instance)| RDS                      |


## Usage

### Prerequisites

- Terraform installed on your local system
- AWS CLI configured with appropriate credentials
- Understanding resource of AWS services (VPC, EC2, RDS, IAM)

### Steps to Deploy(추가예정)

