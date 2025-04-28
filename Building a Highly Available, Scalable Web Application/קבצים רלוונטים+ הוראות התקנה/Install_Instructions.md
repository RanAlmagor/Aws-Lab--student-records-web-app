# Install Instructions - Student Records Web Application

## Overview
This document outlines the steps taken to install and configure the Student Records web application on AWS.

## Installation Steps
1. Created a Virtual Private Cloud (VPC) with public and private subnets in two Availability Zones (us-east-1a, us-east-1b).
2. Launched EC2 instances (Ubuntu) using Amazon Machine Images (AMI) for the web application.
3. Installed Node.js and the application code using the provided script `SolutionCodePOC`.
4. Configured RDS MySQL database in a private subnet with multi-AZ enabled.
5. Migrated the database using `mysqldump` and `mysql` CLI tools.
6. Created a Load Balancer (Application Load Balancer) to distribute traffic across EC2 instances.
7. Configured Auto Scaling Group with min=2 and max=4 instances.
8. Used AWS Secrets Manager to securely store database credentials.
9. Connected the web application to the RDS database using secrets retrieved via IAM Role (LabInstanceProfile).

## How to Restart the Application
- Restart the EC2 instances through the Auto Scaling Group.
- Ensure that the RDS database instance is running.
- Ensure that the Load Balancer is active and pointing to healthy targets.

## Access URL
- **Load Balancer URL**: [http://student-records-web-alb-1943417712.us-east-1.elb.amazonaws.com/](http://student-records-web-alb-1943417712.us-east-1.elb.amazonaws.com/)
