# NodeApp-ECS-GitAction

## Introduction
### This project demonstrates the deployment of a simple Node.js application to AWS Elastic Container Service (ECS) Fargate using GitHub Actions for Continuous Integration and Continuous Deployment (CI/CD).

## 🚀 Features
- Node.js Application: A basic Express.js server (index.js) serving as the application entry point.
- Dockerized: Containerization of the application using a Dockerfile.
- AWS ECS Fargate Deployment: Deployment to AWS ECS Fargate, a serverless compute engine for containers.
- GitHub Actions CI/CD: Automated build and deployment pipeline configured via GitHub Actions workflows.

## 📁 Project Structure
```
.
├── .github/
│   └── workflows/
│       └── deploy.yml         # GitHub Actions workflow for CI/CD
├── Dockerfile                 # Docker configuration file
├── GitAction-wala-task-revision1.json  # ECS task definition
├── index.js                   # Main application file
├── package.json               # Node.js dependencies and scripts
└── test.js                    # Test script for the application
```
## ⚙️ Setup Instructions

1. Clone the Repository
   ```
   git clone https://github.com/khotyash17/NodeApp-ECS-GitAction.git
   cd NodeApp-ECS-GitAction
   ```
2. Configure AWS Credentials
Set up your AWS credentials as secrets in your GitHub repository:
```
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_REGION (e.g., ap-south-1)
```
3. Define ECS Task Definition
The GitAction-wala-task-revision1.json file contains the ECS task definition. Ensure it aligns with your AWS ECS cluster configuration.

4. Configure GitHub Actions Workflow
```
The GitHub Actions workflow is defined in .github/workflows/deploy.yml. This workflow performs the following steps:
Checkout Code: Retrieves the latest code from the repository.
Set Up AWS Credentials: Configures AWS credentials for the session.
Login to Amazon ECR: Authenticates Docker to Amazon ECR.
Create a Repositorie: Give name eg: ecr-repo
Create cluster in AWS ECS: Give name eg: remarkable-crocodile
Create a task In AWS ECS: Give name eg: GitAction-wala-task
Ensure the workflow file is customized with your specific AWS resource names and configurations.
GitHub
```
## 🚀 Deployment
Once the setup is complete and the GitHub Actions workflow is configured, any push to the main branch will trigger the CI/CD pipeline:
1. In Github Repo Click on setting.
2. In setting - click on Environments.
3. Then click on production - In production - click on Environment secrets
4. Add AWS_Access_Key and AWS_Security_Key eg: AWS_ACCESS_KEY_ID , AWS_SECRET_ACCESS_KEY.
```
The application is built and containerized.
The Docker image is pushed to Amazon ECR.
The ECS service is updated with the new task definition, deploying the latest version of the application.
```

