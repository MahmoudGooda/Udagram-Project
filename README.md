# Udagram-Project
Deploying high-availability web app using AWS CloudFormation

## Description
Using AWS CloudFormation, created a script to deploy a highly available web app

## Work Flow
- Build a diagram to visualize main parts of the infrastructure and for better understanding the script. 
- Create network infrastructure components stack in a "YAML" formatted template.
- Create servers stack, security roles and software in a separate template.
- Using paramteters and outputs to make cloudformation templates more reusable (In both templates).

## Specifications
- Servers are distributed in multiple Availability Zones to make the app highly available.
- Created LaunchConfiguration for application servers to have at least four servers, two located in each AZ. 
- The launch configuration will be used by an Auto-Scaling Group.
- Each server will have two vCPUs, at least 4GB of RAM and at least 10GB volume size. The used Operating System is Ubuntu 18.
- Used a userdata script to install Apache2 server at instance launch.

## Security
- Servers will have ***Read Only*** access to S3 service. (In case needed to download any further app data).
- All  inbound traffic will be allowed only from **Port 80** in all resources (Security groups, health checks and listeners associated with the load balancer)
- Servers are located in private subnets so thery're not accessible from outside internet.
- Website is only accessible through the load balancer which is located in a public subnet.
- A Bastion host located in a public subnet is used to SSH web servers for maintainance purpose and it's accessible through SSH from ***My local IP address only***
