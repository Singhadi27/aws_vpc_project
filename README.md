# AWS Production VPC with High Availability and Security

This project provides an example of how to create a Virtual Private Cloud (VPC) on Amazon Web Services (AWS) that is suitable for use in a production environment. The architecture emphasizes **high availability**, **resiliency**, and **security** by leveraging several key AWS services.

## Architecture Highlights

- **High Availability and Resiliency**: To ensure the application remains available, the servers are deployed across **two different Availability Zones**. This is achieved using an **Auto Scaling group**, which automatically manages the number of instances and can replace unhealthy ones, and an **Application Load Balancer** (ALB) to distribute incoming traffic.
- **Enhanced Security**: The servers are placed in **private subnets**, which means they are not directly accessible from the public internet. All incoming requests are routed through the public-facing Application Load Balancer.
- **Internet Connectivity for Servers**: While the servers are in private subnets, they still need to connect to the internet for tasks like software updates. This is made possible by a **NAT gateway** (Network Address Translation gateway), which is also deployed in **both Availability Zones** to maintain resiliency.

## Key AWS Services Used

- **Amazon VPC**: The foundational network environment.
- **Application Load Balancer (ALB)**: Distributes web traffic to your servers.
- **Auto Scaling Group**: Automatically scales the number of EC2 instances based on demand and health checks.
- **NAT Gateway**: Enables instances in a private subnet to connect to the internet.
- **EC2 Instances**: The virtual servers where your application will run.

## Getting Started

1. **Prerequisites**:
   - AWS Account
   - AWS CLI configured on your local machine (or use the AWS CloudShell)
   - Terraform or AWS CloudFormation (if you are using Infrastructure as Code)

2. **Deployment**:
   - *Instructions on how to deploy the project go here. This could be a series of CLI commands, a link to a CloudFormation template, or Terraform code.*

## Project Structure

- `main.tf` or `template.yaml`: Main infrastructure as code file.
- `variables.tf`: Input variables for the project.
- `outputs.tf`: Outputs of the deployed resources (e.g., Load Balancer URL).

## Contributing

Feel free to open issues or submit pull requests.

## License

This project is licensed under the MIT License.
