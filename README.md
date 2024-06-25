# Java Application CI/CD Pipeline with DevOps Tools

## Overview

This documentation outlines the steps taken to set up a Continuous Integration/Continuous Deployment (CI/CD) pipeline for a Java application using various DevOps tools.

## Workflow Diagram

![CI/CD Pipeline Workflow](/ci-cd.png)

## Tools Used

- **Git**: Version control system.
- **GitHub**: Repository hosting service.
- **Jenkins**: Continuous Integration server.
- **Maven**: Build automation tool.
- **SonarQube**: Continuous inspection tool for code quality.
- **Docker**: Containerization platform.
- **Trivy**: Vulnerability scanner for containers.
- **Argo CD**: Continuous Delivery tool for Kubernetes.
- **EKS (Elastic Kubernetes Service)**: Managed Kubernetes service by AWS.
- **Slack**: Messaging app for team communication.



## Workflow Steps

1. **Code Push to GitHub**
   - Developers push their code to the GitHub repository.

2. **Jenkins CI Job**
   - Jenkins is configured to pull the code from the GitHub repository.
   - Jenkins uses Maven to build and test the application.
   - Static code analysis is performed using SonarQube.

3. **Docker Image Creation and Scanning**
   - Upon successful build and test, Jenkins builds a Docker image and pushes it to Docker Hub.
   - The Docker image is scanned for vulnerabilities using Trivy.

4. **Updating Kubernetes Manifests**
   - The build number is updated in the Kubernetes (K8S) manifest files stored in a separate GitHub repository.

5. **Deployment with Argo CD**
   - Argo CD pulls the updated K8S manifest files.
   - The application is deployed to an EKS cluster.

6. **Notification to Slack**
   - Notifications about the deployment status are sent to a designated Slack channel.
Test93

