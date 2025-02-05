# Host-app-ECS-Blue-Green-Mode
Hosting an application in ECS cluster and deploying the changes using blue and green mode

## Introduction:
The application runs inside an ECS cluster, with the infrastructure hosted in a VPC for security and isolation. The CI/CD pipeline automates deployments—whenever new code is pushed to GitHub, the pipeline builds the container image, pushes it to ECR, and updates the ECS Fargate tasks without downtime.

When you create an Amazon ECS service that’s fronted by an Application Load Balancer (ALB), you typically designate a target group for your service. However, in this approach, we created two target groups:
🔹 One for the Blue version of the service.
🔹 One for the Green version of the service.

Each target group uses a different listener port, allowing both environments to run in parallel. This setup enables testing in the green environment without disrupting the live blue version. Access to the green version can be restricted, allowing only internal testers to verify the new deployment before it goes live.


## Architecture:
![Uploading image (3).png…]()


🔄 Blue/Green Deployment Strategy
🔹 It ensures high availability by deploying updates to a separate (green) environment before switching traffic from the current (blue) environment. This allows testing before making the new version live, reducing rollback risks and downtime.

🔹 When you’re ready to replace the old blue service with the new green service, call the ModifyListener API operation to swap the listener’s rules for the target group rules. The change happens within a few seconds. Afterward, the green service runs in the target group with the port 80 listener, while the blue service moves to the port 8080 listener.

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
