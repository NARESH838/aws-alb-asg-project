# VPC-Ready Highly Available Architecture using Application Load Balancer & Auto Scaling
# AWS Application Load Balancer with Auto Scaling Group

## Project Overview
This project demonstrates how to deploy a highly available web application using:
- Application Load Balancer (ALB)
- Auto Scaling Group (ASG)
- EC2 instances in private subnets
- Public and private subnets inside a VPC

## Architecture
- ALB deployed in public subnets
- EC2 instances deployed in private subnets
- Traffic flows: Internet → ALB → EC2
- EC2 instances have no public IPs

## Key AWS Services Used
- Amazon VPC
- Application Load Balancer
- Auto Scaling Group
- EC2
- Target Groups
- Security Groups

## Security Design
- ALB Security Group allows HTTP (80) from internet
- EC2 Security Group allows HTTP (80) only from ALB Security Group
- No direct SSH access to private EC2 instances

## Auto Scaling
- Launch Template with User Data to install Apache automatically
- ASG replaces unhealthy instances automatically

## Health Check
- ALB health check path: /
- Success code: 200

## Outcome
- Target group shows healthy instances
- ALB DNS URL successfully serves web content
