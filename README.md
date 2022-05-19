# Assessment
Infrastructure as Code - Python Flask

Prerequisites:
  1. An AWS Account with local credentials properly configured.
  2. The latest version of the AWS Command Line Interface (AWS CLI).
  3. Terraform 0.14.7+ installed on local workstation.
  4. Docker Desktop 3.1.0+ installed on local workstation.
  5. Python 3.6+ installed on local workstation.
  6. Boto3 installed on local workstation.
  
    Python has a number of web frameworks that can be used to create web apps and APIs. We have chosen to utilize Flask as it is a framework that has a set project structure as well as many built-in tools. These predefined structures can save time and effort for developers.
    We can utilize Python Flask to build an API. Python Flask is a micro framework for building web applications.

Application Build:
  1. Deploying the REST API to Amazon ECS
  2. Application will be hosted on an ECS cluster located in private subnets. 
  3. Users will access the application through an ALB.

Steps:

  1. Create an ECR repository
  2. Build the Docker image
  3. Tag the Docker image
  4. Push your newly created Docker image to ECR
  5. Deploy the image to ECR. 

Terraform - Infrastructure as Code(IaC):
    It is an open source software tool developed by Hashicorp. With Terraform, we can draft declarative configuration files in HashiCorp Configuration Language (HCL) to describe the desired state configuration for resources in various cloud environments. Terraform provides a means to define infrastructure as code on numerous platforms, including Amazon Web Services. 
    Terraform is used to deliver the infrastructure for running the container environment. 
    
    I used Terraform (Infrastructure as Code) for building a Infrastructure to implement a solution which will deploy the attached microservices to a functional state.
    
    Commands:
    
      1. terraform init:
            To initialize the working directory for Terraform on your workstation
      2. terraform plan:
            - terraform plan is used to create an execution plan.
            - terraform plan will show resources are being added, changed, or destroyed based on the provided variable inputs passed to the module      
                during execution. 
      3. terraform apply:
            It is the command used to change a desired target state for an environment.
            
   During terraform plan, it prompted for the ECR image path, we have to provide the frontend URI from the ECR repository
   
   Again terraform apply, it prompted for the ECR image path, we have to provide the frontend URI from the ECR repository
   
   After Apply complete there are 47 resources added. And it gives the output as ALB Dns Name. When we navigate to this address on the browser we can see the frontend microservice, which is index.html file will be executed.
