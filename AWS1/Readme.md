# AWS Secure Web Application Infrastructure (3-Tier Architecture)

## Project Overview

This project demonstrates how to manually build a secure, scalable, and production-ready web application infrastructure using AWS services. Everything was created **from scratch** through the AWS Console — no automation tools — to get a deep understanding of cloud architecture and security best practices.

The application includes a Flask backend hosted on EC2, connected to an RDS database, behind an Application Load Balancer and CloudFront distribution.

---

## Architecture Summary

**Frontend**  
- Amazon S3 (static website)  
- CloudFront (CDN & HTTPS access)

**Application Layer**  
- EC2 (Flask API)
- Application Load Balancer (ALB)
- Auto Scaling Group

**Database Layer**  
- Amazon RDS (MySQL) in a private subnet

---

## AWS Services Used

| Category        | Service                                  | Purpose                                           |
|-----------------|------------------------------------------|---------------------------------------------------|
| Networking      | VPC, Subnets, Route Tables, NAT Gateway  | Isolated network setup with internet access       |
| Compute         | EC2, Auto Scaling, Launch Template       | Backend compute resources                         |
| Load Balancing  | Application Load Balancer (ALB)          | Traffic routing with HTTPS and target groups      |
| Storage         | S3                                        | Static hosting + CloudFront logs                  |
| CDN             | CloudFront                               | Global content delivery, HTTPS proxy              |
| Database        | Amazon RDS (MySQL)                       | Secure backend storage                            |
| Security        | IAM, Security Groups, Systems Manager    | Access control and secure instance management     |
| Monitoring      | CloudWatch, CloudWatch Agent             | Metrics, log collection and health checks         |
| Logging         | ALB & CloudFront Logs → S3 Bucket        | Traffic visibility and security monitoring        |

---

## Key Features

- Flask app served from EC2 and auto-scaled based on load
- RDS database connection over private subnets
- HTTPS support via CloudFront and ALB
- Logs from CloudFront and ALB saved to S3
- Real-time monitoring through CloudWatch & Agent
- Secure design with IAM roles and security groups
- Access to private EC2 via Systems Manager (no SSH)

---

## How It Works

1. Users access the site via CloudFront (HTTPS)
2. CloudFront forwards the request to the ALB
3. ALB routes the request to one of the EC2 instances
4. EC2 Flask app connects to RDS, fetches or writes data
5. Logs and metrics are pushed to CloudWatch and S3
6. Auto Scaling adds/removes EC2 instances when needed

---

## What I Learned

- How to build a complete infrastructure without templates
- How Auto Scaling and Load Balancing work together
- How to secure databases in private subnets
- How to troubleshoot with CloudWatch and IAM roles
- How CDN, logging and metrics enhance real-world security

---

## Future Improvements

- Add AWS WAF for web application protection
- Include Lambda + API Gateway for serverless API
- Add CI/CD pipeline with CodePipeline & GitHub
- Automate all infrastructure with CloudFormation

---

## Author Notes

This was a hands-on project to master AWS services related to architecture and security. Everything was built and tested manually — a real experience, not just theory.

---

