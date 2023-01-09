# Project-19
AUTOMATE INFRASTRUCTURE WITH IAC USING TERRAFORM. PART 4 – TERRAFORM CLOUD

By now, you should be pretty comfortable writing Terraform code to provision Cloud infrastructure using Configuration Language (HCL). Terraform is an open-source system, that you installed and ran a Virtual Machine (VM) that you had to create, maintain and keep up to date. In Cloud world it is quite common to provide a managed version of an open-source software. Managed means that you do not have to install, configure and maintain it yourself – you just create an account and use it "as A Service".

Terraform Cloud is a managed service that provides you with Terraform CLI to provision infrastructure, either on demand or in response to various events.

By default, Terraform CLI performs operation on the server whene it is invoked, it is perfectly fine if you have a dedicated role who can launch it, but if you have a team who works with Terraform – you need a consistent remote environment with remote workflow and shared state to run Terraform commands.

Packer is HashiCorp's open-source tool for creating machine images from source configuration. You can configure Packer images with an operating system and software for your specific use-case. Terraform configuration for a compute instance can use a Packer image to provision your instance without manual configuration

Packer is a tool for creating identical machine images for multiple platforms from a single source configuration file. It can build images for multiple cloud hosting platforms.

Terraform is an open source tool for building, changing, and versioning infrastructure safely and efficiently.


### Commenting some resourses out in order to have a smooth deployment
1. Comment out attcahing autoscalling group of nginx to ext load balancer @ asg-bastion-nginx.tf
2. comment out autoscalling group for wordpress and tooling to int load balancer @ asg-webservers

3. Comment out listerners @ ALB/alb.tf  for wordpress and tooling 

- Once the infra have been completed, update ansible script with values from teraform output in the below places 
    - RDS endpoints for wordpress and tooling
    - Database name, password and username for wordpress and tooling
    - Access point ID for wordpress and tooling
    - Internal load balancee DNS for nginx reverse proxy

### Note
- do aws configure on bastion to configure access key, secret key and set to the region where you have your infra before you run ansible play book

### fix boto error with below
-  python3 --version
- install boto3 ` pip3.9 install boto3`

- Terraform has a quite strong community of contributors (individual developers and 3rd party companies) that along with HashiCorp maintain a Public Registry, where you can find reusable configuration packages (modules). We strongly encourage you to explore modules shared to the public registry, specifically for this project – you can check out this AWS provider registry page.

- Public Module Registry vs Private Module Registry

- As your Terraform code base grows, your DevOps team might want to create your own library of reusable components – Private Registry can help with that.



