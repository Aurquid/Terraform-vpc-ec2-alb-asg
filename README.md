# Terraform-vpc-ec2-alb-asg
This project mimics a production-style AWS environment utilizing Terraform.
It includes a VPC, public/private subnets,EC2 launce template, Application Load Balancer, and Auto Scaling Group.
The goal is to demonstrate real cloud engineering skills using infrastructure as code.

# Table of Contents
* Overview

* Architecture Diagram

* Architecture Summary

* Services Used

* Folder Structure

* Deployment

* Terraform Modules

* IAM Least Privilege

* Monitoring & Logging

* Failure Scenario & Recovery Playbook

* Tradeoff Analysis

* Cost Breakdown

* Business Impact

* Lessons Learned

* Screenshots

# Architecture Diagram

# Architecture Summary 
* VPC with public + private subnets

* Internet Gateway

* (Optional) VPC Endpoints instead of NAT Gateway

* EC2 Launch Template

* Application Load Balancer

* Auto Scaling Group

* Security Groups

* IAM Roles

* CloudWatch monitoring

# Services Used
* VPC

* EC2

* ALB

* Auto Scaling

* IAM

* CloudWatch
  
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
   # Deployment
terraform init
terraform plan
terraform apply
# Terraform Modules
### VPC Module
* VPC

* Subnets

* Route tables

* IGW

* (Optional) VPC endpoints

### EC2 Module
* Launch template

* Security group

* IAM role

* User data

 ### ALB Module
  
* Load balancer

* Listener

* Target group

* Health checks

### ASG Module

* Auto Scaling Group

* Scaling policies

* ALB attachment
  # IAM Least Privilege
  * EC2 role with minimal permissions
 
  * SSM Role ( optional)
 
  * No wildcard policies
 
  * Resource-scoped policies
 
    # Monitoring and Logging
    * Cloudwatch metrics
   
    * Cloudwatch alarms
   
    * ALB access logs
   
    * EC2 system logs

   # Failure Scenario and Recovery Playbook
  ### Scenario : ALB health checks fail
  ### Root Cause: Incorrect security group or user data
  ###  Recovery Steps:
  1. Validate SG inbound rules
  2. Check EC2 user data logs
  3. Restart instand3 or redeploy
  4. Confirm ALB target health
  ### Prevention:
  * Add automated validation
  * Add Cloudwatch alarms
 <details>
<summary> Tradeoff Analysis</summary>

- EC2 vs Lambda  
- ALB vs NLB  
- NAT Gateway vs VPC Endpoints  
- t3.micro vs t4g.nano  

</details>

# Cost Breakdown 
| Component | Cost | Notes |
| --- | --- | --- |
| EC2 t4g.nano | ~$3/mo | cheapest option |
| ALB | ~$16/mo | delete when not testing |
| VPC | $0 | free |
| Endpoints | $0 | free |
# Business Impact
* Cost-efficent scaling
  
* Reduced downtime risk

* Improved reliability

* Lower operational overhead

* Strong security posture

  # Lessons Learned

  * Importance of modular Terraform
 
  * Value of IAM  least privilege
 
  * How ALB  health checks behave
 
  * How to optimize cloud cost
 
  # Screenshots
 
