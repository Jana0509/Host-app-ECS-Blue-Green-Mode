# Host-app-ECS-Blue-Green-Mode
Hosting an application in ECS cluster and deploying the changes using blue and green mode

## Introduction:
This project demonstrates building and deploying the containerized application in ECS cluster(Fargate mode) using CI/CD approach and Implemented Blue/Green Update to ECS. Here, When the code is pushed to the Github, build will trigger and deploy the new version of task to the Fargate containers. In order to avoid the downtime and make sure the application is highly available, we have implemented the deployment strategy in blue/green mode. Overall, Complete infrastructure is running in VPC for secure isolation for the resources.


## Architecture:

## Project Highlights:
1. Version Control : used GIT and Github for Versioning and storing the codebase.

2. Containerization : conatinerized the application using docker.

3. Docker: Used Docker to create the Container Image for the static Application

4. ECS Cluster : Deployed the EcS Cluster for Running the containers in High Availbility and fault tolerant Environment.

5. Elastic Container Registry (ECR) : Set up Amazon ECR to store Docker images for streamlined deployment to ECS.

6. Route 53 : Created the Domain and Hosted Zone for the application. Configured Alias to the Application Load balancer for DNS names

7. Load Balancer: Deployed a Network Load Balancer (NLB) in public subnets to distribute traffic across clusters in multiple AZs.

8. VPC Setup : Designed a custom VPC from scratch

9. Code build : Build and test the code.

10. Code Pipelines : To create the streamline process for the deployment of application.

## Key Learning Outcomes:

1. Understand and build the pipeline using Github, Code build and Code pipelines for the streamline deployment process of containerized application to the ECS cluster.

2. Understand the deployment strategies of blue/green and implemented for the ECS.Using a blue/green deployment strategy increases application availability and reduces deployment risk by simplifying the rollback process if a deployment fails. Once testing has been completed on the green environment, live application traffic is directed to the green environment and the blue environment is deprecated

3. Understand the CICD pipeline for the Containerized workloads.


## Conclusion:
This Project helps me in understanding and building the deployment pipelines and strategies for deploying the containerized workloads in ECS. It showcases how new changes flow from developer machine to the AWS cloud resources using pipelines and teached me how to deploy the new changes without affecting the live traffic.
