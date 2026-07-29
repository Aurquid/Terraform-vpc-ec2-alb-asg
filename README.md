# Terraform-vpc-ec2-alb-asg
This project mimics a production-style AWS environment utilizing Terraform.
It includes a VPC, public/private subnets,EC2 launce template, Application Load Balancer, and Auto Scaling Group.
The goal is to demonstrate real cloud engineering skills using infrastructure as code.

# Architecture Summary 
VPC with public + private subnets

Internet Gateway

(Optional) VPC Endpoints instead of NAT Gateway

EC2 Launch Template

Application Load Balancer

Auto Scaling Group

Security Groups

IAM Roles

CloudWatch monitoring

# Services Used
VPC

EC2

ALB

Auto Scaling

IAM

CloudWatch
# Folder Structure
Terraform
/terraform-vpc-ec2-alb-asg
   /modules
      /vpc
      /ec2
      /alb
      /asg
   /diagrams
   /python-automation
   README.md
   # Goals 
   Build production‑grade infrastructure

Use Terraform modules

Apply IAM least privilege

Add monitoring + logging

Document failure + recovery

Add cost + tradeoff analysis

Add business impact
